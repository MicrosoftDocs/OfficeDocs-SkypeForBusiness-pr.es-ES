---
title: Probar la configuración de la cuenta Kerberos asignada a un sitio
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing configuration of the Kerberos account assigned to a site
ms:assetid: a087d77e-c59e-44f5-9caa-ccfd41be7276
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743837(v=OCS.15)
ms:contentKeyID: 63969637
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 08477e9902a1410a98516a79fe5fdd01c5e94214
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504127"
---
# <a name="testing-configuration-of-the-kerberos-account-assigned-to-a-site-in-lync-server-2013"></a><span data-ttu-id="10dfb-102">Probar la configuración de la cuenta Kerberos asignada a un sitio en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="10dfb-102">Testing configuration of the Kerberos account assigned to a site in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="10dfb-103">_**Última modificación del tema:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="10dfb-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="10dfb-104">Programación de comprobación</span><span class="sxs-lookup"><span data-stu-id="10dfb-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="10dfb-105">Diario</span><span class="sxs-lookup"><span data-stu-id="10dfb-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10dfb-106">Herramienta de prueba</span><span class="sxs-lookup"><span data-stu-id="10dfb-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="10dfb-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="10dfb-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10dfb-108">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="10dfb-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="10dfb-109">Cuando se ejecuta de forma local mediante el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="10dfb-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="10dfb-110">Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet Test-CsKerberosAccountAssignment.</span><span class="sxs-lookup"><span data-stu-id="10dfb-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsKerberosAccountAssignment cmdlet.</span></span> <span data-ttu-id="10dfb-111">Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="10dfb-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsKerberosAccountAssignment&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="10dfb-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="10dfb-112">Description</span></span>

<span data-ttu-id="10dfb-113">El cmdlet Test-CsKerberosAccountAssignment permite comprobar que una cuenta Kerberos está asociada a un sitio determinado, que esta cuenta está configurada correctamente y que la cuenta funciona como se esperaba.</span><span class="sxs-lookup"><span data-stu-id="10dfb-113">The Test-CsKerberosAccountAssignment cmdlet enables you to verify that a Kerberos account is associated with a given site, that this account is configured correctly, and that the account is working as expected.</span></span> <span data-ttu-id="10dfb-114">Las cuentas Kerberos son cuentas de equipo que pueden servir como entidad de autenticación para todos los equipos de un sitio que ejecutan Internet Information Server (IIS).</span><span class="sxs-lookup"><span data-stu-id="10dfb-114">Kerberos accounts are computer accounts that can serve as the authentication principal for all the computers in a site that are running Internet Information Server (IIS).</span></span> <span data-ttu-id="10dfb-115">Como estas cuentas usan el protocolo de autenticación Kerberos, las cuentas se denominan cuentas Kerberos y el nuevo proceso de autenticación se conoce como autenticación Web Kerberos.</span><span class="sxs-lookup"><span data-stu-id="10dfb-115">Because these accounts use the Kerberos authentication protocol, the accounts are known as Kerberos accounts, and the new authentication process is known as Kerberos web authentication.</span></span> <span data-ttu-id="10dfb-116">Esto le permite administrar todos los servidores IIS con una sola cuenta.</span><span class="sxs-lookup"><span data-stu-id="10dfb-116">This enables you to manage all IIS servers by using a single account.</span></span>

<span data-ttu-id="10dfb-117">Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="10dfb-117">For more information, see the Help documentation for the [Test-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15)) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="10dfb-118">Ejecutar la prueba</span><span class="sxs-lookup"><span data-stu-id="10dfb-118">Running the Test</span></span>

