---
title: 'Lync Server 2013: configuración de directiva de grupo para Lync 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Group Policy settings for Lync 2013
ms:assetid: 5917a52b-dae0-4ec0-8548-a68dc20ab71c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204924(v=OCS.15)
ms:contentKeyID: 48184235
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e075af74fd081e49daad0768a33c9769e8a633bf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835108"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="group-policy-settings-for-lync-2013"></a><span data-ttu-id="20ee1-102">Configuración de directiva de grupo para Lync 2013</span><span class="sxs-lookup"><span data-stu-id="20ee1-102">Group Policy settings for Lync 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="20ee1-103">_**Última modificación del tema:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="20ee1-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="20ee1-104">En versiones anteriores de Lync y Office Communicator, una plantilla administrativa independiente de Communicator. adm estaba disponible para configurar las opciones de directiva de grupo de cliente.</span><span class="sxs-lookup"><span data-stu-id="20ee1-104">In previous versions of Lync and Office Communicator, a stand-alone Communicator.adm administrative template was available for configuring client Group Policy settings.</span></span> <span data-ttu-id="20ee1-105">Para Lync 2013, se incluyen nuevos archivos de plantilla administrativa (archivos. ADMX y. ADML) junto con la plantilla administrativa de la Directiva de grupo de Office.</span><span class="sxs-lookup"><span data-stu-id="20ee1-105">For Lync 2013, new administrative template files (.admx and .adml files) are included along with the Office Group Policy Administrative Template.</span></span> <span data-ttu-id="20ee1-106">La disponibilidad de los archivos. ADMX y. ADML de 2013 Lync permite descargar plantillas y administrar de forma centralizada la configuración de la Directiva de grupo para todos los paquetes de idioma y programas de Office.</span><span class="sxs-lookup"><span data-stu-id="20ee1-106">The availability of Lync 2013 .admx and .adml files allows you to download templates and centrally manage Group Policy settings for all your Office programs and language packs.</span></span> <span data-ttu-id="20ee1-107">Para obtener más información, consulte "archivos de plantilla administrativa (ADMX, ADML) de Office 2013" en la <http://go.microsoft.com/fwlink/p/?linkid=267516>documentación de Office 2013 en.</span><span class="sxs-lookup"><span data-stu-id="20ee1-107">For details, see “Office 2013 Administrative Template files (ADMX, ADML)” in the Office 2013 documentation at <http://go.microsoft.com/fwlink/p/?linkid=267516>.</span></span>

<div>

## <a name="client-bootstrapping-policies"></a><span data-ttu-id="20ee1-108">Directivas de inicio del cliente</span><span class="sxs-lookup"><span data-stu-id="20ee1-108">Client Bootstrapping Policies</span></span>

<span data-ttu-id="20ee1-109">Hay varias directivas de inicio del cliente que debe configurar antes de que los usuarios inicien sesión en el servidor por primera vez.</span><span class="sxs-lookup"><span data-stu-id="20ee1-109">There are several client bootstrapping policies that you should configure before users sign in to the server for the first time.</span></span> <span data-ttu-id="20ee1-110">Debido a que estas directivas surten efecto antes de que el cliente inicie sesión y empiece a recibir la configuración de aprovisionamiento en banda del servidor, puede usar la Directiva de grupo para configurarlas.</span><span class="sxs-lookup"><span data-stu-id="20ee1-110">Because these policies take effect before the client signs in and begins receiving in-band provisioning settings from the server, you can use Group Policy to configure them.</span></span> <span data-ttu-id="20ee1-111">Para obtener más información, vea [configuración de directivas de inicio de cliente en Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="20ee1-111">For more information, see [Configuring client bootstrapping policies in Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) in the Deployment documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

