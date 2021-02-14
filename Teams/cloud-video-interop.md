---
title: Interoperabilidad de vídeos en la nube para Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: naforer
f1.keywords:
- NOCSH
description: Use Cloud Video Interoperabilidad como solución intermedia para permitir que los dispositivos de salas de reuniones de terceros se unan a reuniones de Microsoft Teams.
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
ms.custom:
- seo-marvel-apr2020
- seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2a9bf3cade5c17a8d3649a29ca999dec1f909624
ms.sourcegitcommit: 4386f4b89331112e0d54943dc3133791d5dca3fb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/09/2020
ms.locfileid: "49611854"
---
# <a name="cloud-video-interop-for-microsoft-teams"></a>Interoperabilidad de vídeos en la nube para Microsoft Teams

Cloud Video Interoperabilidad (CVI) es una solución de terceros calificada por Microsoft que permite que las salas de reuniones de terceros (telepresencia) y los dispositivos de vídeo personal (VTCs) se unan a las reuniones de Microsoft Teams.
 
Con Microsoft Teams, obtiene colaboración de contenido en línea enriquecido en reuniones que incluyen audio, vídeo y uso compartido de contenido. Esto se puede disfrutar a través del cliente de escritorio y web, así como a través de muchos dispositivos asociados que se integran de forma nativa con Microsoft Teams. Sin embargo, muchos clientes ya han invertido en videoconferencia y dispositivos de comunicación de vídeo personales, que pueden resultar costosos de actualizar. Cloud Video Interoperabilidad proporciona una solución sencilla, lo que le permite seguir usando sus soluciones existentes hasta que esté listo para la actualización.

Con cloud Video Interoperabilidad, Microsoft Teams ofrece una experiencia de reunión nativa para todos los participantes, en salas de reuniones o dentro de clientes de Teams.

### <a name="is-cloud-video-interop-for-me"></a>¿La interoperabilidad de vídeo en la nube es para mí?

Cloud Video Interoperabilidad proporciona un servicio intermedio mientras se pasa a una solución de Microsoft Teams nativa completa con puntos de conexión de Teams. El servicio proporcionado debe formar parte de su ruta de migración.

Cloud Video Interoperabilidad está pensada para los clientes que cumplen los siguientes criterios:

- Tener una gran implementación de dispositivos de salas de reuniones y dispositivos de vídeo personal (más de 50 dispositivos) no cualificados para la integración directa con Microsoft Teams
- Son compatibles con uno de nuestros socios de Interoperabilidad de vídeo en la nube
- Desea conservar el valor de su inversión en sus dispositivos de salas de reuniones actuales y dispositivos de vídeo personal durante la migración a una solución nativa de Microsoft Teams

Mientras que Cloud Video Interoperabilidad proporciona una gran solución intermedia, animamos a nuestros clientes a buscar en nuestras soluciones de reuniones de Teams nativas, como Sistemas de salas de Teams, a largo plazo. 

### <a name="office-365-us-government-and-third-party-services"></a>Office 365 US Government y servicios de terceros

Office 365 permite integrar aplicaciones de terceros en sitios de SharePoint Online, Skype Empresarial, Teams, aplicaciones de Office incluidas en las aplicaciones de Microsoft 365 para empresas (como Word, Excel, PowerPoint y Outlook) y Outlook Web App. Además, Office 365 admite la integración con proveedores de servicios de terceros. Estas aplicaciones y servicios de terceros podrían incluir almacenar, transmitir y procesar los datos de clientes de su organización en sistemas de terceros que están fuera de la infraestructura de Office 365 y, por lo tanto, no están cubiertos por los compromisos de cumplimiento y protección de datos de Office 365. **Se recomienda revisar las declaraciones de privacidad y cumplimiento proporcionadas por los terceros al evaluar el uso apropiado de estos servicios para su organización.**



### <a name="partners-certified-for-microsoft-teams"></a>Partners certificados para Microsoft Teams

Los siguientes partners tienen soluciones de interoperabilidad de vídeo para Microsoft Teams. Su empresa puede trabajar con cualquier combinación de estos partners dentro de su empresa. 

|Partner|Solución de partner|
|----|---|
|![El logotipo que representa Poly RealConnect](media/polycom.png) | <a href="https://aka.ms/PolycomRealConnect" target="_blank">Servicio Poly RealConnect</a> |
|![Logotipo que representa el infinito Pexip](media/pexip.png)| <a href="https://aka.ms/PexipInfinity" target="_blank">Infinito Pexip para Microsoft Teams</a> | 
|![Logotipo que representa BlueJeans Gateway](media/bluejeans.png)| <a href="https://aka.ms/BluejeansGateway" target="_blank">BlueJeans Gateway para Microsoft Teams</a> |
|![Logotipo que representa el CVI de Cisco](media/cisco.png)|<a href="https://aka.ms/CiscoCVI" target="_blank">Integración de Cisco Webex Video para Microsoft Teams</a>|

### <a name="cloud-video-interop-overview"></a>Información general sobre interoperabilidad de vídeo en la nube

Cloud Video Interoperabilidad es un servicio de terceros que ofrecen nuestros socios para proporcionar interoperabilidad entre videoconferencia existente y soluciones de dispositivos de vídeo personales locales, y Microsoft Teams.

Las soluciones ofrecidas por nuestros partners consisten en componentes que se pueden implementar, ya sea totalmente basados en la nube o parcialmente/totalmente locales. 
     
En el siguiente diagrama se muestra la arquitectura de alto nivel de nuestras soluciones de asociados.

![Diagrama que describe una solución de partner de Interoperabilidad de vídeo en la nube de Teams](media/teams-cloud-video-interop-partner-solution.png)


## <a name="deploy-cloud-video-interop"></a>Implementar interoperabilidad de vídeo en la nube

