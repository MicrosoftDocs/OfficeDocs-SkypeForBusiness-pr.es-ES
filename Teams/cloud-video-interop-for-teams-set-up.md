---
title: Configurar la interoperabilidad de vídeo en la nube de Microsoft Teams
author: lolaj
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: srividhc
description: En este artículo se explica cómo puede planear y configurar interoperabilidad de vídeo en la nube para los usuarios de la organización.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: ff969701b9e0641ef09810f00a7aa34410e32b45
ms.sourcegitcommit: 69d1cea64425f03e562b5fb930493e27b61db96b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/21/2018
ms.locfileid: "24968298"
---
# <a name="set-up-cloud-video-interop-for-microsoft-teams"></a>Configurar la interoperabilidad de vídeo en la nube de Microsoft Teams

Cuando haya [elegido en sus socios de interoperabilidad de vídeo en la nube](cloud-video-interop.md), debe planear la implementación, configurar get con detalles de aprovisionamiento y clave de inquilino de socio y consentimiento a la aplicación de interoperabilidad de vídeo en su organización. En el siguiente diagrama describe el proceso. 

![Implementación de CVI en la organización](media/deploying-cvi.png)

## <a name="plan"></a>Planificar

Vea [Interoperabilidad de vídeo en la nube para los equipos de Microsoft](cloud-video-interop.md) para obtener información acerca de cómo identificar un socio o socios para usar en su organización. 

Para planear la habilitación todo el usuario en función o simultánea/sitio: 

- Elegir un modelo de implementación hospedada por el modelo o para su uso
- Seleccione el plan de licencia ideal para su organización. 
- Planeación de capacidad de las máquinas virtuales es que va a hospedar la infraestructura de vídeo.

## <a name="configure"></a>Configurar 

Para configurar la interoperabilidad de vídeo en la nube, siga estos pasos. 

1. Para obtener información de configuración de los socios y socios que tiene elegido (clave de inquilino, AppID...). Puede usar a uno o más asociados de interoperabilidad vídeo en su organización 

2. Asegúrese de que su red está configurada correctamente. Configure el firewall de vídeo basada en estándares para recorrido por la red perimetral admitir. Por ejemplo: 
    - Cisco VCS-e                  
    - Polycom RPAD

3. Configurar salones integrados con exchange y OTD. En la mayoría de los casos, retransmisión adicional tendría que configurarse y configurado en el entorno.


## <a name="provision"></a>Aprovisionamiento
 
La clave de inquilino será la llamada de salida para el servicio de socio. En el ejemplo siguiente, 813878896@t.plcm.vc es la clave de inquilino. 

![Ejemplo de clave de inquilino](media/tenant-key-example.png) 

