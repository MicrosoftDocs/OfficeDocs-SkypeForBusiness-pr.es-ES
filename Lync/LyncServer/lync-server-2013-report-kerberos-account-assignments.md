---
title: 'Lync Server 2013: Creación de informes de asignación de cuentas Kerberos'
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
ms.openlocfilehash: f4c5a6c118596acd406c3741c4dd2ee780fd381b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746700"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="report-kerberos-account-assignments-in-lync-server-2013"></a><span data-ttu-id="1e3d4-102">Creación de informes de asignación de cuentas Kerberos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e3d4-102">Report Kerberos account assignments in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1e3d4-103">_**Última modificación del tema:** 2012-01-16_</span><span class="sxs-lookup"><span data-stu-id="1e3d4-103">_**Topic Last Modified:** 2012-01-16_</span></span>

<span data-ttu-id="1e3d4-104">Para completar correctamente este procedimiento, debe haber iniciado sesión como un usuario que sea miembro del grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="1e3d4-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="1e3d4-105">Puede usar el cmdlet **Get-CsKerberosAccountAssignment** para consultar información acerca de las asignaciones de cuentas de autenticación Kerberos y notificar la información sobre las asignaciones actuales de su implementación.</span><span class="sxs-lookup"><span data-stu-id="1e3d4-105">You can use the **Get-CsKerberosAccountAssignment** cmdlet to query information about the Kerberos authentication account assignments and report information about the current assignments in your deployment.</span></span>

<div>

## <a name="to-query-kerberos-authentication-account-assignments-for-a-site"></a><span data-ttu-id="1e3d4-106">Para consultar asignaciones de cuentas de autenticación Kerberos para un sitio</span><span class="sxs-lookup"><span data-stu-id="1e3d4-106">To query Kerberos authentication account assignments for a site</span></span>

1.  <span data-ttu-id="1e3d4-107">Como miembro del grupo RTCUniversalServerAdmins, inicie sesión en un equipo del dominio que ejecute Lync Server 2013 o en un equipo en el que estén instaladas las herramientas administrativas.</span><span class="sxs-lookup"><span data-stu-id="1e3d4-107">As a member of the RTCUniversalServerAdmins group, log on to a computer in the domain running Lync Server 2013 or on to a computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="1e3d4-108">Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="1e3d4-108">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="1e3d4-109">En la línea de comandos, ejecute uno de los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="1e3d4-109">From the command line, run one of the following commands:</span></span>
    
      - <span data-ttu-id="1e3d4-110">Para consultar todas las asignaciones de cuentas de autenticación Kerberos de su organización y devolver información de asignación sobre cada una de ellas, ejecute el cmdlet sin ningún parámetro:</span><span class="sxs-lookup"><span data-stu-id="1e3d4-110">To query all Kerberos authentication account assignments in your organization and return assignment information about each of them, run the cmdlet without any parameters:</span></span>
        
            Get-CsKerberosAccountAssignment
    
      - <span data-ttu-id="1e3d4-111">Para consultar todas las asignaciones de cuentas de autenticación Kerberos de su implementación y devolver información de asignación de sitio sobre cada una de ellas, ejecute el cmdlet con el parámetro Identity:</span><span class="sxs-lookup"><span data-stu-id="1e3d4-111">To query all Kerberos authentication account assignments in your deployment and return site assignment information about each of them, run the cmdlet with the Identity parameter:</span></span>
        
            Get-CsKerberosAccountAssignment -Identity "site:SiteName"
        
        <span data-ttu-id="1e3d4-112">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="1e3d4-112">For example:</span></span>
        
            Get-CsKerberosAccountAssignment -Identity "site:Redmond"
    
      - <span data-ttu-id="1e3d4-113">Para consultar todas las asignaciones de cuentas de autenticación Kerberos en un solo sitio y devolver información sobre cada una de ellas, ejecute el cmdlet con el parámetro Filter:</span><span class="sxs-lookup"><span data-stu-id="1e3d4-113">To query all Kerberos authentication account assignments in a single site and return assignment information about each of them, run the cmdlet with the Filter parameter:</span></span>
        
            Get-CsKerberosAccountAssignment -Filter "SiteName"
        
        <span data-ttu-id="1e3d4-114">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="1e3d4-114">For example:</span></span>
        
            Get-CsKerberosAccountAssignment -Filter "*Redmond"
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="1e3d4-115">Si se especifica \* SiteName para el parámetro de filtro, se devuelve información acerca de todos los sitios que contienen el nombre de sitio especificado en el identificador de sitio (por ejemplo, todos los sitios que contienen la cadena Redmond en el identificador de sitio).</span><span class="sxs-lookup"><span data-stu-id="1e3d4-115">Specifying \*SiteName for the Filter parameter returns information about all sites that contain the specified site name anywhere in the site identifier (for example, all sites that contain the string Redmond in the site identifier).</span></span>

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

