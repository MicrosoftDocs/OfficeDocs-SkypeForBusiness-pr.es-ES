---
title: Supervisar y mejorar la calidad de las llamadas de Microsoft Teams
author: lolajacobsen
ms.author: lolaj
manager: Serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: vkorlep, siunies
description: Use la configuración de calidad de servicio (QoS) y, a continuación, análisis de llamadas y panel de calidad de llamadas en Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 2d5db11bbd9608aebb1eb2b73ebacc9793629e44
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085940"
---
# <a name="monitor-and-improve-call-quality-for-microsoft-teams"></a>Supervisar y mejorar la calidad de las llamadas de Microsoft Teams

Este artículo presenta tres herramientas clave que puede usar para supervisar, solucionar problemas, administrar y mejorar la calidad de las llamadas en Microsoft Teams. 

- **Panel de calidad de llamadas (CQD)**: para analizar las tendencias o problemas de toda la organización, impulsar las mejoras en el rendimiento

- **Análisis de llamadas**: para analizar la calidad de la llamada y de la reunión para usuarios individuales

- **Calidad de servicio (QoS)**: para priorizar el tráfico de red importante



## <a name="monitor-and-troubleshoot-call-quality"></a>Supervisar y solucionar problemas de calidad de llamadas
Usará el panel de análisis de **llamadas** por usuario y el **Panel de calidad de llamadas** para buscar y solucionar problemas de calidad de llamadas que surjan durante la operación en curso. Esto le permite impulsar las mejoras de rendimiento en toda la red. Ambas herramientas se encuentran en el centro de administración de Teams.

 - El **análisis de llamadas** muestra información detallada sobre los dispositivos, las redes y la conectividad relacionada con ***llamadas y reuniones específicas*** para cada usuario de Teams. Los agentes de administración y Helpdesk de equipos usarán esta información para solucionar problemas de calidad de llamadas y de conexión en una llamada específica. Para obtener más información, lea [configurar análisis de llamadas](set-up-call-analytics.md) y [usar análisis de llamadas para solucionar problemas de baja calidad de las llamadas](use-call-analytics-to-troubleshoot-poor-call-quality.md).
 
 - El **Panel de calidad de llamadas (CQD)** le ofrece una ***vista en toda la red*** de la calidad de las llamadas en toda la organización. Use información del CQD para ayudarle a identificar y solucionar problemas. En primer lugar, [Configure el CQD](turning-on-and-using-call-quality-dashboard.md). A continuación, vea [administrar la calidad de las llamadas y reuniones en Teams](quality-of-experience-review-guide.md).

 El análisis de llamadas y el CQD se ejecutan en paralelo y se pueden usar de forma independiente o conjunta. Por ejemplo, si un especialista de soporte técnico de comunicaciones determina que necesita más ayuda para solucionar el problema de las llamadas de un usuario, puede transferir la llamada a un ingeniero de soporte de comunicaciones, que tiene acceso a información adicional sobre la llamada. A su vez, el ingeniero de soporte técnico de comunicaciones alerta a un ingeniero de red para un posible problema relacionado con el sitio que se observó en el análisis de llamadas. El ingeniero de red comprueba el CQD para ver si un problema general relacionado con el sitio puede ser una causa de que el usuario haya contribuido.


## <a name="prioritize-important-network-traffic-using-qos"></a>Priorizar el tráfico de red importante con QoS
A medida que los usuarios comiencen a usar Teams para realizar llamadas y reuniones, es posible que experimenten la voz de la persona que llama o se corta y sale de una llamada o una reunión. El vídeo compartido puede bloquearse o Pixelizar o fallar por completo. Esto se debe a que los paquetes IP que representan el tráfico de voz y vídeo encontraban la congestión de la red y llegar fuera de secuencia o no. Si esto sucede (o para evitar que suceda en primer lugar), use **calidad de servicio (QoS)**. 

Con QoS, se prioriza el tráfico de red sensible al retraso (por ejemplo, las transmisiones de voz o de vídeo), lo que permite "cortar en línea" frente al tráfico menos sensible (como descargar una nueva aplicación, donde un extra adicional que descargar no es una gran oferta). QoS identifica y marca todos los paquetes en las transmisiones en tiempo real con objetos de directiva de grupo de Windows y una característica de enrutamiento denominada listas de control de acceso basado en puertos, que indica a su red que proporcione voz, vídeo y pantalla para compartir su propio ancho de banda de red dedicado.

Idealmente, implementará la calidad de servicios QoS en su red interna y estará listo para distribuir equipos, pero puede hacerlo en cualquier momento. Si es lo suficientemente pequeño, es posible que no necesite QoS.

Cuando esté listo, lea [implementar calidad de servicio (QoS) en Microsoft Teams](QoS-in-Teams.md).

Para usar QoS para administrar el tráfico de la reunión, lea [establecer cómo desea controlar el tráfico de medios en tiempo real de las reuniones de Teams](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings).


## <a name="related-topics"></a>Temas relacionados

[Configurar análisis de llamadas](set-up-call-analytics.md)

[Usar el Análisis de llamadas para solucionar problemas de mala calidad en las llamadas](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Configurar el CQD](turning-on-and-using-call-quality-dashboard.md)

[Administrar la calidad de las llamadas y reuniones en Teams](quality-of-experience-review-guide.md)

[Solución de problemas de Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)

