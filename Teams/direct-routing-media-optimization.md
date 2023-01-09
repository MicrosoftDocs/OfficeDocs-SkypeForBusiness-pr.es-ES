---
title: Optimización de medios locales para enrutamiento directo
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
ms.openlocfilehash: ce9d25e84c67f5ae8b3b4fec51535d53f7b0044f
ms.sourcegitcommit: 8f26bf0ff88f1f6881de32914be00d5f0cc7396a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2023
ms.locfileid: "69740815"
---
# <a name="plan-for-local-media-optimization-for-direct-routing"></a>Planear la optimización de medios locales para el enrutamiento directo

La voz de la red telefónica conmutada (RTC) se considera una aplicación crítica para la empresa con altas expectativas de calidad de voz. Enrutamiento directo le permite controlar los flujos de tráfico multimedia para dar cabida a una multitud de topologías de red y configuraciones de telefonía local para varias empresas de todo el mundo.

La Optimización de medios locales para enrutamiento directo te permite administrar la calidad de voz mediante:

- Controlar cómo fluye el tráfico multimedia entre los clientes de Teams y los controladores de borde de sesión de cliente (SCS).
- Mantener los medios locales dentro de los límites de las subredes de red corporativas.
- Permitir transmisiones multimedia entre los clientes de Teams y los SBCs incluso si los SBCs están detrás de los firewalls corporativos con ips privadas y no son visibles para Microsoft directamente.

La Optimización de medios locales admite dos escenarios:

- Centralización de todos los troncos locales a través de un SBC centralizado conectado al tronco del Protocolo de inicio de sesión (SIP) principal, proporcionando servicios de telefonía a todas las sucursales locales de la compañía.

- Crear una topología de red virtual de los SBC, donde los SBC de las sucursales locales están conectados a un SBC proxy centralizado que es visible para Microsoft Phone System y para comunicarse con ellos a través de su dirección IP externa. En una topología de red virtual, los SBCs intermedios se comunican a través de direcciones IP internas y no son visibles directamente para Phone System.

En este artículo se describen la funcionalidad de las características y los escenarios y soluciones de los clientes. Para obtener más información sobre la configuración, consulta [Configurar optimización de medios locales](direct-routing-media-optimization-configure.md).

  > [!NOTE]
  > Si quieres mantener los medios locales dentro de los límites de la intranet, se recomienda optimización de medios locales. Si ya tienes Media Bypass y usas solo las direcciones IP públicas de tus SBCs, no es obligatorio pasar a Optimización de medios local. Puede seguir usando la omisión de medios. Para obtener más información, vea [Planear la omisión de medios](direct-routing-plan-media-bypass.md).

Para obtener información sobre qué proveedores de SBC admiten optimización de medios locales, consulte [Controladores de borde de sesión certificados para enrutamiento directo](direct-routing-border-controllers.md).

## <a name="supported-customer-scenarios"></a>Escenarios de clientes admitidos

Para esta discusión, supongamos que Contoso ejecuta varias empresas en todo el mundo tal y como se indica a continuación. (Tenga en cuenta que las regiones de Europa y APAC solo se usan como ejemplos. Una empresa puede tener varias regiones diferentes con requisitos similares).

- **En Europa**, Contoso tiene oficinas en aproximadamente 30 países. Cada oficina tiene su propia central de sucursal privada (PBX).

  Se ofreció a Contoso una opción para centralizar los troncos en una sola ubicación ,Amsterdam, para las 30 oficinas europeas. Contoso implementó el SBC en Ámsterdam, proporcionó suficiente ancho de banda para ejecutar llamadas a través de la ubicación centralizada, conectó un tronco SIP central a la ubicación centralizada y comenzó a servir a todas las ubicaciones europeas desde Amsterdam.

