---
title: Realizar cambios en la configuración de Difusión de reunión de Skype para su organización
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
description: Puede habilitar Difusión de reunión de Skype y realizar cambios en la configuración y las directivas para esas reuniones.
ms.openlocfilehash: 88f074838ff1d03153441beb624bc5d9b7ad157c
ms.sourcegitcommit: a5bc64abb02201cb5c2ff6696f6ef99064e1cae7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753415"
---
# <a name="make-changes-to-skype-meeting-broadcast-settings-for-your-organization"></a><span data-ttu-id="062bf-103">Realizar cambios en la configuración de Difusión de reunión de Skype para su organización</span><span class="sxs-lookup"><span data-stu-id="062bf-103">Make changes to Skype Meeting Broadcast settings for your organization</span></span>

> [!IMPORTANT]
> <span data-ttu-id="062bf-104">El Centro de administración de Microsoft Teams ha sustituido al Centro de administración de Skype Empresarial (portal heredado).</span><span class="sxs-lookup"><span data-stu-id="062bf-104">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="062bf-105">Todas las configuraciones para administrar Skype Empresarial se encuentran ahora en el Centro de administración de Teams.</span><span class="sxs-lookup"><span data-stu-id="062bf-105">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="062bf-106">Debe tener asignado el rol de administrador de [Azure AD](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) de Administrador global o de administrador de Skype Empresarial para administrar las características de Skype Empresarial en el Centro de administración de Teams.</span><span class="sxs-lookup"><span data-stu-id="062bf-106">You must be assigned the [Azure AD admin role](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Teams admin center.</span></span> <span data-ttu-id="062bf-107">Para conocer más, consulte [Administrar la configuración de Skype empresarial en el Centro de administración de Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json)</span><span class="sxs-lookup"><span data-stu-id="062bf-107">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).</span></span>

<span data-ttu-id="062bf-108">Puede habilitar Difusión de reunión de Skype y realizar cambios en la configuración y las directivas para esas reuniones.</span><span class="sxs-lookup"><span data-stu-id="062bf-108">You can enable Skype Meeting Broadcast and make changes to settings and policies for those meetings.</span></span>
  
- <span data-ttu-id="062bf-109">**Habilitar Difusión de reunión de Skype** Habilita Difusión de reunión de Skype.</span><span class="sxs-lookup"><span data-stu-id="062bf-109">**Enable Skype Meeting Broadcast** Enables Skype Meeting Broadcast.</span></span> <span data-ttu-id="062bf-110">Después de habilitar Difusión de reunión de Skype, debe configurar [su red para Difusión de reunión de Skype.](set-up-your-network-for-skype-meeting-broadcast.md)</span><span class="sxs-lookup"><span data-stu-id="062bf-110">After you enable Skype Meeting Broadcast, you need to [Set up your network for Skype Meeting Broadcast](set-up-your-network-for-skype-meeting-broadcast.md).</span></span> <span data-ttu-id="062bf-111">Realice este paso si quiere realizar seminarios web y otras difusiones para personas que no forme parte de su empresa.</span><span class="sxs-lookup"><span data-stu-id="062bf-111">Do this step if you want to hold webinars and other broadcasts for people outside of your business.</span></span> 
    
- <span data-ttu-id="062bf-112">**Habilitar las características de Vista previa de difusión de reunión de Skype para mi organización** Los programas de cliente de Skype Empresarial le proporcionan acceso anticipado a nuevos productos y características.</span><span class="sxs-lookup"><span data-stu-id="062bf-112">**Enable Skype Meeting Broadcast Preview features for my organization** The Skype for Business customer programs provide you early access to new products and features.</span></span> <span data-ttu-id="062bf-113">Esto le permite a su organización echar un vistazo a las novedades y la oportunidad de probar las nuevas características en su propio entorno y enviar comentarios antes de publicar las compilaciones del producto para el público general.</span><span class="sxs-lookup"><span data-stu-id="062bf-113">This gives your organization a sneak peek at what's coming and the opportunity to test the new features in your own environment and give feedback before we release product builds to the general public.</span></span><br/>[<span data-ttu-id="062bf-114">Versión preliminar de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="062bf-114">Skype for Business preview</span></span>](https://www.skypepreview.com/)
    
- <span data-ttu-id="062bf-115">**Permitir que los organizadores programe reuniones anónimas** Esto permite a los organizadores crear eventos de difusión que permiten a cualquier persona de fuera de su organización unirse sin la necesidad de iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="062bf-115">**Allow organizers to schedule anonymous meetings** This lets organizers create broadcast events that allow anyone outside their organization to join without a requirement to sign in.</span></span>
    
- <span data-ttu-id="062bf-116">**Permitir que se grabe la difusión de reuniones** Esto permite que el moderador o el organizador pueda grabar cualquier reunión.</span><span class="sxs-lookup"><span data-stu-id="062bf-116">**Allow broadcast meetings to be recorded** This enables any meetings you have to be recorded by the presenter or organizer.</span></span>
    
- <span data-ttu-id="062bf-117">**Dirección URL del departamento de soporte técnico para los asistentes** Escriba un vínculo para que los asistentes a la difusión de la reunión lo usen si necesitan ayuda para conectarse o asistir a una difusión de reunión.</span><span class="sxs-lookup"><span data-stu-id="062bf-117">**Helpdesk support URL for attendees** Enter a link for meeting broadcast attendees to use if they need help connecting or attending a broadcast meeting.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="062bf-118">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="062bf-118">Related topics</span></span>

[<span data-ttu-id="062bf-119">Configurar la red para Difusión de reunión de Skype</span><span class="sxs-lookup"><span data-stu-id="062bf-119">Set up your network for Skype Meeting Broadcast</span></span>](set-up-your-network-for-skype-meeting-broadcast.md)

  
 
