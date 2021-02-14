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

La configuración de optimización de medios locales se basa en configuraciones de red que son comunes a otras características de voz en la nube, como el enrutamiento Location-Based dinámica y las llamadas de emergencia dinámicas. Para obtener más información sobre regiones de red, sitios de red, subredes de red y direcciones IP de confianza, consulte Configuración de red para las [características de voz en la nube.](cloud-voice-network-settings.md)

Antes de configurar la optimización de medios locales, [vea Optimización de medios locales para el enrutamiento directo.](direct-routing-media-optimization.md)  

Para configurar la optimización de medios locales, son necesarios los pasos siguientes. Puede usar el Centro de administración de Teams o PowerShell. Para obtener más información, [consulte Administrar la topología de red.](manage-your-network-topology.md)

1. Configure el usuario y los sitios SBC (como se describe en este artículo).
2. Configure los SBC para la optimización de medios locales (según la especificación del proveedor de SBC).

El siguiente diagrama muestra la configuración de red usada en los ejemplos a lo largo de este artículo.

![Diagrama que muestra la configuración de red para obtener ejemplos](media/direct-routing-media-op-9.png "Configuración de red para ejemplos")


## <a name="configure-the-user-and-the-sbc-sites"></a>Configurar el usuario y los sitios SBC

Para configurar el usuario y los sitios SBC, necesitará:

1. [Administrar direcciones IP de confianza externas.](#manage-external-trusted-ip-addresses)  

2. [Defina la topología de red configurando](#define-the-network-topology) las regiones de red, los sitios de red y las subredes de red.

3. [Defina la topología de red virtual](#define-the-virtual-network-topology) asignando SBC a los sitios con modos relevantes y valores SBC del proxy.


## <a name="configure-sbcs-for-local-media-optimization-according-to-the-sbc-vendor-specification"></a>Configurar SBC para la optimización de medios locales según la especificación de proveedor de SBC

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
| [Núcleo de SBC de la cinta de opciones](https://support.sonus.net/display/ALLDOC/SBC+8.2+-+Configure+Local+Media+Optimization)  |  SBC 5110         | 8.2  |
|            |  SBC 5210         | 8.2  |
|            |  SBC 5400         | 8.2  |
|            |  SBC 7000         | 8.2  |
|            |  SBC SWe          | 8.2  |
| [Borde de SBC de la cinta de opciones](https://support.sonus.net/display/UXDOC81/Best+Practice+-+Configuring+Microsoft+Teams+Local+Media+Optimization)  |  SBC SWe Lite | 8.1.5 |
|               | SBC 1000 | 8.1.5  |
|               | SBC 2000 | 8.1.5  |
| [TE-SYSTEMS](https://www.anynode.de/local_media_optimization/) |  anynode          | 4.0.1 y posteriores |
| [Oracle](https://www.oracle.com/industries/communications/enterprise-communications/session-border-controller/microsoft.html) | AP 1100 | 8.4.0.0.0 |
|        | AP 3900 | 8.4.0.0.0 |
|        | AP 4600 | 8.4.0.0.0 | 
|        | AP 6300 | 8.4.0.0.0 |
|        | AP 6350 | 8.4.0.0.0 | 
|        | VME     | 8.4.0.0.0 |


## <a name="manage-external-trusted-ip-addresses"></a>Administrar direcciones IP de confianza externas

Las IP de confianza externa son las IP externas a Internet de la red empresarial. Estas IP son las direcciones IP que usan los clientes de Microsoft Teams al conectarse a Microsoft 365. Debe agregar estas IP externas para cada sitio donde tenga usuarios mediante la optimización de medios locales.

Para agregar las direcciones IP públicas de cada sitio, use el cmdlet New-CsTenantTrustedIPAddress público. Puede definir un número ilimitado de direcciones IP de confianza para un inquilino. Si las DIRECCIONES IP externas observadas por Microsoft 365 son direcciones IPv4 e IPv6, debe agregar ambos tipos de direcciones IP. Para IPv4, use la máscara 32. Para IPv6, use la máscara 128. Puede agregar direcciones IP externas individuales y subredes IP externas especificando diferentes MaskBits en el cmdlet.

```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description>
```


Ejemplo de adición de direcciones IP de confianza.

```
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.110 -MaskBits 32 -Description "Vietnam site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.120 -MaskBits 32 -Description "Indonesia site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.130 -MaskBits 32 -Description "Singapore site trusted IP"
```


## <a name="define-the-network-topology"></a>Definir la topología de red

En esta sección se describe cómo definir las regiones de red, los sitios de red y las subredes de red de la topología de red.

Todos los parámetros distinguen mayúsculas de minúsculas, por lo que necesita asegurarse de usar el mismo caso que se usó durante la configuración.  (Por ejemplo, los valores GatewaySiteID "Vietnam" y "vietnam" se tratarán como sitios diferentes).

### <a name="define-network-regions"></a>Definir regiones de red

Para definir regiones de red, use el New-CsTenantNetworkRegion cmdlet. El parámetro RegionID es un nombre lógico que representa la geografía de la región y no tiene dependencias ni restricciones. El parámetro CentralSite <site ID> es opcional.

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

En el ejemplo siguiente se crea una región de red denominada APAC:

```
New-CsTenantNetworkRegion -NetworkRegionID "APAC"  
```

###  <a name="define-network-sites"></a>Definir sitios de red

Para definir sitios de red, use el New-CsTenantNetworkSite cmdlet. Cada sitio de red debe estar asociado a una región de red.

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

En el ejemplo siguiente se crean tres nuevos sitios de red, Vietnam, Indonesia y Singapur, en la región de APAC:

```
New-CsTenantNetworkSite -NetworkSiteID "Vietnam" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Indonesia" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Singapore" -NetworkRegionID "APAC"
```

### <a name="define-network-subnets"></a>Definir subredes de red

Para definir subredes de red y asociarlas a sitios de red, use el New-CsTenantNetworkSubnet cmdlet. Cada subred de red solo puede estar asociada a un sitio. 

```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

En el ejemplo siguiente se definen tres subredes de red y las asocia a los tres sitios de red: Vietnam, Indonesia y Singapur:

```
New-CsTenantNetworkSubnet -SubnetID 192.168.1.0 -MaskBits 24 -NetworkSiteID “Vietnam”
New-CsTenantNetworkSubnet -SubnetID 192.168.2.0 -MaskBits 24 -NetworkSiteID “Indonesia”
New-CsTenantNetworkSubnet -SubnetID 192.168.3.0 -MaskBits 24 -NetworkSiteID “Singapore”
```

## <a name="define-the-virtual-network-topology"></a>Definir la topología de red virtual 

En primer lugar, el administrador de inquilinos crea una nueva configuración de SBC para cada SBC relevante mediante el New-CsOnlinePSTNGateway cmdlet.
El administrador de inquilinos define la topología de red virtual especificando los sitios de red para los objetos de puerta de enlace RTC con el Set-CsOnlinePSTNGateway cmdlet:

```
PS C:\> Set-CsOnlinePSTNGateway -Identity <Identity> -GatewaySiteID <site ID> -MediaBypass <true/false> -BypassMode <Always/OnlyForLocalUsers> -ProxySBC  <proxy SBC FQDN or $null>
```

Tenga en cuenta lo siguiente: 
   - Si el cliente tiene un único SBC, el parámetro -ProxySBC debe ser obligatorio $null o un valor FQDN de SBC (SBC central con escenario de troncos centralizados).
   - El parámetro -MediaBypass debe configurarse en $true poder admitir la optimización de medios locales.
   - Si SBC no tiene establecido el parámetro -BypassMode, los encabezados X-MS no se enviarán. 
   - Todos los parámetros distinguen mayúsculas de minúsculas, por lo que necesita asegurarse de usar el mismo caso que se usó durante la configuración.  (Por ejemplo, los valores GatewaySiteID "Vietnam" y "vietnam" se tratarán como sitios diferentes).

En el ejemplo siguiente se agregan tres SBCs a los sitios de red vietnam, Indonesia y Singapur, en la región de APAC con el modo Omit siempre:

```
Set-CSOnlinePSTNGateway -Identity “proxysbc.contoso.com” -GatewaySiteID “Singapore” -MediaBypass $true -BypassMode “Always” -ProxySBC $null

Set-CSOnlinePSTNGateway -Identity “VNsbc.contoso.com” -GatewaySiteID “Vietnam” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”

Set-CSOnlinePSTNGateway -Identity “IDsbc.contoso.com” -GatewaySiteID “Indonesia” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”
```

Nota: Para garantizar las operaciones sin interrupciones cuando la optimización de medios locales y el enrutamiento de Location-Based (LBR) se configuran al mismo tiempo, las SBR de bajada deben estar habilitadas para LBR estableciendo el parámetro GatewaySiteLbrEnabled en $true para cada SBC de bajada. (Esta configuración no es obligatoria para el servidor proxy SBC).

Según la información anterior, el enrutamiento directo incluirá tres encabezados SIP de propiedad para invitaciones SIP y re-invitaciones, tal y como se muestra en la tabla siguiente.

Encabezados X-MS introducidos en Enrutamiento directo en invitaciones y Re-Invites si BypassMode está definido:

| Nombre del encabezado | Valores | Comentarios | 
|:------------|:-------|:-------|
| X-MS-UserLocation | interno/externo | Indica si el usuario es interno o externo |
| Sip de invitación de URI de solicitud: +84439263000@VNsbc.contoso.com SIP /2.0 | SBC FQDN | El FQDN que se dirige a la llamada incluso si el SBC no está conectado directamente a Enrutamiento directo |
| X-MS-MediaPath | Ejemplo: proxysbc.contoso.com, VNsbc.contoso.com | Orden de los SBC de destino que se deben usar para la ruta de acceso a medios entre el usuario y la SBC de destino. La SBC final siempre es la última |
| X-MS-UserSite | usersiteID | Cadena definida por el administrador de inquilinos |

## <a name="call-flows"></a>Flujos de llamadas 

A continuación se muestran los flujos de llamada para dos modos:

- [Omitir siempre](#always-bypass-mode)
- [Solo para usuarios locales](#only-for-local-users-mode)

### <a name="always-bypass-mode"></a>Modo Omitir siempre

El modo Omitir siempre es la opción más sencilla de configurar. El administrador de inquilinos puede configurar un único sitio para todos los usuarios y SBC si se puede obtener acceso a todos los SBC desde cualquier sitio.

En los ejemplos se muestra siempre el modo de omisión para los escenarios siguientes:

- [Las llamadas salientes y el usuario están en la misma ubicación que el SBC](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [Las llamadas entrantes y el usuario están en la misma ubicación que el SBC](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [Las llamadas salientes y el usuario son externos](#outbound-calls-and-the-user-is-external-with-always-bypass)
- [Las llamadas entrantes y el usuario son externos](#inbound-calls-and-the-user-is-external-with-always-bypass)

En la tabla siguiente se muestran los FQDN y las direcciones IP que se usan en los ejemplos:

| FQDN | Dirección IP externa SBC | Dirección IP interna de SBC | Subred interna | Ubicación | NAT externa (IP de confianza) |
|:------------|:-------|:-------|:-------|:-------|:-------|
| VNsbc.contoso.com | Ninguna | 192.168.1.5 | 192.168.1.0/24 | Vietnam | 172.16.240.110 |
| IDsbc.contoso.com | Ninguna | 192.168.2.5 | 192.168.2.0/24 | Indonesia | 172.16.240.120 |
| proxysbc.contoso.com | 172.16.240.133 | 192.168.3.5 | 192.168.3.0/24 | Singapur | 172.16.240.130 |



#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a>Las llamadas salientes y el usuario están en la misma ubicación que el SBC con siempre omitir

| Modo |    Usuario |  Ubicación |  Dirección de llamada |
|:------------|:-------|:-------| :-------|
| AlwaysBypass |    Interno |  El mismo sitio que SBC |  Saliente |

La tabla siguiente muestra la configuración y la acción del usuario final:

| Ubicación física del usuario| El usuario realiza o recibe una llamada a/desde un número | Número de teléfono de usuario  | Directiva de enrutamiento de voz en línea | Modo configurado para SBC |
|:------------|:-------|:-------|:-------|:-------|
| Vietnam | +84 4 3926 3000 | +84 4 5555 5555   | Prioridad 1: ^ \+ 84(\d {9} )$ -VNsbc.contoso.com <br> Prioridad 2: .* - proxysbc.contoso.com   | VNsbc.contoso.com– Omitir siempre <br> proxysbc.contoso.com– Omitir siempre


En el siguiente diagrama se muestra la autenticación SIP para una llamada saliente con el modo de omisión siempre y el usuario en la misma ubicación que el SBC.

![Diagrama que muestra las llamadas salientes](media/direct-routing-media-op-10.png "Llamadas salientes")

En la tabla siguiente se muestran los encabezados X-MS enviados por Enrutamiento directo:

| Parámetro | Explicación |
|:------------|:-------|
| Invitar a +8443926300@VNsbc.contoso.com | El FQDN de destino del SBC definido en la directiva de enrutamiento de voz en línea se envía en el URI de solicitud | 
| X-MS-UserLocation: interno | El campo indicaba que el usuario se encuentra dentro de la red corporativa |
| X-MS-MediaPath: VNsbc.contoso.com |   Especifica el SBC que el cliente debe atravesar hasta la SBC de destino. En este caso, como siempre, omitemos y el cliente es interno el nombre de destino enviado como el único nombre en el encabezado. | 
|X-MS-UserSite: Vietnam |   El campo indicado dentro del sitio donde se encuentra el usuario. |


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a>Las llamadas entrantes y el usuario están en la misma ubicación que el SBC con siempre bypass

| Modo |    Usuario |  Ubicación |  Dirección de llamada |
|:------------|:-------|:-------|:-------|:-------|
| AlwaysBypass |    Interno | El mismo sitio que SBC | Entrada |


En una llamada entrante, se desconoce la ubicación del usuario y la SBC debe adivinar dónde se encuentra el usuario. Si el resultado no es correcto, será necesario volver a invitar. En este caso, se supone que el usuario es interno, que los medios pueden fluir directamente y que no es necesario realizar ninguna otra acción (volver a invitar).
El SBC conectado al servicio de enrutamiento directo informa de la ubicación de SBC original proporcionando datos Record-Route y campos de contacto. Basándose en estos campos, enrutamiento directo calcula la ruta multimedia.

Nota: Dado que un usuario puede tener varios puntos de conexión, no es posible admitir el 183. El enrutamiento directo siempre usará 180 llamadas en este caso. 

En el siguiente diagrama se muestra la autenticación SIP para las llamadas entrantes con el modo AlwaysBypass y el usuario está en la misma ubicación que el SBC.

![Diagrama que muestra una visita sip](media/direct-routing-media-op-11.png)


#### <a name="outbound-calls-and-the-user-is-external-with-always-bypass"></a>Las llamadas salientes y el usuario son externos con Siempre omitir

| Modo |    Usuario |  Sitio |  Dirección de llamada
|:------------|:-------|:-------|:-------|
AlwaysBypass |  Externo |  N/D | Saliente |


En el siguiente diagrama se muestra la autenticación SIP para una llamada saliente con el modo AlwaysBypass y el usuario es externo:

![Diagrama que muestra una visita sip](media/direct-routing-media-op-12.png)

En la tabla siguiente se muestran los encabezados X-MS enviados por el servicio de enrutamiento directo:

| Parámetro |   Explicación |
|:------------|:-------|
|Invitar a +8443926300@VNsbc.contoso.com | El FQDN de destino de la SBC definido en la directiva de enrutamiento de voz en línea se envía en el URI de solicitud.|
| X-MS-UserLocation: externo | El campo indicaba que el usuario se encuentra fuera de la red corporativa. |
| X-MS-MediaPath: proxysbc.contoso.com, VNsbc.contoso.com    | Especifica el SBC que el cliente debe atravesar hasta la SBC de destino. En este caso, como siempre, omitemos y el cliente es externo. |

#### <a name="inbound-calls-and-the-user-is-external-with-always-bypass"></a>Las llamadas entrantes y el usuario son externos con Siempre omitir

| Modo | Usuario | Sitio |  Dirección de llamada |
|:------------|:-------|:-------|:-------|
AlwaysBypass |  Externo |  N/D |   Entrada |

Para las llamadas entrantes, el SBC conectado a enrutamiento directo tiene que enviar una nueva invitación (siempre se ofrecen de forma predeterminada los candidatos a medios locales) si la ubicación del usuario es externa.  X-MediaPath se calcula según el Record-Route usuario de SBC especificado.

En el siguiente diagrama se muestra la autenticación SIP para una llamada entrante con el modo AlwaysBypass y el usuario es externo.

![Diagrama que muestra una visita sip](media/direct-routing-media-op-13.png)


### <a name="only-for-local-users-mode"></a>Solo para el modo de usuarios locales

Los candidatos a medios locales del SBC de destino solo se ofrecerán si un usuario está en la misma ubicación que la SBC. En todos los demás casos, los elementos multimedia fluirán a través de una IP interna o externa del SBC del proxy.

Se describen los escenarios siguientes:

- [Las llamadas salientes y el usuario están en la misma ubicación que el SBC](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [Las llamadas entrantes y el usuario están en la misma ubicación que el SBC](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [El usuario no está en la misma ubicación que la SBC, pero está en la red corporativa](#user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users)
- [Las llamadas entrantes y el usuario son internos, pero no están en la misma ubicación que el SBC](#inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users)

La tabla siguiente muestra la configuración y la acción del usuario final:

| Ubicación física del usuario |  El usuario realiza o recibe una llamada a/desde un número |  Número de teléfono de usuario | Directiva de enrutamiento de voz en línea |   Modo configurado para SBC |
|:------------|:-------|:-------|:-------|:-------|
| Vietnam | +84 4 3926 3000 |  +84 4 5555 5555 | Prioridad 1: ^ \+ 84(\d {9} )$ -VNsbc.contoso.com <br> Prioridad 2: .* - proxysbc.contoso.com | VNsbc.contoso.com – OnlyForLocalUsers Proxysbc.contoso.com – Omitir siempre |

#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a>Las llamadas salientes y el usuario están en la misma ubicación que el SBC, solo para los usuarios locales

| Modo | Usuario | Sitio | Dirección de llamada |
|:------------|:-------|:-------|:-------|
| OnlyForLocalUsers |   Interno |Igual que SBC   | Saliente |

El siguiente diagrama muestra una llamada saliente con el modo OnlyForLocalUsers y el usuario está en la misma ubicación que el SBC. Este es el mismo flujo que se muestra en las llamadas [salientes cuando el usuario está en la misma ubicación que el SBC.](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)

![Diagrama que muestra una visita sip](media/direct-routing-media-op-14.png)


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a>Las llamadas entrantes y el usuario se encuentra en la misma ubicación que la SBC, solo para los usuarios locales.

| Modo | Usuario | Sitio | Dirección de llamada |
|:------------|:-------|:-------|:-------|
| OnlyForLocalUsers |   Interno | Igual que SBC | Entrada |

El siguiente diagrama muestra una llamada entrante con el modo OnlyForLocalUsers y el usuario está en la misma ubicación que el SBC. Se trata del mismo flujo que se muestra en las llamadas entrantes cuando el [usuario está en la misma ubicación que el SBC.](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)

![Diagrama que muestra una visita sip](media/direct-routing-media-op-15.png)


#### <a name="user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users"></a>El usuario no está en la misma ubicación que la SBC, sino que está en la red corporativa solo para los usuarios locales.

| Modo | Usuario | Sitio |Dirección de llamada |
|:------------|:-------|:-------|:-------|
| OnlyForLocalUsers  | Interno |   Diferente de SBC | Saliente |

El enrutamiento directo calcula X-MediaPath en función de la ubicación notificada del usuario y el modo configurado en la SBC.


El siguiente diagrama muestra una llamada saliente con el modo OnlyForLocalUsers y un usuario interno que no está en la misma ubicación que el SBC.

![Diagrama que muestra una visita sip](media/direct-routing-media-op-16.png)


#### <a name="inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users"></a>La llamada entrante y el usuario son internos, pero no están en la misma ubicación que el SBC, solo para los usuarios locales.

| Modo |    Usuario |  Sitio |  Dirección de llamada |
|:------------|:-------|:-------|:-------|
| OnlyForLocalUsers | Interno |    Diferente de SBC |    Entrada |

El siguiente diagrama muestra una llamada entrante con el modo OnlyForLocalUsers y un usuario interno que no está en la misma ubicación que el SBC.

![Diagrama que muestra una visita sip](media/direct-routing-media-op-17.png)









