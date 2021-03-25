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
description: Use la interoperabilidad de vídeo en la nube como una solución intermedia para permitir que los dispositivos de salas de reuniones de terceros se unan a reuniones de Microsoft Teams.
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
ms.custom:
- seo-marvel-apr2020
- seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3a8d657e2cbc12695453e26ef0e4bf9ad55070bf
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122364"
---
# <a name="cloud-video-interop-for-microsoft-teams"></a>Interoperabilidad de vídeos en la nube para Microsoft Teams

Cloud Video Interop (CVI) es una solución de terceros calificada por Microsoft que permite que las salas de reuniones de terceros (telepresencia) y los dispositivos de vídeo personales (VTCs) se unan a las reuniones de Microsoft Teams.
 
Con Microsoft Teams, obtiene colaboración de contenido en línea enriquecido en reuniones que incluyen audio, vídeo y uso compartido de contenido. Esto se puede disfrutar a través del cliente de escritorio y web, así como a través de muchos dispositivos asociados que se integran de forma nativa con Microsoft Teams. Sin embargo, muchos clientes ya han invertido en dispositivos de videoconferencia y videoconferencia personal, lo que puede resultar costoso de actualizar. La interoperabilidad de vídeo en la nube proporciona una solución sencilla que le permite seguir usando las soluciones existentes hasta que esté listo para actualizar.

Con la interoperabilidad de vídeo en la nube, Microsoft Teams ofrece una experiencia de reunión nativa para todos los participantes: en salas de reuniones o dentro de clientes de Teams.

### <a name="is-cloud-video-interop-for-me"></a>¿La interoperabilidad de vídeo en la nube es para mí?

La interoperabilidad de vídeo en la nube proporciona un servicio intermedio mientras se pasa a una solución nativa completa de Microsoft Teams, con puntos de conexión de Teams. El servicio proporcionado debe formar parte de la ruta de migración.

La interoperabilidad de vídeo en la nube está destinada a los clientes que cumplen los siguientes criterios:

- Tener una gran implementación de dispositivos de sala de reuniones e implementación de dispositivos de vídeo personales (más de 50 dispositivos) que no están cualificados para la integración directa con Microsoft Teams
- Son compatibles con uno de nuestros partners de interoperabilidad de vídeo en la nube
- Desea conservar el valor de su inversión en sus dispositivos actuales de la sala de reuniones y dispositivos de vídeo personales durante la migración a una solución nativa de Microsoft Teams

Aunque la interoperabilidad de vídeo en la nube ofrece una excelente solución intermedia, animamos a nuestros clientes a que busquen nuestras soluciones nativas de reuniones de Teams, como Sistemas de salas de Teams, a largo plazo. 

### <a name="office-365-us-government-and-third-party-services"></a>Office 365 Us Government and third-party services

Office 365 ofrece la capacidad de integrar aplicaciones de terceros en sitios de SharePoint Online, Skype Empresarial, Teams, aplicaciones de Office incluidas en aplicaciones de Microsoft 365 para empresas (como Word, Excel, PowerPoint y Outlook) y Outlook Web App. Además, Office 365 admite la integración con proveedores de servicios de terceros. Estas aplicaciones y servicios de terceros pueden implicar almacenar, transmitir y procesar datos de clientes de su organización en sistemas de terceros que están fuera de la infraestructura de Office 365 y, por lo tanto, no están cubiertos por los compromisos de cumplimiento y protección de datos de Office 365. **Se recomienda revisar las declaraciones de privacidad y cumplimiento proporcionadas por los terceros al evaluar el uso adecuado de estos servicios para su organización.**



### <a name="partners-certified-for-microsoft-teams"></a>Partners certificados para Microsoft Teams

Los siguientes partners tienen soluciones de interoperabilidad de vídeo para Microsoft Teams. Su empresa puede elegir trabajar con cualquier combinación de estos partners dentro de su empresa. 

|Partner|Solución de partner|
|----|---|
|![El logotipo que representa Poly RealConnect](media/polycom.png) | <a href="https://aka.ms/PolycomRealConnect" target="_blank">Poly RealConnect Service</a> |
|![El logotipo que representa Pexip Infinity](media/pexip.png)| <a href="https://aka.ms/PexipInfinity" target="_blank">Pexip Infinity para Microsoft Teams</a> | 
|![El logotipo que representa BlueJeans Gateway](media/bluejeans.png)| <a href="https://aka.ms/BluejeansGateway" target="_blank">BlueJeans Gateway para Microsoft Teams</a> |
|![El logotipo que representa Cisco CVI](media/cisco.png)|<a href="https://aka.ms/CiscoCVI" target="_blank">Integración de vídeo de Cisco Webex para Microsoft Teams</a>|

### <a name="cloud-video-interop-overview"></a>Información general sobre la interoperabilidad de vídeo en la nube

Cloud Video Interop es un servicio de terceros que ofrecen nuestros partners para proporcionar interoperabilidad entre las soluciones de videoconferencia y dispositivos de vídeo personales existentes en las instalaciones y Microsoft Teams.

Las soluciones ofrecidas por nuestros partners consisten en componentes que se pueden implementar ya sea basados en la nube o parcial o totalmente locales. 
     
En el siguiente diagrama se muestra la arquitectura de alto nivel de nuestras soluciones de partners.

![Diagrama que describe una solución de partner de interoperabilidad de vídeo en la nube de Teams](media/teams-cloud-video-interop-partner-solution.png)


## <a name="deploy-cloud-video-interop"></a>Implementar la interoperabilidad de vídeo en la nube

