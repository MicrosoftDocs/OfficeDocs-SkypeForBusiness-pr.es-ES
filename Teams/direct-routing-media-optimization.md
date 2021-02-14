---
title: Optimización de medios locales de enrutamiento directo
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 04/07/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: filippse
search.appverid: MET150
f1.keywords:
- NOCSH
description: Optimización de medios locales para enrutamiento directo
appliesto:
- Microsoft Teams
ms.openlocfilehash: 886dd4d14d8393764f3c939991a8959ed4726aa3
ms.sourcegitcommit: b816ae9de91f3d01e795a69a00465a70003069b2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/16/2020
ms.locfileid: "49686466"
---
# <a name="local-media-optimization-for-direct-routing"></a>Optimización de medios locales para enrutamiento directo

La voz de red telefónica conmutada (RTC) se considera una aplicación crítica para la empresa con grandes expectativas para la calidad de la voz. El enrutamiento directo le permite controlar los flujos de tráfico de medios para dar cabida a una multitud de topologías de red y configuraciones de telefonía local para varias empresas de todo el mundo. 

La optimización de medios locales para enrutamiento directo le permite administrar la calidad de voz mediante:

-   Controlar cómo fluye el tráfico multimedia entre los clientes de Teams y los controladores de borde de sesión (SBCs) del cliente.
-   Mantener los medios locales dentro de los límites de las subredes de red corporativas.
-   Permitir transmisiones multimedia entre los clientes de Teams y las OSN incluso si las sbcs están detrás de los firewalls corporativos con IP privadas y no son visibles para Microsoft directamente.

La optimización de medios locales admite dos escenarios:

- Centralización de todos los troncos locales a través de un SBC centralizado conectado al tronco principal del Protocolo de inicio de sesión (SIP), lo que proporciona servicios de telefonía a todas las sucursales locales de la empresa.

-   Crear una topología de red virtual de SBC, donde los SBC de las sucursales locales están conectados a un SBC proxy centralizado visible para Microsoft Phone System a través de su dirección IP externa y comunicarse con él. En una topología de red virtual, los SSS de bajada se comunican a través de IP internas y no son visibles directamente para Sistema telefónico.

En este artículo se describen la funcionalidad de las características, así como los escenarios y soluciones de los clientes. Para obtener más información sobre la configuración, vea [Configurar optimización de medios locales.](direct-routing-media-optimization-configure.md) 

  > [!NOTE]
  > Si quiere mantener los medios locales dentro de los límites de la intranet, se recomienda optimizar los medios locales. Si ya tiene omita medios y use solo las direcciones IP públicas de sus sbcs, no es obligatorio pasar a la optimización de medios locales. Puede seguir usando Media Bypass. Para obtener más información, vea [Plan de omisión de medios.](direct-routing-plan-media-bypass.md)


## <a name="supported-customer-scenarios"></a>Escenarios de clientes admitidos

Para esta discusión, suponga que Contoso administra varias empresas en todo el mundo de la manera siguiente. (Tenga en cuenta que las regiones de Europa y APAC solo se usan como ejemplos. Una empresa puede tener varias regiones diferentes con requisitos similares).
 
- **En Europa,** Contoso tiene oficinas en aproximadamente 30 países. Cada oficina tiene su propia central de conmutación (PBX). 

  Contoso tenía la opción de centralizar los troncos en una ubicación(Ámsterdam) para las 30 oficinas europeas. Contoso implementó el SBC en Ámsterdam, proporcionó ancho de banda suficiente para realizar llamadas a través de la ubicación centralizada, conectó un tronco SIP central a la ubicación centralizada y comenzó a servir a todas las ubicaciones europeas desde Ámsterdam. 

- **En la región APAC,** Contoso tiene varias oficinas en diferentes países. 

  En muchos países, la compañía todavía tiene troncos de multiplexación de división de tiempo (TDM) en las sucursales locales. La centralización de los troncos TDM no es una opción en la región APAC, por lo que no es posible cambiar a SIP. Suponga que hay más de cincuenta sucursales de Contoso en la región de APAC con cientos de puertas de enlace (SBCs). En este escenario, no es posible emparejar todas las puertas de enlace con la interfaz de enrutamiento directo debido a la falta de direcciones IP públicas o de saltos de Internet locales. Además, algunos países imponen requisitos normativos que no se pueden cumplir sin tener conectividad de red RTC local.

