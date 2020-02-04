---
title: 'Lync Server 2013: ver directivas de versión de cliente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View client version policies
ms:assetid: 6cd9a897-c694-4d6a-8259-2d3c01fce275
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898479(v=OCS.15)
ms:contentKeyID: 50873759
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 13f9fa62b16390c490a0ab555559a7895cdce93e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757484"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-client-version-policies-in-lync-server-2013"></a><span data-ttu-id="53093-102">Ver directivas de versión de cliente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="53093-102">View client version policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="53093-103">_**Última modificación del tema:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="53093-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="53093-104">Las directivas de versión de cliente se usan para aplicar un conjunto de reglas de control de versiones de cliente globalmente o a un sitio, grupo o grupo de usuarios en particular.</span><span class="sxs-lookup"><span data-stu-id="53093-104">Client version policies are used to apply a set of client versioning rules globally or to a particular site, pool, or group of users.</span></span> <span data-ttu-id="53093-105">Puede ver las directivas de versión de cliente que se han configurado en el entorno de Lync Server 2013 desde el panel de control de Lync Server 2013 o el shell de administración de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="53093-105">You can view the client version policies that have been configured in your Lync Server 2013 environment from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-view-client-version-policies-by-using-lync-server-control-panel"></a><span data-ttu-id="53093-106">Para ver las directivas de versión de cliente con el panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="53093-106">To view client version policies by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="53093-107">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="53093-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="53093-108">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="53093-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="53093-109">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="53093-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="53093-110">En la barra de navegación izquierda, haga clic en **clientes**y, a continuación, haga clic en el botón de navegación de la **Directiva de versión cliente** .</span><span class="sxs-lookup"><span data-stu-id="53093-110">In the left navigation bar, click **Clients**, and then click the **Client Version Policy** navigation button.</span></span>

4.  <span data-ttu-id="53093-111">Si desea ver las reglas de una directiva de versión de cliente, en la página **Directiva de versión del cliente** , haga doble clic en la Directiva que desea ver.</span><span class="sxs-lookup"><span data-stu-id="53093-111">If you want to view the rules for a client version policy, on the **Client Version Policy** page, double-click the policy you want to view.</span></span>

</div>

<div>

## <a name="viewing-client-version-policies-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="53093-112">Ver directivas de versión de cliente con cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="53093-112">Viewing Client Version Policies by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="53093-113">Puede ver las directivas de versión de cliente con el cmdlet **Get-CsClientVersionPolicy** .</span><span class="sxs-lookup"><span data-stu-id="53093-113">You can view client version policies by using the **Get-CsClientVersionPolicy** cmdlet.</span></span> <span data-ttu-id="53093-114">Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="53093-114">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="53093-115">Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.</span><span class="sxs-lookup"><span data-stu-id="53093-115">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-client-version-policies"></a><span data-ttu-id="53093-116">Para ver las directivas de versión de cliente</span><span class="sxs-lookup"><span data-stu-id="53093-116">To view client version policies</span></span>

  - <span data-ttu-id="53093-117">Para ver información sobre todas las directivas de versión de cliente, escriba el siguiente comando en el shell de administración de Lync Server y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="53093-117">To view information about all your client version policies, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsClientVersionPolicy
    
    <span data-ttu-id="53093-118">Devolverá información similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="53093-118">That will return information similar to this:</span></span>
    
        Identity    : Global
        Rules       : {RuleId=2336c611-a243-4c5d-994b-eea8a524d0e4;
                      Description=;Action=Block;ActionUrl=;MajorVersion=1;
                      MinorVersion=3;BuildNumber=;QfeNumber=;
                      UserAgent=RTC;UserAgentFullName=;Enabled=True;
                      CompareOp=LEQ, RuleId=342c9b90-4cef-483a-a73a-
                      4fe75c88711d;Description=;Action=Block;ActionUrl=;
                      MajorVersion=5;MinorVersion=;BuildNumber=;QfeNumber=;
                      UserAgent=WM;UserAgentFullName=;Enabled=True;
                      CompareOp=LEQ,RuleId=ea03af61-9db5-4bf9-af3f-042
                      ab8dd9994;Description=;Action=Block;ActionUrl=;
                      MajorVersion=3;MinorVersion=5;BuildNumber=6907;
                      QfeNumber=83;UserAgent=OC;UserAgentFullName=;
                      Enabled=True;CompareOp=LEQ, RuleId=831edb68-
                      e482-4431-a10e-add365ba8099;Description=;
                      Action=Block;ActionUrl=;MajorVersion=2;MinorVersion=0;
                      BuildNumber=5999;QfeNumber=;UserAgent=UCCP;
                      UserAgentFullName=;Enabled=True;CompareOp=LEQ...}
        Description :

</div>

<span data-ttu-id="53093-119">Para obtener más información, vea el tema de ayuda sobre el cmdlet [Get-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsClientVersionPolicy) .</span><span class="sxs-lookup"><span data-stu-id="53093-119">For details, see the Help topic for the [Get-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsClientVersionPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

