---
title: Configuración de servidores de aplicaciones de confianza
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
description: En un entorno mixto, si crea un nuevo servidor de aplicaciones de confianza, debe configurar el grupo de servidores del próximo salto para que sea un grupo de Skype Empresarial Server 2019. En un entorno mixto, tanto el grupo heredado como el grupo de Skype Empresarial Server 2019 aparecen en la lista desplegable. No se admite la selección del grupo heredado.
ms.openlocfilehash: 1c0aac1efa4f83a81ccf2f3bb5ecbc925ee58839
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753950"
---
# <a name="configure-trusted-application-servers"></a><span data-ttu-id="958d7-105">Configuración de servidores de aplicaciones de confianza</span><span class="sxs-lookup"><span data-stu-id="958d7-105">Configure trusted application servers</span></span>

<span data-ttu-id="958d7-106">En un entorno mixto, si crea un nuevo servidor de aplicaciones de confianza, debe configurar el grupo de servidores del próximo salto para que sea un grupo de Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="958d7-106">In a mixed environment, if you create a new trusted application server, you must set the next hop pool to be a Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="958d7-107">En un entorno mixto, tanto el grupo heredado como el grupo de Skype Empresarial Server 2019 aparecen en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="958d7-107">In a mixed environment, both the legacy pool and the Skype for Business Server 2019 pool appear in the drop-down list.</span></span> <span data-ttu-id="958d7-108">No se admite la selección del grupo heredado.</span><span class="sxs-lookup"><span data-stu-id="958d7-108">Selecting the legacy pool is not supported.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="958d7-109">Si va a migrar un servidor de aplicaciones de confianza, también debe actualizar la versión de UCMA que está usando.</span><span class="sxs-lookup"><span data-stu-id="958d7-109">If you are migrating a trusted application server, you should also update the version of UCMA you are using.</span></span> <span data-ttu-id="958d7-110">Si crea un nuevo grupo de aplicaciones de confianza para Skype Empresarial Server 2019, debe actualizar UCMA a la versión que se incluye con Skype Empresarial Server 2019 o a la versión más reciente disponible.</span><span class="sxs-lookup"><span data-stu-id="958d7-110">If you create a new Trusted Application Pool for Skype for Business Server 2019, you should update UCMA to the version that is included with Skype for Business Server 2019 or the latest version available.</span></span> 
  
### <a name="select-skype-for-business-server-2019-as-next-hop-when-creating-a-trusted-application-server"></a><span data-ttu-id="958d7-111">Seleccionar Skype Empresarial Server 2019 como próximo salto al crear un servidor de aplicaciones de confianza</span><span class="sxs-lookup"><span data-stu-id="958d7-111">Select Skype for Business Server 2019 as next hop when creating a Trusted application server</span></span>

1. <span data-ttu-id="958d7-112">Abra el Generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="958d7-112">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="958d7-113">En el panel izquierdo, haga clic con el botón secundario en **Servidores de aplicaciones de** confianza y haga clic en Nuevo grupo de aplicaciones de **confianza.**</span><span class="sxs-lookup"><span data-stu-id="958d7-113">In the left pane, right-click **Trusted application servers** and click **New Trusted Application Pool**.</span></span>
    
3. <span data-ttu-id="958d7-114">Escriba el **FQDN del grupo de** servidores del grupo de aplicaciones de confianza y seleccione si será de un solo servidor o de varios servidores.</span><span class="sxs-lookup"><span data-stu-id="958d7-114">Enter the **Pool FQDN** of the trusted application pool and select whether it will be single-server or multiple-server.</span></span> 
    
4. <span data-ttu-id="958d7-115">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="958d7-115">Click **Next**.</span></span>
    
5. <span data-ttu-id="958d7-116">En la **página Seleccionar el próximo salto,** en la lista, seleccione el grupo de servidores front-end de Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="958d7-116">On the **Select the next hop** page, from the list, select the Skype for Business Server 2019 Front End pool.</span></span> 
    
6. <span data-ttu-id="958d7-117">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="958d7-117">Click **Finish**.</span></span>
    
7. <span data-ttu-id="958d7-118">Seleccione el nodo superior **de Skype Empresarial Server** y, en el **menú** Acción, **seleccione Publicar**.</span><span class="sxs-lookup"><span data-stu-id="958d7-118">Select the top node **Skype for Business Server**, and from the **Action** menu select **Publish**.</span></span>
    
    <span data-ttu-id="958d7-119">Compruebe que el **grupo de aplicaciones de confianza** se ha creado correctamente y está asociado con el grupo de servidores front-end correcto.</span><span class="sxs-lookup"><span data-stu-id="958d7-119">Verify that the **Trusted Application Pool** has been created successfully and is associated with the correct Front End pool.</span></span> 
    

