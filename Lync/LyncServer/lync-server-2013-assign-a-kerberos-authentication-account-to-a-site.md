---
title: 'Lync Server 2013: Asignar una cuenta de autenticación Kerberos a un sitio'
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
ms.openlocfilehash: 230341bfc6b26bebd22b55195280ffdff130873d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738390"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assign-a-kerberos-authentication-account-to-a-site-in-lync-server-2013"></a><span data-ttu-id="b0afb-102">Asignar una cuenta de autenticación Kerberos a un sitio en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b0afb-102">Assign a Kerberos authentication account to a site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b0afb-103">_**Última modificación del tema:** 2017-04-18_</span><span class="sxs-lookup"><span data-stu-id="b0afb-103">_**Topic Last Modified:** 2017-04-18_</span></span>

<span data-ttu-id="b0afb-104">Para completar correctamente este procedimiento, debe haber iniciado sesión como un usuario que sea miembro del grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="b0afb-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="b0afb-105">Después de crear la cuenta de Kerberos, debe asignarla a un sitio.</span><span class="sxs-lookup"><span data-stu-id="b0afb-105">After creating the Kerberos account, you must assign it to a site.</span></span> <span data-ttu-id="b0afb-106">Este es un sitio de Lync Server 2013, no un sitio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b0afb-106">This is a Lync Server 2013 site, not an Active Directory site.</span></span> <span data-ttu-id="b0afb-107">Puede crear varias cuentas de autenticación Kerberos por implementación, pero solo puede asignar una cuenta a un sitio.</span><span class="sxs-lookup"><span data-stu-id="b0afb-107">You can create multiple Kerberos authentication accounts per deployment, but you can assign only one account to a site.</span></span> <span data-ttu-id="b0afb-108">Use el procedimiento siguiente para asignar una cuenta de autenticación Kerberos creada previamente a un sitio.</span><span class="sxs-lookup"><span data-stu-id="b0afb-108">Use the following procedure to assign a previously created Kerberos authentication account to a site.</span></span> <span data-ttu-id="b0afb-109">Para obtener detalles sobre la creación de la cuenta de Kerberos, consulte [crear una cuenta de autenticación Kerberos en Lync Server 2013](lync-server-2013-create-a-kerberos-authentication-account.md).</span><span class="sxs-lookup"><span data-stu-id="b0afb-109">For details about creating the Kerberos account, see [Create a Kerberos authentication account in Lync Server 2013](lync-server-2013-create-a-kerberos-authentication-account.md).</span></span>

<div>

## <a name="to-assign-a-kerberos-authentication-account-to-a-site"></a><span data-ttu-id="b0afb-110">Para asignar una cuenta de autenticación Kerberos a un sitio</span><span class="sxs-lookup"><span data-stu-id="b0afb-110">To assign a Kerberos authentication account to a site</span></span>

1.  <span data-ttu-id="b0afb-111">Como miembro del grupo RTCUniversalServerAdmins, inicie sesión en un equipo del dominio que ejecute Lync Server 2013 o en un equipo en el que estén instaladas las herramientas administrativas.</span><span class="sxs-lookup"><span data-stu-id="b0afb-111">As a member of the RTCUniversalServerAdmins group, log on to a computer in the domain running Lync Server 2013 or on to a computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="b0afb-112">Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="b0afb-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="b0afb-113">En la línea de comandos, ejecute los dos comandos siguientes:</span><span class="sxs-lookup"><span data-stu-id="b0afb-113">From the command line, run the following two commands:</span></span>
    
       ```powershell
        New-CsKerberosAccountAssignment -UserAccount "Domain\UserAccount"
                  -Identity "site:SiteName"
       ```          
    
       ```powershell
        Enable-CsTopology
       ```
    
    <span data-ttu-id="b0afb-114">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b0afb-114">For example:</span></span>
    
       ```powershell
        New-CsKerberosAccountAssignment -UserAccount "contoso\kerbauth"
                  -Identity "site:redmond"
       ```
    
       ```powershell
        Enable-CsTopology
       ```
    
    <div class="">
    

    > [!NOTE]  
    > <span data-ttu-id="b0afb-115">Debe especificar el parámetro Cuentadeusuario con el formato Dominio\usuario.</span><span class="sxs-lookup"><span data-stu-id="b0afb-115">You must specify the UserAccount parameter by using the Domain\User format.</span></span> <span data-ttu-id="b0afb-116">El User@Domain. el formato de extensión no es compatible con la referencia a los objetos de equipo creados para la autenticación Kerberos.</span><span class="sxs-lookup"><span data-stu-id="b0afb-116">The User@Domain.extension format is not supported for referring to the computer objects created for Kerberos authentication purposes.</span></span>

    
    </div>

4.  <span data-ttu-id="b0afb-117">**Opcional**: es posible que haya configurado un reemplazo de FQDN (nombre de dominio completo) para los servicios Web, según [cambie la dirección URL de los servicios web en Lync Server 2013](lync-server-2013-change-the-web-services-url.md).</span><span class="sxs-lookup"><span data-stu-id="b0afb-117">**OPTIONAL**: You may have configured an override FQDN (fully qualified domain name) for your WebServices, as per [Change the Web Services URL in Lync Server 2013](lync-server-2013-change-the-web-services-url.md).</span></span> <span data-ttu-id="b0afb-118">Si es así, también tendrá que agregar un SPN para este FQDN.</span><span class="sxs-lookup"><span data-stu-id="b0afb-118">If that's the case, you'll need to add a SPN for this FQDN as well.</span></span> <span data-ttu-id="b0afb-119">Por ejemplo, si el FQDN es webservices. contoso. local, ejecutaría:</span><span class="sxs-lookup"><span data-stu-id="b0afb-119">For example, if the FQDN was webservices.contoso.local, you would run:</span></span>
    
    ```console
    setspn -S http/webservices.contoso.local kerbauth
    ```
5.     
    <div class="">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="b0afb-120">Después de realizar cambios en la autenticación Kerberos, como agregar una cuenta o quitar una cuenta, debe ejecutar <STRONG>enable-CsTopology</STRONG> desde el símbolo del sistema del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b0afb-120">After making any changes to Kerberos authentication, such as adding an account or removing an account, you must run <STRONG>Enable-CsTopology</STRONG> from the Lync Server Management Shell command prompt.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

