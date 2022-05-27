---
title: Configurar optimización de medios locales para enrutamiento directo
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
description: Configurar optimización de medios locales para enrutamiento directo
appliesto:
- Microsoft Teams
ms.openlocfilehash: 58cf5f560a22a58cb76ea28389d0dce1e3b3f4fb
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674882"
---
# <a name="configure-local-media-optimization-for-direct-routing"></a>Configurar optimización de medios locales para enrutamiento directo

La configuración de Optimización de medios locales se basa en la configuración de red que es común a otras características de voz en la nube, como el enrutamiento Location-Based y las llamadas de emergencia dinámicas. Para obtener más información sobre regiones de red, sitios de red, subredes de red y direcciones IP de confianza, consulte [Configuración de red para las características de voz](cloud-voice-network-settings.md) en la nube.

Antes de configurar la Optimización de medios locales, consulta [Optimización de medios locales para enrutamiento directo](direct-routing-media-optimization.md).

Para configurar optimización de medios locales, son necesarios los siguientes pasos. Puede usar el Centro de Teams Administración o PowerShell. Para obtener más información, consulte [Administrar la topología de red](manage-your-network-topology.md).

1. Configure el usuario y los sitios de SBC (como se describe en este artículo).
2. Configura los SBC para optimización de medios locales (según la especificación del proveedor de SBC).

El siguiente diagrama muestra la configuración de red usada en los ejemplos de este artículo.

> [!div class="mx-imgBorder"]
> ![Diagrama que muestra la configuración de red por ejemplos.](media/direct-routing-media-op-9.png "Configuración de red para ejemplos")

## <a name="configure-the-user-and-the-sbc-sites"></a>Configurar el usuario y los sitios de SBC

Para configurar el usuario y los sitios de SBC, deberá:

1. [Administrar direcciones IP de confianza externas](#manage-external-trusted-ip-addresses).

2. [Defina la topología de red](#define-the-network-topology) configurando las regiones de red, los sitios de red y las subredes de red.

3. [Defina la topología de red virtual](#define-the-virtual-network-topology) asignando SBC a sitios con modos relevantes y valores de SBC de proxy.

> [!NOTE]
> La optimización de medios locales se basa en que las ubicaciones de cliente se detectan como externas o internas en relación con las redes de la compañía con alcance a una interfaz interna de controlador de borde de sesión de enrutamiento directo (DR).
> En escenarios de VPN de túnel dividido cuando el punto de conexión del cliente se detecta como externo a la red del cliente, Microsoft señalará la ubicación externa al SBC aunque el cliente pueda alcanzar la interfaz interna del SBC de enrutamiento directo del cliente. Los clientes de enrutamiento directo que usen optimización de medios locales pueden experimentar tiempos de configuración de llamadas prolongados y, en algunos casos, ningún audio al recibir llamadas desde LA RTC.
> Para evitar esto, los administradores de VPN deben bloquear el acceso entre usuarios remotos de VPN y la interfaz interna de SBC de enrutamiento directo.

## <a name="configure-sbcs-for-local-media-optimization-according-to-the-sbc-vendor-specification"></a>Configurar SBC para optimización de medios locales según la especificación del proveedor de SBC

En este artículo se describe la configuración de los componentes de Microsoft. Para obtener información sobre la configuración de SBC, consulte la documentación del proveedor de SBC. Para obtener información sobre qué proveedores de SBC admiten optimización de medios locales, consulte [Controladores de borde de sesión certificados para enrutamiento directo](direct-routing-border-controllers.md).

## <a name="manage-external-trusted-ip-addresses"></a>Administrar direcciones IP de confianza externas

Las IP externas de confianza son las IP externas de Internet de la red empresarial. Estas DIRECCIONES IP son las direcciones IP usadas por los clientes de Microsoft Teams cuando se conectan a Microsoft 365. Debe agregar estas direcciones IP externas para cada sitio en el que tenga usuarios usando optimización de medios locales.

Para agregar las direcciones IP públicas de cada sitio, use el cmdlet de New-CsTenantTrustedIPAddress. Puede definir un número ilimitado de direcciones IP de confianza para un inquilino. Si los IP externos vistos por Microsoft 365 son direcciones IPv4 e IPv6, debe agregar ambos tipos de direcciones IP. Para IPv4, use la máscara 32. Para IPv6, use la máscara 128. Puede agregar direcciones IP externas individuales y subredes IP externas especificando diferentes MaskBits en el cmdlet.

```powershell
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description>
```

Ejemplo de adición de direcciones IP de confianza.

```powershell
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.110 -MaskBits 32 -Description "Vietnam site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.120 -MaskBits 32 -Description "Indonesia site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.130 -MaskBits 32 -Description "Singapore site trusted IP"
```

## <a name="define-the-network-topology"></a>Definir la topología de red

En esta sección se describe cómo definir las regiones de red, los sitios de red y las subredes de red para la topología de red.

Todos los parámetros distinguen mayúsculas de minúsculas, por lo que debe asegurarse de usar las mismas mayúsculas y minúsculas que se usaron durante la configuración.  (Por ejemplo, los valores de GatewaySiteID "Vietnam" y "vietnam" se tratarán como sitios diferentes).

### <a name="define-network-regions"></a>Definir regiones de red

Para definir regiones de red, use el cmdlet New-CsTenantNetworkRegion. El parámetro RegionID es un nombre lógico que representa la geografía de la región y no tiene dependencias ni restricciones. El parámetro CentralSite `<site ID>` es opcional.

```powershell
New-CsTenantNetworkRegion -NetworkRegionID <region ID>
```

En el ejemplo siguiente se crea una región de red denominada APAC:

```powershell
New-CsTenantNetworkRegion -NetworkRegionID "APAC"
```

### <a name="define-network-sites"></a>Definir sitios de red

Para definir sitios de red, use el cmdlet New-CsTenantNetworkSite. Cada sitio de red debe estar asociado a una región de red.

```powershell
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

En el ejemplo siguiente se crean tres nuevos sitios de red, Vietnam, Indonesia y Singapur en la región de APAC:

```powershell
New-CsTenantNetworkSite -NetworkSiteID "Vietnam" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Indonesia" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Singapore" -NetworkRegionID "APAC"
```

### <a name="define-network-subnets"></a>Definir subredes de red

Para definir subredes de red y asociarlas a sitios de red, use el cmdlet de New-CsTenantNetworkSubnet. Cada subred de red solo puede asociarse con un sitio.

```powershell
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

En el ejemplo siguiente se definen tres subredes de red y se asocian con los tres sitios de red: Vietnam, Indonesia y Singapur:

```powershell
New-CsTenantNetworkSubnet -SubnetID 192.168.1.0 -MaskBits 24 -NetworkSiteID "Vietnam"
New-CsTenantNetworkSubnet -SubnetID 192.168.2.0 -MaskBits 24 -NetworkSiteID "Indonesia"
New-CsTenantNetworkSubnet -SubnetID 192.168.3.0 -MaskBits 24 -NetworkSiteID "Singapore"
```

## <a name="define-the-virtual-network-topology"></a>Definir la topología de red virtual

En primer lugar, el Administrador de inquilinos crea una nueva configuración de SBC para cada SBC relevante mediante el cmdlet de New-CsOnlinePSTNGateway.
La Administrador de inquilinos define la topología de red virtual especificando los sitios de red para los objetos de puerta de enlace RTC mediante el cmdlet Set-CsOnlinePSTNGateway:

```powershell
PS C:\> Set-CsOnlinePSTNGateway -Identity <Identity> -GatewaySiteID <site ID> -MediaBypass <true/false> -BypassMode <Always/OnlyForLocalUsers> -ProxySBC  <proxy SBC FQDN or $null>
```

Tenga en cuenta lo siguiente:

- Si el cliente tiene un único SBC, el parámetro -ProxySBC debe ser obligatorio $null o valor FQDN SBC (SBC central con escenario de troncos centralizados).
- El parámetro -MediaBypass debe establecerse en $true para admitir optimización de medios locales.
- Si el SBC no tiene el parámetro -BypassMode establecido, no se enviarán encabezados X-MS.
- Todos los parámetros distinguen mayúsculas de minúsculas, por lo que debe asegurarse de usar las mismas mayúsculas y minúsculas que se usaron durante la configuración.  (Por ejemplo, los valores de GatewaySiteID "Vietnam" y "vietnam" se tratarán como sitios diferentes).

En el ejemplo siguiente se agregan tres SBCs a los sitios de red Vietnam, Indonesia y Singapur en la región de APAC con el modo Omitir siempre:

```powershell
Set-CSOnlinePSTNGateway -Identity "proxysbc.contoso.com" -GatewaySiteID "Singapore" -MediaBypass $true -BypassMode "Always" -ProxySBC $null

Set-CSOnlinePSTNGateway -Identity "VNsbc.contoso.com" -GatewaySiteID "Vietnam" -MediaBypass $true -BypassMode "Always" -ProxySBC "proxysbc.contoso.com"

Set-CSOnlinePSTNGateway -Identity "IDsbc.contoso.com" -GatewaySiteID "Indonesia" -MediaBypass $true -BypassMode "Always" -ProxySBC "proxysbc.contoso.com"
```

> [!NOTE]
> Para garantizar operaciones sin interrupciones cuando optimización de medios locales y enrutamiento de Location-Based (LBR) están configurados al mismo tiempo, los SBC de bajada deben habilitarse para LBR estableciendo el parámetro GatewaySiteLbrEnabled en $true para cada SBC aguas abajo. (Esta configuración no es obligatoria para el servidor proxy SBC).

En función de la información anterior, el enrutamiento directo incluirá tres encabezados SIP propietarios para invitaciones SIP y re-invitaciones, tal y como se muestra en la tabla siguiente.

Los encabezados X-MS introducidos en enrutamiento directo en invitaciones y Re-Invites si se define BypassMode:

|Nombre del encabezado|Valores|Comentarios|
|---|---|---|
|X-MS-UserLocation|interno/externo|Indica si el usuario es interno o externo|
|Request-URI INVITE sip: +84439263000@VNsbc.contoso.com SIP /2.0|SBC FQDN|El FQDN que se dirige a la llamada incluso si el SBC no está conectado directamente al enrutamiento directo|
|X-MS-MediaPath|Ejemplo: proxysbc.contoso.com, VNsbc.contoso.com|Orden de los SBC que deben usarse para la ruta de acceso multimedia entre el usuario y el SBC de destino. El SBC final siempre es el último|
|X-MS-UserSite|usersiteID|Cadena definida por Administrador de inquilinos|

## <a name="call-flows"></a>Flujos de llamadas

A continuación se muestran los flujos de llamada para dos modos:

- [Omitir siempre](#always-bypass-mode)
- [Solo para usuarios locales](#only-for-local-users-mode)

### <a name="always-bypass-mode"></a>Modo Desvíe siempre

Siempre el modo de omisión es la opción más sencilla de configurar. El Administrador de inquilinos puede configurar un único sitio para todos los usuarios y SBCs si todos los SBCs son accesibles desde cualquier sitio.

Los ejemplos muestran siempre el modo de omisión para los siguientes escenarios:

- [Las llamadas salientes y el usuario se encuentra en la misma ubicación que el SBC](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [Las llamadas entrantes y el usuario se encuentra en la misma ubicación que el SBC](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [Llamadas salientes y el usuario es externo](#outbound-calls-and-the-user-is-external-with-always-bypass)
- [Las llamadas entrantes y el usuario son externas](#inbound-calls-and-the-user-is-external-with-always-bypass)

La tabla siguiente muestra el FQDN y las direcciones IP usadas en los ejemplos:

|FQDN|Dirección IP externa de SBC|Dirección IP interna de SBC|Subred interna|Ubicación|NAT externo (IP de confianza)|
|---|---|---|---|---|---|
|VNsbc.contoso.com|Ninguna|192.168.1.5|192.168.1.0/24|Vietnam|172.16.240.110|
|IDsbc.contoso.com|Ninguna|192.168.2.5|192.168.2.0/24|Indonesia|172.16.240.120|
|proxysbc.contoso.com|172.16.240.133|192.168.3.5|192.168.3.0/24|Singapur|172.16.240.130|

#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a>Las llamadas salientes y el usuario se encuentra en la misma ubicación que la SBC con siempre omisión

|Modo|Usuario|Ubicación|Dirección de llamada|
|---|---|---|---|
|AlwaysBypass|Interno|El mismo sitio que SBC|Saliente|

La tabla siguiente muestra la configuración y la acción del usuario final:

|Ubicación física del usuario|El usuario realiza o recibe una llamada a/desde un número|Número de teléfono de usuario|Directiva de enrutamiento de voz en línea|Modo configurado para SBC|
|---|---|---|---|---|
|Vietnam|+84 4 3926 3000|+84 4 5555 5555|Prioridad 1: ^\+84(\d{9})$ -VNsbc.contoso.com <br> Prioridad 2: .* - proxysbc.contoso.com|VNsbc.contoso.com: omitir siempre <br> proxysbc.contoso.com: omitir siempre|

El siguiente diagrama muestra la escalera del SIP para una llamada saliente con el modo de omisión siempre, y el usuario en la misma ubicación que el SBC.

> [!div class="mx-imgBorder"]
> ![Diagrama que muestra las llamadas salientes.](media/direct-routing-media-op-10.png "Llamadas salientes")

En la tabla siguiente se muestran los encabezados X-MS enviados por Direct Routing:

|Parámetro|Explicación|
|---|---|
|Invitar +8443926300@VNsbc.contoso.com|El FQDN de destino del SBC tal y como se define en la directiva de enrutamiento de voz en línea se envía en el URI de solicitud|
|X-MS-UserLocation: interno|El campo indica que el usuario se encuentra dentro de la red corporativa|
|X-MS-MediaPath: VNsbc.contoso.com|Especifica qué SBC debe atravesar el cliente hasta el SBC de destino. En este caso, ya que tenemos Siempre omitido y el cliente es interno el nombre de destino enviado como el único nombre en el encabezado.|
|X-MS-UserSite: Vietnam|El campo indicado en el sitio donde se encuentra el usuario.|

#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a>Las llamadas entrantes y el usuario se encuentra en la misma ubicación que la SBC con omisión siempre

|Modo|Usuario|Ubicación|Dirección de llamada|
|---|---|---|---|---|
|AlwaysBypass|Interno|El mismo sitio que SBC|Entrantes|

En una llamada entrante, se desconoce la ubicación del usuario y el SBC debe adivinar dónde se encuentra el usuario. Si la conjetura no es correcta, será necesaria una nueva invitación. En este caso se supone que el usuario es interno, que los elementos multimedia pueden fluir directamente y que no es necesario realizar más acciones (volver a invitar).
El SBC conectado al servicio enrutamiento directo notifica la ubicación de SBC original proporcionando Record-Route y los campos Contacto. En función de estos campos, la ruta de acceso a medios se calcula mediante enrutamiento directo.

Nota: Dado que un usuario puede tener varios puntos de conexión, no es posible la compatibilidad con 183. El Enrutamiento directo siempre usará 180 tonos en este caso.

El siguiente diagrama muestra la escalera SIP para en llamada entrante con el modo AlwaysBypass, y el usuario está en la misma ubicación que el SBC.

> [!div class="mx-imgBorder"]
> ![Diagrama que muestra escalera SIP.](media/direct-routing-media-op-11.png)

#### <a name="outbound-calls-and-the-user-is-external-with-always-bypass"></a>Llamadas salientes y el usuario es externo con Siempre omisión

|Modo|Usuario|Sitio|Dirección de llamada
|---|---|---|---|
|AlwaysBypass|Externo|N/D|Saliente|

El siguiente diagrama muestra la escalera sip para una llamada saliente con el modo AlwaysBypass, y el usuario es externo:

> [!div class="mx-imgBorder"]
> ![El diagrama muestra la escalera del SIP.](media/direct-routing-media-op-12.png)

En la tabla siguiente se muestran los encabezados X-MS enviados por el servicio de enrutamiento directo:

|Parámetro|Explicación|
|---|---|
|Invitar +8443926300@VNsbc.contoso.com|El FQDN de destino del SBC tal y como se define en la directiva de enrutamiento de voz en línea se envía en el URI de solicitud.|
|X-MS-UserLocation: externa|El campo indica que el usuario se encuentra fuera de la red corporativa.|
|X-MS-MediaPath: proxysbc.contoso.com, VNsbc.contoso.com|Especifica qué SBC debe atravesar el cliente hasta el SBC de destino. En este caso, ya que tenemos Siempre omisión y el cliente es externo.|

#### <a name="inbound-calls-and-the-user-is-external-with-always-bypass"></a>Llamadas entrantes y el usuario es externo con Siempre omisión

|Modo|Usuario|Sitio|Dirección de llamada|
|---|---|---|---|
|AlwaysBypass|Externo|N/D|Entrantes|

Para una llamada entrante, el SBC conectado al enrutamiento directo debe enviar una nueva invitación (de forma predeterminada, siempre se ofrecen candidatos de medios locales) si la ubicación del usuario es externa.  X-MediaPath se calcula basándose en Record-Route y en el usuario de SBC especificado.

El siguiente diagrama muestra la escalera SIP para una llamada entrante con el modo AlwaysBypass, y el usuario es externo.

> [!div class="mx-imgBorder"]
> ![Diagrama que muestra de nuevo la escalera SIP.](media/direct-routing-media-op-13.png)

### <a name="only-for-local-users-mode"></a>Solo para el modo de usuarios locales

Los candidatos de medios locales del SBC de destino solo se ofrecerán si un usuario está en la misma ubicación que el SBC. En todos los demás casos, los medios fluirán a través de una IP interna o externa del servidor proxy SBC.

Se describen los siguientes escenarios:

- [Las llamadas salientes y el usuario se encuentra en la misma ubicación que el SBC](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [Las llamadas entrantes y el usuario se encuentra en la misma ubicación que el SBC](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [El usuario no está en la misma ubicación que el SBC, pero está en la red corporativa](#user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users)
- [Las llamadas entrantes y el usuario son internas, pero no están en la misma ubicación que el SBC](#inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users)

La tabla siguiente muestra la configuración y la acción del usuario final:

|Ubicación física del usuario|El usuario realiza o recibe una llamada a/desde un número|Número de teléfono de usuario|Directiva de enrutamiento de voz en línea|Modo configurado para SBC|
|---|---|---|---|---|
|Vietnam|+84 4 3926  3000|+84 4 5555 5555|Prioridad 1: ^\+84(\d{9})$ -VNsbc.contoso.com <br> Prioridad 2: .* - proxysbc.contoso.com|VNsbc.contoso.com: OnlyForLocalUsers Proxysbc.contoso.com: omitir siempre|

#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a>Las llamadas salientes y el usuario se encuentra en la misma ubicación que el SBC con solo para los usuarios locales

|Modo|Usuario|Sitio|Dirección de llamada|
|---|---|---|---|
|OnlyForLocalUsers|Interno|Igual que SBC|Saliente|

El siguiente diagrama muestra una llamada saliente con el modo OnlyForLocalUsers y el usuario está en la misma ubicación que el SBC. Este es el mismo flujo mostrado en [las llamadas salientes cuando el usuario está en la misma ubicación que el SBC](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).

> [!div class="mx-imgBorder"]
> ![El diagrama muestra otra vez la escalera del SIP.](media/direct-routing-media-op-14.png)

#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a>Las llamadas entrantes y el usuario se encuentra en la misma ubicación que el SBC con Solo para usuarios locales

|Modo|Usuario|Sitio|Dirección de llamada|
|---|---|---|---|
|OnlyForLocalUsers|Interno|Igual que SBC|Entrantes|

En el siguiente diagrama se muestra una llamada entrante con el modo OnlyForLocalUsers y el usuario está en la misma ubicación que el SBC. Este es el mismo flujo que se muestra en [las llamadas entrantes cuando el usuario está en la misma ubicación que el SBC](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).

> [!div class="mx-imgBorder"]
> ![Otro diagrama que muestra escalera SIP.](media/direct-routing-media-op-15.png)

#### <a name="user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users"></a>El usuario no está en la misma ubicación que el SBC, pero está en la red corporativa con Solo para usuarios locales

|Modo|Usuario|Sitio|Dirección de llamada|
|---|---|---|---|
|OnlyForLocalUsers|Interno|Diferente de SBC|Saliente|

El enrutamiento directo calcula X-MediaPath en función de la ubicación notificada del usuario y del modo configurados en el SBC.

El siguiente diagrama muestra una llamada saliente con el modo OnlyForLocalUsers y un usuario interno que no está en la misma ubicación que el SBC.

> [!div class="mx-imgBorder"]
> ![Otro diagrama muestra la escalera del SIP.](media/direct-routing-media-op-16.png)

#### <a name="inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users"></a>La llamada entrante y el usuario son internos, pero no están en la misma ubicación que el SBC con solo para usuarios locales

|Modo|Usuario|Sitio|Dirección de llamada|
|---|---|---|---|
|OnlyForLocalUsers|Interno|Diferente de SBC|Entrantes|

En el siguiente diagrama se muestra una llamada entrante con el modo OnlyForLocalUsers y un usuario interno que no está en la misma ubicación que el SBC.

> [!div class="mx-imgBorder"]
> ![Otro diagrama que muestra la escalera SIP.](media/direct-routing-media-op-17.png)
