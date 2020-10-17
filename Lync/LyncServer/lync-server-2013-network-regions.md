---
title: 'Lync Server 2013: regiones de red'
description: 'Lync Server 2013: regiones de red.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Network regions
ms:assetid: 1818e9d2-bbb7-420a-93ea-4c3da3a55ad3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687979(v=OCS.15)
ms:contentKeyID: 49733567
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3506f3c543c0728f27bd091b9cd63991c4633da7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561486"
---
# <a name="network-regions-in-lync-server-2013"></a><span data-ttu-id="4b8d5-103">Regiones de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4b8d5-103">Network regions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4b8d5-104">_**Última modificación del tema:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="4b8d5-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="4b8d5-105">Las \*regiones de red \* son los concentradores de red o redes troncales que se usan en la configuración del control de admisión de llamadas, de E9-1-1 y del desvío de medios.</span><span class="sxs-lookup"><span data-stu-id="4b8d5-105">*Network regions* are the network hubs or backbones used in the configuration of call admission control, E9-1-1, and media bypass.</span></span> <span data-ttu-id="4b8d5-106">Siga los siguientes procedimientos para ver, crear o modificar regiones de red.</span><span class="sxs-lookup"><span data-stu-id="4b8d5-106">Use the following procedures to view, create, or modify network regions.</span></span> <span data-ttu-id="4b8d5-107">Por ejemplo, si ya ha creado regiones de red para una característica de voz, no es necesario que cree nuevas regiones de red; otras características avanzadas de Enterprise Voice usarán las mismas regiones de red.</span><span class="sxs-lookup"><span data-stu-id="4b8d5-107">For example, if you have already created network regions for one Voice feature, you do not need to create new network regions; other advanced Enterprise Voice features will use those same network regions.</span></span> <span data-ttu-id="4b8d5-108">Sin embargo, es posible que necesite modificar una definición de región de red existente para aplicar una configuración específica de una característica.</span><span class="sxs-lookup"><span data-stu-id="4b8d5-108">You may, however, need to modify an existing network region definition to apply feature-specific settings.</span></span> <span data-ttu-id="4b8d5-109">Por ejemplo, si ha creado regiones de red para E9-1-1 (que no requieren un sitio central asociado) y, a continuación, implementa el control de admisión de llamadas, debe modificar las definiciones de región de red para especificar un sitio central.</span><span class="sxs-lookup"><span data-stu-id="4b8d5-109">For example, if you have created network regions for E9-1-1 (which do not require an associated central site) and you then deploy call admission control, you need to modify the network region definitions to specify a central site.</span></span> <span data-ttu-id="4b8d5-110">Para obtener más información, consulte [Configure Network Regions for CAC in Lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md).</span><span class="sxs-lookup"><span data-stu-id="4b8d5-110">For details, see [Configure network regions for CAC in Lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4b8d5-111">Cualquier requisito específico de la característica para las definiciones de región de red está documentado en los temas sobre implementación para la característica.</span><span class="sxs-lookup"><span data-stu-id="4b8d5-111">Any feature-specific requirements for network region definitions are documented in the Deployment topics for the feature.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="4b8d5-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="4b8d5-112">In This Section</span></span>

  - [<span data-ttu-id="4b8d5-113">Ver la información de región de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4b8d5-113">Viewing network region information in Lync Server 2013</span></span>](lync-server-2013-viewing-network-region-information.md)

  - [<span data-ttu-id="4b8d5-114">Creación o modificación de regiones de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4b8d5-114">Creating or modifying network regions in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-network-regions.md)

  - [<span data-ttu-id="4b8d5-115">Eliminación de regiones de red existentes en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4b8d5-115">Deleting existing network regions in Lync Server 2013</span></span>](lync-server-2013-deleting-existing-network-regions.md)

</div>

<div>

## <a name="reference"></a><span data-ttu-id="4b8d5-116">Referencia</span><span class="sxs-lookup"><span data-stu-id="4b8d5-116">Reference</span></span>

[<span data-ttu-id="4b8d5-117">Implementación de características avanzadas de telefonía IP empresarial en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4b8d5-117">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

