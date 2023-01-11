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
description: En este artículo se trata la configuración RTMP basada en codificadores para los eventos de streaming de Microsoft Teams.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: 8fd5feffe328083d9e7d5fa6e14cdbdac2ae5ffc
ms.sourcegitcommit: 0d25efb3dae31d5199807a14baaf30e944f561ce
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/11/2023
ms.locfileid: "69767984"
---
# <a name="configuring-encoders-for-live-event-streaming-in-microsoft-teams"></a>Configurar codificadores para el streaming de eventos en directo en Microsoft Teams

Teams acepta fuentes en directo de una variedad de codificadores diferentes que generan RTMP o RTMPS. Cada codificador es diferente, así que asegúrese de seguir las instrucciones para las configuraciones del codificador al enviar a Teams.

Para obtener información sobre cómo configurar un evento en directo en Teams, lea acerca de cómo crear eventos en directo. Si ya está usando un codificador que está integrado con Teams, lea acerca de [la configuración de codificadores para la transmisión en directo](teams-encoder-setup.md).

## <a name="configuration-steps"></a>Pasos de configuración

Después de programar el evento en directo con Teams o Yammer y seleccionar la opción **Codificador de Teams** , podrá recuperar la dirección URL y la clave RTMP de la invitación a la reunión y usarlas para enviar la fuente a la interfaz de usuario del productor de Teams.

### <a name="gather-the-rtmp-information"></a>Recopilar la información rtmp

#### <a name="scheduled-in-teams"></a>Programado en Teams

1. Abra el cliente de Teams y vaya al **Calendario**.
1. Selecciona el evento en directo programado y selecciona el botón de flecha doble para ver los detalles de la invitación.
1. Vaya abajo al **RTMP en la sección de detalles** .
1. Seleccione el vínculo **Obtener RTMP** para copiar la dirección URL de ingestión rtmp en el portapapeles.
1. Seleccione la **tecla Obtener RTMP** para copiar la tecla RTMP en el Portapapeles.

#### <a name="scheduled-in-yammer"></a>Programado en Yammer

1. Vaya a la comunidad de Yammer donde se programó el evento.
1. Seleccione la pestaña **Eventos** para ver los próximos eventos programados.
1. Seleccione el evento deseado para que aparezca la página de detalles.
1. En el lado derecho, en **Producir**, seleccione el vínculo de **información RTMP** para exponer la dirección URL y la clave RTMP.

## <a name="encoder-setup"></a>Configuración del codificador

1. Una vez que hayas recopilado la información de RTMP, asegúrate de que el codificador esté configurado con la configuración correcta según la configuración recomendada del codificador a continuación.
1. Escribe la dirección URL rtmp y la clave en la configuración de streaming del codificador (consulta la documentación del fabricante para obtener detalles específicos).
1. Configura el codificador con las fuentes de audio y vídeo deseadas.
1. Abra el cliente de Teams y únase al conducto de ventilación en directo como productor.
1. Inicie el streaming desde el codificador a la dirección URL de entrada RTMP de Teams.
1. En la ventana Productor de Teams, después de unos segundos, la fuente RTMP del codificador aparecerá en el área de moderador.
1. Haga clic en la fuente RTMP del área del moderador para colocarla en la cola del lado izquierdo.
1. Cuando estés satisfecho con la fuente, selecciona **Enviar en directo** : la fuente también aparecerá en el lado derecho de la ventana Productor.
1. Selecciona **Inicio** para iniciar la transmisión.

## <a name="recommended-encoder-settings"></a>Configuración recomendada del codificador

### <a name="ingest-protocols"></a>Ingerir protocolos

- Velocidad de bits única RTMPS o RTMP

### <a name="video-format"></a>Formato de vídeo

- Códec: H.264
- Perfil: Alto (Nivel 4.0)
- Velocidad de bits: hasta 5 Mbps (5000 kbps)
- Bitrate constante estricto (CBR)
- Fotograma clave/GOP: 2 segundos
  - Debe haber una trama IDR al principio de cada GOP
  - Velocidad de fotogramas: 29,97 fps o 30 fps
  - Resolución: 1280 x 720 (720P)
  - Modo interlace: Progresivo

### <a name="audio-format"></a>Formato de audio

- Códec: AAC (LC)
- Velocidad de bits: 192 kbps
- Velocidad de muestra: 48 kHz o 44,1 kHz (se recomienda 48 kHz)

### <a name="playback-requirements"></a>Requisitos de reproducción

- Tanto una transmisión de audio como de vídeo deben estar presentes para reproducir contenido en Teams.

### <a name="configuration-tips"></a>Sugerencias de configuración

- Siempre que sea posible, utilice una conexión a Internet cableada.
- Al determinar los requisitos de ancho de banda es duplicar las velocidades de transmisión por secuencias de bits. Aunque no es un requisito obligatorio, ayudará a mitigar el impacto de la congestión de la red.
- Al usar codificadores basados en software, cierra los programas innecesarios.
- No cambies la configuración del codificador después de que se haya iniciado la inserción. Tiene efectos negativos en el evento y puede hacer que el evento sea inestable. Si desea hacer esto antes de que se inicie el evento, debe desconectarse usando los controles del productor en Teams y volver a iniciar la configuración.
- Si el codificador se desconecta durante el evento en directo, vuelve a conectarlo manteniendo las mismas marcas de tiempo para continuar con el proceso. Cualquier interrupción puede causar problemas de audio o vídeo en determinados exploradores y dispositivos.
- Dedícate tiempo suficiente para configurar el evento. Para eventos a gran escala, se recomienda iniciar la configuración una hora antes del evento.