Según los requisitos empresariales, Contoso implementó dos soluciones con la optimización de medios locales para enrutamiento directo:

- **En Europa,** todos los troncos están centralizados y los flujos de medios entre la central SBC y los usuarios, en función de la ubicación del usuario. 

  - Si un usuario está conectado a la subred local de una red corporativa (es decir, el usuario es interno), los medios fluyen entre la DIRECCIÓN IP interna de la central SBC y el cliente de Teams del usuario. 
  
  - Si un usuario está fuera de los límites de la red corporativa (por ejemplo, si el usuario está usando una conexión a Internet inalámbrica pública), entonces se considera que el usuario es externo. En este caso, los medios fluyen entre la DIRECCIÓN IP externa del SBC central y el cliente de Teams.

- En la **región APAC,** un servidor proxy centralizado SBC está emparejado con El enrutamiento directo de Microsoft, que dirige los medios entre la interfaz de enrutamiento directo y los SBC de bajada en las sucursales locales. 

  Las sbcs de bajada en las sucursales locales no están directamente visibles para enrutamiento directo en APAC, pero están emparejadas mediante el uso del cmdlet Set-CSOnlinePSTNGateway para crear una topología de red virtual dentro de Microsoft Phone System. Siempre que sea posible, los medios permanecen en su configuración local. Los usuarios externos tienen medios que fluyen entre el cliente de Teams y la DIRECCIÓN IP pública del SBC del proxy.


## <a name="central-sbc-with-centralized-trunks"></a>Central SBC con troncos centralizados

Para crear una solución en la que se proporcionan servicios RTC a todas las sucursales locales a través de un único SBC central con un tronco SIP centralizado conectado, el administrador de inquilinos de Contoso empareja un SBC (centralsbc.contoso.com) al servicio; la SBC tiene un tronco SIP centralizado conectado a él. 

- Cuando un usuario está en la red interna de la compañía, SBC proporciona la IP interna del SBC para los medios. 

- Cuando un usuario está fuera de la red corporativa, SBC proporciona la IP externa (pública) de la SBC.

Nota: Todos los valores de ejemplos, tablas o diagramas se presentan únicamente con fines de ilustración.

Tabla 1. Parámetros de red de ejemplo para sbCs 

| Ubicación | SBC FQDN | Subred interna | NAT externa (IP de confianza) | Dirección IP externa SBC | Dirección IP interna de SBC |
|:------------|:-------|:-------|:-------|:-------|:-------|
| Ámsterdam | centralsbc.contoso.com | 192.168.5.0/24 | 172.16.76.73 | 172.16.76.71 | 192.168.5.5 |
| Alemania | No implementado | 192.168.6.0/24 | 172.16.76.74 | No implementado |  No implementado |
| Francia | No implementado | 192.168.7.0/24 | 172.16.76.75 | No implementado |  No implementado ||||


### <a name="internal-user"></a>Usuario interno

El siguiente diagrama muestra el flujo de tráfico cuando un usuario está conectado a la red corporativa en la sucursal o el sitio del usuario. 

Mientras que local, se asigna al usuario la sucursal local en Alemania. El usuario realiza una llamada telefónica de enrutamiento directo a través de Teams.

- El cliente de Teams del usuario se comunica al sistema telefónico directamente a través de la API de REST, pero los medios generados durante el flujo de llamadas a la dirección IP interna del SBC central. 

- La SBC redirige el flujo a Sistema telefónico y a la red RTC conectada. 

- Sistema telefónico puede ver la central SBC solo a través de la dirección IP externa. 

Diagrama 1. Flujo de tráfico cuando el usuario está en el sitio "hogar" con un SBC centralizado y con un tronco SIP centralizado conectado

![Diagrama que muestra la optimización de medios locales de flujo de tráfico](media/direct-routing-media-op-1.png "Flujo de tráfico cuando el usuario está en el sitio "hogar" con SBC centralizado con tronco SIP centralizado conectado")


### <a name="external-user"></a>Usuario externo

