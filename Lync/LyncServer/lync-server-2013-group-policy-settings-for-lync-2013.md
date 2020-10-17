---
title: 'Lync Server 2013: configuración de directiva de grupo para Lync 2013'
description: 'Lync Server 2013: configuración de directiva de grupo para Lync 2013.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Group Policy settings for Lync 2013
ms:assetid: 5917a52b-dae0-4ec0-8548-a68dc20ab71c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204924(v=OCS.15)
ms:contentKeyID: 48184235
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5c6f2b26fc19653b0098ed4775df1f9c8146986c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564186"
---
# <a name="group-policy-settings-for-lync-2013"></a><span data-ttu-id="cc5d4-103">Configuración de directiva de grupo para Lync 2013</span><span class="sxs-lookup"><span data-stu-id="cc5d4-103">Group Policy settings for Lync 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cc5d4-104">_**Última modificación del tema:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="cc5d4-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="cc5d4-105">En versiones anteriores de Lync y Office Communicator, una plantilla administrativa independiente Communicator. adm estaba disponible para configurar las opciones de directiva de grupo de cliente.</span><span class="sxs-lookup"><span data-stu-id="cc5d4-105">In previous versions of Lync and Office Communicator, a stand-alone Communicator.adm administrative template was available for configuring client Group Policy settings.</span></span> <span data-ttu-id="cc5d4-106">Para Lync 2013, los nuevos archivos de plantilla administrativa (archivos. ADMX y. ADML) se incluyen junto con la plantilla administrativa de directiva de grupo de Office.</span><span class="sxs-lookup"><span data-stu-id="cc5d4-106">For Lync 2013, new administrative template files (.admx and .adml files) are included along with the Office Group Policy Administrative Template.</span></span> <span data-ttu-id="cc5d4-107">La disponibilidad de los archivos. ADMX y. ADML de 2013 Lync permite descargar plantillas y administrar la configuración de la Directiva de grupo de forma centralizada para todos los programas de Office y los paquetes de idioma.</span><span class="sxs-lookup"><span data-stu-id="cc5d4-107">The availability of Lync 2013 .admx and .adml files allows you to download templates and centrally manage Group Policy settings for all your Office programs and language packs.</span></span> <span data-ttu-id="cc5d4-108">Para obtener más información, consulte "Office 2013 Administrative template files (ADMX, ADML)" en la documentación de Office 2013 en <https://go.microsoft.com/fwlink/p/?linkid=267516> .</span><span class="sxs-lookup"><span data-stu-id="cc5d4-108">For details, see “Office 2013 Administrative Template files (ADMX, ADML)” in the Office 2013 documentation at <https://go.microsoft.com/fwlink/p/?linkid=267516>.</span></span>

<div>

## <a name="client-bootstrapping-policies"></a><span data-ttu-id="cc5d4-109">Directivas de arranque de cliente</span><span class="sxs-lookup"><span data-stu-id="cc5d4-109">Client Bootstrapping Policies</span></span>

<span data-ttu-id="cc5d4-110">Hay varias directivas de arranque de clientes que deberán configurarse antes de que los usuarios inicien sesión por primera vez en el servidor.</span><span class="sxs-lookup"><span data-stu-id="cc5d4-110">There are several client bootstrapping policies that you should configure before users sign in to the server for the first time.</span></span> <span data-ttu-id="cc5d4-111">Como estas directivas entran en vigor antes de que el cliente inicie sesión y empiece a recibir la configuración de aprovisionamiento dentro de banda del servidor, el usuario puede usar una directiva de grupo para configurarlas.</span><span class="sxs-lookup"><span data-stu-id="cc5d4-111">Because these policies take effect before the client signs in and begins receiving in-band provisioning settings from the server, you can use Group Policy to configure them.</span></span> <span data-ttu-id="cc5d4-112">Para obtener más información, consulte [configuración de directivas de arranque de cliente en Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="cc5d4-112">For more information, see [Configuring client bootstrapping policies in Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) in the Deployment documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

