---
title: Configurar la interoperabilidad de vídeos en la nube para Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: srividhc
f1.keywords:
- NOCSH
description: En este artículo se explica cómo puede planear y configurar la interoperabilidad de vídeo en la nube para los usuarios de su organización.
ms.localizationpriority: medium
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f9ae7d59a97989d7f0677bf56b46c0a3d51f3e49
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2022
ms.locfileid: "66789335"
---
# <a name="set-up-cloud-video-interop-for-microsoft-teams"></a>Configurar la interoperabilidad de vídeos en la nube para Microsoft Teams

Después de [haber elegido sus socios de Interoperabilidad de vídeo](cloud-video-interop.md) en la nube, tendrá que planear la implementación, configurarse con detalles de aprovisionamiento y la clave de inquilino del partner, y dar su consentimiento a la aplicación de interoperabilidad de vídeo de su organización. En el siguiente diagrama se describe el proceso.

![Implementar CVI en su organización.](media/deploying-cvi.png)

## <a name="plan"></a>Plan

Consulte [Interoperabilidad de vídeo en la nube para Microsoft Teams](cloud-video-interop.md) para obtener información sobre cómo identificar a un partner o partners para que lo usen en su organización.

Para planear la habilitación basada en usuarios, simultáneas o en todo el sitio:

- Elegir un modelo de implementación o un modelo hospedado para su uso
- Seleccione el plan de licencia ideal para su organización.
- Planear la capacidad de las máquinas virtuales es hospedar la infraestructura de vídeo.

## <a name="configure"></a>Configuración

Para configurar la interoperabilidad de vídeo en la nube, siga estos pasos.

1. Obtén información de configuración de los partners que hayas elegido (clave de inquilino, appIds...). Puede usar uno o más partners de interoperabilidad de vídeo en su organización

2. Asegúrate de que la red esté configurada correctamente. Configure el firewall de vídeo basado en estándares para que la red perimetral sea compatible. Por ejemplo:
    - Cisco VCS-e
    - Polycom RPAD

3. Configurar salas integradas con intercambio y OTD. En la mayoría de los casos, la retransmisión adicional tendría que configurarse y configurarse en su entorno.

## <a name="provision"></a>Provisión

La clave del inquilino será la llamada telefónica al servicio del partner. En el ejemplo siguiente, 813878896@t.plcm.vc es la clave de inquilino.

![Ejemplo de clave de espacio empresarial.](media/tenant-key-example.png)

Tendrá que ejecutar los siguientes cmdlets para aprovisionar la clave de inquilino y también habilitar usuarios seleccionados o toda la organización para crear reuniones con coordenadas de interoperabilidad de vídeo.

- **[Get-CsTeamsVideoInteropServicepolicy](/powershell/module/skype/get-csteamsvideointeropservicepolicy):** Microsoft proporciona directivas predefinidas para cada uno de nuestros asociados admitidos que le permiten designar qué asociados usar para la interoperabilidad de vídeo en la nube.

    Este cmdlet le permite identificar las directivas predefinidas que puede usar en su organización. Puede asignar esta directiva a uno o varios de los usuarios aprovechando el cmdlet de Grant-CsTeamsVideoInteropServicePolicy.

- **[Grant-CsTeamsVideoInteropServicePolicy](/powershell/module/skype/grant-csteamsvideointeropservicepolicy):** El cmdlet Grant-CsTeamsVideoInteropServicePolicy le permite asignar una directiva predefinida para su uso en su organización o asignar la directiva a usuarios específicos.

- **[New-CsVideoInteropServiceProvider](/powershell/module/skype/new-csvideointeropserviceprovider):** Use la New-CsVideoInteropServiceProvider para especificar información sobre un socio CVI compatible que le gustaría usar en su organización.

- **[Set-CsVideoInteropServiceProvider](/powershell/module/skype/set-csvideointeropserviceprovider):** Use la Set-CsVideoInteropServiceProvider para actualizar la información sobre un partner CVI compatible que usa su organización.

- **[Get-CsVideoInteropServiceProvider](/powershell/module/skype/get-csvideointeropserviceprovider):** Obtenga todos los proveedores que se han configurado para su uso dentro de la organización.

- **[Remove-CsVideoInteropServiceProvider](/powershell/module/skype/remove-csvideointeropserviceprovider):** Use Remove-CsVideoInteropServiceProvider para quitar toda la información del proveedor sobre un proveedor que la organización ya no usa.

## <a name="consent"></a>Consentimiento

Deberá dar su consentimiento para que los dispositivos de teleconferencia de vídeo (VTCs) se unan a las reuniones de su organización a través del servicio asociado. Este vínculo de consentimiento también será proporcionado por su partner.

Cuando se completen estos pasos, los usuarios habilitados individualmente mediante el cmdlet Grant anterior o todos los usuarios de la organización, si el inquilino está habilitado, tendrán coordenadas de VTC en todas las reuniones de Teams que programen. Cualquier VTC puede unirse a estas reuniones a través de esas coordenadas.

|Nombre|Descripción breve de permisos de aplicación| Descripción|
|---|---|---|
|Calls.JoinGroupCall.All|Unirse a llamadas y reuniones de grupo como una aplicación (versión preliminar)|Permite a la aplicación unirse a llamadas de grupo y reuniones programadas en su organización, sin un usuario que haya iniciado sesión.  La aplicación se unirá con los privilegios de un usuario de directorio a las reuniones de su inquilino.|
|Calls.JoinGroupCallasGuest.All|Unirse a llamadas y reuniones de grupo como usuario invitado (versión preliminar)|Permite a la aplicación unirse anónimamente a llamadas de grupo y reuniones programadas en su organización, sin un usuario que haya iniciado sesión.  La aplicación se unirá como invitado a las reuniones de su inquilino.|
|Calls.AccessMedia.All|Acceder a las transmisiones multimedia en una llamada como aplicación (versión preliminar)|Permite a la aplicación obtener acceso directo a secuencias multimedia en una llamada, sin un usuario que haya iniciado sesión.|
|OnlineMeetings.Read.All|Leer detalles de la reunión en línea (versión preliminar)|Permite a la aplicación leer los detalles de la reunión en línea en su organización, sin un usuario que haya iniciado sesión.|

## <a name="schedule"></a>Horario

A continuación, programe reuniones de Teams con coordenadas de interoperabilidad de vídeo. El usuario habilitado puede programar reuniones de equipos a través de:

- [Complemento para reunión de Teams para Outlook](teams-add-in-for-outlook.md)
- Equipos de escritorio y móviles cliente de Teams

## <a name="join"></a>Join

Puede unirse a reuniones de Teams con sus dispositivos VTC de las siguientes maneras:

- IVR (Respuesta interactiva de voz)
  - Puede llamar al IVR del partner mediante el tenantkey@domain.
  - Una vez que esté en el IVR asociado, se le pedirá que introduzca el Id. de conferencia de VTC, que le conectará a la reunión de Teams.
- Marcación directa
  - Puede llamar directamente a la reunión de Teams sin interactuar con el IVR del partner mediante la característica de marcado directo con la cadena completa de clave de inquilino. ConferenceId@domain VTC.
- Marcación con un solo toque
  - Si tiene una sala de Teams integrada, puede usar las funcionalidades de marcado con un solo toque que ofrece su partner (sin tener que escribir ninguna cadena de marcado).

Por último, interactúe con los usuarios de Teams en sus reuniones con audio, vídeo y uso compartido de contenido.