Al implementar una solución de interoperabilidad de vídeo en la nube, es importante comprender que va a implementar una solución de partner. Los pasos generales que debe seguir para implementar la interoperabilidad de vídeo en la nube se muestran en el siguiente diagrama.

![Diagrama que describe la implementación de CVI en su organización](media/deploying-cvi.png)

### <a name="plan"></a>Plan

Durante la fase del plan, debe identificar los dispositivos que no reemplazará con un dispositivo nativo de Teams y buscar un partner de interoperabilidad de vídeo en la nube que pueda admitir estos dispositivos.  

También es importante comprender que necesitará una licencia para cada usuario que programe reuniones en las que desee que se una un dispositivo habilitado para interoperabilidad de vídeo en la nube. Tenga en cuenta que los requisitos de licencia exactos se pueden obtener del partner de interoperabilidad de vídeo en la nube. Asegúrese de que esto está claro antes de iniciar la implementación.

### <a name="configure"></a>Configuración

El partner que haya elegido para la implementación de CVI le proporcionará un documento de implementación completo que consta de todos los pasos necesarios para implementar correctamente dentro de su organización. Esto incluirá puertos de firewall e intervalos IP, cambios de configuración para sus dispositivos y otras opciones de configuración que deben cambiar.

### <a name="provision"></a>Aprovisionar  

Durante la fase de aprovisionamiento, asignará licencias a los usuarios adecuados según la guía de configuración del partner. También tendrá que pasar por el proceso de consentimiento de Azure para proporcionar al partner acceso a su entorno de Teams. Consulte [Permisos y consentimiento en el punto](/azure/active-directory/develop/v2-permissions-and-consent) de conexión de la plataforma de identidad de Microsoft para obtener más información sobre el proceso de consentimiento de Azure.

### <a name="schedule"></a>Programar

Una vez que un usuario esté habilitado para la interoperabilidad de vídeo en la nube, cualquier reunión programada con el complemento de reunión de Teams para Outlook o el cliente de Teams tendrá la información adicional adecuada agregada automáticamente a la reunión de Teams para que los dispositivos compatibles con la interoperabilidad de vídeo en la nube puedan unirse a estas reuniones.

### <a name="join"></a>Join

Según la solución de partner, hay varias formas de unirse a una reunión habilitada para interoperabilidad de vídeo en la nube. El partner de interoperabilidad de vídeo en la nube le proporciona escenarios exactos de combinación de reuniones. Hemos enumerado algunos ejemplos a continuación:

- IVR (respuesta de voz interactiva) 
  - Puede llamar al IVR del partner con el tenantkey@domain.
  - Cuando se encuentra en el IVR asociado, se le pedirá que escriba el id. de conferencia de VTC, que le conectará a la reunión de Teams.
- Marcado directo 
  - Puede llamar directamente a la reunión de Teams sin interactuar con el IVR del partner mediante la característica de marcado directo, con la cadena completa de tenantkey. VTC ConferenceId@domain.
- Marcado con un solo toque 
  - Si tiene un salón de Teams integrado, puede usar las capacidades de marcado de un solo toque que ofrece su partner (sin tener que escribir ninguna cadena de marcado).

## <a name="manage-cloud-video-interop"></a>Administrar la interoperabilidad de vídeo en la nube

Después de implementar la interoperabilidad de vídeo en la nube, puede administrar los dispositivos con las soluciones proporcionadas por nuestros partners. Cada partner le proporcionará una interfaz administrativa que incluirá la administración de licencias y dispositivos. 

Los informes también están disponibles directamente desde la interfaz administrativa del partner. Para obtener más información sobre las capacidades de informes, póngase en contacto con el partner que prefiera. 

### <a name="troubleshooting-cloud-video-interop"></a>Solución de problemas de interoperabilidad de vídeo en la nube

Cloud Video Interop es un servicio proporcionado por un asociado. Si tiene problemas, el primer paso es conectar un dispositivo que tiene el cliente de Teams instalado y conectarlo al mismo segmento que el dispositivo de interoperabilidad de vídeo en la nube que está causando problemas. 

Si Teams funciona correctamente en este segmento y también ha seguido todas las directrices de configuración y redes que ha proporcionado el partner, tendrá que ponerse en contacto con el partner para obtener más solución de problemas. 

## <a name="powershell-for-cloud-video-interop"></a>Interoperabilidad de vídeo en la nube de PowerShell

Los siguientes cmdlets de PowerShell están disponibles para automatizar (parcialmente) la implementación de interoperabilidad de vídeo en la nube.

- **Get-CsTeamsVideoInteropServicepolicy:** Microsoft proporciona directivas predefinidas para cada uno de nuestros partners compatibles que le permiten designar qué partners usar para la interoperabilidad de vídeo en la nube.<br>Este cmdlet le permite identificar las directivas preconstrucciones que puede usar en su organización. Puede asignar esta directiva a uno o varios de sus usuarios aprovechando el cmdlet Grant-CsTeamsVideoInteropServicePolicy usuario.
- **Grant-CsTeamsVideoInteropServicePolicy:** este cmdlet le permite asignar una directiva predefinida para su uso en su organización o asignar la directiva a usuarios específicos.
- **New-CsVideoInteropServiceProvider:** Use este cmdlet para especificar información sobre un partner CVI compatible que su organización desea usar.
- **Set-CsVideoInteropServiceProvider:** Use este cmdlet para actualizar información sobre un partner CVI compatible que usa su organización.
- **Get-CsVideoInteropServiceProvider:** Use este cmdlet para obtener todos los proveedores que se han configurado para su uso dentro de la organización.
- **Remove-CsVideoInteropServiceProvider:** Use este cmdlet para quitar toda la información del proveedor sobre un proveedor que su organización ya no usa.