<span data-ttu-id="10dfb-119">De forma predeterminada, Test-CsKerberosAccountAssignment muestra muy poco resultados en pantalla.</span><span class="sxs-lookup"><span data-stu-id="10dfb-119">By default, Test-CsKerberosAccountAssignment displays very little output on-screen.</span></span> <span data-ttu-id="10dfb-120">En su lugar, la información devuelta por el cmdlet se escribe en un archivo HTML.</span><span class="sxs-lookup"><span data-stu-id="10dfb-120">Instead, information returned by the cmdlet is written to an HTML file.</span></span> <span data-ttu-id="10dfb-121">Por ello, se recomienda incluir el parámetro verbose y el parámetro Report en cualquier momento que se ejecute test-CsKerberosAccountAssignment.</span><span class="sxs-lookup"><span data-stu-id="10dfb-121">Because of that, we recommend that you include the Verbose parameter and the Report parameter any time that you run Test-CsKerberosAccountAssignment.</span></span> <span data-ttu-id="10dfb-122">El parámetro verbose proporcionará un resultado ligeramente más detallado en pantalla mientras se ejecuta el cmdlet.</span><span class="sxs-lookup"><span data-stu-id="10dfb-122">The Verbose parameter will provide slightly more detailed output on-screen while the cmdlet runs.</span></span> <span data-ttu-id="10dfb-123">El parámetro Report permite especificar una ruta de acceso de archivo y un nombre de archivo para el archivo HTML generado por test-CsKerberosAccountAssignment.</span><span class="sxs-lookup"><span data-stu-id="10dfb-123">The Report parameter allows you to specify a file path and file name for the HTML file generated by Test-CsKerberosAccountAssignment.</span></span> <span data-ttu-id="10dfb-124">Si no incluye el parámetro de informe, el archivo HTML se guardará automáticamente en la carpeta de usuarios y se le asignará un nombre similar al siguiente: ce84964a-c4da-4622-ad34-c54ff3ed361f.html.</span><span class="sxs-lookup"><span data-stu-id="10dfb-124">If you do not include the Report parameter the HTML file will automatically be saved to your Users folder and be given a name similar to this: ce84964a-c4da-4622-ad34-c54ff3ed361f.html.</span></span>

<span data-ttu-id="10dfb-125">También debe especificar una identidad de sitio al ejecutar test-CsKerberosAccountAssignment.</span><span class="sxs-lookup"><span data-stu-id="10dfb-125">You must also specify a site Identity when you run Test-CsKerberosAccountAssignment.</span></span> <span data-ttu-id="10dfb-126">Las cuentas Kerberos se asignan en el ámbito de sitio.</span><span class="sxs-lookup"><span data-stu-id="10dfb-126">Kerberos accounts are assigned at the site scope.</span></span>

<span data-ttu-id="10dfb-127">El siguiente comando ejecuta Test-CsKerberosAccountAssignment y guarda el resultado en un archivo denominado C: \\ Logs \\KerberosTest.html:</span><span class="sxs-lookup"><span data-stu-id="10dfb-127">The following command runs Test-CsKerberosAccountAssignment and saves the output to a file that is named C:\\Logs\\KerberosTest.html:</span></span>

    Test-CsKerberosAccountAssignment -Identity "site:Redmond" -Report "C:\Logs\KerberosTest.html" -Verbose

<span data-ttu-id="10dfb-128">Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="10dfb-128">For more information, see the Help documentation for the [Test-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15)) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="10dfb-129">Determinar si se ha realizado correctamente o erróneo</span><span class="sxs-lookup"><span data-stu-id="10dfb-129">Determining Success or Failure</span></span>

<span data-ttu-id="10dfb-130">El cmdlet Test-CsKerberosAccountAssignment no devuelve una indicación sencilla de éxito o error.</span><span class="sxs-lookup"><span data-stu-id="10dfb-130">The Test-CsKerberosAccountAssignment cmdlet does not return a simple indication of success or failure.</span></span> <span data-ttu-id="10dfb-131">En su lugar, debe ver el archivo HTML generado con Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="10dfb-131">Instead, you must view the generated HTML file by using Internet Explorer.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="10dfb-132">Motivos por los que se ha producido un error en la prueba</span><span class="sxs-lookup"><span data-stu-id="10dfb-132">Reasons Why the Test Might Have Failed</span></span>

