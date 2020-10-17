---
title: Probar y notificar la preparación funcional para la autenticación Kerberos
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test and report functional readiness for Kerberos authentication
ms:assetid: d52c39e5-747d-4f29-88aa-30fd6f26b99c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398925(v=OCS.15)
ms:contentKeyID: 48185519
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ac03f06a5d2c4b4989319f32a867d91614bd3a30
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519327"
---
# <a name="test-and-report-functional-readiness-for-kerberos-authentication-in-lync-server-2013"></a><span data-ttu-id="15597-102">Probar y notificar la preparación funcional para la autenticación Kerberos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="15597-102">Test and report functional readiness for Kerberos authentication in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="15597-103">_**Última modificación del tema:** 2012-01-16_</span><span class="sxs-lookup"><span data-stu-id="15597-103">_**Topic Last Modified:** 2012-01-16_</span></span>

<span data-ttu-id="15597-104">Para completar con éxito este procedimiento, debe iniciar sesión como usuario miembro del grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="15597-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="15597-105">Puede usar el cmdlet **Test-CsKerberosAccountAssignment**   de Windows PowerShell para probar y notificar la preparación funcional de una asignación de sitio para la autenticación Kerberos.</span><span class="sxs-lookup"><span data-stu-id="15597-105">You can use the **Test-CsKerberosAccountAssignment** Windows PowerShell cmdlet to test and report the functional readiness of a site assignment for Kerberos authentication.</span></span> <span data-ttu-id="15597-106">Este comando realiza una consulta al sitio especificado en el parámetro Identity requerido.</span><span class="sxs-lookup"><span data-stu-id="15597-106">This command queries the site specified in the required Identity parameter.</span></span> <span data-ttu-id="15597-107">El parámetro opcional Report hace que el cmdlet escriba un informe HTML en C: \\ logs en el equipo en el que se ejecuta el comando.</span><span class="sxs-lookup"><span data-stu-id="15597-107">The optional Report parameter causes the cmdlet to write an HTML report to C:\\Logs on the computer on which the command is run.</span></span> <span data-ttu-id="15597-108">El parámetro opcional Verbose notifica la información de actividad en la pantalla.</span><span class="sxs-lookup"><span data-stu-id="15597-108">The optional Verbose parameter reports activity information to the screen.</span></span>

<div>

## <a name="to-test-and-report-functional-readiness-for-kerberos-authentication-for-a-site"></a><span data-ttu-id="15597-109">Para probar la autenticación Kerberos de un sitio y notificar que está lista desde el punto de vista funcional</span><span class="sxs-lookup"><span data-stu-id="15597-109">To test and report functional readiness for Kerberos authentication for a site</span></span>

1.  <span data-ttu-id="15597-110">Como miembro del grupo RTCUniversalServerAdmins, inicie sesión en un equipo del dominio que ejecuta Lync Server 2013 o en el equipo donde están instaladas las herramientas administrativas.</span><span class="sxs-lookup"><span data-stu-id="15597-110">As a member of the RTCUniversalServerAdmins group, log on to a computer in the domain running Lync Server 2013 or on to the computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="15597-111">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="15597-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="15597-112">Desde la línea de comandos, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="15597-112">From the command line, run the following command:</span></span>
    
        Test-CsKerberosAccountAssignment -Identity "site:SiteName" -Report "c:\logs\FileName.htm" -Verbose
    
    <span data-ttu-id="15597-113">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="15597-113">For example:</span></span>
    
        Test-CsKerberosAccountAssignment -Identity "site:Redmond" -Report "c:\logs\KerberosReport.htm" -Verbose

</div>

</div>

<span> </span>

</div>

</div>

</div>

