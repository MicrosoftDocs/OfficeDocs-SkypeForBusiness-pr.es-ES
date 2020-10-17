---
title: Probar la configuración de la cuenta Kerberos asignada a un sitio
description: Probar la configuración de la cuenta Kerberos asignada a un sitio.
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
ms.openlocfilehash: 0eab1618474a19753a4c6064d59aa4f8a856fceb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560696"
---
# <a name="testing-configuration-of-the-kerberos-account-assigned-to-a-site-in-lync-server-2013"></a><span data-ttu-id="c78ca-103">Probar la configuración de la cuenta Kerberos asignada a un sitio en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c78ca-103">Testing configuration of the Kerberos account assigned to a site in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c78ca-104">_**Última modificación del tema:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="c78ca-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c78ca-105">Programación de comprobación</span><span class="sxs-lookup"><span data-stu-id="c78ca-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="c78ca-106">Diario</span><span class="sxs-lookup"><span data-stu-id="c78ca-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c78ca-107">Herramienta de prueba</span><span class="sxs-lookup"><span data-stu-id="c78ca-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="c78ca-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c78ca-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c78ca-109">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="c78ca-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="c78ca-110">Cuando se ejecuta de forma local mediante el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="c78ca-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="c78ca-111">Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet Test-CsKerberosAccountAssignment.</span><span class="sxs-lookup"><span data-stu-id="c78ca-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsKerberosAccountAssignment cmdlet.</span></span> <span data-ttu-id="c78ca-112">Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="c78ca-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsKerberosAccountAssignment&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="c78ca-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="c78ca-113">Description</span></span>

<span data-ttu-id="c78ca-114">El cmdlet Test-CsKerberosAccountAssignment permite comprobar que una cuenta Kerberos está asociada a un sitio determinado, que esta cuenta está configurada correctamente y que la cuenta funciona como se esperaba.</span><span class="sxs-lookup"><span data-stu-id="c78ca-114">The Test-CsKerberosAccountAssignment cmdlet enables you to verify that a Kerberos account is associated with a given site, that this account is configured correctly, and that the account is working as expected.</span></span> <span data-ttu-id="c78ca-115">Las cuentas Kerberos son cuentas de equipo que pueden servir como entidad de autenticación para todos los equipos de un sitio que ejecutan Internet Information Server (IIS).</span><span class="sxs-lookup"><span data-stu-id="c78ca-115">Kerberos accounts are computer accounts that can serve as the authentication principal for all the computers in a site that are running Internet Information Server (IIS).</span></span> <span data-ttu-id="c78ca-116">Como estas cuentas usan el protocolo de autenticación Kerberos, las cuentas se denominan cuentas Kerberos y el nuevo proceso de autenticación se conoce como autenticación Web Kerberos.</span><span class="sxs-lookup"><span data-stu-id="c78ca-116">Because these accounts use the Kerberos authentication protocol, the accounts are known as Kerberos accounts, and the new authentication process is known as Kerberos web authentication.</span></span> <span data-ttu-id="c78ca-117">Esto le permite administrar todos los servidores IIS con una sola cuenta.</span><span class="sxs-lookup"><span data-stu-id="c78ca-117">This enables you to manage all IIS servers by using a single account.</span></span>

<span data-ttu-id="c78ca-118">Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="c78ca-118">For more information, see the Help documentation for the [Test-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15)) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="c78ca-119">Ejecutar la prueba</span><span class="sxs-lookup"><span data-stu-id="c78ca-119">Running the Test</span></span>

