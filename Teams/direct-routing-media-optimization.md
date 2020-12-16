---
title: Enrutamiento directo de multimedia local de enrutamiento
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

La voz de la red telefónica conmutada pública (RTC) se considera una aplicación crítica para la empresa con altas expectativas de calidad de voz. El enrutamiento directo le permite controlar los flujos de tráfico de los medios para dar cabida a multitud de topologías de red y a las configuraciones de telefonía local para diversas empresas de todo el mundo. 

La optimización local de medios para el enrutamiento directo permite administrar la calidad de voz de la siguiente manera:

-   Controlar cómo fluye el tráfico de medios entre los clientes de los equipos y los controladores de borde de la sesión del cliente (SBCs).
-   Mantener los medios locales dentro de los límites de las subredes de la red corporativa.
-   Permitir transmisiones de medios entre los clientes de los equipos y SBCs incluso si el SBCs está detrás de firewalls corporativos con IP privadas y no visible para Microsoft directamente.

La optimización local de medios admite dos escenarios:

- Centralización de todos los troncos locales a través de un SBC centralizado conectado al tronco principal del Protocolo de inicio de sesión (SIP), que proporciona servicios de telefonía a todas las sucursales locales de la empresa.

-   Creación de una topología de red virtual de SBCs: donde la SBCs de las sucursales locales está conectada a un SBC de proxy centralizado que está visible y se comunica con el sistema telefónico de Microsoft a través de su dirección IP externa. En una topología de red virtual, SBCs inferior se está comunicando a través de direcciones IP internas y no es directamente visible para el sistema telefónico.

Este artículo describe la funcionalidad de características y las soluciones y los escenarios de clientes. Para obtener más información sobre la configuración, vea [configurar la optimización local de medios](direct-routing-media-optimization-configure.md). 

  > [!NOTE]
  > Si desea mantener los medios locales dentro de los límites de la intranet, se recomienda la optimización local de medios. Si ya tiene un bypass de elementos multimedia y solo usa las direcciones IP públicas de su SBCs, no es obligatorio cambiar a la optimización local de medios. Puede continuar usando la omisión de medios. Para obtener más información, consulte [planear la omisión de medios](direct-routing-plan-media-bypass.md).


## <a name="supported-customer-scenarios"></a>Escenarios de clientes admitidos

Para esta discusión, supongamos que contoso ejecuta varias empresas en todo el mundo de la siguiente manera. (Ten en cuenta que las regiones de Europa y APAC se usan solo como ejemplos. Una empresa puede tener varias regiones diferentes con requisitos similares.)
 
- **En Europa**, Contoso tiene oficinas en aproximadamente 30 países. Cada oficina tiene su propia central de conmutación (PBX). 

  A contoso se le ofreció una opción para centralizar los troncos en un lugar, Ámsterdam, para las 30 oficinas europeas. Contoso implementó el SBC en Amsterdam, proporcionó suficiente ancho de banda para ejecutar llamadas a través de la ubicación centralizada, conectó un tronco SIP central a la ubicación centralizada y comenzó a servir a todas las ubicaciones europeas de Amsterdam. 

- **En la región de APAC**, Contoso tiene varias oficinas en diferentes países. 

  En muchos países, la compañía sigue teniendo troncos de multiplexación de división de tiempo (TDM) en sucursales locales. La centralización de los troncos de TDM no es una opción en la región de APAC, por lo que no es posible cambiar a SIP. Supongamos que hay más de 50 de sucursales de Contoso en toda la región de APAC con centenares de puertas de enlace (SBCs). En este escenario, no es posible emparejar todas las puertas de enlace a la interfaz de enrutamiento directo debido a la falta de direcciones IP públicas o a las sesiones individuales de Internet. Además, algunos países imponen requisitos normativos que no se pueden cumplir sin tener conectividad de red RTC local.

En función de sus necesidades empresariales, contoso implementó dos soluciones con la optimización de medios locales para el enrutamiento directo:

