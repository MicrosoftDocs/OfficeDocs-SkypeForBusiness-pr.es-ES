---
title: 'Lync Server 2013: informes de asignación de cuentas Kerberos'
description: 'Lync Server 2013: Informe sobre las asignaciones de cuenta Kerberos.'
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
ms.openlocfilehash: 23e40dddfc4538db70e2101b1bfcbbce2fe3fa8b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576126"
---
# <a name="report-kerberos-account-assignments-in-lync-server-2013"></a><span data-ttu-id="00ce6-103">Informar sobre las asignaciones de cuentas Kerberos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="00ce6-103">Report Kerberos account assignments in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="00ce6-104">_**Última modificación del tema:** 2012-01-16_</span><span class="sxs-lookup"><span data-stu-id="00ce6-104">_**Topic Last Modified:** 2012-01-16_</span></span>

<span data-ttu-id="00ce6-105">Para completar con éxito este procedimiento, debe iniciar sesión como usuario miembro del grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="00ce6-105">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="00ce6-106">Puede usar el cmdlet **Get-CsKerberosAccountAssignment** para consultar información sobre las asignaciones de cuenta de autenticación Kerberos e información de informe sobre las asignaciones actuales de su implementación.</span><span class="sxs-lookup"><span data-stu-id="00ce6-106">You can use the **Get-CsKerberosAccountAssignment** cmdlet to query information about the Kerberos authentication account assignments and report information about the current assignments in your deployment.</span></span>

<div>

## <a name="to-query-kerberos-authentication-account-assignments-for-a-site"></a><span data-ttu-id="00ce6-107">Para consultar las asignaciones de cuenta de autenticación Kerberos de un sitio</span><span class="sxs-lookup"><span data-stu-id="00ce6-107">To query Kerberos authentication account assignments for a site</span></span>

1.  <span data-ttu-id="00ce6-108">Como miembro del grupo RTCUniversalServerAdmins, inicie sesión en un equipo del dominio que ejecute Lync Server 2013 o en un equipo en el que estén instaladas las herramientas administrativas.</span><span class="sxs-lookup"><span data-stu-id="00ce6-108">As a member of the RTCUniversalServerAdmins group, log on to a computer in the domain running Lync Server 2013 or on to a computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="00ce6-109">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="00ce6-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="00ce6-110">En la línea de comandos, ejecute uno de los comandos que se indican a continuación:</span><span class="sxs-lookup"><span data-stu-id="00ce6-110">From the command line, run one of the following commands:</span></span>
    
      - <span data-ttu-id="00ce6-111">Para consultar todas las asignaciones de cuenta de autenticación Kerberos de su organización y devolver información de asignación sobre cada una de ellas, ejecute el cmdlet sin ningún parámetro:</span><span class="sxs-lookup"><span data-stu-id="00ce6-111">To query all Kerberos authentication account assignments in your organization and return assignment information about each of them, run the cmdlet without any parameters:</span></span>
        
            Get-CsKerberosAccountAssignment
    
      - <span data-ttu-id="00ce6-112">Para consultar todas las asignaciones de cuenta de autenticación Kerberos de su implementación y devolver información de asignación del sitio sobre cada una de ellas, ejecute el cmdlet con el parámetro Identity:</span><span class="sxs-lookup"><span data-stu-id="00ce6-112">To query all Kerberos authentication account assignments in your deployment and return site assignment information about each of them, run the cmdlet with the Identity parameter:</span></span>
        
            Get-CsKerberosAccountAssignment -Identity "site:SiteName"
        
        <span data-ttu-id="00ce6-113">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="00ce6-113">For example:</span></span>
        
            Get-CsKerberosAccountAssignment -Identity "site:Redmond"
    
      - <span data-ttu-id="00ce6-114">Para consultar todas las asignaciones de cuenta de autenticación Kerberos de un único sitio y devolver información de asignación sobre cada una de ellas, ejecute el cmdlet con el parámetro Filter:</span><span class="sxs-lookup"><span data-stu-id="00ce6-114">To query all Kerberos authentication account assignments in a single site and return assignment information about each of them, run the cmdlet with the Filter parameter:</span></span>
        
            Get-CsKerberosAccountAssignment -Filter "SiteName"
        
        <span data-ttu-id="00ce6-115">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="00ce6-115">For example:</span></span>
        
            Get-CsKerberosAccountAssignment -Filter "*Redmond"
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="00ce6-116">La especificación de \*nombre_sitio para el parámetro Filter devuelve información acerca de todos los sitios que contienen el nombre de sitio especificado en cualquier lugar del identificador del sitio (por ejemplo, todos los sitios que contengan la cadena Redmond en el identificador del sitio).</span><span class="sxs-lookup"><span data-stu-id="00ce6-116">Specifying \*SiteName for the Filter parameter returns information about all sites that contain the specified site name anywhere in the site identifier (for example, all sites that contain the string Redmond in the site identifier).</span></span>

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