- **En la región de APAC**, Contoso tiene varias oficinas en diferentes países.

  En muchos países, la compañía todavía tiene troncos de multiplexación por división temporal (TDM) en sucursales locales. La centralización de los troncos TDM no es una opción en la región de APAC, así que cambiar al SIP no es posible. Suponga que hay más de 50 sucursales de Contoso en toda la región de APAC con cientos de puertas de enlace (SDC). En este escenario, no es posible emparejar todas las puertas de enlace a la interfaz de enrutamiento directo debido a la falta de direcciones IP públicas y/o interrupciones locales de Internet. Además, algunos países imponen requisitos normativos que no se pueden cumplir sin tener conectividad de red RTC local.

En función de sus requisitos empresariales, Contoso implementó dos soluciones con optimización de medios locales para enrutamiento directo:

- **En Europa**, todos los troncos están centralizados y los flujos de medios entre el SBC central y los usuarios, en función de la ubicación del usuario.

  - Si un usuario está conectado a la subred local de una red corporativa (es decir, el usuario es interno), los flujos de medios entre la DIRECCIÓN IP interna del SBC central y el cliente de Teams del usuario.

  - Si un usuario está fuera de los límites de la red corporativa (por ejemplo, si el usuario usa una conexión de Internet inalámbrica pública), se considera que es externo. En este caso, los medios fluyen entre la DIRECCIÓN IP externa del SBC central y el cliente de Teams.

- **En la región de APAC**, un SBC de proxy centralizado está emparejado con Microsoft Direct Routing, que dirige los medios entre la interfaz de Enrutamiento directo y los SBC de bajada de las sucursales locales.

  Los S SBC descendentes de las sucursales locales no son visibles directamente para Direct Routing en APAC, pero se emparejan mediante el cmdlet Set-CSOnlinePSTNGateway para crear una topología de red virtual dentro de Microsoft Phone System. Los medios siempre permanecen locales cuando es posible. Los usuarios externos tienen medios que fluyen entre el cliente de Teams y la DIRECCIÓN IP pública del servidor proxy SBC.

## <a name="central-sbc-with-centralized-trunks"></a>SBC central con troncos centralizados

Para crear una solución donde se proporcionan servicios RTC a todas las sucursales locales a través de una única SBC central con un tronco SIP centralizado conectado, el administrador de inquilinos de Contoso empareja un SBC (centralsbc.contoso.com) al servicio; el SBC tiene un tronco del SIP centralizado conectado a él.

- Cuando un usuario está en la red interna de la empresa, el SBC proporciona la DIRECCIÓN IP interna del SBC para los medios.

- Cuando un usuario está fuera de la red corporativa, el SBC proporciona la IP externa (pública) del SBC.

> [!NOTE]
> Todos los valores incluidos en ejemplos, tablas o diagramas se presentan únicamente con fines ilustrativos.

Tabla 1. Parámetros de red de ejemplo para SBCs

| Ubicación | SBC FQDN | Subred interna | NAT externo (IP de confianza) | Dirección IP externa de SBC | Dirección IP interna de SBC |
|:------------|:-------|:-------|:-------|:-------|:-------|
| Ámsterdam | centralsbc.contoso.com | 192.168.5.0/24 | 172.16.76.73 | 172.16.76.71 | 192.168.5.5 |
| Alemania | No implementado | 192.168.6.0/24 | 172.16.76.74 | No implementado |  No implementado |
| Francia | No implementado | 192.168.7.0/24 | 172.16.76.75 | No implementado |  No implementado |

### <a name="internal-user"></a>Usuario interno

El siguiente diagrama muestra el flujo de tráfico cuando un usuario está conectado a la red corporativa en la sucursal o el sitio del usuario.

Mientras esté en local, el usuario se asigna a la sucursal local en Alemania. El usuario realiza una llamada telefónica de enrutamiento directo a través de Teams.

- El cliente de Teams del usuario se comunica directamente con Sistema telefónico a través de la API rest, pero los elementos multimedia generados durante la llamada fluyen a la dirección IP interna del SBC central.

- El SBC redirige el flujo a Sistema telefónico y a la red RTC conectada.

