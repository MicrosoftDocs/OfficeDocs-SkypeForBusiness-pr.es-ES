---
title: Informe de uso y rendimiento de Walkie Talkie
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: admin
ms.topic: article
ms.service: microsoft-365-frontline
ms.reviewer: prastogi
f1.keywords:
- NOCSH
ms.localizationpriority: high
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365-frontline
- highpri
- tier2
description: Obtenga información sobre cómo usar el informe de rendimiento y uso de Walkie Talkie en el Centro de administración de Microsoft Teams para obtener información general sobre la actividad de uso de Walkie Talkie en su organización.
appliesto:
- Microsoft Teams
- Microsoft 365 for frontline workers
ms.openlocfilehash: 85f92e715efe2b9608691151a08d006816658095
ms.sourcegitcommit: 776820a6c927fafabdfad9f50654fe7648d77bf3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/20/2023
ms.locfileid: "69846059"
---
# <a name="walkie-talkie-usage-and-performance-report"></a>Informe de uso y rendimiento de Walkie Talkie

El informe de rendimiento y uso de Walkie Talkie del Centro de administración de Microsoft Teams le ofrece información general sobre la actividad de [Walkie Talkie](../walkie-talkie.md) en su organización. El informe proporciona información como el número de transmisiones push-to-talk (PTT) realizadas y recibidas, la actividad del canal, la duración de la transmisión y los detalles del dispositivo y los participantes.

Use este informe para obtener información sobre las tendencias de uso y el rendimiento de Walkie Talkie en su organización. Para acceder al informe, debe ser administrador global, administrador de Teams, lector global o lector de informes.

## <a name="download-and-view-the-report"></a>Descargar y ver el informe

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, elija **Análisis & informes** > **de uso**. En la pestaña **Ver informes** , en **Informe**, seleccione **Uso de Walkie Talkie**.
1. En **Intervalo de fechas**, seleccione un intervalo de fechas de 7 días o 30 días. Después, elija **Ejecutar informe**.
1. Seleccione **Generar informe**.
1. En la pestaña **Descargas** , en **Estado**, elija **Descargar** para descargar el informe en formato CSV.

## <a name="interpret-the-report"></a>Interpretar el informe

El informe proporciona un desglose de cada transmisión realizada durante el intervalo de fechas que ha seleccionado. Esta es la información que se incluye en el informe.

|Nombre de columna |Descripción |
|---------|---------|
|Id. de inquilino|Id. de inquilino.|
|Userid|Id. de usuario.|
|Deviceid|Id. de dispositivo.|
|ChannelId|El canal Walkie-talkie en el que se produce la comunicación.|
|clientCallStatus | Indica si el dispositivo pudo recibir la transmisión sin ningún problema.|
|ConversationId|Id. de cada transmisión PTT.|
|Id. de equipo|Identificador del equipo que corresponde al canal Walkie Talkie al que se conecta el usuario.|
|UnreachableParticipantsCount|Número de participantes marcados como no accesibles y ocultos de la lista porque no pudieron recibir ninguna de las cinco últimas transmisiones.|
|TransmissionDuration|Duración del tiempo (en milisegundos) entre el momento en que el servicio recibe la notificación de que un participante está a punto de iniciar una transmisión a la que el servicio entrega el último paquete de dicha transmisión.|
|TotalParticipantsCount|Número total de participantes conectados al canal Walkie Talkie.|
|PacketCount|Número de paquetes utilizados para enviar la transmisión de audio.|
|Participantes notificados|Los participantes a los que se envía una notificación push cuando se inicia una transmisión. En situaciones en las que se pierde la conexión entre el dispositivo y el servicio, se envía una notificación al dispositivo para restablecer la conexión lo antes posible porque se produce una transmisión.|
|AudioDurationMilliseconds|Duración de la transmisión en milisegundos.|
|ConnectionId|Identificador de cada conexión a un canal Walkie Talkie que establece el dispositivo.|
|TransmissionStartTime |Fecha y hora en que el servicio recibe el primer paquete de audio.
|TransmissionEndTime|Fecha y hora en que el servicio recibe el último paquete de audio.|
|Lista de participantes|Una lista delimitada por puntos y comas de los identificadores de los dispositivos conectados al canal en el momento en que se envía la transmisión.|
|CallTimedOut|Si la transmisión superó el límite de duración. Este es un valor booleano.|
|Plataforma|Sistema operativo del dispositivo.|
|ParticipantType|Si el participante era el transmisor o un receptor de la transmisión.|
|WebState|Si el estado de la conexión entre el dispositivo y el servicio ya estaba establecido cuando se inició la transmisión.|
|AppVersion|Versión de la aplicación teams instalada en el dispositivo.|

## <a name="related-articles"></a>Artículos relacionados

- [Aplicación Walkie Talkie en Teams](../walkie-talkie.md)
- [Introducción al Walkie Talkie](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)