- **En Europa**, todos los troncos son centralizados y los flujos de medios entre el SBC central y los usuarios, en función de la ubicación del usuario. 

  - Si un usuario se conecta a la subred local de una red corporativa (es decir, el usuario es interno), los medios se transmiten entre la IP interna de la SBC central y el cliente de equipos del usuario. 
  
  - Si un usuario está fuera de los límites de la red corporativa, por ejemplo, si el usuario usa una conexión a Internet inalámbrica pública, se considera que el usuario es externo. En este caso, los medios fluyen entre la IP externa de la SBC central y el cliente de Teams.

- **En la región de APAC**, un SBC de proxy centralizado se empareja al enrutamiento directo de Microsoft, que dirige los medios entre la interfaz de enrutamiento directa y el SBCS indirecto en las sucursales locales. 

  El SBCs indirecto de las sucursales locales no es visible directamente para el enrutamiento directo en APAC, pero se emparejan usando el cmdlet Set-CSOnlinePSTNGateway para crear una topología de red virtual en Microsoft Phone System. Los medios siempre permanecen locales cuando es posible. Los usuarios externos tienen medios que fluyen entre el cliente de Teams y la IP pública del SBC de proxy.


## <a name="central-sbc-with-centralized-trunks"></a>SBC central con troncos centralizados

Para crear una solución en la que los servicios RTC se proporcionan a todas las sucursales locales a través de un solo SBC central con un tronco SIP centralizado conectado, el administrador de inquilinos de Contoso empareja un SBC (centralsbc.contoso.com) al servicio; la SBC tiene un tronco de SIP centralizado conectado a él. 

- Cuando un usuario se encuentra en la red interna de la empresa, el SBC proporciona la IP interna de SBC para los medios. 

- Cuando un usuario está fuera de la red corporativa, el SBC proporciona la IP externa (pública) de la SBC.

Nota: todos los valores de ejemplos, tablas o diagramas se presentan solo a modo ilustrativo.

Tabla 1. Parámetros de red de ejemplo para SBCs 

| Ubicación | FQDN DE SBC | Subred interna | NAT externa (IP de confianza) | Dirección IP externa de SBC | Dirección IP interna de SBC |
|:------------|:-------|:-------|:-------|:-------|:-------|
| Ámsterdam | centralsbc.contoso.com | 192.168.5.0/24 | 172.16.76.73 | 172.16.76.71 | 192.168.5.5 |
| Alemania | No implementado | 192.168.6.0/24 | 172.16.76.74 | No implementado |  No implementado |
| Francia | No implementado | 192.168.7.0/24 | 172.16.76.75 | No implementado |  No implementado ||||


### <a name="internal-user"></a>Usuario interno

En el siguiente diagrama se muestra el flujo de tráfico cuando un usuario se conecta a la red corporativa en la sucursal o sitio principal del usuario. 

En local, el usuario se asigna a la sucursal local de Alemania. El usuario realiza una llamada de teléfono de enrutamiento directo a través de Teams.

- El cliente de Teams del usuario se comunica con el sistema telefónico directamente a través de la API de REST, pero los elementos multimedia generados durante la llamada fluyen a la dirección IP interna de SBC central. 

- El SBC redirige el flujo a un sistema telefónico y a la red RTC conectada. 

- La SBC central está visible para el sistema telefónico solo a través de la dirección IP externa. 

Diagrama 1. El tráfico fluye cuando el usuario se encuentra en el sitio de la casa con un SBC centralizado y con un tronco de SIP centralizado conectado

![Diagrama que muestra el tráfico de la optimización multimedia local](media/direct-routing-media-op-1.png "Flujo de tráfico cuando el usuario está en el sitio de la casa con SBC centralizado con tronco SIP centralizado conectado")


### <a name="external-user"></a>Usuario externo

En el siguiente diagrama se muestra el flujo de tráfico cuando un usuario no es local y no está conectado a la red corporativa (es decir, el dispositivo del usuario está conectado a Internet a través de un dispositivo móvil o de una red Wi-Fi pública). El usuario realiza una llamada de teléfono de enrutamiento directo a través de Teams:

- El cliente de Teams del usuario se comunica con el sistema telefónico directamente a través de la API de REST, pero, en este caso, los elementos multimedia generados durante la llamada fluyen a la dirección IP externa de SBC central. 

- El SBC redirige el flujo a un sistema telefónico y a la red RTC conectada. 