- El SBC central es visible para el sistema telefónico solo a través de la dirección IP externa.

Diagrama 1. Flujo de tráfico cuando el usuario está en el sitio "principal" con un SBC centralizado y con un tronco SIP centralizado conectado

![Diagrama que muestra optimización de medios locales de flujo de tráfico.](media/direct-routing-media-op-1.png "Flujo de tráfico cuando el usuario está en el sitio &quot;hogar&quot; con SBC centralizado con tronco SIP centralizado conectado")


### <a name="external-user"></a>Usuario externo

El siguiente diagrama muestra el flujo de tráfico cuando un usuario no es local y no está conectado a la red corporativa (es decir, el dispositivo del usuario está conectado a Internet a través de un dispositivo móvil o Wi-Fi público). El usuario realiza una llamada de enrutamiento directo por teléfono a través de Teams:

- El cliente de Teams del usuario se comunica directamente con Sistema telefónico a través de la API rest, pero, en este caso, los medios generados durante la llamada fluyen a la dirección IP externa del SBC central.

- El SBC redirige el flujo a Sistema telefónico y a la red RTC conectada.

- El SBC central es visible para el sistema telefónico solo a través de la dirección IP externa.

En este caso, el comportamiento es similar tanto si el usuario es local en la sucursal de Alemania como en cualquier otra sucursal. El usuario se considera externo porque está fuera de los límites de la red corporativa.

Diagrama 2. Flujo de tráfico cuando el usuario es externo con un SBC centralizado y con un tronco SIP centralizado conectado

![El diagrama muestra optimización de medios locales de flujo de tráfico.](media/direct-routing-media-op-2.png "Flujo de tráfico cuando el usuario es externo en caso de SBC centralizado con tronco SIP centralizado conectado")

## <a name="proxy-sbc-with-connected-downstream-sbcs"></a>SBC de proxy con SBCs conectados en bajada

Para crear una solución en la que los servicios RTC se proporcionan en todas las sucursales locales de la región de APAC donde la centralización de los troncos TDM no es una opción, el administrador de Contoso empareja un SBC (proxysbc.contoso.com), también denominado SBC de proxy, al servicio de enrutamiento directo.

Posteriormente, el administrador de Contoso agrega algunos SBC de bajada, lo que indica que se puede llegar a ellos a través de la proxysbc.contoso.com SBC del proxy. Los SBCs descendentes no tienen IP públicas, sin embargo, se pueden asignar a las rutas de voz. La tabla siguiente muestra parámetros de red y configuración de ejemplo.

Cuando un usuario está en la sucursal local donde se encuentra la SBC descendente, el tráfico multimedia fluye directamente entre el usuario y la SBC local descendente. Si un usuario está fuera de la oficina (en un internet público), los elementos multimedia fluyen desde el usuario a la DIRECCIÓN IP pública del servidor proxy SBC, que lo proxya a las SBC correspondientes aguas abajo.

Tabla 2. Información de red SBC de ejemplo

| Ubicación | SBC FQDN | Subred interna | NAT externo (IP de confianza) | Dirección IP externa de SBC  | Dirección IP interna de SBC |
|:------------|:-------|:-------|:-------|:-------|:-------|
| Vietnam | VNsbc.contoso.com | 192.168.1.0/24 | 172.16.240.110 | Ninguna |  192.168.1.5 |
| Indonesia  | IDsbc.contoso.com | 192.168.2.0/24 | 172.16.240.120 | Ninguna |  192.168.2.5 |
| Singapur | proxysbc.contoso.com |   192.168.3.0/24 | 172.16.240.130 | 172.16.240.133 | 192.168.3.5 |



### <a name="internal-user"></a>Usuario interno

El siguiente diagrama muestra el flujo de tráfico de alto nivel para el escenario cuando un usuario está dentro de la oficina en la región de APAC.
El usuario, que está asignado a una sucursal local en Vietnam y es local, realiza una llamada telefónica de enrutamiento directo a través de Teams.

