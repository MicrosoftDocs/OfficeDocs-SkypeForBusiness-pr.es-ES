---
title: 'Lync Server 2013: crear o modificar una directiva de movilidad'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a mobility policy
ms:assetid: fc2dfea0-2215-440d-9f4b-7c985da29211
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721946(v=OCS.15)
ms:contentKeyID: 49733884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 469b7789de98cee3d399e09c9cec4396fdb365e9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048691"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-mobility-policy-in-lync-server-2013"></a><span data-ttu-id="21d7e-102">Crear o modificar una directiva de movilidad en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="21d7e-102">Create or modify a mobility policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="21d7e-103">_**Última modificación del tema:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="21d7e-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="21d7e-104">Puede crear o modificar directivas de movilidad para permitir a los usuarios de móviles utilizar los dispositivos móviles compatibles para las funcionalidades de Lync, como la mensajería instantánea (MI), presencia y contactos.</span><span class="sxs-lookup"><span data-stu-id="21d7e-104">You can create or modify mobility policy to allow mobile users to use supported mobile devices for Lync functionality such as instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="21d7e-105">Puede crear o modificar directivas de movilidad desde el panel de control de Lync Server 2013 o el shell de administración de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="21d7e-105">You can create or modify mobility policies from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell</span></span>

<div>

## <a name="to-create-a-mobility-policy-with-lync-server-control-panel"></a><span data-ttu-id="21d7e-106">Para crear una directiva de movilidad con el panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="21d7e-106">To create a mobility policy with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="21d7e-107">Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="21d7e-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="21d7e-108">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="21d7e-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="21d7e-109">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="21d7e-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="21d7e-110">En la barra de navegación izquierda, haga clic en **Clientes** y, a continuación, en el botón de navegación **Directiva de movilidad**.</span><span class="sxs-lookup"><span data-stu-id="21d7e-110">In the left navigation bar, click **Clients**, and then click the **Mobility Policy** navigation button.</span></span>

4.  <span data-ttu-id="21d7e-111">En la página **Directiva de movilidad** , haga clic en **nuevo**y realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="21d7e-111">On the **Mobility Policy** page, click **New**, and do one of the following:</span></span>
    
    1.  <span data-ttu-id="21d7e-112">Para crear una directiva de movilidad de sitio, haga clic en **Directiva de sitio**, haga clic en un sitio y en **Aceptar**. Reviste la configuración predeterminada y realice los cambios que desee.</span><span class="sxs-lookup"><span data-stu-id="21d7e-112">To create a site mobility policy, click **Site policy**, click a site, click **OK**, review the default settings, and, if you want to, make any changes.</span></span>
    
    2.  <span data-ttu-id="21d7e-113">Para crear una directiva de movilidad, haga clic en **Directiva de usuario**, escriba un nombre, revise la configuración predeterminada y realice los cambios que desee.</span><span class="sxs-lookup"><span data-stu-id="21d7e-113">To create a user mobility policy, click **User policy**, type a name, review the default settings, and if you want to, make any changes.</span></span>

5.  <span data-ttu-id="21d7e-114">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="21d7e-114">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-a-mobility-policy-with-lync-server-control-panel"></a><span data-ttu-id="21d7e-115">Para modificar una directiva de movilidad con el panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="21d7e-115">To modify a mobility policy with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="21d7e-116">Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="21d7e-116">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="21d7e-117">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="21d7e-117">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="21d7e-118">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="21d7e-118">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="21d7e-119">En la barra de navegación izquierda, haga clic en **Clientes** y, a continuación, en el botón de navegación **Directiva de movilidad**.</span><span class="sxs-lookup"><span data-stu-id="21d7e-119">In the left navigation bar, click **Clients**, and then click the **Mobility Policy** navigation button.</span></span>

4.  <span data-ttu-id="21d7e-120">En la página **Directiva de movilidad** , haga clic en una de las directivas de movilidad existentes.</span><span class="sxs-lookup"><span data-stu-id="21d7e-120">On the **Mobility Policy** page, click one of the existing mobility policies.</span></span>

5.  <span data-ttu-id="21d7e-121">En el menú \*\*Editar \*\*, haga clic en \*\*Mostrar detalles \*\*.</span><span class="sxs-lookup"><span data-stu-id="21d7e-121">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="21d7e-122">Edite cualquiera de las opciones.</span><span class="sxs-lookup"><span data-stu-id="21d7e-122">Edit any of the settings.</span></span>

7.  <span data-ttu-id="21d7e-123">Haga clic en \*\*Confirmar \*\*.</span><span class="sxs-lookup"><span data-stu-id="21d7e-123">Click **Commit**.</span></span>

</div>

<div>

