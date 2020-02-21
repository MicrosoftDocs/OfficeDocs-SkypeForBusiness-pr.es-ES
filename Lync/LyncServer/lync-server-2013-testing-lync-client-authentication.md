---
title: 'Lync Server 2013: prueba de la autenticación de cliente de Lync'
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
ms.openlocfilehash: 490068a9c9eec3e582471d9ff228b9bbccad43bf
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194093"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-lync-client-authentication-in-lync-server-2013"></a><span data-ttu-id="649e1-102">Probar la autenticación de clientes de Lync en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="649e1-102">Testing Lync Client authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="649e1-103">_**Última modificación del tema:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="649e1-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="649e1-104">Programación de comprobación</span><span class="sxs-lookup"><span data-stu-id="649e1-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="649e1-105">Diario</span><span class="sxs-lookup"><span data-stu-id="649e1-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="649e1-106">Herramienta de prueba</span><span class="sxs-lookup"><span data-stu-id="649e1-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="649e1-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="649e1-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="649e1-108">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="649e1-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="649e1-109">Cuando se ejecuta de forma local mediante el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="649e1-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="649e1-110">Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet test-CsClientAuth.</span><span class="sxs-lookup"><span data-stu-id="649e1-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsClientAuth cmdlet.</span></span> <span data-ttu-id="649e1-111">Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="649e1-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsClientAuth&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="649e1-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="649e1-112">Description</span></span>

<span data-ttu-id="649e1-113">El cmdlet test-CsClientAuth le permite determinar si un usuario puede iniciar sesión en Lync Server con un certificado de cliente, puede ejecutar el cmdlet test-CsClientAuth.</span><span class="sxs-lookup"><span data-stu-id="649e1-113">The Test-CsClientAuth cmdlet enables you to determine whether a user can log on to the Lync Server by using a client certificate, you can run the Test-CsClientAuth cmdlet.</span></span> <span data-ttu-id="649e1-114">Después de llamar a Test-CsClientAuth, el cmdlet se pondrá en contacto con el servicio de aprovisionamiento de certificados y pedirá descargar una copia de certificados de cliente para el usuario especificado.</span><span class="sxs-lookup"><span data-stu-id="649e1-114">After calling Test-CsClientAuth, the cmdlet will contact the certificate provisioning service and download a copy of any client certificates for the specified user.</span></span> <span data-ttu-id="649e1-115">Si se puede encontrar y descargar un certificado de cliente, test-CsClientAuth intentará iniciar sesión con ese certificado.</span><span class="sxs-lookup"><span data-stu-id="649e1-115">If a client certificate can be found and downloaded, Test-CsClientAuth will then attempt to log on by using that certificate.</span></span> <span data-ttu-id="649e1-116">Si el inicio de sesión se completa satisfactoriamente, Test-CsClientAuth cerrará la sesión e informará que la prueba ha sido satisfactoria.</span><span class="sxs-lookup"><span data-stu-id="649e1-116">If logon succeeds, Test-CsClientAuth will log off and report that the test succeeded.</span></span> <span data-ttu-id="649e1-117">Si no se puede encontrar o descargar un certificado o si el cmdlet no puede iniciar sesión con este certificado, Test-CsClientAuth informará que se ha producido un error en la prueba.</span><span class="sxs-lookup"><span data-stu-id="649e1-117">If a certificate cannot be found or downloaded, or if the cmdlet is unable to logon using that certificate, then Test-CsClientAuth will report that the test failed.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="649e1-118">Ejecutar la prueba</span><span class="sxs-lookup"><span data-stu-id="649e1-118">Running the test</span></span>

<span data-ttu-id="649e1-119">El cmdlet test-CsClientAuth se ejecuta con la cuenta de cualquier usuario que esté habilitado para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="649e1-119">The Test-CsClientAuth cmdlet is run by using the account of any user who is enabled for Lync Server.</span></span> <span data-ttu-id="649e1-120">Para ejecutar esta comprobación con una cuenta de usuario real, primero debe crear un objeto de credenciales de Windows PowerShell que contenga el nombre y la contraseña de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="649e1-120">To run this check using an actual user account, you must first create a Windows PowerShell credentials object that contains the account name and password.</span></span> <span data-ttu-id="649e1-121">A continuación, debe incluir ese objeto Credentials y la dirección SIP asignada a la cuenta cuando el sistema llame a test-CsClientAuth:</span><span class="sxs-lookup"><span data-stu-id="649e1-121">You must then include that credentials object and the SIP address assigned to the account when the system calls Test-CsClientAuth:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsClientAuth -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