- El cliente de Teams del usuario se comunica con Sistema telefónico directamente a través de la API rest, pero los elementos multimedia generados durante la llamada fluyen a la dirección IP interna del SBC local.

- El SBC local redirige el flujo al servidor proxy SBC en Singapur y a la red RTC local conectada.

-  El proxy SBC es visible para el sistema telefónico a través de la dirección IP externa solamente y enruta el flujo desde el SBC descendente (en este caso el SBC local en Vietnam) a Phone System.

- El SBC descendente en la sucursal local no es visible directamente para Phone System, pero se asigna dentro de la topología de red virtual definida por el administrador de Contoso al configurar Optimización de medios locales.

> [!NOTE]
> El comportamiento puede ser diferente para los usuarios locales y no locales en función del modo de optimización de medios locales configurado.

Para obtener más información sobre los posibles modos y el comportamiento relevante, consulta Configurar optimización de medios locales.

Diagrama 3. Flujo de tráfico cuando el usuario está en la red "doméstica" con un SBC de proxy y con SBCs conectados

![Diagrama que muestra de nuevo la optimización de medios locales de flujo de tráfico.](media/direct-routing-media-op-3.png "Traffic flow in case of proxy SBC with connected downstream SBCs when user is in the \"home\" network")

### <a name="external-user"></a>Usuario externo

El siguiente diagrama muestra el flujo de tráfico cuando un usuario está fuera de los límites de la red corporativa. El usuario no es local (no está dentro de los límites de la red corporativa). El usuario realiza una llamada telefónica de enrutamiento directo a través de Teams a un número de teléfono en Vietnam.

- El cliente de Teams del usuario se comunica directamente con Phone System a través de la API rest, pero los elementos multimedia generados durante la llamada fluyen en primer lugar a la dirección IP externa del servidor proxy SBC de Singapur.

- Según las directivas de configuración y voz (consulte [Configurar optimización de medios locales](direct-routing-media-optimization-configure.md) para obtener detalles), el proxy SBC redirige el flujo al SBC descendente en Vietnam.

- El SBC aguas abajo en Vietnam redirige el flujo a la red RTC local conectada.

- El servidor proxy SBC es visible para el sistema telefónico solo a través de la dirección IP externa.

-  El SBC descendente en la sucursal local no es visible directamente para Phone System, pero se asigna dentro de la topología de red virtual que define el administrador de Contoso al configurar Optimización de medios locales. En el ejemplo, el usuario se considera externo porque está fuera de los límites de la red corporativa.

Diagrama 4. Flujo de tráfico cuando el usuario es externo con un SBC de proxy y con SBCs conectados aguas abajo

![El diagrama muestra de nuevo el flujo de tráfico Optimización de medios locales.](media/direct-routing-media-op-4.png "Flujo de tráfico en caso de SBC de proxy con SBCs de bajada conectados cuando el usuario es externo")

## <a name="local-media-optimization-modes"></a>Modos de optimización de medios locales

La Optimización de medios locales admite dos modos:

- **Modo 1: Omitir siempre**. En este caso, si el usuario es interno, los medios fluirán a través de la dirección IP interna de la SBC local, independientemente de la ubicación real del usuario interno; por ejemplo, dentro de la misma sucursal donde se encuentra la SBC descendente o en alguna otra sucursal.

- **Modo 2: Solo para usuarios locales**. En este modo, los elementos multimedia fluirán directamente a la dirección IP interna de la SBC de bajada local solo cuando lo genere el usuario interno ubicado en la misma sucursal que la SBC descendente.

Para distinguir entre modos de optimización de medios locales, el administrador de inquilinos debe establecer el parámetro -BypassMode en 'Always' o 'OnlyForLocalUsers' para cada SBC mediante el cmdlet de Set-CSonlinePSTNGateway. Para obtener más información, consulta [Configurar optimización de medios locales](direct-routing-media-optimization-configure.md).

