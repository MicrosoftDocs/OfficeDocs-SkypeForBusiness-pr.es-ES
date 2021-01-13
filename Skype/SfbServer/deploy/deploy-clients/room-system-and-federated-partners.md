---
title: Sistema de sala de Skype y socios federados de Skype Empresarial
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1cc20323-ecba-4e87-a861-e54193e64cf0
description: Lea este tema para obtener información sobre cómo configurar el Sistema de sala de Skype para socios federados de Skype Empresarial.
ms.openlocfilehash: ac0203479907f830f1bc6cec6831f8804906e669
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820810"
---
# <a name="skype-room-system-and-skype-for-business-federated-partners"></a><span data-ttu-id="85c00-103">Sistema de sala de Skype y socios federados de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="85c00-103">Skype Room System and Skype for Business federated partners</span></span>
 
<span data-ttu-id="85c00-104">Lea este tema para obtener información sobre cómo configurar el Sistema de sala de Skype para socios federados de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="85c00-104">Read this topic to learn how to set up Skype Room System for Skype for Business federated partners.</span></span>
  
## <a name="skype-room-system-and-skype-for-business-federated-partners"></a><span data-ttu-id="85c00-105">Sistema de sala de Skype y socios federados de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="85c00-105">Skype Room System and Skype for Business federated partners</span></span>

<span data-ttu-id="85c00-106">El Sistema de salas de Skype se basa en el vínculo Unirse a una reunión de Skype Empresarial en la solicitud de reunión del calendario.</span><span class="sxs-lookup"><span data-stu-id="85c00-106">Skype Room System relies on the Join Skype for Business Meeting link in the calendar meeting request.</span></span> <span data-ttu-id="85c00-107">El vínculo de unión suele encontrarse en el cuerpo de una solicitud de reunión.</span><span class="sxs-lookup"><span data-stu-id="85c00-107">The join link is usually found in the body of a meeting request.</span></span> <span data-ttu-id="85c00-108">Sin embargo, el Sistema de sala de Skype depende de que este vínculo esté presente en las propiedades MAPI del mensaje.</span><span class="sxs-lookup"><span data-stu-id="85c00-108">However, Skype Room System depends on this link to be present in the MAPI properties of the message.</span></span> <span data-ttu-id="85c00-109">Cuando esta solicitud de reunión se envía a organizaciones remotas (socios federados de Skype Empresarial), de forma predeterminada el Sistema de salas de Skype de la organización remota no mostrará el vínculo para unirse a la reunión en el calendario.</span><span class="sxs-lookup"><span data-stu-id="85c00-109">When this meeting request is sent to remote organizations (Skype for Business federated partners), by default the remote organization's Skype Room System will not show the meeting join link on the calendar.</span></span> <span data-ttu-id="85c00-110">De hecho, los usuarios de Outlook de la organización remota no podrán unirse a la reunión de Skype Empresarial con un clic con el botón derecho del elemento del calendario o desde el aviso de la reunión.</span><span class="sxs-lookup"><span data-stu-id="85c00-110">In fact, any Outlook users in the remote organization will be unable to join the Skype for Business meeting with a right click of the calendar item or from within the meeting reminder.</span></span> <span data-ttu-id="85c00-111">Deben abrir la invitación a la reunión y hacer clic en Unirse a una reunión de Skype Empresarial en el cuerpo del mensaje.</span><span class="sxs-lookup"><span data-stu-id="85c00-111">They must open meeting invite and click Join Skype for Business Meeting in the body of the message.</span></span> 
  
<span data-ttu-id="85c00-112">El motivo de esta limitación es que Outlook y Microsoft Exchange no usan un método especial para empaquetar información para enviar mensajes a través de Internet.</span><span class="sxs-lookup"><span data-stu-id="85c00-112">The reason for this limitation is that Outlook and Microsoft Exchange do not use a special method to package information for sending messages across the Internet.</span></span> <span data-ttu-id="85c00-113">Este método, denominado Formato de encapsulamiento neutro de transporte (TNEF), está deshabilitado de forma predeterminada para los mensajes enviados externamente desde una organización de Exchange.</span><span class="sxs-lookup"><span data-stu-id="85c00-113">This method, referred to as Transport Neutral Encapsulation Format (TNEF), is disabled by default for messages sent externally from an Exchange organization.</span></span> <span data-ttu-id="85c00-114">Para que un vínculo de participación en una reunión aparezca en un sistema remoto de salas de Skype, la organización de envío debe habilitar TNEF mediante el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="85c00-114">For a meeting join link to appear on a remote Skype Room System, the sending organization must enable TNEF by using the following command:</span></span>
  
```powershell
New-RemoteDomain -DomainName Contoso.com -Name Contoso
Set-RemoteDomain -Identity Contoso -TNEFEnabled $true
```

<span data-ttu-id="85c00-115">Después de habilitar TNEF para la organización remota, cualquier mensaje enviado a través de Internet a la organización se envía como datos adjuntos en formato TNEF.</span><span class="sxs-lookup"><span data-stu-id="85c00-115">After TNEF is enabled for the remote organization, any message sent over the Internet to the organization is sent as an attachment in TNEF format.</span></span> <span data-ttu-id="85c00-116">Con TNEF habilitado, cuando se envía una solicitud de reunión de Skype Empresarial al socio federado de Skype Empresarial, el Sistema de salas de Skype podrá representar la reunión de Skype Empresarial y los usuarios remotos podrán unirse a reuniones de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="85c00-116">With TNEF enabled, when a Skype for Business meeting request is sent to the Skype for Business federated partner, Skype Room System will be able to render the Join Skype for Business Meeting and remote users will be able to join Skype for Business meetings.</span></span> 
