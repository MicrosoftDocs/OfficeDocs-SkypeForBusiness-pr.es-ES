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
- highpri
ms.reviewer: roykuntz
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
description: Aprenda a configurar los planes de llamadas de Microsoft y la característica dinámica de llamadas de emergencia del enrutamiento directo del sistema telefónico.
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1061adf81b8e9ae84ad028a5047636b6fee7a959
ms.sourcegitcommit: 052e4b3982b0b8ee7d4edc47da4d63b35518a757
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/18/2023
ms.locfileid: "69814362"
---
# <a name="plan-and-configure-dynamic-emergency-calling"></a>Planear y configurar las llamadas de emergencia dinámicas 

Las llamadas de emergencia dinámicas para los planes de llamadas de Microsoft, Operador Connect, Teams Phone Mobile y Enrutamiento directo proporcionan la capacidad de configurar y enrutar llamadas de emergencia y notificar al personal de seguridad en función de la ubicación actual del cliente de Teams.  

En función de la topología de red (elementos de red asociados a direcciones de emergencia) que defina el administrador de inquilinos, el cliente de Teams proporciona información de conectividad de red en una solicitud al Servicio de información de ubicación (LIS). Si hay una coincidencia, LIS devuelve una ubicación al cliente.

El cliente de Teams incluye datos de ubicación como parte de una llamada de emergencia. A continuación, el proveedor de servicios de emergencia usa estos datos para determinar el punto de respuesta de seguridad pública (PSAP) adecuado y para redirigir la llamada a ese PSAP, lo que permite al distribuidor de PSAP obtener la ubicación del autor de la llamada.  

Para las llamadas de emergencia dinámicas, debe ocurrir lo siguiente:

1. El administrador de red configura las opciones de red y el LIS para crear una asignación de ubicación de red/emergencia.

