---
title: Interoperabilidad de vídeos en la nube para Microsoft Teams
ms.author: mabond
author: mkbond007
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: naforer
f1.keywords:
- NOCSH
description: Use cloud video interop as an intermediate solution to allow third-party meeting room devices to join Microsoft Teams meetings.
ms.localizationpriority: medium
ms.collection:
- M365-voice
- M365-collaboration
ms.custom:
- seo-marvel-apr2020
- seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3c732cc01a525a4895fafe45c954c965fe960853
ms.sourcegitcommit: 424b14534aa269bb408c97c368102a193b481656
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67706457"
---
# <a name="cloud-video-interop-for-microsoft-teams"></a>Interoperabilidad de vídeos en la nube para Microsoft Teams

Cloud Video Interop (CVI) es una solución de terceros calificada por Microsoft que permite que las salas de reuniones (telepresencia) y los dispositivos de vídeo personales (VTCs) de terceros se unan a las reuniones de Microsoft Teams.
 
Con Microsoft Teams, obtiene una colaboración enriquecida de contenido en línea en reuniones que incluyen audio, vídeo y uso compartido de contenido. Esto se puede disfrutar a través del cliente de escritorio y web, así como a través de muchos dispositivos asociados que se integran de forma nativa con Microsoft Teams. Sin embargo, muchos clientes ya han invertido en teleconferencias de vídeo y dispositivos de comunicación de vídeo personales, lo que puede resultar costoso de actualizar. Cloud Video Interop ofrece una solución sencilla, que le permite seguir utilizando sus soluciones existentes hasta que esté listo para actualizar.

Con la interoperabilidad de vídeo en la nube, Microsoft Teams ofrece una experiencia de reunión nativa para todos los participantes, tanto en salas de reuniones como en clientes de Teams.

### <a name="is-cloud-video-interop-for-me"></a>¿Es cloud video interop para mí?

La interoperabilidad de vídeo en la nube proporciona un servicio intermedio mientras realiza la transición a una solución nativa completa de Microsoft Teams, usando los puntos de conexión de Teams. El servicio proporcionado debe formar parte de la ruta de migración.

Cloud Video Interop está destinada a los clientes que cumplen los siguientes criterios:

- Tener una gran implementación de dispositivos de salas de reuniones e implementación de dispositivos de vídeo personales (más de 50 dispositivos) que no están cualificados para la integración directa con Microsoft Teams
- Son compatibles con uno de nuestros asociados de interoperabilidad de Cloud Video
- Desea conservar el valor de su inversión en sus dispositivos actuales de la sala de reuniones y dispositivos de vídeo personales durante la migración a una solución nativa de Microsoft Teams

Mientras que la interoperabilidad de vídeo en la nube ofrece una gran solución intermedia, animamos a nuestros clientes a buscar en nuestras soluciones nativas de Teams Meeting, como Teams Room Systems, a largo plazo. 

### <a name="office-365-us-government-and-third-party-services"></a>Office 365 servicios gubernamentales y de terceros de EE. UU.

Office 365 proporciona la capacidad de integrar aplicaciones de terceros en sitios de SharePoint Online, Skype Empresarial, Teams, aplicaciones de Office incluidas en Aplicaciones Microsoft 365 para empresas (como Word, Excel, PowerPoint y Outlook) y Outlook Web App. Además, Office 365 admite la integración con proveedores de servicios de terceros. Estas aplicaciones y servicios de terceros pueden implicar el almacenamiento, la transmisión y el procesamiento de los datos de clientes de su organización en sistemas de terceros que se encuentran fuera de la infraestructura Office 365 y, por tanto, no están cubiertos por los compromisos de cumplimiento Office 365 y protección de datos. **Se recomienda que revise las declaraciones de privacidad y cumplimiento proporcionadas por los terceros al evaluar el uso adecuado de estos servicios para su organización.**



### <a name="partners-certified-for-microsoft-teams"></a>Partners Certified for Microsoft Teams

Los siguientes asociados tienen soluciones de interoperabilidad de vídeo para Microsoft Teams. Su empresa puede elegir trabajar con cualquier combinación de estos partners dentro de su empresa. 

|Socio|Solución de partner|
|----|---|
|![El logotipo que representa a Poly RealConnect.](media/polycom.png) | <a href="https://aka.ms/PolycomRealConnect" target="_blank">Servicio Poly RealConnect</a> |
|![El logotipo que representa a Pexip Infinity.](media/pexip.png)| <a href="https://aka.ms/PexipInfinity" target="_blank">Pexip Infinity para Microsoft Teams</a> | 
|![El logotipo que representa a BlueJeans Gateway.](media/bluejeans.png)| <a href="https://aka.ms/BluejeansGateway" target="_blank">BlueJeans Gateway para Microsoft Teams</a> |
|![El logotipo que representa a Cisco CVI.](media/cisco.png)|<a href="https://aka.ms/CiscoCVI" target="_blank">Integración de vídeo de Cisco Webex para Microsoft Teams</a>|

### <a name="cloud-video-interop-overview"></a>Información general sobre interoperabilidad de Cloud Video

Cloud Video Interop es un servicio de terceros que nuestros asociados ofrecen para proporcionar interoperabilidad entre las soluciones de videoconferencia existentes y las soluciones de dispositivos de vídeo personales locales, y Microsoft Teams.

Las soluciones ofrecidas por nuestros asociados consisten en componentes que se pueden implementar completamente basados en la nube o parcial o completamente locales. 
     
El siguiente diagrama muestra la arquitectura de alto nivel de nuestras soluciones de asociados.

![Diagrama que describe una solución asociada de interoperabilidad de Vídeo en la nube de Teams.](media/teams-cloud-video-interop-partner-solution.png)


