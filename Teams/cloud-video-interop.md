---
title: Interoperabilidad de vídeos en la nube para Microsoft Teams
author: lolaj
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: srividhc
description: Interoperabilidad de vídeo en la nube permite que terceros dispositivos de salón para unirse a reuniones de Microsoft Teams de la reunión.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9ea1a81f2418b17d247dafe82d9e94e348d3b4c7
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/07/2019
ms.locfileid: "30459751"
---
# <a name="cloud-video-interop-for-microsoft-teams"></a>Interoperabilidad de vídeos en la nube para Microsoft Teams

Interoperabilidad de vídeo en la nube (CVI) es una solución de terceros de Microsoft Qualified que permite que las salas de reuniones de terceros (telepresencia) y los dispositivos de vídeo personal (VTCs) para participar en reuniones de Microsoft Teams.
 
Con Microsoft Teams, obtendrá enriquecido colaboración de contenido en línea en las reuniones que incluyen el uso compartido de audio, vídeo y contenido. Esto puede disfrutado a través del cliente web y de escritorio, así como a través de muchos dispositivos de socio que se integren de forma nativa con Microsoft Teams. Sin embargo, muchos clientes ya han invertido en teleconferencia por vídeo y dispositivos de comunicación de vídeo personal, que pueden ser costosos actualizar. Interoperabilidad de vídeo en la nube proporciona una solución sencilla, lo que le permite seguir usando las soluciones existentes hasta que esté listo para actualizar.

Con la interoperabilidad de vídeo en la nube, Microsoft Teams ofrece una experiencia de reuniones nativo para todos los participantes – en las salas de reuniones o dentro de los clientes de los equipos.

### <a name="is-cloud-video-interop-for-me"></a>¿Es la interoperabilidad de vídeo en la nube para mí?

Interoperabilidad de vídeo en la nube proporciona un servicio de nivel intermedio mientras realiza la transición a una solución completa nativa de los equipos de Microsoft, con los extremos de los equipos. El servicio proporcionado debe formar parte de la ruta de migración.

Interoperabilidad de vídeo en la nube está pensado para clientes que cumplan los siguientes criterios:

- Una implementación de gran tamaño de los dispositivos de la sala de la reunión y la implementación de los dispositivos de vídeo personal (más de 50 dispositivos) que no son compatibles con la integración directa con Microsoft Teams
- Son compatibles con uno de nuestros socios de interoperabilidad de vídeo en la nube
- Para conservar el valor de su inversión en su actual durante la migración a una solución de Microsoft Teams nativa de reunión dispositivos de sala y los dispositivos de vídeo personal

Mientras la interoperabilidad de vídeo en la nube proporciona una gran solución intermedia, le animamos a nuestros clientes para que busque en nuestras soluciones nativos de reunión de los equipos, como los equipos de los sistemas de sala, a largo plazo. 

### <a name="partners-certified-for-microsoft-teams"></a>Socios certificados para los equipos de Microsoft

Los siguientes socios tienen soluciones de interoperabilidad de vídeo para Microsoft Teams. Es posible que elija su compañía para que funcione con cualquier combinación de estos asociados de negocios de la empresa. 

|Socio|Solución de socio|
|----|---|
|![Polycom RealConnect](media/polycom.png) | <a href="https://aka.ms/PolycomRealConnect" target="_blank">Servicio de RealConnect de Polycom</a> |
|![Pexip infinito](media/pexip.png)| <a href="https://aka.ms/PexipInfinity" target="_blank">Infinito Pexip para los equipos de Microsoft</a> | 
|![Puerta de enlace de blueJeans](media/bluejeans.png)| <a href="https://aka.ms/BluejeansGateway" target="_blank">Puerta de enlace de blueJeans para los equipos de Microsoft</a> |

### <a name="cloud-video-interop-overview"></a>Introducción a la interoperabilidad de vídeo en la nube

Interoperabilidad de vídeo en la nube es un servicio de terceros que se ofrece por nuestros socios para proporcionar interoperabilidad entre soluciones de dispositivo de vídeo personal y conferencias de vídeo existente en local y Microsoft Teams.

Las soluciones de nuestros socios constan de los componentes que se pueden implementar totalmente en la nube en función o parcialmente o completamente en local. 
     
En el siguiente diagrama muestra la arquitectura de alto nivel de nuestro socio de soluciones.

![Solución de socio de interoperabilidad de vídeo en la nube de los equipos](media/teams-cloud-video-interop-partner-solution.png)


## <a name="deploy-cloud-video-interop"></a>Implementar la interoperabilidad de vídeo en la nube

Al implementar una solución de interoperabilidad de vídeo en la nube, es importante comprender que va a implementar una solución de socio. En el siguiente diagrama, se enumeran los pasos básicos que debe seguir para implementar la interoperabilidad de vídeo en la nube.

![Implementación de CVI en la organización](media/deploying-cvi.png)

### <a name="plan"></a>Planificar

Durante la fase de planeación, debe identificar los dispositivos que no reemplazar con un dispositivo nativo de los equipos y buscar a un socio de interoperabilidad de vídeo en la nube que puede admitir estos dispositivos.  

