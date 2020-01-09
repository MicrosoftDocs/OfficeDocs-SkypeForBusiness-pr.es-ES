---
title: 'Lync Server 2013: Quitar la autenticación Kerberos de un sitio'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Remove Kerberos authentication from a site
ms:assetid: 93171b02-bb36-42dc-943d-86d9dde45b59
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398749(v=OCS.15)
ms:contentKeyID: 48184806
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 372c8d4689a2c594c853819ced6ccb92adfa6944
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992707"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="in-lync-server-2013-remove-kerberos-authentication-from-a-site"></a><span data-ttu-id="2d92d-102">Quitar la autenticación Kerberos de un sitio en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2d92d-102">In Lync Server 2013 remove Kerberos authentication from a site</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2d92d-103">_**Última modificación del tema:** 2012-01-16_</span><span class="sxs-lookup"><span data-stu-id="2d92d-103">_**Topic Last Modified:** 2012-01-16_</span></span>

<span data-ttu-id="2d92d-104">Para completar correctamente este procedimiento, debe haber iniciado sesión como un usuario que sea miembro del grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="2d92d-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="2d92d-105">Si necesita quitar la autenticación Kerberos de un sitio o retirar un sitio, debe quitar la asignación de cuenta de autenticación Kerberos del sitio mediante el cmdlet **Remove-CsKerberosAccountAssignment** .</span><span class="sxs-lookup"><span data-stu-id="2d92d-105">If you need to remove Kerberos authentication from a site or retire a site, you must remove the Kerberos authentication account assignment from the site by using the **Remove-CsKerberosAccountAssignment** cmdlet.</span></span> <span data-ttu-id="2d92d-106">Use el siguiente procedimiento para quitar la asignación de cuenta de autenticación Kerberos, que quita la asignación de todos los equipos del sitio.</span><span class="sxs-lookup"><span data-stu-id="2d92d-106">Use the following procedure to remove the Kerberos authentication account assignment, which removes the assignment from all computers in the site.</span></span>

<div class=" ">


> [!WARNING]  
> <span data-ttu-id="2d92d-107">Si va a retirar permanentemente la cuenta habilitada para Kerberos, debe usar usuarios y equipos de Active Directory para eliminarla de los servicios de dominio de Active Directory después de quitar la asignación.</span><span class="sxs-lookup"><span data-stu-id="2d92d-107">If you are permanently retiring the Kerberos-enabled account, you should use Active Directory Users and Computers to delete it from Active Directory Domain Services after you have removed the assignment.</span></span> <span data-ttu-id="2d92d-108">Si tiene previsto usar el objeto en el futuro, es posible que desee mantener el objeto de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2d92d-108">If you plan to use the object in the future, you might want to keep the Active Directory object.</span></span>



</div>

<div>

## <a name="to-remove-kerberos-authentication-from-a-site"></a><span data-ttu-id="2d92d-109">Para quitar la autenticación Kerberos de un sitio</span><span class="sxs-lookup"><span data-stu-id="2d92d-109">To remove Kerberos authentication from a site</span></span>

1.  <span data-ttu-id="2d92d-110">Como miembro del grupo RTCUniversalServerAdmins, inicie sesión en un equipo del dominio que ejecute Lync Server 2013 o en un equipo en el que estén instaladas las herramientas administrativas.</span><span class="sxs-lookup"><span data-stu-id="2d92d-110">As a member of the RTCUniversalServerAdmins group, log on to a computer in the domain running Lync Server 2013 or on to a computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="2d92d-111">Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="2d92d-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="2d92d-112">En la línea de comandos, ejecute los dos comandos siguientes:</span><span class="sxs-lookup"><span data-stu-id="2d92d-112">From the command line, run the following two commands:</span></span>
    
       ```PowerShell
        Remove-CsKerberosAccountAssignment -Identity "site:SiteName"
       ```
    
       ```PowerShell
        Enable-CsTopology
       ```
    
    <span data-ttu-id="2d92d-113">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="2d92d-113">For example:</span></span>
    
       ```PowerShell
        Remove-CsKerberosAccountAssignment -Identity "site:Redmond"
       ```
    
       ```PowerShell
        Enable-CsTopology
       ```
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="2d92d-114">Después de realizar cambios en la autenticación Kerberos, como agregar una cuenta o quitar una cuenta, debe ejecutar <STRONG>enable-CsTopology</STRONG> desde el símbolo del sistema del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2d92d-114">After making any changes to Kerberos authentication, such as adding an account or removing an account, you must run <STRONG>Enable-CsTopology</STRONG> from the Lync Server Management Shell command prompt.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

