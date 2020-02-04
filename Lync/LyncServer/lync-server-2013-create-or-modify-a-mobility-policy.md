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
ms.openlocfilehash: 3f64e74b389b268027e06b2f4103b0c828c5be6f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758054"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-mobility-policy-in-lync-server-2013"></a><span data-ttu-id="7da19-102">Crear o modificar una directiva de movilidad en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7da19-102">Create or modify a mobility policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7da19-103">_**Última modificación del tema:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="7da19-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="7da19-104">Puede crear o modificar la Directiva de movilidad para permitir a los usuarios móviles usar dispositivos móviles compatibles para las características de Lync, como la mensajería instantánea (mi), la presencia y los contactos.</span><span class="sxs-lookup"><span data-stu-id="7da19-104">You can create or modify mobility policy to allow mobile users to use supported mobile devices for Lync functionality such as instant messaging (IM), presence, and contacts.</span></span> <span data-ttu-id="7da19-105">Puede crear o modificar directivas de movilidad desde el panel de control de Lync Server 2013 o del shell de administración de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7da19-105">You can create or modify mobility policies from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell</span></span>

<div>

## <a name="to-create-a-mobility-policy-with-lync-server-control-panel"></a><span data-ttu-id="7da19-106">Para crear una directiva de movilidad con el panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="7da19-106">To create a mobility policy with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="7da19-107">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="7da19-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="7da19-108">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7da19-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="7da19-109">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="7da19-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="7da19-110">En la barra de navegación izquierda, haga clic en **clientes**y luego en el botón de navegación de la **Directiva de movilidad** .</span><span class="sxs-lookup"><span data-stu-id="7da19-110">In the left navigation bar, click **Clients**, and then click the **Mobility Policy** navigation button.</span></span>

4.  <span data-ttu-id="7da19-111">En la página **Directiva de movilidad** , haga clic en **nuevo**y realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="7da19-111">On the **Mobility Policy** page, click **New**, and do one of the following:</span></span>
    
    1.  <span data-ttu-id="7da19-112">Para crear una directiva de movilidad de sitio, haga clic en **Directiva del sitio**, haga clic en un sitio, haga clic en **Aceptar**, revise la configuración predeterminada y, si lo desea, realice los cambios.</span><span class="sxs-lookup"><span data-stu-id="7da19-112">To create a site mobility policy, click **Site policy**, click a site, click **OK**, review the default settings, and, if you want to, make any changes.</span></span>
    
    2.  <span data-ttu-id="7da19-113">Para crear una directiva de movilidad de usuario, haga clic en **Directiva de usuario**, escriba un nombre, revise la configuración predeterminada y, si lo desea, realice los cambios.</span><span class="sxs-lookup"><span data-stu-id="7da19-113">To create a user mobility policy, click **User policy**, type a name, review the default settings, and if you want to, make any changes.</span></span>

5.  <span data-ttu-id="7da19-114">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="7da19-114">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-a-mobility-policy-with-lync-server-control-panel"></a><span data-ttu-id="7da19-115">Para modificar una directiva de movilidad con el panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="7da19-115">To modify a mobility policy with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="7da19-116">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="7da19-116">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="7da19-117">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7da19-117">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="7da19-118">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="7da19-118">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="7da19-119">En la barra de navegación izquierda, haga clic en **clientes**y luego en el botón de navegación de la **Directiva de movilidad** .</span><span class="sxs-lookup"><span data-stu-id="7da19-119">In the left navigation bar, click **Clients**, and then click the **Mobility Policy** navigation button.</span></span>

4.  <span data-ttu-id="7da19-120">En la página **Directiva de movilidad** , haga clic en una de las directivas de movilidad existentes.</span><span class="sxs-lookup"><span data-stu-id="7da19-120">On the **Mobility Policy** page, click one of the existing mobility policies.</span></span>

5.  <span data-ttu-id="7da19-121">En el menú **Editar**, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="7da19-121">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="7da19-122">Edite cualquiera de los valores de configuración.</span><span class="sxs-lookup"><span data-stu-id="7da19-122">Edit any of the settings.</span></span>

7.  <span data-ttu-id="7da19-123">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="7da19-123">Click **Commit**.</span></span>

</div>

<div>