Debe ejecutar los siguientes cmdlets para aprovisionar la clave de inquilino y también permiten seleccionar usuarios o toda la organización crear reuniones con coordenadas de interoperabilidad de vídeo.

 
- ** [Get-CsTeamsVideoInteropServicepolicy](https://docs.microsoft.com/en-us/powershell/module/skype/get-csteamsvideointeropservicepolicy):** Microsoft proporciona directivas construidas previamente para cada uno de nuestros socios compatibles que le permiten designar que socios a usar para la interoperabilidad de vídeo en la nube.

    Este cmdlet permite identificar las directivas construidas previa a la que pueden usar en su organización. Puede asignar esta directiva a uno o varios de los usuarios aprovecha el cmdlet Grant-CsTeamsVideoInteropServicePolicy.
 
- ** [Grant-CsTeamsVideoInteropServicePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/grant-csteamsvideointeropservicepolicy):** El cmdlet Grant-CsTeamsVideoInteropServicePolicy permite asignar una directiva previamente construida para su uso en la organización o asignar la directiva a usuarios específicos.
 
- ** [Nuevo CsVideoInteropServiceProvider](https://docs.microsoft.com/en-us/powershell/module/skype/new-csvideointeropserviceprovider):** Use el nuevo-CsVideoInteropServiceProvider para especificar la información acerca de un socio CVI compatible la organización le gustaría usar.
 
- ** [Set-CsVideoInteropServiceProvider](https://docs.microsoft.com/en-us/powershell/module/skype/set-csvideointeropserviceprovider):** Utilice el Set-CsVideoInteropServiceProvider para actualizar la información sobre un socio CVI compatible que usa la organización.
 
- ** [Get-CsVideoInteropServiceProvider](https://docs.microsoft.com/en-us/powershell/module/skype/get-csvideointeropserviceprovider):** Obtener todos los proveedores que se han configurado para su uso dentro de la organización.
 
- ** [Remove-CsVideoInteropServiceProvider](https://docs.microsoft.com/en-us/powershell/module/skype/remove-csvideointeropserviceprovider):** Use Remove-CsVideoInteropServiceProvider para quitar toda la información de proveedor de un proveedor que ya no se usa la organización.  
 
## <a name="consent"></a>Consentimiento

Debe proporcionar el consentimiento de permiso para los dispositivos de videoconferencias (VTCs) para participar en las reuniones de las organizaciones a través del servicio de socio. También se proporcionará este vínculo de consentimiento por su socio.  
 
Una vez completados estos pasos, los usuarios que están habilitados de forma individual mediante el cmdlet Grant por encima o todos los usuarios de la organización si está habilitado el inquilino, tendrán coordenadas VTC en todas las reuniones de los equipos programan. Cualquier VTC puede unirse a estas reuniones a través de esas coordenadas.


|Nombre|Breve descripción de permisos de aplicación| Descripción|
|--|--|---|
|Calls.JoinGroupCall.All|Unirse a reuniones y llamadas de grupo como una aplicación (vista previa)|Permite que la aplicación para unirse a llamadas de grupo y las reuniones programadas en la organización, sin que el usuario ha iniciado sesión.  La aplicación se van a unir con los privilegios de un usuario de Active directory a las reuniones en su inquilino.|
|Calls.JoinGroupCallasGuest.All|Unirse a reuniones y llamadas de grupo como un usuario invitado (vista previa)|Permite que la aplicación de forma anónima unirse a llamadas de grupo y las reuniones programadas en la organización, sin que el usuario ha iniciado sesión.  La aplicación se unirá como invitado a las reuniones en su inquilino.|
|Calls.AccessMedia.All|Secuencias de medios de acceso en una llamada como una aplicación (vista previa)|Permite que la aplicación obtener acceso directo a secuencias de medios en una llamada, sin que el usuario ha iniciado sesión.|
|OnlineMeetings.Read.All|Detalles de la reunión en línea de lectura (vista previa)|Permite que la aplicación leer los detalles de la reunión en línea en la organización, sin que el usuario ha iniciado sesión.|

## <a name="schedule"></a>Programación

A continuación, programar reuniones de los equipos con las coordenadas de interoperabilidad de vídeo. El usuario habilitado puede programar reuniones de los equipos a través de:
- Agregar cliente de Outlook
- Cliente de los equipos móvil y de escritorio


## <a name="join"></a>Join

Puede unirse a reuniones de los equipos con los dispositivos VTC de las siguientes maneras:
 
- IVR (respuesta interactiva de voz)
    - Puede marcar a IVR del socio con la tenantkey@domain. 
    - Una vez que se encuentra en el socio IVR, se le pedirá que lo especifique el conferenceId VTC, que, a continuación, se conectará a la reunión de los equipos.
- Marcado directo
    - Puede marcar directamente a la reunión de los equipos sin necesidad de interacción con IVR del socio mediante la característica de marcado directo con la cadena completa de tenantkey. VTC ConferenceId@domain.
- Marcado con un solo toque
    - Si tiene un salón de equipos integrado, puede usar las capacidades de acceso telefónico con un solo toque ofrecidas por su socio (sin necesidad de escribir cualquier cadena de marcado).

Por último, engaeg con los usuarios de los equipos en las reuniones de uso compartido de audio, vídeo y contenido. 