2. Durante el inicio y periódicamente después, o cuando se cambia una conexión de red, el cliente de Teams envía una solicitud de ubicación que contiene su información de conectividad de red a la configuración de red y al LIS.

   - Si hay una coincidencia en el sitio de configuración de red: las directivas de llamadas de emergencia se devuelven al cliente de Teams desde ese sitio. (Para obtener más información sobre las directivas, vea [Configurar directivas de emergencia](#configure-emergency-policies)).

   - Si hay una coincidencia de LIS: una ubicación de emergencia del elemento de red al que está conectado el cliente de Teams se devuelve al cliente de Teams. La coincidencia se realiza en el siguiente orden y se devuelve el primer resultado coincidente:
       - WAP
       - Conmutador/puerto Ethernet
       - Conmutador Ethernet
       - Subred

3. Cuando el cliente de Teams realiza una llamada de emergencia, la ubicación de emergencia se transmite a la red RTC.

La capacidad de realizar el enrutamiento automático al punto de respuesta de seguridad pública (PSAP) adecuado varía según el país de uso del usuario de Teams.

Los planes de llamadas de Microsoft, los partners Operator Connect y Teams Phone Mobile incluyen servicios dinámicos de enrutamiento de emergencia para los usuarios de la Estados Unidos y Canadá.

Sin embargo, para el enrutamiento directo, se requiere configuración adicional para enrutar llamadas de emergencia y posiblemente para la conectividad de asociados. El administrador debe asegurarse de que la puerta de enlace RTC que enruta la llamada de emergencia se ha configurado para agregar información de ubicación a la INVITACIÓN saliente (estableciendo el parámetro PidfloSupported en True en el objeto de puerta de enlace RTC en línea. Además, el administrador debe configurar la conexión a un proveedor del Servicio de enrutamiento de emergencia (ERS) (Estados Unidos y Canadá) **O** configurar el Controlador de borde de sesión (SBC) para una aplicación de número de identificación de ubicación de emergencia (ELIN). Para obtener información sobre los proveedores de ERS, consulte [Controladores de borde de sesión certificados para enrutamiento directo](direct-routing-border-controllers.md).

Este artículo contiene las secciones siguientes.

- [Asignar direcciones de emergencia](#assign-emergency-addresses)
- [Configurar las opciones de red](#configure-network-settings)
- [Configurar el servicio de información de ubicación](#configure-location-information-service)
- [Configurar directivas de emergencia](#configure-emergency-policies)
- [Habilitar usuarios y sitios](#enable-users-and-sites)
- [Probar las llamadas de emergencia](#test-emergency-calling)

Para obtener más información sobre las llamadas de emergencia, incluida información sobre direcciones de emergencia y enrutamiento de llamadas de emergencia, información específica de países e información sobre la configuración de red y la topología de red, vea lo siguiente:

- [Administrar las llamadas de emergencia](what-are-emergency-locations-addresses-and-call-routing.md)
- [Administrar la configuración de red para las características de voz en la nube](cloud-voice-network-settings.md)
- [Administrar la topología de red para las características de voz en la nube](manage-your-network-topology.md)

Para obtener más información sobre qué características están disponibles en las nubes gubernamentales, consulte [Soporte técnico](#government-support) gubernamental al final de este artículo.


## <a name="supported-clients"></a>Clientes compatibles

Actualmente se admiten los siguientes clientes.  Vuelve a comprobarlo con frecuencia para ver las actualizaciones de esta lista.

- Cliente de escritorio de Teams para Microsoft Windows
- Cliente de escritorio de Teams para Apple macOS
- Cliente móvil de Teams para el cliente iOS de Apple, versión 1.0.92.2019121004 y App Store versión 1.0.92 y posteriores
- Cliente móvil de Teams para cliente Android y Google Play Store versión 1416/1.0.0.2019121201 y superiores
- Versión de teléfono de Teams 1449/1.0.94.2019110802 y superior
- Salas de Teams versión 4.4.25.0 y posteriores

> [!NOTE]
> Las ubicaciones basadas en Wi-Fi y subred son compatibles con todos los clientes de Teams compatibles. <br><br>
> Ethernet/Switch (LLDP) se admite en:
> - Versiones de Windows 10.0 y posteriores en este momento.<br>
> - Mac OS, que requiere [software de habilitación LLDP](https://www.microsoft.com/download/details.aspx?id=103383).<br>
> - Teléfono de Teams con la versión 1449/1.0.94.2021110101 y posteriores de la aplicación Teams.

> [!NOTE]
> Las llamadas dinámicas de emergencia, incluida la notificación de escritorio de seguridad, no se admiten en el cliente web de Teams. Para evitar que los usuarios usen el cliente web de Teams para llamar a números RTC, puede establecer una directiva de llamadas de Teams y desactivar la configuración **Permitir llamadas RTC web** . Para obtener más información, consulte [Directivas de llamada en Teams](teams-calling-policy.md) y [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps). 

> [!NOTE]
> Los teléfonos 3PIP no admiten llamadas de emergencia dinámicas. 



## <a name="assign-emergency-addresses"></a>Asignar direcciones de emergencia

Puede asignar las direcciones de emergencia de la siguiente manera:

- A usuarios del plan de llamadas.

- To Operator Connect and Teams Phone Mobile userspending&mdash;on the capabilities assigned to the number when the carrier uploads them into a customer's inventory.

- A los identificadores de red necesarios para obtener dinámicamente una ubicación. 

Para admitir el enrutamiento automatizado de llamadas de emergencia dentro de la Estados Unidos, debe asegurarse de que las ubicaciones de emergencia asignadas a los identificadores de red incluyan los códigos geográficos asociados. (Las direcciones de emergencia sin códigos geográficos no se pueden asignar a los identificadores de red necesarios para ubicaciones dinámicas).

Azure Maps se usa para servicios basados en la ubicación. Cuando escribe una dirección de emergencia mediante el Centro de administración de Microsoft Teams, Teams comprueba Azure Maps la dirección:

- Si se encuentra una coincidencia, los códigos geográficos se incluyen automáticamente.

- Si no se encuentra una coincidencia, tendrá la oportunidad de crear manualmente una dirección de emergencia. Para ello, puedes usar la característica de colocación de PIN. 

> [!NOTE]
> Las direcciones de emergencia con más de un par de años de antigüedad no se pueden asignar a identificadores de red. Tendrá que volver a crear direcciones antiguas.

Puede agregar y asignar direcciones de emergencia en el Centro de administración de Microsoft Teams o con PowerShell. Para obtener más información, vea [Agregar una ubicación de emergencia para su organización](add-change-remove-emergency-location-organization.md) y [Asignar una ubicación de emergencia a un usuario](assign-change-emergency-location-user.md).

## <a name="configure-network-settings"></a>Configurar las opciones de red

La configuración de red se usa para determinar la ubicación de un cliente de Teams y para obtener dinámicamente directivas de llamadas de emergencia y una ubicación de emergencia. Puede configurar las opciones de red según cómo su organización quiera que funcionen las llamadas de emergencia.

La configuración de red incluye sitios que incluyen una colección de subredes y que se usan exclusivamente para asignar directivas dinámicas a los usuarios. Por ejemplo, una directiva de llamadas de emergencia y una directiva de enrutamiento de llamadas de emergencia se pueden asignar al "sitio de Redmond" para que cualquier usuario que se desplaza desde casa u otra ubicación de Microsoft esté configurado con números de emergencia, enrutamiento y departamento de seguridad específicos de Redmond.  

Las direcciones IP de confianza contienen una colección de direcciones IP externas de Internet de la red empresarial y se usan para determinar si el punto de conexión del usuario se encuentra dentro de la red corporativa. Solo se intentará obtener una directiva dinámica o una ubicación si la dirección IP externa del usuario coincide con una dirección IP de la dirección IP de confianza.

Para obtener más información sobre direcciones IP, regiones de red, sitios y direcciones de subred, consulte [Configuración de red para características de voz](cloud-voice-network-settings.md) en la nube.

Puede configurar las opciones de red en el Centro de administración de Microsoft Teams o mediante PowerShell. Para obtener más información, consulte [Administrar la topología de red para las características de voz en la nube](manage-your-network-topology.md).

Tenga en cuenta que algunos cambios en la configuración de red (como una nueva dirección, identificador de red, etc.) pueden tardar algún tiempo (hasta un par de horas) en propagarse y estar disponibles para los clientes de Teams.  

> [!Note]
> Las subredes también se pueden definir en LIS y se pueden asociar a una ubicación de emergencia.  Las subredes LIS deben definirse mediante el Id. de red que coincida con el intervalo IP de subred asignado a los clientes. Por ejemplo, el id. de red para una máscara o IP de cliente de 10.10.10.150/25 es 10.10.10.128. Para obtener más información, consulte [Comprender los conceptos básicos de direcciones TCP/IP y subredes](/troubleshoot/windows-client/networking/tcpip-addressing-and-subnetting).

> [!Important]
> Las búsquedas de configuración de configuración de red no son compatibles con las implementaciones de servicios de proxy en la nube que modifican las direcciones IP de origen de los clientes de Teams.



**Para los usuarios de Plan de llamadas, Operador Conectar y Teléfono móvil de Teams:**

- Si se requiere una configuración dinámica de notificación del departamento de seguridad, debe configurar tanto las direcciones IP de confianza como los sitios de red.

- Si solo se requieren ubicaciones dinámicas, debe configurar solo las direcciones IP de confianza; no es necesario configurar las opciones de red.

- Si no es necesario, no es necesario configurar la red. 

**Para usuarios de enrutamiento directo:**

- Si es necesario habilitar dinámicamente las llamadas de emergencia o configurar dinámicamente las notificaciones de escritorio de seguridad, debe configurar tanto las direcciones IP de confianza como los sitios de red.

- Si solo se requieren ubicaciones dinámicas, debe configurar solo las direcciones IP de confianza; no es necesario configurar las opciones de red.

- Si no es necesario, no es necesario configurar la red.


## <a name="configure-location-information-service"></a>Configurar el servicio de información de ubicación

Un cliente de Teams obtiene direcciones de emergencia de las ubicaciones asociadas con identificadores de red diferentes. 

Para que un cliente obtenga una ubicación, debe rellenar el LIS con identificadores de red (subredes, WAP, conmutadores, puertos) y ubicaciones de emergencia. Puede hacerlo en el Centro de administración de Microsoft Teams o mediante PowerShell.

### <a name="using-the-microsoft-teams-admin-center"></a>Usar el Centro de administración de Microsoft Teams

1. En el panel de navegación izquierdo, vaya a **Ubicaciones** > **de redes & ubicaciones**.
2. Haga clic en la pestaña que representa el identificador de red que desea agregar. Por ejemplo, haga clic en **Subredes**, **Puntos de acceso Wi-Fi**, **Conmutadores** o **Puertos**. A continuación, haga clic en **Agregar**.
3. Complete los campos, agregue una ubicación de emergencia y, a continuación, haga clic en **Aplicar**.

### <a name="using-powershell"></a>Con PowerShell

Use los siguientes cmdlets para agregar puertos, modificadores, subredes y WAP al LIS.

- [Obtener](/powershell/module/skype/get-csonlinelissubnet?view=skype-ps), [establecer](/powershell/module/skype/set-csonlinelissubnet?view=skype-ps) y [quitar](/powershell/module/skype/remove-csonlinelissubnet?view=skype-ps) -CsOnlineLisSubnet
- [Obtener](/powershell/module/skype/get-csonlinelisport?view=skype-ps), [establecer](/powershell/module/skype/set-csonlinelisport?view=skype-ps) y [quitar](/powershell/module/skype/remove-csonlinelisport?view=skype-ps) -CsOnlineLisPort
- [Obtener](/powershell/module/skype/get-csonlineliswirelessaccesspoint?view=skype-ps), [establecer](/powershell/module/skype/set-csonlineliswirelessaccesspoint?view=skype-ps) y [quitar](/powershell/module/skype/remove-csonlineliswirelessaccesspoint?view=skype-ps) -CsOnlineLisWirelessAccessPoint
- [Obtener](/powershell/module/skype/get-csonlinelisswitch?view=skype-ps), [establecer](/powershell/module/skype/set-csonlinelisswitch?view=skype-ps) y [quitar](/powershell/module/skype/remove-csonlinelisswitch?view=skype-ps) -CsOnlineLisSwitch

>[!Important]
>Si las subredes se usan como parte de los sitios de red, deben redefinirse en el servicio de información de ubicación para representar ubicaciones dinámicas.

## <a name="configure-emergency-policies"></a>Configurar directivas de emergencia

Use las siguientes directivas para configurar las llamadas de emergencia. Puede administrar estas directivas en el Centro de administración de Microsoft Teams o con PowerShell.

- **Directiva de enrutamiento de llamadas de emergencia: se aplica solo al enrutamiento directo**. Esta directiva configura los números de emergencia, las máscaras por número si lo desea y la ruta RTC por número. Puede asignar esta directiva a los usuarios, a sitios de red o a ambos. Para obtener más información, consulte [Administrar directivas de enrutamiento de llamadas de emergencia para enrutamiento directo](manage-emergency-call-routing-policies.md).  

   (Los usuarios de Plan de llamadas, Operador Connect y Teléfono móvil de Teams están habilitados automáticamente para las llamadas de emergencia con los números de emergencia del país en función de su ubicación de uso de Microsoft 365 o Office 365).

- **Directiva de llamadas de emergencia: se aplica a los planes de llamadas, a la conexión de operadores, a Teams Phone Mobile y al enrutamiento directo.** Esta directiva configura la experiencia de notificación del departamento de seguridad cuando se realiza una llamada de emergencia. Puede establecer a quién notificar y cómo se le notifica. Por ejemplo, para notificar automáticamente al departamento de seguridad de su organización y pedirles que escuchen las llamadas de emergencia.  Esta directiva se puede asignar a usuarios o sitios de red o a ambos. Para obtener más información, consulte [Administrar directivas de llamadas de emergencia en Teams](manage-emergency-calling-policies.md).

## <a name="enable-users-and-sites"></a>Habilitar usuarios y sitios

Puede asignar directivas de enrutamiento de llamadas de emergencia y directivas de llamadas de emergencia a usuarios y sitios. Tenga en cuenta que las directivas de enrutamiento de llamadas de emergencia solo se aplican al enrutamiento directo. (Aunque es posible asignar esta directiva a un plan de llamadas, a un operador conectado o a un usuario de Teams Phone Mobile, la directiva no tendrá ningún efecto).

Asigne directivas en el Centro de administración de Microsoft Teams o con PowerShell. Para más información, vea:

- [Administrar directivas de enrutamiento de llamadas de emergencia para enrutamiento directo](manage-emergency-call-routing-policies.md)
- [Administrar directivas de llamadas de emergencia en Teams](manage-emergency-calling-policies.md)

A continuación se muestran ejemplos de PowerShell:

Para habilitar un usuario específico para la notificación de escritorio de seguridad, use el siguiente comando:

```PowerShell
Grant-CsTeamsEmergencyCallingPolicy -Identity user1 -PolicyName SecurityDeskNotification
```

Para asignar una directiva denominada "Directiva de llamadas de emergencia 1 de Contoso" al sitio 1, use el siguiente comando:

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

Para habilitar un usuario específico de Enrutamiento directo para las llamadas de emergencia, use el siguiente comando:

```PowerShell
Grant-CsTeamsEmergencyCallRoutingPolicy -Identity user1 -PolicyName UnitedStates
```

Para asignar una directiva denominada "Enrutamiento de llamadas de emergencia de Contoso Nueva York" al sitio 1, use el siguiente comando:

```PowerShell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallRoutingPolicy "Contoso New York Emergency Call Routing"
```

Si asignó una directiva de llamadas de emergencia a un sitio de red y a un usuario, y si ese usuario se encuentra en ese sitio de red, la directiva que se asigna al sitio de red reemplaza la directiva asignada al usuario.

## <a name="test-emergency-calling"></a>Probar las llamadas de emergencia

Algunos proveedores de servicios de enrutamiento de emergencia (ERSP) de la Estados Unidos ofrecen un bot de prueba de llamadas de emergencia.

- **Los usuarios de Plan de llamadas, Operator Connect y Teams Phone Mobile de la Estados Unidos o Canadá** pueden usar el número de emergencia de prueba predefinido 933 para validar su configuración de llamadas de emergencia. Este número se redirige a un bot, lo que devuelve el número de teléfono del autor de la llamada (identificador de línea de llamada), la dirección de emergencia o la ubicación, y si la llamada se enrutaría automáticamente al PSAP o se realizaría primero una pantalla.

- **Los clientes de enrutamiento directo de la Estados Unidos** deben coordinarse con su ERSP para obtener un servicio de prueba.

## <a name="government-support"></a>Soporte técnico de la administración pública

En la tabla siguiente se muestra la compatibilidad con las llamadas de emergencia dinámicas en las nubes gubernamentales:

| Nube | Disponibilidad |
| :------------|:-------|
| World Wide Multi Tenant | Disponible en todos los clientes de Teams |
| GCC | Disponible en todos los clientes de Teams |
| GCCH | -Disponible en el escritorio de Teams <br> -Disponible en clientes móviles de Teams <br> -Disponible en los teléfonos de Teams, versión de la aplicación: 1449/1.0.94.2022061702 |
| Dod | -Disponible en el escritorio de Teams <br>-Disponible en clientes móviles de Teams <br>-Pendiente en los teléfonos de Teams |

 ## <a name="related-topics"></a>Temas relacionados

- [Administrar las llamadas de emergencia](what-are-emergency-locations-addresses-and-call-routing.md)
- [Administrar directivas de llamadas de emergencia](manage-emergency-calling-policies.md)
- [Administrar directivas de enrutamiento de llamadas de emergencia ](manage-emergency-call-routing-policies.md)
- [Agregar, cambiar o quitar una ubicación de emergencia para su organización](add-change-remove-emergency-location-organization.md)
- [Asignar o cambiar una ubicación de emergencia para el usuario](assign-change-emergency-location-user.md)
- [Configuración de red para características de voz en la nube](cloud-voice-network-settings.md)
- [Administrar la topología de red para las características de voz en la nube](manage-your-network-topology.md)
