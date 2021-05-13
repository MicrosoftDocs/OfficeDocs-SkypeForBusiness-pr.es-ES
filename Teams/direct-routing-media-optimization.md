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
ms.openlocfilehash: aab38cb7f844764faac0e9c19bc03110adac9c10
ms.sourcegitcommit: 50ec59b454e751d952cde9fd13c8017529d0e1d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2021
ms.locfileid: "52469672"
---
# <a name="local-media-optimization-for-direct-routing"></a>Optimización de medios locales para enrutamiento directo

La voz de red telefónica conmutada (RTC) se considera una aplicación crítica para la empresa con grandes expectativas de calidad de voz. Enrutamiento directo le permite controlar los flujos de tráfico multimedia para dar cabida a multitud de topologías de red y configuraciones de telefonía local para varias empresas de todo el mundo. 

Optimización de medios locales para enrutamiento directo le permite administrar la calidad de voz mediante:

-   Controlar cómo fluye el tráfico multimedia entre los Teams y los controladores de borde de sesión (SBC) del cliente.
-   Mantener los medios locales dentro de los límites de las subredes de red corporativa.
-   Permitir transmisiones multimedia entre los clientes Teams y los SBC incluso si los SBC están detrás de firewalls corporativos con IP privadas y no visibles para Microsoft directamente.

Optimización de medios locales admite dos escenarios:

- Centralización de todos los troncos locales a través de un SBC centralizado conectado al tronco principal del Protocolo de inicio de sesión (SIP), proporcionando servicios de telefonía a todas las sucursales locales de la compañía.

-   Crear una topología de red virtual de SBC, donde los SBC de las sucursales locales están conectados a un SBC proxy centralizado que es visible para Teléfono Microsoft System a través de su dirección IP externa. En una topología de red virtual, los SBC descendentes se comunican a través de IP internas y no son directamente visibles para Sistema telefónico.

En este artículo se describen las funciones de características y los escenarios y soluciones de los clientes. Para obtener más información sobre la configuración, vea [Configurar la optimización de medios locales.](direct-routing-media-optimization-configure.md) 

  > [!NOTE]
  > Si desea mantener los medios locales dentro de los límites de la intranet, se recomienda optimizar los medios locales. Si ya tiene La omisión de medios y solo usa las direcciones IP públicas de los SBC, no es obligatorio desplazarse a Optimización de medios locales. Puede seguir usando La omisión de medios. Para obtener más información, vea [Planear la omisión de medios.](direct-routing-plan-media-bypass.md)


## <a name="supported-customer-scenarios"></a>Escenarios de cliente admitidos

Para esta discusión, suponga que Contoso ejecuta varias empresas en todo el mundo de la siguiente manera. (Tenga en cuenta que las regiones de Europa y APAC solo se usan como ejemplos. Una empresa puede tener varias regiones diferentes con requisitos similares).
 
- **En Europa,** Contoso tiene oficinas en aproximadamente 30 países. Cada oficina tiene su propia rama privada Exchange (PBX). 

  A Contoso se le ofreció una opción para centralizar los troncos en una ubicación (Ámsterdam) para las 30 oficinas europeas. Contoso implementó el SBC en Ámsterdam, proporcionó ancho de banda suficiente para ejecutar llamadas a través de la ubicación centralizada, conectó un tronco SIP central a la ubicación centralizada y comenzó a servir a todas las ubicaciones europeas desde Ámsterdam. 

- **En la región de APAC,** Contoso tiene varias oficinas en diferentes países. 

  En muchos países, la compañía todavía tiene troncos de multiplexación de divisiones de tiempo (TDM) en sucursales locales. La centralización de los troncos TDM no es una opción en la región APAC, por lo que no es posible cambiar a SIP. Suponga que hay más de cincuenta sucursales de Contoso en toda la región de APAC con cientos de puertas de enlace (SBC). En este escenario, no es posible emparejar todas las puertas de enlace a la interfaz de enrutamiento directo debido a la falta de direcciones IP públicas o saltos de Internet locales. Además, algunos países imponen requisitos normativos que no se pueden cumplir sin tener conectividad de red RTC local.

En función de sus requisitos empresariales, Contoso implementó dos soluciones con optimización de medios locales para enrutamiento directo:

- **En Europa,** todos los troncos están centralizados y los flujos multimedia entre el SBC central y los usuarios, en función de la ubicación del usuario. 

  - Si un usuario está conectado a la subred local de una red corporativa (es decir, el usuario es interno), los medios fluyen entre la IP interna del SBC central y el cliente de Teams usuario. 
  
  - Si un usuario está fuera de los límites de la red corporativa (por ejemplo, si el usuario usa una conexión a Internet inalámbrica pública), se considera que el usuario es externo. En este caso, los medios fluyen entre la DIRECCIÓN IP externa del SBC central y el Teams cliente.

- En la región **APAC,** un SBC de proxy centralizado se empareja con Microsoft Direct Routing, que dirige los medios entre la interfaz de enrutamiento directo y los SBC descendentes en las sucursales locales. 

  Los SBC descendentes de las sucursales locales no son directamente visibles para enrutamiento directo en APAC, pero se emparejan mediante el cmdlet Set-CSOnlinePSTNGateway para crear una topología de red virtual dentro de Teléfono Microsoft System. Los medios siempre permanecen locales cuando es posible. Los usuarios externos tienen medios que fluyen entre el Teams y la IP pública del SBC proxy.


## <a name="central-sbc-with-centralized-trunks"></a>SBC central con troncos centralizados

Para crear una solución en la que se proporcionan servicios RTC a todas las sucursales locales a través de un único SBC central con un tronco SIP centralizado conectado, el administrador de inquilinos de Contoso empareja un SBC (centralsbc.contoso.com) al servicio; el SBC tiene un tronco SIP centralizado conectado a él. 

- Cuando un usuario se encuentra en la red interna de la empresa, el SBC proporciona la IP interna del SBC para los medios. 

- Cuando un usuario está fuera de la red corporativa, el SBC proporciona la IP externa (pública) del SBC.

Nota: Todos los valores de ejemplos, tablas o diagramas se presentan solo con fines ilustrativos.

Tabla 1. Parámetros de red de ejemplo para SBC 

| Ubicación | SBC FQDN | Subred interna | NAT externa (IP de confianza) | Dirección IP externa de SBC | Dirección IP interna de SBC |
|:------------|:-------|:-------|:-------|:-------|:-------|
| Ámsterdam | centralsbc.contoso.com | 192.168.5.0/24 | 172.16.76.73 | 172.16.76.71 | 192.168.5.5 |
| Alemania | No implementado | 192.168.6.0/24 | 172.16.76.74 | No implementado |  No implementado |
| Francia | No implementado | 192.168.7.0/24 | 172.16.76.75 | No implementado |  No implementado ||||


### <a name="internal-user"></a>Usuario interno

En el siguiente diagrama se muestra el flujo de tráfico cuando un usuario está conectado a la red corporativa en la sucursal o el sitio del usuario. 

Mientras se encuentra en el entorno local, el usuario se asigna a la sucursal local en Alemania. El usuario realiza una llamada telefónica de enrutamiento directo a través Teams.

- El cliente de Teams usuario se comunica a Sistema telefónico directamente a través de la API de REST, pero los medios generados durante la llamada fluyen a la dirección IP interna del SBC central. 

- El SBC redirige el flujo a Sistema telefónico red RTC conectada. 

- El SBC central es visible para Sistema telefónico solo a través de la dirección IP externa. 

Diagrama 1. Flujo de tráfico cuando el usuario se encuentra en el sitio "hogar" con un SBC centralizado y con un tronco SIP centralizado conectado

![Diagrama que muestra la optimización de medios locales del flujo de tráfico](media/direct-routing-media-op-1.png "Flujo de tráfico cuando el usuario está en un sitio &quot;hogar&quot; con SBC centralizado con tronco SIP centralizado conectado")


### <a name="external-user"></a>Usuario externo

En el siguiente diagrama se muestra el flujo de tráfico cuando un usuario no está local y no está conectado a la red corporativa (es decir, el dispositivo del usuario está conectado a Internet a través de un dispositivo móvil o wi-Fi público). El usuario realiza una llamada telefónica de enrutamiento directo a través Teams:

- El cliente de Teams del usuario se comunica a Sistema telefónico directamente a través de la API de REST, pero, en este caso, los medios generados durante la llamada fluyen a la dirección IP externa del SBC central. 

- El SBC redirige el flujo a Sistema telefónico red RTC conectada. 

- El SBC central es visible para Sistema telefónico solo a través de la dirección IP externa. 

