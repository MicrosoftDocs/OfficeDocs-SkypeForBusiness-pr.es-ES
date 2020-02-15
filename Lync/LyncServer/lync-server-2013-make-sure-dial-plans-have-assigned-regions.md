---
title: 'Lync Server 2013: asegurarse de que los planes de marcado tienen regiones asignadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Make sure dial plans have assigned regions
ms:assetid: 3da3a907-0dbf-4440-b12f-370f94dd4c17
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425903(v=OCS.15)
ms:contentKeyID: 48183937
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f25ca766ab7292aeeba0d2e621eccff5a0c47fb8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037570"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="make-sure-dial-plans-lync-server-2013-have-assigned-regions"></a><span data-ttu-id="4fcf0-102">Asegurarse de que los planes de marcado Lync Server 2013 tienen regiones asignadas</span><span class="sxs-lookup"><span data-stu-id="4fcf0-102">Make sure dial plans Lync Server 2013 have assigned regions</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4fcf0-103">_**Última modificación del tema:** 2010-11-02_</span><span class="sxs-lookup"><span data-stu-id="4fcf0-103">_**Topic Last Modified:** 2010-11-02_</span></span>

<span data-ttu-id="4fcf0-p101">Debe haberse especificado una **Región de conferencias de acceso telefónico local** para los planes de marcado que se utilicen para conferencias de acceso telefónico para poder asociar los números de acceso a conferencias de acceso telefónico local con el plan de marcado adecuado. Cuando se configura un plan de marcado, se especifica la región de conferencias de acceso telefónico local que se aplica a dicho plan de marcado. A continuación, cuando se crea el número de acceso telefónico local, se seleccionan las regiones que asocian el número de acceso con los planes de marcado adecuados.</span><span class="sxs-lookup"><span data-stu-id="4fcf0-p101">Dial plans that are used for dial-in conferencing need to have a **Dial-in conferencing region** specified to associate dial-in conferencing access numbers with the appropriate dial plan. When you set up a dial plan, you specify the dial-in conferencing region that applies to that dial plan. Then, when you create the dial-in access number, you select the regions that associate the access number with the appropriate dial plans.</span></span>

<span data-ttu-id="4fcf0-p102">Como es importante especificar una región para todos los planes de marcado, se recomienda usar este procedimiento para comprobar que todos los planes de marcado tienen regiones. Este paso es opcional.</span><span class="sxs-lookup"><span data-stu-id="4fcf0-p102">Because it important to specify a region for all dial plans, we recommend that you use this procedure to verify that all dial plans have regions. This step is optional.</span></span>

<span data-ttu-id="4fcf0-109">Use el cmdlet **Get-CsDialPlan** para comprobar si se ha establecido la región en todos los planes de marcado de conferencia de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="4fcf0-109">Use the **Get-CsDialPlan** cmdlet to verify whether the region is set for all dial-in conferencing dial plans.</span></span> <span data-ttu-id="4fcf0-110">Si falta la región en los planes de marcado, puede usar el cmdlet **Set-CsDialPlan** para establecerla.</span><span class="sxs-lookup"><span data-stu-id="4fcf0-110">If the region is missing from dial plans, you can use the **Set-CsDialPlan** cmdlet to set the region.</span></span> <span data-ttu-id="4fcf0-111">También puede usar el panel de control de Lync Server para actualizar la región en los planes de marcado existentes.</span><span class="sxs-lookup"><span data-stu-id="4fcf0-111">You can also use Lync Server Control Panel to update the region in existing dial plans.</span></span> <span data-ttu-id="4fcf0-112">Para obtener más información sobre el uso del panel de control de Lync Server, consulte [modificar un plan de marcado en Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span><span class="sxs-lookup"><span data-stu-id="4fcf0-112">For details about using Lync Server Control Panel, see [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span></span>

<div>

## <a name="to-verify-whether-dial-plans-have-the-region-property-set"></a><span data-ttu-id="4fcf0-113">Para comprobar si se ha establecido la propiedad Región en los planes de marcado</span><span class="sxs-lookup"><span data-stu-id="4fcf0-113">To verify whether dial plans have the region property set</span></span>

1.  <span data-ttu-id="4fcf0-114">Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol **Cs-VoiceAdministrator**, **Cs-ServerAdministrator** o **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="4fcf0-114">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-VoiceAdministrator**, **Cs-ServerAdministrator**, or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="4fcf0-115">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="4fcf0-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="4fcf0-116">Ejecute los siguientes comandos en símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="4fcf0-116">Run the following at the command prompt:</span></span>
    
        Get-CsDialPlan [-Identity <Identifier of the dial plans to be retrieved>]
    
    <span data-ttu-id="4fcf0-117">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="4fcf0-117">For example:</span></span>
    
        Get-CsDialPlan
    
    <span data-ttu-id="4fcf0-118">En este ejemplo, se devuelven todos los planes de marcado configurados para la organización.</span><span class="sxs-lookup"><span data-stu-id="4fcf0-118">In this example, all the dial plans configured for your organization are returned.</span></span>

4.  <span data-ttu-id="4fcf0-119">Revise los planes de marcado devueltos para identificar si a alguno le falta la región de conferencias de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="4fcf0-119">Review the returned dial plans to identify any that are missing the dial-in conferencing region.</span></span> <span data-ttu-id="4fcf0-120">Para obtener más información, vea la documentación referente a Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="4fcf0-120">For details, see the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="to-set-the-region-property-for-a-dial-plan"></a><span data-ttu-id="4fcf0-121">Para establecer la propiedad Región en un plan de marcado</span><span class="sxs-lookup"><span data-stu-id="4fcf0-121">To set the region property for a dial plan</span></span>

1.  <span data-ttu-id="4fcf0-122">Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol **Cs-VoiceAdministrator**, **Cs-ServerAdministrator** o **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="4fcf0-122">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-VoiceAdministrator**, **Cs-ServerAdministrator**, or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="4fcf0-123">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="4fcf0-123">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="4fcf0-124">Para los planes de marcado a los que les falte la región de conferencias de acceso telefónico local, ejecute:</span><span class="sxs-lookup"><span data-stu-id="4fcf0-124">For any dial plans that are missing the dial-in conferencing region, run:</span></span>
    
        Set-CsDialPlan [-Identity <Identity of the dial plan to be modified>] -DialinConferencingRegion "<new region>"
    
    <span data-ttu-id="4fcf0-125">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="4fcf0-125">For example:</span></span>
    
        Set-CsDialPlan -Identity Redmond -DialinConferencingRegion "US West Coast"
    
    <span data-ttu-id="4fcf0-126">En este ejemplo, el plan de marcado con la identidad de Redmond se modifica para establecer la propiedad DialinConferencingRegion en "US West Coast".</span><span class="sxs-lookup"><span data-stu-id="4fcf0-126">In this example, the dial plan with the Identity of Redmond is modified to set the DialinConferencingRegion property to "US West Coast".</span></span> <span data-ttu-id="4fcf0-127">Para obtener más información, vea la documentación referente a Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="4fcf0-127">For details, see the Lync Server Management Shell documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