<span data-ttu-id="c78ca-120">De forma predeterminada, Test-CsKerberosAccountAssignment muestra muy poco resultados en pantalla.</span><span class="sxs-lookup"><span data-stu-id="c78ca-120">By default, Test-CsKerberosAccountAssignment displays very little output on-screen.</span></span> <span data-ttu-id="c78ca-121">En su lugar, la información devuelta por el cmdlet se escribe en un archivo HTML.</span><span class="sxs-lookup"><span data-stu-id="c78ca-121">Instead, information returned by the cmdlet is written to an HTML file.</span></span> <span data-ttu-id="c78ca-122">Por ello, se recomienda incluir el parámetro verbose y el parámetro Report en cualquier momento que se ejecute test-CsKerberosAccountAssignment.</span><span class="sxs-lookup"><span data-stu-id="c78ca-122">Because of that, we recommend that you include the Verbose parameter and the Report parameter any time that you run Test-CsKerberosAccountAssignment.</span></span> <span data-ttu-id="c78ca-123">El parámetro verbose proporcionará un resultado ligeramente más detallado en pantalla mientras se ejecuta el cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c78ca-123">The Verbose parameter will provide slightly more detailed output on-screen while the cmdlet runs.</span></span> <span data-ttu-id="c78ca-124">El parámetro Report permite especificar una ruta de acceso de archivo y un nombre de archivo para el archivo HTML generado por test-CsKerberosAccountAssignment.</span><span class="sxs-lookup"><span data-stu-id="c78ca-124">The Report parameter allows you to specify a file path and file name for the HTML file generated by Test-CsKerberosAccountAssignment.</span></span> <span data-ttu-id="c78ca-125">Si no incluye el parámetro de informe, el archivo HTML se guardará automáticamente en la carpeta de usuarios y se le asignará un nombre similar al siguiente: ce84964a-c4da-4622-ad34-c54ff3ed361f.html.</span><span class="sxs-lookup"><span data-stu-id="c78ca-125">If you do not include the Report parameter the HTML file will automatically be saved to your Users folder and be given a name similar to this: ce84964a-c4da-4622-ad34-c54ff3ed361f.html.</span></span>

<span data-ttu-id="c78ca-126">También debe especificar una identidad de sitio al ejecutar test-CsKerberosAccountAssignment.</span><span class="sxs-lookup"><span data-stu-id="c78ca-126">You must also specify a site Identity when you run Test-CsKerberosAccountAssignment.</span></span> <span data-ttu-id="c78ca-127">Las cuentas Kerberos se asignan en el ámbito de sitio.</span><span class="sxs-lookup"><span data-stu-id="c78ca-127">Kerberos accounts are assigned at the site scope.</span></span>

<span data-ttu-id="c78ca-128">El siguiente comando ejecuta Test-CsKerberosAccountAssignment y guarda el resultado en un archivo denominado C: \\ Logs \\KerberosTest.html:</span><span class="sxs-lookup"><span data-stu-id="c78ca-128">The following command runs Test-CsKerberosAccountAssignment and saves the output to a file that is named C:\\Logs\\KerberosTest.html:</span></span>

    Test-CsKerberosAccountAssignment -Identity "site:Redmond" -Report "C:\Logs\KerberosTest.html" -Verbose