- La SBC central está visible para el sistema telefónico solo a través de la dirección IP externa. 

En este caso, el comportamiento es similar si el usuario es local en la sucursal de Alemania o en cualquier otra sucursal. El usuario se considera externo porque el usuario está fuera de los límites de la red corporativa.

Diagrama 2. Flujo de tráfico cuando el usuario es externo con un SBC centralizado y con un tronco de SIP centralizado conectado

![Diagrama que muestra el tráfico de la optimización multimedia local](media/direct-routing-media-op-2.png "Flujo de tráfico cuando el usuario es externo en caso de SBC centralizado con tronco SIP centralizado conectado")

## <a name="proxy-sbc-with-connected-downstream-sbcs"></a>SBC de proxy con SBCs indirecto conectado

Para crear una solución en la que los servicios RTC se proporcionan en todas las sucursales locales de la región de APAC donde la centralización de los troncos TDM no es una opción, el administrador de Contoso empareja un SBC (proxysbc.contoso.com), también denominado SBC proxy, al servicio de enrutamiento directo. 

Después, el administrador de Contoso agrega un poco de SBCs indirecto que indica que se puede acceder a ellos a través del servidor de SBC proxysbc.contoso.com. Los SBCs indirectos no tienen IPs público, sin embargo, se pueden asignar a las rutas de voz. En la siguiente tabla se muestran los parámetros de red y la configuración de ejemplo.

Cuando un usuario está en la sucursal local donde se encuentra el SBC descendente, el tráfico multimedia fluye directamente entre el usuario y el SBC descendente local. Si un usuario está fuera de la oficina (en una Internet pública), los medios fluyen del usuario a la dirección IP pública del SBC de proxy, que se envía a través de un servidor proxy de SBC (s) de referencia.

Tabla 2. Ejemplo de información de red de SBC

| Ubicación | FQDN DE SBC | Subred interna | NAT externa (IP de confianza) | Dirección IP externa de SBC  | Dirección IP interna de SBC |
|:------------|:-------|:-------|:-------|:-------|:-------|
| Vietnam | VNsbc.contoso.com | 192.168.1.0/24 | 172.16.240.110 | Ninguna |  192.168.1.5 |
| Indonesia  | IDsbc.contoso.com | 192.168.2.0/24 | 172.16.240.120 | Ninguna |  192.168.2.5 |
| Singapur | proxysbc.contoso.com |   192.168.3.0/24 | 172.16.240.130 | 172.16.240.133 | 192.168.3.5 |



### <a name="internal-user"></a>Usuario interno 

En el siguiente diagrama se muestra el flujo de tráfico de alto nivel para el escenario en el que un usuario está dentro de la oficina en la región de APAC. El usuario, que se asigna a una sucursal local en Vietnam y se encuentra en el entorno local, realiza una llamada telefónica directa a través de Teams. 

- El cliente de Teams del usuario se comunica con el sistema telefónico directamente a través de la API de REST, pero los elementos multimedia generados durante la llamada fluyen a la dirección IP interna de SBC local.

- El SBC local redirige el flujo al SBC proxy en Singapur y a la red RTC local conectada.

-  El SBC de proxy está visible para el sistema telefónico a través de la dirección IP externa y enruta el flujo desde el SBC indirecto (en este caso, el SBC local en Vietnam) hasta el sistema telefónico. 

- El servicio de SBC en la sucursal local no es visible para el sistema telefónico directamente, sino que está asignado dentro de la topología de red virtual que está definida por el administrador de Contoso al mismo tiempo que se configura la optimización multimedia local.

Nota: el comportamiento puede ser diferente para los usuarios locales y no locales, según el modo de optimización local de medios configurado. 

Para obtener más información sobre los posibles modos y el comportamiento pertinente, vea Configurar la optimización de medios locales.

Diagrama 3. Flujo de tráfico cuando el usuario está en la red "casa" con un SBC proxy y con un nivel de SBCs conectado 

![Diagrama que muestra el tráfico de la optimización multimedia local](media/direct-routing-media-op-3.png "Flujo de tráfico en caso de SBC proxy con el nivel inferior conectado SBCs cuando el usuario está en la red "doméstica"")

### <a name="external-user"></a>Usuario externo

