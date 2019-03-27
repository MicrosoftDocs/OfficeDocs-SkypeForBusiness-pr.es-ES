---
title: Expansor de configuración de sitio de Lync Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.SiteSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 940bd9c0-bfcf-4d15-a5c1-a09f1cd692b6
ROBOTS: NOINDEX, NOFOLLOW
description: 'Para editar las propiedades de un sitio existente, realice lo siguiente:'
ms.openlocfilehash: fdbcd5ddb62de7d4d4040e0b790e3475e20372c7
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30887050"
---
# <a name="lync-server-site-settings-expander"></a><span data-ttu-id="e7a7c-103">Expansor de configuración de sitio de Lync Server</span><span class="sxs-lookup"><span data-stu-id="e7a7c-103">Lync Server Site Settings Expander</span></span>

<span data-ttu-id="e7a7c-104">Para editar las propiedades de un sitio existente, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e7a7c-104">To edit the properties of an existing site, do the following:</span></span>



## <a name="site-properties"></a><span data-ttu-id="e7a7c-105">Propiedades de sitio</span><span class="sxs-lookup"><span data-stu-id="e7a7c-105">Site properties</span></span>

<span data-ttu-id="e7a7c-106">En Propiedades de sitio, puede cambiar o modificar el sitio nombre (obligatorio), descripción (opcional), ciudad (opcional), estado o provincia (opcional) y el código de país o región (opcional).</span><span class="sxs-lookup"><span data-stu-id="e7a7c-106">In site properties, you can change or modify the site Name (required), Description (optional), City (optional), State/Province (optional), and the Country/Region Code (optional).</span></span>

<span data-ttu-id="e7a7c-107">Para obtener información detallada acerca de las propiedades de sitio, vea [Add Branch Sites to Your Topology](https://technet.microsoft.com/library/b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335.aspx).</span><span class="sxs-lookup"><span data-stu-id="e7a7c-107">For details about site properties, see [Add Branch Sites to Your Topology](https://technet.microsoft.com/library/b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335.aspx).</span></span>

## <a name="federation-route-properties"></a><span data-ttu-id="e7a7c-108">Propiedades de ruta de federación</span><span class="sxs-lookup"><span data-stu-id="e7a7c-108">Federation Route properties</span></span>

<span data-ttu-id="e7a7c-109">Para establecer una asignación de ruta de federación de sitio, primero debe tener habilitada en un servidor perimetral o un grupo de servidores perimetrales de federación.</span><span class="sxs-lookup"><span data-stu-id="e7a7c-109">To set a site federation route assignment, you must first have federation enabled on an Edge Server or an Edge Server pool.</span></span> <span data-ttu-id="e7a7c-110">Si no está habilitada la federación en un servidor perimetral o grupo de servidores, la configuración de asignación de ruta de federación para el sitio no estará disponible para su modificación.</span><span class="sxs-lookup"><span data-stu-id="e7a7c-110">If federation is not enabled on an Edge Server or pool, the federation route assignment settings for the site will not be available for modification.</span></span>

<span data-ttu-id="e7a7c-111">Si se ha configurado la configuración de federación en el servidor perimetral o grupo de servidores, seleccione **Habilitar** en el nivel de sitio.</span><span class="sxs-lookup"><span data-stu-id="e7a7c-111">If the federation setting at the Edge Server or pool has been configured, select **Enable** at the site level.</span></span> <span data-ttu-id="e7a7c-112">A continuación, seleccione una arista o un Director de la lista desplegable para establecer como la ruta de federación.</span><span class="sxs-lookup"><span data-stu-id="e7a7c-112">Then select an Edge or a Director from the drop-down list to set as the federation route.</span></span>

> [!CAUTION]
> <span data-ttu-id="e7a7c-113">Esta configuración afectará a todos los sitios.</span><span class="sxs-lookup"><span data-stu-id="e7a7c-113">This setting will affect all sites.</span></span> <span data-ttu-id="e7a7c-114">Asegúrese de que la configuración que se va a configurar en este sitio es adecuada para todos los sitios.</span><span class="sxs-lookup"><span data-stu-id="e7a7c-114">Be sure that the setting that you are configuring at this site is appropriate for all sites.</span></span>

## <a name="see-also"></a><span data-ttu-id="e7a7c-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e7a7c-115">See also</span></span>

<span data-ttu-id="e7a7c-116">Para obtener información detallada, vea [topologías para acceso de usuarios externos](https://technet.microsoft.com/library/25697446-b045-4d12-9b1c-47f694b4f224.aspx).</span><span class="sxs-lookup"><span data-stu-id="e7a7c-116">For details, see [Topologies for External User Access](https://technet.microsoft.com/library/25697446-b045-4d12-9b1c-47f694b4f224.aspx).</span></span>


