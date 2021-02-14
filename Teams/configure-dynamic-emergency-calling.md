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
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
description: Aprenda a configurar la característica de llamadas dinámicas de emergencia de planes de llamadas de Microsoft y de enrutamiento directo del sistema telefónico.
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 06153eccd343ef8731af38ff4e3b45cea334fcb2
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031016"
---
# <a name="plan-and-configure-dynamic-emergency-calling"></a>Planear y configurar las llamadas de emergencia dinámicas 

Las llamadas de emergencia dinámicas para planes de llamadas de Microsoft y enrutamiento directo del sistema telefónico proporcionan la capacidad de configurar y enrutar llamadas de emergencia y notificar al personal de seguridad según la ubicación actual del cliente de Teams.  

Según la topología de red que defina el administrador de inquilinos, el cliente de Teams proporciona información de conectividad de red en una solicitud al Servicio de información de ubicación (LIS). Si hay una coincidencia, LIS devuelve una ubicación al cliente. Estos datos de ubicación se transmiten al cliente.  

El cliente de Teams incluye los datos de ubicación como parte de una llamada de emergencia. A continuación, el proveedor de servicios de emergencia usa estos datos para determinar el punto de respuesta de seguridad pública (PSAP) adecuado y para enrutar la llamada a dicho PSAP, lo que permite al distribuidor de la PSAP obtener la ubicación del autor de la llamada.  

Para llamadas de emergencia dinámicas, es necesario lo siguiente:

1. El administrador de red configura las opciones de red y lis para crear un mapa de red/ubicación de emergencia.

   Para enrutamiento directo, se requiere configuración adicional para enrutar llamadas de emergencia y posiblemente para la conectividad con asociados. El administrador debe configurar la conexión a un proveedor de  servicios de enrutamiento de emergencia (ERS) (Estados Unidos) O configurar el controlador de borde de sesión (SBC) para una aplicación de número de identificación de ubicación de emergencia (ELIN).

