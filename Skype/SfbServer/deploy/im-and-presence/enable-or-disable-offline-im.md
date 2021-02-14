---
title: Habilitar o deshabilitar la mensajería instantánea sin conexión en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c0f44352-fb4a-45d3-85b0-a4320d4b8339
description: Aprenda a habilitar o deshabilitar la mensajería instantánea sin conexión en Skype Empresarial Server.
ms.openlocfilehash: 510ebe65e60b9ea12d2f368b0e2d33c705b8d0d6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801950"
---
# <a name="enable-or-disable-offline-instant-messaging-im-in-skype-for-business-server"></a>Habilitar o deshabilitar la mensajería instantánea sin conexión en Skype Empresarial Server
 
Aprenda a habilitar o deshabilitar la mensajería instantánea sin conexión en Skype Empresarial Server.
  
## <a name="enable-offline-instant-messaging-im-in-skype-for-business-server"></a>Habilitar la mensajería instantánea sin conexión en Skype Empresarial Server

La mensajería instantánea sin conexión es una característica del lado cliente integrada en el cliente de Skype Empresarial (compilación 2016 C2R 16.0.6701.1000 o superior) que aprovecha los servicios Web Exchange (EWS) para enviar mensajes desde el cliente de Skype Empresarial al buzón de Exchange de un usuario. La mensajería instantánea sin conexión usa los servicios Web Exchange (EWS) para enviar mensajes sin conexión desde el cliente de Skype Empresarial al buzón de correo del destinatario. EWS debe estar disponible para el cliente de Skype Empresarial para que se envíen mensajes sin conexión. Para obtener más información acerca de la planeación de la mensajería instantánea y la presencia, consulte [Plan for instant messaging and presence in Skype for Business Server](../../plan-your-deployment/instant-messaging-and-presence.md).
  
> [!NOTE]
> Si el buzón del usuario está hospedado en Exchange local, se requiere el cliente de Skype Empresarial (compilación 16.0.6920.1000 de C2R de 2016) 
  
### <a name="to-enable-or-disable-offline-im-in-skype-for-business-server"></a>Para habilitar o deshabilitar la mensajería instantánea sin conexión en Skype Empresarial Server

1. Abra el Shell de administración de Skype Empresarial Server.
    
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
  
Para los mensajes sin conexión enviados dentro de la misma organización, se recibirán como un mensaje de correo electrónico con la clase de mensaje IM.Note.MissedConversation y se incluirán en la carpeta Conversación perdida de **Outlook,** así como el historial de conversaciones que se seleccionará en la pestaña historial de listas o conversaciones recientes en los clientes de Skype Empresarial.
  
Para los mensajes sin conexión enviados desde una organización federada, se recibirán como un mensaje de correo electrónico sin IM.Note.MisssedConversation y no se seleccionarán en las carpetas de conversación perdida o historial de conversaciones. 
  
## <a name="troubleshooting"></a>Solución de problemas

Hay un temporizador de dos minutos desde que se envía un mensaje sin conexión cuando se selecciona y se procesa. Si los mensajes sin conexión no se pueden procesar, aparecerán en el siguiente directorio: 
  
  <pre>  %localappdata%\microsoft\office\16.0\lync\SipUserAddress\History Spooler   </pre>

El registro ETL principal de Skype Empresarial contendrá información sobre el procesamiento de mensajes sin conexión y es la mejor fuente para la investigación y solución de problemas. 
  
> [!NOTE]
> Se ha notificado un problema en el que los mensajes sin conexión no se enviaron y la carpeta "Borradores" se rellenaba con mensajes. Esto ocurrió con buzones locales de Exchange. The issue has been fixed in all C2R channels as of 6/14/2016.  