El siguiente diagrama muestra el flujo de tráfico cuando un usuario no está local y no está conectado a la red corporativa (es decir, el dispositivo del usuario está conectado a Internet a través de un dispositivo móvil o una red Wi-Fi pública). El usuario realiza una llamada telefónica de enrutamiento directo a través de Teams:

- El cliente de Teams del usuario se comunica al sistema telefónico directamente a través de la API de REST, pero, en este caso, los medios generados durante los flujos de llamada a la dirección IP externa de la central SBC. 

- La SBC redirige el flujo a Sistema telefónico y a la red RTC conectada. 

- Sistema telefónico puede ver la central SBC solo a través de la dirección IP externa. 

En este caso, el comportamiento es similar tanto si el usuario es local en la sucursal en Alemania como en cualquier otra sucursal. El usuario se considera externo porque se encuentra fuera de los límites de la red corporativa.

Diagrama 2. Flujo de tráfico cuando el usuario está externo con un SBC centralizado y con un tronco SIP centralizado conectado

![Diagrama que muestra la optimización de medios locales de flujo de tráfico](media/direct-routing-media-op-2.png "Flujo de tráfico cuando el usuario está externo en caso de SBC centralizado con tronco SIP centralizado conectado")

## <a name="proxy-sbc-with-connected-downstream-sbcs"></a>SBC del proxy con SBCs de bajada conectados

Para crear una solución en la que los servicios RTC se proporcionan en todas las sucursales locales de la región APAC, donde la centralización de los troncos TDM no es una opción, el administrador de Contoso empareja un SBC (proxysbc.contoso.com), también denominado SBC proxy, al servicio de enrutamiento directo. 

Posteriormente, el administrador de Contoso agrega algunos SBC de bajada que indican que se puede llegar a ellos a través del SBC proxy proxysbc.contoso.com. Sin embargo, los sbcs de bajada no tienen IP públicas, pero se pueden asignar a las rutas de voz. En la tabla siguiente se muestran ejemplos de parámetros de red y configuración.

Cuando un usuario está en la sucursal local donde se encuentra la SBC descendente, el tráfico multimedia fluye entre el usuario y el SBC local descendente directamente. Si un usuario está fuera de la oficina (en una Internet pública), los medios fluyen desde el usuario a la DIRECCIÓN IP pública del SBC del proxy, que lo proxy lo asigna a los SBC de bajada relevantes.

Tabla 2. Ejemplo de información de red SBC

| Ubicación | SBC FQDN | Subred interna | NAT externa (IP de confianza) | Dirección IP externa SBC  | Dirección IP interna de SBC |
|:------------|:-------|:-------|:-------|:-------|:-------|
| Vietnam | VNsbc.contoso.com | 192.168.1.0/24 | 172.16.240.110 | Ninguna |  192.168.1.5 |
| Indonesia  | IDsbc.contoso.com | 192.168.2.0/24 | 172.16.240.120 | Ninguna |  192.168.2.5 |
| Singapur | proxysbc.contoso.com |   192.168.3.0/24 | 172.16.240.130 | 172.16.240.133 | 192.168.3.5 |



### <a name="internal-user"></a>Usuario interno 

El siguiente diagrama muestra el flujo de tráfico de alto nivel para el escenario cuando un usuario está dentro de la oficina en la región APAC. El usuario, que está asignado a una sucursal local en Vietnam y está en local, realiza una llamada telefónica de enrutamiento directo a través de Teams. 

- El cliente de Teams del usuario se comunica con Sistema telefónico directamente a través de la API de REST, pero los medios que se generan durante el flujo de llamadas a la dirección IP interna de SBC local.

- La SBC local redirige el flujo al SBC proxy en Singapur y a la red RTC local conectada.

-  The proxy SBC is visible to Phone System through the external IP address only and routes the flow from the downstream SBC (in this case the local SBC in Vietnam) to Phone System. 

- La SBC descendente en la sucursal local no es visible para Sistema telefónico directamente, sino que se asigna dentro de la topología de red virtual definida por el administrador de Contoso al configurar la optimización de medios locales.

Nota: El comportamiento puede ser diferente para usuarios locales y usuarios no locales, según el modo de optimización de medios locales configurado. 

Para obtener más información sobre los posibles modos y el comportamiento relevante, vea Configurar la optimización de medios locales.

Diagrama 3. Flujo de tráfico cuando el usuario está en la red "doméstica" con un SBC proxy y con SBC conectados de bajada 

