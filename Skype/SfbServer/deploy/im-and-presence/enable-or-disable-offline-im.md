---
title: Habilitar o deshabilitar la mensajería instantánea sin conexión (mi) en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c0f44352-fb4a-45d3-85b0-a4320d4b8339
description: Aprenda a habilitar o deshabilitar la mensajería instantánea sin conexión (mi) en Skype empresarial Server.
ms.openlocfilehash: 02056618aff8a2dcaa6edc2023b67ad38aa9f314
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003050"
---
# <a name="enable-or-disable-offline-instant-messaging-im-in-skype-for-business-server"></a><span data-ttu-id="b308a-103">Habilitar o deshabilitar la mensajería instantánea sin conexión (mi) en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="b308a-103">Enable or Disable Offline Instant Messaging (IM) in Skype for Business Server</span></span>
 
<span data-ttu-id="b308a-104">Aprenda a habilitar o deshabilitar la mensajería instantánea sin conexión (mi) en Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="b308a-104">Learn to enable or disable Offline Instant Messaging (IM) in Skype for Business Server.</span></span>
  
## <a name="enable-offline-instant-messaging-im-in-skype-for-business-server"></a><span data-ttu-id="b308a-105">Habilitar la mensajería instantánea (mi) sin conexión en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="b308a-105">Enable Offline Instant Messaging (IM) in Skype for Business Server</span></span>

<span data-ttu-id="b308a-106">La mensajería instantánea sin conexión es una característica del lado cliente incorporada en el cliente de Skype empresarial (2016 C2R compilación 16.0.6701.1000 o superior) que aprovecha los servicios Web de Exchange (EWS) para enviar mensajes desde el cliente de Skype empresarial al buzón de Exchange de un usuario.</span><span class="sxs-lookup"><span data-stu-id="b308a-106">Offline IM is a client side feature built into Skype for Business client (2016 C2R build 16.0.6701.1000 or higher) that leverages Exchange Web Services (EWS) to send messages from the Skype for Business client to a user's Exchange mailbox.</span></span> <span data-ttu-id="b308a-107">La mensajería instantánea sin conexión usa los servicios web Exchange (EWS) para enviar mensajes sin conexión desde el cliente de Skype empresarial hasta el buzón de correo del destinatario.</span><span class="sxs-lookup"><span data-stu-id="b308a-107">Offline IM uses Exchange Web Services (EWS) to send Offline messages from the Skype for Business client to the mailbox of recipient.</span></span> <span data-ttu-id="b308a-108">EWS debe estar disponible para que el cliente de Skype empresarial pueda enviar mensajes sin conexión.</span><span class="sxs-lookup"><span data-stu-id="b308a-108">EWS must be available to the Skype for Business client for Offline messages to be sent.</span></span> <span data-ttu-id="b308a-109">Para obtener más información sobre cómo planear la mensajería instantánea y la presencia, consulte [planear la mensajería instantánea y la presencia en Skype empresarial Server](../../plan-your-deployment/instant-messaging-and-presence.md).</span><span class="sxs-lookup"><span data-stu-id="b308a-109">To learn more about planning for instant messaging and presence, see [Plan for instant messaging and presence in Skype for Business Server](../../plan-your-deployment/instant-messaging-and-presence.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="b308a-110">Si el buzón del usuario se hospeda en Exchange local, el cliente de Skype empresarial (2016 C2R compilación 16.0.6920.1000) es necesario</span><span class="sxs-lookup"><span data-stu-id="b308a-110">If the user's mailbox is hosted in Exchange On-Premises, the Skype for Business client (2016 C2R build 16.0.6920.1000) is required</span></span> 
  
### <a name="to-enable-or-disable-offline-im-in-skype-for-business-server"></a><span data-ttu-id="b308a-111">Para habilitar o deshabilitar la mensajería instantánea sin conexión en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="b308a-111">To enable or disable Offline IM in Skype for Business Server</span></span>

1. <span data-ttu-id="b308a-112">Abra el shell de administración de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="b308a-112">Open the Skype for Business Server Management Shell.</span></span>
    
2. <span data-ttu-id="b308a-113">Ejecute el siguiente comando para habilitar la MI sin conexión.</span><span class="sxs-lookup"><span data-stu-id="b308a-113">Run the following command to enable Offline IM.</span></span>
    
   ```powershell
   Set-CsImConfiguration -EnableOfflineIM $True
   ```

    > [!NOTE]
    > <span data-ttu-id="b308a-114">En Skype empresarial Server 2015 CU3, la opción EnableOfflineIM se establece en $True de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="b308a-114">In Skype for Business Server 2015 CU3, the EnableOfflineIM option is set to $True by default.</span></span> <span data-ttu-id="b308a-115">Para deshabilitarla, defina este valor en $False.</span><span class="sxs-lookup"><span data-stu-id="b308a-115">To disable, set this value to $False.</span></span> 
  