2. Durante el inicio y periódicamente después, o cuando se cambia una conexión de red, el cliente de Teams envía una solicitud de ubicación que contiene su información de conectividad de red a la configuración de red y a LIS.

   - Si hay una coincidencia del sitio de configuración de red: las directivas de llamadas de emergencia se devuelven al cliente de Teams desde ese sitio. (Para obtener más información sobre las directivas, vea [Configurar directivas de emergencia).](#configure-emergency-policies)

   - Si existe una coincidencia de LIS: una ubicación de emergencia desde el elemento de red al que está conectado el cliente de Teams se devuelve al cliente de Teams. La coincidencia se realiza en el orden siguiente y se devuelve el primer resultado coincidente:
       - TIEMPO
       - Conmutador/puerto Ethernet
       - Conmutador Ethernet
       - Subred

3. Cuando el cliente de Teams realiza una llamada de emergencia, la ubicación de emergencia se transmite a la red RTC.

   Para el enrutamiento directo, el administrador debe configurar la SBC para enviar llamadas de emergencia al proveedor de servicios de red o configurar la aplicación ELIN SBC.

Este artículo contiene las secciones siguientes.

- [Configurar direcciones de emergencia](#assign-emergency-addresses)
- [Configurar las opciones de red](#configure-network-settings)
- [Configurar el servicio de información de ubicación](#configure-location-information-service)
- [Configurar directivas de emergencia](#configure-emergency-policies)
- [Habilitar usuarios y sitios](#enable-users-and-sites)
- [Probar llamadas de emergencia](#test-emergency-calling)

La capacidad de enrutamiento automático al punto de respuesta de seguridad pública (PSAP) adecuado varía según el país de uso del usuario de Teams.

Para obtener más información sobre las llamadas de emergencia, incluida la información sobre las direcciones de emergencia y el enrutamiento de llamadas de emergencia, información específica de países e información sobre la configuración de red y la topología de red, vea lo siguiente:

- [Administrar llamadas de emergencia](what-are-emergency-locations-addresses-and-call-routing.md)
- [Administrar la configuración de red para las características de voz en la nube](cloud-voice-network-settings.md)
- [Administrar la topología de red para las características de voz en la nube](manage-your-network-topology.md)

## <a name="supported-clients"></a>Clientes compatibles

Los siguientes clientes son compatibles actualmente.  Vuelve a comprobarlo a menudo para ver las actualizaciones de esta lista.

- Cliente de escritorio de Teams para Microsoft Windows
- Cliente de escritorio de Teams para Apple macOS
- Cliente móvil de Teams para el cliente de iOS de Apple versión 1.0.92.2019121004 y app Store versión 1.0.92 y superior
- Cliente móvil de Teams para cliente Android y Google Play Store versión 1416/1.0.0.2019121201 y superiores
- Versión de teléfono de Teams 1449/1.0.94.2019110802 y versiones superiores
- Salas de Teams versión 4.4.25.0 y posterior

> [!NOTE]
> Las llamadas de emergencia dinámicas incluidas las notificaciones de escritorio de seguridad no se admiten en el cliente web de Teams. Para evitar que los usuarios utilicen el cliente web de Teams para llamar a números RTC, puede establecer una directiva de llamadas de Teams y desactivar la opción Permitir llamadas RTC **web.** Para obtener más información, consulte [Directivas de llamadas en Teams](teams-calling-policy.md) y [Set-CsTeamsCallingPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)

## <a name="assign-emergency-addresses"></a>Asignar direcciones de emergencia

Puede asignar direcciones de emergencia tanto a los usuarios del plan de llamadas como a los identificadores de red necesarios para obtener de forma dinámica una ubicación. (Se admiten subredes y AP WiFi. El conmutador/puerto Ethernet es compatible con Windows 8.1 y versiones posteriores en este momento).

Para admitir el enrutamiento automatizado de llamadas de emergencia dentro de los Estados Unidos, debe asegurarse de que las ubicaciones de emergencia asignadas a identificadores de red incluyen los códigos geográficos asociados. (Las direcciones de emergencia sin códigos geográficos no se pueden asignar a los identificadores de red necesarios para ubicaciones dinámicas).

Azure Maps se usa para servicios basados en la ubicación.  Cuando introduce una dirección de emergencia mediante el Centro de administración de Microsoft Teams, Teams comprueba la dirección de Azure Maps:

- Si se encuentra una coincidencia, los códigos geográficos se incluyen automáticamente.

- Si no se encuentra ninguna coincidencia, tendrá la oportunidad de crear manualmente una dirección de emergencia. Puede usar la característica de colocación de PIN para hacerlo. 

Esto significa que si una ubicación de emergencia existente que se crea para asignar a los usuarios del plan de llamadas está pensada para una ubicación dinámica, se debe volver a crear la misma dirección para incluir los códigos geográficos. Para distinguir entre las dos ubicaciones, debe incluir una descripción diferente. La nueva ubicación de emergencia se puede asignar a los usuarios que tienen la ubicación antigua. Cuando se migra completamente, se puede eliminar la ubicación anterior.

Puede agregar y asignar direcciones de emergencia en el centro de administración de Microsoft Teams o mediante PowerShell. Para obtener más información, [vea Agregar una ubicación de emergencia para su](add-change-remove-emergency-location-organization.md) organización y Asignar una ubicación de emergencia a un [usuario.](assign-change-emergency-location-user.md)

## <a name="configure-network-settings"></a>Configurar las opciones de red

La configuración de red se usa para determinar la ubicación de un cliente de Teams y para obtener dinámicamente directivas de llamadas de emergencia y una ubicación de emergencia. Puede configurar las opciones de red según el modo en que su organización quiere que funcionen las llamadas de emergencia.

La configuración de red incluye sitios que incluyen una colección de subredes y que se usan exclusivamente para la asignación dinámica de directivas a los usuarios. Por ejemplo, una directiva de llamadas de emergencia y una directiva de enrutamiento de llamadas de emergencia se podrían asignar al "sitio de Redmond" para que cualquier usuario que se des recorrido desde casa o desde otra ubicación de Microsoft esté configurado con números de emergencia, enrutamiento y escritorio de seguridad específicos para Redmond.  

>[!Note]
>Las subredes también se pueden definir en LIS y se pueden asociar a una ubicación de emergencia.  

Tenga en cuenta las siguientes definiciones. Para obtener más información, vea Configuración [de red para las características de voz en la nube.](cloud-voice-network-settings.md)

- Las direcciones IP de confianza contienen una colección de las direcciones IP externas a Internet de la red empresarial y se utilizan para determinar si el punto de conexión del usuario se encuentra dentro de la red corporativa. Solo se intentará obtener una directiva dinámica o una ubicación si la dirección IP externa del usuario coincide con una dirección IP de la dirección IP de confianza. Se puede hacer una coincidencia con las direcciones IP IPv4 o IPv6 y depende del formato del paquete IP enviado a la configuración de red.  (Si una dirección IP pública tiene IPv4 e IPv6, debe agregar ambas como direcciones IP de confianza).

- Una región de red incluye una colección de sitios de red. 

- Un sitio de red representa una ubicación donde su organización tiene un valor físico, como una oficina, un conjunto de edificios o un campus. Estos sitios se definen como una colección de subredes IP.

- Una subred de red debe estar asociada a un sitio de red específico. La ubicación de un cliente se determina según la subred de red y el sitio de red asociado.  

Configure las opciones de red en el Centro de administración de Microsoft Teams o mediante PowerShell. Para obtener más información, vea [Administrar la topología de red para las características de voz en la nube.](manage-your-network-topology.md)

Tenga en cuenta que algunos cambios en la configuración de red (como una nueva dirección, identificador de red, entre otros) pueden tardar algún tiempo (hasta un par de horas) en propagarse y estar disponibles para los clientes de Teams.  

**Para usuarios del plan de llamadas:**

- Si se requiere una configuración dinámica de notificación del servicio de seguridad, debe configurar tanto las direcciones IP de confianza como los sitios de red.

- Si solo son necesarias ubicaciones dinámicas, debe configurar solo las direcciones IP de confianza.

- Si no es necesario, no es necesario configurar la configuración de red. 

**Para usuarios de enrutamiento directo:**

- Si es necesaria una habilitación dinámica de las llamadas de emergencia o una configuración dinámica de las notificaciones del servicio de seguridad, debe configurar tanto las direcciones IP de confianza como los sitios de red.

- Si solo son necesarias ubicaciones dinámicas, debe configurar solo las direcciones IP de confianza.

- Si no es necesario, no es necesario configurar la configuración de red.


## <a name="configure-location-information-service"></a>Configurar el servicio de información de ubicación

Un cliente de Teams obtiene direcciones de emergencia de las ubicaciones asociadas con distintos identificadores de red. Se admiten tanto subredes como puntos de acceso inalámbrico (WAP). El conmutador/puerto Ethernet es compatible con Windows 8.1 y versiones posteriores en este momento.

Para que un cliente obtenga una ubicación, debe rellenar el LIS con identificadores de red (subredes, WAP, conmutadores, puertos) y ubicaciones de emergencia. Puede hacerlo en el Centro de administración de Microsoft Teams o mediante PowerShell.

### <a name="using-the-microsoft-teams-admin-center"></a>Usar el Centro de administración de Microsoft Teams

1. En el panel de navegación izquierdo, vaya **a Ubicaciones** redes  >  **& ubicaciones.**
2. Haga clic en la pestaña que representa el identificador de red que desea agregar. Por ejemplo, haga clic **en Subredes,** puntos de **acceso Wi-Fi,** **Conmutadores** o **Puertos.** A continuación, **haga clic en Agregar.**
3. Complete los campos, agregue una ubicación de emergencia y, a continuación, haga clic en **Aplicar.**

### <a name="using-powershell"></a>Con PowerShell

Use los siguientes cmdlets para agregar puertos, modificadores, subredes y WAP a LIS.

- [Get,](https://docs.microsoft.com/powershell/module/skype/get-csonlinelissubnet?view=skype-ps) [Set,](https://docs.microsoft.com/powershell/module/skype/set-csonlinelissubnet?view=skype-ps) [Remove](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelissubnet?view=skype-ps) -CsOnlineLisSubnet
- [Get,](https://docs.microsoft.com/powershell/module/skype/get-csonlinelisport?view=skype-ps) [Set](https://docs.microsoft.com/powershell/module/skype/set-csonlinelisport?view=skype-ps), [Remove](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelisport?view=skype-ps) -CsOnlineLisPort
- [Get,](https://docs.microsoft.com/powershell/module/skype/get-csonlineliswirelessaccesspoint?view=skype-ps) [Set](https://docs.microsoft.com/powershell/module/skype/set-csonlineliswirelessaccesspoint?view=skype-ps), [Remove](https://docs.microsoft.com/powershell/module/skype/remove-csonlineliswirelessaccesspoint?view=skype-ps) -CsOnlineLisWirelessAccessPoint
- [Get,](https://docs.microsoft.com/powershell/module/skype/get-csonlinelisswitch?view=skype-ps) [Set,](https://docs.microsoft.com/powershell/module/skype/set-csonlinelisswitch?view=skype-ps) [Remove](https://docs.microsoft.com/powershell/module/skype/remove-csonlinelisswitch?view=skype-ps) -CsOnlineLisSwitch

>[!Important]
>Si las subredes se usan como parte de sitios de red, se tienen que volver a definir en el Servicio de información de ubicaciones para representar ubicaciones dinámicas.

## <a name="configure-emergency-policies"></a>Configurar directivas de emergencia

Use las siguientes directivas para configurar las llamadas de emergencia. Puede administrar estas directivas en el Centro de administración de Microsoft Teams o mediante PowerShell.

- **Directiva de enrutamiento de llamadas de** emergencia: solo se aplica al enrutamiento directo. Esta directiva configura los números de emergencia, las máscaras por número (si se quiere) y la ruta RTC por número.  Puede asignar esta directiva a los usuarios, a sitios de red o a ambos. (Los clientes de los equipos de planes de llamadas se habilitan automáticamente para las llamadas de emergencia con los números de emergencia del país en función de su ubicación de uso de Microsoft 365 u Office 365).  Para obtener más información, consulte [Administrar directivas de enrutamiento de llamadas de emergencia para enrutamiento directo.](manage-emergency-call-routing-policies.md)

- **Directiva de llamadas de** emergencia: se aplica a planes de llamadas y enrutamiento directo. Esta directiva configura la experiencia de notificaciones del servicio de seguridad cuando se realiza una llamada de emergencia. Puede establecer a quién notificar y cómo se le notifica. Por ejemplo, para notificar automáticamente al servicio de seguridad de su organización y que escuche las llamadas de emergencia.  Esta directiva se puede asignar a usuarios, sitios de red o ambos. Para obtener más información, consulte [Administrar directivas de llamadas de emergencia en Teams.](manage-emergency-calling-policies.md)

## <a name="enable-users-and-sites"></a>Habilitar usuarios y sitios

Puede asignar directivas de enrutamiento de llamadas de emergencia y directivas de llamadas de emergencia a los usuarios y a los sitios. Tenga en cuenta que las directivas de enrutamiento de llamadas de emergencia solo se aplican al enrutamiento directo. (Aunque es posible asignar esta directiva a un usuario del plan de llamadas, la directiva no tendrá ningún efecto).

Asigne directivas en el Centro de administración de Microsoft Teams o mediante PowerShell. Para obtener más información, consulte:

- [Administrar directivas de enrutamiento de llamadas de emergencia para enrutamiento directo](manage-emergency-call-routing-policies.md)
- [Administrar directivas de llamadas de emergencia en Teams](manage-emergency-calling-policies.md)

Estos son algunos ejemplos de PowerShell.

Para habilitar un usuario específico para las notificaciones del servicio de seguridad, use el comando siguiente:

```PowerShell
Grant-CsTeamsEmergencyCallingPolicy -Identity user1 -PolicyName SecurityDeskNotification
```

Para asignar una directiva denominada "Directiva de llamadas de emergencia de Contoso 1" al Sitio 1, use el comando siguiente:

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

Para habilitar un usuario específico de enrutamiento directo para llamadas de emergencia, use el comando siguiente:

```PowerShell
Grant-CsTeamsEmergencyCallRoutingPolicy -Identity user1 -PolicyName UnitedStates
```

Para asignar una directiva denominada "Enrutamiento de llamadas de emergencia de Contoso Nueva York" al Sitio 1, use el siguiente comando:

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Contoso New York Emergency Call Routing"
```

Si asignó una directiva de llamadas de emergencia a un sitio de red y a un usuario, y si ese usuario se encuentra en ese sitio de red, la directiva asignada al sitio de red invalidará la directiva asignada al usuario.

## <a name="test-emergency-calling"></a>Probar llamadas de emergencia

Algunos proveedores de servicios de enrutamiento de emergencia (ERSP) de Estados Unidos ofrecen un bot de prueba de llamadas de emergencia.

- **Los usuarios del plan de llamadas de Estados Unidos pueden** usar el número de emergencia de prueba predefinido 933 para validar su configuración de llamadas de emergencia. Este número se enruta a un bot, que después hace eco del número de teléfono del autor de la llamada (id. de línea de llamada), la dirección de emergencia o la ubicación, y si la llamada se enruta automáticamente al PSAP o se muestra primero en pantalla.

- **Los clientes de enrutamiento directo en Estados Unidos deben** coordinarse con su proveedor de servicios de prueba.

 ## <a name="related-topics"></a>Temas relacionados

- [Administrar llamadas de emergencia](what-are-emergency-locations-addresses-and-call-routing.md)
- [Administrar directivas de llamadas de emergencia](manage-emergency-calling-policies.md)
- [Administrar directivas de enrutamiento de llamadas de emergencia ](manage-emergency-call-routing-policies.md)
- [Agregar, cambiar o quitar una ubicación de emergencia para su organización](add-change-remove-emergency-location-organization.md)
- [Asignar o cambiar una ubicación de emergencia para el usuario](assign-change-emergency-location-user.md)
- [Configuración de red para características de voz en la nube](cloud-voice-network-settings.md)
- [Administrar la topología de red para las características de voz en la nube](manage-your-network-topology.md)