<span data-ttu-id="10dfb-133">Estas son algunas de las razones comunes por las que Test-CsKerberosAccountAssignment podría producir un error:</span><span class="sxs-lookup"><span data-stu-id="10dfb-133">Here are some common reasons why Test-CsKerberosAccountAssignment might fail:</span></span>

  - <span data-ttu-id="10dfb-134">Es posible que haya especificado una identidad de sitio incorrecta.</span><span class="sxs-lookup"><span data-stu-id="10dfb-134">You might have specified an incorrect site Identity.</span></span> <span data-ttu-id="10dfb-135">Para devolver una lista de identidades de sitio válidas, use este comando:</span><span class="sxs-lookup"><span data-stu-id="10dfb-135">To return a list of valid site Identity, use this command:</span></span>
    
        Get-CsSite | Select-Identity Identity
    
    <span data-ttu-id="10dfb-136">Una identidad de sitio suele tener el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="10dfb-136">A site Identity typically looks as follows:</span></span>
    
    <span data-ttu-id="10dfb-137">sitio: Redmond</span><span class="sxs-lookup"><span data-stu-id="10dfb-137">site:Redmond</span></span>

  - <span data-ttu-id="10dfb-138">Es posible que el sitio especificado no tenga asignada una cuenta Kerberos.</span><span class="sxs-lookup"><span data-stu-id="10dfb-138">The specified site might not have a Kerberos account assigned to it.</span></span> <span data-ttu-id="10dfb-139">Puede determinar si una cuenta Kerberos está asignada a un sitio mediante la ejecución de un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="10dfb-139">You can determine whether or not a Kerberos account is assigned to a site by running a command similar to this:</span></span>
    
        Get-CsKerberosAccountAssignment -Identity "site:Redmond"

  - <span data-ttu-id="10dfb-140">Es posible que la cuenta Kerberos tenga una contraseña no válida.</span><span class="sxs-lookup"><span data-stu-id="10dfb-140">Your Kerberos account might have a password that isn't valid.</span></span> <span data-ttu-id="10dfb-141">Si recibe el siguiente mensaje de error en el informe, probablemente tendrá que restablecer la contraseña de la cuenta Kerberos:</span><span class="sxs-lookup"><span data-stu-id="10dfb-141">If you receive the following error message in report, you'll probably have to reset the Kerberos account password:</span></span>
    
    <span data-ttu-id="10dfb-142">InvalidKerberosConfiguration: la configuración de Kerberos no es válida.</span><span class="sxs-lookup"><span data-stu-id="10dfb-142">InvalidKerberosConfiguration: The Kerberos configuration is invalid.</span></span>
    
    <span data-ttu-id="10dfb-143">InvalidKerberosConfiguration: la configuración de Kerberos en atl-cs001.litwareinc.com no es válida.</span><span class="sxs-lookup"><span data-stu-id="10dfb-143">InvalidKerberosConfiguration: The Kerberos configuration on atl-cs001.litwareinc.com is invalid.</span></span> <span data-ttu-id="10dfb-144">La cuenta asignada esperada es litwareinc \\ kerberostest.</span><span class="sxs-lookup"><span data-stu-id="10dfb-144">The expected assigned account is litwareinc\\kerberostest.</span></span> <span data-ttu-id="10dfb-145">Asegúrese de que la cuenta no ha expirado y de que la contraseña configurada en el equipo coincida con la contraseña de Active Directory de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="10dfb-145">Ensure that the account has not expired, and the configured password on the machine matches the Active Directory password of the account.</span></span>
    
    <span data-ttu-id="10dfb-146">Puede establecer la contraseña con el cmdlet [set-CsKerberosAccountPassword](https://technet.microsoft.com/library/Gg398659(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="10dfb-146">You can set the password using the [Set-CsKerberosAccountPassword](https://technet.microsoft.com/library/Gg398659(v=OCS.15)) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

