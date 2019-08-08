---
title: Interoperabilidad de vídeos en la nube para Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: srividhc
description: La interoperabilidad de vídeo en nube permite que los dispositivos de la sala de reuniones de terceros participen en reuniones de Microsoft Teams.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4d37acef498abfd0ed3e9125529abef38f737406
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36237076"
---
# <a name="cloud-video-interop-for-microsoft-teams"></a>Interoperabilidad de vídeos en la nube para Microsoft Teams

La interoperabilidad de vídeo en nube (CVI) es una solución de terceros calificada por Microsoft que permite a las salas de reuniones de terceros (TelePresence) y a los dispositivos de vídeo personal (VTCs) unirse a las reuniones de Microsoft Teams.
 
Con Microsoft Teams, obtendrá una rica colaboración de contenido en línea en las reuniones que incluyen audio, vídeo y uso compartido de contenido. Esto se puede disfrutar a través del escritorio y del cliente web, así como con muchos dispositivos asociados que se integran de forma nativa con Microsoft Teams. Sin embargo, muchos clientes ya han invertido en videoconferencias y dispositivos de comunicación de video personal, que pueden ser caros de actualizar. La interoperabilidad de vídeo en la nube ofrece una solución sencilla, que le permite seguir usando sus soluciones existentes hasta que esté listo para la actualización.

Con la interoperabilidad de vídeo en la nube, Microsoft Teams ofrece una experiencia de reunión nativa para todos los participantes, en salas de reuniones o dentro de clientes de Teams.

### <a name="is-cloud-video-interop-for-me"></a>¿Es la interoperabilidad de video en la nube?

La interoperabilidad de vídeo en la nube proporciona un servicio intermedio mientras se pasa a una solución nativa completa de Microsoft Teams con los puntos de conexión de Teams. El servicio proporcionado debe formar parte de la ruta de migración.

La interoperabilidad de vídeo en la nube está destinada a clientes que cumplen los siguientes criterios:

- Realizar una implementación grande de los dispositivos de la sala de reuniones y la implementación de dispositivos de vídeo personales (más de 50 dispositivos) que no están capacitadas para la integración directa con Microsoft Teams
- Son compatibles con uno de nuestros socios de interoperabilidad de video en la nube
- Desea conservar el valor de su inversión en sus dispositivos actuales de la sala de reuniones y en los dispositivos de vídeo personales durante la migración a una solución nativa de Microsoft Teams

Aunque la interoperabilidad de vídeo en la nube ofrece una excelente solución intermedia, recomendamos a nuestros clientes que examinen nuestras soluciones de reuniones nativas de equipos, como los sistemas de salas de equipos, a largo plazo. 

### <a name="partners-certified-for-microsoft-teams"></a>Socios certificados para Microsoft Teams

Los siguientes Partners tienen soluciones de interoperabilidad de video para Microsoft Teams. Tu empresa puede elegir trabajar con cualquier combinación de estos socios dentro de tu empresa. 

|Servidor|Solución de socio|
|----|---|
|![El logotipo representa la RealConnect de Polycom](media/polycom.png) | <a href="https://aka.ms/PolycomRealConnect" target="_blank">Servicio RealConnect de Polycom</a> |
|![El logotipo representa infinito de Pexip](media/pexip.png)| <a href="https://aka.ms/PexipInfinity" target="_blank">Pexip Infinity para Microsoft Teams</a> | 
|![El logotipo representa la puerta de enlace de BlueJeans](media/bluejeans.png)| <a href="https://aka.ms/BluejeansGateway" target="_blank">Puerta de enlace de BlueJeans para Microsoft Teams</a> |

### <a name="cloud-video-interop-overview"></a>Introducción a la interoperabilidad de vídeo en nube

La interoperabilidad de vídeo en nube es un servicio de terceros ofrecido por nuestros socios para proporcionar interoperabilidad entre las soluciones de videoconferencias existentes y las soluciones de dispositivos de video personales locales y Microsoft Teams.

Las soluciones que ofrecen nuestros socios son componentes que se pueden implementar totalmente en la nube o de forma parcial o completa. 
     
En el siguiente diagrama se muestra la arquitectura de alto nivel de nuestros socios de soluciones.

![Diagrama que describe una solución de socio de interoperabilidad de vídeo en la nube de Teams](media/teams-cloud-video-interop-partner-solution.png)


## <a name="deploy-cloud-video-interop"></a>Implementar interoperabilidad de vídeo en la nube

Al implementar una solución de interoperabilidad de vídeo en la nube, es importante comprender que está implementando una solución de socio. Los pasos generales que debe seguir para implementar la interoperabilidad de vídeo en la nube se enumeran en el siguiente diagrama.

![Diagrama que describe cómo implementar CVI en su organización](media/deploying-cvi.png)

### <a name="plan"></a>Plan

Durante la fase de planeación, debe identificar los dispositivos que no va a reemplazar con un dispositivo nativo de equipo y encontrar un asociado de interoperabilidad de video interoperabilidad de nube que pueda admitir estos dispositivos.  

