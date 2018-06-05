---
title: Habilitar o deshabilitar la mensajería instantánea (MI) para usuarios desconectados en Skype Empresarial Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 6/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c0f44352-fb4a-45d3-85b0-a4320d4b8339
description: Aprenda a habilitar o deshabilitar sin conexión mensajería instantánea (mi) en Skype para Business Server 2015.
ms.openlocfilehash: 46adfbea2e3164944d9670310819d3ae46d8d07c
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569815"
---
# <a name="enable-or-disable-offline-instant-messaging-im-in-skype-for-business-server-2015"></a>Habilitar o deshabilitar la mensajería instantánea (MI) para usuarios desconectados en Skype Empresarial Server 2015
 
Aprenda a habilitar o deshabilitar sin conexión mensajería instantánea (mi) en Skype para Business Server 2015.
  
## <a name="enable-offline-instant-messaging-im-in-skype-for-business-server-2015"></a>Habilitar la mensajería instantánea sin conexión (mi) en Skype para Business Server 2015

Mensajería instantánea sin conexión es una característica del lado cliente integrada en Skype para Business client (2016 C2R crear 16.0.6701.1000 o superior) que aprovecha los servicios Web de Exchange (EWS) para enviar mensajes desde el Skype para clientes empresariales al buzón de Exchange de un usuario. Desconectado mensajería instantánea utiliza Exchange Web Services (EWS) para enviar mensajes sin conexión desde el Skype para clientes empresariales para el buzón de correo del destinatario. EWS debe estar disponibles para el Skype para el cliente de negocio para enviar los mensajes sin conexión. Para obtener más información acerca de la planeación para mensajería instantánea y presencia, consulte [Plan para mensajería instantánea y presencia en Skype para Business Server 2015](../../plan-your-deployment/instant-messaging-and-presence.md).
  
> [!NOTE]
> Si el buzón del usuario está hospedado en Exchange local, se requiere la Skype para Business client (2016 C2R compilación 16.0.6920.1000) 
  
### <a name="to-enable-or-disable-offline-im-in-skype-for-business-server-2015-with-cu3"></a>Para habilitar o deshabilitar sin conexión de mensajería instantánea en Skype para Business Server 2015 con CU3

1. Abra el Skype para Shell de administración de servidor empresarial.
    
2. Ejecute el siguiente comando para habilitar la MI sin conexión.
    
   ```
   Set-CsImConfiguration -EnableOfflineIM $True
   ```

    > [!NOTE]
    > En Skype para Business Server 2015 CU3, la opción EnableOfflineIM se establece en $True de forma predeterminada. Para deshabilitarla, defina este valor en $False. 
  
3. Ejecute el siguiente comando para confirmar que se establece la capacidad de almacenar sin conexión mensajería instantánea.
    
   ```
   Get-CsImConfiguration
   ```

## <a name="offline-im-integration-with-exchange"></a>Integración de MI sin conexión con Exchange

La MI sin conexión no estará disponible para los remitentes si disponen de una directiva que deshabilita el guardado automático de los mensajes sin conexión en la carpeta de historial de conversaciones (EnableIMAutoArchiving = $false). No existe ningún mecanismo para comprobar si el destinatario puede recibir mensajes sin conexión.
  
Para los mensajes sin conexión enviados dentro de la misma organización se recibirá como un mensaje de correo electrónico con la clase de mensaje de mensajería instantánea. Note.MissedConversation y se incluirá en la carpeta de Outlook **Conversaciones perdidas** , así como el historial de conversaciones que se recogen en la ficha reciente de historial de conversación y lista de Skype para clientes empresariales.
  
Los mensajes sin conexión enviados desde una organización federada se recibirán como un mensaje de correo electrónico sin IM.Note.MisssedConversation y no se podrán recuperar en las carpetas de conversación perdida o historial de conversaciones. 
  
## <a name="troubleshooting"></a>Solución de problemas

Hay un temporizador de dos minutos de cuando se envía un mensaje sin conexión para cuando recogida y procesan. Si no se puede procesar los mensajes sin conexión aparecen en el siguiente directorio: 
  
  <pre>  %localappdata%\microsoft\office\16.0\lync\SipUserAddress\History Spooler   </pre>

La principal Skype para registro de ETL empresarial contendrá información sobre el procesamiento del mensaje sin conexión y es la mejor fuente para la investigación y solución de problemas. 
  
> [!NOTE]
> Se ha informado de un problema en que los mensajes sin conexión no lograban enviarse y la carpeta Borradores se llenaba de mensajes. Este problema se producía en buzones de correo de Exchange local y se ha corregido en todos los canales C2R a fecha del 14/6/2016.  