![Diagrama que muestra la optimización de medios locales de flujo de tráfico](media/direct-routing-media-op-3.png "Flujo de tráfico en el caso de SBC del proxy con SBC conectado de bajada cuando el usuario está en la red "doméstica".")

### <a name="external-user"></a>Usuario externo

El siguiente diagrama muestra el flujo de tráfico cuando un usuario está fuera de los límites de la red corporativa. El usuario no es local (no está dentro de los límites de la red corporativa). El usuario realiza una llamada de enrutamiento directo a través de Teams a un número de teléfono en Vietnam. 

- El cliente de Teams del usuario se comunica con Sistema telefónico directamente a través de la API REST, pero los medios que se generan durante la llamada fluyen primero a la dirección IP externa del servidor proxy SBC en Singapur. 

- Según las directivas de [](direct-routing-media-optimization-configure.md) configuración y voz (consulte Configurar optimización de medios locales para obtener más información), el SBC del proxy redirige el flujo al SBC descendente en Vietnam. 

- La secuencia descendente de SBC en Vietnam redirige el flujo a la red RTC local conectada. 

- El SBC del proxy está visible para Sistema telefónico solo a través de la dirección IP externa.

-  La SBC descendente en la sucursal local no es visible para Sistema telefónico directamente, sino que se asigna dentro de la topología de red virtual definida por el administrador de Contoso al configurar la optimización de medios locales. En el ejemplo, el usuario se considera externo porque está fuera de los límites de la red corporativa. 

Diagrama 4. Flujo de tráfico cuando el usuario es externo con un SBC proxy y con SBCs conectados de bajada

![Diagrama que muestra la optimización de medios locales de flujo de tráfico](media/direct-routing-media-op-4.png "Flujo de tráfico en el caso de SBC del proxy con SBC conectado de bajada cuando el usuario es externo")

## <a name="local-media-optimization-modes"></a>Modos de optimización de medios locales

La optimización de medios locales admite dos modos:

- **Modo 1: Omitir siempre.** En este caso, si el usuario es interno, los medios fluirán por la dirección IP interna de SBC local descendente independientemente de la ubicación real del usuario interno; por ejemplo, dentro de la misma sucursal donde se encuentra la SBC de bajada o en alguna otra sucursal.  

- **Modo 2: Solo para usuarios locales.** In this mode, media will flow directly to the local downstream SBC's internal IP address only when generated by the internal user located in the same branch office as the downstream SBC. 

Para distinguir entre los modos de optimización de medios locales, el administrador de inquilinos debe establecer el parámetro -BypassMode en "Always" o "OnlyForLocalUsers" para cada SBC usando el cmdlet Set-CSonlinePSTNGateway. Para obtener más información, vea [Configurar la optimización de medios locales.](direct-routing-media-optimization-configure.md)  

 > [!NOTE]
  > Cuando los usuarios son internos, se requiere la conectividad multimedia entre el usuario y el SBC a través de la dirección IP **interna.** No hay ninguna reserva de retransmisión de transporte público para los medios en este caso, ya que la SBC estará proporcionando una DIRECCIÓN IP interna para la conectividad multimedia. 

### <a name="mode-1-always-bypass"></a>Modo 1: Omitir siempre

Si tiene una buena conexión entre sucursales, el modo recomendado siempre se omite.
 
Por ejemplo, supongamos que una compañía tiene un tronco SIP centralizado en Ámsterdam, que sirve a 30 países y tiene una buena conectividad entre los 30 sitios y los usuarios locales. También hay una rama en Alemania donde hay implementado un SBC local.

La SBC en Alemania se puede configurar en modo de "omisión siempre". Los usuarios, independientemente de su ubicación, se conectarán a la SBC directamente a través de la dirección IP interna de la SBC (por ejemplo, de Francia a Alemania; consulte el diagrama siguiente para consultarlo).

A continuación se describen dos escenarios:

- Escenario 1. El usuario se encuentra en la misma ubicación que el SBC definido en la directiva de enrutamiento de voz en línea.

- Escenario 2. El usuario y las puertas de enlace se encuentran en sitios diferentes.