En este caso, el comportamiento es similar si el usuario es local en la sucursal en Alemania o en cualquier otra sucursal. El usuario se considera externo porque el usuario está fuera de los límites de la red corporativa.

Diagrama 2. Flujo de tráfico cuando el usuario es externo con un SBC centralizado y con un tronco SIP centralizado conectado

![Diagrama que muestra la optimización de medios locales del flujo de tráfico](media/direct-routing-media-op-2.png "Flujo de tráfico cuando el usuario es externo en caso de SBC centralizado con tronco SIP centralizado conectado")

## <a name="proxy-sbc-with-connected-downstream-sbcs"></a>SBC proxy con SBC descendente conectado

Para crear una solución en la que los servicios RTC se proporcionan en todas las sucursales locales de la región de APAC, donde la centralización de los troncos TDM no es una opción, el administrador de Contoso empareja un SBC (proxysbc.contoso.com), también denominado SBC proxy, al servicio de enrutamiento directo. 

Posteriormente, el administrador de Contoso agrega algunos SBC descendentes que indican que se puede llegar a ellos a través del SBC proxy proxysbc.contoso.com. Sin embargo, los SBC descendentes no tienen IP públicas, pero se pueden asignar a las rutas de voz. En la tabla siguiente se muestran parámetros de red y configuración de ejemplo.

Cuando un usuario se encuentra en la sucursal local donde se encuentra el SBC descendente, el tráfico multimedia fluye entre el usuario y el SBC local descendente directamente. Si un usuario está fuera de la oficina (en internet público), los medios fluyen del usuario a la IP pública del SBC proxy, que lo proxy a los SBC posteriores correspondientes.

Tabla 2. Información de red SBC de ejemplo

| Ubicación | SBC FQDN | Subred interna | NAT externa (IP de confianza) | Dirección IP externa de SBC  | Dirección IP interna de SBC |
|:------------|:-------|:-------|:-------|:-------|:-------|
| Vietnam | VNsbc.contoso.com | 192.168.1.0/24 | 172.16.240.110 | Ninguna |  192.168.1.5 |
| Indonesia  | IDsbc.contoso.com | 192.168.2.0/24 | 172.16.240.120 | Ninguna |  192.168.2.5 |
| Singapur | proxysbc.contoso.com |   192.168.3.0/24 | 172.16.240.130 | 172.16.240.133 | 192.168.3.5 |



### <a name="internal-user"></a>Usuario interno 

En el siguiente diagrama se muestra el flujo de tráfico de alto nivel para el escenario cuando un usuario está dentro de la oficina en la región APAC. El usuario, que está asignado a una sucursal local en Vietnam y está en las instalaciones, realiza una llamada telefónica de enrutamiento directo a través de Teams. 

- El cliente de Teams usuario se comunica con Sistema telefónico directamente a través de la API de REST, pero los medios generados durante la llamada fluyen a la dirección IP interna de SBC local.

- El SBC local redirige el flujo al SBC proxy en Singapur y a la red RTC local conectada.

-  El SBC proxy es visible para Sistema telefónico a través de la dirección IP externa y enruta el flujo desde el SBC descendente (en este caso, el SBC local en Vietnam) a Sistema telefónico. 

- El SBC descendente de la sucursal local no es visible para Sistema telefónico directamente, pero se asigna dentro de la topología de red virtual definida por el administrador de Contoso al configurar optimización de medios locales.

Nota: El comportamiento puede ser diferente para usuarios locales y usuarios no locales dependiendo del modo de optimización de medios locales configurado. 

Para obtener más información sobre los posibles modos y el comportamiento relevante, vea Configurar la optimización de medios locales.

Diagrama 3. Flujo de tráfico cuando el usuario está en la red "doméstica" con un SBC proxy y con SBC descendente conectado 

![Diagrama que muestra la optimización de medios locales del flujo de tráfico](media/direct-routing-media-op-3.png "Flujo de tráfico en caso de SBC proxy con SBC descendente conectado cuando el usuario está en la red &quot;doméstica&quot;.")

### <a name="external-user"></a>Usuario externo

En el siguiente diagrama se muestra el flujo de tráfico cuando un usuario está fuera de los límites de la red corporativa. El usuario no es local (no está dentro de los límites de la red corporativa). El usuario realiza una llamada de teléfono de enrutamiento directo Teams a un número de teléfono en Vietnam. 

