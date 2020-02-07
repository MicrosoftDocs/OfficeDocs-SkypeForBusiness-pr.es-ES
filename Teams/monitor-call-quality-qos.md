---
title: Implementar QoS y supervisar los análisis de llamadas en Microsoft Teams
author: jambirk
ms.author: jambirk
manager: Serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: jambirk
description: Use la configuración de calidad de servicio (QoS) y, a continuación, análisis de llamadas y panel de calidad de llamadas en Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8899316d24616bf61918b93c9edd7118b89f5347
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41832680"
---
# <a name="implement-qos-and-monitor-call-quality-in-microsoft-teams"></a>Implementar QoS y supervisar la calidad de las llamadas en Microsoft Teams

## <a name="get-started"></a>Introducción

A medida que los usuarios comiencen a usar Teams para hacer llamadas y celebrar reuniones, es posible que experimenten la voz de la persona que chopping o salga de una llamada o una reunión. El vídeo compartido puede bloquearse o Pixelizar o fallar por completo. Esto se debe a que los paquetes IP que representan el tráfico de voz y vídeo encontraban la congestión de la red y llegar fuera de secuencia o no. Hay formas de identificar estos problemas cuando se muestran y evitan su regreso, principalmente calidad de servicio (QoS).

**Calidad de servicio (QoS)** es una forma de permitir el tráfico de red en tiempo real (como las transmisiones de voz o vídeo) que es sensible a los retrasos de red para "cortar en línea" frente al tráfico menos sensible (como descargar una nueva aplicación, donde un extra adicional para descargar no es una gran oferta). QoS identifica y marca todos los paquetes en las transmisiones en tiempo real con objetos de directiva de grupo de Windows y una característica de enrutamiento denominada listas de control de acceso basado en puertos, que ayuda a la red a proporcionar a las transmisiones de voz, vídeo y compartir pantalla sus propias partes dedicadas de ancho de banda de red.

 Por el momento, simplemente indicaremos que es muy parecido a enviar una carta a través del correo electrónico: Si envías tarifas de libros de ti, llega muy pronto y eso es lo suficientemente bueno, si lo envíos por primera vez, se obtiene una gran velocidad y si envías el correo con prioridad , entra en un plazo de dos días. De las redes de cursos se ejecutan más rápido que el correo, pero sigue funcionando, pero sí que la velocidad es crítica para algunas aplicaciones y no es tan importante para otros. Este tema es intrínsecamente detallado y complicado de comprender al principio, pero tiene una enorme diferencia en la experiencia del usuario, por lo que merece la pena invertir tiempo y energía al frente. Lea [implementar calidad de servicio (QoS) en Microsoft Teams](QoS-in-Teams.md) para obtener una explicación más detallada.

Idealmente, implementaría QoS en la red interna al configurar Teams, pero si es lo suficientemente pequeño puede ser opcional. Esto permite que el tráfico de voz y vídeo con retraso en la demoras se priorice antes que otro tráfico. Debe realizar esta priorización en todos los [dispositivos cliente](QoS-in-Teams-clients.md), en el [centro de administración de Microsoft Teams](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings), así como en los conmutadores y enrutadores de su red.

El [**Panel de análisis de llamadas y el panel de calidad de llamadas**](difference-between-call-analytics-and-call-quality-dashboard.md) se usan para buscar y solucionar problemas que surjan durante la operación en curso.  

El **análisis de llamadas** muestra información detallada sobre los dispositivos, las redes y la conectividad relacionada con ***llamadas y reuniones específicas*** para cada usuario en una cuenta de Microsoft Teams o Skype empresarial. Si es administrador de Office 365, puede usar análisis de llamadas para solucionar problemas de calidad de llamadas y de conexión experimentados en una llamada específica. Esto puede ayudarte a identificar y eliminar problemas.

El **Panel de calidad de llamadas (CQD)** está diseñado para ayudar a los administradores e ingenieros de red a optimizar su ***red***, no a analizar y solucionar una sola llamada. El CQD pasa el foco de usuarios específicos para mirar la información agregada de toda una organización. Esto también puede ayudarte a identificar y eliminar problemas.

## <a name="related-topics"></a>Temas relacionados

[Implementar calidad de servicio (QoS) en Microsoft Teams](QoS-in-Teams.md)

[Vídeo: información general sobre la calidad de las llamadas](https://aka.ms/teams-quality)

[Configurar el Análisis de llamadas](set-up-call-analytics.md)

[Usar el Análisis de llamadas para solucionar problemas de mala calidad en las llamadas](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Activar y usar paneles de calidad de llamadas](turning-on-and-using-call-quality-dashboard.md)

[Dimensiones y medidas disponibles en el Panel de calidad de llamadas](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Clasificación de la secuencia en el Panel de calidad de llamadas](stream-classification-in-call-quality-dashboard.md)