#### <a name="scenario-1-the-user-is-in-the-same-location-as-the-sbc-defined-in-the-online-voice-routing-policy"></a>Escenario 1. El usuario se encuentra en la misma ubicación que el SBC definido en la directiva de enrutamiento de voz en línea.

El SBC de Ámsterdam está configurado para ser un SBC proxy para un SBC local de bajada en Alemania. El usuario se encuentra en Alemania dentro de la misma subred que la red corporativa de la SBC local. Ambos SCS (proxy y corriente abajo) se configuran para el modo de omisión siempre. Las directivas de enrutamiento de voz en línea especifican que, en el caso de llamadas dentro de Alemania (con el código de área +49), deberían dirigirse a la SBC local en Alemania. Todas las demás llamadas (y, en caso de que se produce un error en la SBC en Alemania, las llamadas en Alemania) deberían dirigirse al SBC proxy en Ámsterdam. En la tabla siguiente se resume la configuración de ejemplo. 

Tabla 3. Configuración de ejemplo para el escenario 1

| Ubicación física del usuario | El usuario realiza una llamada a un número | Directiva de enrutamiento de voz en línea | Modo configurado para SBC | Media Flow | 
|:------------|:-------|:-------|:-------|:-------|
| Alemania | +49 1 437 2800 | Prioridad 1: ^ \+ 49(\d {8} )$ -DEsbc.contoso.com<br>Prioridad 2: .* - proxysbc.contoso.com| DEsbc.contoso.com– Omitir siempre <br>proxysbc.contoso.com– Omitir siempre | Aplicación de usuario < Teams > DEsbc.contoso.com |

El siguiente diagrama muestra el flujo de tráfico de alto nivel para el usuario interno en Alemania que realiza una llamada telefónica de enrutamiento directo a través de Teams al número en Alemania. 

- El cliente de Teams del usuario se comunica con Sistema telefónico directamente a través de la API de REST. 

- Los medios generados durante el flujo de llamadas a la dirección IP interna de SBC local. 

- La SBC local redirige el flujo al SBC proxy en Ámsterdam y a la red RTC local conectada. 

- The proxy SBC is visible to Phone System through the external IP address only and routes the flow from the downstream SBC (in this case, the local SBC in Germany) to Phone System. 

- La SBC descendente en la sucursal local no es visible para Sistema telefónico directamente, sino que se asigna dentro de la topología de red virtual definida por el administrador de Contoso al configurar la optimización de medios locales.


Diagrama 5.  Flujo de tráfico con el modo "Omitir siempre" y el usuario está en el sitio "principal"

![Diagrama que muestra la optimización de medios locales de flujo de tráfico](media/direct-routing-media-op-5.png "Flujo de tráfico con el modo "Omitir siempre" y el usuario está en el sitio "principal"")


#### <a name="scenario-2-the-user-and-gateways-are-in-different-sites"></a>Situación 2: El usuario y las puertas de enlace se encuentran en sitios diferentes

El SBC de Ámsterdam está configurado para ser un SBC proxy para un SBC local de bajada en Alemania. Ambos SCS (proxy y corriente abajo) se configuran para el modo de omisión siempre. El usuario interno en Francia, ubicado en la sucursal local, está realizando una llamada de enrutamiento directo a Alemania. Las directivas de enrutamiento de voz en línea especifican que las llamadas a Alemania (con el código de área +49) se enrutar a la SBC local en Alemania. Todas las demás llamadas (y, en caso de que se produce un error en la SBC en Alemania, todas las llamadas en Alemania) deberían dirigirse al SBC proxy en Ámsterdam. En la tabla siguiente se resume la configuración de ejemplo. 

Tabla 4. Configuración de ejemplo para el escenario 2

| Ubicación física del usuario | El usuario realiza una llamada a un número | Directiva de enrutamiento de voz en línea | Modo configurado para SBC | Media Flow | 
|:------------|:-------|:-------|:-------|:-------|
| Francia | +49 1 437 2800 | Prioridad 1: ^ \+ 49(\d {8} )$ -DEsbc.contoso.com <br>Prioridad 2: .* - proxysbc.contoso.com |  DEsbc.contoso.com – Omitir siempre proxysbc.contoso.com – Omitir siempre | Aplicación para < Teams: > DEsbc.contoso.com  |

