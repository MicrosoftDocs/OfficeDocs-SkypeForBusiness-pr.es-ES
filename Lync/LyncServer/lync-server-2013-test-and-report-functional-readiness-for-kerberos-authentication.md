---
title: Comprobar y crear informes de disponibilidad funcional para la autenticación Kerberos
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
ms.openlocfilehash: 8763203827afd3d14638b68474c4f9bd9d6d0cfc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746512"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-and-report-functional-readiness-for-kerberos-authentication-in-lync-server-2013"></a><span data-ttu-id="926d0-102">Comprobar y crear informes de disponibilidad funcional para la autenticación Kerberos en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="926d0-102">Test and report functional readiness for Kerberos authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="926d0-103">_**Última modificación del tema:** 2012-01-16_</span><span class="sxs-lookup"><span data-stu-id="926d0-103">_**Topic Last Modified:** 2012-01-16_</span></span>

<span data-ttu-id="926d0-104">Para completar correctamente este procedimiento, debe haber iniciado sesión como un usuario que sea miembro del grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="926d0-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="926d0-105">Puede usar el cmdlet **Test-CsKerberosAccountAssignment** de Windows PowerShell para probar y notificar la preparación funcional de una asignación de sitio para la autenticación Kerberos.</span><span class="sxs-lookup"><span data-stu-id="926d0-105">You can use the **Test-CsKerberosAccountAssignment** Windows PowerShell cmdlet to test and report the functional readiness of a site assignment for Kerberos authentication.</span></span> <span data-ttu-id="926d0-106">Este comando consulta el sitio especificado en el parámetro Identity requerido.</span><span class="sxs-lookup"><span data-stu-id="926d0-106">This command queries the site specified in the required Identity parameter.</span></span> <span data-ttu-id="926d0-107">El parámetro de informe opcional hace que el cmdlet escriba un informe HTML en C\\: logs en el equipo en el que se ejecuta el comando.</span><span class="sxs-lookup"><span data-stu-id="926d0-107">The optional Report parameter causes the cmdlet to write an HTML report to C:\\Logs on the computer on which the command is run.</span></span> <span data-ttu-id="926d0-108">El parámetro detallado opcional informa de la información de actividad en la pantalla.</span><span class="sxs-lookup"><span data-stu-id="926d0-108">The optional Verbose parameter reports activity information to the screen.</span></span>

<div>

## <a name="to-test-and-report-functional-readiness-for-kerberos-authentication-for-a-site"></a><span data-ttu-id="926d0-109">Para probar e informar sobre la preparación funcional de la autenticación Kerberos para un sitio</span><span class="sxs-lookup"><span data-stu-id="926d0-109">To test and report functional readiness for Kerberos authentication for a site</span></span>

1.  <span data-ttu-id="926d0-110">Como miembro del grupo RTCUniversalServerAdmins, inicie sesión en un equipo del dominio que ejecute Lync Server 2013 o en el equipo en el que estén instaladas las herramientas administrativas.</span><span class="sxs-lookup"><span data-stu-id="926d0-110">As a member of the RTCUniversalServerAdmins group, log on to a computer in the domain running Lync Server 2013 or on to the computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="926d0-111">Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="926d0-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="926d0-112">En la línea de comandos, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="926d0-112">From the command line, run the following command:</span></span>
    
        Test-CsKerberosAccountAssignment -Identity "site:SiteName" -Report "c:\logs\FileName.htm" -Verbose
    
    <span data-ttu-id="926d0-113">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="926d0-113">For example:</span></span>
    
        Test-CsKerberosAccountAssignment -Identity "site:Redmond" -Report "c:\logs\KerberosReport.htm" -Verbose

</div>

</div>

<span> </span>

</div>

</div>

</div>

