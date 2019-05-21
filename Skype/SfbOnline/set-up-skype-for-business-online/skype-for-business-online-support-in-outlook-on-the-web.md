---
title: Compatibilidad de Skype Empresarial Online en Outlook en la web
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 305984ec-3da8-4509-bb2b-6643dcf2cb7d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: Outlook en la web (Outlook Web App) en Office 365 ofrece un cliente básico de Skype Empresarial en la barra de navegación. Este cliente básico está disponible para los usuarios en línea cuyo administrador no ha configurado una dirección URL de cortesía para su organización de Office 365. Siempre que la cuenta del usuario esté conectada y no tenga una dirección URL de cortesía, la persona seguirá viendo la experiencia incluso si su organización tiene algunas cuentas de usuario que se encuentran en el modo local. Los usuarios que tienen cuentas de usuario locales (ya tengan una dirección URL de cortesía o no) o que administra Microsoft verán la experiencia de Lync en Outlook Web App.
ms.openlocfilehash: 3a985bd8ad0a04198501ca8d1ec780496c59f561
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34285088"
---
# <a name="skype-for-business-online-support-in-outlook-on-the-web"></a><span data-ttu-id="0ac36-106">Compatibilidad de Skype Empresarial Online en Outlook en la web</span><span class="sxs-lookup"><span data-stu-id="0ac36-106">Skype for Business Online support in Outlook on the web</span></span>

<span data-ttu-id="0ac36-107">[] Outlook en la web (Outlook Web App) en Office 365 ofrece un cliente básico de Skype Empresarial en la barra de navegación.</span><span class="sxs-lookup"><span data-stu-id="0ac36-107">Outlook on the web (Outlook Web App) in Office 365 offers a basic Skype for Business web client from the navigation bar.</span></span> <span data-ttu-id="0ac36-108">Este cliente básico está disponible para los usuarios en línea cuyo administrador no ha configurado una dirección URL de cortesía para su organización de Office 365.</span><span class="sxs-lookup"><span data-stu-id="0ac36-108">This basic client is available for Online users whose admin hasn't configured a vanity URL for their Office 365 organization.</span></span> <span data-ttu-id="0ac36-109">Siempre que la cuenta del usuario esté conectada y no tenga una dirección URL de cortesía, la persona seguirá viendo la experiencia incluso si su organización tiene algunas cuentas de usuario que se encuentran en el modo local.</span><span class="sxs-lookup"><span data-stu-id="0ac36-109">As long as the user's account is online and doesn't have a vanity URL, they will still see the experience even if their organization has some user accounts that are homed on-premises.</span></span> <span data-ttu-id="0ac36-110">Los usuarios que tienen cuentas de usuario locales (ya tengan una dirección URL de cortesía o no) o que administra Microsoft verán la experiencia de Lync en Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="0ac36-110">Users who have user accounts on-premises (whether they have a vanity URL or not) or are managed by Microsoft will see the Lync experience in the Outlook web app.</span></span>
  