En el diagrama siguiente se muestra el flujo de tráfico cuando un usuario está fuera de los límites de la red corporativa. El usuario no es local (no está dentro de los límites de la red corporativa). El usuario realiza una llamada telefónica directa a través de Teams a un número de teléfono en Vietnam. 

- El cliente de Teams del usuario se comunica con el sistema telefónico directamente a través de la API de REST, pero los medios generados durante la llamada fluyen primero a la dirección IP externa del SBC proxy en Singapur. 

- Según las directivas de configuración y voz (consulte [configurar la optimización de medios locales](direct-routing-media-optimization-configure.md) para obtener más información), el SBC de proxy redirige el flujo al SBC downstream en Vietnam. 

- El SBC indirecto de Vietnam redirige el flujo a la red RTC local conectada. 

- El SBC de proxy está visible para el sistema telefónico solo a través de la dirección IP externa.

-  El sistema telefónico no puede ver directamente el SBC indirecto en la sucursal local, pero está asignado dentro de la topología de red virtual que está definida por el administrador de Contoso al mismo tiempo que se configura la optimización multimedia local. En el ejemplo, el usuario se considera externo porque el usuario está fuera de los límites de la red corporativa. 

Diagrama 4. Flujo de tráfico cuando el usuario es externo con un SBC proxy y con un nivel de SBCs conectado

![Diagrama que muestra el tráfico de la optimización multimedia local](media/direct-routing-media-op-4.png "Flujo de tráfico en caso de SBC proxy con el nivel inferior conectado SBCs cuando el usuario es externo")

## <a name="local-media-optimization-modes"></a>Modos de optimización de medios locales

La optimización local de medios admite dos modos:

- **Modo 1: omitir siempre**. En este caso, si el usuario es interno, el elemento multimedia fluirá por la dirección IP interna de SBC downstream local, independientemente de la ubicación real del usuario interno. por ejemplo, dentro de la misma sucursal donde se encuentra el SBC descendente o en otra sucursal.  

- **Modo 2: solo para usuarios locales**. En este modo, los medios fluyen directamente a la dirección IP interna de SBC de downstream local solo cuando la genera el usuario interno ubicado en la misma sucursal que el SBC inferior. 

Para distinguir entre los modos de optimización local multimedia, el administrador de inquilinos debe establecer el parámetro-BypassMode en ' Always ' o ' OnlyForLocalUsers ' para cada SBC mediante el cmdlet Set-CSonlinePSTNGateway. Para obtener más información, vea [configurar la optimización local de medios](direct-routing-media-optimization-configure.md).  

 > [!NOTE]
  > Cuando los usuarios son internos, se **requiere** conectividad multimedia entre el usuario y la SBC sobre la dirección IP interna. En este caso, no hay ninguna reserva a los transmisores de transporte público para archivos multimedia porque el SBC proporcionará una IP interna para la conectividad de medios. 

### <a name="mode-1-always-bypass"></a>Modo 1: omitir siempre

Si tiene una buena conexión entre sucursales, el modo recomendado siempre es omitir.
 
Por ejemplo, imaginemos que una empresa tiene un tronco de SIP centralizado en Amsterdam, que sirve a 30 países y que tiene una buena conectividad entre los 30 sitios y los usuarios locales. También hay una rama en Alemania en la que se implementa un SBC local.

El SBC en Alemania se puede configurar en el modo "omitir siempre". Los usuarios, independientemente de su ubicación, se conectarán al SBC directamente a través de la dirección IP interna de SBC (por ejemplo, de Francia a Alemania; vea el siguiente diagrama para consulta).

A continuación se describen dos escenarios:

- Escenario 1. El usuario se encuentra en la misma ubicación que la SBC definida en la Directiva de enrutamiento de voz en línea.

- Escenario 2. El usuario y las puertas de enlace están en distintos sitios.

#### <a name="scenario-1-the-user-is-in-the-same-location-as-the-sbc-defined-in-the-online-voice-routing-policy"></a>Escenario 1. El usuario se encuentra en la misma ubicación que la SBC definida en la Directiva de enrutamiento de voz en línea.

