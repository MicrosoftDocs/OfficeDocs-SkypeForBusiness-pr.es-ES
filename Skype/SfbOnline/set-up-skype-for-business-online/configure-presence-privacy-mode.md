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
description: 'Obtenga información sobre cómo configurar el modo de privacidad para sus usuarios para que puedan controlar mejor cómo ven los usuarios su disponibilidad. '
ms.openlocfilehash: a2b4ed11f1d56927a4bc7eed6ce36b5b04411509
ms.sourcegitcommit: a5bc64abb02201cb5c2ff6696f6ef99064e1cae7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753445"
---
# <a name="configure-presence-privacy-mode"></a><span data-ttu-id="89fe4-103">Configurar el modo de privacidad de presencia</span><span class="sxs-lookup"><span data-stu-id="89fe4-103">Configure presence privacy mode</span></span>

> [!IMPORTANT]
> <span data-ttu-id="89fe4-104">El Centro de administración de Microsoft Teams ha sustituido al Centro de administración de Skype Empresarial (portal heredado).</span><span class="sxs-lookup"><span data-stu-id="89fe4-104">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="89fe4-105">Todas las configuraciones para administrar Skype Empresarial se encuentran ahora en el Centro de administración de Teams.</span><span class="sxs-lookup"><span data-stu-id="89fe4-105">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="89fe4-106">Debe tener asignado el rol de administrador de [Azure AD](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) de Administrador global o de administrador de Skype Empresarial para administrar las características de Skype Empresarial en el Centro de administración de Teams.</span><span class="sxs-lookup"><span data-stu-id="89fe4-106">You must be assigned the [Azure AD admin role](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Teams admin center.</span></span> <span data-ttu-id="89fe4-107">Para conocer más, consulte [Administrar la configuración de Skype empresarial en el Centro de administración de Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json)</span><span class="sxs-lookup"><span data-stu-id="89fe4-107">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).</span></span>

<span data-ttu-id="89fe4-108">La configuración de presencia de Skype Empresarial Online proporciona a los usuarios más control sobre quién puede ver si están disponibles, en una reunión o fuera de la oficina.</span><span class="sxs-lookup"><span data-stu-id="89fe4-108">The Skype for Business Online presence setting gives people more control over who can see whether they are available, in a meeting, or out of the office.</span></span> <span data-ttu-id="89fe4-109">Para obtener más información sobre la configuración de privacidad y presencia de Skype Empresarial, consulte Configurar la presencia [en Skype Empresarial Online.](configure-presence-in-skype-for-business-online.md)</span><span class="sxs-lookup"><span data-stu-id="89fe4-109">For details about Skype for Business presence and privacy settings, see [Configure presence in Skype for Business Online](configure-presence-in-skype-for-business-online.md).</span></span> 
  
## <a name="choose-the-default-online-presence-setting-for-everyone-in-your-organization"></a><span data-ttu-id="89fe4-110">Elija la configuración de presencia en línea predeterminada para todos los usuarios de su organización</span><span class="sxs-lookup"><span data-stu-id="89fe4-110">Choose the default online presence setting for everyone in your organization</span></span>
<span data-ttu-id="89fe4-111"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="89fe4-111"><a name="__top"> </a></span></span>

1. <span data-ttu-id="89fe4-112">Vaya al Centro de administración de Skype Empresarial Online > **Organización > General.**</span><span class="sxs-lookup"><span data-stu-id="89fe4-112">Go to the Skype for Business Online admin center > **Organization > General**.</span></span>
    
2. <span data-ttu-id="89fe4-113">En **Modo de privacidad de** presencia, elija la configuración y, a continuación, haga clic en **Guardar.**</span><span class="sxs-lookup"><span data-stu-id="89fe4-113">Under **Presence privacy mode**, choose the setting, and then click **Save**.</span></span>
    
|<span data-ttu-id="89fe4-114">**Setting**</span><span class="sxs-lookup"><span data-stu-id="89fe4-114">**Setting**</span></span>|<span data-ttu-id="89fe4-115">**Quién puede ver la presencia de un usuario**</span><span class="sxs-lookup"><span data-stu-id="89fe4-115">**Who can view a user's presence**</span></span>|
|:-----|:-----|
|<span data-ttu-id="89fe4-116">**Mostrar información de presencia automáticamente**</span><span class="sxs-lookup"><span data-stu-id="89fe4-116">**Automatically display presence information**</span></span> <br/> |<span data-ttu-id="89fe4-117">Todos los usuarios de Skype Empresarial que no pertenezcan a los grupos de privacidad **Externo** o **Bloqueado**.</span><span class="sxs-lookup"><span data-stu-id="89fe4-117">Any Skype for Business user who does not belong to the **External** or **Blocked** privacy group.</span></span> <br/> |
|<span data-ttu-id="89fe4-118">**Mostrar la información de presencia solo a los contactos de un usuario**</span><span class="sxs-lookup"><span data-stu-id="89fe4-118">**Display presence information only to a user's contacts**</span></span> <br/> |<span data-ttu-id="89fe4-119">Cualquier persona de la lista de contactos de un usuario que no pertenezca al **grupo de** **privacidad** externa o bloqueada.</span><span class="sxs-lookup"><span data-stu-id="89fe4-119">Anyone in a user's contact list who does not belong to the **External** or **Blocked** privacy group.</span></span> <br/> <span data-ttu-id="89fe4-120">Los usuarios individuales pueden cambiar esta configuración en el cuadro de diálogo **Opciones de** Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="89fe4-120">Individual users can change this setting in the Skype for Business **Options** dialog box.</span></span> <br/> |
   
## <a name="related-topics"></a><span data-ttu-id="89fe4-121">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="89fe4-121">Related topics</span></span>
[<span data-ttu-id="89fe4-122">Configurar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="89fe4-122">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="89fe4-123">Permitir que los usuarios de Skype Empresarial agreguen contactos de Skype</span><span class="sxs-lookup"><span data-stu-id="89fe4-123">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