- El cliente de Teams usuario se comunica con Sistema telefónico directamente a través de la API de REST, pero los medios generados durante la llamada fluyen primero a la dirección IP externa del SBC proxy en Singapur. 

- En función de las directivas de configuración y voz (consulte Configurar la optimización de medios [locales](direct-routing-media-optimization-configure.md) para obtener más información), el SBC proxy redirige el flujo al SBC descendente en Vietnam. 

- El SBC descendente en Vietnam redirige el flujo a la red RTC local conectada. 

- El SBC proxy es visible para Sistema telefónico solo a través de la dirección IP externa.

-  El SBC descendente de la sucursal local no es visible para Sistema telefónico directamente, pero se asigna dentro de la topología de red virtual que define el administrador de Contoso al configurar optimización de medios locales. En el ejemplo, el usuario se considera externo porque el usuario está fuera de los límites de la red corporativa. 

Diagrama 4. Flujo de tráfico cuando el usuario es externo con un SBC proxy y con SBC descendente conectado

![Diagrama que muestra la optimización de medios locales del flujo de tráfico](media/direct-routing-media-op-4.png "Flujo de tráfico en caso de SBC proxy con SBC descendente conectado cuando el usuario es externo")

## <a name="local-media-optimization-modes"></a>Modos de optimización de medios locales

Optimización de medios locales admite dos modos:

- **Modo 1: Omitir siempre**. En este caso, si el usuario es interno, el medio fluirá a través de la dirección IP interna del SBC local, independientemente de la ubicación real del usuario interno; por ejemplo, dentro de la misma sucursal en la que se encuentra el SBC descendente o en alguna otra sucursal.  

- **Modo 2: Solo para usuarios locales.** En este modo, los medios fluirán directamente a la dirección IP interna del SBC descendente local solo cuando lo genere el usuario interno ubicado en la misma sucursal que el SBC descendente. 

Para distinguir entre los modos de optimización de medios locales, el administrador de inquilinos debe establecer el parámetro -BypassMode en "Always" o "OnlyForLocalUsers" para cada SBC mediante el cmdlet Set-CSonlinePSTNGateway. Para obtener más información, vea [Configurar la optimización de medios locales.](direct-routing-media-optimization-configure.md)  

 > [!NOTE]
  > Cuando los usuarios son internos, se requiere conectividad multimedia entre el usuario y el SBC a través de la dirección IP **interna.** No hay ningún retroceso en los retransmisión de transporte público para medios en este caso, ya que el SBC estará proporcionando una IP interna para la conectividad de medios. 

### <a name="mode-1-always-bypass"></a>Modo 1: Omitir siempre

Si tiene una buena conexión entre sucursales, el modo recomendado es Omitir siempre.
 
Por ejemplo, supongamos que una empresa tiene un tronco SIP centralizado en Ámsterdam, que sirve a 30 países y tiene una buena conectividad entre los 30 sitios y los usuarios locales. También hay una sucursal en Alemania donde se implementa un SBC local.

El SBC en Alemania se puede configurar en el modo "Omitir siempre". Los usuarios, independientemente de su ubicación, se conectarán al SBC directamente a través de la dirección IP interna del SBC (por ejemplo, de Francia a Alemania; vea el diagrama siguiente para obtener referencia).

A continuación se describen dos escenarios:

- Escenario 1. El usuario se encuentra en la misma ubicación que el SBC definido en la directiva de enrutamiento de voz en línea.

- Escenario 2. El usuario y las puertas de enlace están en sitios diferentes.

#### <a name="scenario-1-the-user-is-in-the-same-location-as-the-sbc-defined-in-the-online-voice-routing-policy"></a>Escenario 1. El usuario se encuentra en la misma ubicación que el SBC definido en la directiva de enrutamiento de voz en línea

El SBC de Ámsterdam está configurado para ser un SBC proxy para un SBC local descendente en Alemania. El usuario se encuentra en Alemania dentro de la misma subred que la red corporativa del SBC local. Ambos SBC (proxy y downstream) están configurados para el modo Desuso siempre. Las directivas de enrutamiento de voz en línea especifican que, en caso de llamadas dentro de Alemania (con código de área +49), se deben enrutar al SBC local de Alemania. Todas las demás llamadas (y en caso de que el SBC en Alemania falle, las llamadas en Alemania) se deben enrutar al SBC proxy en Ámsterdam. En la tabla siguiente se resume la configuración de ejemplo. 