El SBC en Amsterdam está configurado para ser un SBC proxy para un SBC de downstream local en Alemania. El usuario se encuentra en Alemania dentro de la misma subred que la red corporativa del SBC local. Tanto SBCs (proxy como posterior) están configurados para el modo de omisión. Las directivas de enrutamiento de voz en línea especifican que, en caso de llamadas en Alemania (con código de área + 49), se deben enrutar al SBC local de Alemania. Todas las demás llamadas, y en caso de que se produzcan errores en la SBC en Alemania, las llamadas en Alemania deben dirigirse al SBC proxy de Amsterdam. En la tabla siguiente se resume la configuración de ejemplo. 

Tabla 3. Configuración de ejemplo para el escenario 1

| Ubicación física de usuario | El usuario realiza una llamada a un número | Directiva de enrutamiento de voz en línea | Modo configurado para SBC | Flujo de medios | 
|:------------|:-------|:-------|:-------|:-------|
| Alemania | + 49 1 437 2800 | Prioridad 1: ^ \+ 49 (\d {8} ) $-DEsbc.contoso.com<br>Prioridad 2:. *-proxysbc.contoso.com| DEsbc.contoso.com: omite siempre <br>proxysbc.contoso.com: omite siempre | < de usuario de Teams: > DEsbc.contoso.com |

El diagrama siguiente muestra el flujo de tráfico de alto nivel para que el usuario interno de Alemania realice una llamada de teléfono de enrutamiento directo a través de Teams al número de Alemania. 

- El cliente de Teams del usuario se comunica con el sistema telefónico directamente a través de la API de REST. 

- Los elementos multimedia generados durante la llamada fluyen a la dirección IP interna de SBC local. 

- El SBC local redirige el flujo al SBC proxy en Ámsterdam y a la red RTC local conectada. 

- El SBC de proxy está visible para el sistema telefónico a través de la dirección IP externa y enruta el flujo desde el SBC indirecto (en este caso, el SBC local de Alemania) a sistema telefónico. 

- El servicio de SBC en la sucursal local no es visible para el sistema telefónico directamente, sino que está asignado dentro de la topología de red virtual que está definida por el administrador de Contoso al mismo tiempo que se configura la optimización multimedia local.


Diagrama 5.  Flujo de tráfico con el modo "omitir siempre" y el usuario está en el sitio "hogar"

![Diagrama que muestra el tráfico de la optimización multimedia local](media/direct-routing-media-op-5.png "El flujo de tráfico con el modo "omitir siempre" y el usuario se encuentra en el sitio "doméstico"")


#### <a name="scenario-2-the-user-and-gateways-are-in-different-sites"></a>Escenario 2: el usuario y las puertas de enlace están en distintos sitios

El SBC en Amsterdam está configurado para ser un SBC proxy para un SBC de downstream local en Alemania. Tanto SBCs (proxy como posterior) están configurados para el modo de omisión. El usuario interno de Francia, que se encuentra en la sucursal local, está realizando una llamada de enrutamiento directo a Alemania. Las directivas de enrutamiento de voz en línea especifican que las llamadas a Alemania (con código de área + 49) se deben dirigir al SBC local de Alemania. Todas las demás llamadas, y en caso de que se produzcan errores en el SBC de Alemania, todas las llamadas de Alemania se enruten al SBC proxy de Amsterdam. En la tabla siguiente se resume la configuración de ejemplo. 

Tabla 4. Configuración de ejemplo para el escenario 2

| Ubicación física de usuario | El usuario realiza una llamada a un número | Directiva de enrutamiento de voz en línea | Modo configurado para SBC | Flujo de medios | 
|:------------|:-------|:-------|:-------|:-------|
| Francia | + 49 1 437 2800 | Prioridad 1: ^ \+ 49 (\d {8} ) $-DEsbc.contoso.com <br>Prioridad 2:. *-proxysbc.contoso.com |  DEsbc.contoso.com: omite siempre proxysbc.contoso.com: siempre omite | < de usuario de Teams: > DEsbc.contoso.com  |

En el siguiente diagrama se muestra el flujo de tráfico de alto nivel cuando el usuario alemán interno ubicado en Francia realiza una llamada de teléfono de enrutamiento directo a través de Teams al número de Alemania. 

