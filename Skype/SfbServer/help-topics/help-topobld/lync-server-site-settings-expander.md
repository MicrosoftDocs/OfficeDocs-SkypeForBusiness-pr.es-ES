---
title: Expansor de configuración de sitio de Lync Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.SiteSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 940bd9c0-bfcf-4d15-a5c1-a09f1cd692b6
description: 'Para editar las propiedades de un sitio existente, haga lo siguiente:'
ms.openlocfilehash: adee80a545487600ffa2d8d7f49285b24645263e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276140"
---
# <a name="lync-server-site-settings-expander"></a><span data-ttu-id="70521-103">Expansor de configuración de sitio de Lync Server</span><span class="sxs-lookup"><span data-stu-id="70521-103">Lync Server Site Settings Expander</span></span>

<span data-ttu-id="70521-104">Para editar las propiedades de un sitio existente, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="70521-104">To edit the properties of an existing site, do the following:</span></span>



## <a name="site-properties"></a><span data-ttu-id="70521-105">Propiedades del sitio</span><span class="sxs-lookup"><span data-stu-id="70521-105">Site properties</span></span>

<span data-ttu-id="70521-106">En las propiedades del sitio, puede cambiar o modificar el nombre del sitio (obligatorio), la descripción (opcional), la ciudad (opcional), el estado o provincia (opcional) y el código de país o región (opcional).</span><span class="sxs-lookup"><span data-stu-id="70521-106">In site properties, you can change or modify the site Name (required), Description (optional), City (optional), State/Province (optional), and the Country/Region Code (optional).</span></span>

<span data-ttu-id="70521-107">Para obtener más información sobre las propiedades del sitio, vea [Agregar sitios de sucursales a su topología](https://technet.microsoft.com/library/b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335.aspx).</span><span class="sxs-lookup"><span data-stu-id="70521-107">For details about site properties, see [Add Branch Sites to Your Topology](https://technet.microsoft.com/library/b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335.aspx).</span></span>

## <a name="federation-route-properties"></a><span data-ttu-id="70521-108">Propiedades de la ruta de Federación</span><span class="sxs-lookup"><span data-stu-id="70521-108">Federation Route properties</span></span>

<span data-ttu-id="70521-109">Para establecer una asignación de enrutamiento de Federación de sitios, primero debe tener habilitada la Federación en un servidor perimetral o en un grupo de servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="70521-109">To set a site federation route assignment, you must first have federation enabled on an Edge Server or an Edge Server pool.</span></span> <span data-ttu-id="70521-110">Si la Federación no está habilitada en un servidor perimetral o en un grupo, la configuración de asignación de rutas de Federación para el sitio no estará disponible para su modificación.</span><span class="sxs-lookup"><span data-stu-id="70521-110">If federation is not enabled on an Edge Server or pool, the federation route assignment settings for the site will not be available for modification.</span></span>

<span data-ttu-id="70521-111">Si se ha configurado la configuración de Federación en el servidor perimetral o en el grupo, seleccione **Habilitar** en el nivel del sitio.</span><span class="sxs-lookup"><span data-stu-id="70521-111">If the federation setting at the Edge Server or pool has been configured, select **Enable** at the site level.</span></span> <span data-ttu-id="70521-112">A continuación, seleccione un borde o un director de la lista desplegable para establecer como ruta de Federación.</span><span class="sxs-lookup"><span data-stu-id="70521-112">Then select an Edge or a Director from the drop-down list to set as the federation route.</span></span>

> [!CAUTION]
> <span data-ttu-id="70521-113">Esta configuración afectará a todos los sitios.</span><span class="sxs-lookup"><span data-stu-id="70521-113">This setting will affect all sites.</span></span> <span data-ttu-id="70521-114">Asegúrese de que la configuración que está configurando en este sitio es adecuada para todos los sitios.</span><span class="sxs-lookup"><span data-stu-id="70521-114">Be sure that the setting that you are configuring at this site is appropriate for all sites.</span></span>

## <a name="see-also"></a><span data-ttu-id="70521-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="70521-115">See also</span></span>

<span data-ttu-id="70521-116">Para obtener más información, vea [topologías para el acceso de usuarios externos](https://technet.microsoft.com/library/25697446-b045-4d12-9b1c-47f694b4f224.aspx).</span><span class="sxs-lookup"><span data-stu-id="70521-116">For details, see [Topologies for External User Access](https://technet.microsoft.com/library/25697446-b045-4d12-9b1c-47f694b4f224.aspx).</span></span>


