---
title: Crear una transmisión en Microsoft Teams
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
description: En este artículo se describe cómo crear una transmisión para los eventos de streaming de Microsoft Teams.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.custom: ''
ms.openlocfilehash: b7ff5d15a08f186ae59ccef65fcd8280d84237d1
ms.sourcegitcommit: 0d25efb3dae31d5199807a14baaf30e944f561ce
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/11/2023
ms.locfileid: "69767994"
---
# <a name="create-a-live-event-in-microsoft-teams"></a>Crear un evento en directo en Microsoft Teams

> [!IMPORTANT]
> **China**: Actualmente, los usuarios ubicados en China no podrán configurar ni asistir a eventos en directo de Microsoft Teams o Yammer ni ver vídeos a petición sin la ayuda de su administrador de TI.
>
> Antes de empezar, póngase en contacto con su administrador para ver si necesita configurar una VPN para conectar su red corporativa de modo que estas aplicaciones puedan funcionar sin problemas en su organización.

> [!IMPORTANT]
> Al configurar un evento en directo, le recomendamos que configure los permisos de vídeo, comunidad y usuario al menos 24 horas antes del evento para obtener la mejor experiencia. Esto incluye opciones de configuración como agregar usuarios, actualizar los permisos de vídeo y cambiar una comunidad de privada a pública. Algunos cambios pueden tardar hasta dos (2) horas en propagarse por Microsoft Stream, Microsoft Teams y Microsoft Yammer. Permitir 24 horas o más puede proporcionar tiempo para probar y realizar ajustes si es necesario.

## <a name="schedule-the-live-event"></a>Programar el evento en directo

1. Abra el cliente de Microsoft Teams y vaya al calendario.
1. Use la lista desplegable **Nueva reunión** .
1. Seleccione la opción **Evento en directo** .
1. En la ventana emergente **Nuevo evento en directo** , escriba los detalles del evento a la izquierda (**Título**, **Ubicación**, **Inicio**, **Fin**, **Zona horaria** y **Detalles**).
1. En la misma página, a la derecha, **invite a los moderadores** a agregar moderadores y productores, ya sea de forma individual o a través de grupos.
1. Cuando todo esté escrito, selecciona **Siguiente**.
1. Seleccione **Personas y grupos**, **Toda la organización** o **Público** en **Permisos de eventos en** directo para especificar quién puede ver el evento en directo.
1. Seleccione **Codificador de Teams (versión preliminar)** en **¿Cómo producirá el evento en directo**?
1. Configure las opciones necesarias, como **Q&A**, **Títulos** y otros en **Opciones de evento**.
1. Seleccione **Programación** para completar la programación del evento en directo.

## <a name="stream-the-live-event"></a>Hacer streaming del evento en directo

1. Una vez que programe el evento en directo, puede recuperar la **url de ingestión del servidor RTMP** y la **clave RTMP** en la sección **Detalles** del calendario de la invitación, que puede utilizar para insertar el contenido del codificador a través de la ingestión de RTMP.
1. Para configurar el codificador, copie la dirección URL de entrada RTMP y la clave RTMP en el codificador para empezar a enviar la fuente del codificador en directo a Team. El uso de un codificador para el streaming en directo en Microsoft Teams tiene más información.
1. Con un cliente de Microsoft Teams, únase al evento en directo como productor. También puede encontrar RTMP En detalles, encontrará más detalles > Opciones de reunión.
1. Cuando empieces a insertar contenido desde el codificador al punto de ingestión del servidor, deberías ver la actualización de vista previa del productor.
1. Cuando estés satisfecho con la configuración y puedas ver la vista previa en la interfaz de usuario del productor, selecciona la **fuente RTMP** de fuentes y **Enviar en directo**.
1. Seleccione **Iniciar evento** para iniciar el evento en directo y publique qué miembros de la audiencia pueden ver el evento.
1. Cuando hayas terminado con el evento, selecciona **Finalizar evento** en la interfaz de usuario del productor. Esto finaliza el evento y hace que el contenido esté inmediatamente disponible para vídeo a petición.

Para obtener más información sobre cómo hacer streaming del evento en directo, consulte [Producir un evento en directo con el codificador de Teams](https://support.microsoft.com/office/produce-a-teams-live-event-using-teams-encoder-b0026c9d-fd37-4bb3-bffc-6961f221fbe9).
