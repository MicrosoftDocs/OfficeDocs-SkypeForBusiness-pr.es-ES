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
ms.openlocfilehash: f8589dfb648693f0c0c4331a1a16119a3d7fe748
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52239957"
---
# <a name="configure-presence-privacy-mode"></a><span data-ttu-id="e8e0d-103">Configurar el modo de privacidad de presencia</span><span class="sxs-lookup"><span data-stu-id="e8e0d-103">Configure presence privacy mode</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!IMPORTANT]
> <span data-ttu-id="e8e0d-104">El Microsoft Teams de administración ha sustituido al Skype Empresarial de administración (portal heredado).</span><span class="sxs-lookup"><span data-stu-id="e8e0d-104">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="e8e0d-105">Todas las opciones de Skype Empresarial están ahora en el centro Teams administración.</span><span class="sxs-lookup"><span data-stu-id="e8e0d-105">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="e8e0d-106">Debe tener asignado el rol de administrador de [Azure AD](/azure/active-directory/roles/permissions-reference) de administrador global o Skype Empresarial administrador para administrar Skype Empresarial características en el centro Teams administración.</span><span class="sxs-lookup"><span data-stu-id="e8e0d-106">You must be assigned the [Azure AD admin role](/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Teams admin center.</span></span> <span data-ttu-id="e8e0d-107">Para conocer más, consulte [Administrar la configuración de Skype empresarial en el Centro de administración de Microsoft Teams](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json)</span><span class="sxs-lookup"><span data-stu-id="e8e0d-107">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json).</span></span>

<span data-ttu-id="e8e0d-108">La Skype Empresarial presencia en línea proporciona a los usuarios más control sobre quién puede ver si están disponibles, en una reunión o fuera de la oficina.</span><span class="sxs-lookup"><span data-stu-id="e8e0d-108">The Skype for Business Online presence setting gives people more control over who can see whether they are available, in a meeting, or out of the office.</span></span> <span data-ttu-id="e8e0d-109">Para obtener más información Skype Empresarial configuración de privacidad y presencia, vea Configurar la presencia [en Skype Empresarial online.](configure-presence-in-skype-for-business-online.md)</span><span class="sxs-lookup"><span data-stu-id="e8e0d-109">For details about Skype for Business presence and privacy settings, see [Configure presence in Skype for Business Online](configure-presence-in-skype-for-business-online.md).</span></span> 
  
## <a name="choose-the-default-online-presence-setting-for-everyone-in-your-organization"></a><span data-ttu-id="e8e0d-110">Elija la configuración de presencia en línea predeterminada para todos los usuarios de su organización</span><span class="sxs-lookup"><span data-stu-id="e8e0d-110">Choose the default online presence setting for everyone in your organization</span></span>
<span data-ttu-id="e8e0d-111"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="e8e0d-111"><a name="__top"> </a></span></span>

1. <span data-ttu-id="e8e0d-112">Vaya al Centro Skype Empresarial administración en línea > **Organización > General**.</span><span class="sxs-lookup"><span data-stu-id="e8e0d-112">Go to the Skype for Business Online admin center > **Organization > General**.</span></span>
    
2. <span data-ttu-id="e8e0d-113">En **Modo de privacidad de presencia,** elija la configuración y, a continuación, haga clic en **Guardar.**</span><span class="sxs-lookup"><span data-stu-id="e8e0d-113">Under **Presence privacy mode**, choose the setting, and then click **Save**.</span></span>
    
|<span data-ttu-id="e8e0d-114">**Setting**</span><span class="sxs-lookup"><span data-stu-id="e8e0d-114">**Setting**</span></span>|<span data-ttu-id="e8e0d-115">**Quién puede ver la presencia de un usuario**</span><span class="sxs-lookup"><span data-stu-id="e8e0d-115">**Who can view a user's presence**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e8e0d-116">**Mostrar información de presencia automáticamente**</span><span class="sxs-lookup"><span data-stu-id="e8e0d-116">**Automatically display presence information**</span></span> <br/> |<span data-ttu-id="e8e0d-117">Todos los usuarios de Skype Empresarial que no pertenezcan a los grupos de privacidad **Externo** o **Bloqueado**.</span><span class="sxs-lookup"><span data-stu-id="e8e0d-117">Any Skype for Business user who does not belong to the **External** or **Blocked** privacy group.</span></span> <br/> |
|<span data-ttu-id="e8e0d-118">**Mostrar información de presencia solo a los contactos de un usuario**</span><span class="sxs-lookup"><span data-stu-id="e8e0d-118">**Display presence information only to a user's contacts**</span></span> <br/> |<span data-ttu-id="e8e0d-119">Cualquier persona de la lista de contactos de un usuario que no pertenezca al **grupo** de privacidad **Externo** o Bloqueado.</span><span class="sxs-lookup"><span data-stu-id="e8e0d-119">Anyone in a user's contact list who does not belong to the **External** or **Blocked** privacy group.</span></span> <br/> <span data-ttu-id="e8e0d-120">Los usuarios individuales pueden cambiar  esta configuración en el cuadro de diálogo Skype Empresarial opciones.</span><span class="sxs-lookup"><span data-stu-id="e8e0d-120">Individual users can change this setting in the Skype for Business **Options** dialog box.</span></span> <br/> |
   
## <a name="related-topics"></a><span data-ttu-id="e8e0d-121">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="e8e0d-121">Related topics</span></span>
[<span data-ttu-id="e8e0d-122">Configurar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="e8e0d-122">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="e8e0d-123">Permitir que los usuarios de Skype Empresarial agreguen contactos de Skype</span><span class="sxs-lookup"><span data-stu-id="e8e0d-123">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
