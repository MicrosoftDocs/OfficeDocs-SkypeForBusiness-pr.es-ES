---
title: Habilitar o deshabilitar la mensajería instantánea sin conexión (mi) en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c0f44352-fb4a-45d3-85b0-a4320d4b8339
description: Aprenda a habilitar o deshabilitar la mensajería instantánea sin conexión (mi) en Skype empresarial Server.
ms.openlocfilehash: 77078b6092dc1d23dde1315c505c5baf26798b86
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34289710"
---
# <a name="enable-or-disable-offline-instant-messaging-im-in-skype-for-business-server"></a>Habilitar o deshabilitar la mensajería instantánea sin conexión (mi) en Skype empresarial Server
 
Aprenda a habilitar o deshabilitar la mensajería instantánea sin conexión (mi) en Skype empresarial Server.
  
## <a name="enable-offline-instant-messaging-im-in-skype-for-business-server"></a>Habilitar la mensajería instantánea (mi) sin conexión en Skype empresarial Server

La mensajería instantánea sin conexión es una característica del lado cliente incorporada en el cliente de Skype empresarial (2016 C2R compilación 16.0.6701.1000 o superior) que aprovecha los servicios Web de Exchange (EWS) para enviar mensajes desde el cliente de Skype empresarial al buzón de Exchange de un usuario. La mensajería instantánea sin conexión usa los servicios web Exchange (EWS) para enviar mensajes sin conexión desde el cliente de Skype empresarial hasta el buzón de correo del destinatario. EWS debe estar disponible para que el cliente de Skype empresarial pueda enviar mensajes sin conexión. Para obtener más información sobre cómo planear la mensajería instantánea y la presencia, consulte [planear la mensajería instantánea y la presencia en Skype empresarial Server](../../plan-your-deployment/instant-messaging-and-presence.md).
  
> [!NOTE]
> Si el buzón del usuario se hospeda en Exchange local, el cliente de Skype empresarial (2016 C2R compilación 16.0.6920.1000) es necesario 
  
### <a name="to-enable-or-disable-offline-im-in-skype-for-business-server"></a>Para habilitar o deshabilitar la mensajería instantánea sin conexión en Skype empresarial Server

1. Abra el shell de administración de Skype empresarial Server.
    
2. Ejecute el siguiente comando para habilitar la MI sin conexión.
    
   ```
   Set-CsImConfiguration -EnableOfflineIM $True
   ```

    > [!NOTE]
    > En Skype empresarial Server 2015 CU3, la opción EnableOfflineIM se establece en $True de forma predeterminada. Para deshabilitarla, defina este valor en $False. 
  
3. Ejecute el siguiente comando para confirmar la capacidad de almacenar los mensajes instantáneos sin conexión.
    
   ```
   Get-CsImConfiguration
   ```

## <a name="offline-im-integration-with-exchange"></a>Integración de MI sin conexión con Exchange

La MI sin conexión no estará disponible para los remitentes si disponen de una directiva que deshabilita el guardado automático de los mensajes sin conexión en la carpeta de historial de conversaciones (EnableIMAutoArchiving = $false). No existe ningún mecanismo para comprobar si el destinatario puede recibir mensajes sin conexión.
  
Para los mensajes sin conexión enviados dentro de la misma organización se recibirán como un mensaje de correo electrónico con la clase de mensaje de mensajería instantánea. Note. MissedConversation y se incluirá en la carpeta de **conversaciones perdidas** de Outlook, así como en el historial de conversaciones, que se recogerá en la ficha de la lista de elementos recientes/historial de conversaciones en los clientes de Skype empresarial.
  
Los mensajes sin conexión enviados desde una organización federada se recibirán como un mensaje de correo electrónico sin IM.Note.MisssedConversation y no se podrán recuperar en las carpetas de conversación perdida o historial de conversaciones. 
  
## <a name="troubleshooting"></a>Solución de problemas

Hay un temporizador de dos minutos desde que se envía un mensaje sin conexión al momento en que se selecciona y se procesa. Si los mensajes sin conexión no se pueden procesar, aparecerán en el siguiente directorio: 
  
  <pre>  %localappdata%\microsoft\office\16.0\lync\SipUserAddress\History Spooler   </pre>

El registro ETL principal de Skype empresarial contendrá información sobre el procesamiento de mensajes sin conexión y es la mejor fuente de investigación y solución de problemas. 
  
> [!NOTE]
> Se ha informado de un problema en que los mensajes sin conexión no lograban enviarse y la carpeta Borradores se llenaba de mensajes. Este problema se producía en buzones de correo de Exchange local y se ha corregido en todos los canales C2R a fecha del 14/6/2016.   