El siguiente diagrama muestra el flujo de tráfico de alto nivel cuando el usuario interno alemán ubicado en Francia realiza una llamada telefónica de enrutamiento directo a través de Teams al número en Alemania. 

- El cliente de Teams del usuario se comunica con Sistema telefónico directamente a través de la API de REST.

- Los medios generados durante la llamada fluyen directamente a la SBC en la dirección IP interna de Alemania. 

- La SBC en Alemania redirige el flujo a la SBC proxy en Ámsterdam y a la red RTC local conectada. 

Diagrama 6.  Flujo de tráfico con el modo "Omitir siempre" y el usuario no está en el sitio "hogar", sino en la red interna

![Diagrama que muestra la optimización de medios locales de flujo de tráfico](media/direct-routing-media-op-6.png "El flujo de tráfico con el modo "Omitir siempre" y el usuario no está en el sitio "hogar", sino en la red interna.")

### <a name="mode-2-only-for-local-users"></a>Modo 2: Solo para usuarios locales

Si hay conexiones malas entre sucursales locales pero conexiones buenas entre cada sucursal local y oficina regional, entonces el modo recomendado es "Solo para usuarios locales".

Por ejemplo, en la región APAC, supongamos que Contoso tiene varias oficinas en diferentes países. Para muchos países, no es posible cambiar a SIP porque la compañía todavía tiene troncos TDM en muchas sucursales locales. La centralización de los troncos TDM no es una opción en la región APAC. Además, hay más de cincuenta sucursales de Contoso en la región de APAC con cientos de puertas de enlace (SBCs). 

Para crear una solución en la que los servicios RTC se proporcionan en todas las sucursales locales de la región APAC donde la centralización de los troncos TDM no es una opción, el administrador de Contoso empareja un SBC regional en Singapur como SBC proxy al servicio de enrutamiento directo. La conexión directa entre las sucursales locales no es buena, pero hay una buena conexión entre cada sucursal local y el SBC regional en Singapur. Para la SBC regional, el administrador elige "Omitir siempre" el modo y, para los SBC locales descendentes, el administrador elige "Solo para usuarios locales".

A continuación se describen dos escenarios:

- Escenario 1. El usuario se encuentra en la misma ubicación que el SBC definido en la directiva de enrutamiento de voz en línea.

- Escenario 2. El usuario y las puertas de enlace se encuentran en diferentes sitios

#### <a name="scenario-1-the-user-is-in-the-same-location-as-the-sbc-defined-in-online-voice-routing-policy"></a>Escenario 1. El usuario se encuentra en la misma ubicación que el SBC definido en la directiva de enrutamiento de voz en línea.

Suponga que la SBC en Singapur está configurada para ser un SBC proxy para los SBC locales de bajada en Vietnam e Indonesia. El usuario está en Vietnam dentro de la misma ubicación que la SBC local. Las directivas de enrutamiento de voz en línea especifican que las llamadas en Vietnam (con el código de área +84) se enrutan a la SBC local en Vietnam. Todas las demás llamadas (y, si se produce un error en la SBC en Vietnam, las llamadas en Vietnam) deberían dirigirse al SBC proxy en Singapur. En la tabla siguiente se resume la configuración de ejemplo. 

Tabla 5. Configuración de ejemplo para el escenario 1 de modo "Solo para usuarios locales"

| Ubicación física del usuario | El usuario realiza una llamada a un número | Directiva de enrutamiento de voz en línea | Modo configurado para SBC | Media Flow | 
|:------------|:-------|:-------|:-------|:-------|
| Vietnam | +84 4 3926 3000 | Prioridad 1: ^ \+ 84(\d {9} )$ -VNsbc.contoso.com <br>Prioridad 2: .* - proxysbc.contoso.com | VNsbc.contoso.com: solo para usuarios locales <br> proxysbc.contoso.com– Omitir siempre | Aplicación de usuario < Teams > VNsbc.contoso.com |

En el siguiente diagrama, un usuario asignado a la sucursal local en Vietnam, mientras que está de forma local, realiza una llamada telefónica de enrutamiento directo a través de Teams. 

- El cliente de Teams del usuario se comunica con Sistema telefónico directamente a través de la API de REST. 

- Medios generados durante los flujos de llamada a la dirección IP interna de SBC local. 

- La SBC local redirige el flujo al SBC proxy en Singapur y a la red RTC local conectada. 

