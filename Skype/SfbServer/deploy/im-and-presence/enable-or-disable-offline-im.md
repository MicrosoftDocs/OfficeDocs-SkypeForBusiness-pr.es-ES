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
# <a name="enable-or-disable-offline-instant-messaging-im-in-skype-for-business-server"></a><span data-ttu-id="effc0-103">Habilitar o deshabilitar la mensajería instantánea sin conexión en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="effc0-103">Enable or Disable Offline Instant Messaging (IM) in Skype for Business Server</span></span>
 
<span data-ttu-id="effc0-104">Aprenda a habilitar o deshabilitar la mensajería instantánea sin conexión en Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="effc0-104">Learn to enable or disable Offline Instant Messaging (IM) in Skype for Business Server.</span></span>
  
## <a name="enable-offline-instant-messaging-im-in-skype-for-business-server"></a><span data-ttu-id="effc0-105">Habilitar la mensajería instantánea sin conexión en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="effc0-105">Enable Offline Instant Messaging (IM) in Skype for Business Server</span></span>

<span data-ttu-id="effc0-106">La mensajería instantánea sin conexión es una característica del lado cliente integrada en el cliente de Skype Empresarial (compilación 2016 C2R 16.0.6701.1000 o superior) que aprovecha los servicios Web Exchange (EWS) para enviar mensajes desde el cliente de Skype Empresarial al buzón de Exchange de un usuario.</span><span class="sxs-lookup"><span data-stu-id="effc0-106">Offline IM is a client side feature built into Skype for Business client (2016 C2R build 16.0.6701.1000 or higher) that leverages Exchange Web Services (EWS) to send messages from the Skype for Business client to a user's Exchange mailbox.</span></span> <span data-ttu-id="effc0-107">La mensajería instantánea sin conexión usa los servicios Web Exchange (EWS) para enviar mensajes sin conexión desde el cliente de Skype Empresarial al buzón de correo del destinatario.</span><span class="sxs-lookup"><span data-stu-id="effc0-107">Offline IM uses Exchange Web Services (EWS) to send Offline messages from the Skype for Business client to the mailbox of recipient.</span></span> <span data-ttu-id="effc0-108">EWS debe estar disponible para el cliente de Skype Empresarial para que se envíen mensajes sin conexión.</span><span class="sxs-lookup"><span data-stu-id="effc0-108">EWS must be available to the Skype for Business client for Offline messages to be sent.</span></span> <span data-ttu-id="effc0-109">Para obtener más información acerca de la planeación de la mensajería instantánea y la presencia, consulte [Plan for instant messaging and presence in Skype for Business Server](../../plan-your-deployment/instant-messaging-and-presence.md).</span><span class="sxs-lookup"><span data-stu-id="effc0-109">To learn more about planning for instant messaging and presence, see [Plan for instant messaging and presence in Skype for Business Server](../../plan-your-deployment/instant-messaging-and-presence.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="effc0-110">Si el buzón del usuario está hospedado en Exchange local, se requiere el cliente de Skype Empresarial (compilación 16.0.6920.1000 de C2R de 2016)</span><span class="sxs-lookup"><span data-stu-id="effc0-110">If the user's mailbox is hosted in Exchange On-Premises, the Skype for Business client (2016 C2R build 16.0.6920.1000) is required</span></span> 
  
### <a name="to-enable-or-disable-offline-im-in-skype-for-business-server"></a><span data-ttu-id="effc0-111">Para habilitar o deshabilitar la mensajería instantánea sin conexión en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="effc0-111">To enable or disable Offline IM in Skype for Business Server</span></span>

1. <span data-ttu-id="effc0-112">Abra el Shell de administración de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="effc0-112">Open the Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="effc0-113">Ejecute el siguiente comando para habilitar la mensajería instantánea sin conexión.</span><span class="sxs-lookup"><span data-stu-id="effc0-113">Run the following command to enable Offline IM.</span></span>
    
   ```powershell
   Set-CsImConfiguration -EnableOfflineIM $True
   ```

    > [!NOTE]
    > <span data-ttu-id="effc0-114">En Skype Empresarial Server 2015 CU3, la opción EnableOfflineIM se establece en $True predeterminada.</span><span class="sxs-lookup"><span data-stu-id="effc0-114">In Skype for Business Server 2015 CU3, the EnableOfflineIM option is set to $True by default.</span></span> <span data-ttu-id="effc0-115">Para deshabilitar, establezca este valor en $False.</span><span class="sxs-lookup"><span data-stu-id="effc0-115">To disable, set this value to $False.</span></span> 
  
