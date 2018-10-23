---
title: Socios federados del Sistema de salas de Skype y de Skype Empresarial
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1cc20323-ecba-4e87-a861-e54193e64cf0
description: Lea este tema para obtener información acerca de cómo configurar el Sistema de salas de Skype para socios federados de Skype Empresarial.
ms.openlocfilehash: e954bf5d7586c651d9d045b2d428f86f01de8a30
ms.sourcegitcommit: d3c3467320a2928d3bad14a1a44a31ee5a9a988c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/23/2018
ms.locfileid: "25699547"
---
# <a name="skype-room-system-and-skype-for-business-federated-partners"></a><span data-ttu-id="fea23-103">Socios federados del Sistema de salas de Skype y de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="fea23-103">Skype Room System and Skype for Business federated partners</span></span>
 
<span data-ttu-id="fea23-104">Lea este tema para obtener información acerca de cómo configurar el Sistema de salas de Skype para socios federados de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="fea23-104">Read this topic to learn how to set up Skype Room System for Skype for Business federated partners.</span></span>
  
## <a name="skype-room-system-and-skype-for-business-federated-partners"></a><span data-ttu-id="fea23-105">Socios federados del Sistema de salas de Skype y de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="fea23-105">Skype Room System and Skype for Business federated partners</span></span>

<span data-ttu-id="fea23-106">Sistema de sala de Skype se basa en la Skype unirse a para el vínculo de la reunión de negocios en la convocatoria de reunión del calendario.</span><span class="sxs-lookup"><span data-stu-id="fea23-106">Skype Room System relies on the Join Skype for Business Meeting link in the calendar meeting request.</span></span> <span data-ttu-id="fea23-107">El vínculo de unión generalmente se encuentra en el cuerpo de una convocatoria de reunión.</span><span class="sxs-lookup"><span data-stu-id="fea23-107">The join link is usually found in the body of a meeting request.</span></span> <span data-ttu-id="fea23-108">Sin embargo, sistema de sala de Skype depende de este vínculo a estar presentes en las propiedades MAPI del mensaje.</span><span class="sxs-lookup"><span data-stu-id="fea23-108">However, Skype Room System depends on this link to be present in the MAPI properties of the message.</span></span> <span data-ttu-id="fea23-109">Cuando esta reunión es enviar una solicitud a las organizaciones remotas (Skype para socios federados), de forma predeterminada del sistema de salas de Skype no mostrará de la organización remoto la participación en reuniones de vínculos en el calendario.</span><span class="sxs-lookup"><span data-stu-id="fea23-109">When this meeting request is sent to remote organizations (Skype for Business federated partners), by default the remote organization's Skype Room System will not show the meeting join link on the calendar.</span></span> <span data-ttu-id="fea23-110">De hecho, los usuarios de Outlook en la organización remota podrán unirse a la Skype para la reunión de negocios con un clic derecho del calendario al elemento o desde dentro del aviso de reunión.</span><span class="sxs-lookup"><span data-stu-id="fea23-110">In fact, any Outlook users in the remote organization will be unable to join the Skype for Business meeting with a right click of the calendar item or from within the meeting reminder.</span></span> <span data-ttu-id="fea23-111">Debe abrir la invitación a la reunión y haga clic en unirse a Skype para la reunión de negocios en el cuerpo del mensaje.</span><span class="sxs-lookup"><span data-stu-id="fea23-111">They must open meeting invite and click Join Skype for Business Meeting in the body of the message.</span></span> 
  
<span data-ttu-id="fea23-112">El motivo de esta limitación es que Outlook y Microsoft Exchange no usan un método especial para empaquetar información a la hora de enviar mensajes a través de Internet.</span><span class="sxs-lookup"><span data-stu-id="fea23-112">The reason for this limitation is that Outlook and Microsoft Exchange do not use a special method to package information for sending messages across the Internet.</span></span> <span data-ttu-id="fea23-113">Este método, que se conoce como Formato de encapsulamiento neutro de transporte (TNEF), está deshabilitado de forma predeterminada para los mensajes enviados externamente desde una organización de Exchange.</span><span class="sxs-lookup"><span data-stu-id="fea23-113">This method, referred to as Transport Neutral Encapsulation Format (TNEF), is disabled by default for messages sent externally from an Exchange organization.</span></span> <span data-ttu-id="fea23-114">Para una reunión de vínculo unirse a que aparezca en un sistema remoto de salón de Skype, la organización de envío debe habilitar TNEF mediante el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="fea23-114">For a meeting join link to appear on a remote Skype Room System, the sending organization must enable TNEF by using the following command:</span></span>
  
```
New-RemoteDomain -DomainName Contoso.com -Name Contoso
Set-RemoteDomain -Identity Contoso -TNEFEnabled $true
```

<span data-ttu-id="fea23-115">Una vez que TNEF está habilitado para la organización remota, los mensajes enviados a través de Internet a la organización se envían como datos adjuntos en formato TNEF.</span><span class="sxs-lookup"><span data-stu-id="fea23-115">After TNEF is enabled for the remote organization, any message sent over the Internet to the organization is sent as an attachment in TNEF format.</span></span> <span data-ttu-id="fea23-116">Con TNEF habilitada, cuando un Skype para convocatoria de reunión de negocio se envía a la Skype para socios federados de negocio, sistema de sala de Skype podrá representar la participación de Skype para la reunión de negocios y los usuarios remotos podrán unirse a Skype para reuniones de negocios.</span><span class="sxs-lookup"><span data-stu-id="fea23-116">With TNEF enabled, when a Skype for Business meeting request is sent to the Skype for Business federated partner, Skype Room System will be able to render the Join Skype for Business Meeting and remote users will be able to join Skype for Business meetings.</span></span> 