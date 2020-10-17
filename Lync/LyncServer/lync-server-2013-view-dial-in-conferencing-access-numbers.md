---
title: 'Lync Server 2013: ver los números de acceso de conferencia de acceso telefónico local'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View dial-in conferencing access numbers
ms:assetid: 41a7dfb4-0c89-4650-b61b-0e1bf875c62b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688037(v=OCS.15)
ms:contentKeyID: 49733628
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6794eee3015aca9a7f0d5281be5db10d87d833ab
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506447"
---
# <a name="view-dial-in-conferencing-access-numbers-in-lync-server-2013"></a><span data-ttu-id="16817-102">Ver los números de acceso de conferencia de acceso telefónico local en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="16817-102">View dial-in conferencing access numbers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="16817-103">_**Última modificación del tema:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="16817-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="16817-104">En el panel de control de Lync Server 2013, proporciona números de acceso telefónico a los usuarios para que puedan unirse a una reunión externamente.</span><span class="sxs-lookup"><span data-stu-id="16817-104">In Lync Server 2013 Control Panel, you provide dial-in access numbers to users so that they can join a meeting externally.</span></span>

<div>

## <a name="to-view-dial-in-access-numbers"></a><span data-ttu-id="16817-105">Para ver los números de acceso telefónico</span><span class="sxs-lookup"><span data-stu-id="16817-105">To view dial-in access numbers</span></span>

1.  <span data-ttu-id="16817-106">Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="16817-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="16817-107">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="16817-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="16817-108">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="16817-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="16817-109">En la barra de navegación de la izquierda, haga clic en **Conferencias** y, a continuación, en **Número de acceso telefónico**.</span><span class="sxs-lookup"><span data-stu-id="16817-109">In the left navigation bar, click **Conferencing** and then click **Dial-in Access Number**.</span></span>

4.  <span data-ttu-id="16817-110">En la página **Número de acceso telefónico**, haga clic en el número de acceso que desea ver.</span><span class="sxs-lookup"><span data-stu-id="16817-110">On the **Dial-in Access Number** page, click the access number that you would like to view.</span></span>

5.  <span data-ttu-id="16817-p102">En **Editar**, active la casilla **Mostrar detalles...**.</span><span class="sxs-lookup"><span data-stu-id="16817-p102">In **Edit**, select the **Show Details…** check box.</span></span>

</div>

<div>

## <a name="viewing-dial-in-conferencing-access-numbers-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="16817-113">Ver los números de acceso a conferencias de acceso telefónico local con los cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="16817-113">Viewing Dial-in Conferencing Access Numbers by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="16817-114">Los números de acceso de conferencia de acceso telefónico local se pueden ver con Windows PowerShell y el cmdlet Get-CsDialInConferencingAccessNumber.</span><span class="sxs-lookup"><span data-stu-id="16817-114">Dial-in conferencing access numbers can be viewed by using Windows PowerShell and the Get-CsDialInConferencingAccessNumber cmdlet.</span></span> <span data-ttu-id="16817-115">Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="16817-115">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="16817-116">Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server 2010 mediante PowerShell remoto" en [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="16817-116">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-dial-in-conferencing-access-numbers"></a><span data-ttu-id="16817-117">Para ver los números de acceso de conferencia de acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="16817-117">To view dial-in conferencing access numbers</span></span>

  - <span data-ttu-id="16817-118">Para ver información sobre todos los números de acceso de conferencias de acceso telefónico local, escriba el siguiente comando en el shell de administración de Lync Server y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="16817-118">To view information about all your dial-in conferencing access numbers, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsDialInConferencingAccessNumber
    
    <span data-ttu-id="16817-119">Devolverá información similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="16817-119">That will return information similar to this:</span></span>
    
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

<span data-ttu-id="16817-120">Para obtener más información, consulte el tema de ayuda para el cmdlet [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/Get-CsDialInConferencingAccessNumber) .</span><span class="sxs-lookup"><span data-stu-id="16817-120">For more information, see the help topic for the [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/Get-CsDialInConferencingAccessNumber) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