Tabla 3. Configuración de ejemplo para escenario 1

| Ubicación física del usuario | El usuario realiza una llamada a un número | Directiva de enrutamiento de voz en línea | Modo configurado para SBC | Media Flow | 
|:------------|:-------|:-------|:-------|:-------|
| Alemania | +49 1 437 2800 | Prioridad 1: ^ \+ 49(\d {8} )$ -DEsbc.contoso.com<br>Prioridad 2: .* - proxysbc.contoso.com| DEsbc.contoso.com: omitir siempre <br>proxysbc.contoso.com: omitir siempre | Teams Usuario <–> DEsbc.contoso.com |

En el siguiente diagrama se muestra el flujo de tráfico de alto nivel para el usuario interno de Alemania que realiza una llamada telefónica de enrutamiento directo a través de Teams al número en Alemania. 

- El cliente de Teams usuario se comunica con Sistema telefónico directamente a través de la API de REST. 

- Los medios generados durante la llamada fluyen a la dirección IP interna del SBC local. 

- El SBC local redirige el flujo al SBC proxy de Ámsterdam y a la red RTC local conectada. 

- El SBC proxy es visible para Sistema telefónico a través de la dirección IP externa y enruta el flujo desde el SBC descendente (en este caso, el SBC local en Alemania) a Sistema telefónico. 

- El SBC descendente de la sucursal local no es visible para Sistema telefónico directamente, pero se asigna dentro de la topología de red virtual definida por el administrador de Contoso al configurar optimización de medios locales.


Diagrama 5.  Flujo de tráfico con el modo "Omitir siempre" y el usuario se encuentra en el sitio "inicio"

![Diagrama que muestra la optimización de medios locales del flujo de tráfico](media/direct-routing-media-op-5.png "Flujo de tráfico con el modo &quot;Omitir siempre&quot; y el usuario se encuentra en el sitio &quot;inicio&quot;")


#### <a name="scenario-2-the-user-and-gateways-are-in-different-sites"></a>Escenario 2: El usuario y las puertas de enlace están en sitios diferentes

El SBC de Ámsterdam está configurado para ser un SBC proxy para un SBC local descendente en Alemania. Ambos SBC (proxy y downstream) están configurados para el modo Desuso siempre. El usuario interno de Francia, ubicado en la sucursal local, realiza una llamada de enrutamiento directo a Alemania. Las directivas de enrutamiento de voz en línea especifican que las llamadas a Alemania (con código de área +49) se deben enrutar al SBC local de Alemania. Todas las demás llamadas (y, en caso de que el SBC en Alemania no se pueda realizar, todas las llamadas en Alemania) se deben enrutar al SBC proxy de Ámsterdam. En la tabla siguiente se resume la configuración de ejemplo. 

Tabla 4. Configuración de ejemplo para el escenario 2

| Ubicación física del usuario | El usuario realiza una llamada a un número | Directiva de enrutamiento de voz en línea | Modo configurado para SBC | Media Flow | 
|:------------|:-------|:-------|:-------|:-------|
| Francia | +49 1 437 2800 | Prioridad 1: ^ \+ 49(\d {8} )$ -DEsbc.contoso.com <br>Prioridad 2: .* - proxysbc.contoso.com |  DEsbc.contoso.com: Omitir siempre proxysbc.contoso.com: omitir siempre | Teams Usuario <: > DEsbc.contoso.com  |

En el siguiente diagrama se muestra el flujo de tráfico de alto nivel cuando el usuario interno alemán ubicado en Francia realiza una llamada telefónica de enrutamiento directo Teams al número en Alemania. 

- El cliente de Teams usuario se comunica con Sistema telefónico directamente a través de la API de REST.

- Los medios generados durante la llamada fluyen directamente al SBC en la dirección IP interna de Alemania. 

- El SBC de Alemania redirige el flujo al SBC proxy de Ámsterdam y a la red RTC local conectada. 

Diagrama 6.  Flujo de tráfico con el modo "Omitir siempre" y el usuario no está en el sitio "inicio", sino en la red interna

![Diagrama que muestra la optimización de medios locales del flujo de tráfico](media/direct-routing-media-op-6.png "El flujo de tráfico con el modo &quot;Omitir siempre&quot; y el usuario no está en el sitio &quot;inicio&quot;, sino en la red interna")

### <a name="mode-2-only-for-local-users"></a>Modo 2: Solo para usuarios locales

