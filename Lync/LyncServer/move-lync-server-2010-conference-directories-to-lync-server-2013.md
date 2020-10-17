---
title: Mover los directorios de conferencia de Lync Server 2010 a Lync Server 2013
description: Mueva los directorios de conferencia de Lync Server 2010 a Lync Server 2013.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move Conference Directories
ms:assetid: 659867e0-ce91-4a95-9787-b1c1566460a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727126(v=OCS.15)
ms:contentKeyID: 62387565
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 12ac58ac0ab6f1908e7eac3e5824bf2304256632
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571366"
---
# <a name="move-conference-directories"></a><span data-ttu-id="db482-103">Mover directorios de conferencia</span><span class="sxs-lookup"><span data-stu-id="db482-103">Move Conference Directories</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="db482-104">_**Última modificación del tema:** 2014-05-28_</span><span class="sxs-lookup"><span data-stu-id="db482-104">_**Topic Last Modified:** 2014-05-28_</span></span>

<span data-ttu-id="db482-105">Antes de retirar un grupo de servidores, debe realizar el siguiente procedimiento para cada directorio de conferencia del grupo de servidores de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="db482-105">Before decommissioning a pool you must perform the following procedure for each conference directory in your Lync Server 2010 pool.</span></span>

<div>

## <a name="to-move-a-conference-directory-to-lync-server-2013"></a><span data-ttu-id="db482-106">Para mover un directorio de conferencia a Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="db482-106">To Move a Conference Directory to Lync Server 2013</span></span>

1.  <span data-ttu-id="db482-107">Abra el Shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="db482-107">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="db482-108">Para obtener la identidad de los directorios de conferencia de su organización, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="db482-108">To obtain the identity of the conference directories in your organization, run the following command:</span></span>
    
        Get-CsConferenceDirectory
    
    <span data-ttu-id="db482-109">El comando anterior devuelve todos los directorios de conferencia de la organización.</span><span class="sxs-lookup"><span data-stu-id="db482-109">The preceding command returns all the conference directories in your organization.</span></span> <span data-ttu-id="db482-110">Por ello, es posible que desee limitar los resultados al grupo de servidores que se está retirando.</span><span class="sxs-lookup"><span data-stu-id="db482-110">Because of that, you might want to limit the results to the pool being decommissioned.</span></span> <span data-ttu-id="db482-111">Por ejemplo, si va a retirar el grupo de servidores con el nombre de dominio completo (FQDN) pool01.contoso.net, use este comando para limitar los datos devueltos a los directorios de conferencia de ese grupo:</span><span class="sxs-lookup"><span data-stu-id="db482-111">For example, if you are decommissioning the pool with the fully qualified domain name (FQDN) pool01.contoso.net, use this command to limit the returned data to conference directories from that pool:</span></span>
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
    
    <span data-ttu-id="db482-112">Este comando devuelve sólo los directorios de conferencia en los que la propiedad ServiceID contiene el FQDN pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="db482-112">That command returns only the conference directories where the ServiceID property contains the FQDN pool01.contoso.net.</span></span>

3.  <span data-ttu-id="db482-113">Para mover los directorios de conferencia, ejecute el siguiente comando para cada directorio de conferencia del Grupo:</span><span class="sxs-lookup"><span data-stu-id="db482-113">To move conference directories, run the following command for each conference directory in the pool:</span></span>
    
        Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
    
    <span data-ttu-id="db482-114">Por ejemplo, para mover el directorio de conferencia 3 Use este comando, especificando un grupo de servidores de Lync Server 2013 como TargetPool:</span><span class="sxs-lookup"><span data-stu-id="db482-114">For example, to move conference directory 3 use this command, specifying a Lync Server 2013 pool as the TargetPool:</span></span>
    
        Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
    
    <span data-ttu-id="db482-115">Si desea mover todos los directorios de conferencia de un grupo de servidores, use un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="db482-115">If you want to move all the conference directories on a pool then use a command similar to the following:</span></span>
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"

<span data-ttu-id="db482-116">Consulte el documento "desinstalar Microsoft Lync Server 2010 y quitar roles de servidor" (del que se puede descargar [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkid=246227) ) para obtener instrucciones detalladas paso a paso sobre cómo retirar los grupos de Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="db482-116">Please see the document "Uninstalling Microsoft Lync Server 2010 and Removing Server Roles" (which can be downloaded from [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkid=246227)) for comprehensive, step-by-step instructions on decommissioning Lync 2010 pools.</span></span>

<span data-ttu-id="db482-117">Al mover los directorios de conferencia, es posible que se produzca el siguiente error:</span><span class="sxs-lookup"><span data-stu-id="db482-117">When moving conference directories you might encounter the following error:</span></span>

    WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
    WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
    Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
    This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.

<span data-ttu-id="db482-118">Este error suele producirse cuando el shell de administración de Lync Server requiere un conjunto actualizado de permisos de Active Directory para poder completar una tarea.</span><span class="sxs-lookup"><span data-stu-id="db482-118">This error typically occurs when the Lync Server Management Shell requires an updated set of Active Directory permissions in order to complete a task.</span></span> <span data-ttu-id="db482-119">Para solucionar el problema, cierre la instancia actual del shell de administración, abra una nueva instancia del shell y vuelva a ejecutar el comando para mover el directorio de conferencia.</span><span class="sxs-lookup"><span data-stu-id="db482-119">To resolve the problem, close the current instance of the Management Shell, then open a new instance of the shell and re-run the command in order to move the conference directory.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

