---
title: Supervisar y mejorar la calidad de las llamadas de Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: Serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: vkorlep, siunies
description: Use la configuración de Calidad de servicio (QoS) y, a continuación, análisis de llamadas y panel de calidad de llamadas en Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 107bbf867c410a556e02d76eb991cf5f04730efa
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "46587659"
---
# <a name="monitor-and-improve-call-quality-for-microsoft-teams"></a>Supervisar y mejorar la calidad de las llamadas de Microsoft Teams

Este artículo presenta tres herramientas clave que puede usar para supervisar, solucionar problemas, administrar y mejorar la calidad de las llamadas en Microsoft Teams. 

- **Panel de calidad de llamadas:** para analizar problemas o tendencias de toda la organización, mejore el rendimiento

- **Análisis de llamadas:** Para analizar la calidad de las llamadas y reuniones de usuarios individuales

- **Calidad de servicio (QoS): para** priorizar el tráfico de red importante



## <a name="monitor-and-troubleshoot-call-quality"></a>Supervisar y solucionar problemas de calidad de llamadas
Usará análisis de llamadas  por  usuario y panel de calidad de llamadas para buscar y solucionar problemas de calidad de llamadas que se encuentren durante el funcionamiento en curso. Esto le permite mejorar el rendimiento en toda la red. Ambas herramientas se encuentran en el Centro de administración de Teams.

 - **El análisis de** llamadas muestra información detallada sobre los  ***dispositivos,*** redes y conectividad relacionados con llamadas y reuniones específicas para cada usuario de Teams. El administrador de Teams y los agentes del departamento de soporte técnico usarán esta información para solucionar problemas de conexión y calidad de la llamada en una llamada específica. Para obtener más información, lea [Configurar análisis de llamadas y](set-up-call-analytics.md) Usar Análisis de llamadas para solucionar problemas de mala calidad de las [llamadas.](use-call-analytics-to-troubleshoot-poor-call-quality.md)
 
 - **El panel de calidad de llamadas (CQD)** proporciona ***una*** vista de la calidad de las llamadas en toda la organización. Use la información del CQD para ayudarle a identificar y solucionar problemas. En primer [lugar, configure el CQD.](turning-on-and-using-call-quality-dashboard.md) A continuación, lea [Administrar la calidad de las llamadas y reuniones en Teams.](quality-of-experience-review-guide.md)

 El análisis de llamadas y el CQD se ejecutan en paralelo y se pueden usar de forma independiente o conjunta. Por ejemplo, si un especialista de soporte técnico de comunicaciones determina que necesita más ayuda para solucionar el problema de llamada de un usuario, escala la llamada a un ingeniero de soporte técnico de comunicaciones, que tiene acceso a información adicional sobre la llamada. A su vez, el ingeniero de soporte técnico de comunicaciones alerta a un ingeniero de red de un posible problema relacionado con el sitio que ha observado en el análisis de llamadas. El ingeniero de red comprueba el CQD para ver si un problema general relacionado con el sitio puede ser una causa colaborativo del problema de llamada del usuario.


## <a name="prioritize-important-network-traffic-using-qos"></a>Priorizar el tráfico de red importante con QoS
Cuando los usuarios empiezan a usar Teams para llamadas y reuniones, es posible que experimente que la voz de la persona que llama se separa o corta y sale de una llamada o reunión. El vídeo compartido se puede inmovilizar, pixelar o fallar. Esto se debe a los paquetes de IP que representan el tráfico de voz y vídeo que detecta congestión de red y que llega fuera de la secuencia o no en absoluto. Si esto sucede (o para evitar que esto suceda en primer lugar), use **QoS (Calidad de servicio).** 

Con QoS, se da prioridad al tráfico de red con más retraso (por ejemplo, las transmisiones de voz o vídeo), lo que permite "cortar en línea" frente al tráfico que sea menos confidencial (como la descarga de una nueva aplicación, donde un segundo adicional para descargar no es demasiado importante). QoS identifica y marca todos los paquetes en transmisiones en tiempo real mediante objetos de directiva de grupo de Windows y una característica de enrutamiento denominada Listas de control de acceso basadas en puertos, que indica a su red que dé voz, vídeo y uso compartido de pantalla a su propio ancho de banda de red dedicado.

Lo ideal es que implemente QoS en su red interna mientras se prepara para implementar Teams, pero puede hacerlo en cualquier momento. Si es lo bastante pequeño, es posible que no necesite QoS.

Cuando esté listo, lea Implementar [calidad de servicio (QoS) en Microsoft Teams.](QoS-in-Teams.md)

Para usar QoS para administrar el tráfico de reuniones, lea Configurar cómo desea controlar el tráfico multimedia en tiempo [real para las reuniones de Teams.](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)


## <a name="related-topics"></a>Temas relacionados

[Configurar análisis de llamadas](set-up-call-analytics.md)

[Usar el Análisis de llamadas para solucionar problemas de mala calidad en las llamadas](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Configurar el CQD](turning-on-and-using-call-quality-dashboard.md)

[Administrar la calidad de las llamadas y reuniones en Teams](quality-of-experience-review-guide.md)

[Solución de problemas de Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)

