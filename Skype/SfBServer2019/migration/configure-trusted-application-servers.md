---
title: Configurar servidores de aplicaciones de confianza
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: En un entorno mixto, si crea un nuevo servidor de aplicaciones de confianza, debe configurar el grupo de próximos saltos para que sea un grupo de servidores de Skype empresarial 2019. En un entorno mixto, tanto el grupo heredado como el grupo de servidores de Skype empresarial 2019 aparecen en la lista desplegable. No se puede seleccionar el grupo heredado.
ms.openlocfilehash: b0dfb9ba1e4744ba3e0ea0c376f67a224e70376a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34289602"
---
# <a name="configure-trusted-application-servers"></a><span data-ttu-id="7a2d8-105">Configurar servidores de aplicaciones de confianza</span><span class="sxs-lookup"><span data-stu-id="7a2d8-105">Configure trusted application servers</span></span>

<span data-ttu-id="7a2d8-106">En un entorno mixto, si crea un nuevo servidor de aplicaciones de confianza, debe configurar el grupo de próximos saltos para que sea un grupo de servidores de Skype empresarial 2019.</span><span class="sxs-lookup"><span data-stu-id="7a2d8-106">In a mixed environment, if you create a new trusted application server, you must set the next hop pool to be a Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="7a2d8-107">En un entorno mixto, tanto el grupo heredado como el grupo de servidores de Skype empresarial 2019 aparecen en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="7a2d8-107">In a mixed environment, both the legacy pool and the Skype for Business Server 2019 pool appear in the drop-down list.</span></span> <span data-ttu-id="7a2d8-108">No se puede seleccionar el grupo heredado.</span><span class="sxs-lookup"><span data-stu-id="7a2d8-108">Selecting the legacy pool is not supported.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="7a2d8-109">Si va a migrar un servidor de aplicaciones de confianza, también debe actualizar la versión de UCMA que está usando.</span><span class="sxs-lookup"><span data-stu-id="7a2d8-109">If you are migrating a trusted application server, you should also update the version of UCMA you are using.</span></span> <span data-ttu-id="7a2d8-110">Si crea un nuevo grupo de aplicaciones de confianza para Skype empresarial Server 2019, debe actualizar UCMA a la versión que se incluye con Skype empresarial Server 2019 o a la versión más reciente disponible.</span><span class="sxs-lookup"><span data-stu-id="7a2d8-110">If you create a new Trusted Application Pool for Skype for Business Server 2019, you should update UCMA to the version that is included with Skype for Business Server 2019 or the latest version available.</span></span> 
  
### <a name="select-skype-for-business-server-2019-as-next-hop-when-creating-a-trusted-application-server"></a><span data-ttu-id="7a2d8-111">Seleccione Skype empresarial Server 2019 como próximo salto al crear un servidor de aplicaciones de confianza</span><span class="sxs-lookup"><span data-stu-id="7a2d8-111">Select Skype for Business Server 2019 as next hop when creating a Trusted application server</span></span>

1. <span data-ttu-id="7a2d8-112">Abra el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="7a2d8-112">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="7a2d8-113">En el panel izquierdo, haga clic con el botón secundario en **servidores de aplicaciones de confianza** y haga clic en **nuevo grupo de aplicaciones de confianza**.</span><span class="sxs-lookup"><span data-stu-id="7a2d8-113">In the left pane, right-click **Trusted application servers** and click **New Trusted Application Pool**.</span></span>
    
3. <span data-ttu-id="7a2d8-114">Escriba el **FQDN del grupo** del grupo de aplicaciones de confianza y seleccione si será de servidor único o de varios servidores.</span><span class="sxs-lookup"><span data-stu-id="7a2d8-114">Enter the **Pool FQDN** of the trusted application pool and select whether it will be single-server or multiple-server.</span></span> 
    
4. <span data-ttu-id="7a2d8-115">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7a2d8-115">Click **Next**.</span></span>
    
5. <span data-ttu-id="7a2d8-116">En la página **seleccionar el próximo salto** , en la lista, seleccione el grupo front-end de Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="7a2d8-116">On the **Select the next hop** page, from the list, select the Skype for Business Server 2019 Front End pool.</span></span> 
    
6. <span data-ttu-id="7a2d8-117">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="7a2d8-117">Click **Finish**.</span></span>
    
7. <span data-ttu-id="7a2d8-118">Seleccione el nodo superior **de Skype empresarial Server**y, en el menú **acción** , seleccione **publicar**.</span><span class="sxs-lookup"><span data-stu-id="7a2d8-118">Select the top node **Skype for Business Server**, and from the **Action** menu select **Publish**.</span></span>
    
    <span data-ttu-id="7a2d8-119">Compruebe que el **grupo de aplicaciones de confianza** se haya creado correctamente y que esté asociado al grupo de servidores front-end correcto.</span><span class="sxs-lookup"><span data-stu-id="7a2d8-119">Verify that the **Trusted Application Pool** has been created successfully and is associated with the correct Front End pool.</span></span> 
    

