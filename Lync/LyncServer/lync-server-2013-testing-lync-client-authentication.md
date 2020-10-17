---
title: 'Lync Server 2013: prueba de la autenticación de cliente de Lync'
description: 'Lync Server 2013: prueba de la autenticación de cliente de Lync.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Lync Client authentication
ms:assetid: e22114cb-4456-4e5f-93ab-51592c4a8209
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689120(v=OCS.15)
ms:contentKeyID: 63969659
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03694b7fd56d7847d8d493304b97af335d2a5b4d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560586"
---
# <a name="testing-lync-client-authentication-in-lync-server-2013"></a><span data-ttu-id="6154d-103">Probar la autenticación de clientes de Lync en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6154d-103">Testing Lync Client authentication in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6154d-104">_**Última modificación del tema:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="6154d-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6154d-105">Programación de comprobación</span><span class="sxs-lookup"><span data-stu-id="6154d-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="6154d-106">Diario</span><span class="sxs-lookup"><span data-stu-id="6154d-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6154d-107">Herramienta de prueba</span><span class="sxs-lookup"><span data-stu-id="6154d-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="6154d-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6154d-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6154d-109">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="6154d-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="6154d-110">Cuando se ejecuta de forma local mediante el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="6154d-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="6154d-111">Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet Test-CsClientAuth.</span><span class="sxs-lookup"><span data-stu-id="6154d-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsClientAuth cmdlet.</span></span> <span data-ttu-id="6154d-112">Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="6154d-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsClientAuth&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="6154d-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="6154d-113">Description</span></span>

<span data-ttu-id="6154d-114">El cmdlet Test-CsClientAuth le permite determinar si un usuario puede iniciar sesión en el servidor Lync con un certificado de cliente, puede ejecutar el cmdlet Test-CsClientAuth.</span><span class="sxs-lookup"><span data-stu-id="6154d-114">The Test-CsClientAuth cmdlet enables you to determine whether a user can log on to the Lync Server by using a client certificate, you can run the Test-CsClientAuth cmdlet.</span></span> <span data-ttu-id="6154d-115">Después de llamar a Test-CsClientAuth, el cmdlet se pondrá en contacto con el servicio de aprovisionamiento de certificados y pedirá descargar una copia de certificados de cliente para el usuario especificado.</span><span class="sxs-lookup"><span data-stu-id="6154d-115">After calling Test-CsClientAuth, the cmdlet will contact the certificate provisioning service and download a copy of any client certificates for the specified user.</span></span> <span data-ttu-id="6154d-116">Si se puede encontrar y descargar un certificado de cliente, Test-CsClientAuth intentará iniciar sesión con ese certificado.</span><span class="sxs-lookup"><span data-stu-id="6154d-116">If a client certificate can be found and downloaded, Test-CsClientAuth will then attempt to log on by using that certificate.</span></span> <span data-ttu-id="6154d-117">Si el inicio de sesión se completa satisfactoriamente, Test-CsClientAuth cerrará la sesión e informará que la prueba ha sido satisfactoria.</span><span class="sxs-lookup"><span data-stu-id="6154d-117">If logon succeeds, Test-CsClientAuth will log off and report that the test succeeded.</span></span> <span data-ttu-id="6154d-118">Si no se puede encontrar o descargar un certificado o si el cmdlet no puede iniciar sesión con este certificado, Test-CsClientAuth informará que se ha producido un error en la prueba.</span><span class="sxs-lookup"><span data-stu-id="6154d-118">If a certificate cannot be found or downloaded, or if the cmdlet is unable to logon using that certificate, then Test-CsClientAuth will report that the test failed.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="6154d-119">Ejecutar la prueba</span><span class="sxs-lookup"><span data-stu-id="6154d-119">Running the test</span></span>