Al implementar una solución de interoperabilidad de vídeo en la nube, es importante comprender que está implementando una solución de asociado. Los pasos generales que debe seguir para implementar la interoperabilidad de vídeo en la nube se muestran en el siguiente diagrama.

![Diagrama que describe cómo implementar CVI en su organización](media/deploying-cvi.png)

### <a name="plan"></a>Plan

Durante la fase del plan, debe identificar los dispositivos que no va a reemplazar por un dispositivo nativo de Teams y buscar un partner de interoperabilidad de vídeo en la nube que pueda admitir estos dispositivos.  

También es importante comprender que necesitará una licencia para cada usuario que programe reuniones en las que desea un dispositivo habilitado para interoperabilidad de vídeo en la nube. Tenga en cuenta que se pueden obtener requisitos de licencia exactos del partner cloud Video Interoperabilidad. Asegúrese de que está claro antes de iniciar la implementación.

### <a name="configure"></a>Configuración

El partner que haya elegido para la implementación de CVI le proporcionará un documento de implementación completo que consta de todos los pasos necesarios para implementar correctamente dentro de su organización. Esto incluirá puertos e intervalos IP de firewall, cambios en la configuración de los dispositivos y otras opciones de configuración que necesiten cambiar.

### <a name="provision"></a>Aprovisionar  

Durante la fase de aprovisionamiento, asignará licencias a los usuarios correspondientes según la guía de configuración del partner. También deberá pasar por el proceso de consentimiento de Azure para proporcionar acceso de asociados a su entorno de Teams. Consulta [Permisos y consentimiento en el punto de conexión de la plataforma de identidad de Microsoft](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent) para obtener más información sobre el proceso de consentimiento de Azure.

### <a name="schedule"></a>Programación

Cuando se habilita a un usuario para la interoperabilidad de vídeo en la nube, todas las reuniones programadas mediante el complemento de reunión de Teams para Outlook o el cliente de Teams tendrán la información adicional adecuada agregada automáticamente a la reunión de Teams para que los dispositivos compatibles con interoperabilidad de vídeo en la nube puedan unirse a estas reuniones.

### <a name="join"></a>Join

Según la solución de partner, hay varias formas de unirse a una reunión habilitada para interoperabilidad de vídeo en la nube. Su partner de interoperabilidad de vídeo en la nube le proporciona escenarios exactos de unión a reuniones. Hemos enumerado algunos ejemplos a continuación:

- IVR (respuesta interactiva de voz) 
  - Puedes llamar al IVR del partner mediante el tenantkey@domain.
  - Cuando se encuentra en el IVR asociado, se le pedirá que introduzca el id. de conferencia de VTC, que le conectará a la reunión de Teams.
- Marcado directo 
  - Puede llamar directamente a la reunión de Teams sin interactuar con el IVR del partner mediante la característica de marcado directo, usando la cadena completa de clave de inquilino. VTC ConferenceId@domain.
- Marcado con un solo toque 
  - Si tiene una sala de Teams integrada, puede usar las capacidades de marcado con un solo toque que ofrece su partner (sin tener que escribir ninguna cadena de marcado).

## <a name="manage-cloud-video-interop"></a>Administrar interoperabilidad de vídeo en la nube

Después de implementar Cloud Video Interoperabilidad, puede administrar los dispositivos con las soluciones proporcionadas por nuestros socios. Cada partner le proporcionará una interfaz administrativa que incluirá la administración de licencias y dispositivos. 

Los informes también están disponibles directamente desde la interfaz administrativa del asociado. Para obtener más información sobre las capacidades de informes, póngase en contacto con el partner que prefiera. 

### <a name="troubleshooting-cloud-video-interop"></a>Solución de problemas de interoperabilidad de vídeo en la nube

Cloud Video Interoperabilidad es un servicio proporcionado por un socio. Si está experimentando problemas, el primer paso es conectar un dispositivo que tiene instalado el cliente de Teams y conectarlo al mismo segmento que el dispositivo de interoperabilidad de vídeo en la nube que está causando problemas. 

Si Teams funciona correctamente en este segmento y también ha seguido todas las directrices de configuración y redes que ha proporcionado el partner, deberá ponerse en contacto con el partner para obtener una solución de problemas. 

## <a name="powershell-for-cloud-video-interop"></a>PowerShell para interoperabilidad de vídeo en la nube

Los siguientes cmdlets de PowerShell están disponibles para automatizar (parcialmente) la implementación de interoperabilidad de vídeo en la nube.

- **Get-CsTeamsVideoInteropServicepolicy**: Microsoft proporciona directivas pre-construir para cada uno de nuestros socios compatibles que le permiten designar qué socios usar para cloud Video Interoperabilidad.<br>Este cmdlet le permite identificar las directivas pre-construir que puede usar en su organización. Puede asignar esta directiva a uno o varios de los usuarios aprovechando el cmdlet Grant-CsTeamsVideoInteropServicePolicy web.
- **Grant-CsTeamsVideoInteropServicePolicy:** este cmdlet le permite asignar una directiva preconstruyendo para su uso en su organización o asignar la directiva a usuarios específicos.
- **New-CsVideoInteropServiceProvider:** Use este cmdlet para especificar información sobre un partner CVI compatible que le gustaría usar en su organización.
- **Set-CsVideoInteropServiceProvider:** Use este cmdlet para actualizar información sobre un partner CVI compatible que use su organización.
- **Get-CsVideoInteropServiceProvider:** Use este cmdlet para obtener todos los proveedores que se han configurado para su uso dentro de la organización.
- **Remove-CsVideoInteropServiceProvider:** use este cmdlet para quitar toda la información del proveedor sobre un proveedor que ya no usa su organización.