- The proxy SBC is visible to Phone System through the external IP address only and routes the flow from the downstream SBC (in this case, the local SBC in Vietnam) to Phone System. 

- La SBC descendente en la sucursal local no es visible para Sistema telefónico directamente, pero se asigna dentro de la topología de red virtual.

Diagrama 7. Flujo de tráfico con el modo "Solo para usuarios locales" y el usuario está en el sitio "hogar"

![Diagrama que muestra la optimización de medios locales de flujo de tráfico](media/direct-routing-media-op-7.png "Flujo de tráfico con el modo "Solo para usuarios locales" y el usuario está en el sitio "local"")


#### <a name="scenario-2-the-user-and-gateways-are-in-different-sites"></a>Escenario 2. El usuario y las puertas de enlace se encuentran en diferentes sitios

Suponga que la SBC en Singapur está configurada para ser un SBC proxy para los SBC locales de bajada en Vietnam e Indonesia. El usuario interno en Indonesia, ubicado en la sucursal local, está realizando una llamada directa a Vietnam. Las directivas de enrutamiento de voz en línea especifican que las llamadas a Vietnam (con el código de área +84) se enrutan a la SBC local en Vietnam. Todas las demás llamadas (y, en caso de que la SBC en Vietnam falle, las llamadas a Vietnam) deberían dirigirse al SBC proxy en Singapur. El SBC proxy en Singapur está establecido en el modo "Omitir siempre" y el SBC local en Vietnam está establecido en el modo "Solo para usuarios locales". En la tabla siguiente se resume la configuración de ejemplo. 

Tabla 6. Configuración de usuario

| Ubicación física del usuario | El usuario realiza una llamada a un número | Directiva de enrutamiento de voz en línea | Modo configurado para SBC | Media Flow | 
|:------------|:-------|:-------|:-------|:-------|
| Indonesia | +84 4 3926 3000 | Prioridad 1: ^ \+ 84(\d {9} )$ -VNsbc.contoso.com <br> Prioridad 2: .* - proxysbc.contoso.com |VNsbc.contoso.com: solo para usuarios locales <br> proxysbc.contoso.com– Omitir siempre | Los administradores < de > proxysbc.contoso.com < teams > VNsbc.contoso.com |


En el siguiente diagrama, el usuario interno, mientras esté en las instalaciones de la sucursal de Indonesia, realiza una llamada de enrutamiento directo a través de Teams a un número en Vietnam. 

- El cliente de Teams del usuario se comunica con Sistema telefónico directamente a través de la API de REST.

- Los medios generados durante los flujos de llamada a la dirección IP interna del proxy SBC en primer lugar. 

- The proxy SBC in Singapore redirects the flow to the internal IP address of the downstream SBC in Vietnam and to Phone System. 

- La secuencia descendente de SBC en Vietnam enruta el flujo a la red RTC local conectada. 

- El SBC del proxy está visible para Sistema telefónico solo a través de la dirección IP externa.

- Las sbcs de bajada de las sucursales locales no son visibles para Sistema telefónico directamente, pero se asignan dentro de la topología de red virtual.

Diagrama 8.  Flujo de tráfico con el modo "Solo para usuarios locales" y el usuario no está en el sitio "hogar", sino en la red interna.

![Diagrama que muestra la optimización de medios locales de flujo de tráfico](media/direct-routing-media-op-8.png "Flujo de tráfico con el modo "Solo para usuarios locales", el usuario no está en el sitio "hogar", sino en la red interna.")

## <a name="known-issues"></a>Problemas conocidos

A continuación se muestra una lista de problemas conocidos que están presentes actualmente en la optimización de medios locales. Microsoft está trabajando para solucionar estos problemas.

| Problema | Solución alternativa |
| :--- | :--- |
| El cliente de Teams no se identifica como interno **cuando** la IP pública del cliente de Teams coincide con la lista de IP de confianza del cliente. | La optimización de medios locales requiere que la subred del cliente de Teams coincida con una subred de red configurada [por el inquilino.](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps)|
| Las escalaciones de llamadas resultan en llamadas que se descartan cuando el cliente de Teams se identifica como interno.| Deshabilite la optimización de medios locales en el SBC de enrutamiento directo.|