## <a name="creating-external-access-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="7da19-124">Crear directivas de acceso externas mediante cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7da19-124">Creating External Access Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="7da19-125">Puede crear directivas de movilidad (en el ámbito del sitio o en el ámbito por usuario) mediante Windows PowerShell y el cmdlet **New-CsMobilityPolicy** .</span><span class="sxs-lookup"><span data-stu-id="7da19-125">You can create mobility policies (at the site scope or the per-user scope) by using Windows PowerShell and the **New-CsMobilityPolicy** cmdlet.</span></span> <span data-ttu-id="7da19-126">Además, puede usar el cmdlet **set-CsMobilityPolicy** para modificar cualquiera de las directivas existentes, incluida la directiva global.</span><span class="sxs-lookup"><span data-stu-id="7da19-126">Additionally, you can use the **Set-CsMobilityPolicy** cmdlet to modify any of your existing policies, including the global policy.</span></span> <span data-ttu-id="7da19-127">Estos cmdlets se pueden ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7da19-127">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="7da19-128">Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.</span><span class="sxs-lookup"><span data-stu-id="7da19-128">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-a-mobility-policy-at-the-site-scope"></a><span data-ttu-id="7da19-129">Para crear una directiva de movilidad en el ámbito del sitio</span><span class="sxs-lookup"><span data-stu-id="7da19-129">To create a mobility policy at the site scope</span></span>

  - <span data-ttu-id="7da19-130">Este comando crea una nueva Directiva de movilidad para el sitio de Redmond:</span><span class="sxs-lookup"><span data-stu-id="7da19-130">This command creates a new mobility policy for the Redmond site:</span></span>
    
        New-CsMobilityPolicy -Identity "site:Redmond"
    
    <span data-ttu-id="7da19-131">Dado que no se especificó ningún parámetro (excepto el parámetro de identidad obligatorio) en el comando anterior, las directivas usarán los valores predeterminados para todas sus propiedades.</span><span class="sxs-lookup"><span data-stu-id="7da19-131">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the policies will use the default values for all its properties.</span></span>

</div>

<div>

## <a name="to-create-a-mobility-policy-at-the-per-user-scope"></a><span data-ttu-id="7da19-132">Para crear una directiva de movilidad en el ámbito de cada usuario</span><span class="sxs-lookup"><span data-stu-id="7da19-132">To create a mobility policy at the per-user scope</span></span>

  - <span data-ttu-id="7da19-133">Para crear una directiva de movilidad en el ámbito de cada usuario, especifique una identidad única para la Directiva:</span><span class="sxs-lookup"><span data-stu-id="7da19-133">To create a mobility policy at the per-user scope, specify a unique Identity for the policy:</span></span>
    
        New-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-a-mobility-policy"></a><span data-ttu-id="7da19-134">Para cambiar un único valor de propiedad al crear una directiva de movilidad</span><span class="sxs-lookup"><span data-stu-id="7da19-134">To change a single property value when creating a mobility policy</span></span>

  - <span data-ttu-id="7da19-135">Para crear directivas que usen valores de propiedad diferentes, incluya el parámetro adecuado y el valor de parámetro.</span><span class="sxs-lookup"><span data-stu-id="7da19-135">To create policies that use different property values, include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="7da19-136">Por ejemplo, este comando crea una directiva de movilidad que deshabilita la llamada a través del trabajo:</span><span class="sxs-lookup"><span data-stu-id="7da19-136">For example, this command creates mobility policy that disables Call via Work:</span></span>
    
        New-CsMobilityPolicy -Identity "site:Redmond" -EnableOutsideVoice $False

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-a-mobility-policy"></a><span data-ttu-id="7da19-137">Para cambiar varios valores de propiedad al crear una directiva de movilidad</span><span class="sxs-lookup"><span data-stu-id="7da19-137">To change multiple property values when creating a mobility policy</span></span>

  - <span data-ttu-id="7da19-138">Puede incluir varios parámetros para modificar varios valores de propiedad.</span><span class="sxs-lookup"><span data-stu-id="7da19-138">Multiple property values can be modified by including multiple parameters.</span></span> <span data-ttu-id="7da19-139">Por ejemplo, este comando crea una directiva que deshabilita la movilidad y la llamada a través del trabajo:</span><span class="sxs-lookup"><span data-stu-id="7da19-139">For example, this command creates a policy that disables both mobility and Call via Work:</span></span>
    
        New-CsMobilityPolicy "site:Redmond" -EnableMobility $False -EnableOutsideVoice $False

</div>

<span data-ttu-id="7da19-140">Para obtener más información, vea el tema de ayuda sobre los cmdlets [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy) y [set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy) .</span><span class="sxs-lookup"><span data-stu-id="7da19-140">For details, see the Help topic for the [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy) and the [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy) cmdlets.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7da19-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="7da19-141">See Also</span></span>


[<span data-ttu-id="7da19-142">Configuración de la directiva de movilidad en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7da19-142">Configuring mobility policy in Lync Server 2013</span></span>](lync-server-2013-configuring-mobility-policy.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

