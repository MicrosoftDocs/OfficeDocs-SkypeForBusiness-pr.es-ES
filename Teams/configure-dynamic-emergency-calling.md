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
ms.reviewer: roykuntz
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
description: Aprenda a configurar el enrutamiento directo de las llamadas de Microsoft y el sistema telefónico de la característica de llamadas de emergencia dinámicas.
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 772b439c7d0590cdc917c3e94780761de2da8915
ms.sourcegitcommit: 5c232ab2dfe4374ac69701241e55b05b8de8eb3e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2020
ms.locfileid: "48269654"
---
# <a name="plan-and-configure-dynamic-emergency-calling"></a>Planear y configurar las llamadas de emergencia dinámicas 

Las llamadas de emergencia dinámicas para los planes de llamadas de Microsoft y el enrutamiento directo del sistema telefónico proporcionan la capacidad de configurar y enrutar llamadas de emergencia y de notificar al personal de seguridad en función de la ubicación actual del cliente de Teams.  

En función de la topología de red que defina el administrador de inquilinos, el cliente de Teams proporciona información de conectividad de red en una solicitud al servicio de información de ubicación (LIS). Si hay una coincidencia, el LIS devuelve una ubicación al cliente. Los datos de esta ubicación se transmiten de vuelta al cliente.  

El cliente de Teams incluye datos de ubicación como parte de una llamada de emergencia. A continuación, el proveedor de servicios de emergencia utiliza estos datos para determinar el punto de respuesta de seguridad pública correspondiente (PSAP) y para enrutar la llamada a ese PSAP, lo que permite al distribuidor de PSAP obtener la ubicación del autor de la llamada.  

Para las llamadas de emergencia dinámicas, se debe hacer lo siguiente:

1. El administrador de la red configura la configuración de la red y el LIS para crear un mapa de ubicación de red/emergencia.

   Para el enrutamiento directo, se necesita una configuración adicional para el enrutamiento de llamadas de emergencia y posiblemente para conectividad de socios. El administrador debe configurar la conexión a un proveedor de servicio de enrutamiento de emergencia (Estados Unidos) **o** configurar el controlador de borde de sesión (SBC) para una aplicación de número de identificación de ubicación de ERS (Elin).