> [!NOTE]
> Cuando los usuarios son internos, se **requiere** conectividad multimedia entre el usuario y el SBC a través de la dirección IP interna. No hay ninguna reserva a los relés de transporte público para los medios en este caso, ya que el SBC proporcionará una IP interna para la conectividad multimedia.

### <a name="mode-1-always-bypass"></a>Modo 1: Omitir siempre

Si tiene una buena conexión entre sucursales, el modo recomendado es Omitir siempre.

Por ejemplo, supongamos que una compañía tiene un tronco SIP centralizado en Ámsterdam, que sirve a 30 países y tiene buena conectividad entre los 30 sitios y los usuarios locales. También hay una rama en Alemania donde se implementa un SBC local.

El SBC en Alemania se puede configurar en modo "Siempre bypass". Los usuarios, independientemente de su ubicación, se conectarán al SBC directamente a través de la dirección IP interna del SBC (por ejemplo, de Francia a Alemania; consulte el diagrama siguiente para obtener referencia).

A continuación se describen dos escenarios:

- Escenario 1. El usuario está en la misma ubicación que el SBC definido en la directiva de enrutamiento de voz en línea.

- Escenario 2. El usuario y las puertas de enlace están en sitios diferentes.

#### <a name="scenario-1-the-user-is-in-the-same-location-as-the-sbc-defined-in-the-online-voice-routing-policy"></a>Escenario 1. El usuario está en la misma ubicación que el SBC definido en la directiva de enrutamiento de voz en línea

El SBC en Ámsterdam está configurado para ser un proxy SBC para un SBC local aguas abajo en Alemania. El usuario está en Alemania dentro de la misma subred que la red corporativa de la SBC local. Ambos SBCs (proxy y aguas abajo) están configurados para el modo Siempre omitido. Las directivas de enrutamiento de voz en línea especifican que, en caso de llamadas dentro de Alemania (con código de área +49), deben redirigirse al SBC local en Alemania. Todas las demás llamadas (y en caso de que el SBC de Alemania falle, las llamadas en Alemania) deben redirigirse al servidor proxy SBC en Ámsterdam. En la tabla siguiente se resume la configuración de ejemplo.

Tabla 3. Configuración de ejemplo para el escenario 1

| Ubicación física del usuario | El usuario realiza una llamada a un número | Directiva de enrutamiento de voz en línea | Modo configurado para SBC | Flujo de medios |
|:------------|:-------|:-------|:-------|:-------|
| Alemania | +49 1 437 2800 | Prioridad 1: ^\+49(\d{8})$ -DEsbc.contoso.com<br>Prioridad 2: .* - proxysbc.contoso.com| DEsbc.contoso.com: omitir siempre <br>proxysbc.contoso.com: omitir siempre | < de usuario de Teams: > DEsbc.contoso.com |

El diagrama siguiente muestra el flujo de tráfico de alto nivel para el usuario interno en Alemania que realiza una llamada telefónica de enrutamiento directo a través de Teams al número de Alemania.

- El cliente de Teams del usuario se comunica con Sistema telefónico directamente a través de la API REST.

- Los medios generados durante la llamada fluyen a la dirección IP interna del SBC local.

- El SBC local redirige el flujo al servidor proxy SBC en Ámsterdam y a la red RTC local conectada.

- El proxy SBC es visible para el sistema telefónico a través de la dirección IP externa solamente y enruta el flujo desde el SBC descendente (en este caso, el SBC local en Alemania) a Phone System.

- El SBC descendente en la sucursal local no es visible directamente para Phone System, pero se asigna dentro de la topología de red virtual definida por el administrador de Contoso al configurar Optimización de medios locales.


Diagrama 5.  Flujo de tráfico con el modo "Omitir siempre" y el usuario se encuentra en el sitio "principal"

![Diagrama que muestra optimización de medios locales de flujo de tráfico.](media/direct-routing-media-op-5.png "El flujo de tráfico con el modo &quot;Omitir siempre&quot; y el usuario está en el sitio &quot;principal&quot;")


