---
title: Configurar servidores de aplicaciones de confianza
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: En un entorno mixto, si crea un nuevo servidor de aplicaciones de confianza, debe establecer el próximo salto para ser un Skype para el grupo de servidores de Business Server 2019. En un entorno mixto, el grupo heredado y el Skype para el grupo de servidores de Business Server 2019 aparecen en la lista desplegable. No se admite la selección del grupo heredado.
ms.openlocfilehash: 79f4de527008d2d9bf295fcb82eee433d04a1691
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32238685"
---
# <a name="configure-trusted-application-servers"></a><span data-ttu-id="98bf3-105">Configurar servidores de aplicaciones de confianza</span><span class="sxs-lookup"><span data-stu-id="98bf3-105">Configure trusted application servers</span></span>

<span data-ttu-id="98bf3-106">En un entorno mixto, si crea un nuevo servidor de aplicaciones de confianza, debe establecer el próximo salto para ser un Skype para el grupo de servidores de Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="98bf3-106">In a mixed environment, if you create a new trusted application server, you must set the next hop pool to be a Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="98bf3-107">En un entorno mixto, el grupo heredado y el Skype para el grupo de servidores de Business Server 2019 aparecen en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="98bf3-107">In a mixed environment, both the legacy pool and the Skype for Business Server 2019 pool appear in the drop-down list.</span></span> <span data-ttu-id="98bf3-108">No se admite la selección del grupo heredado.</span><span class="sxs-lookup"><span data-stu-id="98bf3-108">Selecting the legacy pool is not supported.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="98bf3-109">Si va a migrar un servidor de aplicaciones de confianza, también deberá actualizar la versión de UCMA está utilizando.</span><span class="sxs-lookup"><span data-stu-id="98bf3-109">If you are migrating a trusted application server, you should also update the version of UCMA you are using.</span></span> <span data-ttu-id="98bf3-110">Si se crea un nuevo grupo de aplicaciones de confianza para Skype para Business Server 2019, deberá actualizar UCMA a la versión que se incluye con Skype para Business Server 2019 o la versión más reciente disponible.</span><span class="sxs-lookup"><span data-stu-id="98bf3-110">If you create a new Trusted Application Pool for Skype for Business Server 2019, you should update UCMA to the version that is included with Skype for Business Server 2019 or the latest version available.</span></span> 
  
### <a name="select-skype-for-business-server-2019-as-next-hop-when-creating-a-trusted-application-server"></a><span data-ttu-id="98bf3-111">Seleccione Skype para Business Server 2019 como próximo salto al crear un servidor de aplicaciones de confianza</span><span class="sxs-lookup"><span data-stu-id="98bf3-111">Select Skype for Business Server 2019 as next hop when creating a Trusted application server</span></span>

1. <span data-ttu-id="98bf3-112">Abra el generador de topología.</span><span class="sxs-lookup"><span data-stu-id="98bf3-112">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="98bf3-113">En el panel izquierdo, haga clic en **servidores de aplicaciones de confianza** y haga clic en **Nuevo grupo de aplicaciones de confianza**.</span><span class="sxs-lookup"><span data-stu-id="98bf3-113">In the left pane, right-click **Trusted application servers** and click **New Trusted Application Pool**.</span></span>
    
3. <span data-ttu-id="98bf3-114">Escriba el **FQDN del grupo de servidores** del grupo de aplicaciones de confianza y seleccione si será un único servidor o varios servidores.</span><span class="sxs-lookup"><span data-stu-id="98bf3-114">Enter the **Pool FQDN** of the trusted application pool and select whether it will be single-server or multiple-server.</span></span> 
    
4. <span data-ttu-id="98bf3-115">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="98bf3-115">Click **Next**.</span></span>
    
5. <span data-ttu-id="98bf3-116">En la página **Seleccionar el próximo salto** , en la lista, seleccione el Skype para el grupo de servidores Front-End de Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="98bf3-116">On the **Select the next hop** page, from the list, select the Skype for Business Server 2019 Front End pool.</span></span> 
    
6. <span data-ttu-id="98bf3-117">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="98bf3-117">Click **Finish**.</span></span>
    
7. <span data-ttu-id="98bf3-118">Seleccione el nodo superior **Skype para Business Server**y, en el menú **acción** , seleccione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="98bf3-118">Select the top node **Skype for Business Server**, and from the **Action** menu select **Publish**.</span></span>
    
    <span data-ttu-id="98bf3-119">Compruebe que el **Grupo de aplicaciones de confianza** se ha creado correctamente y está asociado con el grupo de servidores Front-End correcto.</span><span class="sxs-lookup"><span data-stu-id="98bf3-119">Verify that the **Trusted Application Pool** has been created successfully and is associated with the correct Front End pool.</span></span> 
    

