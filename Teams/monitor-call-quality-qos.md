---
title: Implementar QoS y supervisar los análisis de llamadas en Microsoft Teams
author: jambirk
ms.author: jambirk
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
ms.openlocfilehash: 097426e60ebcd141d1c8375343509db5607c50e2
ms.sourcegitcommit: ad126165b6440b98e550ab48e6b3491aeba9402b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/22/2019
ms.locfileid: "30205774"
---
# <a name="implement-qos-and-monitor-call-quality-in-microsoft-teams"></a>Implementar QoS y calidad de la llamada Monitor en los equipos de Microsoft

## <a name="get-started"></a>Empezar a trabajar

Como los usuarios empiecen a usar los equipos para realizar llamadas y mantiene las reuniones, pueden experimentar voz de un autor de la llamada dividir o cortar dentro y fuera de una llamada o reunión. Compartir vídeo pueden inmovilizados o Pixelizar, o se producirá un error por completo. Esto es debido a los paquetes IP que representan la voz y vídeo tráfico encontrar congestión de la red y que llega fuera de la secuencia o no en absoluto. Existen formas para identificar estos problemas cuando extraen y evitar que su retorno, principalmente calidad de servicio (QoS).

**Calidad de servicio (QoS)** es una forma para permitir el tráfico de red en tiempo real (por ejemplo, secuencias de voz o vídeo) que es sensible a retrasos en la red "recortar en línea" delante del tráfico que es menos sensible (como descargar una aplicación nueva, donde un segundo adicional para descargar no es muy importante). QoS identifica y marca todos los paquetes en secuencias en tiempo real mediante objetos de directiva de grupo de Windows y una característica de enrutamiento denominada puerto-based Access Control listas de, que, a continuación, ayuda a la red para proporcionar la voz, vídeo y compartir de pantalla secuencias sus propios partes dedicados de ancho de banda de red.

 Por ahora, sólo mencionaremos que lo es muy parecido a enviar una carta por correo electrónico: si lo envía tasa de libro existe obtiene muy pronto y que es lo suficientemente bueno, si lo envía primera clase existe obtiene mucho más rápido, y si lo envía correo de prioridad , obtiene existe dentro de dos días. Por supuesto redes ejecutan con más rapidez que el correo, pero aún ejecuta true que la velocidad es fundamental para algunas aplicaciones y no es tan importante para que otros usuarios. Este tema es esencialmente detallada y difícil de comprender al principio, pero hace que sea una gran diferencia en el usuario de experiencia, por lo que tiene la pena invertir tiempo y energía por adelantado. Lea [Implementar calidad de servicio (QoS) en los equipos de Microsoft](QoS-in-Teams.md) para obtener una descripción más detallada.

Lo ideal sería implementar QoS en su red interna durante la configuración de seguridad de los equipos, pero si es pequeña suficientemente puede ser opcional. Esto permite la voz de retraso confidenciales y el tráfico de vídeo para obtener prioriza antes que otro tráfico. Esto hace esta priorización en todos los [dispositivos de cliente](QoS-in-Teams-clients.md), en el [Centro de administración de equipos de Microsoft](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings), así como en los conmutadores y enrutadores en la red.

[**Análisis de llamadas y panel de calidad de llamadas**](difference-between-call-analytics-and-call-quality-dashboard.md) se usan para encontrar y solucionar los problemas que surgen durante la operación en curso.  

**Análisis de llamadas** muestra información detallada acerca de los dispositivos, redes y conectividad relacionados con ***las reuniones y llamadas específicas*** para cada usuario en un Microsoft Teams o Skype para la cuenta de empresa. Si usted es un administrador de Office 365, puede usar el análisis de llamadas para solucionar problemas de calidad y conexión de llamada tuvo en una llamada concreta. Esto puede ayudarle a identificar y solucionar los problemas.

**Panel de calidad de llamadas (CQD)** está diseñado para ayudar a los administradores y los ingenieros de red optimización su ***red***, no a analizar y solucionar problemas de una sola llamada. CQD cambia el foco de determinados usuarios a mirar información agregada para toda la organización. Esto también puede ayudar a identificar y solucionar los problemas.

## <a name="related-topics"></a>Temas relacionados

[Implementar la calidad de servicio (QoS) en los equipos de Microsoft](QoS-in-Teams.md)

[Vídeo: Información general de la calidad de llamada](https://aka.ms/teams-quality)

[Configurar el Análisis de llamadas](set-up-call-analytics.md)

[Usar el Análisis de llamadas para solucionar problemas de mala calidad en las llamadas](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Activar y usar paneles de calidad de llamadas](turning-on-and-using-call-quality-dashboard.md)

[Dimensiones y medidas disponibles en el Panel de calidad de llamadas](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Clasificación de la transmisión en el panel de calidad de llamadas](stream-classification-in-call-quality-dashboard.md)