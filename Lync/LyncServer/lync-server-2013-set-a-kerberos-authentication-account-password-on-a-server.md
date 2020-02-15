---
title: 'Lync Server 2013: establecer una contraseña de cuenta de autenticación Kerberos en un servidor'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set a Kerberos authentication account password on a server
ms:assetid: 902d3292-678d-4512-9248-586053cb638b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398734(v=OCS.15)
ms:contentKeyID: 48184787
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9799be0fda2b1a3c5b7765774b1f9e3199cc61f3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051664"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-a-kerberos-authentication-account-password-on-a-server-in-lync-server-2013"></a><span data-ttu-id="14b80-102">Establecer una contraseña de cuenta de autenticación Kerberos en un servidor en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="14b80-102">Set a Kerberos authentication account password on a server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="14b80-103">_**Última modificación del tema:** 2012-01-16_</span><span class="sxs-lookup"><span data-stu-id="14b80-103">_**Topic Last Modified:** 2012-01-16_</span></span>

<span data-ttu-id="14b80-104">Para completar con éxito este procedimiento, debe iniciar sesión como usuario miembro del grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="14b80-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group.</span></span>

<span data-ttu-id="14b80-105">Debe configurar una contraseña en la cuenta de Kerberos por cada sitio que tenga servidores front-end, servidores Standard Edition y directores.</span><span class="sxs-lookup"><span data-stu-id="14b80-105">You must set up a password on the Kerberos account for each site that has Front End Servers, Standard Edition servers, and Directors.</span></span> <span data-ttu-id="14b80-106">Puede configurar la contraseña si ejecuta el cmdlet **set-CsKerberosAccountPassword** de Windows PowerShell en un servidor del sitio (por ejemplo, un servidor front-end).</span><span class="sxs-lookup"><span data-stu-id="14b80-106">You can set up the password by running the **Set-CsKerberosAccountPassword** Windows PowerShell cmdlet on one server in the site (for example, one Front End Server).</span></span> <span data-ttu-id="14b80-107">Para cada sitio, debe ejecutar el cmdlet **set-CsKerberosAccountPassword** .</span><span class="sxs-lookup"><span data-stu-id="14b80-107">For each site, you must run the **Set-CsKerberosAccountPassword** cmdlet.</span></span> <span data-ttu-id="14b80-108">El cmdlet configura Internet Information Services (IIS) para el servicio de servicios web y, a continuación, establece la contraseña en la cuenta de equipo en servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="14b80-108">The cmdlet configures Internet Information Services (IIS) for the Web Services service, and then sets the password on the computer account in Active Directory Domain Services.</span></span> <span data-ttu-id="14b80-109">Un método alternativo, basado en el parámetro que se usa con el cmdlet, configura IIS en un servidor mientras usa otro servidor que se ha configurado como el origen de la contraseña de la cuenta de Kerberos.</span><span class="sxs-lookup"><span data-stu-id="14b80-109">An alternate method, based on which parameter is used with the cmdlet, configures IIS on one server while using another server that has been configured as the source of the Kerberos account password.</span></span>

<span data-ttu-id="14b80-110">Cuando usa el cmdlet **Set-CsKerberosAccountPassword** para establecer una contraseña, Kerberos elige como contraseña una cadena generada al azar.</span><span class="sxs-lookup"><span data-stu-id="14b80-110">When you use the **Set-CsKerberosAccountPassword** cmdlet to set a password, Kerberos sets the password to a randomly generated string.</span></span> <span data-ttu-id="14b80-111">Este cmdlet se pone en contacto con todas las instancias de IIS en todos los sitios centrales de Lync Server 2013 a los que esta cuenta está asignada.</span><span class="sxs-lookup"><span data-stu-id="14b80-111">This cmdlet contacts all IIS instances in all Lync Server 2013 central sites to which this account is assigned.</span></span>

<div>

## <a name="to-set-a-password-for-a-kerberos-authentication-account"></a><span data-ttu-id="14b80-112">Para establecer una contraseña de una cuenta de autenticación de Kerberos</span><span class="sxs-lookup"><span data-stu-id="14b80-112">To set a password for a Kerberos authentication account</span></span>

1.  <span data-ttu-id="14b80-113">Inicie sesión en cualquier equipo del dominio que tenga instalado el shell de administración de Lync Server como miembro del grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="14b80-113">Log on to any domain computer with Lync Server Management Shell installed as a member of the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="14b80-114">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="14b80-114">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="14b80-115">En la línea de comandos, ejecute los dos comandos siguientes:</span><span class="sxs-lookup"><span data-stu-id="14b80-115">From the command line, run the following two commands:</span></span>
    
        Set-CsKerberosAccountPassword -UserAccount "Domain\UserAccount"
    
    <span data-ttu-id="14b80-116">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="14b80-116">For example:</span></span>
    
        Set-CsKerberosAccountPassword -UserAccount "contoso\KerbAuth"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="14b80-p103">Debe especificar el parámetro UserAccount con el formato dominio\nombre de usuario. No se admite el formato Usuario@Dominio.extensión para hacer referencia a los objetos de equipo creados para la autenticación de Kerberos.</span><span class="sxs-lookup"><span data-stu-id="14b80-p103">You must specify the UserAccount parameter by using the Domain\User format. The User@Domain.extension format is not supported for referencing the computer objects created for Kerberos authentication purposes.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="14b80-119">Después de realizar cambios en la autenticación Kerberos, como agregar una cuenta o quitar una cuenta, debe ejecutar <STRONG>enable-CsTopology</STRONG> desde el símbolo del sistema del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="14b80-119">After making any changes to Kerberos authentication, such as adding an account or removing an account, you must run <STRONG>Enable-CsTopology</STRONG> from the Lync Server Management Shell command prompt.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

