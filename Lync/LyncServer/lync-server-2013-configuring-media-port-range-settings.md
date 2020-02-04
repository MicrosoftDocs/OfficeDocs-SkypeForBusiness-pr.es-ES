---
title: 'Lync Server 2013: configuración de intervalos de puertos de medios'
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
ms.openlocfilehash: 80e835bfcf12495c75612ecee93d87cf3c421651
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755944"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-media-port-range-settings-in-lync-server-2013"></a><span data-ttu-id="f9733-102">Configuración de la configuración de intervalo de puertos de medios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f9733-102">Configuring media port range settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f9733-103">_**Última modificación del tema:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="f9733-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="f9733-104">La configuración de intervalo de puertos de medios puede influir significativamente en el rendimiento del cliente y debe configurarse.</span><span class="sxs-lookup"><span data-stu-id="f9733-104">Media port range settings can significantly impact client performance and should be configured.</span></span> <span data-ttu-id="f9733-105">Puede configurar estas opciones con el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f9733-105">You can configure these settings by using Lync Server Management Shell.</span></span>

### <a name="media-port-range-settings"></a><span data-ttu-id="f9733-106">Configuración de intervalo de puertos de medios</span><span class="sxs-lookup"><span data-stu-id="f9733-106">Media Port Range Settings</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f9733-107">Configuración</span><span class="sxs-lookup"><span data-stu-id="f9733-107">Setting</span></span></th>
<th><span data-ttu-id="f9733-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="f9733-108">Description</span></span></th>
<th><span data-ttu-id="f9733-109">Cmdlet del shell de administración de Lync Server</span><span class="sxs-lookup"><span data-stu-id="f9733-109">Lync Server Management Shell cmdlet</span></span></th>
<th><span data-ttu-id="f9733-110">Parámetros del cmdlet</span><span class="sxs-lookup"><span data-stu-id="f9733-110">Cmdlet parameters</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f9733-111">Portrange\Enabled</span><span class="sxs-lookup"><span data-stu-id="f9733-111">Portrange\Enabled</span></span></p></td>
<td><p><span data-ttu-id="f9733-112">Especifica si el cliente debe usar los intervalos de puertos enviados por el servidor para multimedia y para la señalización.</span><span class="sxs-lookup"><span data-stu-id="f9733-112">Specifies whether the port ranges sent by the server should be used by the client for media and signaling.</span></span> <span data-ttu-id="f9733-113">Se usa junto con los subvalores MinMediaPort y MaxMediaPort.</span><span class="sxs-lookup"><span data-stu-id="f9733-113">Used in conjunction with the subvalues MinMediaPort and MaxMediaPort.</span></span></p></td>
<td><p><span data-ttu-id="f9733-114"><strong>CsConferencingConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="f9733-114"><strong>CsConferencingConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="f9733-115">ClientMediaPortRangeEnabled</span><span class="sxs-lookup"><span data-stu-id="f9733-115">ClientMediaPortRangeEnabled</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f9733-116">Portrange\MinMediaPort</span><span class="sxs-lookup"><span data-stu-id="f9733-116">Portrange\MinMediaPort</span></span></p></td>
<td><p><span data-ttu-id="f9733-117">Especifica el número de puerto de inicio que se va a usar para los medios.</span><span class="sxs-lookup"><span data-stu-id="f9733-117">Specifies the starting port number to use for media.</span></span> <span data-ttu-id="f9733-118">Se combina con MaxMediaPort para especificar el rango de puertos.</span><span class="sxs-lookup"><span data-stu-id="f9733-118">Combines with MaxMediaPort to specify the range of ports.</span></span> <span data-ttu-id="f9733-119">El intervalo mínimo recomendado es 40 puertos.</span><span class="sxs-lookup"><span data-stu-id="f9733-119">The recommended minimum range is 40 ports.</span></span></p></td>
<td><p><span data-ttu-id="f9733-120"><strong>CsConferencingConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="f9733-120"><strong>CsConferencingConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="f9733-121">ClientMediaPort (representa el número de puerto de inicio para usar en los medios del cliente)</span><span class="sxs-lookup"><span data-stu-id="f9733-121">ClientMediaPort (represents the starting port number to use for client media)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f9733-122">Portrange\MaxMediaPort</span><span class="sxs-lookup"><span data-stu-id="f9733-122">Portrange\MaxMediaPort</span></span></p></td>
<td><p><span data-ttu-id="f9733-123">Especifica el número de puerto más alto que se debe usar para los medios.</span><span class="sxs-lookup"><span data-stu-id="f9733-123">Specifies the highest port number to use for media.</span></span> <span data-ttu-id="f9733-124">Se combina con MinMediaPort para especificar el rango de puertos.</span><span class="sxs-lookup"><span data-stu-id="f9733-124">Combines with MinMediaPort to specify the range of ports.</span></span> <span data-ttu-id="f9733-125">El intervalo mínimo recomendado es 40 puertos.</span><span class="sxs-lookup"><span data-stu-id="f9733-125">The recommended minimum range is 40 ports.</span></span></p></td>
<td><p><span data-ttu-id="f9733-126"><strong>CsConferencingConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="f9733-126"><strong>CsConferencingConfiguration</strong></span></span></p></td>
<td><p><span data-ttu-id="f9733-127">ClientMediaPortRange (indica el número total de puertos disponibles para los medios de cliente; el valor predeterminado es 40)</span><span class="sxs-lookup"><span data-stu-id="f9733-127">ClientMediaPortRange (indicates the total number of ports available for client media; default is 40)</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-media-port-range-settings"></a><span data-ttu-id="f9733-128">Para configurar las opciones de intervalo de puertos de medios</span><span class="sxs-lookup"><span data-stu-id="f9733-128">To Configure Media Port Range Settings</span></span>

