---
title: 'Lync Server 2013: ver números de acceso a conferencias de acceso telefónico local'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View dial-in conferencing access numbers
ms:assetid: 41a7dfb4-0c89-4650-b61b-0e1bf875c62b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688037(v=OCS.15)
ms:contentKeyID: 49733628
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b9d9e6ca8d4f388edf6f04f4012726f6abee9e9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850111"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-dial-in-conferencing-access-numbers-in-lync-server-2013"></a><span data-ttu-id="f0a0a-102">Ver los números de acceso a la Conferencia de acceso telefónico local en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0a0a-102">View dial-in conferencing access numbers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f0a0a-103">_**Última modificación del tema:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="f0a0a-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="f0a0a-104">En el panel de control de Lync Server 2013, proporciona números de acceso telefónico local a los usuarios para que puedan unirse a una reunión de forma externa.</span><span class="sxs-lookup"><span data-stu-id="f0a0a-104">In Lync Server 2013 Control Panel, you provide dial-in access numbers to users so that they can join a meeting externally.</span></span>

<div>

## <a name="to-view-dial-in-access-numbers"></a><span data-ttu-id="f0a0a-105">Para ver los números de acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="f0a0a-105">To view dial-in access numbers</span></span>

1.  <span data-ttu-id="f0a0a-106">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="f0a0a-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f0a0a-107">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f0a0a-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f0a0a-108">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f0a0a-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f0a0a-109">En la barra de navegación de la izquierda, haga clic en **Conferencia** y después en **Número de acceso telefónico local**.</span><span class="sxs-lookup"><span data-stu-id="f0a0a-109">In the left navigation bar, click **Conferencing** and then click **Dial-in Access Number**.</span></span>

4.  <span data-ttu-id="f0a0a-110">En la página **Número de acceso telefónico local**, haga clic en el número de acceso que desea ver.</span><span class="sxs-lookup"><span data-stu-id="f0a0a-110">On the **Dial-in Access Number** page, click the access number that you would like to view.</span></span>

5.  <span data-ttu-id="f0a0a-111">En **Editar**, seleccione **Mostrar detalles...**</span><span class="sxs-lookup"><span data-stu-id="f0a0a-111">In **Edit**, select the **Show Details…**</span></span> <span data-ttu-id="f0a0a-112">casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="f0a0a-112">check box.</span></span>

</div>

<div>

## <a name="viewing-dial-in-conferencing-access-numbers-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="f0a0a-113">Ver los números de acceso a la Conferencia de acceso telefónico local mediante cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f0a0a-113">Viewing Dial-in Conferencing Access Numbers by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="f0a0a-114">Los números de acceso de la Conferencia de acceso telefónico local se pueden ver con Windows PowerShell y el cmdlet Get-CsDialInConferencingAccessNumber.</span><span class="sxs-lookup"><span data-stu-id="f0a0a-114">Dial-in conferencing access numbers can be viewed by using Windows PowerShell and the Get-CsDialInConferencingAccessNumber cmdlet.</span></span> <span data-ttu-id="f0a0a-115">Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f0a0a-115">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="f0a0a-116">Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.</span><span class="sxs-lookup"><span data-stu-id="f0a0a-116">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-dial-in-conferencing-access-numbers"></a><span data-ttu-id="f0a0a-117">Para ver los números de acceso a la Conferencia de acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="f0a0a-117">To view dial-in conferencing access numbers</span></span>

  - <span data-ttu-id="f0a0a-118">Para ver la información sobre todos los números de acceso de la Conferencia de acceso telefónico local, escriba el siguiente comando en el shell de administración de Lync Server y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="f0a0a-118">To view information about all your dial-in conferencing access numbers, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsDialInConferencingAccessNumber
    
    <span data-ttu-id="f0a0a-119">Devolverá información similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="f0a0a-119">That will return information similar to this:</span></span>
    
        Identity           : CN={20ca8dc8-5ff8-41f4-b5bb-22ba9972ae2e},
                             CN=Application Contacts,CN=RTCService=Services,
                             CN=Configuration,DC=litwareinc,DC=com
        PrimaryUri         : sip:testnumber@litwareinc.com
        DisplayName        : Test
        DisplayNumber      : 1-425-555-1019
        LineUri            : tel:+14255551019
        PrimaryLanguage    : en-US
        SecondaryLanguages : {}
        Pool               : atl-cs-001.litwareinc.com
        HostingProvider    :
        Regions            : {US}

</div>

<span data-ttu-id="f0a0a-120">Para obtener más información, consulte el tema de ayuda para el cmdlet [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/Get-CsDialInConferencingAccessNumber) .</span><span class="sxs-lookup"><span data-stu-id="f0a0a-120">For more information, see the help topic for the [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/Get-CsDialInConferencingAccessNumber) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

