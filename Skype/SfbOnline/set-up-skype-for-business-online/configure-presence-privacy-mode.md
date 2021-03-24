---
title: Configurar el modo de privacidad de presencia
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: b33d57fe-b9cf-43c1-961a-edf28db738e8
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
- Setup
- ms.lync.lac.OrgPresencePrivacy
description: 'Obtenga información sobre cómo configurar el modo de privacidad de los usuarios para que puedan controlar mejor cómo ven las personas su disponibilidad. '
ms.openlocfilehash: 0b708c86d2693228ad7a613755a181fff5b3743d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093474"
---
# <a name="configure-presence-privacy-mode"></a><span data-ttu-id="593f4-103">Configurar el modo de privacidad de presencia</span><span class="sxs-lookup"><span data-stu-id="593f4-103">Configure presence privacy mode</span></span>

> [!IMPORTANT]
> <span data-ttu-id="593f4-104">El Centro de administración de Microsoft Teams ha sustituido al Centro de administración de Skype Empresarial (portal heredado).</span><span class="sxs-lookup"><span data-stu-id="593f4-104">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="593f4-105">Todas las opciones de configuración para administrar Skype Empresarial se encuentran ahora en el Centro de administración de Teams.</span><span class="sxs-lookup"><span data-stu-id="593f4-105">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="593f4-106">Debe tener asignado el rol de administrador de [Azure AD](/azure/active-directory/roles/permissions-reference) de administrador global o administrador de Skype Empresarial para administrar las características de Skype Empresarial en el Centro de administración de Teams.</span><span class="sxs-lookup"><span data-stu-id="593f4-106">You must be assigned the [Azure AD admin role](/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Teams admin center.</span></span> <span data-ttu-id="593f4-107">Para conocer más, consulte [Administrar la configuración de Skype empresarial en el Centro de administración de Microsoft Teams](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json)</span><span class="sxs-lookup"><span data-stu-id="593f4-107">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json).</span></span>

<span data-ttu-id="593f4-108">La configuración de presencia de Skype Empresarial Online proporciona a los usuarios más control sobre quién puede ver si están disponibles, en una reunión o fuera de la oficina.</span><span class="sxs-lookup"><span data-stu-id="593f4-108">The Skype for Business Online presence setting gives people more control over who can see whether they are available, in a meeting, or out of the office.</span></span> <span data-ttu-id="593f4-109">Para obtener más información sobre la presencia y la configuración de privacidad de Skype Empresarial, vea Configurar la [presencia en Skype Empresarial Online.](configure-presence-in-skype-for-business-online.md)</span><span class="sxs-lookup"><span data-stu-id="593f4-109">For details about Skype for Business presence and privacy settings, see [Configure presence in Skype for Business Online](configure-presence-in-skype-for-business-online.md).</span></span> 
  
## <a name="choose-the-default-online-presence-setting-for-everyone-in-your-organization"></a><span data-ttu-id="593f4-110">Elija la configuración de presencia en línea predeterminada para todos los usuarios de su organización</span><span class="sxs-lookup"><span data-stu-id="593f4-110">Choose the default online presence setting for everyone in your organization</span></span>
<span data-ttu-id="593f4-111"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="593f4-111"><a name="__top"> </a></span></span>

1. <span data-ttu-id="593f4-112">Vaya al Centro de administración de Skype Empresarial Online > **Organización > General.**</span><span class="sxs-lookup"><span data-stu-id="593f4-112">Go to the Skype for Business Online admin center > **Organization > General**.</span></span>
    
2. <span data-ttu-id="593f4-113">En **Modo de privacidad de presencia,** elija la configuración y, a continuación, haga clic en **Guardar.**</span><span class="sxs-lookup"><span data-stu-id="593f4-113">Under **Presence privacy mode**, choose the setting, and then click **Save**.</span></span>
    
|<span data-ttu-id="593f4-114">**Setting**</span><span class="sxs-lookup"><span data-stu-id="593f4-114">**Setting**</span></span>|<span data-ttu-id="593f4-115">**Quién puede ver la presencia de un usuario**</span><span class="sxs-lookup"><span data-stu-id="593f4-115">**Who can view a user's presence**</span></span>|
|:-----|:-----|
|<span data-ttu-id="593f4-116">**Mostrar información de presencia automáticamente**</span><span class="sxs-lookup"><span data-stu-id="593f4-116">**Automatically display presence information**</span></span> <br/> |<span data-ttu-id="593f4-117">Todos los usuarios de Skype Empresarial que no pertenezcan a los grupos de privacidad **Externo** o **Bloqueado**.</span><span class="sxs-lookup"><span data-stu-id="593f4-117">Any Skype for Business user who does not belong to the **External** or **Blocked** privacy group.</span></span> <br/> |
|<span data-ttu-id="593f4-118">**Mostrar información de presencia solo a los contactos de un usuario**</span><span class="sxs-lookup"><span data-stu-id="593f4-118">**Display presence information only to a user's contacts**</span></span> <br/> |<span data-ttu-id="593f4-119">Cualquier persona de la lista de contactos de un usuario que no pertenezca al **grupo** de privacidad **Externo** o Bloqueado.</span><span class="sxs-lookup"><span data-stu-id="593f4-119">Anyone in a user's contact list who does not belong to the **External** or **Blocked** privacy group.</span></span> <br/> <span data-ttu-id="593f4-120">Los usuarios individuales pueden cambiar esta configuración en el cuadro de diálogo Opciones **de** Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="593f4-120">Individual users can change this setting in the Skype for Business **Options** dialog box.</span></span> <br/> |
   
## <a name="related-topics"></a><span data-ttu-id="593f4-121">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="593f4-121">Related topics</span></span>
[<span data-ttu-id="593f4-122">Configurar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="593f4-122">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="593f4-123">Permitir que los usuarios de Skype Empresarial agreguen contactos de Skype</span><span class="sxs-lookup"><span data-stu-id="593f4-123">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
