---
title: Configurar las llamadas de emergencia dinámicas
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: roykuntz
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
description: Obtenga información sobre cómo configurar los planes de llamadas de Microsoft y Sistema telefónico de llamadas de emergencia dinámicas de enrutamiento directo.
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: a9df546e694fa3dcbdabae8454eeb5a6f7cba6a7
ms.sourcegitcommit: 563567ab140d5802756170c846dade3645d0b9e4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2021
ms.locfileid: "61284728"
---
# <a name="plan-and-configure-dynamic-emergency-calling"></a>Planear y configurar las llamadas de emergencia dinámicas 

Las llamadas de emergencia dinámicas para planes de llamadas de Microsoft, Operador Conectar y Enrutamiento directo ofrecen la capacidad de configurar y enrutar llamadas de emergencia y notificar al personal de seguridad en función de la ubicación actual del cliente Teams cliente.  

En función de la topología de red (elementos de red asociados con direcciones de emergencia) que define el administrador de inquilinos, el cliente de Teams proporciona información de conectividad de red en una solicitud al Servicio de información de ubicación (LIS). Si hay una coincidencia, el LIS devuelve una ubicación al cliente.

El Teams incluye datos de ubicación como parte de una llamada de emergencia. A continuación, el proveedor de servicios de emergencia usa estos datos para determinar el punto de respuesta de seguridad pública (PSAP) adecuado y para enrutar la llamada a ese PSAP, lo que permite al despachador de PSAP obtener la ubicación del autor de la llamada.  

Para las llamadas de emergencia dinámicas, debe ocurrir lo siguiente:

1. El administrador de red configura la configuración de red y el LIS para crear un mapa de ubicación de red o emergencia.