<span data-ttu-id="0ac36-111">En la tabla siguiente se resumen las distintas configuraciones que puede tener y el cliente web que se usa.</span><span class="sxs-lookup"><span data-stu-id="0ac36-111">The following table summarizes the different setups that you may have and the web client that is used.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="0ac36-112">**Ubicación de la cuenta de usuario**</span><span class="sxs-lookup"><span data-stu-id="0ac36-112">**User account is located**</span></span> <br/> |<span data-ttu-id="0ac36-113">**Hay una URL mnemónica configurada o una organización dedicada**</span><span class="sxs-lookup"><span data-stu-id="0ac36-113">**Vanity URL is configured or there is a dedicated organization**</span></span> <br/> |<span data-ttu-id="0ac36-114">**Experiencia de Skype Empresarial o Lync**</span><span class="sxs-lookup"><span data-stu-id="0ac36-114">**Skype for Business or Lync Experience?**</span></span> <br/> |
|<span data-ttu-id="0ac36-115">Online</span><span class="sxs-lookup"><span data-stu-id="0ac36-115">Online</span></span>  <br/> |<span data-ttu-id="0ac36-116">No</span><span class="sxs-lookup"><span data-stu-id="0ac36-116">No</span></span>  <br/> |<span data-ttu-id="0ac36-117">Experiencia web de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="0ac36-117">Skype for Business web experience</span></span>  <br/> |
|<span data-ttu-id="0ac36-118">Online</span><span class="sxs-lookup"><span data-stu-id="0ac36-118">Online</span></span>  <br/> |<span data-ttu-id="0ac36-119">Sí</span><span class="sxs-lookup"><span data-stu-id="0ac36-119">Yes</span></span>  <br/> |<span data-ttu-id="0ac36-120">Experiencia web de Lync</span><span class="sxs-lookup"><span data-stu-id="0ac36-120">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="0ac36-121">Híbrida pero hospedada en línea</span><span class="sxs-lookup"><span data-stu-id="0ac36-121">Hybrid but homed online</span></span>  <br/> |<span data-ttu-id="0ac36-122">No</span><span class="sxs-lookup"><span data-stu-id="0ac36-122">No</span></span>  <br/> |<span data-ttu-id="0ac36-123">Experiencia web de Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="0ac36-123">Skype for Business web experience</span></span>  <br/> |
|<span data-ttu-id="0ac36-124">Híbrida pero hospedada en línea</span><span class="sxs-lookup"><span data-stu-id="0ac36-124">Hybrid but homed online</span></span>  <br/> |<span data-ttu-id="0ac36-125">Sí</span><span class="sxs-lookup"><span data-stu-id="0ac36-125">Yes</span></span>  <br/> |<span data-ttu-id="0ac36-126">Experiencia web de Lync</span><span class="sxs-lookup"><span data-stu-id="0ac36-126">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="0ac36-127">Híbrida pero hospedada localmente</span><span class="sxs-lookup"><span data-stu-id="0ac36-127">Hybrid but homed on prem</span></span>  <br/> |<span data-ttu-id="0ac36-128">No</span><span class="sxs-lookup"><span data-stu-id="0ac36-128">No</span></span>  <br/> |<span data-ttu-id="0ac36-129">Experiencia web de Lync</span><span class="sxs-lookup"><span data-stu-id="0ac36-129">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="0ac36-130">Híbrida pero hospedada localmente</span><span class="sxs-lookup"><span data-stu-id="0ac36-130">Hybrid but homed on prem</span></span>  <br/> |<span data-ttu-id="0ac36-131">Sí</span><span class="sxs-lookup"><span data-stu-id="0ac36-131">Yes</span></span>  <br/> |<span data-ttu-id="0ac36-132">Experiencia web de Lync</span><span class="sxs-lookup"><span data-stu-id="0ac36-132">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="0ac36-133">Local puro</span><span class="sxs-lookup"><span data-stu-id="0ac36-133">Pure on prem</span></span>  <br/> |<span data-ttu-id="0ac36-134">No</span><span class="sxs-lookup"><span data-stu-id="0ac36-134">No</span></span>  <br/> |<span data-ttu-id="0ac36-135">Experiencia web de Lync</span><span class="sxs-lookup"><span data-stu-id="0ac36-135">Lync web experience</span></span>  <br/> |
|<span data-ttu-id="0ac36-136">Local puro</span><span class="sxs-lookup"><span data-stu-id="0ac36-136">Pure on prem</span></span>  <br/> |<span data-ttu-id="0ac36-137">Sí</span><span class="sxs-lookup"><span data-stu-id="0ac36-137">Yes</span></span>  <br/> |<span data-ttu-id="0ac36-138">Experiencia web de Lync</span><span class="sxs-lookup"><span data-stu-id="0ac36-138">Lync web experience</span></span>  <br/> |
   

## <a name="related-topics"></a><span data-ttu-id="0ac36-139">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="0ac36-139">Related topics</span></span>
[<span data-ttu-id="0ac36-140">Configurar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="0ac36-140">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="0ac36-141">Permitir que los usuarios de Skype Empresarial agreguen contactos de Skype</span><span class="sxs-lookup"><span data-stu-id="0ac36-141">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
