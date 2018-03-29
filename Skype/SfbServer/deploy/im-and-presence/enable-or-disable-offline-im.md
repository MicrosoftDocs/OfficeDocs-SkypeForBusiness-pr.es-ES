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
ms.openlocfilehash: a9133ad82e4d25fae2aebd266273ecbb37c2a010
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="enable-or-disable-offline-instant-messaging-im-in-skype-for-business-server-2015"></a>Habilitar o deshabilitar la mensajería instantánea (MI) para usuarios desconectados en Skype Empresarial Server 2015
 
Aprenda a habilitar o deshabilitar sin conexión mensajería instantánea (mi) en Skype para Business Server 2015.
  
## <a name="enable-offline-instant-messaging-im-in-skype-for-business-server-2015"></a>Habilitar la mensajería instantánea sin conexión (IM) en Skype para Business Server 2015

Mensajería instantánea sin conexión es una característica de lado cliente integrada en Skype para Business client (2016 C2R generar 16.0.6701.1000 o superior) que aprovecha Exchange Web Services (EWS) para enviar mensajes desde el Skype para Business client al buzón de Exchange del usuario. Sin conexión IM utiliza Exchange Web Services (EWS) para enviar mensajes sin conexión desde el Skype para Business client en el buzón del destinatario. EWS deben estar disponibles para el Skype para el cliente de negocios para enviar mensajes sin conexión. Para más información acerca de cómo planear la presencia y mensajería instantánea, consulte [Plan para mensajería instantánea y presencia en Skype para Business Server 2015](../../plan-your-deployment/instant-messaging-and-presence.md).
  
> [!NOTE]
> Si el buzón del usuario está alojado en Exchange local, se requiere el Skype para Business client (C2R de 2016 compilación 16.0.6920.1000) 
  
### <a name="to-enable-or-disable-offline-im-in-skype-for-business-server-2015-with-cu3"></a>Para habilitar o deshabilitar sin conexión IM en Skype para Business Server 2015 con CU3

1. Abra el Skype para el Shell de administración de servidor empresarial.
    
2. Ejecute el siguiente comando para habilitar la MI sin conexión.
    
   ```
   Set-CsImConfiguration -EnableOfflineIM $True
   ```

    > [!NOTE]
    > En Skype para Business Server 2015 CU3, la opción EnableOfflineIM se establece en $True predeterminada. Para deshabilitarla, defina este valor en $False. 
  
3. Ejecute el siguiente comando para confirmar que se establece la capacidad de almacenar sin conexión del primero.
    
   ```
   Get-CsImConfiguration
   ```

## <a name="offline-im-integration-with-exchange"></a>Integración de MI sin conexión con Exchange

La MI sin conexión no estará disponible para los remitentes si disponen de una directiva que deshabilita el guardado automático de los mensajes sin conexión en la carpeta de historial de conversaciones (EnableIMAutoArchiving = $false). No existe ningún mecanismo para comprobar si el destinatario puede recibir mensajes sin conexión.
  
Sin conexión mensajes enviados dentro de la misma organización se recibirá como un mensaje de correo electrónico con la clase de mensaje de mensajería instantánea. Note.MissedConversation y se incluirá en la carpeta Outlook **Conversación perdida** , así como el historial de las conversaciones que se recogen en la ficha de historial de conversación y lista reciente de Skype para clientes empresariales.
  
Los mensajes sin conexión enviados desde una organización federada se recibirán como un mensaje de correo electrónico sin IM.Note.MisssedConversation y no se podrán recuperar en las carpetas de conversación perdida o historial de conversaciones. 
  
## <a name="troubleshooting"></a>Solución de problemas

Hay un temporizador de dos minutos de cuando se envía un mensaje sin conexión para cuando haya recogido y procesado. Si no se puede procesar los mensajes sin conexión aparecen en el directorio siguiente: 
  
   ```
  %localappdata%\microsoft\office\16.0\lync\SipUserAddress\History Spooler
  ```

El principal Skype para registro de ETL empresariales contendrá información sobre el procesamiento de mensajes sin conexión y es la mejor fuente para la investigación y solución de problemas. 
  
> [!NOTE]
> Se ha informado de un problema en que los mensajes sin conexión no lograban enviarse y la carpeta Borradores se llenaba de mensajes. Este problema se producía en buzones de correo de Exchange local y se ha corregido en todos los canales C2R a fecha del 14/6/2016.  
  

