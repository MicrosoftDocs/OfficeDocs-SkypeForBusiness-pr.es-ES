---
title: Configuración del codificador para el streaming en Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: asteele
search.appverid: MET150
f1.keywords:
- NOCSH
description: En este artículo se trata la configuración rtmp basada en codificadores para eventos de streaming de Microsoft Teams.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: 8a31b8b0de30367401c998d17dbf59ea06fc5687
ms.sourcegitcommit: 0d25efb3dae31d5199807a14baaf30e944f561ce
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/11/2023
ms.locfileid: "69767985"
---
# <a name="using-an-encoder-for-live-streaming-in-microsoft-teams"></a>Usar un codificador para el streaming en directo en Microsoft Teams

Los codificadores de Teams permiten a los usuarios producir eventos en directo directamente desde un codificador externo basado en software o hardware con Microsoft Teams.

## <a name="overview"></a>Información general

Un codificador toma contenido de audio y vídeo de varias fuentes que usas durante un evento en directo, como una cámara, un micrófono, una captura de pantalla de escritorio, etc. Comprime y convierte ese medio en un formato digital adecuado y, a continuación, lo envía a Teams para su streaming en directo a su audiencia. Consulte nuestra [guía de producción personalizada](https://aka.ms/CustomProductionVEP) para obtener más información sobre cómo puede usar las tecnologías de producción de Teams (como NDI) con codificadores externos.

## <a name="production-workflow-when-using-an-encoder"></a>Flujo de trabajo de producción al usar un codificador

El flujo de trabajo para producir un evento en directo de Teams es el siguiente:

Se programa un evento en directo en Teams o Yammer y se selecciona la opción **Codificador de Teams** . Esto aprovisiona un punto final RTMP, que se proporciona con una DIRECCIÓN URL RTMP y la clave correspondiente. El codificador usa la dirección URL y la clave para conectarse al punto de conexión RTMP para el evento en directo programado.

### <a name="common-encoders-user-with-live-events"></a>Usuarios comunes de codificadores con eventos en directo

Microsoft ha probado los codificadores de las dos listas siguientes para hacer streaming en directo con Teams. La primera lista es un subconjunto de estos codificadores, que se han probado con el producto para facilitar su uso y una configuración rápida.

#### <a name="stream-ready-encoders"></a>Codificadores listos para Stream

|Codificador                                |Sitio web  |Detalles  |
|---------------------------------------|---------|---------|
|Haivision                              |[Haivision Makito X](https://www.haivision.com/microsoft/stream) |Ofrece vídeo HD de alta calidad con Haivision Hub, una potente alternativa a RTMP. |
|Haivision                              |[Haivision KB](https://www.haivision.com/microsoft/stream) |Los codificadores de vídeo H.264 y HEV ofrecen cascadas de vídeo ABR de alta calidad para resoluciones de hasta 4K. |
|Open Broadcaster Software (OBS Studio) |[Abrir software de radiodifusión](https://obsproject.com/) |Captura y mezcla de vídeo y audio en tiempo real de alto rendimiento, lo que admite todas las plataformas de streaming y mucho más. |
|vMix                                   |[vMix](https://www.vmix.com/) |Mezclador de visión de software que controla la grabación, mezcla y streaming en vivo de cámaras, vídeos, audio y mucho más. |
|Wirecast                               |[Wirecast](https://www.telestream.net/wirecast) |Software de difusión web que cubre todos los conceptos básicos + producción multi-cámara. |
|Switcher Studio                        |[Switcher Studio](https://www.switcherstudio.com/microsoft-stream) |Sincroniza varios dispositivos Apple con una o más cámaras para la captura y edición de vídeo en tiempo real. |
|AWS Elemental Live                     |[AWS Elemental Live](https://www.elemental.com/products/aws-elemental-appliances-software/#elemental-live) |Grabación de vídeo y audio en tiempo real para streaming en vivo en dispositivos conectados a Internet |
|XSplit Broadcaster                     |[XSplit Broadcaster](https://www.xsplit.com/) |Produce, mezcla y ofrece contenido de vídeo enriquecido, incluido el juego para el streaming en directo. |
|Ffmpeg                                 |[Ffmpeg](https://ffmpeg.org/) |Conjunto de software de código abierto para manejar vídeo, audio y otros archivos multimedia y transmisiones en directo. |
|Camión de producción          |[Camión de producción](https://www.blueframetech.com/productiontruck) |Películas y transmisiones de eventos en el lugar desde una camioneta móvil o camión. |
|Productor de IA de Live Arena                 |Productor de IA |Estudio de producción integrado en Microsoft Teams como aplicación para reuniones.|
|StreamYard                             |StreamYard |Live streaming studio en el explorador.|
|Sociales                              |Sociales |Plataforma de producción de vídeo en la nube, que proporciona una experiencia todo en uno para producir y distribuir contenido de vídeo de calidad studio.|
|Brandlive                              |BrandLive |Plataforma de producción basada en la nube.|

### <a name="haivision-makito-x-encoder-and-makito-kb-encoder"></a>Haivision Makito X Encoder y Makito KB Encoder

Si tienes un codificador Haivision X o Makito KB existente, puedes elegir la opción adecuada en la lista desplegable y seguir la lista de instrucciones.

1. Selecciona **Iniciar configuración** para crear un canal de streaming en directo. Espere a que se complete la configuración. Verás un mensaje **Listo para conectar** en la pantalla.
1. Una vez completado, descargue el valor preestablecido que contiene todos los parámetros de codificación, incluidos la dirección URL de ingestión y el nombre del evento. Importe el valor preestablecido en el codificador e inicie el codificador.
1. Volver a Teams. Una vez que puedas ver la vista previa del codificador, selecciona **Iniciar evento** para que el público pueda ver el evento en directo.

> [!NOTE]
> El soporte de Haivision KB Encoder para RTMPS aún no se ha probado. Haivision Makito X Encoder no admite RTMPS. Los valores preestablecidos descargados para ambos codificadores contienen la dirección URL de entrada RTMP.

### <a name="switcher-studio"></a>Switcher Studio

Puede usar Switcher Studio para iniciar la transmisión a Teams con iPhone o iPad.

1. Selecciona **Iniciar configuración** para crear un canal de streaming en directo. Espere a que se complete la configuración. Verás un mensaje **Listo para conectar** en la pantalla.
2. Switcher Studio abrirá el panel de Switcher Studio para agregar el evento en directo a tu cuenta.

> [!NOTE]
> Si aún no tienes una cuenta de Switcher Studio, tendrás que crear una).

3. Cuando esto se haya completado, puede ir a la aplicación Switcher Studio en su iPhone o iPad, seleccionar Teams en la pestaña Salida e iniciar la transmisión a Teams.
4. Volver a Teams. Una vez que puedas ver la vista previa del codificador, selecciona **Iniciar evento** para que el público pueda ver el evento en directo.

> [!NOTE]
> Switcher Studio usa la dirección URL de entrada RTMP.

### <a name="wirecast"></a>Wirecast

Si es un usuario existente de Wirecast, puede elegir esta opción en la lista desplegable para enviar una transmisión en directo a Teams. Ten en cuenta que necesitarás la versión 10 o posterior de wirecast.

1. Selecciona **Iniciar configuración** para crear un canal de streaming en directo. Espere a que se complete la configuración. Verás un mensaje **Listo para conectar** en la pantalla.
1. El codificador iniciará la aplicación Wirecast en el equipo preconfigurado con los parámetros de codificación correctos y la dirección URL de ingestión para ese evento en directo. Cuando esté listo, haga clic en el icono de Teams en la aplicación Wirecast para iniciar la transmisión a Teams.
1. Volver a Teams. Una vez que puedas ver la vista previa del codificador, selecciona **Iniciar evento** para que el público pueda ver el evento en directo.

> [!NOTE]
> La aplicación Wirecast se inicia con la url de ingestión RTMPS preconfigurada.
