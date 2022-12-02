---
title: Supervisar y mejorar la calidad de las llamadas para Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: Serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: vkorlep, siunies
description: Use la configuración de calidad de servicio (QoS) y, después, haga clic en Análisis de llamadas y panel de calidad de llamadas en Microsoft Teams.
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 969fc5645023bfcf4ad2bc0aadfe692f61b350f0
ms.sourcegitcommit: aef1ab47fb9cb4502cb49bc3c7ffafcd62e54c82
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2022
ms.locfileid: "69245715"
---
# <a name="improve-call-quality-in-microsoft-teams"></a>Mejorar la calidad de las llamadas en Microsoft Teams

En este artículo se presentan tres herramientas clave que puede usar para supervisar, solucionar problemas, administrar y mejorar la calidad de las llamadas en Microsoft Teams. 

- **Panel de calidad de llamadas( CQD):** Para analizar las tendencias o problemas de toda la organización, impulse las mejoras en el rendimiento

- **Análisis de llamadas**: Para analizar la calidad de llamadas y reuniones de usuarios individuales

- **Calidad de servicio (QoS):** Priorizar el tráfico de red importante



## <a name="monitor-and-troubleshoot-call-quality"></a>Supervisar y solucionar problemas de calidad de llamadas
Usará análisis de **llamadas** por usuario y panel de **calidad de llamadas** para buscar y solucionar problemas de calidad de llamada que surjan durante el funcionamiento continuo. Esto te permite impulsar las mejoras de rendimiento en toda la red. Ambas herramientas se encuentran en el Centro de administración de Teams.

 - **Análisis de llamadas** muestra información detallada sobre los dispositivos, las redes y la conectividad  **_relacionadas con llamadas y reuniones específicas_** para cada usuario en Teams. El administrador de Teams y los agentes del departamento de soporte técnico usarán esta información para solucionar problemas de conexión y calidad de llamadas en una llamada específica. Para obtener más información, lea [Configurar análisis de llamadas](set-up-call-analytics.md) y [Usar análisis de llamadas para solucionar problemas de mala calidad de llamadas](use-call-analytics-to-troubleshoot-poor-call-quality.md).
 
 - **El Panel de calidad de llamadas (CQD)** le ofrece una **_vista de_** toda la red de la calidad de las llamadas en toda la organización. Use la información del CQD para ayudarle a identificar y corregir problemas. En primer lugar, [Configure el CQD](turning-on-and-using-call-quality-dashboard.md). Después, lea [Administrar la calidad de las llamadas y reuniones en Teams](quality-of-experience-review-guide.md).

 El análisis de llamadas y el CQD se ejecutan en paralelo y se pueden usar de forma independiente o conjunta. Por ejemplo, si un especialista en soporte técnico de comunicaciones determina que necesita más ayuda para solucionar el problema de llamada de un usuario, escalará la llamada a un ingeniero de soporte técnico de comunicaciones, que tiene acceso a información adicional sobre la llamada. A su vez, el ingeniero de soporte técnico de comunicaciones alerta a un ingeniero de red sobre un posible problema relacionado con el sitio que observaron en el análisis de llamadas. El ingeniero de red comprueba el CQD para ver si un problema general relacionado con el sitio podría ser una causa importante del problema de llamada del usuario.


## <a name="prioritize-important-network-traffic-using-qos"></a>Priorizar el tráfico de red importante con QoS
A medida que los usuarios empiezan a usar Teams para llamadas y reuniones, es posible que la voz del autor de la llamada se divida o se interroje y salga de una llamada o reunión. El vídeo compartido puede inmovilizarse o pixelarse, o fallar por completo. Esto se debe a que los paquetes IP que representan el tráfico de voz y vídeo que encuentra congestión de la red y que llegan fuera de la secuencia o no en absoluto. Si esto sucede (o para evitar que ocurra en primer lugar), use **Calidad de servicio (QoS)**. 

Con QoS, prioriza el tráfico de red sensible a retrasos (por ejemplo, las transmisiones de voz o vídeo), lo que le permite "cortar en línea" delante del tráfico que sea menos sensible (como descargar una nueva aplicación, donde descargar un segundo adicional no es importante). QoS identifica y marca todos los paquetes en secuencias en tiempo real mediante objetos de Windows directiva de grupo y una característica de enrutamiento denominada Listas de Access Control basadas en puertos, que indica a la red que proporcione a su red un ancho de banda dedicado propio de voz, vídeo y pantalla.

Lo ideal es que implemente QoS en su red interna mientras se prepara para implementar Teams, pero puede hacerlo en cualquier momento. Si es lo suficientemente pequeño, es posible que no necesite QoS.

Cuando esté listo, lea [Implementar calidad de servicio (QoS) en Microsoft Teams](QoS-in-Teams.md).

Para usar QoS para administrar el tráfico de las reuniones, lea [Establecer cómo desea controlar el tráfico multimedia en tiempo real para las reuniones de Teams](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings).


## <a name="related-topics"></a>Temas relacionados

[Configurar análisis de llamadas](set-up-call-analytics.md)

[Usar el Análisis de llamadas para solucionar problemas de mala calidad en las llamadas](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Configurar el CQD](turning-on-and-using-call-quality-dashboard.md)

[Administrar la calidad de las llamadas y reuniones en Teams](quality-of-experience-review-guide.md)

[Solución de problemas de Teams](/MicrosoftTeams/troubleshoot/teams)