<span data-ttu-id="6154d-120">El cmdlet Test-CsClientAuth se ejecuta con la cuenta de cualquier usuario que esté habilitado para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6154d-120">The Test-CsClientAuth cmdlet is run by using the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="6154d-121">Para ejecutar esta comprobación con una cuenta de usuario real, primero debe crear un objeto de credenciales de Windows PowerShell que contenga el nombre y la contraseña de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="6154d-121">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="6154d-122">A continuación, debe incluir ese objeto Credentials y la dirección SIP asignada a la cuenta cuando el sistema llame a test-CsClientAuth:</span><span class="sxs-lookup"><span data-stu-id="6154d-122">You must then include that credentials object and the SIP address assigned to the account when the system calls Test-CsClientAuth:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsClientAuth -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="6154d-123">Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsClientAuth](https://technet.microsoft.com/library/gg398712\(v=ocs.14\).aspx) .</span><span class="sxs-lookup"><span data-stu-id="6154d-123">For more information, see the Help documentation for the [Test-CsClientAuth](https://technet.microsoft.com/library/gg398712\(v=ocs.14\).aspx) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="6154d-124">Determinar si se ha realizado correctamente o erróneo</span><span class="sxs-lookup"><span data-stu-id="6154d-124">Determining success or failure</span></span>

<span data-ttu-id="6154d-125">Si el usuario especificado puede iniciar sesión en Lync Server con un certificado de cliente, recibirá una salida similar a la siguiente y la propiedad result se marcará como **correcta:**</span><span class="sxs-lookup"><span data-stu-id="6154d-125">If the specified user can log on to Lync Server by using a client certificate, you will receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="6154d-126">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="6154d-126">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="6154d-127">Resultado: correcto</span><span class="sxs-lookup"><span data-stu-id="6154d-127">Result : Success</span></span>

<span data-ttu-id="6154d-128">Latencia: 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="6154d-128">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="6154d-129">Error</span><span class="sxs-lookup"><span data-stu-id="6154d-129">Error :</span></span>

<span data-ttu-id="6154d-130">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="6154d-130">Diagnosis :</span></span>

<span data-ttu-id="6154d-131">Si el usuario especificado no puede iniciar sesión, el resultado se mostrará como error y la información adicional se registrará en las propiedades error y diagnosis:</span><span class="sxs-lookup"><span data-stu-id="6154d-131">If the specified user can not log on, the Result will be shown as Failure and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="6154d-132">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="6154d-132">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="6154d-133">Resultado: error</span><span class="sxs-lookup"><span data-stu-id="6154d-133">Result : Failure</span></span>

<span data-ttu-id="6154d-134">Latencia: 00:00:03.3645259</span><span class="sxs-lookup"><span data-stu-id="6154d-134">Latency : 00:00:03.3645259</span></span>

<span data-ttu-id="6154d-135">Error: no se pudo descargar un certificado CS para el usuario especificado.</span><span class="sxs-lookup"><span data-stu-id="6154d-135">Error : Could not download a CS Certificate for the given user.</span></span> <span data-ttu-id="6154d-136">Compruebe si</span><span class="sxs-lookup"><span data-stu-id="6154d-136">Check if</span></span>

<span data-ttu-id="6154d-137">el URI y las credenciales proporcionados son correctos.</span><span class="sxs-lookup"><span data-stu-id="6154d-137">provided uri and credentials are correct.</span></span>

<span data-ttu-id="6154d-138">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="6154d-138">Diagnosis :</span></span>

<span data-ttu-id="6154d-139">Por ejemplo, la salida anterior indica que se produjo un error en la prueba porque no se encontró un certificado de cliente válido para el usuario especificado.</span><span class="sxs-lookup"><span data-stu-id="6154d-139">For example, the previous output states that the test failed because a valid client certificate couldn't be located for the specified user.</span></span> <span data-ttu-id="6154d-140">Puede devolver una lista de los certificados de cliente emitidos a un usuario mediante la ejecución de un comando de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="6154d-140">You can return a list of the client certificates issued to a user by running a command as follows:</span></span>

    Get-CsClientCertificate -Identity "sip:kenmyer@litwareinc.com"

<span data-ttu-id="6154d-141">Si Test-CsClientAuth da error, es posible que desee volver a ejecutar la prueba, pero esta vez incluya el parámetro verbose:</span><span class="sxs-lookup"><span data-stu-id="6154d-141">If Test-CsClientAuth fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsClientAuth -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential -Verbose

