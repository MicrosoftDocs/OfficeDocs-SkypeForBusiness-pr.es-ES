---
title: Mover directorios de conferencia de Lync Server 2010 a Lync Server 2013
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
ms.openlocfilehash: e9bd597665f389c814fbdc8fe1745587fd3d1b3e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41766121"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-conference-directories"></a><span data-ttu-id="06c87-102">Mover directorios de conferencia</span><span class="sxs-lookup"><span data-stu-id="06c87-102">Move Conference Directories</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="06c87-103">_**Última modificación del tema:** 2014-05-28_</span><span class="sxs-lookup"><span data-stu-id="06c87-103">_**Topic Last Modified:** 2014-05-28_</span></span>

<span data-ttu-id="06c87-104">Antes de dar de baja un grupo, debe realizar el siguiente procedimiento para cada directorio de conferencia de su grupo de 2010 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="06c87-104">Before decommissioning a pool you must perform the following procedure for each conference directory in your Lync Server 2010 pool.</span></span>

<div>

## <a name="to-move-a-conference-directory-to-lync-server-2013"></a><span data-ttu-id="06c87-105">Para mover un directorio de conferencia a Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="06c87-105">To Move a Conference Directory to Lync Server 2013</span></span>

1.  <span data-ttu-id="06c87-106">Abra el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="06c87-106">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="06c87-107">Para obtener la identidad de los directorios de conferencia de su organización, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="06c87-107">To obtain the identity of the conference directories in your organization, run the following command:</span></span>
    
        Get-CsConferenceDirectory
    
    <span data-ttu-id="06c87-108">El comando anterior devuelve todos los directorios de conferencia de su organización.</span><span class="sxs-lookup"><span data-stu-id="06c87-108">The preceding command returns all the conference directories in your organization.</span></span> <span data-ttu-id="06c87-109">Por eso, es posible que desee limitar los resultados al grupo que se va a retirar.</span><span class="sxs-lookup"><span data-stu-id="06c87-109">Because of that, you might want to limit the results to the pool being decommissioned.</span></span> <span data-ttu-id="06c87-110">Por ejemplo, si va a retirar el grupo con el nombre de dominio completo (FQDN) pool01.contoso.net, use este comando para limitar los datos devueltos a los directorios de conferencia de ese grupo:</span><span class="sxs-lookup"><span data-stu-id="06c87-110">For example, if you are decommissioning the pool with the fully qualified domain name (FQDN) pool01.contoso.net, use this command to limit the returned data to conference directories from that pool:</span></span>
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
    
    <span data-ttu-id="06c87-111">Ese comando devuelve solo los directorios de la Conferencia en los que la propiedad ServiceID contiene el FQDN pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="06c87-111">That command returns only the conference directories where the ServiceID property contains the FQDN pool01.contoso.net.</span></span>

3.  <span data-ttu-id="06c87-112">Para mover los directorios de la Conferencia, ejecute el comando siguiente para cada directorio de conferencia del Grupo:</span><span class="sxs-lookup"><span data-stu-id="06c87-112">To move conference directories, run the following command for each conference directory in the pool:</span></span>
    
        Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
    
    <span data-ttu-id="06c87-113">Por ejemplo, para mover el directorio de la Conferencia 3, use este comando, especificando un grupo de servidores de Lync Server 2013 como TargetPool:</span><span class="sxs-lookup"><span data-stu-id="06c87-113">For example, to move conference directory 3 use this command, specifying a Lync Server 2013 pool as the TargetPool:</span></span>
    
        Move-CsConferenceDirectory -Identity 3 -TargetPool "pool02.contoso.net"
    
    <span data-ttu-id="06c87-114">Si desea mover todos los directorios de conferencia de un grupo, use un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="06c87-114">If you want to move all the conference directories on a pool then use a command similar to the following:</span></span>
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"} | Move-CsConferenceDirectory -TargetPool "pool02.contoso.net"

<span data-ttu-id="06c87-115">Consulte el documento "desinstalar Microsoft Lync Server 2010 y quitar roles de servidor" (del [http://go.microsoft.com/fwlink/p/?linkId=246227](http://go.microsoft.com/fwlink/p/?linkid=246227)que se puede descargar) para obtener instrucciones completas paso a paso sobre la retirada de grupos de servidores de Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="06c87-115">Please see the document "Uninstalling Microsoft Lync Server 2010 and Removing Server Roles" (which can be downloaded from [http://go.microsoft.com/fwlink/p/?linkId=246227](http://go.microsoft.com/fwlink/p/?linkid=246227)) for comprehensive, step-by-step instructions on decommissioning Lync 2010 pools.</span></span>

<span data-ttu-id="06c87-116">Al mover los directorios de la Conferencia, es posible que se produzca el siguiente error:</span><span class="sxs-lookup"><span data-stu-id="06c87-116">When moving conference directories you might encounter the following error:</span></span>

    WARNING: Move operation failed for conference directory with ID "5". Cannot perform a rollback because data migration might have already started. Retry the operation.
    WARNING: Before using the -Force parameter, ensure that you have exported the conference directory data using DBImpExp.exe and imported the data on the target pool. Refer to the DBImpExp-Readme.htm file for more information.
    Move-CsConferenceDirectory : Unable to cast COM object of type 'System._ComObject' to interface type 'Microsoft.Rtc.Interop.User.IRtcConfDirManagement'. 
    This operation failed because the QueryInterface call on the COM component for the interface with SID '{4262B886-503F-4BEA-868C-04E8DF562CEB}' failed due to the following error: The specified module could not be found.

<span data-ttu-id="06c87-117">Este error suele ocurrir cuando el shell de administración de Lync Server requiere un conjunto actualizado de permisos de Active Directory para poder completar una tarea.</span><span class="sxs-lookup"><span data-stu-id="06c87-117">This error typically occurs when the Lync Server Management Shell requires an updated set of Active Directory permissions in order to complete a task.</span></span> <span data-ttu-id="06c87-118">Para resolver el problema, cierre la instancia actual del shell de administración, abra una nueva instancia de la Shell y vuelva a ejecutar el comando para mover el directorio de la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="06c87-118">To resolve the problem, close the current instance of the Management Shell, then open a new instance of the shell and re-run the command in order to move the conference directory.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