## <a name="deploy-cloud-video-interop"></a>Implementar la interoperabilidad de vídeo en la nube

Al implementar una solución de interoperabilidad de vídeo en la nube, es importante comprender que está implementando una solución asociada. Los pasos generales que debe seguir para implementar cloud video interop se enumeran en el siguiente diagrama.

![Diagrama que describe la implementación de CVI en su organización.](media/deploying-cvi.png)

### <a name="plan"></a>Plan

Durante la fase del plan, debe identificar los dispositivos que no reemplazará por un dispositivo nativo de Teams y buscar un socio de interoperabilidad de vídeo en la nube que pueda admitir estos dispositivos.  

También es importante comprender que necesitará una licencia para cada usuario que programe reuniones en las que desee un dispositivo habilitado para interoperabilidad de Cloud Video. Tenga en cuenta que los requisitos de licencia exactos se pueden obtener del partner Cloud Video Interop. Asegúrese de que está claro antes de iniciar la implementación.

### <a name="configure"></a>Configuración

El partner que ha elegido para la implementación de CVI le proporcionará un documento de implementación completo que consta de todos los pasos necesarios para implementar correctamente en su organización. Esto incluirá puertos de firewall e intervalos IP, cambios de configuración para los dispositivos y otras opciones de configuración que deben cambiar.

### <a name="provision"></a>Provisión  

Durante la fase de aprovisionamiento, asignará licencias a los usuarios adecuados según la guía de configuración del partner. También tendrá que pasar por el proceso de consentimiento de Azure para proporcionar acceso al partner a su entorno de Teams. Vea [Permisos y consentimiento en el punto de conexión de Plataforma de identidad de Microsoft](/azure/active-directory/develop/v2-permissions-and-consent) para obtener más información sobre el proceso de consentimiento de Azure.

### <a name="schedule"></a>Horario

Después de habilitar a un usuario para la interoperabilidad de vídeo en la nube, cualquier reunión programada mediante el complemento de reunión de Teams para Outlook o el cliente de Teams tendrá la información adicional apropiada agregada automáticamente a la reunión de Teams para que los dispositivos compatibles con la interoperabilidad de vídeo en la nube puedan unirse a estas reuniones.

### <a name="join"></a>Join

En función de la solución asociada, hay varias maneras de unirse a una reunión habilitada para interoperabilidad de Cloud Video. Su socio de interoperabilidad de Cloud Video le proporcionará escenarios de unión a reuniones exactos. Hemos enumerado algunos ejemplos a continuación:

- IVR (Respuesta interactiva de voz) 
  - Puede llamar al IVR del partner mediante el tenantkey@domain.
  - Cuando esté en el IVR asociado, se le pedirá que introduzca el Id. de conferencia de VTC, que le conectará a la reunión de Teams.
- Marcación directa 
  - Puede llamar directamente a la reunión de Teams sin interactuar con el IVR del partner mediante la característica de marcado directo, usando la cadena completa de clave de inquilino. ConferenceId@domain VTC.
- Marcación con un solo toque 
  - Si tiene una sala de Teams integrada, puede usar las funcionalidades de marcado con un solo toque que ofrece su partner (sin tener que escribir ninguna cadena de marcado).

## <a name="manage-cloud-video-interop"></a>Administrar la interoperabilidad de vídeo en la nube

Después de implementar cloud video interop, usted puede gestionar los dispositivos utilizando las soluciones proporcionadas por nuestros socios. Cada partner le proporcionará una interfaz administrativa que incluirá la administración de dispositivos y licencias. 

Los informes también están disponibles directamente desde la interfaz administrativa del asociado. Para obtener más información sobre las capacidades de creación de informes, póngase en contacto con el partner de su elección. 

### <a name="troubleshooting-cloud-video-interop"></a>Solución de problemas de interoperabilidad de vídeo en la nube

Cloud Video Interop es un servicio proporcionado por un partner. Si tiene problemas, el primer paso es conectar un dispositivo que tenga instalado el cliente de Teams y conectarlo al mismo segmento que el dispositivo de interoperabilidad de vídeo en la nube que está causando problemas. 

Si Teams funciona correctamente en este segmento y también ha seguido todas las directrices de configuración y redes que ha proporcionado el partner, deberá ponerse en contacto con el partner para encontrar más soluciones de problemas. 

## <a name="powershell-for-cloud-video-interop"></a>PowerShell para interoperabilidad de vídeo en la nube

Los siguientes cmdlets de PowerShell están disponibles para automatizar (parcialmente) la implementación de interoperabilidad de Cloud Video.

- **Get-CsTeamsVideoInteropServicepolicy**: Microsoft proporciona directivas predefinidas para cada uno de nuestros asociados admitidos que le permiten designar qué asociados usar para la interoperabilidad de vídeo en la nube.<br>Este cmdlet le permite identificar las directivas predefinidas que puede usar en su organización. Puede asignar esta directiva a uno o varios de los usuarios aprovechando el cmdlet de Grant-CsTeamsVideoInteropServicePolicy.
- **Grant-CsTeamsVideoInteropServicePolicy**: este cmdlet le permite asignar una directiva predefinida para su uso en su organización o asignar la directiva a usuarios específicos.
- **New-CsVideoInteropServiceProvider**: Use este cmdlet para especificar información sobre un partner CVI compatible que su organización desea usar.
- **Set-CsVideoInteropServiceProvider**: Use este cmdlet para actualizar la información sobre un partner CVI compatible que usa su organización.
- **Get-CsVideoInteropServiceProvider**: Use este cmdlet para obtener todos los proveedores que se han configurado para su uso dentro de la organización.
- **Remove-CsVideoInteropServiceProvider**: Use este cmdlet para quitar toda la información del proveedor sobre un proveedor que su organización ya no usa.