---
title: Mover directorios de conferencia
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Move conference directories
ms:assetid: 71a28308-1f3b-4717-b535-2f4bfe3499a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204994(v=OCS.15)
ms:contentKeyID: 48184463
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 705540ba138a6b62c41480e275f183d67dbfbfc4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42209727"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-conference-directories"></a><span data-ttu-id="52a57-102">Mover directorios de conferencia</span><span class="sxs-lookup"><span data-stu-id="52a57-102">Move conference directories</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="52a57-103">_**Última modificación del tema:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="52a57-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="52a57-104">Antes de retirar un grupo de servidores, debe realizar el siguiente procedimiento para cada directorio de conferencia del grupo de servidores de Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="52a57-104">Before decommissioning a pool, you need to perform the following procedure for each conference directory in your Office Communications Server 2007 R2 pool.</span></span>

<div>

## <a name="to-move-a-conference-directory-to-lync-server-2013"></a><span data-ttu-id="52a57-105">Para mover un directorio de conferencia a Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52a57-105">To move a conference directory to Lync Server 2013</span></span>

1.  <span data-ttu-id="52a57-106">Abra el Shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="52a57-106">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="52a57-107">Para obtener la identidad de los directorios de conferencia de su organización, ejecute los comandos siguientes:</span><span class="sxs-lookup"><span data-stu-id="52a57-107">To obtain the identity of the conference directories in your organization, run the following commands:</span></span>
    
        Get-CsConferenceDirectory
    
    <span data-ttu-id="52a57-p101">Debido a que este cmdlet devuelve todos los directorios de conferencia de su organización, es posible que desee limitar los resultados solo a los grupos que desea retirar. Por ejemplo, si desea retirar un grupo con el nombre de dominio completo (FQDN) pool01.contoso.net:</span><span class="sxs-lookup"><span data-stu-id="52a57-p101">Because this cmdlet returns all the conference directories in your organization, you may want to limit the results to only the pool you want to decommission. For example, if you want to decommission a pool with the fully qualified domain name (FQDN) pool01.contoso.net:</span></span>
    
        Get-CsConferenceDirectory | Where-Object {$_.ServiceID -match "pool01.contoso.net"}
    
    <span data-ttu-id="52a57-110">Este cmdlet devuelve todos los directorios de conferencia en los que el Id. de servicio contiene el FQDN pool01.contoso.net.</span><span class="sxs-lookup"><span data-stu-id="52a57-110">This cmdlet returns all the conference directories where service ID contains the FQDN pool01.contoso.net.</span></span>

3.  <span data-ttu-id="52a57-111">Para mover directorios de conferencia, ejecute lo siguiente para cada directorio de conferencia del grupo:</span><span class="sxs-lookup"><span data-stu-id="52a57-111">To move conference directories, run the following for each conference directory in the pool:</span></span>
    
        Move-CsConferenceDirectory -Identity <Numeric identity of conference directory> -TargetPool <FQDN of pool where ownership is to be transitioned>
    
    <span data-ttu-id="52a57-112">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="52a57-112">For example:</span></span>
    
        Move-CsConferenceDirectory -Identity 3 -TargetPool pool02.contoso.net

<div>


> [!NOTE]  
> <span data-ttu-id="52a57-113">Puede experimentar un error, que se muestra a continuación, debido a que el shell de administración de Lync Server requiere un conjunto actualizado de permisos de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="52a57-113">You may experience an error, shown below, that is caused by the Lync Server Management Shell requiring an updated set of permissions from Active Directory.</span></span> <span data-ttu-id="52a57-114">Para solucionar el error, cierre la ventana actual y abra un nuevo shell de administración de Lync Server y ejecute el comando de nuevo.</span><span class="sxs-lookup"><span data-stu-id="52a57-114">To resolve the error, closed the current window and open a new Lync Server Management Shell and run the command again.</span></span>



</div>

<span data-ttu-id="52a57-115">![Salida de error de Move-CsConferenceDirectory](images/JJ204994.4748b9e8-9651-4527-afe1-cbdc6d5ce4a8(OCS.15).jpg "Salida de error de Move-CsConferenceDirectory")</span><span class="sxs-lookup"><span data-stu-id="52a57-115">![Move-CsConferenceDirectory error output](images/JJ204994.4748b9e8-9651-4527-afe1-cbdc6d5ce4a8(OCS.15).jpg "Move-CsConferenceDirectory error output")</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

