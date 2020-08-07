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
description: En este artículo se explica cómo se puede planear y configurar la interoperabilidad de vídeo en la nube para los usuarios de su organización.
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

Una vez que haya [elegido sus socios de interoperabilidad de video en la nube](cloud-video-interop.md), tendrá que planear su implementación, configurar los detalles de aprovisionamiento y la clave de inquilino del Partner, y el consentimiento de la aplicación de interoperabilidad de vídeo de su organización. En el siguiente diagrama se describe el proceso. 

![Implementar CVI en su organización](media/deploying-cvi.png)

## <a name="plan"></a>Plan

Consulte [interoperabilidad de vídeo en la nube para Microsoft Teams](cloud-video-interop.md) para obtener información sobre cómo identificar un partner o socios para usar en su organización. 

Para planificar la habilitación de los sitios de forma simultánea o concurrente: 

- Elegir un modelo de implementación o un modelo hospedado para su uso
- Seleccione el plan de licencia ideal para su organización. 
- Planee la capacidad de las VMs para hospedar su infraestructura de video.

## <a name="configure"></a>Configuración 

Para configurar la interoperabilidad de vídeo en la nube, siga estos pasos. 

1. Obtener información de configuración de los socios o socios que ha elegido (clave de inquilino, appIds...). Puede usar uno o varios socios de interoperabilidad de vídeo de su organización 

2. Asegúrese de que la red está configurada correctamente. Configure su firewall de vídeo basado en estándares para que sea compatible con la red perimetral. Por ejemplo: 
    - VCS-e de Cisco                  
    - RPAD Polycom

3. Configurar salas integradas con Exchange y OTD. En la mayoría de los casos, será necesario configurar y configurar la retransmisión adicional en su entorno.


## <a name="provision"></a>Aprovisionar
 
La clave de inquilino se enviará a través del servicio asociado. En el ejemplo siguiente, 813878896@t.plcm.vc es la clave de inquilino. 

![Ejemplo de clave de inquilino](media/tenant-key-example.png) 

Tendrá que ejecutar los siguientes cmdlets para aprovisionar la clave de inquilino y también habilitar a usuarios seleccionados o a toda la organización para crear reuniones con coordenadas de interoperabilidad de vídeo.

 
- ** [Get-CsTeamsVideoInteropServicepolicy](https://docs.microsoft.com/powershell/module/skype/get-csteamsvideointeropservicepolicy):** Microsoft proporciona directivas preconstruidas para cada uno de nuestros socios compatibles, que le permiten designar qué asociados usar para la interoperabilidad de vídeo en la nube.

    Este cmdlet le permite identificar las directivas preconstruidas que puede usar en su organización. Puede asignar esta directiva a uno o más de los usuarios que aprovechan el cmdlet Grant-CsTeamsVideoInteropServicePolicy.
 
- ** [Grant-CsTeamsVideoInteropServicePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsvideointeropservicepolicy):** El cmdlet Grant-CsTeamsVideoInteropServicePolicy le permite asignar una directiva preconstruida para su uso en su organización o asignar la Directiva a usuarios específicos.
 
- ** [New-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/new-csvideointeropserviceprovider):** Use el nuevo-CsVideoInteropServiceProvider para especificar información sobre un socio de CVI admitido que su organización desea usar.
 
- ** [Set-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/set-csvideointeropserviceprovider):** Use set-CsVideoInteropServiceProvider para actualizar la información sobre un socio de CVI compatible que usa su organización.
 
- ** [Get-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/get-csvideointeropserviceprovider):** Obtener todos los proveedores que se han configurado para su uso dentro de la organización.
 
- ** [Remove-CsVideoInteropServiceProvider](https://docs.microsoft.com/powershell/module/skype/remove-csvideointeropserviceprovider):** Use Remove-CsVideoInteropServiceProvider para quitar toda la información de proveedores de un proveedor que ya no use su organización.  
 
## <a name="consent"></a>Concede

Necesitará proporcionar autorización de permiso para que los dispositivos de teleconferencia de vídeo (VTCs) se unan a las reuniones de su organización a través del servicio de asociación. El socio también proporcionará este vínculo de consentimiento.  
 
Una vez completados estos pasos, los usuarios que se habilitan individualmente mediante el cmdlet Grant anterior o todos los usuarios de la organización si el inquilino está habilitado, tendrán coordenadas de VTC en todas las reuniones de teams que programen. Cualquier VTC puede unirse a estas reuniones a través de esas coordinadas.


|Nombre|Descripción breve de permisos de la aplicación| Descripción|
|--|--|---|
|Calls. JoinGroupCall. All|Unirse a reuniones grupales y reuniones como una aplicación (vista previa)|Permite a la aplicación unirse a llamadas grupales y a las reuniones programadas de su organización, sin necesidad de que un usuario haya iniciado sesión.  La aplicación se unirá con los privilegios de un usuario del directorio a las reuniones de su inquilino.|
|Calls. JoinGroupCallasGuest. All|Unirse a reuniones de grupo y reuniones como un usuario invitado (vista previa)|Permite a la aplicación unirse anónimamente a llamadas grupales y a reuniones programadas de su organización, sin necesidad de que un usuario haya iniciado sesión.  La aplicación se unirá como invitado a las reuniones de su inquilino.|
|Calls. AccessMedia. All|Acceder a las transmisiones multimedia en una llamada como una aplicación (vista previa)|Permite que la aplicación obtenga acceso directo a las transmisiones multimedia en una llamada, sin necesidad de que un usuario haya iniciado sesión.|
|OnlineMeetings. Read. All|Leer detalles de la reunión en línea (vista previa)|Permite que la aplicación Lea los detalles de la reunión en línea en su organización, sin necesidad de que un usuario haya iniciado sesión.|

## <a name="schedule"></a>Programa

A continuación, programe Teams reunión con coordenadas de interoperabilidad de vídeo. El usuario habilitado puede programar reuniones de Teams a través de:
- [Complemento de reunión de Teams para Outlook](teams-add-in-for-outlook.md)
- Equipo cliente de escritorio y móvil


## <a name="join"></a>Join

Puede unirse a las reuniones de Teams con sus dispositivos de VTC de las siguientes maneras:
 
- IVR (respuesta interactiva de voz)
    - Puedes llamar al IVR del socio con el tenantkey@domain. 
    - Una vez que se encuentre en el IVR de socio, se le pedirá que introduzca el VTC conferenceId, que le conectará a la reunión de Teams.
- Marcado directo
    - Puede llamar directamente a la reunión de Teams sin interactuar con el IVR del socio mediante la característica de marcado directo con la cadena completa de tenantkey. VTC ConferenceId@domain.
- Marcación sencilla
    - Si tiene una sala de equipos integrada, puede usar las funciones de marcado con un solo toque que le ofrece su partner (sin necesidad de escribir ninguna cadena de marcado).

Por último, comuníquese con los usuarios de Teams en sus reuniones con audio, vídeo y uso compartido de contenido. 
