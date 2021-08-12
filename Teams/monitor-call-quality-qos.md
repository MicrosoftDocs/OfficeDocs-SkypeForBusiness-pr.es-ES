---
title: Supervisar y mejorar la calidad de las llamadas en Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: Serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: vkorlep, siunies
description: Use la configuración de calidad del servicio (QoS) y, a continuación, análisis de llamadas y panel de calidad de llamadas en Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: ed9bab3ad0cde91bc8faa4298956b07f73438e823e3e3c110ce09610fee5e7c0
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54286269"
---
# <a name="monitor-and-improve-call-quality-for-microsoft-teams"></a>Supervisar y mejorar la calidad de las llamadas en Microsoft Teams

En este artículo se presentan tres herramientas clave que puede usar para supervisar, solucionar problemas, administrar y mejorar la calidad de las llamadas en Microsoft Teams. 

- **Panel de calidad de llamadas (CQD):** para analizar las tendencias o problemas de toda la organización, mejore el rendimiento

- **Análisis de llamadas:** para analizar la calidad de llamadas y reuniones para usuarios individuales

- **Calidad del servicio (QoS): para** priorizar el tráfico de red importante



## <a name="monitor-and-troubleshoot-call-quality"></a>Supervisar y solucionar problemas de calidad de llamadas
Usará el análisis de  llamadas  por usuario y el Panel de calidad de llamadas para buscar y solucionar problemas de calidad de llamadas que se den durante el funcionamiento en curso. Esto le permite impulsar mejoras de rendimiento en toda la red. Ambas herramientas se encuentran en el centro Teams administración.

 - **El análisis de** llamadas muestra información detallada acerca **** de los dispositivos, redes y conectividad relacionados con llamadas y reuniones específicas para cada usuario de Teams. Teams administradores y agentes de soporte técnico usarán esta información para solucionar problemas de conexión y calidad de llamadas en una llamada específica. Para obtener más información, lea [Configurar análisis de llamadas](set-up-call-analytics.md) y Usar análisis de llamadas para solucionar problemas de mala calidad de la [llamada.](use-call-analytics-to-troubleshoot-poor-call-quality.md)
 
 - **El Panel de calidad de llamadas (CQD)** le ofrece una vista en toda **_la_** red de la calidad de las llamadas en toda la organización. Use la información de CQD para ayudarle a identificar y solucionar problemas. En primer [lugar, Configurar CQD](turning-on-and-using-call-quality-dashboard.md). A continuación, lea [Manage call and meeting quality in Teams](quality-of-experience-review-guide.md).

 El análisis de llamadas y CQD se ejecutan en paralelo y se pueden usar de forma independiente o conjunta. Por ejemplo, si un especialista en soporte técnico de comunicaciones determina que necesita más ayuda para solucionar el problema de llamada de un usuario, escala la llamada a un ingeniero de soporte técnico de comunicaciones, que tiene acceso a información adicional sobre la llamada. A su vez, el ingeniero de soporte técnico de comunicaciones alerta a un ingeniero de red sobre un posible problema relacionado con el sitio que notó en el análisis de llamadas. El ingeniero de red comprueba CQD para ver si un problema general relacionado con el sitio puede ser una causa que contribuye al problema de llamada del usuario.


## <a name="prioritize-important-network-traffic-using-qos"></a>Priorizar el tráfico de red importante mediante QoS
A medida que los usuarios comienzan a usar Teams para llamadas y reuniones, es posible que experimente que la voz de un autor de la llamada se separa o corta o sale de una llamada o reunión. El vídeo compartido puede inmovilizarse, pixelar o fallar por completo. Esto se debe a que los paquetes IP que representan el tráfico de voz y vídeo encuentran congestión de red y llegan fuera de la secuencia o no en absoluto. Si esto ocurre (o para evitar que suceda en primer lugar), use **Quality of Service (QoS)**. 

Con QoS, se prioriza el tráfico de red sensible al retraso (por ejemplo, secuencias de voz o vídeo), lo que le permite "cortar en línea" frente al tráfico que es menos confidencial (como descargar una nueva aplicación, donde un segundo adicional para descargar no es un gran problema). QoS identifica y marca todos los paquetes en secuencias en tiempo real mediante objetos de directiva de grupo de Windows y una característica de enrutamiento denominada Listas de control de acceso basadas en puertos, que indica a la red que dé voz, vídeo y pantalla para compartir su propio ancho de banda de red dedicado.

Idealmente, implementará QoS en la red interna mientras se prepara para implementar Teams, pero puede hacerlo en cualquier momento. Si es lo suficientemente pequeño, es posible que no necesite QoS.

Cuando esté listo, lea [Implementar calidad de servicio (QoS) en Microsoft Teams](QoS-in-Teams.md).

Para usar QoS para administrar el tráfico de reuniones, lea Establecer cómo desea controlar el tráfico multimedia en tiempo real para [Teams reuniones.](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)


## <a name="related-topics"></a>Temas relacionados

[Configurar los análisis de llamadas](set-up-call-analytics.md)

[Usar el Análisis de llamadas para solucionar problemas de mala calidad en las llamadas](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Configurar el CQD](turning-on-and-using-call-quality-dashboard.md)

[Administrar la calidad de llamadas y reuniones en Teams](quality-of-experience-review-guide.md)

[Solución de problemas de Teams](/MicrosoftTeams/troubleshoot/teams)