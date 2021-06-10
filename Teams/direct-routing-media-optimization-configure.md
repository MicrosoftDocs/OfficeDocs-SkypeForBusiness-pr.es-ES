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
description: Configurar la optimización de medios locales para enrutamiento directo
appliesto:
- Microsoft Teams
ms.openlocfilehash: ecbbb4f01267265f9f1041e7d51652d063ced353
ms.sourcegitcommit: 2aea6ec07149a3054ee4434c8a0bffabf1a16d25
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "46576992"
---
# <a name="configure-local-media-optimization-for-direct-routing"></a>Configurar la optimización de medios locales para enrutamiento directo

La configuración de optimización de medios locales se basa en la configuración de red que es común a otras características de voz en la nube, como el enrutamiento Location-Based y las llamadas de emergencia dinámicas. Para obtener más información sobre regiones de red, sitios de red, subredes de red y direcciones IP de confianza, vea Configuración de red para [características de voz en la nube.](cloud-voice-network-settings.md)

Antes de configurar la optimización de medios locales, [vea Optimización de medios locales para enrutamiento directo.](direct-routing-media-optimization.md)  

Para configurar la optimización de medios locales, se necesitan los pasos siguientes. Puede usar el Centro Teams de administración o PowerShell. Para obtener más información, [vea Administrar la topología de red.](manage-your-network-topology.md)

1. Configure el usuario y los sitios de SBC (como se describe en este artículo).
2. Configure los SBC para la optimización de medios locales (según la especificación del proveedor de SBC).

En el siguiente diagrama se muestra la configuración de red usada en los ejemplos de este artículo.

![Diagrama que muestra la configuración de red para ejemplos](media/direct-routing-media-op-9.png "Configuración de red para ejemplos")


## <a name="configure-the-user-and-the-sbc-sites"></a>Configurar el usuario y los sitios de SBC

Para configurar el usuario y los sitios de SBC, deberá:

