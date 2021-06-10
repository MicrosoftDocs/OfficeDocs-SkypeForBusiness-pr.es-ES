---
title: Configurar la interoperabilidad de vídeos en la nube para Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: srividhc
f1.keywords:
- NOCSH
description: En este artículo se explica cómo planear y configurar la interoperabilidad de vídeo en la nube para los usuarios de su organización.
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 64d790e775ac0d76de48a71de8d165656f2e6927
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102606"
---
# <a name="set-up-cloud-video-interop-for-microsoft-teams"></a>Configurar la interoperabilidad de vídeos en la nube para Microsoft Teams

Una vez que haya elegido sus partners de interoperabilidad de vídeo en la [nube,](cloud-video-interop.md)tendrá que planear la implementación, configurarse con detalles de aprovisionamiento y clave de inquilino de partners, y dar su consentimiento a la aplicación de interoperabilidad de vídeo de su organización. En el siguiente diagrama se describe el proceso. 

![Implementar CVI en su organización](media/deploying-cvi.png)

## <a name="plan"></a>Plan

Vea [Interoperabilidad de](cloud-video-interop.md) vídeo en la nube para obtener Microsoft Teams información sobre cómo identificar un partner o partners para usarlo en su organización. 

Para planear la habilitación de todo el sitio/ simultánea o basada en el usuario: 

- Elegir un modelo de implementación o modelo hospedado para su uso
- Seleccione el plan de licencia ideal para su organización. 
- Planear la capacidad de las máquinas virtuales es hospedar su infraestructura de vídeo.

## <a name="configure"></a>Configuración 

Para configurar la interoperabilidad de vídeo en la nube, siga estos pasos. 

1. Obtenga información de configuración de los partners que ha elegido (clave de inquilino, appIds...). Puede usar uno o varios partners de interoperabilidad de vídeo en su organización 

2. Asegúrese de que la red está configurada correctamente. Configure el firewall de vídeo basado en estándares para que se admita el recorrido de red perimetral. Por ejemplo: 
    - Cisco VCS-e                  
    - Polycom RPAD

3. Configure salas integradas con exchange y OTD. En la mayoría de los casos, es necesario configurar y configurar relés adicionales en su entorno.


## <a name="provision"></a>Aprovisionar
 
La clave de inquilino será la llamada al servicio de partners. En el ejemplo siguiente, 813878896@t.plcm.vc es la clave de inquilino. 

![Ejemplo de clave de inquilino](media/tenant-key-example.png) 

Tendrá que ejecutar los siguientes cmdlets para aprovisionar la clave de inquilino y también habilitar usuarios seleccionados o toda la organización para crear reuniones con coordenadas de interoperabilidad de vídeo.

 
- **[Get-CsTeamsVideoInteropServicepolicy](/powershell/module/skype/get-csteamsvideointeropservicepolicy):** Microsoft proporciona directivas preconstrucciones para cada uno de nuestros partners compatibles que le permiten designar qué partners usar para la interoperabilidad de vídeo en la nube.

    Este cmdlet le permite identificar las directivas preconstrucciones que puede usar en su organización. Puede asignar esta directiva a uno o varios de sus usuarios aprovechando el cmdlet Grant-CsTeamsVideoInteropServicePolicy usuario.
 
- **[Grant-CsTeamsVideoInteropServicePolicy](/powershell/module/skype/grant-csteamsvideointeropservicepolicy):** El cmdlet Grant-CsTeamsVideoInteropServicePolicy permite asignar una directiva preconstrucciones para su uso en su organización o asignar la directiva a usuarios específicos.
 
- **[New-CsVideoInteropServiceProvider](/powershell/module/skype/new-csvideointeropserviceprovider):** Use la New-CsVideoInteropServiceProvider para especificar información sobre un partner CVI compatible que su organización desea usar.
 
- **[Set-CsVideoInteropServiceProvider](/powershell/module/skype/set-csvideointeropserviceprovider):** Use la Set-CsVideoInteropServiceProvider para actualizar información sobre un partner CVI compatible que usa su organización.
 
- **[Get-CsVideoInteropServiceProvider](/powershell/module/skype/get-csvideointeropserviceprovider):** Obtenga todos los proveedores que se han configurado para su uso dentro de la organización.
 
- **[Remove-CsVideoInteropServiceProvider](/powershell/module/skype/remove-csvideointeropserviceprovider):** Use Remove-CsVideoInteropServiceProvider para quitar toda la información del proveedor sobre un proveedor que su organización ya no usa.  
 
## <a name="consent"></a>Consentimiento

Tendrá que proporcionar permiso para que los dispositivos de videoconferencia (VTC) se unan a las reuniones de su organización a través del servicio de partners. Este vínculo de consentimiento también será proporcionado por tu partner.  
 
Cuando se completen estos pasos, los usuarios que estén habilitados individualmente a través del cmdlet Grant anterior, o todos los usuarios de la organización si el espacio empresarial está habilitado, tendrán coordenadas VTC en todas las reuniones Teams que programe. Cualquier VTC puede unirse a estas reuniones a través de esas coordenadas.


|Nombre|Descripción breve del permiso de aplicación| Descripción|
|--|--|---|
|Calls.JoinGroupCall.All|Unirse a llamadas de grupo y reuniones como una aplicación (vista previa)|Permite a la aplicación unirse a llamadas grupales y reuniones programadas en su organización, sin un usuario que haya iniciado sesión.  La aplicación se unirá con los privilegios de un usuario de directorio a las reuniones de su inquilino.|
|Calls.JoinGroupCallasGuest.All|Unirse a llamadas de grupo y reuniones como usuario invitado (vista previa)|Permite que la aplicación se una de forma anónima a llamadas grupales y reuniones programadas en su organización, sin un usuario que haya iniciado sesión.  La aplicación se unirá como invitado a las reuniones de su inquilino.|
|Calls.AccessMedia.All|Acceder a transmisiones multimedia en una llamada como una aplicación (vista previa)|Permite que la aplicación obtenga acceso directo a las transmisiones multimedia en una llamada, sin un usuario que haya iniciado sesión.|
|OnlineMeetings.Read.All|Leer detalles de la reunión en línea (vista previa)|Permite que la aplicación lea los detalles de la reunión en línea en su organización, sin un usuario que haya iniciado sesión.|

## <a name="schedule"></a>Programar

A continuación, programe Teams reunión con coordenadas de interoperabilidad de vídeo. El usuario habilitado puede programar reuniones de equipos a través de:
- [Teams Complemento de reunión para Outlook](teams-add-in-for-outlook.md)
- Teams cliente de escritorio y móvil


## <a name="join"></a>Join

Puede unirse a Teams reuniones con sus dispositivos VTC de las siguientes maneras:
 
- IVR (respuesta de voz interactiva)
    - Puede llamar al IVR del partner con el tenantkey@domain. 
    - Una vez que esté en el IVR asociado, se le pedirá que escriba el id. de conferencia de VTC, que le conectará a la reunión Teams asociado.
- Marcado directo
    - Puede llamar directamente a la reunión de Teams sin interactuar con el IVR del partner mediante la característica de marcado directo con la cadena completa de tenantkey. VTC ConferenceId@domain.
- Marcado con un solo toque
    - Si tiene un salón de Teams integrado, puede usar las capacidades de marcado de un solo toque que ofrece su partner (sin tener que escribir ninguna cadena de marcado).

Por último, interactúe con Teams usuarios en sus reuniones mediante el uso compartido de audio, vídeo y contenido.