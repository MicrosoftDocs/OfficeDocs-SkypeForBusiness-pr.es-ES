---
title: Compatibilidad de Skype Empresarial Online en Outlook en la web
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 305984ec-3da8-4509-bb2b-6643dcf2cb7d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: Outlook en la web (Outlook Web App) en Office 365 ofrece un cliente básico de Skype Empresarial en la barra de navegación. Este cliente básico está disponible para los usuarios en línea cuyo administrador no ha configurado una dirección URL de cortesía para su organización de Office 365. Siempre y cuando la cuenta de usuario está en línea y no tiene una dirección URL mnemónica, seguirán viendo la experiencia incluso si su organización tiene algunas cuentas de usuario que se encuentran ubicados en local. Los usuarios que dispongan de usuario cuentas locales (si tienen una dirección URL de personal o no) o son administrados por Microsoft verán la experiencia de Lync en Outlook web app.
ms.openlocfilehash: 112da508d0f21175d309679a529f86d22a37d0d4
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23863249"
---
# <a name="skype-for-business-online-support-in-outlook-on-the-web"></a><span data-ttu-id="97c5a-106">Compatibilidad de Skype Empresarial Online en Outlook en la web</span><span class="sxs-lookup"><span data-stu-id="97c5a-106">Skype for Business Online support in Outlook on the web</span></span>

<span data-ttu-id="97c5a-107">Outlook en la web (Outlook Web App) en Office 365 ofrece un cliente básico de Skype Empresarial en la barra de navegación.</span><span class="sxs-lookup"><span data-stu-id="97c5a-107">Outlook on the web (Outlook Web App) in Office 365 offers a basic Skype for Business web client from the navigation bar.</span></span> <span data-ttu-id="97c5a-108">Este cliente básico está disponible para los usuarios en línea cuyo administrador no ha configurado una dirección URL de cortesía para su organización de Office 365.</span><span class="sxs-lookup"><span data-stu-id="97c5a-108">This basic client is available for Online users whose admin hasn't configured a vanity URL for their Office 365 organization.</span></span> <span data-ttu-id="97c5a-109">Siempre y cuando la cuenta de usuario está en línea y no tiene una dirección URL mnemónica, seguirán viendo la experiencia incluso si su organización tiene algunas cuentas de usuario que se encuentran ubicados en local.</span><span class="sxs-lookup"><span data-stu-id="97c5a-109">As long as the user's account is online and doesn't have a vanity URL, they will still see the experience even if their organization has some user accounts that are homed on-premises.</span></span> <span data-ttu-id="97c5a-110">Los usuarios que dispongan de usuario cuentas locales (si tienen una dirección URL de personal o no) o son administrados por Microsoft verán la experiencia de Lync en Outlook web app.</span><span class="sxs-lookup"><span data-stu-id="97c5a-110">Users who have user accounts on-premises (whether they have a vanity URL or not) or are managed by Microsoft will see the Lync experience in the Outlook web app.</span></span>
  