#### <a name="scenario-2-the-user-and-gateways-are-in-different-sites"></a>Escenario 2: El usuario y las puertas de enlace están en diferentes sitios

El SBC en Ámsterdam está configurado para ser un proxy SBC para un SBC local aguas abajo en Alemania. Ambos SBCs (proxy y aguas abajo) están configurados para el modo Siempre omitido. El usuario interno en Francia, ubicado en la sucursal local, está realizando una llamada de enrutamiento directo a Alemania. Las directivas de enrutamiento de voz en línea especifican que las llamadas a Alemania (con el código de área +49) deben redirigirse al SBC local de Alemania. Todas las demás llamadas (y, en caso de que el SBC de Alemania falle, todas las llamadas en Alemania) deben redirigirse al servidor proxy SBC en Ámsterdam. En la tabla siguiente se resume la configuración de ejemplo.

Tabla 4. Configuración de ejemplo para el escenario 2

| Ubicación física del usuario | El usuario realiza una llamada a un número | Directiva de enrutamiento de voz en línea | Modo configurado para SBC | Flujo de medios |
|:------------|:-------|:-------|:-------|:-------|
| Francia | +49 1 437 2800 | Prioridad 1: ^\+49(\d{8})$ -DEsbc.contoso.com <br>Prioridad 2: .* - proxysbc.contoso.com |  DEsbc.contoso.com: omitir siempre proxysbc.contoso.com: omitir siempre | < de usuarios de Teams: > DEsbc.contoso.com  |

El siguiente diagrama muestra el flujo de tráfico de alto nivel cuando el usuario interno alemán ubicado en Francia realiza una llamada telefónica de enrutamiento directo a través de Teams al número de Alemania.

- El cliente de Teams del usuario se comunica con Sistema telefónico directamente a través de la API REST.

- Los medios generados durante la llamada fluyen directamente al SBC en la dirección IP interna de Alemania.

- El SBC en Alemania redirige el flujo al servidor proxy SBC en Ámsterdam y a la red RTC local conectada.

Diagrama 6.  Flujo de tráfico con el modo "Omitir siempre" y el usuario no está en el sitio "particular", sino en la red interna

![Un diagrama muestra optimización de medios locales de flujo de tráfico.](media/direct-routing-media-op-6.png "El flujo de tráfico con el modo &quot;Omitir siempre&quot; y el usuario no está en el sitio &quot;particular&quot;, sino en la red interna")

### <a name="mode-2-only-for-local-users"></a>Modo 2: Solo para usuarios locales

Si hay conexiones incorrectas entre las sucursales locales pero buenas conexiones entre cada sucursal local y la oficina regional, el modo recomendado es "Solo para usuarios locales".

Por ejemplo, en la región de APAC, supongamos que Contoso tiene varias oficinas en diferentes países. Para muchos países, cambiar a SIP no es posible porque la compañía todavía tiene troncales TDM en muchas sucursales locales. La centralización de los troncos TDM no es una opción en la región de APAC. Además, hay más de 50 sucursales de Contoso en toda la región de APAC con cientos de puertas de enlace (SFC).

Para crear una solución en la que los servicios RTC se proporcionan en todas las sucursales locales de la región de APAC donde la centralización de los troncos TDM no es una opción, el administrador de Contoso empareja un SBC regional en Singapur como el SBC proxy al servicio de enrutamiento directo. La conexión directa entre las sucursales locales no es buena, pero hay una buena conexión entre cada sucursal local y la SBC regional en Singapur. Para el SBC regional, el administrador elige el modo "Omitir siempre" y, para los SBC locales en bajada, el administrador elige el modo "Solo para usuarios locales".

A continuación se describen dos escenarios:

- Escenario 1. El usuario está en la misma ubicación que el SBC definido en la directiva de enrutamiento de voz en línea

- Escenario 2. El usuario y las puertas de enlace están en sitios diferentes

