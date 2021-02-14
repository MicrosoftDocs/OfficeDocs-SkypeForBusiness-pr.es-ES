---
title: Cambiar las direcciones URL simples tras la migración
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Skype Empresarial Server admite direcciones URL sencillas.
ms.openlocfilehash: 1b25dd74f5bdca433554091b3f8ce1c1d2dfa8ce
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753910"
---
# <a name="change-simple-urls-after-migration"></a><span data-ttu-id="9642e-103">Cambiar las direcciones URL simples tras la migración</span><span class="sxs-lookup"><span data-stu-id="9642e-103">Change simple URLs after migration</span></span>

<span data-ttu-id="9642e-104">Skype Empresarial Server admite tres direcciones URL sencillas:</span><span class="sxs-lookup"><span data-stu-id="9642e-104">Skype for Business Server supports three simple URLs:</span></span>
  
- <span data-ttu-id="9642e-p101">**Reunión** sirve como dirección URL base de todas las conferencias del sitio o la organización. Con una dirección URL simple de reunión, los vínculos para unirse a reuniones son fáciles de identificar, comunicar y distribuir.</span><span class="sxs-lookup"><span data-stu-id="9642e-p101">**Meet** is used as the base URL for all conferences in the site or organization. With the Meet simple URL, links to join meetings are easy to comprehend, and easy to communicate and distribute.</span></span> 
    
- <span data-ttu-id="9642e-p102">**Acceso telefónico** permite el acceso a la página web Configuración de conferencia de acceso telefónico local. La dirección URL simple de acceso telefónico aparece en todas las invitaciones a reuniones para que los usuarios que marquen para unirse a la reunión puedan tener acceso al número de teléfono e información de PIN necesarios.</span><span class="sxs-lookup"><span data-stu-id="9642e-p102">**Dial-in** enables access to the Dial-in Conferencing Settings webpage. The Dial-in simple URL is included in all meeting invitations so that users who want to dial in to the meeting can access the necessary phone number and PIN information.</span></span> 
    
- <span data-ttu-id="9642e-109">**La** administración permite el acceso rápido al Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="9642e-109">**Admin** enables quick access to the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="9642e-110">La dirección URL simple de administración es de uso interno para la organización.</span><span class="sxs-lookup"><span data-stu-id="9642e-110">The Admin simple URL is internal to your organization.</span></span> 
    
<span data-ttu-id="9642e-111">Después de migrar a Skype Empresarial Server, debe conocer cómo afecta el cambio a los certificados y registros DNS para direcciones URL sencillas.</span><span class="sxs-lookup"><span data-stu-id="9642e-111">After migrating to Skype for Business Server, you must be aware of how the change impacts your DNS records and certificates for simple URLs.</span></span> <span data-ttu-id="9642e-112">Si el director heredado de Skype Empresarial Server permanece en uso en la topología, no es necesario realizar cambios en las direcciones URL sencillas.</span><span class="sxs-lookup"><span data-stu-id="9642e-112">If the legacy Skype for Business Server Director remains in use in the topology, no changes to your simple URLs are required.</span></span> <span data-ttu-id="9642e-113">Si el director de Skype Empresarial Server se quita de la topología después de la migración, los registros DNS de la dirección URL sencilla deben actualizarse para que apunten a uno de los grupos de servidores de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="9642e-113">If the Skype for Business Server Director is removed from the topology after migration, the simple URL DNS records must be updated to point to one of the Skype for Business Server pools.</span></span> <span data-ttu-id="9642e-114">Sin embargo, cuando modifique el nombre de una dirección URL simple, deberá ejecutar Enable-CsComputer en cada director y servidor front-end para registrar el cambio.</span><span class="sxs-lookup"><span data-stu-id="9642e-114">Whenever you change a simple URL name, however, you must run Enable-CsComputer on each Director and Front End Server to register the change.</span></span>

## <a name="to-update-the-meet-simple-url"></a><span data-ttu-id="9642e-115">Para actualizar las direcciones URL simples de reunión</span><span class="sxs-lookup"><span data-stu-id="9642e-115">To update the Meet simple URL</span></span>

1. <span data-ttu-id="9642e-116">En el Generador de topologías, haga clic con el botón secundario en el nodo superior **de Skype Empresarial Server** y, a continuación, haga clic en Editar **propiedades.**</span><span class="sxs-lookup"><span data-stu-id="9642e-116">In Topology Builder, right-click the top node **Skype for Business Server**, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="9642e-117">Seleccione **Direcciones URL sencillas** en el panel izquierdo y, a continuación, debajo de Direcciones URL de **reunión:** seleccione la dirección URL de reunión y, a continuación, haga clic **en Editar dirección URL.**</span><span class="sxs-lookup"><span data-stu-id="9642e-117">Select **Simple URLs** in the left pane, then below **Meeting URLs:** select the Meet URL and then click **Edit URL**.</span></span>
    
3. <span data-ttu-id="9642e-118">Actualice la dirección URL al valor deseado y haga clic en **Aceptar** para guardar la dirección URL modificada.</span><span class="sxs-lookup"><span data-stu-id="9642e-118">Update the URL to the value you want, and then click **OK** to save the edited URL.</span></span> 
    
## <a name="to-update-the-admin-simple-url"></a><span data-ttu-id="9642e-119">Para actualizar las direcciones URL simples de administración</span><span class="sxs-lookup"><span data-stu-id="9642e-119">To update the Admin simple URL</span></span>

1. <span data-ttu-id="9642e-120">En el Generador de topologías, haga clic con el botón secundario en el nodo superior **de Skype Empresarial Server** y, a continuación, haga clic en Editar **propiedades.**</span><span class="sxs-lookup"><span data-stu-id="9642e-120">In Topology Builder, right-click the top node **Skype for Business Server**, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="9642e-121">Seleccione **Direcciones URL** sencillas en el panel izquierdo y, a continuación, debajo del cuadro Dirección **URL** de acceso administrativo, escriba la dirección URL sencilla que desea para el acceso administrativo al Panel de control de Skype Empresarial Server y, a continuación, haga clic en **Aceptar.**</span><span class="sxs-lookup"><span data-stu-id="9642e-121">Select **Simple URLs** in the left pane, then below **Administrative access URL** box, enter the simple URL you want for administrative access to Skype for Business Server Control Panel, and then click **OK**.</span></span>
    
   > [!TIP]
   > <span data-ttu-id="9642e-122">Recomendamos usar la dirección URL más simple posible para la dirección URL de administración.</span><span class="sxs-lookup"><span data-stu-id="9642e-122">We recommend using the simplest possible URL for the Admin URL.</span></span> <span data-ttu-id="9642e-123">La opción más sencilla es https://admin ... <em>\<domain\></em></span><span class="sxs-lookup"><span data-stu-id="9642e-123">The simplest option is https://admin.<em>\<domain\></em>.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="9642e-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="9642e-124">See also</span></span>

[<span data-ttu-id="9642e-125">Requisitos de DNS para direcciones URL sencillas en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="9642e-125">DNS requirements for simple URLs in Skype for Business Server</span></span>](../../SfbServer/plan-your-deployment/network-requirements/simple-urls.md)