3. <span data-ttu-id="effc0-116">Ejecute el siguiente comando para confirmar que se ha establecido la capacidad de almacenar mensajería instantánea sin conexión.</span><span class="sxs-lookup"><span data-stu-id="effc0-116">Run the following command to confirm the ability to store Offline IM's is set.</span></span>
    
   ```powershell
   Get-CsImConfiguration
   ```

## <a name="offline-im-integration-with-exchange"></a><span data-ttu-id="effc0-117">Integración de mensajería instantánea sin conexión con Exchange</span><span class="sxs-lookup"><span data-stu-id="effc0-117">Offline IM Integration with Exchange</span></span>

<span data-ttu-id="effc0-118">La mensajería instantánea sin conexión no estará disponible para los remitentes si tienen una directiva de cliente que deshabilita el guardado automático de mensajes sin conexión en la carpeta del historial de conversaciones (EnableIMAutoArchiving = $false).</span><span class="sxs-lookup"><span data-stu-id="effc0-118">Offline IM will not be available to senders if they have a client policy that disables automatic saving of Offline messages to the conversation history folder (EnableIMAutoArchiving = $false).</span></span> <span data-ttu-id="effc0-119">No hay ningún mecanismo para comprobar si el destinatario puede recibir mensajes sin conexión.</span><span class="sxs-lookup"><span data-stu-id="effc0-119">There is no mechanism to check if the recipient is able to receive Offline messages.</span></span>
  
<span data-ttu-id="effc0-120">Para los mensajes sin conexión enviados dentro de la misma organización, se recibirán como un mensaje de correo electrónico con la clase de mensaje IM.Note.MissedConversation y se incluirán en la carpeta Conversación perdida de **Outlook,** así como el historial de conversaciones que se seleccionará en la pestaña historial de listas o conversaciones recientes en los clientes de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="effc0-120">For Offline messages sent within the same organization they will be received as an email message with message class of IM.Note.MissedConversation and will be included in Outlook **Missed Conversation** folder, as well as conversation history which will be picked up in recent list/conversation history tab in Skype for Business clients.</span></span>
  
<span data-ttu-id="effc0-121">Para los mensajes sin conexión enviados desde una organización federada, se recibirán como un mensaje de correo electrónico sin IM.Note.MisssedConversation y no se seleccionarán en las carpetas de conversación perdida o historial de conversaciones.</span><span class="sxs-lookup"><span data-stu-id="effc0-121">For Offline messages sent from federated organization they will be received as an email message without IM.Note.MisssedConversation and will not be picked up in the missed conversation or conversation history folders.</span></span> 
  
## <a name="troubleshooting"></a><span data-ttu-id="effc0-122">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="effc0-122">Troubleshooting</span></span>

<span data-ttu-id="effc0-123">Hay un temporizador de dos minutos desde que se envía un mensaje sin conexión cuando se selecciona y se procesa.</span><span class="sxs-lookup"><span data-stu-id="effc0-123">There is a two minute timer from when an offline message is sent to when it's picked up and processed.</span></span> <span data-ttu-id="effc0-124">Si los mensajes sin conexión no se pueden procesar, aparecerán en el siguiente directorio:</span><span class="sxs-lookup"><span data-stu-id="effc0-124">If offline messages can't be processed they will appear in the following directory:</span></span> 
  
  <pre>  %localappdata%\microsoft\office\16.0\lync\SipUserAddress\History Spooler   </pre>

<span data-ttu-id="effc0-125">El registro ETL principal de Skype Empresarial contendrá información sobre el procesamiento de mensajes sin conexión y es la mejor fuente para la investigación y la solución de problemas.</span><span class="sxs-lookup"><span data-stu-id="effc0-125">The primary Skype for Business ETL log will contain information about Offline message processing and is your best source for investigation/troubleshooting.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="effc0-126">Se ha notificado un problema en el que los mensajes sin conexión no se enviaron y la carpeta "Borradores" se rellenaba con mensajes.</span><span class="sxs-lookup"><span data-stu-id="effc0-126">An issue has been reported where Offline messages failed to send and the 'Drafts' folder was getting filled with messages.</span></span> <span data-ttu-id="effc0-127">Esto ocurrió con buzones locales de Exchange.</span><span class="sxs-lookup"><span data-stu-id="effc0-127">This occurred with Exchange On-Premises mailboxes.</span></span> <span data-ttu-id="effc0-128">The issue has been fixed in all C2R channels as of 6/14/2016.</span><span class="sxs-lookup"><span data-stu-id="effc0-128">The issue has been fixed in all C2R channels as of 6/14/2016.</span></span>  