#### <a name="scenario-1-the-user-is-in-the-same-location-as-the-sbc-defined-in-online-voice-routing-policy"></a>Escenario 1. El usuario está en la misma ubicación que el SBC definido en la directiva de enrutamiento de voz en línea

Suponga que el SBC en Singapur está configurado para ser un SBC proxy para los SBC locales aguas abajo en Vietnam e Indonesia. El usuario está en Vietnam dentro de la misma ubicación que el SBC local. Las directivas de enrutamiento de voz en línea especifican que las llamadas en Vietnam (con el código de área +84) deben redirigirse al SBC local en Vietnam. Todas las demás llamadas (y, si el SBC en Vietnam falla, las llamadas en Vietnam) deben redirigirse al servidor proxy SBC en Singapur. En la tabla siguiente se resume la configuración de ejemplo.

Tabla 5. Configuración de ejemplo para el escenario 1 del modo "Solo para usuarios locales"

| Ubicación física del usuario | El usuario realiza una llamada a un número | Directiva de enrutamiento de voz en línea | Modo configurado para SBC | Flujo de medios |
|:------------|:-------|:-------|:-------|:-------|
| Vietnam | +84 4 3926 3000 | Prioridad 1: ^\+84(\d{9})$ -VNsbc.contoso.com <br>Prioridad 2: .* - proxysbc.contoso.com | VNsbc.contoso.com: solo para usuarios locales <br> proxysbc.contoso.com: omitir siempre | < de usuario de Teams: > VNsbc.contoso.com |

En el siguiente diagrama, un usuario asignado a la sucursal local en Vietnam, mientras está en local, realiza una llamada telefónica de enrutamiento directo a través de Teams.

- El cliente de Teams del usuario se comunica con Sistema telefónico directamente a través de la API REST.

- Los medios generados durante la llamada fluyen a la dirección IP interna del SBC local.

- El SBC local redirige el flujo al servidor proxy SBC en Singapur y a la red RTC local conectada.

- El proxy SBC es visible para el sistema telefónico a través de la dirección IP externa solamente y enruta el flujo desde el SBC descendente (en este caso, el SBC local en Vietnam) a Phone System.

- El SBC descendente en la sucursal local no es visible directamente para Phone System, pero se asigna dentro de la topología de red virtual.

Diagrama 7. Flujo de tráfico con el modo "Solo para usuarios locales" y el usuario está en el sitio "principal"

![Otro diagrama que muestra optimización de medios locales de flujo de tráfico.](media/direct-routing-media-op-7.png "El flujo de tráfico con el modo &quot;Solo para usuarios locales&quot; y el usuario está en el sitio &quot;principal&quot;")


#### <a name="scenario-2-the-user-and-gateways-are-in-different-sites"></a>Escenario 2. El usuario y las puertas de enlace están en sitios diferentes

Suponga que el SBC en Singapur está configurado para ser un SBC proxy para los SBC locales aguas abajo en Vietnam e Indonesia. El usuario interno en Indonesia, ubicado en la sucursal local, está realizando una llamada de enrutamiento directo a Vietnam. Las directivas de enrutamiento de voz en línea especifican que las llamadas a Vietnam (con código de área +84) deben redirigirse al SBC local de Vietnam. Todas las demás llamadas (y, en caso de que el SBC en Vietnam falle, las llamadas a Vietnam) deben redirigirse al servidor proxy SBC en Singapur. El proxy SBC en Singapur se establece en modo "Siempre bypass", y el SBC local en Vietnam se establece en modo "Solo para usuarios locales". En la tabla siguiente se resume la configuración de ejemplo.

Tabla 6. Configuración de usuario

| Ubicación física del usuario | El usuario realiza una llamada a un número | Directiva de enrutamiento de voz en línea | Modo configurado para SBC | Flujo de medios |
|:------------|:-------|:-------|:-------|:-------|
| Indonesia | +84 4 3926 3000 | Prioridad 1: ^\+84(\d{9})$ -VNsbc.contoso.com <br> Prioridad 2: .* - proxysbc.contoso.com |VNsbc.contoso.com: solo para usuarios locales <br> proxysbc.contoso.com: omitir siempre | < de usuario de Teams(> proxysbc.contoso.com <)> VNsbc.contoso.com |


