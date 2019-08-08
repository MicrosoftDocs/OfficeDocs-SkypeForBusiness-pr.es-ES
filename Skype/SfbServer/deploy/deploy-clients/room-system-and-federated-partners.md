---
title: Socios federados del Sistema de salas de Skype y de Skype Empresarial
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1cc20323-ecba-4e87-a861-e54193e64cf0
description: Lea este tema para obtener información acerca de cómo configurar el Sistema de salas de Skype para socios federados de Skype Empresarial.
ms.openlocfilehash: a3f7841ab3e04220c0b6d77a5f2e3605d3ac6e67
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36235053"
---
# <a name="skype-room-system-and-skype-for-business-federated-partners"></a><span data-ttu-id="c5af8-103">Socios federados del Sistema de salas de Skype y de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="c5af8-103">Skype Room System and Skype for Business federated partners</span></span>
 
<span data-ttu-id="c5af8-104">Lea este tema para obtener información acerca de cómo configurar el Sistema de salas de Skype para socios federados de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="c5af8-104">Read this topic to learn how to set up Skype Room System for Skype for Business federated partners.</span></span>
  
## <a name="skype-room-system-and-skype-for-business-federated-partners"></a><span data-ttu-id="c5af8-105">Socios federados del Sistema de salas de Skype y de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="c5af8-105">Skype Room System and Skype for Business federated partners</span></span>

<span data-ttu-id="c5af8-106">El sistema de salas de Skype depende del vínculo unirse a la reunión de Skype empresarial en la convocatoria de reunión del calendario.</span><span class="sxs-lookup"><span data-stu-id="c5af8-106">Skype Room System relies on the Join Skype for Business Meeting link in the calendar meeting request.</span></span> <span data-ttu-id="c5af8-107">El vínculo de unión generalmente se encuentra en el cuerpo de una convocatoria de reunión.</span><span class="sxs-lookup"><span data-stu-id="c5af8-107">The join link is usually found in the body of a meeting request.</span></span> <span data-ttu-id="c5af8-108">Sin embargo, el sistema de salas de Skype depende de este vínculo para estar presente en las propiedades MAPI del mensaje.</span><span class="sxs-lookup"><span data-stu-id="c5af8-108">However, Skype Room System depends on this link to be present in the MAPI properties of the message.</span></span> <span data-ttu-id="c5af8-109">Cuando se envía esta convocatoria de reunión a organizaciones remotas (socios federados de Skype empresarial), de forma predeterminada, el sistema de salas de Skype de la organización remota no mostrará el vínculo de unión a la reunión en el calendario.</span><span class="sxs-lookup"><span data-stu-id="c5af8-109">When this meeting request is sent to remote organizations (Skype for Business federated partners), by default the remote organization's Skype Room System will not show the meeting join link on the calendar.</span></span> <span data-ttu-id="c5af8-110">De hecho, todos los usuarios de Outlook de la organización remota no podrán unirse a la reunión de Skype empresarial con un clic secundario en el elemento de calendario o desde el aviso de reunión.</span><span class="sxs-lookup"><span data-stu-id="c5af8-110">In fact, any Outlook users in the remote organization will be unable to join the Skype for Business meeting with a right click of the calendar item or from within the meeting reminder.</span></span> <span data-ttu-id="c5af8-111">Deben abrir la invitación a la reunión y hacer clic en unirse a la reunión de Skype empresarial en el cuerpo del mensaje.</span><span class="sxs-lookup"><span data-stu-id="c5af8-111">They must open meeting invite and click Join Skype for Business Meeting in the body of the message.</span></span> 
  
<span data-ttu-id="c5af8-112">El motivo de esta limitación es que Outlook y Microsoft Exchange no usan un método especial para empaquetar información a la hora de enviar mensajes a través de Internet.</span><span class="sxs-lookup"><span data-stu-id="c5af8-112">The reason for this limitation is that Outlook and Microsoft Exchange do not use a special method to package information for sending messages across the Internet.</span></span> <span data-ttu-id="c5af8-113">Este método, que se conoce como Formato de encapsulamiento neutro de transporte (TNEF), está deshabilitado de forma predeterminada para los mensajes enviados externamente desde una organización de Exchange.</span><span class="sxs-lookup"><span data-stu-id="c5af8-113">This method, referred to as Transport Neutral Encapsulation Format (TNEF), is disabled by default for messages sent externally from an Exchange organization.</span></span> <span data-ttu-id="c5af8-114">Para que un vínculo de unirse a una reunión aparezca en un sistema de salas de Skype remoto, la organización remitente debe habilitar la codificación TNEF con el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="c5af8-114">For a meeting join link to appear on a remote Skype Room System, the sending organization must enable TNEF by using the following command:</span></span>
  
```
New-RemoteDomain -DomainName Contoso.com -Name Contoso
Set-RemoteDomain -Identity Contoso -TNEFEnabled $true
```

<span data-ttu-id="c5af8-115">Una vez que TNEF está habilitado para la organización remota, los mensajes enviados a través de Internet a la organización se envían como datos adjuntos en formato TNEF.</span><span class="sxs-lookup"><span data-stu-id="c5af8-115">After TNEF is enabled for the remote organization, any message sent over the Internet to the organization is sent as an attachment in TNEF format.</span></span> <span data-ttu-id="c5af8-116">Con TNEF habilitado, cuando se envía una solicitud de reunión de Skype empresarial al socio federado de Skype empresarial, el sistema de salas de Skype podrá representar la reunión de Skype empresarial y los usuarios remotos podrán unirse a reuniones de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="c5af8-116">With TNEF enabled, when a Skype for Business meeting request is sent to the Skype for Business federated partner, Skype Room System will be able to render the Join Skype for Business Meeting and remote users will be able to join Skype for Business meetings.</span></span> 
