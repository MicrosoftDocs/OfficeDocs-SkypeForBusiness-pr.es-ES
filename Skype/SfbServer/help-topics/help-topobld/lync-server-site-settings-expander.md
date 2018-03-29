---
title: Ampliador de configuración de sitio de Lync Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.SiteSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 940bd9c0-bfcf-4d15-a5c1-a09f1cd692b6
description: 'Para editar las propiedades de un sitio existente, siga este procedimiento:'
ms.openlocfilehash: 6ae0154da4e53cffb9d0b6bb02a2eda3cb0cbaa8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="lync-server-site-settings-expander"></a><span data-ttu-id="52043-103">Ampliador de configuración de sitio de Lync Server</span><span class="sxs-lookup"><span data-stu-id="52043-103">Lync Server Site Settings Expander</span></span>
 
<span data-ttu-id="52043-104">Para editar las propiedades de un sitio existente, siga este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="52043-104">To edit the properties of an existing site, do the following:</span></span>
  
## 

### <a name="site-properties"></a><span data-ttu-id="52043-105">Propiedades de sitio</span><span class="sxs-lookup"><span data-stu-id="52043-105">Site properties</span></span>

<span data-ttu-id="52043-106">En Propiedades de sitio, puede cambiar o modificar el sitio nombre (obligatorio), descripción (opcional), (opcional) de la ciudad, estado o provincia (opcional) y el código de país o región (opcional).</span><span class="sxs-lookup"><span data-stu-id="52043-106">In site properties, you can change or modify the site Name (required), Description (optional), City (optional), State/Province (optional), and the Country/Region Code (optional).</span></span>
  
<span data-ttu-id="52043-107">Para obtener más información acerca de las propiedades del sitio, vea [Agregar sitios de sucursal para su topología](http://technet.microsoft.com/library/b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335.aspx).</span><span class="sxs-lookup"><span data-stu-id="52043-107">For details about site properties, see [Add Branch Sites to Your Topology](http://technet.microsoft.com/library/b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335.aspx).</span></span>
  
### <a name="federation-route-properties"></a><span data-ttu-id="52043-108">Propiedades de la ruta de la federación</span><span class="sxs-lookup"><span data-stu-id="52043-108">Federation Route properties</span></span>

<span data-ttu-id="52043-109">Para establecer una asignación de ruta de la federación de sitio, primero debe tener habilitada en un servidor perimetral o un grupo de servidor perimetral de federación.</span><span class="sxs-lookup"><span data-stu-id="52043-109">To set a site federation route assignment, you must first have federation enabled on an Edge Server or an Edge Server pool.</span></span> <span data-ttu-id="52043-110">Si la federación no está habilitada en un servidor perimetral o un grupo de servidores, la configuración de asignación de ruta de federación para el sitio no estará disponible para su modificación.</span><span class="sxs-lookup"><span data-stu-id="52043-110">If federation is not enabled on an Edge Server or pool, the federation route assignment settings for the site will not be available for modification.</span></span>
  
<span data-ttu-id="52043-111">Si se ha configurado la configuración de la federación en el servidor perimetral o un grupo de servidores, seleccione **Habilitar** en el nivel de sitio.</span><span class="sxs-lookup"><span data-stu-id="52043-111">If the federation setting at the Edge Server or pool has been configured, select **Enable** at the site level.</span></span> <span data-ttu-id="52043-112">A continuación, seleccione una arista o un Director de la lista desplegable para establecer como la ruta de la federación.</span><span class="sxs-lookup"><span data-stu-id="52043-112">Then select an Edge or a Director from the drop-down list to set as the federation route.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="52043-113">Esta configuración afectará a todos los sitios.</span><span class="sxs-lookup"><span data-stu-id="52043-113">This setting will affect all sites.</span></span> <span data-ttu-id="52043-114">Asegúrese de que la configuración que se está configurando en este sitio es adecuada para todos los sitios.</span><span class="sxs-lookup"><span data-stu-id="52043-114">Be sure that the setting that you are configuring at this site is appropriate for all sites.</span></span> 
  
### 

<span data-ttu-id="52043-115">Para obtener más información, consulte [topologías para acceso de usuario externo](http://technet.microsoft.com/library/25697446-b045-4d12-9b1c-47f694b4f224.aspx).</span><span class="sxs-lookup"><span data-stu-id="52043-115">For details, see [Topologies for External User Access](http://technet.microsoft.com/library/25697446-b045-4d12-9b1c-47f694b4f224.aspx).</span></span>
  

