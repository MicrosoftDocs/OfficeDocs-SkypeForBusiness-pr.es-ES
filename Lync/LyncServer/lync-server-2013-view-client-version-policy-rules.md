---
title: 'Lync Server 2013: ver reglas de directiva de versión de cliente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View client version policy rules
ms:assetid: f3a0215f-f72f-4e9b-a07b-25858dc4203a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ923060(v=OCS.15)
ms:contentKeyID: 50675350
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b64dce1b74be8ed1aed0c5d1f515910341f57c52
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757474"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-client-version-policy-rules-in-lync-server-2013"></a><span data-ttu-id="97bc4-102">Ver reglas de directiva de versión de cliente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97bc4-102">View client version policy rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="97bc4-103">_**Última modificación del tema:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="97bc4-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="97bc4-104">Una directiva de versión de cliente está formada por un conjunto de reglas de directiva de versión de cliente.</span><span class="sxs-lookup"><span data-stu-id="97bc4-104">A client version policy is made up of a set of client version policy rules.</span></span> <span data-ttu-id="97bc4-105">Estas reglas definen las acciones que se necesitan realizar cuando los usuarios intentan iniciar sesión con clientes y versiones de clientes específicos.</span><span class="sxs-lookup"><span data-stu-id="97bc4-105">These rules define the actions that should be taken when users attempt to log on with specific clients and client versions.</span></span> <span data-ttu-id="97bc4-106">Puede ver reglas de directiva de versión de cliente desde el panel de control de Lync Server 2013 o del shell de administración de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="97bc4-106">You can view client version policy rules from Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-view-client-version-policy-rules-by-using-lync-server-control-panel"></a><span data-ttu-id="97bc4-107">Para ver las reglas de directiva de versión de cliente con el panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="97bc4-107">To view client version policy rules by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="97bc4-108">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="97bc4-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="97bc4-109">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="97bc4-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="97bc4-110">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="97bc4-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="97bc4-111">En la barra de navegación izquierda, haga clic en **clientes**y, a continuación, haga clic en el botón de navegación de la **Directiva de versión cliente** .</span><span class="sxs-lookup"><span data-stu-id="97bc4-111">In the left navigation bar, click **Clients**, and then click the **Client Version Policy** navigation button.</span></span>

4.  <span data-ttu-id="97bc4-112">En la página de la **Directiva de versión del cliente** , haga doble clic en una directiva de versión de cliente que quiera ver.</span><span class="sxs-lookup"><span data-stu-id="97bc4-112">On the **Client Version Policy** page, double-click a client version policy you want to view.</span></span>

5.  <span data-ttu-id="97bc4-113">Las reglas aparecen en la página **Editar Directiva de versión del cliente** .</span><span class="sxs-lookup"><span data-stu-id="97bc4-113">The rules appear on the **Edit Client Version Policy** page.</span></span> <span data-ttu-id="97bc4-114">Para ver los detalles de una regla, seleccione la regla y, a continuación, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="97bc4-114">To view the details for a rule, select the rule, and then click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-client-version-policy-rules-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="97bc4-115">Visualización de reglas de directiva de versión de cliente con cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="97bc4-115">Viewing Client Version Policy Rules by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="97bc4-116">Puede ver las reglas de directiva de versión de cliente mediante el shell de administración de Lync Server y el cmdlet **Get-CsClientVersionPolicyRule** .</span><span class="sxs-lookup"><span data-stu-id="97bc4-116">You can view client version policy rules by using Lync Server Management Shell and the **Get-CsClientVersionPolicyRule** cmdlet.</span></span> <span data-ttu-id="97bc4-117">Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="97bc4-117">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="97bc4-118">Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.</span><span class="sxs-lookup"><span data-stu-id="97bc4-118">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-client-version-policy-rules"></a><span data-ttu-id="97bc4-119">Para ver las reglas de directiva de versión de cliente</span><span class="sxs-lookup"><span data-stu-id="97bc4-119">To view client version policy rules</span></span>

  - <span data-ttu-id="97bc4-120">Para ver las reglas de directiva de versión de cliente, escriba el siguiente comando en el shell de administración de Lync Server y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="97bc4-120">To view the client version policy rules, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsClientVersionPolicyRule
    
    <span data-ttu-id="97bc4-121">Que devolverá información similar a esta para cada regla configurada:</span><span class="sxs-lookup"><span data-stu-id="97bc4-121">That will return information similar to this for each configured rule:</span></span>
    
        Identity          : Global/2336c611-a243-4c5d-994b-eea8a524d0e4
        Priority          : 0
        RuleId            : 2336c611-a243-4c5d-994b-eea8a524d0e4
        Description       :
        Action            : Block
        ActionUrl         :
        MajorVersion      : 1
        MinorVersion      : 3
        BuildNumber       :
        QfeNumber         :
        UserAgent         : RTC
        UserAgentFullName :
        Enabled           : True
        CompareOp         : LEQ

</div>

<span data-ttu-id="97bc4-122">Para obtener más información, vea el tema de ayuda sobre el cmdlet [Get-CsClientVersionPolicyRule](https://docs.microsoft.com/powershell/module/skype/Get-CsClientVersionPolicyRule) .</span><span class="sxs-lookup"><span data-stu-id="97bc4-122">For details, see the help topic for the [Get-CsClientVersionPolicyRule](https://docs.microsoft.com/powershell/module/skype/Get-CsClientVersionPolicyRule) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