También es importante comprender que necesitará una licencia para cada usuario que programe reuniones en las que desea que se unan un dispositivo con la interoperabilidad de nube habilitada. Tenga en cuenta que los requisitos de licencias exactos se pueden obtener del socio de interoperabilidad de vídeo en la nube. Asegúrese de que está claro antes de empezar a implementar.

### <a name="configure"></a>Configuración

El partner que ha elegido para su implementación de CVI le proporcionará un documento de implementación completo que consta de todos los pasos necesarios para implementar correctamente en su organización. Esto incluirá los puertos de Firewall e intervalos IP, los cambios de configuración para los dispositivos y otras opciones de configuración que deben cambiar.

### <a name="provision"></a>Aprovisionar  

Durante la fase de provisión, asignará licencias a los usuarios adecuados de acuerdo con la guía de configuración del partner. También tendrá que pasar por el proceso de consentimiento de Azure para proporcionar al asociado acceso al entorno de su equipo. Puede encontrar más información sobre el proceso de consentimiento de Azure aquí:https://docs.microsoft.com/en-us/azure/active-directory/develop/v2-permissions-and-consent 

### <a name="schedule"></a>Programa

Una vez que un usuario está habilitado para la interoperabilidad de vídeo en la nube, cualquier reunión programada con el complemento de reunión de equipos para Outlook o el cliente de equipos tendrá la información adicional adecuada para agregar automáticamente a la reunión de Teams, de modo que el video de nube Los dispositivos compatibles con la interoperabilidad pueden unirse a estas reuniones.

### <a name="join"></a>Join

En función de la solución asociada, hay varias maneras de unirse a una reunión habilitada para la interoperabilidad de vídeo en la nube. Su socio de interoperabilidad de video en la nube proporcionará escenarios de combinación de reuniones exactas. A continuación se muestran algunos ejemplos:

- IVR (respuesta interactiva de voz) 
  - Puede llamar al IVR del socio mediante el dominio tenantkey @.
  - Cuando se encuentre en el IVR de socio, se le pedirá que introduzca el VTC conferenceId, que le conectará a la reunión de Teams.
- Marcado directo 
  - Puede llamar directamente a la reunión de Teams sin interactuar con el IVR del socio mediante la característica de marcado directo, usando la cadena completa de tenantkey. VTC ConferenceId @ dominio.
- Marcación sencilla 
  - Si tiene una sala de equipos integrada, puede usar las funciones de marcado con un solo toque que le ofrece su partner (sin necesidad de escribir ninguna cadena de marcado).

## <a name="manage-cloud-video-interop"></a>Administrar la interoperabilidad de vídeo en la nube

Después de implementar la interoperabilidad de vídeo en la nube, puede administrar los dispositivos con las soluciones proporcionadas por nuestros socios. Cada socio le proporcionará una interfaz administrativa que incluirá tanto la administración de licencias como la de dispositivos. 

Los informes también están disponibles directamente desde la interfaz administrativa del socio. Para obtener más información sobre las capacidades de informes, póngase en contacto con el socio de su elección. 

### <a name="troubleshooting-cloud-video-interop"></a>Solución de problemas de interoperabilidad de vídeo en la nube

La interoperabilidad de vídeo en la nube es un servicio proporcionado por el socio. Si tiene problemas, el primer paso consiste en conectar un dispositivo que tiene el cliente del equipo instalado y conectarlo al mismo segmento que el dispositivo de interoperabilidad de nube que causa los problemas. 

Si Teams funciona correctamente en este segmento y también ha seguido todas las directrices de redes y de configuración que el socio haya proporcionado, tendrá que ponerse en contacto con él para obtener más información. 

## <a name="powershell-for-cloud-video-interop"></a>PowerShell para interoperabilidad de vídeo en la nube

Los siguientes cmdlets de PowerShell están disponibles para que pueda (parcialmente) automatizar la implementación de interoperabilidad de vídeo en la nube.

- **Get-CsTeamsVideoInteropServicepolicy**: Microsoft proporciona directivas preconstruidas para cada uno de nuestros socios compatibles que le permiten designar qué asociados usar para la interoperabilidad de vídeo en la nube.<br>Este cmdlet le permite identificar las directivas preconstruidas que puede usar en su organización. Puede asignar esta directiva a uno o más de sus usuarios aprovechando el cmdlet Grant-CsTeamsVideoInteropServicePolicy.
- **Grant-CsTeamsVideoInteropServicePolicy**: este cmdlet le permite asignar una directiva preconstruida para su uso en su organización o asignar la Directiva a usuarios específicos.
- **New-CsVideoInteropServiceProvider**: Use este cmdlet para especificar información sobre un partner de CVI admitido que su organización desearía usar.
- **Set-CsVideoInteropServiceProvider**: Use este cmdlet para actualizar la información sobre un partner de CVI admitido que use su organización.
- **Get-CsVideoInteropServiceProvider**: Use este cmdlet para obtener todos los proveedores que se han configurado para su uso dentro de la organización.
- **Remove-CsVideoInteropServiceProvider**: Use este cmdlet para quitar toda la información del proveedor sobre un proveedor que ya no usa su organización.
