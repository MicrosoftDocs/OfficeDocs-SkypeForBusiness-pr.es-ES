---
title: Habilitar o deshabilitar la mensajería instantánea sin conexión (MI) en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: c0f44352-fb4a-45d3-85b0-a4320d4b8339
description: Aprenda a habilitar o deshabilitar la mensajería instantánea sin conexión (MI) en Skype Empresarial Server.
ms.openlocfilehash: aace1ca45c224ce6ef6c7d6d6f151ecd3ab9b260
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60858637"
---
# <a name="enable-or-disable-offline-instant-messaging-im-in-skype-for-business-server"></a>Habilitar o deshabilitar la mensajería instantánea sin conexión (MI) en Skype Empresarial Server
 
Aprenda a habilitar o deshabilitar la mensajería instantánea sin conexión (MI) en Skype Empresarial Server.
  
## <a name="enable-offline-instant-messaging-im-in-skype-for-business-server"></a>Habilitar la mensajería instantánea sin conexión (MI) en Skype Empresarial Server

La mensajería instantánea sin conexión es una característica del lado cliente integrada en un cliente de Skype Empresarial (2016 C2R compilación 16.0.6701.1000 o posterior) que aprovecha Exchange Web Services (EWS) para enviar mensajes desde el cliente de Skype Empresarial al buzón de correo Exchange de un usuario. La mensajería instantánea sin conexión usa Exchange Web Services (EWS) para enviar mensajes sin conexión desde el Skype Empresarial cliente al buzón de correo del destinatario. EWS debe estar disponible para el Skype Empresarial para enviar mensajes sin conexión. Para obtener más información sobre la planeación de la mensajería instantánea y la presencia, vea [Plan for instant messaging and presence in Skype Empresarial Server](../../plan-your-deployment/instant-messaging-and-presence.md).
  
> [!NOTE]
> Si el buzón del usuario está hospedado en Exchange Local, se requiere el cliente de Skype Empresarial (compilación 16.0.6920.1000 de C2R de 2016) 
  
### <a name="to-enable-or-disable-offline-im-in-skype-for-business-server"></a>Para habilitar o deshabilitar la mensajería instantánea sin conexión en Skype Empresarial Server

1. Abra el Shell Skype Empresarial Server administración.
    
2. Ejecute el siguiente comando para habilitar la mensajería instantánea sin conexión.
    
   ```powershell
   Set-CsImConfiguration -EnableOfflineIM $True
   ```

    > [!NOTE]
    > En Skype Empresarial Server 2015 CU3, la opción EnableOfflineIM se establece en $True de forma predeterminada. Para deshabilitar, establezca este valor en $False. 
  
3. Ejecute el siguiente comando para confirmar que se ha establecido la capacidad de almacenar mensajería instantánea sin conexión.
    
   ```powershell
   Get-CsImConfiguration
   ```

## <a name="offline-im-integration-with-exchange"></a>Integración de mensajería instantánea sin conexión con Exchange

La mensajería instantánea sin conexión no estará disponible para los remitentes si tienen una directiva de cliente que deshabilita el guardado automático de mensajes sin conexión en la carpeta del historial de conversaciones (EnableIMAutoArchiving = $false). No hay ningún mecanismo para comprobar si el destinatario puede recibir mensajes sin conexión.
  
Para los mensajes sin conexión enviados **dentro** de la misma organización, se recibirán como un mensaje de correo electrónico con la clase de mensaje IM.Note.MissedConversa Outlook tion y se incluirán en una carpeta de conversación perdida, así como en el historial de conversaciones que se recogerá en la pestaña historial de listas o conversaciones recientes en clientes de Skype Empresarial.
  
Para los mensajes sin conexión enviados desde una organización federada, se recibirán como un mensaje de correo electrónico sin IM.Note.MisssedConversation y no se recogerán en las carpetas de historial de conversaciones o conversación perdidas. 
  
## <a name="troubleshooting"></a>Solución de problemas

Hay un temporizador de dos minutos desde que se envía un mensaje sin conexión a cuando se recoge y se procesa. Si los mensajes sin conexión no se pueden procesar, aparecerán en el siguiente directorio: 
  
  <pre>  %localappdata%\microsoft\office\16.0\lync\SipUserAddress\History Spooler   </pre>

El registro Skype Empresarial ETL principal contendrá información sobre el procesamiento de mensajes sin conexión y es el mejor origen para la investigación y solución de problemas. 
  
> [!NOTE]
> Se ha notificado un problema en el que los mensajes sin conexión no se enviaron y la carpeta "Borradores" se llenaba de mensajes. Esto ocurrió con Exchange buzones locales. El problema se ha corregido en todos los canales C2R a partir del 14/6/2016.  