<span data-ttu-id="649e1-122">Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsClientAuth](https://technet.microsoft.com/library/gg398712\(v=ocs.14\).aspx) .</span><span class="sxs-lookup"><span data-stu-id="649e1-122">For more information, see the Help documentation for the [Test-CsClientAuth](https://technet.microsoft.com/library/gg398712\(v=ocs.14\).aspx) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="649e1-123">Determinar si se ha realizado correctamente o erróneo</span><span class="sxs-lookup"><span data-stu-id="649e1-123">Determining success or failure</span></span>

<span data-ttu-id="649e1-124">Si el usuario especificado puede iniciar sesión en Lync Server con un certificado de cliente, recibirá una salida similar a la siguiente y la propiedad result se marcará como **correcta:**</span><span class="sxs-lookup"><span data-stu-id="649e1-124">If the specified user can log on to Lync Server by using a client certificate, you will receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="649e1-125">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="649e1-125">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="649e1-126">Resultado: correcto</span><span class="sxs-lookup"><span data-stu-id="649e1-126">Result : Success</span></span>

<span data-ttu-id="649e1-127">Latencia: 00:00:06.8630376</span><span class="sxs-lookup"><span data-stu-id="649e1-127">Latency : 00:00:06.8630376</span></span>

<span data-ttu-id="649e1-128">Error</span><span class="sxs-lookup"><span data-stu-id="649e1-128">Error :</span></span>

<span data-ttu-id="649e1-129">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="649e1-129">Diagnosis :</span></span>

<span data-ttu-id="649e1-130">Si el usuario especificado no puede iniciar sesión, el resultado se mostrará como error y la información adicional se registrará en las propiedades error y diagnosis:</span><span class="sxs-lookup"><span data-stu-id="649e1-130">If the specified user can not log on, the Result will be shown as Failure and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="649e1-131">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="649e1-131">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="649e1-132">Resultado: error</span><span class="sxs-lookup"><span data-stu-id="649e1-132">Result : Failure</span></span>

<span data-ttu-id="649e1-133">Latencia: 00:00:03.3645259</span><span class="sxs-lookup"><span data-stu-id="649e1-133">Latency : 00:00:03.3645259</span></span>

<span data-ttu-id="649e1-134">Error: no se pudo descargar un certificado CS para el usuario especificado.</span><span class="sxs-lookup"><span data-stu-id="649e1-134">Error : Could not download a CS Certificate for the given user.</span></span> <span data-ttu-id="649e1-135">Compruebe si</span><span class="sxs-lookup"><span data-stu-id="649e1-135">Check if</span></span>

<span data-ttu-id="649e1-136">el URI y las credenciales proporcionados son correctos.</span><span class="sxs-lookup"><span data-stu-id="649e1-136">provided uri and credentials are correct.</span></span>

<span data-ttu-id="649e1-137">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="649e1-137">Diagnosis :</span></span>

<span data-ttu-id="649e1-138">Por ejemplo, la salida anterior indica que se produjo un error en la prueba porque no se encontró un certificado de cliente válido para el usuario especificado.</span><span class="sxs-lookup"><span data-stu-id="649e1-138">For example, the previous output states that the test failed because a valid client certificate couldn't be located for the specified user.</span></span> <span data-ttu-id="649e1-139">Puede devolver una lista de los certificados de cliente emitidos a un usuario mediante la ejecución de un comando de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="649e1-139">You can return a list of the client certificates issued to a user by running a command as follows:</span></span>

    Get-CsClientCertificate -Identity "sip:kenmyer@litwareinc.com"

<span data-ttu-id="649e1-140">Si test-CsClientAuth produce un error, es posible que desee volver a ejecutar la prueba, pero esta vez incluya el parámetro verbose:</span><span class="sxs-lookup"><span data-stu-id="649e1-140">If Test-CsClientAuth fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsClientAuth -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential -Verbose

<span data-ttu-id="649e1-141">Cuando se incluye el parámetro verbose, test-CsClientAuth devolverá una cuenta paso a paso de cada acción que se intentó realizar cuando se comprobó la capacidad del usuario especificado para iniciar sesión en Lync Server.</span><span class="sxs-lookup"><span data-stu-id="649e1-141">When the Verbose parameter is included, Test-CsClientAuth will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="649e1-142">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="649e1-142">For example:</span></span>

<span data-ttu-id="649e1-143">Se está intentando descargar un certificado CS para el usuario: kenmyer@litwareinc.com Endpoint: STEpid</span><span class="sxs-lookup"><span data-stu-id="649e1-143">Trying to download a CS certificate for User : kenmyer@litwareinc.com endpoint : STEpid</span></span>

<span data-ttu-id="649e1-144">Dirección URL del servicio Web:https://atl-cs-001.litwareinc.com:443/CertProv/CertprovisioningService.svc</span><span class="sxs-lookup"><span data-stu-id="649e1-144">Web Service url : https://atl-cs-001.litwareinc.com:443/CertProv/CertprovisioningService.svc</span></span>

<span data-ttu-id="649e1-145">No se pudo descargar un certificado CS del servicio Web.</span><span class="sxs-lookup"><span data-stu-id="649e1-145">Could not download a CS certificate from web service.</span></span>

<span data-ttu-id="649e1-146">SILLA</span><span class="sxs-lookup"><span data-stu-id="649e1-146">CHECK:</span></span>

<span data-ttu-id="649e1-147">\-La URL del servicio web es válida y los servicios web son funcionales</span><span class="sxs-lookup"><span data-stu-id="649e1-147">\- Web service url is valid and the web services are functional</span></span>

<span data-ttu-id="649e1-148">\-Si usa PhoneNo\\\\PIN para autenticarse, asegúrese de que coinciden con el URI de usuario</span><span class="sxs-lookup"><span data-stu-id="649e1-148">\- If using PhoneNo\\\\Pin to authenticate, make sure they match the user uri</span></span>

<span data-ttu-id="649e1-149">\-Si se usa\\la autenticación Kerberos NTLM, asegúrese de que ha proporcionado credenciales válidas</span><span class="sxs-lookup"><span data-stu-id="649e1-149">\- If using NTLM\\Kerberos auth, make sure you provided valid credentials</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="649e1-150">Motivos por los que se ha producido un error en la prueba</span><span class="sxs-lookup"><span data-stu-id="649e1-150">Reasons why the test might have failed</span></span>

<span data-ttu-id="649e1-151">Estas son algunas de las razones comunes por las que test-CsClientAuth podría fallar:</span><span class="sxs-lookup"><span data-stu-id="649e1-151">Here are some common reasons why Test-CsClientAuth might fail:</span></span>

  - <span data-ttu-id="649e1-152">Ha especificado una cuenta de usuario que no es válida.</span><span class="sxs-lookup"><span data-stu-id="649e1-152">You specified a user account that was not valid.</span></span> <span data-ttu-id="649e1-153">Puede comprobar si existe una cuenta de usuario mediante la ejecución de un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="649e1-153">You can verify that a user account exists by running a command similar to this:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="649e1-154">La cuenta de usuario es válida, pero la cuenta no está habilitada actualmente para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="649e1-154">The user account is valid, but the account is currently not enabled for Lync Server.</span></span> <span data-ttu-id="649e1-155">Para comprobar que una cuenta de usuario está habilitada para Lync Server, ejecute un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="649e1-155">To verify that a user account is enabled for Lync Server, run a command similar to the following:</span></span>
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    <span data-ttu-id="649e1-156">Si la propiedad Enabled se establece en false, significa que el usuario no está habilitado actualmente para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="649e1-156">If the Enabled property is set to False, that means that the user is currently not enabled for Lync Server.</span></span>

  - <span data-ttu-id="649e1-157">Es posible que el usuario de prueba no tenga un certificado de cliente válido.</span><span class="sxs-lookup"><span data-stu-id="649e1-157">The test user might not have a valid client certificate.</span></span> <span data-ttu-id="649e1-158">Puede devolver información sobre los certificados de cliente asignados a un usuario mediante un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="649e1-158">You can return information about the client certificates assigned to a user by using a command similar to this:</span></span>
    
        Get-CsClientCertificate -Identity "sip:kenmyer@litwareinc.com"

</div>

</div>

<span> </span>

</div>

</div>

</div>

