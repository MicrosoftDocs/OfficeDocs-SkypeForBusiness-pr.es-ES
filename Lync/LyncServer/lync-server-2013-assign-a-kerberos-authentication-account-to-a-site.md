---
title: 'Lync Server 2013: asignar una cuenta de autenticación Kerberos a un sitio'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a Kerberos authentication account to a site
ms:assetid: 3d9c587c-c8b8-4f81-8ed9-1458a31fc292
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425901(v=OCS.15)
ms:contentKeyID: 48183929
ms.date: 04/18/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf69e71dd66337551557bddd3bfb7700257a7f69
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029281"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assign-a-kerberos-authentication-account-to-a-site-in-lync-server-2013"></a><span data-ttu-id="c7258-102">Asignar una cuenta de autenticación Kerberos a un sitio en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c7258-102">Assign a Kerberos authentication account to a site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c7258-103">_**Última modificación del tema:** 2017-04-18_</span><span class="sxs-lookup"><span data-stu-id="c7258-103">_**Topic Last Modified:** 2017-04-18_</span></span>

<span data-ttu-id="c7258-104">Para completar con éxito este procedimiento, debe iniciar sesión como usuario miembro del grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="c7258-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="c7258-105">Después de crear la cuenta Kerberos, debe asignarla a un sitio.</span><span class="sxs-lookup"><span data-stu-id="c7258-105">After creating the Kerberos account, you must assign it to a site.</span></span> <span data-ttu-id="c7258-106">Este es un sitio de Lync Server 2013, no un sitio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c7258-106">This is a Lync Server 2013 site, not an Active Directory site.</span></span> <span data-ttu-id="c7258-107">Puede crear varias cuentas de autenticación Kerberos por implementación, pero solo puede asignar una sola cuenta un sitio.</span><span class="sxs-lookup"><span data-stu-id="c7258-107">You can create multiple Kerberos authentication accounts per deployment, but you can assign only one account to a site.</span></span> <span data-ttu-id="c7258-108">Use el siguiente procedimiento para asignar una cuenta de autenticación Kerberos creada con anterioridad a un sitio.</span><span class="sxs-lookup"><span data-stu-id="c7258-108">Use the following procedure to assign a previously created Kerberos authentication account to a site.</span></span> <span data-ttu-id="c7258-109">Para obtener más información sobre cómo crear la cuenta Kerberos, consulte [crear una cuenta de autenticación Kerberos en Lync Server 2013](lync-server-2013-create-a-kerberos-authentication-account.md).</span><span class="sxs-lookup"><span data-stu-id="c7258-109">For details about creating the Kerberos account, see [Create a Kerberos authentication account in Lync Server 2013](lync-server-2013-create-a-kerberos-authentication-account.md).</span></span>

<div>

## <a name="to-assign-a-kerberos-authentication-account-to-a-site"></a><span data-ttu-id="c7258-110">Para asignar cuenta de autenticación Kerberos a un sitio</span><span class="sxs-lookup"><span data-stu-id="c7258-110">To assign a Kerberos authentication account to a site</span></span>

1.  <span data-ttu-id="c7258-111">Como miembro del grupo RTCUniversalServerAdmins, inicie sesión en un equipo del dominio que ejecute Lync Server 2013 o en un equipo en el que estén instaladas las herramientas administrativas.</span><span class="sxs-lookup"><span data-stu-id="c7258-111">As a member of the RTCUniversalServerAdmins group, log on to a computer in the domain running Lync Server 2013 or on to a computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="c7258-112">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="c7258-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="c7258-113">En la línea de comandos, ejecute los dos comandos siguientes:</span><span class="sxs-lookup"><span data-stu-id="c7258-113">From the command line, run the following two commands:</span></span>
    
       ```powershell
        New-CsKerberosAccountAssignment -UserAccount "Domain\UserAccount"
                  -Identity "site:SiteName"
       ```          
    
       ```powershell
        Enable-CsTopology
       ```
    
    <span data-ttu-id="c7258-114">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="c7258-114">For example:</span></span>
    
       ```powershell
        New-CsKerberosAccountAssignment -UserAccount "contoso\kerbauth"
                  -Identity "site:redmond"
       ```
    
       ```powershell
        Enable-CsTopology
       ```
    
    <div class="">
    

    > [!NOTE]  
    > <span data-ttu-id="c7258-p102">Debe especificar el parámetro UserAccount con el formato dominio\nombre de usuario. No se admite el formato User@Domain.extension para hacer referencia a los objetos de equipo creados con fines de autenticación Kerberos.</span><span class="sxs-lookup"><span data-stu-id="c7258-p102">You must specify the UserAccount parameter by using the Domain\User format. The User@Domain.extension format is not supported for referring to the computer objects created for Kerberos authentication purposes.</span></span>

    
    </div>

4.  <span data-ttu-id="c7258-117">**Opcional**: es posible que haya configurado un FQDN (nombre de dominio completo) para los servicios Web, según [cambie la dirección URL de los servicios web en Lync Server 2013](lync-server-2013-change-the-web-services-url.md).</span><span class="sxs-lookup"><span data-stu-id="c7258-117">**OPTIONAL**: You may have configured an override FQDN (fully qualified domain name) for your WebServices, as per [Change the Web Services URL in Lync Server 2013](lync-server-2013-change-the-web-services-url.md).</span></span> <span data-ttu-id="c7258-118">Si ese es el caso, necesitará agregar un SPN para este FQDN también.</span><span class="sxs-lookup"><span data-stu-id="c7258-118">If that's the case, you'll need to add a SPN for this FQDN as well.</span></span> <span data-ttu-id="c7258-119">Por ejemplo, si el FQDN es webservices. contoso. local, ejecutaría:</span><span class="sxs-lookup"><span data-stu-id="c7258-119">For example, if the FQDN was webservices.contoso.local, you would run:</span></span>
    
    ```console
    setspn -S http/webservices.contoso.local kerbauth
    ```
5.     
    <div class="">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c7258-120">Después de realizar cambios en la autenticación Kerberos, como agregar una cuenta o quitar una cuenta, debe ejecutar <STRONG>enable-CsTopology</STRONG> desde el símbolo del sistema del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c7258-120">After making any changes to Kerberos authentication, such as adding an account or removing an account, you must run <STRONG>Enable-CsTopology</STRONG> from the Lync Server Management Shell command prompt.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

