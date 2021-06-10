---
title: Supervisar y mejorar la calidad de las llamadas Microsoft Teams
author: SerdarSoysal
ms.author: serdars
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
ms.openlocfilehash: 62e687de154fadffd6ac95bd628fec6f9454cc51
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51162680"
---
# <a name="monitor-and-improve-call-quality-for-microsoft-teams"></a>Supervisar y mejorar la calidad de las llamadas Microsoft Teams

En este artículo se presentan tres herramientas clave que puede usar para supervisar, solucionar problemas, administrar y mejorar la calidad de las llamadas en Microsoft Teams. 

- **Panel de calidad de llamadas (CQD):** Para analizar las tendencias o problemas de toda la organización, mejore el rendimiento

- **Análisis de llamadas:** Para analizar la calidad de las llamadas y reuniones para usuarios individuales

- **Calidad de servicio (QoS): Para** priorizar el tráfico de red importante



## <a name="monitor-and-troubleshoot-call-quality"></a>Supervisar y solucionar problemas de calidad de llamadas
Usará análisis de llamadas  por  usuario y panel de calidad de llamadas para buscar y solucionar problemas de calidad de llamadas que se den durante el funcionamiento en curso. Esto le permite mejorar el rendimiento en toda la red. Ambas herramientas se encuentran en el centro Teams administración.

 - **El análisis de** llamadas muestra información detallada sobre los **_dispositivos,_** redes y conectividad relacionados con llamadas y reuniones específicas para cada usuario en Teams. Teams administradores y agentes de soporte técnico usarán esta información para solucionar problemas de conexión y calidad de llamadas en una llamada específica. Para obtener más información, lea [Configurar análisis de llamadas](set-up-call-analytics.md) y Usar Análisis de llamadas para solucionar problemas de mala calidad de las [llamadas.](use-call-analytics-to-troubleshoot-poor-call-quality.md)
 
 - **El Panel de calidad de llamadas (CQD)** le ofrece **_una_** vista en toda la red de la calidad de las llamadas en toda la organización. Use la información de CQD para ayudarle a identificar y solucionar problemas. En primer lugar, [Configurar CQD](turning-on-and-using-call-quality-dashboard.md). A continuación, lea Administrar la calidad de la llamada [y la reunión en Teams](quality-of-experience-review-guide.md).

 Los análisis de llamadas y CQD se ejecutan en paralelo y se pueden usar de forma independiente o conjunta. Por ejemplo, si un especialista en soporte técnico de comunicaciones determina que necesita más ayuda para solucionar el problema de llamada de un usuario, escala la llamada a un ingeniero de soporte técnico de comunicaciones, que tiene acceso a información adicional sobre la llamada. A su vez, el ingeniero de soporte técnico de comunicaciones alerta a un ingeniero de red de un posible problema relacionado con el sitio que han observado en el análisis de llamadas. El ingeniero de red comprueba CQD para ver si un problema general relacionado con el sitio podría ser una causa que contribuye al problema de llamada del usuario.


## <a name="prioritize-important-network-traffic-using-qos"></a>Priorizar el tráfico de red importante con QoS
A medida que los usuarios comienzan a usar Teams llamadas y reuniones, es posible que experimente que la voz de un autor de la llamada se separa o corta y sale de una llamada o reunión. El vídeo compartido puede inmovilizarse, pixelar o fallar por completo. Esto se debe a que los paquetes IP que representan el tráfico de voz y vídeo encuentran congestión de red y llegan fuera de la secuencia o no en absoluto. Si esto ocurre (o para evitar que esto suceda en primer lugar), use Calidad de servicio **(QoS).** 

Con QoS, prioriza el tráfico de red sensible al retraso (por ejemplo, transmisiones de voz o vídeo), lo que le permite "cortar en línea" frente al tráfico que es menos sensible (como descargar una nueva aplicación, donde un segundo adicional para descargar no es un gran problema). QoS identifica y marca todos los paquetes en transmisiones en tiempo real con objetos de directiva de grupo de Windows y una característica de enrutamiento denominada Listas de control de acceso basadas en puertos, que indica a su red que dé voz, vídeo y pantalla compartida con su propio ancho de banda de red dedicado.

Lo ideal es implementar QoS en su red interna mientras se prepara para implementar Teams, pero puede hacerlo en cualquier momento. Si es lo suficientemente pequeño, es posible que no necesite QoS.

Cuando esté listo, lea [Implementar calidad de servicio (QoS) en Microsoft Teams](QoS-in-Teams.md).

Para usar QoS para administrar el tráfico de reuniones, lea Establecer cómo desea controlar el tráfico multimedia en tiempo [real para Teams reuniones.](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)


## <a name="related-topics"></a>Temas relacionados

[Configurar análisis de llamadas](set-up-call-analytics.md)

[Usar el Análisis de llamadas para solucionar problemas de mala calidad en las llamadas](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Configurar CQD](turning-on-and-using-call-quality-dashboard.md)

[Administrar la calidad de las llamadas y las reuniones en Teams](quality-of-experience-review-guide.md)

[Solución de problemas de Teams](/MicrosoftTeams/troubleshoot/teams)