---
title: Implementar QoS y análisis de la llamada de Monitor en los equipos de Microsoft
author: jambirk
ms.author: MyAdvisor
manager: Serdars
ms.topic: article
ms.service: msteams
ms.reviewer: jambirk
description: Use la configuración de calidad de servicio (QoS) y, a continuación, llame al análisis y panel de calidad de llamadas de Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: d0f82a546057558cc6c69c9c0de19bc9ccb021cd
ms.sourcegitcommit: 788e3526ff973454f3904c33d867691a2fae814f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2019
ms.locfileid: "28328181"
---
# <a name="implement-qos-and-monitor-call-quality-in-microsoft-teams"></a>Implementar QoS y calidad de la llamada Monitor en los equipos de Microsoft

## <a name="get-started"></a>Empezar a trabajar

Como los usuarios empiecen a usar los equipos para realizar llamadas y mantiene las reuniones, es posible que encuentre altavoces separación SAI (UPS) o cortar dentro y fuera de una llamada o una reunión. Vídeo compartido puede inmovilizar o pixellate, o se producirá un error por completo. Esto es debido a los paquetes IP que representan la voz y vídeo tráfico encontrar congestión de la red y que llega fuera de la secuencia o no en absoluto. Existen formas para evitarlo e identificar otros problemas cuando extraen, principalmente calidad de servicio (QoS).

[**Calidad de servicio (QoS)**](monitor-call-quality-qos.md) es una forma de identificar los paquetes que son sensibles a los retrasos y congestión y, a continuación, proporcione los paquetes con tratamiento preferente, por lo que se encuentre mucho menos congestión. Por ahora, sólo mencionaremos que lo es muy parecido a enviar una carta por correo electrónico: si lo envía tasa de libro existe obtiene muy pronto y que es lo suficientemente bueno, si lo envía primera clase existe obtiene mucho más rápido, y si lo envía correo de prioridad , obtiene existe dentro de dos días. Por supuesto redes ejecutan con más rapidez que el correo, pero aún ejecuta true que la velocidad es fundamental para algunas aplicaciones y no es tan importante para que otros usuarios. Este tema es esencialmente detallada y difícil de comprender al principio, pero hace que sea una gran diferencia en el usuario de experiencia, por lo que tiene la pena invertir tiempo y energía por adelantado.

Lo ideal sería implementar QoS en su red interna durante la configuración de seguridad de los equipos, pero si es pequeña suficientemente puede ser opcional. Esto permite la voz de retraso confidenciales y el tráfico de vídeo para obtener prioriza antes que otro tráfico. Esto hace esta priorización en todos los dispositivos de cliente, así como en los conmutadores y enrutadores en la red.

[**Análisis de llamadas y panel de calidad de llamadas**](difference-between-call-analytics-and-call-quality-dashboard.md) se usan para encontrar y solucionar los problemas que surgen durante la operación en curso.  

Análisis de la llamada muestran información detallada acerca de los dispositivos, redes y conectividad relacionadas con las llamadas específicas y las reuniones para cada usuario en un Microsoft Teams o Skype para la cuenta de empresa. Si usted es un administrador de Office 365, puede usar el análisis de llamadas para solucionar problemas de calidad y conexión de llamada tuvo en una llamada concreta. Esto puede ayudarle a identificar y solucionar los problemas.

Panel de calidad de llamada (CQD) está diseñado para ayudar a los administradores y los ingenieros de red optimización una **red**, no a analizar y solucionar problemas de una sola llamada. CQD cambia el foco de determinados usuarios a mirar información agregada para toda la organización. Esto también puede ayudar a identificar y solucionar los problemas.

## <a name="related-topics"></a>Temas relacionados

[Implementar QoS para equipos de Microsoft](monitor-call-quality-qos.md)

[Configurar el análisis de llamadas](set-up-call-analytics.md)

[Usar Análisis de llamadas para solucionar problemas de mala calidad de llamada](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Activar y con el panel de calidad de llamadas](turning-on-and-using-call-quality-dashboard.md)

[Dimensiones y medidas disponibles en el Panel de calidad de llamadas](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Clasificación de la transmisión en el panel de calidad de llamadas](stream-classification-in-call-quality-dashboard.md)