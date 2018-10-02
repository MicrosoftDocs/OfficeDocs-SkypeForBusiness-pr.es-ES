---
title: Configurar para eventos en directo en Microsoft Teams
author: tonysmith
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: tonysmit
search.appverid: MET150
description: Aprenda los pasos para configurar live para los eventos de Microsoft Teams, incluida la preparación de su red, asignación de licencias, habilitar el evento en directo de programación para los usuarios y la configuración de un proveedor de red eCDN.
appliesto:
- Microsoft Teams
ms.openlocfilehash: a6fa8e2bc277bbece7dcbd94fca397e219cdf278
ms.sourcegitcommit: 6447a3aa060452c8d6879524cd6a56aecf33b152
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2018
ms.locfileid: "25354367"
---
# <a name="set-up-for-live-events-in-microsoft-teams"></a>Configurar para eventos en directo en Microsoft Teams
> [!INCLUDE [Preview customer token](../includes/preview-feature.md)]

Cuando se configura para eventos en directo, hay varios pasos que debe seguir:

## <a name="step-1-set-up-your-network-for-live-events-in-microsoft-teams"></a>Paso 1: Configurar la red para eventos en directo en Microsoft Teams
Los eventos de live de inicio rápido requieren para [Preparar la red de su organización para que los equipos de Microsoft](https://docs.microsoft.com/microsoftteams/prepare-network).  

## <a name="step-2-get-and-assign-licenses"></a>Paso 2: obtener licencias y asignarlas
Asegúrese de que tiene asignaciones de licencia correcta para [quién puede crear y programar eventos en directo?](#who-can-create-and-schedule-live-events) y [quién puede ver los eventos en directo?](#who-can-watch-live-events).

## <a name="step-3-enable-live-event-scheduling-for-users"></a>Paso 3: Habilitar el evento en directo de programación para los usuarios
Programación de evento en directo está habilitada de forma predeterminada para los usuarios de los equipos, pero si desea que los usuarios programar eventos externos codificador existen pasos adicionales que debe realizar.

### <a name="for-quick-start-events"></a>Para los eventos de inicio rápido
Use la opción *AllowBroadcastScheduling* en **TeamsMeetingBroadcastPolicy** en los equipos de PowerShell para controlar si el usuario puede crear eventos en directo en los equipos o no. Encontrará más información acerca de cómo administrar TeamsMeetingBroadcastPolicy [aquí](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).

 Si no ha asignado una directiva personalizada asignada a los usuarios, los usuarios obtendrá la directiva *Global* , que tiene la grabación habilitado de forma predeterminada.

Compruebe que el parámetro *AllowBroadcastScheduling* se establece en *True*:
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
A continuación, asigne al usuario a la directiva *Global* , ejecute:
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

#### <a name="user-scenarios"></a>Escenarios de usuario
**Desea que todos los usuarios de su compañía para poder crear eventos en directo.**

Si los usuarios tienen asignados la directiva *global* , ejecute y compruebe que *AllowBroadcastScheduling* * está establecida en *True*:
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
Si los usuarios se les asigna una directiva que no sea la directiva *Global* , ejecute lo siguiente y comprobación *- AllowBroadcastScheduling* se establece en *True*:
```
Get-CsTeamsMeetingBroadcastPolicy -identity {policy name}
```

**Desea que el evento en directo programación se va a 100% deshabilitado en toda la organización.**

Deshabilitar la programación de difusión, ejecute:
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
Asignar a todos los usuarios de la organización a la directiva *Global* , ejecute:
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```

**Desea un gran número de usuarios que puedan crear eventos en directo, pero desea evitar que un conjunto de usuarios desde su creación.**

Asigne la directiva *Global* mediante la **Concesión CsTeamsMeetingBroadcastPolicy** para algunos de los usuarios (que desea que se estén activados) pero primero ejecute lo siguiente y compruebe que *AllowBroadcastScheduling* está establecido en *True*:
```
Get-CsTeamsMeetingBroadcastPolicy -identity Global
```
A continuación, asignar un usuario o a los usuarios a la directiva *Global* , ejecute:
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
Crear y asignar una directiva para deshabilitar la programación mediante el cmdlet **Grant-CsTeamsMeetingBroadcastPolicy** a los demás usuarios (que desee deshabilitado). 

Crear la nueva directiva con él deshabilitado, ejecute:
```
New-CSTeamsMeetingBroadcastPolicy -identity DisabledBroadcastSchedulingpolicy
```
Deshabilitar la programación, ejecute:
```
Set-CsTeamsMeetingBroadcastPolicy -identity DisabledBroadcastSchedulingpolicy -AllowBroadcastScheduling $false
```
A continuación, asignar a usuarios a esta directiva, ejecute:
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName DisabledBroadcastSchedulingpolicy -Verbose
```
**Desea eventos en directo que se deshabilite para un gran número de los usuarios, pero desea permitir que un conjunto de usuarios para crearlos.**

Deshabilitar la programación de difusión, ejecute:
```
Set-CsTeamsMeetingBroadcastPolicy -identity Global -AllowBroadcastScheduling $false
```
A continuación, asignar a los usuarios a la directiva *Global* , ejecute:
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName $null -Verbose
```
Crear y asignar una directiva para habilitar la programación, ejecute:
```
New-CSTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy
```
Habilitar la programación, ejecute:
```
Set-CsTeamsMeetingBroadcastPolicy -identity EnableBroadcastSchedulingpolicy -AllowBroadcastScheduling $true
```
A continuación, asignar a usuarios a esta directiva, ejecute:
```
Grant-CsTeamsMeetingBroadcastPolicy -Identity {user} -PolicyName EnableBroadcastSchedulingpolicy -Verbose
```

### <a name="for-external-encoder-events"></a>Para los eventos de codificador externo
Debe hacer lo siguiente para habilitar el evento en directo de programación para esos usuarios.

#### <a name="step-1-enable-microsoft-stream-for-users-in-your-organization"></a>Paso 1: Habilitar Microsoft Stream para los usuarios de su organización **
Microsoft Stream está disponible como parte de suscripciones a Office 365 optan o como un servicio independiente. Para obtener más información, vea [información general sobre licencias de secuencia](https://docs.microsoft.com/stream/license-overview) .

> ! [NOTA] Microsoft Stream no se incluye en los planes de negocio Essentials o Business Premium.  

Obtenga más información acerca de cómo se pueden [asignar licencias a los usuarios de Office 365](https://support.office.com/article/Assign-licenses-to-users-in-Office-365-for-business-997596B5-4173-4627-B915-36ABAC6786DC) para que los usuarios pueden tener acceso a Microsoft Stream. Asegúrese de que no se bloquea Microsoft Stream para los usuarios tal como se define en [este artículo](https://docs.microsoft.com/stream/disable-user-organization).

#### <a name="step-2-ensure-users-have-live-event-creation-permission-in-microsoft-stream"></a>Paso 2: Asegúrese de los usuarios tienen permiso de creación de evento en directo en la secuencia de Microsoft **
De forma predeterminada, los administradores pueden crear codificador externo eventos en directo. Administrador de Microsoft Stream puede [Permitir que los usuarios adicionales para la creación de evento en directo](https://docs.microsoft.com/stream/live-event-administration#enabling-and-restricting-users-to-creating) en secuencia.  

#### <a name="step-3-ensure-live-event-organizers-have-consented-to-the-company-policy-set-by-stream-admin"></a>Paso 3: Asegúrese de evento en directo han dado su consentimiento los organizadores de la directiva de empresa establecida por secuencia admin **
Si un administrador de Microsoft Stream tiene que [Configurar una directiva de instrucciones de la compañía](https://docs.microsoft.com/stream/company-policy-and-consent) y requiere que los empleados Aceptar esta directiva antes de guardar el contenido, a continuación, los usuarios deben hacerlo antes de crear un evento en directo (con producción codificador externo) en los equipos. Antes de la implantación la característica de eventos en directo en la organización, asegúrese de que los usuarios que vayan a crear estos eventos en directo han dado su consentimiento a la directiva. 

## <a name="step-4-set-up-ecdn-provider-for-live-events-in-microsoft-teams"></a>Paso 4: Configurar proveedor eCDN para eventos en directo en Microsoft Teams 
Reproducción de vídeos de evento en directo usa adaptable velocidad de bits de transmisión por secuencias (ABR) pero es una secuencia de unidifusión, lo que significa que cada visor obtiene su propia secuencia de vídeo de internet. Para eventos en directo o los vídeos que se envía al gran parte de su organización, podría ser una cantidad considerable de ancho de banda de internet que consume los visores. Para las organizaciones que desean reducir este tráfico de internet para eventos en directo, eventos en directo soluciones se integran con de Microsoft de confianza definen de socios de entrega de vídeo que ofrecen software redes (SDNs) o redes de entrega de contenido empresarial (eCDNs). Estos SDN eCDN plataformas permiten a las organizaciones a optimizar el ancho de banda de red sin sacrificar usuario final experiencias de visualización. Nuestros socios pueden ayudar a permitir una distribución de vídeo más escalable y eficaz a través de la red de la empresa.

**Compra & el programa de instalación la solución fuera de Microsoft Teams** Obtenga ayuda de expertos con ajuste de escala entrega vídeo mediante el aprovechamiento de los socios de entrega de vídeo de confianza de Microsoft. Para poder habilitar un proveedor de entrega de vídeo que se usará con los equipos de debe comprar y configurar la solución SDN/eCDN externa e independiente de los equipos.

Las siguientes soluciones SDN/eCDN están integradas en previamente y pueden ser el programa de instalación para usarse con Microsoft Stream.

- **Subárbol de transmisión por secuencias** proporciona una solución sencilla y eficaz para la distribución de vídeo en directo y a petición enterprise. Subárbol es una solución basada en software que no requiere ningún hardware adicional o el ancho de banda y proporciona un modo seguro para habilitar miles de visores de vídeo simultáneos sin afectar a la red. Para clientes que desean para comprender el vídeo de impacto que tiene en su red antes de adquirir una solución de SDN/eCDN, también subárbol de transmisión por secuencias proporciona una solución de análisis basada en explorador para los clientes de Microsoft. [Más información](https://www.hivestreaming.com/partners/integration-partners/microsoft/).
 
- **Kollective** es una basada en la nube, smart interconexión distribución plataforma que aprovecha la infraestructura de red existente para entregar contenido, en muchas formas, (live transmisiones de vídeo, vídeo y a petición, las actualizaciones de software, las revisiones de seguridad, etc.) con mayor rapidez, confiable y con menos ancho de banda. Nuestra plataforma segura es de confianza por las instituciones financieras más grandes del mundo y sin hardware adicional y, a continuación, el programa de instalación y mantenimiento son fáciles. [Más información](http://www.kollective.com).
 
- **Mejorar OmniCache** proporciona la distribución de red de próxima generación y garantiza la entrega perfecta de contenido de vídeo a través de WAN global, ayudar a los productores de evento optimizar el ancho de banda de red y admitir las difusiones de evento correcta en directo y a petición transmisión por secuencias. La compatibilidad para mejorar OmniCache para eventos en directo inicio rápido estará disponible próximamente.  [Más información](http://www.ramp.com). 
 
> [!NOTE] 
> La solución elegida eCDN está sujeto a la seleccionado **términos 3ª del proveedor de servicio y política de privacidad**, donde se regula el uso de la solución del proveedor eCDN. El uso de la solución del proveedor eCDN no estará sujeto a los términos de licencia por volumen de Microsoft o los términos de servicios en línea. Si no acepta los **términos de 3ª del proveedor**, a continuación, no habilite la solución eCDN en los equipos. 

**Configurar una red eCDN para "Inicio rápido" eventos en directo** Puede configurar el proveedor eCDN para eventos en directo en los equipos de uso de PowerShell. 

> [!NOTE] 
> Un proveedor único eCDN puede configurarse para su organización. 

***Subárbol*** Puede usar el cmdlet de PowerShell de [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps) para configurar el proveedor de red eCDN. En primer lugar, obtener la dirección URL licencia API y el identificador de plantilla desde su contacto subárbol, a continuación, ejecute lo siguiente:
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName hive -SdnLicenseId {license ID GUID provided by Hive} -SdnApiTemplateUrl “{API template URL provided by Hive}”
```
***Kollective*** Puede usar el cmdlet de PowerShell de [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps) para configurar el proveedor de red eCDN. En primer lugar obtener el token de API y la dirección URL de plantilla de API de su contacto Kollective, a continuación, ejecute lo siguiente:
```
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName kollective -SdnApiTemplateUrl "{API template URL provided by Kollective}" -SdnApiToken {API token GUID provided by Kollective}
```
**Configurar una red eCDN para eventos en directo "Codificador externo"** 

Si va a crear eventos en directo que usar codificadores externos, necesita [configurar su proveedor eCDN con la secuencia de Microsoft](https://docs.microsoft.com/stream/network-caching) así como. 

## <a name="next-steps"></a>Pasos siguientes
Vaya a [configurar los equipos de eventos en directo](configure-teams-live-events.md).
