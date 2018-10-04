---
title: Direcciones URL sencillas de cambio después de la migración
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype para Business Server es compatible con las direcciones URL sencillas.
ms.openlocfilehash: 71935aab09de1598b355d2a7b27dfa02fd169216
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25374993"
---
# <a name="change-simple-urls-after-migration"></a><span data-ttu-id="0504c-103">Direcciones URL sencillas de cambio después de la migración</span><span class="sxs-lookup"><span data-stu-id="0504c-103">Change simple URLs after migration</span></span>

<span data-ttu-id="0504c-104">Skype para Business Server admite tres direcciones URL sencillas:</span><span class="sxs-lookup"><span data-stu-id="0504c-104">Skype for Business Server supports three simple URLs:</span></span>
  
- <span data-ttu-id="0504c-105">**Cumplir** se usa como la dirección URL base para todas las conferencias en el sitio o la organización.</span><span class="sxs-lookup"><span data-stu-id="0504c-105">**Meet** is used as the base URL for all conferences in the site or organization.</span></span> <span data-ttu-id="0504c-106">Con la URL simples de reunión, vínculos a unirse a reuniones son fáciles de comprender y fácil de comunicarse y distribuir.</span><span class="sxs-lookup"><span data-stu-id="0504c-106">With the Meet simple URL, links to join meetings are easy to comprehend, and easy to communicate and distribute.</span></span> 
    
- <span data-ttu-id="0504c-107">**Dial-in** habilita el acceso a la página Web de configuración de conferencia de acceso telefónico.</span><span class="sxs-lookup"><span data-stu-id="0504c-107">**Dial-in** enables access to the Dial-in Conferencing Settings webpage.</span></span> <span data-ttu-id="0504c-108">La dirección URL sencilla de marcado se incluye en todas las invitaciones a reuniones para que los usuarios que deseen conectarse a la reunión pueden tener acceso a la información de PIN y número de teléfono es necesario.</span><span class="sxs-lookup"><span data-stu-id="0504c-108">The Dial-in simple URL is included in all meeting invitations so that users who want to dial in to the meeting can access the necessary phone number and PIN information.</span></span> 
    
- <span data-ttu-id="0504c-109">**Admin** permite el acceso rápido a la Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="0504c-109">**Admin** enables quick access to the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="0504c-110">La dirección URL de administración simple es interna a la organización.</span><span class="sxs-lookup"><span data-stu-id="0504c-110">The Admin simple URL is internal to your organization.</span></span> 
    
<span data-ttu-id="0504c-111">Después de migrar a Skype para Business Server, debe tener en cuenta cómo afecta el cambio a sus registros DNS y los certificados para las direcciones URL sencillas.</span><span class="sxs-lookup"><span data-stu-id="0504c-111">After migrating to Skype for Business Server, you must be aware of how the change impacts your DNS records and certificates for simple URLs.</span></span> <span data-ttu-id="0504c-112">Si el Director del servidor para profesionales de Skype heredado permanece en uso en la topología, se requiere ningún cambio en las direcciones URL sencillas.</span><span class="sxs-lookup"><span data-stu-id="0504c-112">If the legacy Skype for Business Server Director remains in use in the topology, no changes to your simple URLs are required.</span></span> <span data-ttu-id="0504c-113">Si el Director del servidor para profesionales de Skype se ha quitado de la topología de después de la migración, se deben actualizar los registros DNS de la dirección URL simples para que apunte a uno de los Skype para grupos de servidores de negocio.</span><span class="sxs-lookup"><span data-stu-id="0504c-113">If the Skype for Business Server Director is removed from the topology after migration, the simple URL DNS records must be updated to point to one of the Skype for Business Server pools.</span></span> <span data-ttu-id="0504c-114">Sin embargo, cada vez que cambie un nombre de dirección URL simple, debe ejecutar Enable-CsComputer en cada Director y el servidor Front-End para registrar el cambio.</span><span class="sxs-lookup"><span data-stu-id="0504c-114">Whenever you change a simple URL name, however, you must run Enable-CsComputer on each Director and Front End Server to register the change.</span></span>

## <a name="to-update-the-meet-simple-url"></a><span data-ttu-id="0504c-115">Para actualizar la URL simples de reunión</span><span class="sxs-lookup"><span data-stu-id="0504c-115">To update the Meet simple URL</span></span>

1. <span data-ttu-id="0504c-116">En el generador, haga clic en el nodo superior **Skype para Business Server**y, a continuación, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="0504c-116">In Topology Builder, right-click the top node **Skype for Business Server**, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="0504c-117">Seleccione **Direcciones URL simples** en el panel izquierdo, a continuación, debajo de **direcciones URL de reunión:** seleccione la dirección URL de la reunión y, a continuación, haga clic en **Editar dirección URL**.</span><span class="sxs-lookup"><span data-stu-id="0504c-117">Select **Simple URLs** in the left pane, then below **Meeting URLs:** select the Meet URL and then click **Edit URL**.</span></span>
    
3. <span data-ttu-id="0504c-118">Actualice la dirección URL con el valor que quiera y haga clic en **Aceptar** para guardar la dirección URL modificada.</span><span class="sxs-lookup"><span data-stu-id="0504c-118">Update the URL to the value you want, and then click **OK** to save the edited URL.</span></span> 
    
## <a name="to-update-the-admin-simple-url"></a><span data-ttu-id="0504c-119">Para actualizar la dirección URL de administración simple</span><span class="sxs-lookup"><span data-stu-id="0504c-119">To update the Admin simple URL</span></span>

1. <span data-ttu-id="0504c-120">En el generador, haga clic en el nodo superior **Skype para Business Server**y, a continuación, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="0504c-120">In Topology Builder, right-click the top node **Skype for Business Server**, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="0504c-121">Seleccione **Direcciones URL simples** en el panel izquierdo, a continuación, debajo de cuadro de **dirección URL de acceso administrativo** , escriba la dirección URL sencilla que desee para el acceso administrativo a Skype para el Panel de Control de servidor empresarial y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0504c-121">Select **Simple URLs** in the left pane, then below **Administrative access URL** box, enter the simple URL you want for administrative access to Skype for Business Server Control Panel, and then click **OK**.</span></span>
    
   > [!TIP]
   > <span data-ttu-id="0504c-122">Recomendamos usar la dirección URL más simple posible como dirección URL sencilla de administración.</span><span class="sxs-lookup"><span data-stu-id="0504c-122">We recommend using the simplest possible URL for the Admin URL.</span></span> <span data-ttu-id="0504c-123">La opción más sencilla es https://admin. <em> \<dominio\></em>.</span><span class="sxs-lookup"><span data-stu-id="0504c-123">The simplest option is https://admin.<em>\<domain\></em>.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="0504c-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="0504c-124">See also</span></span>

[<span data-ttu-id="0504c-125">Requisitos de DNS para direcciones URL simples en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="0504c-125">DNS requirements for simple URLs in Skype for Business Server</span></span>](../../SfbServer/plan-your-deployment/network-requirements/simple-urls.md)
