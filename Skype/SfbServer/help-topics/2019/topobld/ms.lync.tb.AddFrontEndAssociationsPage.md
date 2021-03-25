---
title: Agregar asociaciones front-end
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndAssociationsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 95620425-defd-47fd-a5c0-e4a283d812a5
ROBOTS: NOINDEX, NOFOLLOW
description: 'Puede habilitar la compatibilidad con determinadas características que requieran la implementación de otros servidores asociando los roles de servidor con el grupo de servidores front-end ahora. También puede asociar los roles de servidor con el grupo de servidores front-end más adelante. Los roles de servidor que se pueden asociar con un grupo de servidores front-end incluyen:'
ms.openlocfilehash: 1a528fbeeabc4ca9a4c676a9f064b651c37298c6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122661"
---
# <a name="add-front-end-associations"></a><span data-ttu-id="db141-105">Agregar asociaciones front-end</span><span class="sxs-lookup"><span data-stu-id="db141-105">Add Front End Associations</span></span>

<span data-ttu-id="db141-p102">Puede habilitar la compatibilidad con determinadas características que requieran la implementación de otros servidores asociando los roles de servidor con el grupo de servidores front-end ahora. También puede asociar los roles de servidor con el grupo de servidores front-end más adelante. Los roles de servidor que se pueden asociar con un grupo de servidores front-end incluyen:</span><span class="sxs-lookup"><span data-stu-id="db141-p102">You can enable support for specific features that require the deployment of other servers by associating the server roles with the Front End pool now. You can also associate server roles with the Front End pool at a later time. The server roles that can be associated with a Front End pool include the following:</span></span>

- <span data-ttu-id="db141-109">Servidor perimetral A/V.</span><span class="sxs-lookup"><span data-stu-id="db141-109">A/V Edge Server.</span></span> <span data-ttu-id="db141-110">Para más información sobre la implementación de un servidor perimetral A/V, consulte [Planning for Conferencing](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-conferencing) en la documentación sobre planificación.</span><span class="sxs-lookup"><span data-stu-id="db141-110">For details about the implementation of an A/V Edge Server, see [Planning for Conferencing](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-conferencing) in the Planning documentation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="db141-111">Si habilita ahora la compatibilidad de cualquiera de estas características, el diseño de la topología que publique incluirá los componentes del servidor que se requieren para implementar cada una de las características seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="db141-111">If you enable support for any of these features now, the topology design that you publish will include the server components that are required to implement each selected feature.</span></span> <span data-ttu-id="db141-112">Para que la publicación de una topología se realice con éxito, debe tener los equipos físicos unidos en el dominio.</span><span class="sxs-lookup"><span data-stu-id="db141-112">For the publishing of a topology to succeed without error, you must have the physical computers joined to the domain.</span></span> <span data-ttu-id="db141-113">Por ejemplo, si habilita la compatibilidad con el archivado ahora, debe implementar un servidor de archivado y configurar las opciones de archivado adecuadas antes de iniciar las comunicaciones de archivado para su organización.</span><span class="sxs-lookup"><span data-stu-id="db141-113">For example, if you enable support for archiving now, you must then deploy an Archiving Server and configure the appropriate archiving options before you start archiving communications for your organization.</span></span>