Si hay conexiones malas entre sucursales locales pero buenas conexiones entre cada sucursal local y cada oficina regional, el modo recomendado es "Solo para usuarios locales".

Por ejemplo, en la región APAC, suponga que Contoso tiene varias oficinas en diferentes países. Para muchos países, cambiar a SIP no es posible porque la empresa todavía tiene troncos TDM en muchas sucursales locales. La centralización de los troncos TDM no es una opción en la región APAC. Además, hay más de cincuenta sucursales de Contoso en toda la región de APAC con cientos de puertas de enlace (SBC). 

Para crear una solución en la que los servicios RTC se proporcionan en todas las sucursales locales de la región de APAC, donde la centralización de los troncos TDM no es una opción, el administrador de Contoso empareja un SBC regional en Singapur como SBC proxy para el servicio de enrutamiento directo. La conexión directa entre las sucursales locales no es buena, pero hay una buena conexión entre cada sucursal local y el SBC regional en Singapur. Para el SBC regional, el administrador elige el modo "Omitir siempre" y, para los SBC descendentes locales, el administrador elige el modo "Solo para usuarios locales".

A continuación se describen dos escenarios:

- Escenario 1. El usuario se encuentra en la misma ubicación que el SBC definido en la directiva de enrutamiento de voz en línea

- Escenario 2. El usuario y las puertas de enlace están en sitios diferentes

#### <a name="scenario-1-the-user-is-in-the-same-location-as-the-sbc-defined-in-online-voice-routing-policy"></a>Escenario 1. El usuario se encuentra en la misma ubicación que el SBC definido en la directiva de enrutamiento de voz en línea

Suponga que el SBC de Singapur está configurado para ser un SBC proxy para los SBC locales de nivel inferior en Vietnam e Indonesia. El usuario se encuentra en Vietnam en la misma ubicación que el SBC local. Las directivas de enrutamiento de voz en línea especifican que las llamadas en Vietnam (con código de área +84) se deben enrutar al SBC local en Vietnam. Todas las demás llamadas (y, si el SBC en Vietnam falla, las llamadas en Vietnam) se deben enrutar al SBC proxy en Singapur. En la tabla siguiente se resume la configuración de ejemplo. 

Tabla 5. Configuración de ejemplo para el modo "Solo para usuarios locales" Escenario 1

| Ubicación física del usuario | El usuario realiza una llamada a un número | Directiva de enrutamiento de voz en línea | Modo configurado para SBC | Media Flow | 
|:------------|:-------|:-------|:-------|:-------|
| Vietnam | +84 4 3926 3000 | Prioridad 1: ^ \+ 84(\d {9} )$ -VNsbc.contoso.com <br>Prioridad 2: .* - proxysbc.contoso.com | VNsbc.contoso.com: solo para usuarios locales <br> proxysbc.contoso.com: omitir siempre | Teams Usuario <–> VNsbc.contoso.com |

En el siguiente diagrama, un usuario asignado a la sucursal local en Vietnam, mientras está en las instalaciones, realiza una llamada telefónica de enrutamiento directo a través de Teams. 

- El cliente de Teams usuario se comunica con Sistema telefónico directamente a través de la API de REST. 

- Los medios generados durante la llamada fluyen a la dirección IP interna del SBC local. 

- El SBC local redirige el flujo al SBC proxy en Singapur y a la red RTC local conectada. 

- El SBC proxy es visible para Sistema telefónico a través de la dirección IP externa y enruta el flujo desde el SBC descendente (en este caso, el SBC local en Vietnam) a Sistema telefónico. 

- El SBC descendente de la sucursal local no es visible Sistema telefónico directamente, pero se asigna dentro de la topología de red virtual.

Diagrama 7. Flujo de tráfico con el modo "Solo para usuarios locales" y el usuario se encuentra en el sitio "inicio".

![Diagrama que muestra la optimización de medios locales del flujo de tráfico](media/direct-routing-media-op-7.png "Flujo de tráfico con el modo &quot;Solo para usuarios locales&quot; y el usuario está en el sitio &quot;inicio&quot;")


#### <a name="scenario-2-the-user-and-gateways-are-in-different-sites"></a>Escenario 2. El usuario y las puertas de enlace están en sitios diferentes