1. [Administrar direcciones IP de confianza externa.](#manage-external-trusted-ip-addresses)  

2. [Defina la topología de red](#define-the-network-topology) configurando las regiones de red, los sitios de red y las subredes de red.

3. [Defina la topología de red virtual](#define-the-virtual-network-topology) asignando SBC a sitios con modos relevantes y valores SBC proxy.


## <a name="configure-sbcs-for-local-media-optimization-according-to-the-sbc-vendor-specification"></a>Configurar SBC para optimización de medios locales según la especificación de proveedor de SBC

En este artículo se describe la configuración de los componentes de Microsoft. Para obtener información sobre la configuración de SBC, consulte la documentación del proveedor de SBC.

La optimización de medios locales es compatible con los siguientes proveedores de SBC:

| Proveedor | Producto |    Versión de software |
|:------------|:-------|:-------|
| [AudioCodes](https://www.audiocodes.com/media/13253/connecting-audiocodes-sbc-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf) |    SBC Mediant 500 |   7.20A.256 | 
|            |  SBC Mediant 800 |   7.20A.256 | 
|            |  SBC Mediant 2600 |  7.20A.256 | 
|            |  SBC Mediant 4000 |  7.20A.256 | 
|            |  Mediant 1000B SBC | 7.20A.256 | 
|            |  Mediant 9000 SBC |  7.20A.256 | 
|            |  Mediant Virtual Edition SBC |   7.20A.256 | 
|            |  Mediant Cloud Edition SBC | 7.20A.256 |
| [Cinta de SBC Core](https://support.sonus.net/display/ALLDOC/SBC+8.2+-+Configure+Local+Media+Optimization)  |  SBC 5110         | 8.2  |
|            |  SBC 5210         | 8.2  |
|            |  SBC 5400         | 8.2  |
|            |  SBC 7000         | 8.2  |
|            |  SBC SWe          | 8.2  |
| [Cinta de opciones SBC Edge](https://support.sonus.net/display/UXDOC81/Best+Practice+-+Configuring+Microsoft+Teams+Local+Media+Optimization)  |  SBC SWe Lite | 8.1.5 |
|               | SBC 1000 | 8.1.5  |
|               | SBC 2000 | 8.1.5  |
| [TE-SYSTEMS](https://www.anynode.de/local_media_optimization/) |  anynode          | 4.0.1+ |
| [Oracle](https://www.oracle.com/industries/communications/enterprise-communications/session-border-controller/microsoft.html) | AP 1100 | 8.4.0.0.0 |
|        | AP 3900 | 8.4.0.0.0 |
|        | AP 4600 | 8.4.0.0.0 | 
|        | AP 6300 | 8.4.0.0.0 |
|        | AP 6350 | 8.4.0.0.0 | 
|        | VME     | 8.4.0.0.0 |


## <a name="manage-external-trusted-ip-addresses"></a>Administrar direcciones IP de confianza externa

Las IP de confianza externa son las IP externas de Internet de la red empresarial. Estas DIRECCIONES IP son las direcciones IP que usan los Microsoft Teams cuando se conectan a Microsoft 365. Debe agregar estas IP externas para cada sitio en el que tenga usuarios con optimización de medios locales.

Para agregar las direcciones IP públicas de cada sitio, use el cmdlet New-CsTenantTrustedIPAddress sitio. Puede definir un número ilimitado de direcciones IP de confianza para un inquilino. Si las direcciones IP externas que Microsoft 365 son direcciones IPv4 e IPv6, debe agregar ambos tipos de direcciones IP. Para IPv4, use la máscara 32. Para IPv6, use la máscara 128. Puede agregar direcciones IP externas individuales y subredes IP externas especificando diferentes MaskBits en el cmdlet.

```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description>
```


Ejemplo de agregar direcciones IP de confianza.

```
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.110 -MaskBits 32 -Description "Vietnam site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.120 -MaskBits 32 -Description "Indonesia site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.130 -MaskBits 32 -Description "Singapore site trusted IP"
```


## <a name="define-the-network-topology"></a>Definir la topología de red

En esta sección se describe cómo definir las regiones de red, los sitios de red y las subredes de red para la topología de red.

Todos los parámetros distinguen entre mayúsculas y minúsculas, por lo que debe asegurarse de usar el mismo caso que se usó durante la configuración.  (Por ejemplo, los valores GatewaySiteID "Vietnam" y "vietnam" se tratarán como sitios diferentes).

### <a name="define-network-regions"></a>Definir regiones de red

Para definir regiones de red, use el cmdlet New-CsTenantNetworkRegion red. El parámetro Id.región es un nombre lógico que representa la geografía de la región y no tiene dependencias ni restricciones. El parámetro CentralSite <site ID> es opcional.

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

En el ejemplo siguiente se crea una región de red denominada APAC:

```
New-CsTenantNetworkRegion -NetworkRegionID "APAC"  
```

###  <a name="define-network-sites"></a>Definir sitios de red

Para definir sitios de red, use el cmdlet New-CsTenantNetworkSite red. Cada sitio de red debe estar asociado a una región de red.

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

En el ejemplo siguiente se crean tres nuevos sitios de red, Vietnam, Indonesia y Singapur en la región de APAC:

```
New-CsTenantNetworkSite -NetworkSiteID "Vietnam" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Indonesia" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Singapore" -NetworkRegionID "APAC"
```

### <a name="define-network-subnets"></a>Definir subredes de red

Para definir subredes de red y asociarlas a sitios de red, use el cmdlet New-CsTenantNetworkSubnet red. Cada subred de red solo se puede asociar a un sitio. 

```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

En el ejemplo siguiente se definen tres subredes de red y se asocian a los tres sitios de red: Vietnam, Indonesia y Singapur:

```
New-CsTenantNetworkSubnet -SubnetID 192.168.1.0 -MaskBits 24 -NetworkSiteID “Vietnam”
New-CsTenantNetworkSubnet -SubnetID 192.168.2.0 -MaskBits 24 -NetworkSiteID “Indonesia”
New-CsTenantNetworkSubnet -SubnetID 192.168.3.0 -MaskBits 24 -NetworkSiteID “Singapore”
```

## <a name="define-the-virtual-network-topology"></a>Definir la topología de red virtual 

En primer lugar, el administrador de inquilinos crea una nueva configuración de SBC para cada SBC relevante mediante el cmdlet New-CsOnlinePSTNGateway espacio empresarial.
El administrador de inquilinos define la topología de red virtual especificando los sitios de red para los objetos de puerta de enlace RTC con el cmdlet Set-CsOnlinePSTNGateway datos:

```
PS C:\> Set-CsOnlinePSTNGateway -Identity <Identity> -GatewaySiteID <site ID> -MediaBypass <true/false> -BypassMode <Always/OnlyForLocalUsers> -ProxySBC  <proxy SBC FQDN or $null>
```

Tenga en cuenta lo siguiente: 
   - Si el cliente tiene un único SBC, el parámetro -ProxySBC debe ser obligatorio $null o fqdn de SBC (escenario de SBC central con troncos centralizados).
   - El parámetro -MediaBypass debe establecerse en $true para admitir la optimización de medios locales.
   - Si el SBC no tiene el conjunto de parámetros -BypassMode, los encabezados X-MS no se enviarán. 
   - Todos los parámetros distinguen entre mayúsculas y minúsculas, por lo que debe asegurarse de que usa el mismo caso que se usó durante la configuración.  (Por ejemplo, los valores GatewaySiteID "Vietnam" y "vietnam" se tratarán como sitios diferentes).

En el ejemplo siguiente se agregan tres SBC a los sitios de red Vietnam, Indonesia y Singapur en la región de APAC con el modo Omitir siempre:

```
Set-CSOnlinePSTNGateway -Identity “proxysbc.contoso.com” -GatewaySiteID “Singapore” -MediaBypass $true -BypassMode “Always” -ProxySBC $null

Set-CSOnlinePSTNGateway -Identity “VNsbc.contoso.com” -GatewaySiteID “Vietnam” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”

Set-CSOnlinePSTNGateway -Identity “IDsbc.contoso.com” -GatewaySiteID “Indonesia” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”
```

Nota: Para garantizar las operaciones sin interrupciones cuando la optimización de medios locales y el enrutamiento Location-Based (LBR) están configurados al mismo tiempo, los SBC descendentes deben habilitarse para LBR estableciendo el parámetro GatewaySiteLbrEnabled en $true para cada SBC descendente. (Esta configuración no es obligatoria para el SBC proxy).

Según la información anterior, enrutamiento directo incluirá tres encabezados SIP propietarios a invitaciones SIP y re-invitaciones, como se muestra en la tabla siguiente.

Encabezados X-MS introducidos en Enrutamiento directo en invitaciones y Re-Invites si BypassMode está definido:

| Nombre del encabezado | Valores | Comentarios | 
|:------------|:-------|:-------|
| X-MS-UserLocation | interno/externo | Indica si el usuario es interno o externo |
| Request-URI INVITE sip: +84439263000@VNsbc.contoso.com SIP /2.0 | SBC FQDN | El FQDN que está dirigido a la llamada incluso si el SBC no está conectado directamente al enrutamiento directo |
| X-MS-MediaPath | Ejemplo: proxysbc.contoso.com, VNsbc.contoso.com | Orden de SBC que debe usarse para la ruta de acceso multimedia entre el usuario y el SBC de destino. El SBC final siempre es el último |
| X-MS-UserSite | usersiteID | Cadena definida por el administrador de inquilinos |

## <a name="call-flows"></a>Flujos de llamadas 

A continuación se muestran los flujos de llamadas para dos modos:

- [Omitir siempre](#always-bypass-mode)
- [Solo para usuarios locales](#only-for-local-users-mode)

### <a name="always-bypass-mode"></a>Modo Omitir siempre

El modo Omitir siempre es la opción más sencilla de configurar. El administrador de inquilinos puede configurar un único sitio para todos los usuarios y SBC si todos los SBC son accesibles desde cualquier sitio.

Los ejemplos muestran el modo de omisión siempre para los siguientes escenarios:

- [Las llamadas salientes y el usuario se encuentra en la misma ubicación que el SBC](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [Las llamadas entrantes y el usuario se encuentra en la misma ubicación que el SBC](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [Llamadas salientes y el usuario es externo](#outbound-calls-and-the-user-is-external-with-always-bypass)
- [Llamadas entrantes y el usuario es externo](#inbound-calls-and-the-user-is-external-with-always-bypass)

En la tabla siguiente se muestran los FQDN y las direcciones IP que se usan en los ejemplos:

| FQDN | Dirección IP externa de SBC | Dirección IP interna de SBC | Subred interna | Ubicación | NAT externa (IP de confianza) |
|:------------|:-------|:-------|:-------|:-------|:-------|
| VNsbc.contoso.com | Ninguna | 192.168.1.5 | 192.168.1.0/24 | Vietnam | 172.16.240.110 |
| IDsbc.contoso.com | Ninguna | 192.168.2.5 | 192.168.2.0/24 | Indonesia | 172.16.240.120 |
| proxysbc.contoso.com | 172.16.240.133 | 192.168.3.5 | 192.168.3.0/24 | Singapur | 172.16.240.130 |



#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a>Las llamadas salientes y el usuario se encuentra en la misma ubicación que el SBC con Omitir siempre

| Modo |    Usuario |  Ubicación |  Dirección de llamada |
|:------------|:-------|:-------| :-------|
| AlwaysBypass |    Interno |  El mismo sitio que SBC |  Saliente |

En la tabla siguiente se muestra la configuración y la acción del usuario final:

| Ubicación física del usuario| El usuario realiza o recibe una llamada a/desde un número | Número de teléfono de usuario  | Directiva de enrutamiento de voz en línea | Modo configurado para SBC |
|:------------|:-------|:-------|:-------|:-------|
| Vietnam | +84 4 3926 3000 | +84 4 5555 5555   | Prioridad 1: ^ \+ 84(\d {9} )$ -VNsbc.contoso.com <br> Prioridad 2: .* - proxysbc.contoso.com   | VNsbc.contoso.com: omitir siempre <br> proxysbc.contoso.com: omitir siempre


En el siguiente diagrama se muestra la escala SIP para una llamada saliente con el modo Desviado siempre y el usuario en la misma ubicación que el SBC.

![Diagrama que muestra las llamadas salientes](media/direct-routing-media-op-10.png "Llamadas salientes")

En la tabla siguiente se muestran los encabezados X-MS enviados por Enrutamiento directo:

| Parámetro | Explicación |
|:------------|:-------|
| Invitar +8443926300@VNsbc.contoso.com | El FQDN de destino del SBC definido en la directiva de enrutamiento de voz en línea se envía en el URI de solicitud | 
| X-MS-UserLocation: interno | El campo indicaba que el usuario se encuentra dentro de la red corporativa |
| X-MS-MediaPath: VNsbc.contoso.com |   Especifica el SBC que el cliente debe atravesar hasta el SBC de destino. En este caso, como siempre hemos omitdo, y el cliente es interno el nombre de destino enviado como el único nombre en el encabezado. | 
|X-MS-UserSite: Vietnam |   El campo indicado dentro del sitio donde se encuentra el usuario. |


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a>Las llamadas entrantes y el usuario se encuentra en la misma ubicación que el SBC con Omitir siempre

| Modo |    Usuario |  Ubicación |  Dirección de llamada |
|:------------|:-------|:-------|:-------|:-------|
| AlwaysBypass |    Interno | El mismo sitio que SBC | Entrada |


En una llamada entrante, se desconoce la ubicación del usuario y el SBC debe adivinar dónde está el usuario. Si la conjetura no es correcta, se requiere una nueva invitación. En este caso se supone que el usuario es interno, que los medios pueden fluir directamente y que no es necesario realizar más acciones (volver a invitar).
El SBC conectado al servicio de enrutamiento directo notifica la ubicación de SBC de origen proporcionando Record-Route y campos de contacto. En función de estos campos, la ruta de acceso multimedia se calcula mediante enrutamiento directo.

Nota: Dado que un usuario puede tener varios puntos de conexión, no es posible admitir 183. El enrutamiento directo siempre usará 180 llamadas en este caso. 

En el siguiente diagrama se muestra la escala SIP para las llamadas entrantes con el modo AlwaysBypass y el usuario se encuentra en la misma ubicación que el SBC.

![Diagrama que muestra la escala SIP](media/direct-routing-media-op-11.png)


#### <a name="outbound-calls-and-the-user-is-external-with-always-bypass"></a>Llamadas salientes y el usuario es externo con Omitir siempre

| Modo |    Usuario |  Sitio |  Dirección de llamada
|:------------|:-------|:-------|:-------|
AlwaysBypass |  Externo |  N/D | Saliente |


En el siguiente diagrama se muestra la escala SIP para una llamada saliente con el modo AlwaysBypass y el usuario es externo:

![Diagrama que muestra la escala SIP](media/direct-routing-media-op-12.png)

En la tabla siguiente se muestran los encabezados X-MS enviados por el servicio de enrutamiento directo:

| Parámetro |   Explicación |
|:------------|:-------|
|Invitar +8443926300@VNsbc.contoso.com | El FQDN de destino del SBC definido en la directiva de enrutamiento de voz en línea se envía en el URI de solicitud.|
| X-MS-UserLocation: externa | El campo indicaba que el usuario se encuentra fuera de la red corporativa. |
| X-MS-MediaPath: proxysbc.contoso.com, VNsbc.contoso.com    | Especifica el SBC que el cliente debe atravesar hasta el SBC de destino. En este caso, como siempre hemos omitdo, y el cliente es externo. |

#### <a name="inbound-calls-and-the-user-is-external-with-always-bypass"></a>Las llamadas entrantes y el usuario son externos con Omitir siempre

| Modo | Usuario | Sitio |  Dirección de llamada |
|:------------|:-------|:-------|:-------|
AlwaysBypass |  Externo |  N/D |   Entrada |

Para una llamada entrante, el SBC conectado a Enrutamiento directo debe enviar una nueva invitación (de forma predeterminada, siempre se ofrecen candidatos de medios locales) si la ubicación del usuario es externa.  X-MediaPath se calcula en función Record-Route usuario de SBC especificado.

En el siguiente diagrama se muestra la escala SIP de una llamada entrante con el modo AlwaysBypass y el usuario es externo.

![Diagrama que muestra la escala SIP](media/direct-routing-media-op-13.png)


### <a name="only-for-local-users-mode"></a>Solo para el modo de usuarios locales

Los candidatos de medios locales del SBC de destino solo se ofrecerán si un usuario se encuentra en la misma ubicación que el SBC. En todos los demás casos, los medios fluirán a través de una IP interna o externa del SBC proxy.

Se describen los siguientes escenarios:

- [Las llamadas salientes y el usuario se encuentra en la misma ubicación que el SBC](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [Las llamadas entrantes y el usuario se encuentra en la misma ubicación que el SBC](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [El usuario no está en la misma ubicación que el SBC, pero está en la red corporativa](#user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users)
- [Las llamadas entrantes y el usuario son internos, pero no se encuentra en la misma ubicación que el SBC](#inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users)

En la tabla siguiente se muestra la configuración y la acción del usuario final:

| Ubicación física del usuario |  El usuario realiza o recibe una llamada a/desde un número |  Número de teléfono de usuario | Directiva de enrutamiento de voz en línea |   Modo configurado para SBC |
|:------------|:-------|:-------|:-------|:-------|
| Vietnam | +84 4 3926 3000 |  +84 4 5555 5555 | Prioridad 1: ^ \+ 84(\d {9} )$ -VNsbc.contoso.com <br> Prioridad 2: .* - proxysbc.contoso.com | VNsbc.contoso.com: OnlyForLocalUsers Proxysbc.contoso.com– Omitir siempre |

#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a>Las llamadas salientes y el usuario se encuentra en la misma ubicación que el SBC con solo para usuarios locales

| Modo | Usuario | Sitio | Dirección de llamada |
|:------------|:-------|:-------|:-------|
| OnlyForLocalUsers |   Interno |Igual que SBC   | Saliente |

En el siguiente diagrama se muestra una llamada saliente con el modo OnlyForLocalUsers y el usuario se encuentra en la misma ubicación que el SBC. Este es el mismo flujo que se muestra en las llamadas salientes cuando el [usuario se encuentra en la misma ubicación que el SBC.](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)

![Diagrama que muestra la escala SIP](media/direct-routing-media-op-14.png)


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a>Las llamadas entrantes y el usuario se encuentra en la misma ubicación que el SBC con solo para usuarios locales

| Modo | Usuario | Sitio | Dirección de llamada |
|:------------|:-------|:-------|:-------|
| OnlyForLocalUsers |   Interno | Igual que SBC | Entrada |

En el siguiente diagrama se muestra una llamada entrante con el modo OnlyForLocalUsers y el usuario se encuentra en la misma ubicación que el SBC. Este es el mismo flujo que se muestra en Las llamadas entrantes cuando el [usuario se encuentra en la misma ubicación que el SBC.](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)

![Diagrama que muestra la escala SIP](media/direct-routing-media-op-15.png)


#### <a name="user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users"></a>El usuario no está en la misma ubicación que el SBC, pero está en la red corporativa con Solo para usuarios locales

| Modo | Usuario | Sitio |Dirección de llamada |
|:------------|:-------|:-------|:-------|
| OnlyForLocalUsers  | Interno |   Diferente de SBC | Saliente |

El enrutamiento directo calcula X-MediaPath en función de la ubicación notificada del usuario y el modo configurado en el SBC.


En el siguiente diagrama se muestra una llamada saliente con el modo OnlyForLocalUsers y un usuario interno que no se encuentra en la misma ubicación que el SBC.

![Diagrama que muestra la escala SIP](media/direct-routing-media-op-16.png)


#### <a name="inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users"></a>La llamada entrante y el usuario es interno, pero no se encuentra en la misma ubicación que el SBC con solo para usuarios locales

| Modo |    Usuario |  Sitio |  Dirección de llamada |
|:------------|:-------|:-------|:-------|
| OnlyForLocalUsers | Interno |    Diferente de SBC |    Entrada |

En el siguiente diagrama se muestra una llamada entrante con el modo OnlyForLocalUsers y un usuario interno que no se encuentra en la misma ubicación que el SBC.

![Diagrama que muestra la escala SIP](media/direct-routing-media-op-17.png)









