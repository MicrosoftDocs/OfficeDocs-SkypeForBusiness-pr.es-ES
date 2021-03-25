---
title: Realizar cambios en la configuración de difusión de reunión de Skype para su organización
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: micchan
ms.topic: article
ms.assetid: 8e46e857-f046-4e87-a633-0d7fb88d66d5
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- SMB
- ms.lync.lac.BroadcastMeetings
description: Puede habilitar difusión de reunión de Skype y realizar cambios en la configuración y las directivas para esas reuniones.
ms.openlocfilehash: 75b1894f486d6448662c459b0d77d4f5d3057a2f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51106556"
---
# <a name="make-changes-to-skype-meeting-broadcast-settings-for-your-organization"></a><span data-ttu-id="47653-103">Realizar cambios en la configuración de difusión de reunión de Skype para su organización</span><span class="sxs-lookup"><span data-stu-id="47653-103">Make changes to Skype Meeting Broadcast settings for your organization</span></span>

> [!IMPORTANT]
> <span data-ttu-id="47653-104">El Centro de administración de Microsoft Teams ha sustituido al Centro de administración de Skype Empresarial (portal heredado).</span><span class="sxs-lookup"><span data-stu-id="47653-104">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="47653-105">Todas las opciones de configuración para administrar Skype Empresarial se encuentran ahora en el Centro de administración de Teams.</span><span class="sxs-lookup"><span data-stu-id="47653-105">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="47653-106">Debe tener asignado el rol de administrador de [Azure AD](/azure/active-directory/roles/permissions-reference) de administrador global o administrador de Skype Empresarial para administrar las características de Skype Empresarial en el Centro de administración de Teams.</span><span class="sxs-lookup"><span data-stu-id="47653-106">You must be assigned the [Azure AD admin role](/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Teams admin center.</span></span> <span data-ttu-id="47653-107">Para conocer más, consulte [Administrar la configuración de Skype empresarial en el Centro de administración de Microsoft Teams](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json)</span><span class="sxs-lookup"><span data-stu-id="47653-107">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json).</span></span>

<span data-ttu-id="47653-108">Puede habilitar difusión de reunión de Skype y realizar cambios en la configuración y las directivas para esas reuniones.</span><span class="sxs-lookup"><span data-stu-id="47653-108">You can enable Skype Meeting Broadcast and make changes to settings and policies for those meetings.</span></span>
  
- <span data-ttu-id="47653-109">**Habilitar difusión de reunión de Skype** Habilita difusión de reunión de Skype.</span><span class="sxs-lookup"><span data-stu-id="47653-109">**Enable Skype Meeting Broadcast** Enables Skype Meeting Broadcast.</span></span> <span data-ttu-id="47653-110">Después de habilitar difusión de reunión de Skype, debe [configurar su red para difusión de reunión de Skype.](set-up-your-network-for-skype-meeting-broadcast.md)</span><span class="sxs-lookup"><span data-stu-id="47653-110">After you enable Skype Meeting Broadcast, you need to [Set up your network for Skype Meeting Broadcast](set-up-your-network-for-skype-meeting-broadcast.md).</span></span> <span data-ttu-id="47653-111">Realice este paso si desea celebrar seminarios web y otras difusión para personas ajenas a su empresa.</span><span class="sxs-lookup"><span data-stu-id="47653-111">Do this step if you want to hold webinars and other broadcasts for people outside of your business.</span></span> 
    
- <span data-ttu-id="47653-112">**Habilitar las características de vista previa de difusión de reunión de Skype para mi organización** Los programas para clientes de Skype Empresarial le proporcionan acceso anticipado a nuevos productos y características.</span><span class="sxs-lookup"><span data-stu-id="47653-112">**Enable Skype Meeting Broadcast Preview features for my organization** The Skype for Business customer programs provide you early access to new products and features.</span></span> <span data-ttu-id="47653-113">Esto ofrece a su organización un vistazo a lo que viene y la oportunidad de probar las nuevas características en su propio entorno y enviar comentarios antes de publicar compilaciones de productos para el público en general.</span><span class="sxs-lookup"><span data-stu-id="47653-113">This gives your organization a sneak peek at what's coming and the opportunity to test the new features in your own environment and give feedback before we release product builds to the general public.</span></span><br/>[<span data-ttu-id="47653-114">Vista previa de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="47653-114">Skype for Business preview</span></span>](https://www.skypepreview.com/)
    
- <span data-ttu-id="47653-115">**Permitir a los organizadores programar reuniones anónimas** Esto permite a los organizadores crear eventos de difusión que permiten a cualquier persona de fuera de su organización unirse sin necesidad de iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="47653-115">**Allow organizers to schedule anonymous meetings** This lets organizers create broadcast events that allow anyone outside their organization to join without a requirement to sign in.</span></span>
    
- <span data-ttu-id="47653-116">**Permitir que se graben reuniones de difusión** Esto permite que el moderador u organizador grabe las reuniones que tenga que grabar.</span><span class="sxs-lookup"><span data-stu-id="47653-116">**Allow broadcast meetings to be recorded** This enables any meetings you have to be recorded by the presenter or organizer.</span></span>
    
- <span data-ttu-id="47653-117">**Url de soporte técnico para asistentes** Escriba un vínculo para que los asistentes a la difusión de la reunión lo usen si necesitan ayuda para conectarse o asistir a una reunión de difusión.</span><span class="sxs-lookup"><span data-stu-id="47653-117">**Helpdesk support URL for attendees** Enter a link for meeting broadcast attendees to use if they need help connecting or attending a broadcast meeting.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="47653-118">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="47653-118">Related topics</span></span>

[<span data-ttu-id="47653-119">Configurar la red para Difusión de reunión de Skype</span><span class="sxs-lookup"><span data-stu-id="47653-119">Set up your network for Skype Meeting Broadcast</span></span>](set-up-your-network-for-skype-meeting-broadcast.md)

  