2. Durante el inicio y después periódicamente, o cuando se cambia una conexión de red, el cliente de Teams envía una solicitud de ubicación que contiene la información de conectividad de red a la configuración de red y al LIS.

   - Si hay una coincidencia de sitio de configuración de red: las directivas de llamadas de emergencia se devuelven al cliente de equipos de ese sitio. Para obtener más información acerca de las directivas, consulte [configurar directivas de emergencia](#configure-emergency-policies).

   - Si hay una coincidencia de LIS: una ubicación de emergencia del elemento de red al que está conectado el cliente de Teams se devuelve al cliente de Teams. La coincidencia se realiza en el orden siguiente y se devuelve el primer resultado coincidente:
       - WAP
       - Conmutador/puerto Ethernet
       - Conmutador Ethernet
       - Subred

3. Cuando el cliente de Teams realiza una llamada de emergencia, la ubicación de emergencia se transmite a la red PSTN.

   Para el enrutamiento directo, el administrador debe configurar el SBC para que envíe llamadas de emergencia al proveedor de ERS o configurar la aplicación de ELIN de SBC.

Este artículo contiene las secciones siguientes.

- [Configurar direcciones de emergencia](#assign-emergency-addresses)
- [Configurar las opciones de red](#configure-network-settings)
- [Configurar servicio de información de ubicación](#configure-location-information-service)
- [Configurar directivas de emergencia](#configure-emergency-policies)
- [Habilitar usuarios y sitios](#enable-users-and-sites)
- [Probar las llamadas de emergencia](#test-emergency-calling)

La capacidad de llevar a cabo el enrutamiento automático para el correspondiente punto de respuesta de seguridad pública (PSAP) varía según el país de uso del usuario de los equipos.

Para obtener más información sobre las llamadas de emergencia, incluida información sobre las direcciones de emergencia y el enrutamiento de llamadas de emergencia, información específica de países e información sobre la configuración de red y la topología de red, consulte lo siguiente:

- [Administrar las llamadas de emergencia](what-are-emergency-locations-addresses-and-call-routing.md)
- [Administrar la configuración de red para características de voz en la nube](cloud-voice-network-settings.md)
- [Administrar la topología de red para las características de voz en la nube](manage-your-network-topology.md)

## <a name="supported-clients"></a>Clientes compatibles

Actualmente se admiten los siguientes clientes.  Vuelva a consultar a menudo para ver las actualizaciones de esta lista.

- Cliente de escritorio de Teams para Microsoft Windows
- Cliente de escritorio de Teams para Apple macOS
- Teams Mobile Client para Apple iOS Client versión 1.0.92.2019121004 y App Store versión 1.0.92 y posteriores
- Teams Mobile Client para Android y Google Play Store versión 1416/1.0.0.2019121201 y superior
- Teams Phone versión 1449/1.0.94.2019110802 y posteriores
- Salas de equipos versión 4.4.25.0 y posteriores

> [!NOTE]
> Las llamadas de emergencia dinámicas, incluidas las notificaciones de seguridad, no se admiten en el cliente web de Teams. Para evitar que los usuarios usen el cliente web de Teams para llamar a números RTC, puede establecer una directiva de llamadas de equipo y desactivar la configuración de **permitir la llamada RTC en Internet** . Para obtener más información, vea [llamadas a directivas en Teams](teams-calling-policy.md) y [set-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps).

## <a name="assign-emergency-addresses"></a>Asignar direcciones de emergencia

Puede asignar direcciones de emergencia tanto a los usuarios del plan de llamadas como a los identificadores de red necesarios para obtener dinámicamente una ubicación. (Se admite la subred y el punto de conexión WiFi. El conmutador o puerto Ethernet es compatible con Windows 8,1 y versiones posteriores en este momento).

Para admitir el enrutamiento automatizado de llamadas de emergencia dentro de los Estados Unidos, debe asegurarse de que las ubicaciones de emergencia asignadas a identificadores de red incluyan los códigos geográficas asociados. (Las direcciones de emergencia sin códigos geográficas no se pueden asignar a los identificadores de red necesarios para las ubicaciones dinámicas).

Azure Maps se usa para los servicios basados en la ubicación.  Cuando se especifica una dirección de emergencia con el centro de administración de Microsoft Teams, Teams comprueba las asignaciones de Azure de la dirección:

- Si se encuentra una coincidencia, los códigos geográficas se incluyen automáticamente.

- Si no se encuentra una coincidencia, tendrá la oportunidad de crear manualmente una dirección de emergencia. Puede usar la característica de colocación de PIN para hacerlo. 

Esto significa que si una ubicación de emergencia existente creada para asignarla a los usuarios del plan de llamadas está pensada para una ubicación dinámica, debe volver a crearse la misma dirección para incluir los códigos geográficas. Para distinguir entre las dos ubicaciones, debe incluir una descripción diferente. La nueva ubicación de emergencia se puede asignar a los usuarios que tienen la ubicación anterior. Una vez completada la migración, se puede eliminar la ubicación anterior.

Agregue y asigne direcciones de emergencia en el centro de administración de Microsoft Teams o mediante PowerShell. Para obtener más información, vea [Agregar una ubicación de emergencia para su organización](add-change-remove-emergency-location-organization.md) y [asignar una ubicación de emergencia para un usuario](assign-change-emergency-location-user.md).

## <a name="configure-network-settings"></a>Configurar las opciones de red

La configuración de red se usa para determinar la ubicación de un cliente de equipos y para obtener dinámicamente las directivas de llamadas de emergencia y una ubicación de emergencia. Puede configurar la configuración de red según el modo en que su organización desea que las llamadas de emergencia funcionen.

La configuración de red incluye sitios que incluyen una colección de subredes y que se usan exclusivamente para la asignación de directivas dinámicas a los usuarios. Por ejemplo, se puede asignar una directiva de llamadas de emergencia y una directiva de enrutamiento de llamadas de emergencia al sitio de Redmond para que todos los usuarios que se desplazan desde casa u otra ubicación de Microsoft estén configurados con números de emergencia, enrutamiento y seguridad específicos para Redmond.  

>[!Note]
>Las subredes también pueden definirse en LIS y asociarse a una ubicación de emergencia.  

Tenga en cuenta las siguientes definiciones: Para obtener más información, consulte [configuración de red para características de voz en la nube](cloud-voice-network-settings.md).

- Las direcciones IP de confianza contienen una recopilación de las direcciones IP externas de Internet de la red empresarial y se usan para determinar si el extremo del usuario se encuentra dentro de la red corporativa. Un intento de obtener una ubicación o Directiva dinámica solo se realiza si la dirección IP externa del usuario coincide con una dirección IP de la dirección IP de confianza. Se puede establecer una coincidencia con las direcciones IP IPv4 o IPv6, y depende del formato del paquete IP que se envía a la configuración de red.  (Si una dirección IP pública tiene IPv4 e IPv6, debe agregar ambas como direcciones IP de confianza).

- Una región de red incluye una colección de sitios de red. 

- Un sitio de red representa una ubicación en la que su organización tiene un valor físico, como una oficina, un conjunto de edificios o un campus. Estos sitios se definen como una colección de subredes IP.

- Una subred de red debe estar asociada a un sitio de red específico. La ubicación de un cliente se determina en función de la subred de la red y el sitio de red asociado.  

La configuración de red se establece en el centro de administración de Microsoft Teams o mediante PowerShell. Para obtener más información, vea [administrar la topología de red para características de voz en la nube](manage-your-network-topology.md).

Tenga en cuenta que puede tardar un poco de tiempo (hasta un par de horas) en algunos cambios en la configuración de red (como una nueva dirección, un identificador de red, etc.) para que se propaguen y estén disponibles para los clientes de Teams.  

**Para los usuarios del plan de llamadas:**

- Si se requiere la configuración dinámica de la notificación del escritorio de seguridad, debe configurar tanto las direcciones IP de confianza como los sitios de red.

- Si solo se necesitan ubicaciones dinámicas, debe configurar solo direcciones IP de confianza.

- Si no es necesario, no es necesario establecer la configuración de red. 

**Para usuarios de enrutamiento directo:**

- Si se requiere la habilitación dinámica de las llamadas de emergencia o la configuración dinámica de la notificación del escritorio de seguridad, debe configurar tanto las direcciones IP de confianza como los sitios de red.

- Si solo se necesitan ubicaciones dinámicas, debe configurar solo direcciones IP de confianza.

- Si no es necesario, no es necesario establecer la configuración de red.


## <a name="configure-location-information-service"></a>Configurar servicio de información de ubicación

Un cliente de Teams obtiene las direcciones de emergencia de las ubicaciones asociadas a identificadores de red diferentes. Se admiten las subredes y los puntos de acceso inalámbrico (WAP). El conmutador o puerto Ethernet es compatible con Windows 8,1 y versiones posteriores en este momento.

Para que un cliente obtenga una ubicación, debe rellenar el LIS con identificadores de red (subredes, WAP, conmutadores, puertos) y ubicaciones de emergencia. Puede hacerlo en el centro de administración de Microsoft Teams o mediante PowerShell.

### <a name="using-the-microsoft-teams-admin-center"></a>Usar el centro de administración de Microsoft Teams

1. En el navegación de la izquierda, vaya a **ubicaciones**  >  **redes & ubicaciones**.
2. Haga clic en la pestaña que representa el identificador de red que desea agregar. Por ejemplo, haga clic en **subredes**, **puntos de acceso Wi-Fi**, **conmutadores**o **puertos**. A continuación, haga clic en **Agregar**.
3. Complete los campos, agregue una ubicación de emergencia y, a continuación, haga clic en **aplicar**.

### <a name="using-powershell"></a>Con PowerShell

Use los siguientes cmdlets para agregar puertos, conmutadores, subredes y WAP al LIS.

- [Get](https://docs.microsoft.com/powershell/module/skype/get-csonlinelissubnet?view=skype-ps), [set](https://docs.microsoft.com/powershell/module/skype/set-csonlinelissubnet?view=skype-ps), [Remove](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelissubnet?view=skype-ps) -CsOnlineLisSubnet
- [Get](https://docs.microsoft.com/powershell/module/skype/get-csonlinelisport?view=skype-ps), [set](https://docs.microsoft.com/powershell/module/skype/set-csonlinelisport?view=skype-ps), [Remove](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelisport?view=skype-ps) -CsOnlineLisPort
- [Get](https://docs.microsoft.com/powershell/module/skype/get-csonlineliswirelessaccesspoint?view=skype-ps), [set](https://docs.microsoft.com/powershell/module/skype/set-csonlineliswirelessaccesspoint?view=skype-ps), [Remove](https://docs.microsoft.com/powershell/module/skype/remove-csonlineliswirelessaccesspoint?view=skype-ps) -CsOnlineLisWirelessAccessPoint
- [Get](https://docs.microsoft.com/powershell/module/skype/get-csonlinelisswitch?view=skype-ps), [set](https://docs.microsoft.com/powershell/module/skype/set-csonlinelisswitch?view=skype-ps), [Remove](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelisswitch?view=skype-ps) -CsOnlineLisSwitch

>[!Important]
>Si se usan subredes como parte de sitios de red, deben redefinirse en el servicio de información de ubicación para representar ubicaciones dinámicas.

## <a name="configure-emergency-policies"></a>Configurar directivas de emergencia

Use las siguientes directivas para configurar las llamadas de emergencia. Puede administrar estas directivas en el centro de administración de Microsoft Teams o mediante PowerShell.

- **Política de enrutamiento de llamadas de emergencia** : solo se aplica al enrutamiento directo. Esta directiva configura los números de emergencia, las máscaras por número si así lo desea y la ruta RTC por número.  Puede asignar esta directiva a usuarios, a sitios de red o a ambos. (Planes de llamadas los clientes de Teams se habilitan automáticamente para llamadas de emergencia con los números de emergencia del país en función de su ubicación de uso de Microsoft 365 o de Office 365).  Para obtener más información, consulte [Administrar directivas de enrutamiento de llamadas de emergencia para enrutamiento directo](manage-emergency-call-routing-policies.md).

- **Política de llamadas de emergencia** : se aplica a los planes de llamadas y al enrutamiento directo. Esta directiva configura la experiencia de notificación del centro de seguridad cuando se realiza una llamada de emergencia. Puedes establecer a quién deseas notificar y cómo. Por ejemplo, para notificar automáticamente a la mesa de seguridad de la organización y hacer que escuchen en las llamadas de emergencia.  Esta Directiva se puede asignar a los usuarios o a los sitios de red o a ambos. Para obtener más información, consulte [Administrar directivas de llamadas de emergencia en Teams](manage-emergency-calling-policies.md).

## <a name="enable-users-and-sites"></a>Habilitar usuarios y sitios

Puede asignar políticas de enrutamiento de llamadas de emergencia y políticas de llamadas de emergencia a los usuarios y a los sitios. Ten en cuenta que rigen las políticas de enrutamiento de llamadas de emergencia solo para enrutamiento directo. (Aunque es posible asignar esta directiva a un usuario de un plan de llamadas, la Directiva no tendrá ningún efecto).

Asigne directivas en el centro de administración de Microsoft Teams o mediante PowerShell. Para obtener más información, consulte:

- [Administrar las políticas de enrutamiento de llamadas de emergencia para enrutamiento directo](manage-emergency-call-routing-policies.md)
- [Administrar las directivas de llamadas de emergencia en Teams](manage-emergency-calling-policies.md)

A continuación se muestran algunos ejemplos de PowerShell.

Para habilitar un usuario específico para notificaciones de seguridad, use el siguiente comando:

```PowerShell
Grant-CsTeamsEmergencyCallingPolicy -Identity user1 -PolicyName SecurityDeskNotification
```

Para asignar una directiva denominada "Directiva de llamadas de emergencia de Contoso 1" al sitio 1, use el siguiente comando:

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

Para habilitar un usuario de enrutamiento directo específico para llamadas de emergencia, use el siguiente comando:

```PowerShell
Grant-CsTeamsEmergencyCallRoutingPolicy -Identity user1 -PolicyName UnitedStates
```

Para asignar una directiva denominada "enrutamiento de llamadas de emergencia de Contoso en la Nueva York" al sitio 1, use el siguiente comando:

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Contoso New York Emergency Call Routing"
```

Si ha asignado una directiva de llamadas de emergencia a un sitio de red y a un usuario, y si ese usuario se encuentra en el sitio de red, la directiva asignada al sitio de red reemplaza la directiva asignada al usuario.

## <a name="test-emergency-calling"></a>Probar las llamadas de emergencia

Algunos proveedores de servicios de enrutamiento de emergencia (ERSPs) de los Estados Unidos ofrecen un bot de prueba para llamadas de emergencia.

- **Los usuarios del plan de llamadas de Estados Unidos** pueden usar el número de emergencia de prueba predefinido 933 para validar la configuración de las llamadas de emergencia. Este número se enruta a un bot, que después vuelve a devolverle el número de teléfono de la persona que llama (identificación de la línea de llamada), la dirección o ubicación de emergencia, y si la llamada se redirigirá automáticamente a la PSAP o se ha superpuesto.

- **Los clientes de enrutamiento directo de los Estados Unidos** deben coordinarse con sus ERSP para un servicio de prueba.

 ## <a name="related-topics"></a>Temas relacionados

- [Administrar las llamadas de emergencia](what-are-emergency-locations-addresses-and-call-routing.md)
- [Administrar directivas de llamadas de emergencia](manage-emergency-calling-policies.md)
- [Administrar las directivas de enrutamiento de llamadas de emergencia ](manage-emergency-call-routing-policies.md)
- [Agregar, cambiar o quitar una ubicación de emergencia para su organización](add-change-remove-emergency-location-organization.md)
- [Asignar o cambiar una ubicación de emergencia para el usuario](assign-change-emergency-location-user.md)
- [Configuración de red para características de voz en la nube](cloud-voice-network-settings.md)
- [Administrar la topología de red para las características de voz en la nube](manage-your-network-topology.md)