En el siguiente diagrama, el usuario interno, mientras se encuentra de forma local en la sucursal indonesia, realiza una llamada de enrutamiento directo de teléfono a través de Teams a un número en Vietnam.

- El cliente de Teams del usuario se comunica con Sistema telefónico directamente a través de la API REST.

- Medios generados durante los flujos de llamada a la dirección IP interna del proxy SBC en primer lugar.

- El servidor proxy SBC en Singapur redirige el flujo a la dirección IP interna de la SBC aguas abajo en Vietnam y a Phone System.

- El SBC aguas abajo en Vietnam enruta el flujo a la red RTC local conectada.

- El servidor proxy SBC es visible para el sistema telefónico solo a través de la dirección IP externa.

- Los SDC descendentes en sucursales locales no son visibles directamente para Phone System, pero se asignan dentro de la topología de red virtual.

Diagrama 8.  Flujo de tráfico con el modo "Solo para usuarios locales" y el usuario no está en el sitio "principal" sino en la red interna

![Otro diagrama muestra optimización de medios locales de flujo de tráfico.](media/direct-routing-media-op-8.png "Flujo de tráfico con el modo &quot;Solo para usuarios locales&quot;, el usuario no está en el sitio &quot;principal&quot; sino en la red interna")

## <a name="known-issues"></a>Problemas conocidos

La siguiente es una lista de problemas conocidos que están actualmente presentes en optimización de medios locales. Microsoft está trabajando para solucionar estos problemas.

| Problema | Solución |
| :--- | :--- |
| El cliente de Teams no se identifica como **interno** cuando la IP pública del cliente de Teams coincide con la lista ip de confianza del cliente. | La optimización de medios locales requiere que la subred del cliente de Teams coincida con la [subred de red](/powershell/module/skype/new-cstenantnetworksubnet) configurada por un inquilino|
| Las escalaciones de llamadas provocan llamadas caídas cuando el cliente de Teams se identifica como interno.| Deshabilita la Optimización de medios locales en el SBC de enrutamiento directo.|
| Escalaciones de llamadas de 1 a 1 llamada entre clientes internos a llamadas de varias partes con el resultado de cliente o recurso externo en llamadas interrumpidas | Trabajo en curso para encontrar una corrección. Como alternativa, deshabilita la Optimización de medios locales en el SBC de enrutamiento directo.|
| El usuario de Teams pone la llamada en espera. La música se reproduce al final de LA RTC y la optimización de medios locales funciona. El usuario de Teams reanuda la llamada. La llamada a RTC se reanuda, pero optimización de medios locales no funciona y la llamada continúa a través de Central (Proxy) SBC | Cuando un usuario estaciona una llamada para iniciar la música en espera (MoH), se está escalando de 1:1 a una llamada de varias partes por el controlador de llamada para invocar el controlador multimedia y el procesador multimedia (que sirve como mezclador AVMCU) a través del cual MoH llega a un usuario que se ha puesto en espera. La desviación a una llamada individual después de reanudar la llamada nunca se produce según el diseño. Deshabilita la Optimización de medios locales en el SBC de enrutamiento directo.|
|Mientras se establece una llamada durante unos segundos, es posible que el usuario escuche silencio.| Debido a la complejidad de la arquitectura de Optimización de medios locales, esto puede ocurrir en algunos casos.|
|Las aplicaciones de voz (por ejemplo, Operador automático, Cola de llamadas) no funcionan.| La Optimización de medios locales no admite las aplicaciones de voz porque residen en la nube y requieren conectividad externa. Para ver Location-Based escenarios de enrutamiento, consulte [Aplicaciones de voz (operador automático o cola de llamadas).](location-based-routing-plan.md#inbound-calls-through-voice-apps-auto-attendant-or-call-queue)|