1.  <span data-ttu-id="f9733-129">Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="f9733-129">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="f9733-130">Ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="f9733-130">Run the following cmdlet:</span></span>
    
        Get-CsConferencingConfiguration
    
    <span data-ttu-id="f9733-131">Este cmdlet devuelve la configuración de la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="f9733-131">This cmdlet returns the conferencing configuration settings.</span></span>

3.  <span data-ttu-id="f9733-132">Ejecute el siguiente cmdlet con los parámetros y valores que desea cambiar (para obtener información detallada sobre los parámetros para este cmdlet, consulte la documentación del shell de administración de Lync Server):</span><span class="sxs-lookup"><span data-stu-id="f9733-132">Run the following cmdlet with the parameters and values you want to change (for details about the parameters for this cmdlet, see the Lync Server Management Shell documentation):</span></span>
    
        Set-CsConferencingConfiguration
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f9733-133">Puede crear más conjuntos de parámetros de configuración de conferencias para sitios específicos.</span><span class="sxs-lookup"><span data-stu-id="f9733-133">You can create additional sets of conferencing configuration settings for specific sites.</span></span> <span data-ttu-id="f9733-134">Use el cmdlet <STRONG>New-CsConferencingConfiguration</STRONG> con una identidad de sitio.</span><span class="sxs-lookup"><span data-stu-id="f9733-134">Use the <STRONG>New- CsConferencingConfiguration</STRONG> cmdlet with a site identity.</span></span> <span data-ttu-id="f9733-135">Al crear nuevas opciones de configuración de conferencias para sitios, la configuración del sitio tiene prioridad sobre la configuración global.</span><span class="sxs-lookup"><span data-stu-id="f9733-135">When you create new conferencing configuration settings for sites, the site settings take precedence over the global settings.</span></span> <span data-ttu-id="f9733-136">Para obtener más información, consulte la documentación del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f9733-136">For details, see the Lync Server Management Shell documentation.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

