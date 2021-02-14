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
ms.openlocfilehash: a1f45967b3e2737f6e2df74c505932ea69afe37f
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "46582637"
---
# <a name="set-up-cloud-video-interop-for-microsoft-teams"></a>Configurar la interoperabilidad de vídeos en la nube para Microsoft Teams

Después de haber elegido los partners de interoperabilidad de vídeo en la [nube,](cloud-video-interop.md)necesitará planear la implementación, configurar los detalles de aprovisionamiento y la clave del inquilino del partner, y dar su consentimiento para la aplicación de interoperabilidad de vídeo en su organización. En el siguiente diagrama se describe el proceso. 

![Implementar CVI en su organización](media/deploying-cvi.png)

## <a name="plan"></a>Plan

Vea [Cloud Video Interoperabilidad para Microsoft Teams](cloud-video-interop.md) para obtener información sobre cómo identificar a un partner o partners para usarlos en su organización. 

Para planear la habilitación del ancho del sitio/basado en usuarios/simultáneos/sitio: 

- Elegir un modelo de implementación/modelo hospedado para su uso
- Seleccione el plan de licencia ideal para su organización. 
- La planificación de la capacidad de las máquinas virtuales es hospedar la infraestructura de vídeo.

## <a name="configure"></a>Configuración 

Para configurar la interoperabilidad de vídeo en la nube, siga estos pasos. 

1. Obtenga información de configuración de los partners que haya elegido (clave de inquilino, appIds...). Puede usar uno o varios partners de interoperabilidad de vídeo en su organización 

2. Asegúrese de que la red está configurada correctamente. Configure su firewall de vídeo basado en estándares para recorrer la red perimetral como soporte técnico. Por ejemplo: 
    - Cisco VCS-e                  
    - Polycom RPAD

3. Configure salas integradas con exchange y OTD. En la mayoría de los casos, tendría que configurar retransmisión adicional en su entorno.


## <a name="provision"></a>Aprovisionar
 
La clave del inquilino será la llamada al servicio del asociado. En el ejemplo siguiente, 813878896@t.plcm.vc clave de inquilino. 

![Ejemplo de clave de espacio empresarial](media/tenant-key-example.png) 

Tendrá que ejecutar los siguientes cmdlets para aprovisionar la clave de inquilino y, además, habilitar a los usuarios seleccionados o a toda la organización para crear reuniones con coordenadas de interoperabilidad de vídeo.

 
- **[Get-CsTeamsVideoInteropServicepolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsvideointeropservicepolicy):** Microsoft proporciona directivas de construcción previa para cada uno de nuestros socios compatibles que le permiten designar qué socios usar para la interoperabilidad de vídeo en la nube.

    Este cmdlet le permite identificar las directivas pre-construir que puede usar en su organización. Puede asignar esta directiva a uno o varios de los usuarios aprovechando el cmdlet Grant-CsTeamsVideoInteropServicePolicy web.
 
- **[Grant-CsTeamsVideoInteropServicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsvideointeropservicepolicy):** El Grant-CsTeamsVideoInteropServicePolicy cmdlet le permite asignar una directiva predefinida para su uso en su organización o asignar la directiva a usuarios específicos.
 
- **[New-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/new-csvideointeropserviceprovider):** Use la New-CsVideoInteropServiceProvider para especificar información sobre un partner de CVI compatible que le gustaría usar en su organización.
 
- **[Set-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/set-csvideointeropserviceprovider):** Use la aplicación Set-CsVideoInteropServiceProvider para actualizar la información sobre un partner de CVI compatible que usa su organización.
 
- **[Get-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/get-csvideointeropserviceprovider):** Obtenga todos los proveedores que se han configurado para su uso dentro de la organización.
 
- **[Remove-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/remove-csvideointeropserviceprovider):** Use Remove-CsVideoInteropServiceProvider para quitar toda la información del proveedor sobre un proveedor que ya no usa su organización.  
 
## <a name="consent"></a>Consentimiento

Deberá proporcionar el consentimiento de permisos para los dispositivos de teleconferencia (VTC) para unirse a las reuniones de su organización a través del servicio de asociados. Este vínculo de consentimiento también será proporcionado por tu partner.  
 
Cuando se completen estos pasos, los usuarios habilitados individualmente a través del cmdlet Grant anterior, o todos los usuarios de la organización si el espacio empresarial está habilitado, tendrán coordenadas de VTC en todas las reuniones de Teams que programe. Cualquier VTC puede unirse a estas reuniones a través de esas coordenadas.


|Nombre|Descripción breve de permiso de aplicación| Descripción|
|--|--|---|
|Calls.JoinGroupCall.All|Unirse a llamadas y reuniones grupales como aplicación (versión preliminar)|Permite que la aplicación se una a llamadas grupales y reuniones programadas en su organización, sin un usuario que haya iniciado sesión.  La aplicación se unirá con los privilegios de un usuario de directorio para las reuniones de su inquilino.|
|Calls.JoinGroupCallasGuest.All|Unirse a llamadas y reuniones grupales como usuario invitado (versión preliminar)|Permite que la aplicación se una anónimamente a llamadas grupales y reuniones programadas en su organización, sin un usuario que haya iniciado sesión.  La aplicación se unirá como invitado a las reuniones de su inquilino.|
|Calls.AccessMedia.All|Acceder a las transmisiones multimedia en una llamada como una aplicación (vista previa)|Permite a la aplicación obtener acceso directo a las transmisiones multimedia en una llamada, sin un usuario que haya iniciado sesión.|
|OnlineMeetings.Read.All|Leer detalles de la reunión en línea (versión preliminar)|Permite que la aplicación lea los detalles de la reunión en línea de su organización, sin un usuario que haya iniciado sesión.|

## <a name="schedule"></a>Programación

Después, programe la reunión de Teams con las coordenadas de interoperabilidad de vídeo. El usuario habilitado puede programar reuniones de equipos a través de:
- [Complemento para reunión de Teams para Outlook](teams-add-in-for-outlook.md)
- Equipos de escritorio y dispositivos móviles del cliente de Teams


## <a name="join"></a>Join

Puede unirse a las reuniones de Teams con sus dispositivos VTC de las siguientes maneras:
 
- IVR (respuesta interactiva de voz)
    - Puedes llamar al IVR del partner mediante el tenantkey@domain. 
    - Una vez que se encuentra en el IVR asociado, se le pedirá que introduzca el id. de conferencia de VTC, que le conectará a la reunión de Teams.
- Marcado directo
    - Puede llamar directamente a la reunión de Teams sin interactuar con el IVR del partner mediante la característica de marcado directo con la cadena completa de clave de inquilino. VTC ConferenceId@domain.
- Marcado con un solo toque
    - Si tiene una sala de Teams integrada, puede usar las capacidades de marcado con un solo toque que ofrece su partner (sin tener que escribir ninguna cadena de marcado).

Por último, interactúe con los usuarios de Teams en sus reuniones mediante el uso compartido de audio, vídeo y contenido. 
