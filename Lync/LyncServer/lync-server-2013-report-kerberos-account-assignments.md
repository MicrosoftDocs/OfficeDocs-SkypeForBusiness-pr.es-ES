---
title: 'Lync Server 2013: informes de asignación de cuentas Kerberos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Report Kerberos account assignments
ms:assetid: 523231f6-81b3-454b-996d-663d9bd5cf83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398343(v=OCS.15)
ms:contentKeyID: 48184151
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9576d772aa340e7d578186974fb00418479ea691
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138761"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="report-kerberos-account-assignments-in-lync-server-2013"></a><span data-ttu-id="9c7e2-102">Informar sobre las asignaciones de cuentas Kerberos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9c7e2-102">Report Kerberos account assignments in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9c7e2-103">_**Última modificación del tema:** 2012-01-16_</span><span class="sxs-lookup"><span data-stu-id="9c7e2-103">_**Topic Last Modified:** 2012-01-16_</span></span>

<span data-ttu-id="9c7e2-104">Para completar con éxito este procedimiento, debe iniciar sesión como usuario miembro del grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="9c7e2-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="9c7e2-105">Puede usar el cmdlet **Get-CsKerberosAccountAssignment** para consultar información sobre las asignaciones de cuenta de autenticación Kerberos e información de informe sobre las asignaciones actuales de su implementación.</span><span class="sxs-lookup"><span data-stu-id="9c7e2-105">You can use the **Get-CsKerberosAccountAssignment** cmdlet to query information about the Kerberos authentication account assignments and report information about the current assignments in your deployment.</span></span>

<div>

## <a name="to-query-kerberos-authentication-account-assignments-for-a-site"></a><span data-ttu-id="9c7e2-106">Para consultar las asignaciones de cuenta de autenticación Kerberos de un sitio</span><span class="sxs-lookup"><span data-stu-id="9c7e2-106">To query Kerberos authentication account assignments for a site</span></span>

1.  <span data-ttu-id="9c7e2-107">Como miembro del grupo RTCUniversalServerAdmins, inicie sesión en un equipo del dominio que ejecute Lync Server 2013 o en un equipo en el que estén instaladas las herramientas administrativas.</span><span class="sxs-lookup"><span data-stu-id="9c7e2-107">As a member of the RTCUniversalServerAdmins group, log on to a computer in the domain running Lync Server 2013 or on to a computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="9c7e2-108">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="9c7e2-108">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="9c7e2-109">En la línea de comandos, ejecute uno de los comandos que se indican a continuación:</span><span class="sxs-lookup"><span data-stu-id="9c7e2-109">From the command line, run one of the following commands:</span></span>
    
      - <span data-ttu-id="9c7e2-110">Para consultar todas las asignaciones de cuenta de autenticación Kerberos de su organización y devolver información de asignación sobre cada una de ellas, ejecute el cmdlet sin ningún parámetro:</span><span class="sxs-lookup"><span data-stu-id="9c7e2-110">To query all Kerberos authentication account assignments in your organization and return assignment information about each of them, run the cmdlet without any parameters:</span></span>
        
            Get-CsKerberosAccountAssignment
    
      - <span data-ttu-id="9c7e2-111">Para consultar todas las asignaciones de cuenta de autenticación Kerberos de su implementación y devolver información de asignación del sitio sobre cada una de ellas, ejecute el cmdlet con el parámetro Identity:</span><span class="sxs-lookup"><span data-stu-id="9c7e2-111">To query all Kerberos authentication account assignments in your deployment and return site assignment information about each of them, run the cmdlet with the Identity parameter:</span></span>
        
            Get-CsKerberosAccountAssignment -Identity "site:SiteName"
        
        <span data-ttu-id="9c7e2-112">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="9c7e2-112">For example:</span></span>
        
            Get-CsKerberosAccountAssignment -Identity "site:Redmond"
    
      - <span data-ttu-id="9c7e2-113">Para consultar todas las asignaciones de cuenta de autenticación Kerberos de un único sitio y devolver información de asignación sobre cada una de ellas, ejecute el cmdlet con el parámetro Filter:</span><span class="sxs-lookup"><span data-stu-id="9c7e2-113">To query all Kerberos authentication account assignments in a single site and return assignment information about each of them, run the cmdlet with the Filter parameter:</span></span>
        
            Get-CsKerberosAccountAssignment -Filter "SiteName"
        
        <span data-ttu-id="9c7e2-114">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="9c7e2-114">For example:</span></span>
        
            Get-CsKerberosAccountAssignment -Filter "*Redmond"
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="9c7e2-115">La especificación de \*nombre_sitio para el parámetro Filter devuelve información acerca de todos los sitios que contienen el nombre de sitio especificado en cualquier lugar del identificador del sitio (por ejemplo, todos los sitios que contengan la cadena Redmond en el identificador del sitio).</span><span class="sxs-lookup"><span data-stu-id="9c7e2-115">Specifying \*SiteName for the Filter parameter returns information about all sites that contain the specified site name anywhere in the site identifier (for example, all sites that contain the string Redmond in the site identifier).</span></span>

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

