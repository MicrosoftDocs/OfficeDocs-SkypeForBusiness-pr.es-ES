---
title: 'Lync Server 2013: configuración de intervalos de puertos de medios'
description: 'Lync Server 2013: configuración del intervalo de puertos de medios.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring media port range settings
ms:assetid: 2c4b7c0b-0dce-48f4-a489-336d6e526f7c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204770(v=OCS.15)
ms:contentKeyID: 48183723
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1a7670284c593197068c366f43bbb3faaaad8f63
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570746"
---
# <a name="configuring-media-port-range-settings-in-lync-server-2013"></a><span data-ttu-id="4f85c-103">Configuración de intervalos de puertos de medios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4f85c-103">Configuring media port range settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4f85c-104">_**Última modificación del tema:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="4f85c-104">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="4f85c-105">La configuración del intervalo de puertos de medios puede afectar significativamente al rendimiento del cliente y debe configurarse.</span><span class="sxs-lookup"><span data-stu-id="4f85c-105">Media port range settings can significantly impact client performance and should be configured.</span></span> <span data-ttu-id="4f85c-106">Puede configurar estas opciones mediante el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4f85c-106">You can configure these settings by using Lync Server Management Shell.</span></span>

### <a name="media-port-range-settings"></a><span data-ttu-id="4f85c-107">Configuración de intervalo de puertos de medios</span><span class="sxs-lookup"><span data-stu-id="4f85c-107">Media Port Range Settings</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4f85c-108">Configuración</span><span class="sxs-lookup"><span data-stu-id="4f85c-108">Setting</span></span></th>
<th><span data-ttu-id="4f85c-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="4f85c-109">Description</span></span></th>
<th><span data-ttu-id="4f85c-110">Cmdlet de Shell de administración de Lync Server</span><span class="sxs-lookup"><span data-stu-id="4f85c-110">Lync Server Management Shell cmdlet</span></span></th>
<th><span data-ttu-id="4f85c-111">Parámetros del cmdlet</span><span class="sxs-lookup"><span data-stu-id="4f85c-111">Cmdlet parameters</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4f85c-112">Portrange\Enabled</span><span class="sxs-lookup"><span data-stu-id="4f85c-112">Portrange\Enabled</span></span></p></td>
<td><p><span data-ttu-id="4f85c-113">Especifica si el cliente debe usar los intervalos de puertos enviados por el servidor para medios y señalización.</span><span class="sxs-lookup"><span data-stu-id="4f85c-113">Specifies whether the port ranges sent by the server should be used by the client for media and signaling.</span></span> <span data-ttu-id="4f85c-114">Se usa junto con los subvalores MinMediaPort y MaxMediaPort.</span><span class="sxs-lookup"><span data-stu-id="4f85c-114">Used in conjunction with the subvalues MinMediaPort and MaxMediaPort.</span></span></p></td>
<td><p><span data-ttu-id="4f85c-115"><strong>CsConferencingConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="4f85c-115"><strong>CsConferencingConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="4f85c-116">Los parámetros clientmediaportrangeenabled</span><span class="sxs-lookup"><span data-stu-id="4f85c-116">ClientMediaPortRangeEnabled</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4f85c-117">Portrange\MinMediaPort</span><span class="sxs-lookup"><span data-stu-id="4f85c-117">Portrange\MinMediaPort</span></span></p></td>
<td><p><span data-ttu-id="4f85c-118">Especifica el número de Puerto inicial que se va a usar para los medios.</span><span class="sxs-lookup"><span data-stu-id="4f85c-118">Specifies the starting port number to use for media.</span></span> <span data-ttu-id="4f85c-119">Se combina con MaxMediaPort para especificar el intervalo de puertos.</span><span class="sxs-lookup"><span data-stu-id="4f85c-119">Combines with MaxMediaPort to specify the range of ports.</span></span> <span data-ttu-id="4f85c-120">El intervalo mínimo recomendado es de 40 puertos.</span><span class="sxs-lookup"><span data-stu-id="4f85c-120">The recommended minimum range is 40 ports.</span></span></p></td>
<td><p><span data-ttu-id="4f85c-121"><strong>CsConferencingConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="4f85c-121"><strong>CsConferencingConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="4f85c-122">ClientMediaPort (representa el número inicial de puerto que debe usarse para los medios de cliente)</span><span class="sxs-lookup"><span data-stu-id="4f85c-122">ClientMediaPort (represents the starting port number to use for client media)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4f85c-123">Portrange\MaxMediaPort</span><span class="sxs-lookup"><span data-stu-id="4f85c-123">Portrange\MaxMediaPort</span></span></p></td>
<td><p><span data-ttu-id="4f85c-124">Especifica el número de puerto más alto que se va a usar para los medios.</span><span class="sxs-lookup"><span data-stu-id="4f85c-124">Specifies the highest port number to use for media.</span></span> <span data-ttu-id="4f85c-125">Se combina con MinMediaPort para especificar el intervalo de puertos.</span><span class="sxs-lookup"><span data-stu-id="4f85c-125">Combines with MinMediaPort to specify the range of ports.</span></span> <span data-ttu-id="4f85c-126">El intervalo mínimo recomendado es de 40 puertos.</span><span class="sxs-lookup"><span data-stu-id="4f85c-126">The recommended minimum range is 40 ports.</span></span></p></td>
<td><p><span data-ttu-id="4f85c-127"><strong>CsConferencingConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="4f85c-127"><strong>CsConferencingConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="4f85c-128">ClientMediaPortRange (indica el número total de puertos disponibles para los medios de cliente; el valor predeterminado es 40)</span><span class="sxs-lookup"><span data-stu-id="4f85c-128">ClientMediaPortRange (indicates the total number of ports available for client media; default is 40)</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-media-port-range-settings"></a><span data-ttu-id="4f85c-129">Para configurar las opciones de intervalo de puertos de medios</span><span class="sxs-lookup"><span data-stu-id="4f85c-129">To Configure Media Port Range Settings</span></span>

