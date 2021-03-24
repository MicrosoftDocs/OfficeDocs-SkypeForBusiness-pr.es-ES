---
title: Expansor de configuración de sitio de Lync Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.SiteSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 940bd9c0-bfcf-4d15-a5c1-a09f1cd692b6
description: 'Para editar las propiedades de un sitio ya creado, efectúe las acciones siguientes:'
ms.openlocfilehash: aedb248bf229af754d2ef8eb9c5e3837c69c808d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104456"
---
# <a name="lync-server-site-settings-expander"></a><span data-ttu-id="c16eb-103">Expansor de configuración de sitio de Lync Server</span><span class="sxs-lookup"><span data-stu-id="c16eb-103">Lync Server Site Settings Expander</span></span>

<span data-ttu-id="c16eb-104">Para editar las propiedades de un sitio ya creado, efectúe las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="c16eb-104">To edit the properties of an existing site, do the following:</span></span>



## <a name="site-properties"></a><span data-ttu-id="c16eb-105">Propiedades del sitio</span><span class="sxs-lookup"><span data-stu-id="c16eb-105">Site properties</span></span>

<span data-ttu-id="c16eb-106">En las propiedades del sitio se puede cambiar o modificar las opciones Nombre del sitio (obligatorio), Descripción (opcional), Ciudad (opcional), Estado o provincia (opcional) y País o región (opcional).</span><span class="sxs-lookup"><span data-stu-id="c16eb-106">In site properties, you can change or modify the site Name (required), Description (optional), City (optional), State/Province (optional), and the Country/Region Code (optional).</span></span>

<span data-ttu-id="c16eb-107">Para obtener más información sobre las propiedades de los sitios, consulte [Agregar sucursales a la topología](/previous-versions/office/lync-server-2013/lync-server-2013-add-branch-sites-to-your-topology).</span><span class="sxs-lookup"><span data-stu-id="c16eb-107">For details about site properties, see [Add Branch Sites to Your Topology](/previous-versions/office/lync-server-2013/lync-server-2013-add-branch-sites-to-your-topology).</span></span>

## <a name="federation-route-properties"></a><span data-ttu-id="c16eb-108">Propiedades de la ruta de federación</span><span class="sxs-lookup"><span data-stu-id="c16eb-108">Federation Route properties</span></span>

<span data-ttu-id="c16eb-p101">Para definir una asignación de ruta de federación de un sitio, primero debe tener la federación habilitada en un servidor perimetral o grupo de servidores perimetrales. Si la federación no está habilitada en un servidor perimetral o un grupo de servidores perimetrales, la configuración de la asignación de ruta de federación para el sitio no se podrá modificar.</span><span class="sxs-lookup"><span data-stu-id="c16eb-p101">To set a site federation route assignment, you must first have federation enabled on an Edge Server or an Edge Server pool. If federation is not enabled on an Edge Server or pool, the federation route assignment settings for the site will not be available for modification.</span></span>

<span data-ttu-id="c16eb-p102">Si se ha definido una configuración de federación del servidor o grupo de servidores perimetrales, seleccione **Habilitar** en el nivel del sitio. A continuación, seleccione un servidor perimetral o director de la lista desplegable para definirlos como ruta de federación.</span><span class="sxs-lookup"><span data-stu-id="c16eb-p102">If the federation setting at the Edge Server or pool has been configured, select **Enable** at the site level. Then select an Edge or a Director from the drop-down list to set as the federation route.</span></span>

> [!CAUTION]
> <span data-ttu-id="c16eb-p103">Esta configuración afectará a todos los sitios. Asegúrese de que la configuración que está configurando en este sitio es adecuada para todos los sitios.</span><span class="sxs-lookup"><span data-stu-id="c16eb-p103">This setting will affect all sites. Be sure that the setting that you are configuring at this site is appropriate for all sites.</span></span>

## <a name="see-also"></a><span data-ttu-id="c16eb-115">Ver también</span><span class="sxs-lookup"><span data-stu-id="c16eb-115">See also</span></span>

<span data-ttu-id="c16eb-116">Para obtener información, consulte [Topologías para el acceso de usuarios externos](/previous-versions/office/lync-server-2013/lync-server-2013-scenarios-for-external-user-access).</span><span class="sxs-lookup"><span data-stu-id="c16eb-116">For details, see [Topologies for External User Access](/previous-versions/office/lync-server-2013/lync-server-2013-scenarios-for-external-user-access).</span></span>