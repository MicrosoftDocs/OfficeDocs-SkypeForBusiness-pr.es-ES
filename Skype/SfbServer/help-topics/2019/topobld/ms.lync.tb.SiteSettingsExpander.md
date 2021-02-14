---
title: Expansor de configuración de sitio de Lync Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.SiteSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 940bd9c0-bfcf-4d15-a5c1-a09f1cd692b6
ROBOTS: NOINDEX, NOFOLLOW
description: 'Para editar las propiedades de un sitio ya creado, efectúe las acciones siguientes:'
ms.openlocfilehash: 30e11a6b580b80719ffd6f745c7c37edf2cf358e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805570"
---
# <a name="lync-server-site-settings-expander"></a><span data-ttu-id="259be-103">Expansor de configuración de sitio de Lync Server</span><span class="sxs-lookup"><span data-stu-id="259be-103">Lync Server Site Settings Expander</span></span>

<span data-ttu-id="259be-104">Para editar las propiedades de un sitio ya creado, efectúe las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="259be-104">To edit the properties of an existing site, do the following:</span></span>



## <a name="site-properties"></a><span data-ttu-id="259be-105">Propiedades del sitio</span><span class="sxs-lookup"><span data-stu-id="259be-105">Site properties</span></span>

<span data-ttu-id="259be-106">En las propiedades del sitio se puede cambiar o modificar las opciones Nombre del sitio (obligatorio), Descripción (opcional), Ciudad (opcional), Estado o provincia (opcional) y País o región (opcional).</span><span class="sxs-lookup"><span data-stu-id="259be-106">In site properties, you can change or modify the site Name (required), Description (optional), City (optional), State/Province (optional), and the Country/Region Code (optional).</span></span>

<span data-ttu-id="259be-107">Para obtener más información sobre las propiedades de los sitios, consulte [Agregar sucursales a la topología](https://technet.microsoft.com/library/b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335.aspx).</span><span class="sxs-lookup"><span data-stu-id="259be-107">For details about site properties, see [Add Branch Sites to Your Topology](https://technet.microsoft.com/library/b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335.aspx).</span></span>

## <a name="federation-route-properties"></a><span data-ttu-id="259be-108">Propiedades de la ruta de federación</span><span class="sxs-lookup"><span data-stu-id="259be-108">Federation Route properties</span></span>

<span data-ttu-id="259be-p101">Para definir una asignación de ruta de federación de un sitio, primero debe tener la federación habilitada en un servidor perimetral o grupo de servidores perimetrales. Si la federación no está habilitada en un servidor perimetral o un grupo de servidores perimetrales, la configuración de la asignación de ruta de federación para el sitio no se podrá modificar.</span><span class="sxs-lookup"><span data-stu-id="259be-p101">To set a site federation route assignment, you must first have federation enabled on an Edge Server or an Edge Server pool. If federation is not enabled on an Edge Server or pool, the federation route assignment settings for the site will not be available for modification.</span></span>

<span data-ttu-id="259be-p102">Si se ha definido una configuración de federación del servidor o grupo de servidores perimetrales, seleccione **Habilitar** en el nivel del sitio. A continuación, seleccione un servidor perimetral o director de la lista desplegable para definirlos como ruta de federación.</span><span class="sxs-lookup"><span data-stu-id="259be-p102">If the federation setting at the Edge Server or pool has been configured, select **Enable** at the site level. Then select an Edge or a Director from the drop-down list to set as the federation route.</span></span>

> [!CAUTION]
> <span data-ttu-id="259be-p103">Esta configuración afectará a todos los sitios. Asegúrese de que la configuración que está configurando en este sitio es adecuada para todos los sitios.</span><span class="sxs-lookup"><span data-stu-id="259be-p103">This setting will affect all sites. Be sure that the setting that you are configuring at this site is appropriate for all sites.</span></span>

## <a name="see-also"></a><span data-ttu-id="259be-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="259be-115">See also</span></span>

<span data-ttu-id="259be-116">Para obtener información, consulte [Topologías para el acceso de usuarios externos](https://technet.microsoft.com/library/25697446-b045-4d12-9b1c-47f694b4f224.aspx).</span><span class="sxs-lookup"><span data-stu-id="259be-116">For details, see [Topologies for External User Access](https://technet.microsoft.com/library/25697446-b045-4d12-9b1c-47f694b4f224.aspx).</span></span>