<span data-ttu-id="97c5a-111">En la siguiente tabla se resume las diferentes configuraciones que es posible que tenga y el cliente web que se usa.</span><span class="sxs-lookup"><span data-stu-id="97c5a-111">The following table summarizes the different setups that you may have and the web client that is used.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="97c5a-112">**Ubicación de la cuenta de usuario**</span><span class="sxs-lookup"><span data-stu-id="97c5a-112">**User account is located**</span></span> <br/> |<span data-ttu-id="97c5a-113">**Hay una URL mnemónica configurada o una organización dedicada**</span><span class="sxs-lookup"><span data-stu-id="97c5a-113">**Vanity URL is configured or there is a dedicated organization**</span></span> <br/> |<span data-ttu-id="97c5a-114">**Experiencia de Skype Empresarial o Lync**</span><span class="sxs-lookup"><span data-stu-id="97c5a-114">**Skype for Business or Lync Experience?**</span></span> <br/> |
|<span data-ttu-id="97c5a-115">Online</span><span class="sxs-lookup"><span data-stu-id="97c5a-115">Online</span></span>  <br/> |<span data-ttu-id="97c5a-116">No</span><span class="sxs-lookup"><span data-stu-id="97c5a-116">No</span></span>  <br/> |<span data-ttu-id="97c5a-117">Experiencia web de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="97c5a-117">Skype for Business web experience</span></span>  <br/> |
|<span data-ttu-id="97c5a-118">Online</span><span class="sxs-lookup"><span data-stu-id="97c5a-118">Online</span></span>  <br/> |<span data-ttu-id="97c5a-119">Sí</span><span class="sxs-lookup"><span data-stu-id="97c5a-119">Yes</span></span>  <br/> |<span data-ttu-id="97c5a-120">Experiencia web de Lync</span><span class="sxs-lookup"><span data-stu-id="97c5a-120">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="97c5a-121">Híbrida pero hospedada en línea</span><span class="sxs-lookup"><span data-stu-id="97c5a-121">Hybrid but homed online</span></span>  <br/> |<span data-ttu-id="97c5a-122">No</span><span class="sxs-lookup"><span data-stu-id="97c5a-122">No</span></span>  <br/> |<span data-ttu-id="97c5a-123">Experiencia web de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="97c5a-123">Skype for Business web experience</span></span>  <br/> |
|<span data-ttu-id="97c5a-124">Híbrida pero hospedada en línea</span><span class="sxs-lookup"><span data-stu-id="97c5a-124">Hybrid but homed online</span></span>  <br/> |<span data-ttu-id="97c5a-125">Sí</span><span class="sxs-lookup"><span data-stu-id="97c5a-125">Yes</span></span>  <br/> |<span data-ttu-id="97c5a-126">Experiencia web de Lync</span><span class="sxs-lookup"><span data-stu-id="97c5a-126">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="97c5a-127">Híbrida pero hospedada localmente</span><span class="sxs-lookup"><span data-stu-id="97c5a-127">Hybrid but homed on prem</span></span>  <br/> |<span data-ttu-id="97c5a-128">No</span><span class="sxs-lookup"><span data-stu-id="97c5a-128">No</span></span>  <br/> |<span data-ttu-id="97c5a-129">Experiencia web de Lync</span><span class="sxs-lookup"><span data-stu-id="97c5a-129">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="97c5a-130">Híbrida pero hospedada localmente</span><span class="sxs-lookup"><span data-stu-id="97c5a-130">Hybrid but homed on prem</span></span>  <br/> |<span data-ttu-id="97c5a-131">Sí</span><span class="sxs-lookup"><span data-stu-id="97c5a-131">Yes</span></span>  <br/> |<span data-ttu-id="97c5a-132">Experiencia web de Lync</span><span class="sxs-lookup"><span data-stu-id="97c5a-132">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="97c5a-133">Puro en prem</span><span class="sxs-lookup"><span data-stu-id="97c5a-133">Pure on prem</span></span>  <br/> |<span data-ttu-id="97c5a-134">No</span><span class="sxs-lookup"><span data-stu-id="97c5a-134">No</span></span>  <br/> |<span data-ttu-id="97c5a-135">Experiencia web de Lync</span><span class="sxs-lookup"><span data-stu-id="97c5a-135">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="97c5a-136">Puro en prem</span><span class="sxs-lookup"><span data-stu-id="97c5a-136">Pure on prem</span></span>  <br/> |<span data-ttu-id="97c5a-137">Sí</span><span class="sxs-lookup"><span data-stu-id="97c5a-137">Yes</span></span>  <br/> |<span data-ttu-id="97c5a-138">Experiencia web de Lync</span><span class="sxs-lookup"><span data-stu-id="97c5a-138">Lync web experience</span></span>  <br/> |
   

## <a name="related-topics"></a><span data-ttu-id="97c5a-139">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="97c5a-139">Related topics</span></span>
[<span data-ttu-id="97c5a-140">Configurar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="97c5a-140">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="97c5a-141">Permitir que los usuarios de Skype Empresarial agreguen contactos de Skype</span><span class="sxs-lookup"><span data-stu-id="97c5a-141">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 