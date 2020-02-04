---
title: 'Lync Server 2013: eliminar una intervalo orbitar de llamada'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a Call Park orbit range
ms:assetid: 85e9f916-062d-450d-ac0a-aeaefc0f7cdc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182546(v=OCS.15)
ms:contentKeyID: 48184713
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 934559f1b67c1325684ee5b477be18ed112224df
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726220"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-call-park-orbit-range-in-lync-server-2013"></a><span data-ttu-id="24281-102">Eliminar un intervalo orbitar de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24281-102">Delete a Call Park orbit range in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="24281-103">_**Última modificación del tema:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="24281-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="24281-104">Use uno de los procedimientos siguientes para eliminar un intervalo de llamada en órbita.</span><span class="sxs-lookup"><span data-stu-id="24281-104">Use one of the following procedures to delete a Call Park orbit range.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-to-delete-a-call-park-orbit-range"></a><span data-ttu-id="24281-105">Para usar el panel de control de Lync Server para eliminar un intervalo orbitar de llamadas</span><span class="sxs-lookup"><span data-stu-id="24281-105">To use Lync Server Control Panel to delete a Call Park orbit range</span></span>

1.  <span data-ttu-id="24281-106">Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="24281-106">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="24281-107">Para obtener más información, consulte [permisos de configuración de delegación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="24281-107">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="24281-108">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="24281-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="24281-109">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="24281-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="24281-110">En la barra de navegación izquierda, haga clic en **Características de voz** y, a continuación, en **Estacionamiento de llamadas**.</span><span class="sxs-lookup"><span data-stu-id="24281-110">In the left navigation bar, click **Voice Features** and then click **Call Park**.</span></span>

4.  <span data-ttu-id="24281-111">En la página de **llamada estacionamiento** , en el campo de búsqueda, escriba todo o parte del nombre del rango de órbita que desea eliminar.</span><span class="sxs-lookup"><span data-stu-id="24281-111">On the **Call Park** page, in the search field, type all or part of the name of the orbit range that you want to delete.</span></span>

5.  <span data-ttu-id="24281-112">En la lista resultante de órbitas, haga clic en la órbita, haga clic en **Editar**y, a continuación, haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="24281-112">In the resulting list of orbits, click the orbit, click **Edit**, and then click **Delete**.</span></span>

6.  <span data-ttu-id="24281-113">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="24281-113">Click **OK**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-delete-a-call-park-orbit-range"></a><span data-ttu-id="24281-114">Para usar Windows PowerShell para eliminar un intervalo de llamada de Parque orbital</span><span class="sxs-lookup"><span data-stu-id="24281-114">To use Windows PowerShell to delete a Call Park orbit range</span></span>

1.  <span data-ttu-id="24281-115">Inicie sesión en el equipo donde está instalado el shell de administración de Lync Server como miembro del grupo RTCUniversalServerAdmins o con los derechos de usuario necesarios, tal y como se describe en [permisos de configuración de delegado en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="24281-115">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="24281-116">Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="24281-116">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="24281-117">En la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="24281-117">At the command line, type:</span></span>
    
        Remove-CsCallParkOrbit -Identity "<orbit range name>" 
    
    <span data-ttu-id="24281-118">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="24281-118">For example:</span></span>
    
        Remove-CsCallParkOrbit -Identity "Redmond orbit 1"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="24281-119">Para obtener más información sobre más opciones, consulte <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsCallParkOrbit">Remove-CsCallParkOrbit</A>.</span><span class="sxs-lookup"><span data-stu-id="24281-119">For details about more options, see <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsCallParkOrbit">Remove-CsCallParkOrbit</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="24281-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="24281-120">See Also</span></span>


[<span data-ttu-id="24281-121">Crear o modificar un intervalo orbitar de llamadas en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="24281-121">Create or modify a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)  


[<span data-ttu-id="24281-122">Remove-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="24281-122">Remove-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsCallParkOrbit)  
[<span data-ttu-id="24281-123">Get-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="24281-123">Get-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCallParkOrbit)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