1.  <span data-ttu-id="4f85c-130">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="4f85c-130">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="4f85c-131">Ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="4f85c-131">Run the following cmdlet:</span></span>
    
        Get-CsConferencingConfiguration
    
    <span data-ttu-id="4f85c-132">Este cmdlet devuelve las opciones de configuración de conferencia.</span><span class="sxs-lookup"><span data-stu-id="4f85c-132">This cmdlet returns the conferencing configuration settings.</span></span>

3.  <span data-ttu-id="4f85c-133">Ejecute el siguiente cmdlet con los parámetros y valores que desee cambiar (para obtener información detallada sobre los parámetros de este cmdlet, consulte la documentación del shell de administración de Lync Server):</span><span class="sxs-lookup"><span data-stu-id="4f85c-133">Run the following cmdlet with the parameters and values you want to change (for details about the parameters for this cmdlet, see the Lync Server Management Shell documentation):</span></span>
    
        Set-CsConferencingConfiguration
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4f85c-134">Puede crear conjuntos adicionales de opciones de configuración de conferencia para sitios específicos.</span><span class="sxs-lookup"><span data-stu-id="4f85c-134">You can create additional sets of conferencing configuration settings for specific sites.</span></span> <span data-ttu-id="4f85c-135">Use el cmdlet <STRONG>New-CsConferencingConfiguration</STRONG> con una identidad de sitio.</span><span class="sxs-lookup"><span data-stu-id="4f85c-135">Use the <STRONG>New- CsConferencingConfiguration</STRONG> cmdlet with a site identity.</span></span> <span data-ttu-id="4f85c-136">Al crear nuevas opciones de configuración de conferencia para los sitios, la configuración del sitio tiene prioridad sobre la configuración global.</span><span class="sxs-lookup"><span data-stu-id="4f85c-136">When you create new conferencing configuration settings for sites, the site settings take precedence over the global settings.</span></span> <span data-ttu-id="4f85c-137">Para obtener más información, vea la documentación referente a Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="4f85c-137">For details, see the Lync Server Management Shell documentation.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