2. Durante el inicio y periódicamente posteriormente, o cuando se cambia una conexión de red, el cliente de Teams envía una solicitud de ubicación que contiene su información de conectividad de red a la configuración de red y al LIS.

   - Si hay una coincidencia del sitio de configuración de red: las directivas de llamadas de emergencia se devuelven al Teams de ese sitio. (Para obtener más información sobre las directivas, vea [Configurar directivas de emergencia).](#configure-emergency-policies)

   - Si hay una coincidencia de LIS: una ubicación de emergencia del elemento de red a la que está conectado el Teams se devuelve al Teams usuario. La coincidencia se realiza en el orden siguiente y se devuelve el primer resultado coincidente:
       - WAP
       - Conmutador/puerto Ethernet
       - Conmutador Ethernet
       - Subred

3. Cuando el Teams realiza una llamada de emergencia, la ubicación de emergencia se transmite a la red RTC.

La capacidad de enrutamiento automático al punto de respuesta de seguridad pública (PSAP) adecuado varía según el país de uso del usuario Teams usuario.

Los planes de llamadas de Microsoft y los Conectar asociados incluyen servicios de enrutamiento de emergencia dinámicos para los usuarios de Estados Unidos y Canadá.

Sin embargo, para enrutamiento directo, se requiere una configuración adicional para el enrutamiento de llamadas de emergencia y, posiblemente, para la conectividad de partners. El administrador debe configurar la conexión a un proveedor del Servicio de enrutamiento de emergencia (ERS) (Estados Unidos y **Canadá)** O configurar el controlador de borde de sesión (SBC) para una aplicación de número de identificación de ubicación de emergencia (ELIN). Para obtener información sobre los proveedores de ERS, vea [Controladores de borde de sesión certificados para enrutamiento directo.](direct-routing-border-controllers.md)

Este artículo contiene las secciones siguientes.

- [Asignar direcciones de emergencia](#assign-emergency-addresses)
- [Configurar la configuración de red](#configure-network-settings)
- [Configurar el servicio de información de ubicación](#configure-location-information-service)
- [Configurar directivas de emergencia](#configure-emergency-policies)
- [Habilitar usuarios y sitios](#enable-users-and-sites)
- [Probar llamadas de emergencia](#test-emergency-calling)

Para obtener más información sobre las llamadas de emergencia, incluida información sobre direcciones de emergencia y enrutamiento de llamadas de emergencia, información específica de países e información sobre la configuración de red y la topología de red, vea lo siguiente:

- [Administrar llamadas de emergencia](what-are-emergency-locations-addresses-and-call-routing.md)
- [Administrar la configuración de red para las características de voz en la nube](cloud-voice-network-settings.md)
- [Administrar la topología de red para las características de voz en la nube](manage-your-network-topology.md)

Para obtener más información sobre qué características están disponibles en las nubes gubernamentales, [vea](#government-support) Soporte técnico del gobierno al final de este artículo.


## <a name="supported-clients"></a>Clientes compatibles

Actualmente, se admiten los siguientes clientes.  Vuelva a comprobarlo a menudo para ver las actualizaciones de esta lista.

- Teams cliente de escritorio para Microsoft Windows
- Teams cliente de escritorio para Apple macOS
- Teams móvil para el cliente iOS de Apple versión 1.0.92.2019121004 y app Store versión 1.0.92 y posterior
- Teams móvil para cliente Android y Google Play Store versión 1416/1.0.0.2019121201 y superior
- Teams de teléfono 1449/1.0.94.2019110802 y versiones 2
- Salas de Teams versión 4.4.25.0 y posterior

> [!NOTE]
> Los teléfonos 3PIP no admiten llamadas de emergencia dinámicas. 

> [!NOTE]
> Las llamadas de emergencia dinámicas, incluidas las notificaciones de escritorio de seguridad, no se admiten en el Teams web. Para evitar que los usuarios utilicen el cliente web Teams llamar a números RTC, puede establecer una directiva de llamadas Teams y desactivar la configuración Permitir llamadas **RTC web.** Para obtener más información, vea [Directivas de llamadas en Teams](teams-calling-policy.md) y [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps). 

> [!NOTE]
> Las ubicaciones basadas en Subred y WiFi son compatibles con todos Teams clientes. <br>
> Ethernet/Switch (LLDP) es compatible con:
> - Windows versión 8.1 y posteriores en este momento.<br>
> - Mac OS, que requiere software [de habilitación lldp.](https://www.microsoft.com/download/details.aspx?id=103383)<br>
> - Teams teléfono con Teams aplicación versión 1449/1.0.94.2021110101 y posteriores.

## <a name="assign-emergency-addresses"></a>Asignar direcciones de emergencia

Puede asignar direcciones de emergencia de la siguiente manera:

- A los usuarios del plan de llamadas.

- Para operador Conectar usuarios en función de las capacidades asignadas al número cuando el operador los carga en el &mdash; inventario de un cliente.

- Para los identificadores de red necesarios para obtener dinámicamente una ubicación. 

Para admitir el enrutamiento automatizado de llamadas de emergencia dentro de los Estados Unidos, debe asegurarse de que las ubicaciones de emergencia asignadas a identificadores de red incluyan los códigos geográficos asociados. (Las direcciones de emergencia sin códigos geográficos no se pueden asignar a los identificadores de red necesarios para ubicaciones dinámicas).

Azure Mapas se usa para servicios basados en ubicación. Al escribir una dirección de emergencia mediante el centro de administración de Microsoft Teams, Teams azure Mapas la dirección:

- Si se encuentra una coincidencia, los códigos geográficos se incluyen automáticamente.

- Si no se encuentra una coincidencia, tendrá la oportunidad de crear manualmente una dirección de emergencia. Para ello, puede usar la característica de colocación de PIN. 

> [!NOTE]
> Las direcciones de emergencia que tienen más de un par de años de antigüedad no se pueden asignar a identificadores de red. Tendrá que volver a crear direcciones anteriores.

Puede agregar y asignar direcciones de emergencia en el Microsoft Teams de administración o mediante PowerShell. Para obtener más información, vea [Agregar una ubicación de emergencia para su organización](add-change-remove-emergency-location-organization.md) y Asignar una ubicación de emergencia para un [usuario.](assign-change-emergency-location-user.md)

## <a name="configure-network-settings"></a>Configurar la configuración de red

La configuración de red se usa para determinar la ubicación de un cliente Teams y para obtener dinámicamente directivas de llamadas de emergencia y una ubicación de emergencia. Puede configurar la configuración de red según cómo su organización quiere que funcionen las llamadas de emergencia.

La configuración de red incluye sitios que incluyen una colección de subredes y que se usan exclusivamente para la asignación dinámica de directivas a los usuarios. Por ejemplo, una directiva de llamadas de emergencia y una directiva de enrutamiento de llamadas de emergencia se pueden asignar al "sitio de Redmond" para que cualquier usuario que desista de casa u otra ubicación de Microsoft esté configurado con números de emergencia, enrutamiento y escritorio de seguridad específicos de Redmond.  

Las direcciones IP de confianza contienen una colección de las direcciones IP externas de Internet de la red empresarial y se usan para determinar si el punto de conexión del usuario está dentro de la red corporativa. Solo se intentará obtener una directiva dinámica o una ubicación si la dirección IP externa del usuario coincide con una dirección IP en la dirección IP de confianza.

Para obtener más información sobre direcciones IP, regiones de red, sitios y direcciones de subred, vea Configuración de red [para características de voz en la nube.](cloud-voice-network-settings.md)

Puede configurar la configuración de red en el Microsoft Teams de administración o mediante PowerShell. Para obtener más información, vea [Administrar la topología de red para las características de voz en la nube.](manage-your-network-topology.md)

Tenga en cuenta que algunos cambios en la configuración de red (como una dirección nueva, identificador de red, entre otros) pueden tardar algún tiempo (hasta un par de horas) en propagarse y estar disponibles para Teams clientes.  

> [!Note]
> Las subredes también se pueden definir en LIS y se pueden asociar a una ubicación de emergencia.  Las subredes LIS deben definirse mediante el id. de red que coincida con el rango IP de subred asignado a los clientes. Por ejemplo, el id. de red de un IP/máscara de cliente de 10.10.10.150/25 es 10.10.10.128. Para obtener más información, vea Comprender los conceptos básicos de [direccionamiento TCP/IP y subred.](/troubleshoot/windows-client/networking/tcpip-addressing-and-subnetting)

> [!Important]
> Las búsquedas de configuración de red no son compatibles con implementaciones de servicio de proxy en la nube que modifican las direcciones IP de origen Teams clientes.



**Para el plan de llamadas y el operador Conectar usuarios:**

- Si se requiere una configuración dinámica de notificación de escritorio de seguridad, debe configurar tanto las direcciones IP de confianza como los sitios de red.

- Si solo se necesitan ubicaciones dinámicas, debe configurar solo las direcciones IP de confianza; no es necesario configurar la configuración de red.

- Si no es necesario, no es necesario configurar la configuración de red. 

**Para usuarios de Enrutamiento directo:**

- Si se requiere la habilitación dinámica de las llamadas de emergencia o la configuración dinámica de la notificación de escritorio de seguridad, debe configurar tanto las direcciones IP de confianza como los sitios de red.

- Si solo se necesitan ubicaciones dinámicas, debe configurar solo las direcciones IP de confianza; no es necesario configurar la configuración del trabajo de trabajo.

- Si no es necesario, no es necesario configurar la configuración de red.


## <a name="configure-location-information-service"></a>Configurar el servicio de información de ubicación

Un cliente Teams obtiene direcciones de emergencia de las ubicaciones asociadas con distintos identificadores de red. 

Para que un cliente obtenga una ubicación, debe rellenar el LIS con identificadores de red (subredes, WAP, modificadores, puertos) y ubicaciones de emergencia. Puede hacerlo en el centro de Microsoft Teams o mediante PowerShell.

### <a name="using-the-microsoft-teams-admin-center"></a>Usar el Centro de administración de Microsoft Teams

1. En el panel de navegación izquierdo, vaya a **Ubicaciones**  >  **Redes & ubicaciones.**
2. Haga clic en la pestaña que representa el identificador de red que desea agregar. Por ejemplo, haga clic **en Subredes,** **Puntos de acceso Wi-Fi,** **Modificadores** o **Puertos.** A continuación, **haga clic en Agregar**.
3. Complete los campos, agregue una ubicación de emergencia y, a continuación, haga clic en **Aplicar.**

### <a name="using-powershell"></a>Con PowerShell

Use los cmdlets siguientes para agregar puertos, modificadores, subredes y WAP al LIS.

- [Get](/powershell/module/skype/get-csonlinelissubnet?view=skype-ps), [Set](/powershell/module/skype/set-csonlinelissubnet?view=skype-ps), [Remove](/powershell/module/skype/remove-csonlinelissubnet?view=skype-ps) -CsOnlineLisSubnet
- [Get](/powershell/module/skype/get-csonlinelisport?view=skype-ps), [Set](/powershell/module/skype/set-csonlinelisport?view=skype-ps), [Remove](/powershell/module/skype/remove-csonlinelisport?view=skype-ps) -CsOnlineLisPort
- [Get](/powershell/module/skype/get-csonlineliswirelessaccesspoint?view=skype-ps), [Set](/powershell/module/skype/set-csonlineliswirelessaccesspoint?view=skype-ps), [Remove](/powershell/module/skype/remove-csonlineliswirelessaccesspoint?view=skype-ps) -CsOnlineLisWirelessAccessPoint
- [Get](/powershell/module/skype/get-csonlinelisswitch?view=skype-ps), [Set](/powershell/module/skype/set-csonlinelisswitch?view=skype-ps), [Remove](/powershell/module/skype/remove-csonlinelisswitch?view=skype-ps) -CsOnlineLisSwitch

>[!Important]
>Si las subredes se usan como parte de sitios de red, deben redefinrse en el Servicio de información de ubicación para representar ubicaciones dinámicas.

## <a name="configure-emergency-policies"></a>Configurar directivas de emergencia

Use las siguientes directivas para configurar las llamadas de emergencia. Puede administrar estas directivas en el centro Microsoft Teams de administración o mediante PowerShell.

- **Directiva de enrutamiento de llamadas de emergencia: solo se aplica al enrutamiento directo.** Esta directiva configura los números de emergencia, las máscaras por número si lo desea y la ruta RTC por número. Puede asignar esta directiva a los usuarios, a los sitios de red o a ambos. Para obtener más información, vea Administrar directivas de enrutamiento de [llamadas de emergencia para enrutamiento directo.](manage-emergency-call-routing-policies.md)  

   (Plan de llamadas y Operador Conectar usuarios se habilitan automáticamente para las llamadas de emergencia con los números de emergencia del país en función de su ubicación de uso Microsoft 365 o Office 365).

- **Directiva de llamadas de emergencia: se aplica a planes de llamadas, Conectar operador y enrutamiento directo.** Esta directiva configura la experiencia de notificación de escritorio de seguridad cuando se realiza una llamada de emergencia. Puede establecer a quién notificar y cómo se les notifica. Por ejemplo, para notificar automáticamente al servicio de seguridad de su organización y que escuche las llamadas de emergencia.  Esta directiva se puede asignar a usuarios, sitios de red o ambos. Para obtener más información, vea [Administrar directivas de llamadas de emergencia en Teams](manage-emergency-calling-policies.md).

## <a name="enable-users-and-sites"></a>Habilitar usuarios y sitios

Puede asignar directivas de enrutamiento de llamadas de emergencia y directivas de llamadas de emergencia a usuarios y sitios. Tenga en cuenta que las directivas de enrutamiento de llamadas de emergencia solo se aplican al enrutamiento directo. (Aunque es posible asignar esta directiva a un plan de llamadas u operador Conectar usuario, la directiva no tendrá ningún efecto).

Puede asignar directivas en el centro Microsoft Teams de administración o mediante PowerShell. Para más información, vea:

- [Administrar directivas de enrutamiento de llamadas de emergencia para enrutamiento directo](manage-emergency-call-routing-policies.md)
- [Administrar directivas de llamadas de emergencia en Teams](manage-emergency-calling-policies.md)

A continuación se muestran ejemplos de PowerShell:

Para habilitar un usuario específico para la notificación de escritorio de seguridad, use el siguiente comando:

```PowerShell
Grant-CsTeamsEmergencyCallingPolicy -Identity user1 -PolicyName SecurityDeskNotification
```

Para asignar una directiva denominada "Directiva de llamadas de emergencia contoso 1" al sitio 1, use el comando siguiente:

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

Para habilitar un usuario de Enrutamiento directo específico para llamadas de emergencia, use el siguiente comando:

```PowerShell
Grant-CsTeamsEmergencyCallRoutingPolicy -Identity user1 -PolicyName UnitedStates
```

Para asignar una directiva denominada "Enrutamiento de llamadas de emergencia de Contoso New York" al sitio 1, use el comando siguiente:

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Contoso New York Emergency Call Routing"
```

Si asignó una directiva de llamadas de emergencia a un sitio de red y a un usuario, y si ese usuario se encuentra en ese sitio de red, la directiva asignada al sitio de red reemplaza la directiva asignada al usuario.

## <a name="test-emergency-calling"></a>Probar llamadas de emergencia

Algunos proveedores de servicios de enrutamiento de emergencia (ERSP) de Estados Unidos ofrecen un bot de prueba de llamadas de emergencia.

- **El plan de** llamadas y el operador Conectar usuarios de Estados Unidos o Canadá pueden usar el número de emergencia de prueba predefinido 933 para validar su configuración de llamadas de emergencia. Este número se enruta a un bot, que, a continuación, vuelve a hacer eco del número de teléfono de la llamada (id. de línea de llamada), la dirección de emergencia o la ubicación, y si la llamada se enruta automáticamente al PSAP o se muestra primero en pantalla.

- **Los clientes de Enrutamiento directo de Estados Unidos deben** coordinarse con su ERSP para un servicio de prueba.

## <a name="government-support"></a>Soporte técnico del gobierno

En la tabla siguiente se muestra el soporte para llamadas de emergencia dinámicas en las nubes gubernamentales:

| Nube | Disponibilidad |
| :------------|:-------|
| World Wide Multi Tenant | Disponible en todos los Teams clientes |
| GCC | Disponible en todos los Teams clientes |
| GCCH | Disponible en Teams escritorio |
| DoD | Pending |

 ## <a name="related-topics"></a>Temas relacionados

- [Administrar llamadas de emergencia](what-are-emergency-locations-addresses-and-call-routing.md)
- [Administrar directivas de llamadas de emergencia](manage-emergency-calling-policies.md)
- [Administrar directivas de enrutamiento de llamadas de emergencia ](manage-emergency-call-routing-policies.md)
- [Agregar, cambiar o quitar una ubicación de emergencia para su organización](add-change-remove-emergency-location-organization.md)
- [Asignar o cambiar una ubicación de emergencia para el usuario](assign-change-emergency-location-user.md)
- [Configuración de red para características de voz en la nube](cloud-voice-network-settings.md)
- [Administrar la topología de red para las características de voz en la nube](manage-your-network-topology.md)