<span data-ttu-id="6154d-142">Cuando se incluye el parámetro verbose, Test-CsClientAuth devolverá una cuenta paso a paso por cada acción que se intentó realizar cuando se comprobó la capacidad del usuario especificado para iniciar sesión en Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6154d-142">When the Verbose parameter is included, Test-CsClientAuth will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="6154d-143">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="6154d-143">For example:</span></span>

<span data-ttu-id="6154d-144">Se está intentando descargar un certificado CS para el usuario: kenmyer@litwareinc.com Endpoint: STEpid</span><span class="sxs-lookup"><span data-stu-id="6154d-144">Trying to download a CS certificate for User : kenmyer@litwareinc.com endpoint : STEpid</span></span>

<span data-ttu-id="6154d-145">Dirección URL del servicio Web: https://atl-cs-001.litwareinc.com:443/CertProv/CertprovisioningService.svc</span><span class="sxs-lookup"><span data-stu-id="6154d-145">Web Service url : https://atl-cs-001.litwareinc.com:443/CertProv/CertprovisioningService.svc</span></span>

<span data-ttu-id="6154d-146">No se pudo descargar un certificado CS del servicio Web.</span><span class="sxs-lookup"><span data-stu-id="6154d-146">Could not download a CS certificate from web service.</span></span>

<span data-ttu-id="6154d-147">SILLA</span><span class="sxs-lookup"><span data-stu-id="6154d-147">CHECK:</span></span>

<span data-ttu-id="6154d-148">\- La URL del servicio web es válida y los servicios web son funcionales</span><span class="sxs-lookup"><span data-stu-id="6154d-148">\- Web service url is valid and the web services are functional</span></span>

<span data-ttu-id="6154d-149">\-Si usa PhoneNo \\ \\ PIN para autenticarse, asegúrese de que coinciden con el URI de usuario</span><span class="sxs-lookup"><span data-stu-id="6154d-149">\- If using PhoneNo\\\\Pin to authenticate, make sure they match the user uri</span></span>

<span data-ttu-id="6154d-150">\- Si se usa la \\ autenticación Kerberos NTLM, asegúrese de que ha proporcionado credenciales válidas</span><span class="sxs-lookup"><span data-stu-id="6154d-150">\- If using NTLM\\Kerberos auth, make sure you provided valid credentials</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="6154d-151">Motivos por los que se ha producido un error en la prueba</span><span class="sxs-lookup"><span data-stu-id="6154d-151">Reasons why the test might have failed</span></span>

<span data-ttu-id="6154d-152">Estas son algunas de las razones comunes por las que Test-CsClientAuth podría producir un error:</span><span class="sxs-lookup"><span data-stu-id="6154d-152">Here are some common reasons why Test-CsClientAuth might fail:</span></span>

  - <span data-ttu-id="6154d-153">Ha especificado una cuenta de usuario que no es válida.</span><span class="sxs-lookup"><span data-stu-id="6154d-153">You specified a user account that was not valid.</span></span> <span data-ttu-id="6154d-154">Puede comprobar si existe una cuenta de usuario mediante la ejecución de un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="6154d-154">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="6154d-155">La cuenta de usuario es válida, pero la cuenta no está habilitada actualmente para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6154d-155">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="6154d-156">Para comprobar que una cuenta de usuario está habilitada para Lync Server, ejecute un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="6154d-156">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="6154d-157">Si la propiedad Enabled se establece en false, significa que el usuario no está habilitado actualmente para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6154d-157">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="6154d-158">Es posible que el usuario de prueba no tenga un certificado de cliente válido.</span><span class="sxs-lookup"><span data-stu-id="6154d-158">The test user might not have a valid client certificate.</span></span> <span data-ttu-id="6154d-159">Puede devolver información sobre los certificados de cliente asignados a un usuario mediante un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="6154d-159">You can return information about the client certificates assigned to a user by using a command similar to this:</span></span>
    
        Get-CsClientCertificate -Identity "sip:kenmyer@litwareinc.com"

</div>

</div>

<span> </span>

</div>

</div>

</div>

