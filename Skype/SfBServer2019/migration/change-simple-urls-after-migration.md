---
title: Cambiar las direcciones URL simples tras la migración
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Skype empresarial Server admite URL simples.
ms.openlocfilehash: ab820c1b24eb9b2e8befc85a34e82d068c9083ea
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813888"
---
# <a name="change-simple-urls-after-migration"></a><span data-ttu-id="90cdd-103">Cambiar las direcciones URL simples tras la migración</span><span class="sxs-lookup"><span data-stu-id="90cdd-103">Change simple URLs after migration</span></span>

<span data-ttu-id="90cdd-104">Skype empresarial Server admite tres direcciones URL simples:</span><span class="sxs-lookup"><span data-stu-id="90cdd-104">Skype for Business Server supports three simple URLs:</span></span>
  
- <span data-ttu-id="90cdd-105">**Reunirse** se usa como la dirección URL base para todas las conferencias del sitio o la organización.</span><span class="sxs-lookup"><span data-stu-id="90cdd-105">**Meet** is used as the base URL for all conferences in the site or organization.</span></span> <span data-ttu-id="90cdd-106">Con la dirección URL simple, los vínculos a las reuniones de unirse son fáciles de comprender y se pueden comunicar y distribuir fácilmente.</span><span class="sxs-lookup"><span data-stu-id="90cdd-106">With the Meet simple URL, links to join meetings are easy to comprehend, and easy to communicate and distribute.</span></span> 
    
- <span data-ttu-id="90cdd-107">El acceso **telefónico** permite el acceso a la Página Web de configuración de conferencias de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="90cdd-107">**Dial-in** enables access to the Dial-in Conferencing Settings webpage.</span></span> <span data-ttu-id="90cdd-108">La dirección URL de acceso telefónico simple está incluida en todas las invitaciones a reuniones para que los usuarios que deseen llamar a la reunión puedan tener acceso a la información del número de teléfono y del PIN necesarios.</span><span class="sxs-lookup"><span data-stu-id="90cdd-108">The Dial-in simple URL is included in all meeting invitations so that users who want to dial in to the meeting can access the necessary phone number and PIN information.</span></span> 
    
- <span data-ttu-id="90cdd-109">El **Administrador** permite acceder rápidamente al panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="90cdd-109">**Admin** enables quick access to the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="90cdd-110">La dirección URL simple de administración es interna de su organización.</span><span class="sxs-lookup"><span data-stu-id="90cdd-110">The Admin simple URL is internal to your organization.</span></span> 
    
<span data-ttu-id="90cdd-111">Después de migrar a Skype empresarial Server, debe tener en cuenta cómo afecta el cambio a los registros DNS y certificados para las direcciones URL simples.</span><span class="sxs-lookup"><span data-stu-id="90cdd-111">After migrating to Skype for Business Server, you must be aware of how the change impacts your DNS records and certificates for simple URLs.</span></span> <span data-ttu-id="90cdd-112">Si el director de Skype empresarial heredado sigue en uso en la topología, no es necesario realizar cambios en las direcciones URL simples.</span><span class="sxs-lookup"><span data-stu-id="90cdd-112">If the legacy Skype for Business Server Director remains in use in the topology, no changes to your simple URLs are required.</span></span> <span data-ttu-id="90cdd-113">Si el director de Skype empresarial Server se quita de la topología después de la migración, los registros DNS de direcciones URL simples deben actualizarse para que apunten a uno de los grupos de servidores de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="90cdd-113">If the Skype for Business Server Director is removed from the topology after migration, the simple URL DNS records must be updated to point to one of the Skype for Business Server pools.</span></span> <span data-ttu-id="90cdd-114">Sin embargo, cada vez que cambie un nombre de dirección URL simple, debe ejecutar enable-CsComputer en cada director y en el servidor front-end para registrar el cambio.</span><span class="sxs-lookup"><span data-stu-id="90cdd-114">Whenever you change a simple URL name, however, you must run Enable-CsComputer on each Director and Front End Server to register the change.</span></span>

## <a name="to-update-the-meet-simple-url"></a><span data-ttu-id="90cdd-115">Para actualizar la dirección URL simple de reunirse</span><span class="sxs-lookup"><span data-stu-id="90cdd-115">To update the Meet simple URL</span></span>

1. <span data-ttu-id="90cdd-116">En el generador de topología, haga clic con el botón derecho en el nodo superior **de Skype empresarial Server**y, a continuación, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="90cdd-116">In Topology Builder, right-click the top node **Skype for Business Server**, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="90cdd-117">Seleccione **URL simples** en el panel izquierdo y, a continuación, debajo de **direcciones URL de reunión:** seleccione la dirección URL de la reunión y haga clic en **Editar URL**.</span><span class="sxs-lookup"><span data-stu-id="90cdd-117">Select **Simple URLs** in the left pane, then below **Meeting URLs:** select the Meet URL and then click **Edit URL**.</span></span>
    
3. <span data-ttu-id="90cdd-118">Actualice la dirección URL con el valor que quiera y haga clic en **Aceptar** para guardar la dirección URL modificada.</span><span class="sxs-lookup"><span data-stu-id="90cdd-118">Update the URL to the value you want, and then click **OK** to save the edited URL.</span></span> 
    
## <a name="to-update-the-admin-simple-url"></a><span data-ttu-id="90cdd-119">Para actualizar la dirección URL simple de administración</span><span class="sxs-lookup"><span data-stu-id="90cdd-119">To update the Admin simple URL</span></span>

1. <span data-ttu-id="90cdd-120">En el generador de topología, haga clic con el botón derecho en el nodo superior **de Skype empresarial Server**y, a continuación, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="90cdd-120">In Topology Builder, right-click the top node **Skype for Business Server**, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="90cdd-121">Seleccione **URL simples** en el panel izquierdo y, a continuación, en **dirección URL de acceso administrativo** , escriba la dirección URL simple que desee para el acceso administrativo al panel de control de Skype empresarial Server y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="90cdd-121">Select **Simple URLs** in the left pane, then below **Administrative access URL** box, enter the simple URL you want for administrative access to Skype for Business Server Control Panel, and then click **OK**.</span></span>
    
   > [!TIP]
   > <span data-ttu-id="90cdd-122">Recomendamos usar la dirección URL más simple posible como dirección URL sencilla de administración.</span><span class="sxs-lookup"><span data-stu-id="90cdd-122">We recommend using the simplest possible URL for the Admin URL.</span></span> <span data-ttu-id="90cdd-123">La opción más sencilla es https://admin. <em> \<dominio\></em>.</span><span class="sxs-lookup"><span data-stu-id="90cdd-123">The simplest option is https://admin.<em>\<domain\></em>.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="90cdd-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="90cdd-124">See also</span></span>

[<span data-ttu-id="90cdd-125">Requisitos de DNS para las direcciones URL simples en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="90cdd-125">DNS requirements for simple URLs in Skype for Business Server</span></span>](../../SfbServer/plan-your-deployment/network-requirements/simple-urls.md)
