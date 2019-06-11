---
title: 'Lync Server 2013: crear o modificar una nueva Directiva de versión de cliente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a new client version policy
ms:assetid: 4be6e449-aa82-4b46-abb1-d31281573a72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898476(v=OCS.15)
ms:contentKeyID: 50873756
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 64e9d9d2879d4633b1775f8934186b8b01992d13
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835779"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-new-client-version-policy-in-lync-server-2013"></a><span data-ttu-id="dd502-102">Crear o modificar una nueva Directiva de versión de cliente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dd502-102">Create or modify a new client version policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dd502-103">_**Última modificación del tema:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="dd502-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="dd502-104">Puede usar las directivas de versión de cliente para especificar las versiones de clientes que se admiten en su entorno.</span><span class="sxs-lookup"><span data-stu-id="dd502-104">You can use client version policies to specify the versions of clients that are supported in your environment.</span></span> <span data-ttu-id="dd502-105">El uso del control de versiones de cliente puede ayudar a reducir los costos asociados a la compatibilidad de varias versiones de cliente.</span><span class="sxs-lookup"><span data-stu-id="dd502-105">Using client versioning can help reduce the costs associated with supporting multiple client versions.</span></span> <span data-ttu-id="dd502-106">También puede mejorar la experiencia general del usuario, ya que cuando interactúan versiones anteriores y posteriores de los clientes, las características disponibles pueden verse limitadas por la versión anterior del cliente.</span><span class="sxs-lookup"><span data-stu-id="dd502-106">It can also improve the overall user experience, because when earlier and later versions of clients interact, the available features can be limited by the earlier version of the client.</span></span> <span data-ttu-id="dd502-107">Puede crear o modificar directivas de versión de cliente desde el panel de control de Lync Server 2013 o del shell de administración de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dd502-107">You can create or modify client version policies from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-create-or-modify-client-version-policies-by-using-lync-server-control-panel"></a><span data-ttu-id="dd502-108">Para crear o modificar directivas de versión de cliente con el panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="dd502-108">To create or modify client version policies by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="dd502-109">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="dd502-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="dd502-110">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="dd502-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="dd502-111">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="dd502-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="dd502-112">En la barra de navegación izquierda, haga clic en **clientes**.</span><span class="sxs-lookup"><span data-stu-id="dd502-112">In the left navigation bar, click **Clients**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="dd502-113">La pestaña <STRONG>Directiva de versión del cliente</STRONG> está seleccionada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="dd502-113">The <STRONG>Client Version Policy</STRONG> tab is selected by default.</span></span>

    
    </div>

4.  <span data-ttu-id="dd502-114">En la página **Directiva de versión del cliente** , realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="dd502-114">On the **Client Version Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="dd502-115">Para crear una directiva de versión de cliente, haga clic en **nuevo**, seleccione **Directiva de sitio**, **Directiva de grupo**o **Directiva de usuario**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="dd502-115">To create a client version policy, click **New**, select **Site policy**, **Pool policy**, or **User policy**, and then click **OK**.</span></span>
    
      - <span data-ttu-id="dd502-116">Para modificar la directiva global u otra directiva de versión de cliente existente, seleccione la Directiva, haga clic en **Editar**y, a continuación, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="dd502-116">To modify the global policy or another existing client version policy, select the policy, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="dd502-117">En la página **Editar Directiva de versión del cliente** , cree o modifique reglas tal y como se describe en [crear o modificar una nueva regla de versión de cliente en Lync Server 2013](lync-server-2013-create-or-modify-a-new-client-version-policy-rule.md).</span><span class="sxs-lookup"><span data-stu-id="dd502-117">On the **Edit Client Version Policy** page, create or modify rules as described in [Create or modify a new client version policy rule in Lync Server 2013](lync-server-2013-create-or-modify-a-new-client-version-policy-rule.md).</span></span>

</div>

<div>

## <a name="creating-or-modifying-client-version-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="dd502-118">Crear o modificar directivas de versión de cliente con cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="dd502-118">Creating or Modifying Client Version Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="dd502-119">Puede crear directivas de versión de cliente con el cmdlet **New-CsClientVersionPolicy** y modificarlas mediante el cmdlet **set-CsClientVersionPolicy** .</span><span class="sxs-lookup"><span data-stu-id="dd502-119">You can create client version policies by using the **New-CsClientVersionPolicy** cmdlet, and modify them by using the **Set-CsClientVersionPolicy** cmdlet.</span></span> <span data-ttu-id="dd502-120">Estos cmdlets se pueden ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dd502-120">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="dd502-121">Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.</span><span class="sxs-lookup"><span data-stu-id="dd502-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-a-new-site-scoped-client-version-policy"></a><span data-ttu-id="dd502-122">Para crear una nueva Directiva de versión de cliente con ámbito de sitio</span><span class="sxs-lookup"><span data-stu-id="dd502-122">To create a new site-scoped client version policy</span></span>

  - <span data-ttu-id="dd502-123">El siguiente comando crea una nueva Directiva de versión de cliente que se aplica al sitio de Redmond.</span><span class="sxs-lookup"><span data-stu-id="dd502-123">The following command creates a new client version policy applied to the Redmond site.</span></span> <span data-ttu-id="dd502-124">Como no se especifican parámetros adicionales, la nueva Directiva usará la configuración de versión de cliente predeterminada.</span><span class="sxs-lookup"><span data-stu-id="dd502-124">Because no additional parameters are specified, the new policy will use the default client version settings.</span></span>
    
        New-CsClientVersionPolicy -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-new-per-user-client-version-policy"></a><span data-ttu-id="dd502-125">Para crear una nueva Directiva de versión de cliente por usuario</span><span class="sxs-lookup"><span data-stu-id="dd502-125">To create a new per-user client version policy</span></span>

  - <span data-ttu-id="dd502-126">Para crear una directiva por usuario, use un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="dd502-126">To create a per-user policy, use a command similar to this:</span></span>
    
        New-CsClientVersionPolicy -Identity "RedmondClientVersionPolicy"

</div>

<span data-ttu-id="dd502-127">Para obtener más información, consulte los temas de ayuda para el cmdlet [New-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientVersionPolicy) y el cmdlet [set-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionPolicy) .</span><span class="sxs-lookup"><span data-stu-id="dd502-127">For details, see the Help topics for the [New-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientVersionPolicy) cmdlet and the [Set-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