<span data-ttu-id="c78ca-129">Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="c78ca-129">For more information, see the Help documentation for the [Test-CsKerberosAccountAssignment](https://technet.microsoft.com/library/Gg425938(v=OCS.15)) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="c78ca-130">Determinar si se ha realizado correctamente o erróneo</span><span class="sxs-lookup"><span data-stu-id="c78ca-130">Determining Success or Failure</span></span>

<span data-ttu-id="c78ca-131">El cmdlet Test-CsKerberosAccountAssignment no devuelve una indicación sencilla de éxito o error.</span><span class="sxs-lookup"><span data-stu-id="c78ca-131">The Test-CsKerberosAccountAssignment cmdlet does not return a simple indication of success or failure.</span></span> <span data-ttu-id="c78ca-132">En su lugar, debe ver el archivo HTML generado con Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="c78ca-132">Instead, you must view the generated HTML file by using Internet Explorer.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="c78ca-133">Motivos por los que se ha producido un error en la prueba</span><span class="sxs-lookup"><span data-stu-id="c78ca-133">Reasons Why the Test Might Have Failed</span></span>

<span data-ttu-id="c78ca-134">Estas son algunas de las razones comunes por las que Test-CsKerberosAccountAssignment podría producir un error:</span><span class="sxs-lookup"><span data-stu-id="c78ca-134">Here are some common reasons why Test-CsKerberosAccountAssignment might fail:</span></span>

  - <span data-ttu-id="c78ca-135">Es posible que haya especificado una identidad de sitio incorrecta.</span><span class="sxs-lookup"><span data-stu-id="c78ca-135">You might have specified an incorrect site Identity.</span></span> <span data-ttu-id="c78ca-136">Para devolver una lista de identidades de sitio válidas, use este comando:</span><span class="sxs-lookup"><span data-stu-id="c78ca-136">To return a list of valid site Identity, use this command:</span></span>
    
        Get-CsSite | Select-Identity Identity
    
    <span data-ttu-id="c78ca-137">Una identidad de sitio suele tener el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="c78ca-137">A site Identity typically looks as follows:</span></span>
    
    <span data-ttu-id="c78ca-138">sitio: Redmond</span><span class="sxs-lookup"><span data-stu-id="c78ca-138">site:Redmond</span></span>

  - <span data-ttu-id="c78ca-139">Es posible que el sitio especificado no tenga asignada una cuenta Kerberos.</span><span class="sxs-lookup"><span data-stu-id="c78ca-139">The specified site might not have a Kerberos account assigned to it.</span></span> <span data-ttu-id="c78ca-140">Puede determinar si una cuenta Kerberos está asignada a un sitio mediante la ejecución de un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="c78ca-140">You can determine whether or not a Kerberos account is assigned to a site by running a command similar to this:</span></span>
    
        Get-CsKerberosAccountAssignment -Identity "site:Redmond"

  - <span data-ttu-id="c78ca-141">Es posible que la cuenta Kerberos tenga una contraseña no válida.</span><span class="sxs-lookup"><span data-stu-id="c78ca-141">Your Kerberos account might have a password that isn't valid.</span></span> <span data-ttu-id="c78ca-142">Si recibe el siguiente mensaje de error en el informe, probablemente tendrá que restablecer la contraseña de la cuenta Kerberos:</span><span class="sxs-lookup"><span data-stu-id="c78ca-142">If you receive the following error message in report, you'll probably have to reset the Kerberos account password:</span></span>
    
    <span data-ttu-id="c78ca-143">InvalidKerberosConfiguration: la configuración de Kerberos no es válida.</span><span class="sxs-lookup"><span data-stu-id="c78ca-143">InvalidKerberosConfiguration: The Kerberos configuration is invalid.</span></span>
    
    <span data-ttu-id="c78ca-144">InvalidKerberosConfiguration: la configuración de Kerberos en atl-cs001.litwareinc.com no es válida.</span><span class="sxs-lookup"><span data-stu-id="c78ca-144">InvalidKerberosConfiguration: The Kerberos configuration on atl-cs001.litwareinc.com is invalid.</span></span> <span data-ttu-id="c78ca-145">La cuenta asignada esperada es litwareinc \\ kerberostest.</span><span class="sxs-lookup"><span data-stu-id="c78ca-145">The expected assigned account is litwareinc\\kerberostest.</span></span> <span data-ttu-id="c78ca-146">Asegúrese de que la cuenta no ha expirado y de que la contraseña configurada en el equipo coincida con la contraseña de Active Directory de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="c78ca-146">Ensure that the account has not expired, and the configured password on the machine matches the Active Directory password of the account.</span></span>
    
    <span data-ttu-id="c78ca-147">Puede establecer la contraseña con el cmdlet [set-CsKerberosAccountPassword](https://technet.microsoft.com/library/Gg398659(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="c78ca-147">You can set the password using the [Set-CsKerberosAccountPassword](https://technet.microsoft.com/library/Gg398659(v=OCS.15)) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

