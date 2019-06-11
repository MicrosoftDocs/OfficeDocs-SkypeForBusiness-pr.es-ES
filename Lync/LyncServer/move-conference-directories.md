---
title: Mover directorios de conferencia
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Move conference directories
ms:assetid: 71a28308-1f3b-4717-b535-2f4bfe3499a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204994(v=OCS.15)
ms:contentKeyID: 48184463
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ba7480e3454d338d9d6f2ff521c09e26b4f17c5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849944"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-conference-directories"></a><span data-ttu-id="22606-102">Mover directorios de conferencia</span><span class="sxs-lookup"><span data-stu-id="22606-102">Move conference directories</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="22606-103">_**Última modificación del tema:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="22606-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="22606-104">Antes de dar de baja un grupo, debe realizar el siguiente procedimiento para cada directorio de conferencia del grupo de Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="22606-104">Before decommissioning a pool, you need to perform the following procedure for each conference directory in your Office Communications Server 2007 R2 pool.</span></span>

<div>

## <a name="to-move-a-conference-directory-to-lync-server-2013"></a><span data-ttu-id="22606-105">Para mover un directorio de conferencia a Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="22606-105">To move a conference directory to Lync Server 2013</span></span>

1.  <span data-ttu-id="22606-106">Abra el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="22606-106">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="22606-107">Para obtener la identidad de los directorios de conferencia de su organización, ejecute los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="22606-107">To obtain the identity of the conference directories in your organization, run the following commands:</span></span>
    
        Get-CsConferenceDirectory
    
    <span data-ttu-id="22606-108">Dado que este cmdlet devuelve todos los directorios de conferencia de su organización, es posible que desee limitar los resultados solo a la agrupación que desea retirar.</span><span class="sxs-lookup"><span data-stu-id="22606-108">Because this cmdlet returns all the conference directories in your organization, you may want to limit the results to only the pool you want to decommission.</span></span> <span data-ttu-id="22606-109">Por ejemplo, si desea retirar un grupo con el nombre de dominio completo (FQDN) pool01.contoso.net:</span><span class="sxs-lookup"><span data-stu-id="22606-109">For example, if you want to decommission a pool with the fully qualified domain name (FQDN) pool01.contoso.net:</span></span>
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
    
    <span data-ttu-id="22606-110">Este cmdlet devuelve todos los directorios de conferencia en los que el identificador de servicio contiene el FQDN pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="22606-110">This cmdlet returns all the conference directories where service ID contains the FQDN pool01.contoso.net.</span></span>

3.  <span data-ttu-id="22606-111">Para mover los directorios de una conferencia, ejecute lo siguiente para cada directorio de conferencia del Grupo:</span><span class="sxs-lookup"><span data-stu-id="22606-111">To move conference directories, run the following for each conference directory in the pool:</span></span>
    
        Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
    
    <span data-ttu-id="22606-112">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="22606-112">For example:</span></span>
    
        Move-CsConferenceDirectory -Identity 3 -TargetPool pool02.contoso.net

<div>


> [!NOTE]  
> <span data-ttu-id="22606-113">Puede experimentar un error, que se muestra a continuación, provocado por el shell de administración de Lync Server que requiere un conjunto actualizado de permisos de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="22606-113">You may experience an error, shown below, that is caused by the Lync Server Management Shell requiring an updated set of permissions from Active Directory.</span></span> <span data-ttu-id="22606-114">Para resolver el error, cierre la ventana actual y abra un nuevo shell de administración de Lync Server y vuelva a ejecutar el comando.</span><span class="sxs-lookup"><span data-stu-id="22606-114">To resolve the error, closed the current window and open a new Lync Server Management Shell and run the command again.</span></span>



</div>

<span data-ttu-id="22606-115">![Salida de error de movimiento-CsConferenceDirectory] (images/JJ204994.4748b9e8-9651-4527-afe1-cbdc6d5ce4a8(OCS.15).jpg "Salida de error de movimiento-CsConferenceDirectory")</span><span class="sxs-lookup"><span data-stu-id="22606-115">![Move-CsConferenceDirectory error output](images/JJ204994.4748b9e8-9651-4527-afe1-cbdc6d5ce4a8(OCS.15).jpg "Move-CsConferenceDirectory error output")</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

