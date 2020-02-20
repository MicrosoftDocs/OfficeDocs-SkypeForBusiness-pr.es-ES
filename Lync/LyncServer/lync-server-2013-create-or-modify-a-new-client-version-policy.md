---
title: 'Lync Server 2013: crear o modificar una nueva Directiva de versión de cliente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a new client version policy
ms:assetid: 4be6e449-aa82-4b46-abb1-d31281573a72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898476(v=OCS.15)
ms:contentKeyID: 50873756
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a941908c30a338c12f6c0a7731ade2f1e411dc38
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146243"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-new-client-version-policy-in-lync-server-2013"></a><span data-ttu-id="22272-102">Crear o modificar una nueva Directiva de versión de cliente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="22272-102">Create or modify a new client version policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="22272-103">_**Última modificación del tema:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="22272-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="22272-104">Puede usar las directivas de versión de cliente para especificar las versiones de clientes que son compatibles con su entorno.</span><span class="sxs-lookup"><span data-stu-id="22272-104">You can use client version policies to specify the versions of clients that are supported in your environment.</span></span> <span data-ttu-id="22272-105">El uso del control de versiones de cliente puede ayudar a reducir los costos asociados a la compatibilidad con varias versiones de cliente.</span><span class="sxs-lookup"><span data-stu-id="22272-105">Using client versioning can help reduce the costs associated with supporting multiple client versions.</span></span> <span data-ttu-id="22272-106">También puede mejorar la experiencia general del usuario, ya que cuando interactúan versiones anteriores y posteriores de los clientes, las características disponibles pueden estar limitadas por la versión anterior del cliente.</span><span class="sxs-lookup"><span data-stu-id="22272-106">It can also improve the overall user experience, because when earlier and later versions of clients interact, the available features can be limited by the earlier version of the client.</span></span> <span data-ttu-id="22272-107">Puede crear o modificar directivas de versión de cliente desde el panel de control de Lync Server 2013 o el shell de administración de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="22272-107">You can create or modify client version policies from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-create-or-modify-client-version-policies-by-using-lync-server-control-panel"></a><span data-ttu-id="22272-108">Para crear o modificar directivas de versión de cliente mediante el panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="22272-108">To create or modify client version policies by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="22272-109">Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="22272-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="22272-110">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="22272-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="22272-111">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="22272-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="22272-112">En la barra de navegación izquierda, haga clic en **Clientes**.</span><span class="sxs-lookup"><span data-stu-id="22272-112">In the left navigation bar, click **Clients**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="22272-113">La pestaña <STRONG>Directiva de versión de cliente</STRONG> está seleccionada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="22272-113">The <STRONG>Client Version Policy</STRONG> tab is selected by default.</span></span>

    
    </div>

4.  <span data-ttu-id="22272-114">En la página **Directiva de versión de cliente** , realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="22272-114">On the **Client Version Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="22272-115">Para crear una directiva de versión de cliente, haga clic en **nuevo**, seleccione Directiva de **sitio**, **Directiva de grupo**de servidores o Directiva de **usuario**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="22272-115">To create a client version policy, click **New**, select **Site policy**, **Pool policy**, or **User policy**, and then click **OK**.</span></span>
    
      - <span data-ttu-id="22272-116">Para modificar la directiva global u otra directiva de versión de cliente existente, seleccione la Directiva, haga clic en **Editar**y, a continuación, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="22272-116">To modify the global policy or another existing client version policy, select the policy, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="22272-117">En la página **Editar Directiva de versión de cliente** , cree o modifique reglas tal y como se describe en [Create or Modify a New Client version Policy Rule in Lync Server 2013](lync-server-2013-create-or-modify-a-new-client-version-policy-rule.md).</span><span class="sxs-lookup"><span data-stu-id="22272-117">On the **Edit Client Version Policy** page, create or modify rules as described in [Create or modify a new client version policy rule in Lync Server 2013](lync-server-2013-create-or-modify-a-new-client-version-policy-rule.md).</span></span>

</div>

<div>

## <a name="creating-or-modifying-client-version-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="22272-118">Creación o modificación de directivas de versión de cliente mediante cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="22272-118">Creating or Modifying Client Version Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="22272-119">Puede crear directivas de versión de cliente con el cmdlet **New-CsClientVersionPolicy** y modificarlas con el cmdlet **set-CsClientVersionPolicy** .</span><span class="sxs-lookup"><span data-stu-id="22272-119">You can create client version policies by using the **New-CsClientVersionPolicy** cmdlet, and modify them by using the **Set-CsClientVersionPolicy** cmdlet.</span></span> <span data-ttu-id="22272-120">Estos cmdlets se pueden ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="22272-120">These cmdlets can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="22272-121">Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.</span><span class="sxs-lookup"><span data-stu-id="22272-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-a-new-site-scoped-client-version-policy"></a><span data-ttu-id="22272-122">Para crear una nueva Directiva de versión de cliente con ámbito en el sitio</span><span class="sxs-lookup"><span data-stu-id="22272-122">To create a new site-scoped client version policy</span></span>

  - <span data-ttu-id="22272-123">El siguiente comando crea una nueva Directiva de versión de cliente que se aplica al sitio Redmond.</span><span class="sxs-lookup"><span data-stu-id="22272-123">The following command creates a new client version policy applied to the Redmond site.</span></span> <span data-ttu-id="22272-124">Como no se especifican parámetros adicionales, la nueva Directiva usará la configuración de versión de cliente predeterminada.</span><span class="sxs-lookup"><span data-stu-id="22272-124">Because no additional parameters are specified, the new policy will use the default client version settings.</span></span>
    
        New-CsClientVersionPolicy -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-new-per-user-client-version-policy"></a><span data-ttu-id="22272-125">Para crear una nueva Directiva de versión de cliente por usuario</span><span class="sxs-lookup"><span data-stu-id="22272-125">To create a new per-user client version policy</span></span>

  - <span data-ttu-id="22272-126">Para crear una directiva por usuario, use un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="22272-126">To create a per-user policy, use a command similar to this:</span></span>
    
        New-CsClientVersionPolicy -Identity "RedmondClientVersionPolicy"

</div>

<span data-ttu-id="22272-127">Para obtener más información, consulte los temas de ayuda del cmdlet [New-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientVersionPolicy) y el cmdlet [set-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionPolicy) .</span><span class="sxs-lookup"><span data-stu-id="22272-127">For details, see the Help topics for the [New-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientVersionPolicy) cmdlet and the [Set-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

