---
title: 'Lync Server 2013: configurar rutas de voz para llamadas salientes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring voice routes for outbound calls
ms:assetid: 3c182cdd-7a4a-4a9d-bdac-4199f0abd947
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425890(v=OCS.15)
ms:contentKeyID: 48183875
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f2e3f8fed51dd671a3012f5488569b2e38232be5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536967"
---
# <a name="configuring-voice-routes-for-outbound-calls-in-lync-server-2013"></a><span data-ttu-id="6bf27-102">Configurar rutas de voz para llamadas salientes en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6bf27-102">Configuring voice routes for outbound calls in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6bf27-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="6bf27-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="6bf27-104">Una ruta de voz de Lync Server 2013 asocia los números de teléfono de destino con una o más puertas de enlace de red telefónica conmutada (RTC) o troncos SIP y uno o más registros de uso de RTC.</span><span class="sxs-lookup"><span data-stu-id="6bf27-104">A Lync Server 2013 voice route associates destination phone numbers with one or more public switched telephone network (PSTN) gateways or SIP trunks and one or more PSTN usage records.</span></span>

<span data-ttu-id="6bf27-105">**Para ver las rutas de voz con el panel de control de Lync Server**</span><span class="sxs-lookup"><span data-stu-id="6bf27-105">**To view voice routes by using Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="6bf27-106">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6bf27-106">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="6bf27-107">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="6bf27-107">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="6bf27-108">Haga clic en **Enrutamiento de voz**.</span><span class="sxs-lookup"><span data-stu-id="6bf27-108">Click **Voice Routing**.</span></span>

3.  <span data-ttu-id="6bf27-109">Haga clic en **Ruta**.</span><span class="sxs-lookup"><span data-stu-id="6bf27-109">Click **Route**.</span></span>

4.  <span data-ttu-id="6bf27-p102">Haga doble clic en una ruta de voz para ver otras propiedades de la lista de rutas de voz o seleccione la ruta y haga clic en **Editar**. A continuación, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="6bf27-p102">Double-click a voice route to view additional properties from the list of voice routes, or select the route and click **Edit**. Then click **Show details**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6bf27-112">Solamente puede ver información detallada para una única ruta a la vez.</span><span class="sxs-lookup"><span data-stu-id="6bf27-112">You can only view detailed information for a single route at a time.</span></span>

    
    </div>

<span data-ttu-id="6bf27-113">**Para ver las rutas de voz con Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="6bf27-113">**To view voice routes by using Windows PowerShell**</span></span>

  - <span data-ttu-id="6bf27-114">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="6bf27-114">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span> <span data-ttu-id="6bf27-115">Las rutas de voz se pueden ver con Windows PowerShell y el cmdlet **Get-CsVoiceRoute** .</span><span class="sxs-lookup"><span data-stu-id="6bf27-115">Voice routes can be viewed by using Windows PowerShell and the **Get-CsVoiceRoute** cmdlet.</span></span> <span data-ttu-id="6bf27-116">Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6bf27-116">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="6bf27-117">Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server 2010 mediante PowerShell remoto" en [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="6bf27-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>
    
    <span data-ttu-id="6bf27-118">Para ver información sobre todas las rutas de voz, escriba el siguiente comando en el shell de administración de Lync Server y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="6bf27-118">To view information about all of your voice routes, type the following command in the Lync Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsVoiceRoute
    
    <span data-ttu-id="6bf27-119">Devolverá información similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="6bf27-119">That will return information similar to this:</span></span>
    
        Identity          : global
        Priority          : -1
        Description       :
        NumberPattern     : ^(\+1[0-9]{10})$
        PstnUsages        : {}
        PstnGatewayList   : {}
        Name              : global
        SuppressCallerId  :
        AlternateCallerId :

<div>


> [!NOTE]  
> <span data-ttu-id="6bf27-120">Para obtener más información, consulte <A href="lync-server-2013-voice-routes.md">rutas de voz en Lync Server 2013</A> en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="6bf27-120">For details, see <A href="lync-server-2013-voice-routes.md">Voice routes in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6bf27-121">En esta sección</span><span class="sxs-lookup"><span data-stu-id="6bf27-121">In This Section</span></span>

  - [<span data-ttu-id="6bf27-122">Crear una ruta de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6bf27-122">Create a voice route in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-route.md)

  - [<span data-ttu-id="6bf27-123">Modificar una ruta de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6bf27-123">Modify a voice route in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-route.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6bf27-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6bf27-124">See Also</span></span>


[<span data-ttu-id="6bf27-125">Administrar el enrutamiento de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6bf27-125">Managing voice routing in Lync Server 2013</span></span>](lync-server-2013-managing-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