## <a name="creating-external-access-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="21d7e-124">Creación de directivas de acceso externo mediante cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="21d7e-124">Creating External Access Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="21d7e-125">Puede crear directivas de movilidad (en el ámbito del sitio o en el ámbito por usuario) mediante Windows PowerShell y el cmdlet **New-CsMobilityPolicy** .</span><span class="sxs-lookup"><span data-stu-id="21d7e-125">You can create mobility policies (at the site scope or the per-user scope) by using Windows PowerShell and the **New-CsMobilityPolicy** cmdlet.</span></span> <span data-ttu-id="21d7e-126">Además, puede utilizar el cmdlet **Set-CsMobilityPolicy** para modificar cualquiera de las directivas existentes, incluida la directiva global.</span><span class="sxs-lookup"><span data-stu-id="21d7e-126">Additionally, you can use the **Set-CsMobilityPolicy** cmdlet to modify any of your existing policies, including the global policy.</span></span> <span data-ttu-id="21d7e-127">Estos cmdlets se pueden ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="21d7e-127">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="21d7e-128">Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.</span><span class="sxs-lookup"><span data-stu-id="21d7e-128">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-a-mobility-policy-at-the-site-scope"></a><span data-ttu-id="21d7e-129">Para crear una directiva de movilidad en el ámbito de sitio</span><span class="sxs-lookup"><span data-stu-id="21d7e-129">To create a mobility policy at the site scope</span></span>

  - <span data-ttu-id="21d7e-130">Este comando crea una directiva de movilidad nueva para el sitio Redmond:</span><span class="sxs-lookup"><span data-stu-id="21d7e-130">This command creates a new mobility policy for the Redmond site:</span></span>
    
        New-CsMobilityPolicy -Identity "site:Redmond"
    
    <span data-ttu-id="21d7e-131">Como no se han especificado parámetros (aparte del parámetro obligatorio Identity) en el comando anterior, las directivas utilizarán los valores predeterminados en todas sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="21d7e-131">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the policies will use the default values for all its properties.</span></span>

</div>

<div>

## <a name="to-create-a-mobility-policy-at-the-per-user-scope"></a><span data-ttu-id="21d7e-132">Para crear una directiva de movilidad en el ámbito por usuario</span><span class="sxs-lookup"><span data-stu-id="21d7e-132">To create a mobility policy at the per-user scope</span></span>

  - <span data-ttu-id="21d7e-133">Para crear una directiva de movilidad en el ámbito de usuario, especifique una identidad única para la directiva:</span><span class="sxs-lookup"><span data-stu-id="21d7e-133">To create a mobility policy at the per-user scope, specify a unique Identity for the policy:</span></span>
    
        New-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-a-mobility-policy"></a><span data-ttu-id="21d7e-134">Para cambiar un valor de propiedad único al crear una directiva de movilidad</span><span class="sxs-lookup"><span data-stu-id="21d7e-134">To change a single property value when creating a mobility policy</span></span>

  - <span data-ttu-id="21d7e-p105">Para crear directivas que utilicen diferentes valores de propiedad, incluya el parámetro adecuado y el valor de parámetro. Por ejemplo, este comando crea una directiva de movilidad que deshabilita las llamadas vía trabajo:</span><span class="sxs-lookup"><span data-stu-id="21d7e-p105">To create policies that use different property values, include the appropriate parameter and parameter value. For example, this command creates mobility policy that disables Call via Work:</span></span>
    
        New-CsMobilityPolicy -Identity "site:Redmond" -EnableOutsideVoice $False

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-a-mobility-policy"></a><span data-ttu-id="21d7e-137">Para cambiar varios valores de propiedad al crear una directiva de movilidad</span><span class="sxs-lookup"><span data-stu-id="21d7e-137">To change multiple property values when creating a mobility policy</span></span>

  - <span data-ttu-id="21d7e-p106">Se pueden modificar varios valores de propiedad incluyendo varios parámetros. Por ejemplo, este comando crea una directiva que deshabilita tanto la movilidad como la llamada vía trabajo:</span><span class="sxs-lookup"><span data-stu-id="21d7e-p106">Multiple property values can be modified by including multiple parameters. For example, this command creates a policy that disables both mobility and Call via Work:</span></span>
    
        New-CsMobilityPolicy "site:Redmond" -EnableMobility $False -EnableOutsideVoice $False

</div>

<span data-ttu-id="21d7e-140">Para obtener más información, consulte el tema de ayuda relativo a los cmdlets [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy) y [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy).</span><span class="sxs-lookup"><span data-stu-id="21d7e-140">For details, see the Help topic for the [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy) and the [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy) cmdlets.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="21d7e-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="21d7e-141">See Also</span></span>


[<span data-ttu-id="21d7e-142">Configuración de la Directiva de movilidad en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="21d7e-142">Configuring mobility policy in Lync Server 2013</span></span>](lync-server-2013-configuring-mobility-policy.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