- El cliente de Teams del usuario se comunica con el sistema telefónico directamente a través de la API de REST.

- Los medios generados durante la llamada fluyen directamente al SBC en la dirección IP interna de Alemania. 

- El SBC de Alemania redirige el flujo al SBC proxy de Amsterdam y a la red RTC local conectada. 

Diagrama 6.  El flujo de tráfico con el modo "omitir siempre" y el usuario no está en el sitio "doméstico", sino en la red interna.

![Diagrama que muestra el tráfico de la optimización multimedia local](media/direct-routing-media-op-6.png "El flujo de tráfico con el modo "omitir siempre" y el usuario no está en el sitio "doméstico", sino en la red interna")

### <a name="mode-2-only-for-local-users"></a>Modo 2: solo para usuarios locales

Si hay conexiones incorrectas entre las sucursales locales pero las conexiones correctas entre cada sucursal local y la oficina regional, el modo recomendado es "solo para usuarios locales".

Por ejemplo, en la región de APAC, se supone que Contoso tiene varias oficinas en diferentes países. En muchos países, no es posible cambiar a SIP porque la compañía aún tiene troncos de TDM en muchas sucursales locales. La centralización de los troncos TDM no es una opción en la región APAC. Además, hay más de 50 de sucursales de Contoso en toda la región de APAC con cientos de puertas de enlace (SBCs). 

Para crear una solución en la que los servicios RTC se proporcionan en todas las sucursales locales de la región de APAC donde la centralización de los troncos TDM no es una opción, el administrador de Contoso empareja un SBC regional en Singapur como SBC proxy al servicio de enrutamiento directo. La conexión directa entre las sucursales locales no es buena, pero hay una buena conexión entre cada sucursal local y el SBC regional en Singapur. Para el SBC regional, el administrador elige el modo "omitir siempre" y, para la SBCs de downstream local, el administrador elige "solo para el modo de usuarios locales.

A continuación se describen dos escenarios:

- Escenario 1. El usuario se encuentra en la misma ubicación que la SBC definida en la Directiva de enrutamiento de voz en línea.

- Escenario 2. El usuario y las puertas de enlace están en distintos sitios

#### <a name="scenario-1-the-user-is-in-the-same-location-as-the-sbc-defined-in-online-voice-routing-policy"></a>Escenario 1. El usuario se encuentra en la misma ubicación que la SBC definida en la Directiva de enrutamiento de voz en línea.

Supongamos que la SBC en Singapur está configurada como un SBC de proxy para el nivel de SBCs local de SBCs en Vietnam y Indonesia. El usuario pertenece a Vietnam dentro de la misma ubicación que el SBC local. Las directivas de enrutamiento de voz en línea especifican que las llamadas en Vietnam (con código de área + 84) se deben dirigir al SBC local de Vietnam. Todas las demás llamadas, y si se produce un error en la SBC en Vietnam, las llamadas en Vietnam deben enrutarse al SBC proxy en Singapur. En la tabla siguiente se resume la configuración de ejemplo. 

Tabla 5. Configuración de ejemplo para el escenario 1 solo para usuarios locales

| Ubicación física de usuario | El usuario realiza una llamada a un número | Directiva de enrutamiento de voz en línea | Modo configurado para SBC | Flujo de medios | 
|:------------|:-------|:-------|:-------|:-------|
| Vietnam | + 84 4 3926 3000 | Prioridad 1: ^ \+ 84 (\d {9} ) $-VNsbc.contoso.com <br>Prioridad 2:. *-proxysbc.contoso.com | VNsbc.contoso.com: solo para usuarios locales <br> proxysbc.contoso.com: omite siempre | < de usuario de Teams: > VNsbc.contoso.com |

En el siguiente diagrama, un usuario asignado a la sucursal local de Vietnam, aunque local, realiza una llamada de teléfono de enrutamiento directo a través de Teams. 

- El cliente de Teams del usuario se comunica con el sistema telefónico directamente a través de la API de REST. 

- Los elementos multimedia generados durante la llamada fluyen a la dirección IP interna de SBC local. 

- El SBC local redirige el flujo al SBC proxy en Singapur y a la red RTC local conectada. 