También es importante comprender que necesitará una licencia para cada usuario que va a programar reuniones en la que desee que un dispositivo habilitado para la interoperabilidad de vídeo en la nube para unirse a. Tenga en cuenta que los requisitos de licencia exactos pueden obtenerse desde el asociado de interoperabilidad de vídeo en la nube. Asegúrese de que está desactivada antes de empezar la implementación.

### <a name="configure"></a>Configuración

El socio que ha elegido para la implementación de CVI le proporcionará un documento de una implementación completa que se compone de todos los pasos necesarios para implementar correctamente dentro de la organización. Esto incluirá los puertos de firewall y rangos IP, los cambios de configuración para los dispositivos y otras opciones de configuración que se deben cambiar.

### <a name="provision"></a>Provisión  

Durante la fase de aprovisionamiento, va a asignar licencias a los usuarios adecuados según el socio Guía de configuración. También necesitará ir a través del proceso de consentimiento de Azure para proporcionar el acceso de socios para el entorno de los equipos. Aquí encontrará más información sobre el proceso de consentimiento de Azure:https://docs.microsoft.com/en-us/azure/active-directory/develop/v2-permissions-and-consent 

### <a name="schedule"></a>Programación

Después de que un usuario está habilitado para la interoperabilidad de vídeo en la nube, cualquier reunión programada con puede ser la reunión de los equipos complemento para Outlook o el cliente de los equipos tendrá la adecuada información adicional se agrega automáticamente en los equipos de la reunión lo que el vídeo en la nube Los dispositivos compatibles con interoperabilidad pueden unirse a estas reuniones.

### <a name="join"></a>Join

Dependiendo de la solución de socio, hay varias maneras para unirse a una reunión habilitado para la interoperabilidad de vídeo en la nube. Exacta de participación en la reunión, se proporcionará escenarios por su socio de interoperabilidad de vídeo en la nube. Presentamos algunos ejemplos que aparece a continuación:

- IVR (respuesta interactiva de voz) 
  - Puede marcar a IVR del socio con la tenantkey@domain.
  - Cuando se encuentre en el socio IVR, se le pedirá que lo especifique el conferenceId VTC, que, a continuación, se conectará a la reunión de los equipos.
- Marcado directo 
  - Puede marcar directamente en a la reunión de los equipos sin necesidad de interacción con IVR del socio mediante el uso de la característica de marcado directo, con la cadena completa de tenantkey. VTC ConferenceId@domain.
- Marcado con un solo toque 
  - Si tiene un salón de equipos integrado, puede usar las capacidades de acceso telefónico con un solo toque ofrecidas por su socio (sin necesidad de escribir cualquier cadena de marcado).

## <a name="manage-cloud-video-interop"></a>Administrar la interoperabilidad de vídeo en la nube

Una vez se haya implementado la interoperabilidad de vídeo en la nube, puede administrar los dispositivos con las soluciones proporcionadas por nuestros asociados de negocios. Cada socio proporcionará una interfaz de administración que se incluye la administración de licencias y el dispositivo. 

Creación de informes también está disponible directamente desde la interfaz administrativa de socio. Para obtener más información sobre las funcionalidades de informes, póngase en contacto con el socio de su elección. 

### <a name="troubleshooting-cloud-video-interop"></a>Solución de problemas de interoperabilidad de vídeo en la nube

Interoperabilidad de vídeo en la nube es un servicio proporcionados por los socios. Si experimenta problemas, el primer paso es conectar un dispositivo que tiene instalado el cliente de los equipos y conectarse al mismo segmento como el dispositivo de interoperabilidad de vídeo en la nube que está causando problemas. 

Si las funciones de los equipos correctamente en este segmento y también han seguido todas las instrucciones de redes y configuración que ha proporcionado el socio, debe ponerse en contacto con el socio para solucionar problemas. 

## <a name="powershell-for-cloud-video-interop"></a>PowerShell para la interoperabilidad de vídeo en la nube

Los cmdlets de PowerShell siguientes están disponibles para (parcialmente) automatizar la implementación de interoperabilidad de vídeo en la nube.

- **Get-CsTeamsVideoInteropServicepolicy**: Microsoft proporciona directivas construidas previamente para cada uno de nuestros socios compatibles que le permiten designar qué socios a usar para la interoperabilidad de vídeo en la nube.<br>Este cmdlet permite identificar las directivas construidas previa a la que pueden usar en su organización. Puede asignar esta directiva a uno o varios de los usuarios al aprovechar el cmdlet Grant-CsTeamsVideoInteropServicePolicy.
- **Grant CsTeamsVideoInteropServicePolicy**: este cmdlet permite asignar una directiva previamente construida para su uso en la organización o asignar la directiva a usuarios específicos.
- **New-CsVideoInteropServiceProvider**: Use este cmdlet para especificar la información acerca de un socio CVI compatible que su organización le gustaría usar.
- **Set-CsVideoInteropServiceProvider**: Use este cmdlet para actualizar la información sobre un socio CVI compatible que usa la organización.
- **Get-CsVideoInteropServiceProvider**: Use este cmdlet para obtener todos los proveedores que se han configurado para su uso dentro de la organización.
- **Remove-CsVideoInteropServiceProvider**: Use este cmdlet para quitar toda la información de proveedor acerca de un proveedor que ya no se usa la organización.