3. <span data-ttu-id="b308a-116">Ejecute el siguiente comando para confirmar la capacidad de almacenar los mensajes instantáneos sin conexión.</span><span class="sxs-lookup"><span data-stu-id="b308a-116">Run the following command to confirm the ability to store Offline IM's is set.</span></span>
    
   ```powershell
   Get-CsImConfiguration
   ```

## <a name="offline-im-integration-with-exchange"></a><span data-ttu-id="b308a-117">Integración de MI sin conexión con Exchange</span><span class="sxs-lookup"><span data-stu-id="b308a-117">Offline IM Integration with Exchange</span></span>

<span data-ttu-id="b308a-p103">La MI sin conexión no estará disponible para los remitentes si disponen de una directiva que deshabilita el guardado automático de los mensajes sin conexión en la carpeta de historial de conversaciones (EnableIMAutoArchiving = $false). No existe ningún mecanismo para comprobar si el destinatario puede recibir mensajes sin conexión.</span><span class="sxs-lookup"><span data-stu-id="b308a-p103">Offline IM will not be available to senders if they have a client policy that disables automatic saving of Offline messages to the conversation history folder (EnableIMAutoArchiving = $false). There is no mechanism to check if the recipient is able to receive Offline messages.</span></span>
  
<span data-ttu-id="b308a-120">Para los mensajes sin conexión enviados dentro de la misma organización se recibirán como un mensaje de correo electrónico con la clase de mensaje de mensajería instantánea. Note. MissedConversation y se incluirá en la carpeta de **conversaciones perdidas** de Outlook, así como en el historial de conversaciones, que se recogerá en la ficha de la lista de elementos recientes/historial de conversaciones en los clientes de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="b308a-120">For Offline messages sent within the same organization they will be received as an email message with message class of IM.Note.MissedConversation and will be included in Outlook **Missed Conversation** folder, as well as conversation history which will be picked up in recent list/conversation history tab in Skype for Business clients.</span></span>
  
<span data-ttu-id="b308a-121">Los mensajes sin conexión enviados desde una organización federada se recibirán como un mensaje de correo electrónico sin IM.Note.MisssedConversation y no se podrán recuperar en las carpetas de conversación perdida o historial de conversaciones.</span><span class="sxs-lookup"><span data-stu-id="b308a-121">For Offline messages sent from federated organization they will be received as an email message without IM.Note.MisssedConversation and will not be picked up in the missed conversation or conversation history folders.</span></span> 
  
## <a name="troubleshooting"></a><span data-ttu-id="b308a-122">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="b308a-122">Troubleshooting</span></span>

<span data-ttu-id="b308a-123">Hay un temporizador de dos minutos desde que se envía un mensaje sin conexión al momento en que se selecciona y se procesa.</span><span class="sxs-lookup"><span data-stu-id="b308a-123">There is a two minute timer from when an offline message is sent to when it's picked up and processed.</span></span> <span data-ttu-id="b308a-124">Si los mensajes sin conexión no se pueden procesar, aparecerán en el siguiente directorio:</span><span class="sxs-lookup"><span data-stu-id="b308a-124">If offline messages can't be processed they will appear in the following directory:</span></span> 
  
  <pre>  %localappdata%\microsoft\office\16.0\lync\SipUserAddress\History Spooler   </pre>

<span data-ttu-id="b308a-125">El registro ETL principal de Skype empresarial contendrá información sobre el procesamiento de mensajes sin conexión y es la mejor fuente de investigación y solución de problemas.</span><span class="sxs-lookup"><span data-stu-id="b308a-125">The primary Skype for Business ETL log will contain information about Offline message processing and is your best source for investigation/troubleshooting.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="b308a-p105">Se ha informado de un problema en que los mensajes sin conexión no lograban enviarse y la carpeta Borradores se llenaba de mensajes. Este problema se producía en buzones de correo de Exchange local y se ha corregido en todos los canales C2R a fecha del 14/6/2016. </span><span class="sxs-lookup"><span data-stu-id="b308a-p105">An issue has been reported where Offline messages failed to send and the 'Drafts' folder was getting filled with messages. This occurred with Exchange On-Premises mailboxes. The issue has been fixed in all C2R channels as of 6/14/2016.</span></span>  