- El SBC de proxy está visible para el sistema telefónico a través de la dirección IP externa y enruta el flujo desde el SBC indirecto (en este caso, el SBC local en Vietnam) a sistema telefónico. 

- El sistema telefónico no puede ver el SBC indirecto en la sucursal local, sino que está asignado dentro de la topología de la red virtual.

Diagrama 7. El tráfico fluye con el modo "solo para usuarios locales" y el usuario está en el sitio "doméstico"

![Diagrama que muestra el tráfico de la optimización multimedia local](media/direct-routing-media-op-7.png "El flujo de tráfico con el modo "solo para usuarios locales" y el usuario está en el sitio "doméstico"")


#### <a name="scenario-2-the-user-and-gateways-are-in-different-sites"></a>Escenario 2. El usuario y las puertas de enlace están en distintos sitios

Supongamos que la SBC en Singapur está configurada como un SBC de proxy para el nivel de SBCs local de SBCs en Vietnam y Indonesia. El usuario interno de Indonesia, que se encuentra en la sucursal local, está realizando una llamada de enrutamiento directo a Vietnam. Las directivas de enrutamiento de voz en línea especifican que las llamadas a Vietnam (con código de área + 84) se deben enrutar al SBC local de Vietnam. Todas las demás llamadas, y en caso de que se produzcan errores en el SBC de Vietnam, las llamadas a Vietnam deben enrutarse al SBC proxy en Singapur. El SBC de proxy de Singapur se establece en el modo "omitir siempre", y el SBC local en Vietnam se establece en "solo para el modo de los usuarios locales". En la tabla siguiente se resume la configuración de ejemplo. 

Tabla 6. Configuración de usuario

| Ubicación física de usuario | El usuario realiza una llamada a un número | Directiva de enrutamiento de voz en línea | Modo configurado para SBC | Flujo de medios | 
|:------------|:-------|:-------|:-------|:-------|
| Indonesia | + 84 4 3926 3000 | Prioridad 1: ^ \+ 84 (\d {9} ) $-VNsbc.contoso.com <br> Prioridad 2:. *-proxysbc.contoso.com |VNsbc.contoso.com: solo para usuarios locales <br> proxysbc.contoso.com: omite siempre | < de usuario de Teams: > proxysbc.contoso.com <: > VNsbc.contoso.com |


En el siguiente diagrama, el usuario interno, aunque local en la sucursal de indonesio, realiza una llamada telefónica directa a través de Teams a un número en Vietnam. 

- El cliente de Teams del usuario se comunica con el sistema telefónico directamente a través de la API de REST.

- Los elementos multimedia generados durante la llamada fluyen primero a la dirección IP interna del SBC. 

- El SBC de proxy en Singapur redirige el flujo a la dirección IP interna del SBC indirecto en Vietnam y al sistema telefónico. 

- El SBC indirecto de Vietnam enruta el flujo a la red RTC local conectada. 

- El SBC de proxy está visible para el sistema telefónico solo a través de la dirección IP externa.

- El sistema telefónico no es visible para el sistema telefónico de las sucursales de nivel inferior en las sucursales locales, pero está asignado dentro de la topología de la red virtual.

Diagrama 8.  El tráfico fluye con el modo "solo para usuarios locales" y el usuario no está en el sitio "doméstico", sino en la red interna.

![Diagrama que muestra el tráfico de la optimización multimedia local](media/direct-routing-media-op-8.png "Flujo de tráfico con el modo "solo para usuarios locales", el usuario no está en el sitio "doméstico", sino en la red interna")

## <a name="known-issues"></a>Problemas conocidos

A continuación se muestra una lista de problemas conocidos que se encuentran actualmente en la optimización local de medios. Microsoft está trabajando en resolver estos problemas.

| Problema | Solución alternativa |
| :--- | :--- |
| El cliente de equipos no está identificado como **interno** cuando la IP pública del cliente de Teams coincide con la lista de IP de confianza del cliente. | La optimización local de medios requiere que la subred del cliente de Teams coincida con un inquilino de subred configurado de la [red](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps)|
| Las escalaciones de llamadas provocan que se rechacen las llamadas cuando el cliente de Teams se identifica como Internal.| Deshabilite la optimización de multimedia local en el SBC de enrutamiento directo.|