Suponga que el SBC de Singapur está configurado para ser un SBC proxy para los SBC locales de nivel inferior en Vietnam e Indonesia. El usuario interno de Indonesia, ubicado en la sucursal local, realiza una llamada de enrutamiento directo a Vietnam. Las directivas de enrutamiento de voz en línea especifican que las llamadas a Vietnam (con código de área +84) se deben enrutar al SBC local en Vietnam. Todas las demás llamadas (y, en caso de que el SBC de Vietnam falle, las llamadas a Vietnam) se deben enrutar al SBC proxy en Singapur. El SBC proxy en Singapur se establece en el modo "Omitir siempre" y el SBC local en Vietnam se establece en el modo "Solo para usuarios locales". En la tabla siguiente se resume la configuración de ejemplo. 

Tabla 6. Configuración de usuario

| Ubicación física del usuario | El usuario realiza una llamada a un número | Directiva de enrutamiento de voz en línea | Modo configurado para SBC | Media Flow | 
|:------------|:-------|:-------|:-------|:-------|
| Indonesia | +84 4 3926 3000 | Prioridad 1: ^ \+ 84(\d {9} )$ -VNsbc.contoso.com <br> Prioridad 2: .* - proxysbc.contoso.com |VNsbc.contoso.com: solo para usuarios locales <br> proxysbc.contoso.com: omitir siempre | Teams Usuario <–> proxysbc.contoso.com <–> VNsbc.contoso.com |


En el siguiente diagrama, el usuario interno, mientras se encuentra en las instalaciones de la sucursal indonesia, realiza una llamada telefónica de enrutamiento directo a través de Teams a un número en Vietnam. 

- El cliente de Teams usuario se comunica con Sistema telefónico directamente a través de la API de REST.

- Los medios generados durante la llamada fluyen primero a la dirección IP interna del SBC del proxy. 

- El SBC proxy en Singapur redirige el flujo a la dirección IP interna del SBC descendente en Vietnam y a Sistema telefónico. 

- El SBC descendente en Vietnam enruta el flujo a la red RTC local conectada. 

- El SBC proxy es visible para Sistema telefónico solo a través de la dirección IP externa.

- Los SBC descendentes de las sucursales locales no son visibles para Sistema telefónico directamente, pero se asignan dentro de la topología de red virtual.

Diagrama 8.  Flujo de tráfico con el modo "Solo para usuarios locales" y el usuario no se encuentra en el sitio "inicio", sino en la red interna

![Diagrama que muestra la optimización de medios locales del flujo de tráfico](media/direct-routing-media-op-8.png "Flujo de tráfico con el modo &quot;Solo para usuarios locales&quot;, el usuario no está en el sitio &quot;inicio&quot;, sino en la red interna")

## <a name="known-issues"></a>Problemas conocidos

A continuación se muestra una lista de los problemas conocidos que están presentes actualmente en optimización de medios locales. Microsoft está trabajando para solucionar estos problemas.

| Problema | Solución alternativa |
| :--- | :--- |
| Teams cliente no se identifica **como** interno cuando Teams cliente IP pública coincide con la lista IP de confianza del cliente. | Optimización de medios locales requiere que la subred Teams cliente coincida con una subred de red [configurada por el inquilino](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps)|
| Las escalaciones de llamadas resultan en llamadas descartadas cuando el Teams se identifica como interno.| Deshabilite la optimización de medios locales en el SBC de enrutamiento directo.|
| Escalaciones de llamadas de 1 a 1 llamada entre clientes internos a llamadas multipartes con el resultado de cliente o recurso externo en llamadas descartadas | Trabajar en curso en una corrección. Como alternativa, deshabilite la optimización de medios locales en el SBC de enrutamiento directo.|
| Teams usuario pone la llamada en espera. Música se reproduce en el extremo RTC y la optimización de medios locales funciona. El Teams reanudará la llamada. La llamada a RTC se reanuda, pero la optimización de medios locales no funciona y la llamada continúa a través de SBC central (proxy) | Cuando un usuario aparca una llamada para iniciar la música en espera (MoH), el controlador de llamadas está escalando de 1:1 a una llamada multiparte para invocar el controlador multimedia y el procesador multimedia (que sirve como mezclador AVMCU) a través del cual el MoH llega a un usuario que se ha puesto en espera. La desescalación a una llamada de 1:1 después de reanudar la llamada nunca se produce según el diseño. Deshabilite la optimización de medios locales en el SBC de enrutamiento directo.|
