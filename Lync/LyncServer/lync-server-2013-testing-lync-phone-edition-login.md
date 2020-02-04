---
title: 'Lync Server 2013: Inicio de sesión de Lync Phone Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Lync Phone Edition login
ms:assetid: 1ccde6bf-9a2d-4fcf-b81f-1bc9fee2cfbb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690128(v=OCS.15)
ms:contentKeyID: 63969583
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3bfce8b1e034fd9772e10178366b0ed524fdbd55
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745670"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-lync-phone-edition-login-in-lync-server-2013"></a><span data-ttu-id="1fd22-102">Probar el inicio de sesión de Lync Phone Edition en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1fd22-102">Testing Lync Phone Edition login in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1fd22-103">_**Última modificación del tema:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="1fd22-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1fd22-104">Programación de verificación</span><span class="sxs-lookup"><span data-stu-id="1fd22-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="1fd22-105">Cada día</span><span class="sxs-lookup"><span data-stu-id="1fd22-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1fd22-106">Herramienta de prueba</span><span class="sxs-lookup"><span data-stu-id="1fd22-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="1fd22-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1fd22-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1fd22-108">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="1fd22-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="1fd22-109">Al ejecutarse de forma local con el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="1fd22-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="1fd22-110">Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol de RBAC que tenga permiso para ejecutar el cmdlet test-CsPhoneBootstrap.</span><span class="sxs-lookup"><span data-stu-id="1fd22-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsPhoneBootstrap cmdlet.</span></span> <span data-ttu-id="1fd22-111">Para ver una lista de todos los roles de RBAC que pueden usar este cmdlet, ejecute el siguiente comando en el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="1fd22-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPhoneBootstrap&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="1fd22-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="1fd22-112">Description</span></span>

<span data-ttu-id="1fd22-113">El cmdlet test-CsPhoneBootstrap permite a los administradores comprobar que un usuario determinado (con el número de teléfono y el PIN que le ha asignado) puede iniciar sesión en el sistema desde un dispositivo compatible con Lync 2013 Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="1fd22-113">The Test-CsPhoneBootstrap cmdlet enables administrators to verify that a given user—using the phone number and PIN assigned to him or her—can log on to the system from a Lync 2013 Phone Edition-compatible device.</span></span> <span data-ttu-id="1fd22-114">(En realidad, no se necesita ningún dispositivo para ejecutar la prueba).</span><span class="sxs-lookup"><span data-stu-id="1fd22-114">(No device is actually needed to run the test.)</span></span>

<span data-ttu-id="1fd22-115">Para que la prueba CsPhoneBootstrap realice su comprobación, el grupo registrador que hospeda la cuenta de usuario que se está probando debe ser reconocible con DHCP.</span><span class="sxs-lookup"><span data-stu-id="1fd22-115">In order for Test-CsPhoneBootstrap to make its check, the Registrar pool that hosts the user account being tested must be discoverable using DHCP.</span></span> <span data-ttu-id="1fd22-116">Para determinar si un registrador es reconocible de esta manera, use el cmdlet Get-CsRegistrarConfiguration y compruebe el valor de la propiedad EnableDHCPServer.</span><span class="sxs-lookup"><span data-stu-id="1fd22-116">To determine whether a Registrar is discoverable in this manner, use the cmdlet Get-CsRegistrarConfiguration and check the value of the EnableDHCPServer property.</span></span> <span data-ttu-id="1fd22-117">Si esta propiedad se establece en false, debe usar Set-CsRegistrarConfiguration para establecer el valor de la propiedad en true y hacer que el registrador se pueda detectar mediante DHCP.</span><span class="sxs-lookup"><span data-stu-id="1fd22-117">If this property is set to False, you must use Set-CsRegistrarConfiguration to set the property value to True and make the Registrar discoverable using DHCP.</span></span> <span data-ttu-id="1fd22-118">Esto también se puede realizar mediante el servidor DHCP empresarial y la configuración de las opciones específicas de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1fd22-118">This can also be done by using Enterprise DHCP Server and configuring the Lync Server-specific options.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="1fd22-119">Ejecutar la prueba</span><span class="sxs-lookup"><span data-stu-id="1fd22-119">Running the test</span></span>

<span data-ttu-id="1fd22-120">Para ejecutar el cmdlet test-CsPhoneBootstrap, debe proporcionar, como mínimo, el número de teléfono y el número de identificación personal del cliente (PIN) para un usuario de Lync Server válido.</span><span class="sxs-lookup"><span data-stu-id="1fd22-120">To run the Test-CsPhoneBootstrap cmdlet, you must, at a minimum, supply the phone number and client personal identification number (PIN) for a valid Lync Server user.</span></span> <span data-ttu-id="1fd22-121">Por ejemplo, este comando prueba la capacidad de inicio de sesión para el usuario que tiene el número de teléfono 12065551219 y el PIN 0712:</span><span class="sxs-lookup"><span data-stu-id="1fd22-121">For example, this command tests the logon ability for the user who has the phone number 12065551219 and the PIN 0712:</span></span>

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712"

<span data-ttu-id="1fd22-122">Para una comprobación más completa, también puedes incluir la dirección SIP del usuario.</span><span class="sxs-lookup"><span data-stu-id="1fd22-122">For a more comprehensive check, you can also include the user’s SIP address.</span></span> <span data-ttu-id="1fd22-123">En ese caso, el número de teléfono, el PIN del cliente y la dirección SIP deben ser válidos para que la prueba se realice correctamente:</span><span class="sxs-lookup"><span data-stu-id="1fd22-123">In that case, the phone number, client PIN, and SIP address must all be valid for the test to succeed:</span></span>

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712" -UserSipAddress "sip:kenmyer@litwareinc.com"

<span data-ttu-id="1fd22-124">Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsPhoneBootstrap](https://docs.microsoft.com/powershell/module/skype/Test-CsPhoneBootstrap) .</span><span class="sxs-lookup"><span data-stu-id="1fd22-124">For more information, see the Help documentation for the [Test-CsPhoneBootstrap](https://docs.microsoft.com/powershell/module/skype/Test-CsPhoneBootstrap) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="1fd22-125">Determinar el éxito o el fracaso</span><span class="sxs-lookup"><span data-stu-id="1fd22-125">Determining success or failure</span></span>

<span data-ttu-id="1fd22-126">Si el usuario especificado pudo conectarse a Lync Server, recibirá un resultado similar a este, con la propiedad result marcada como **correcta:**</span><span class="sxs-lookup"><span data-stu-id="1fd22-126">If the specified user was able to connect to Lync Server, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="1fd22-127">TargetUrihttps://atl-cs-001.litwareinc.com:443/CertProv/</span><span class="sxs-lookup"><span data-stu-id="1fd22-127">TargetUri : https://atl-cs-001.litwareinc.com:443/CertProv/</span></span>

<span data-ttu-id="1fd22-128">CertProvisioningService. SVC</span><span class="sxs-lookup"><span data-stu-id="1fd22-128">CertProvisioningService.svc</span></span>

<span data-ttu-id="1fd22-129">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="1fd22-129">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="1fd22-130">Resultado: éxito</span><span class="sxs-lookup"><span data-stu-id="1fd22-130">Result : Success</span></span>

<span data-ttu-id="1fd22-131">Latencia: 00:00:06.3981276</span><span class="sxs-lookup"><span data-stu-id="1fd22-131">Latency : 00:00:06.3981276</span></span>

<span data-ttu-id="1fd22-132">:</span><span class="sxs-lookup"><span data-stu-id="1fd22-132">Error :</span></span>

<span data-ttu-id="1fd22-133">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="1fd22-133">Diagnosis :</span></span>

<span data-ttu-id="1fd22-134">Si el usuario especificado no pudo establecer una conexión, el resultado se mostrará como error y la información adicional se registrará en las propiedades de diagnóstico y errores:</span><span class="sxs-lookup"><span data-stu-id="1fd22-134">If the specified user was not able to make a connection, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="1fd22-135">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="1fd22-135">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="1fd22-136">Resultado: error</span><span class="sxs-lookup"><span data-stu-id="1fd22-136">Result : Failure</span></span>

<span data-ttu-id="1fd22-137">Latencia: 00:00:04.1993845</span><span class="sxs-lookup"><span data-stu-id="1fd22-137">Latency : 00:00:04.1993845</span></span>

<span data-ttu-id="1fd22-138">Error: no se recibió ninguna respuesta para el servicio de vales Web.</span><span class="sxs-lookup"><span data-stu-id="1fd22-138">Error : ERROR - No response received for Web-Ticket service.</span></span>

<span data-ttu-id="1fd22-139">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="1fd22-139">Diagnosis :</span></span>

<span data-ttu-id="1fd22-140">El resultado anterior indica que no se pudo realizar la prueba porque el servicio de vales web no respondió.</span><span class="sxs-lookup"><span data-stu-id="1fd22-140">The previous output states that the test failed because the Web Ticket service did not respond.</span></span> <span data-ttu-id="1fd22-141">Esto puede deberse a un problema con el servicio, o puede deberse a la dirección SIP, el número de teléfono o el PIN del cliente que se pasa a test-CsPhoneBootstrap.</span><span class="sxs-lookup"><span data-stu-id="1fd22-141">This could be due to a problem with the service itself, or it might be due to the SIP address, phone number, or client PIN passed to Test-CsPhoneBootstrap.</span></span> <span data-ttu-id="1fd22-142">Puede comprobar la dirección SIP y el número de teléfono del usuario con un comando parecido a este:</span><span class="sxs-lookup"><span data-stu-id="1fd22-142">You can verify the user’s SIP address and phone number by using a command similar to this one:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, LineUri

<span data-ttu-id="1fd22-143">Y puede comprobar que el usuario tiene un PIN válido con un comando de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="1fd22-143">And you can verify that the user has a valid PIN by using a command as follows:</span></span>

    Get-CsClientPinInfo -Identity "sip:kenmyer@litwareinc.com" 

<span data-ttu-id="1fd22-144">Si prueba-CsPhoneBootstrap da error, es posible que desee volver a ejecutar la prueba, esta vez incluido el parámetro detallado:</span><span class="sxs-lookup"><span data-stu-id="1fd22-144">If Test-CsPhoneBootstrap fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsPhoneBootstrap -PhoneOrExt "+12065551219" -Pin "0712" -Verbose

<span data-ttu-id="1fd22-145">Cuando se incluye el parámetro detallado, test-CsPhoneBootstrap devolverá una cuenta paso a paso de cada acción que se probó cuando se comprobó la capacidad del usuario especificado para iniciar sesión en Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1fd22-145">When the Verbose parameter is included, Test-CsPhoneBootstrap will return a step-by-step account of each action it tried when it checked the ability of the specified user to log on to Lync Server.</span></span> <span data-ttu-id="1fd22-146">Por ejemplo, a continuación se muestra una parte de la salida de un inicio de sesión incorrecto, una sesión en la que se incluyó un PIN incorrecto:</span><span class="sxs-lookup"><span data-stu-id="1fd22-146">For example, here is a portion of the output for an unsuccessful logon, a session in which an incorrect PIN was included:</span></span>

<span data-ttu-id="1fd22-147">Usar la autenticación del PIN\\con ext. de teléfono: 12065551219 pin: 0712</span><span class="sxs-lookup"><span data-stu-id="1fd22-147">Using PIN auth with Phone\\Ext : 12065551219 Pin : 0712</span></span>

<span data-ttu-id="1fd22-148">No se pudo obtener el vale Web</span><span class="sxs-lookup"><span data-stu-id="1fd22-148">Could not get web ticket</span></span>

<span data-ttu-id="1fd22-149">Si</span><span class="sxs-lookup"><span data-stu-id="1fd22-149">CHECK :</span></span>

<span data-ttu-id="1fd22-150">\-La dirección URL del servicio web es válida y los servicios web son funcionales</span><span class="sxs-lookup"><span data-stu-id="1fd22-150">\- Web service url is valid and the web services are functional</span></span>

<span data-ttu-id="1fd22-151">\-Si usas PhoneNo\\PIN para autenticar, asegúrate de que coincidan con el URI de usuario.</span><span class="sxs-lookup"><span data-stu-id="1fd22-151">\- If using PhoneNo\\PIN to authenticate, make sure they match the user uri</span></span>

<span data-ttu-id="1fd22-152">\-Si usa NTLM\\Kerberos auth, asegúrese de que ha proporcionado credenciales válidas</span><span class="sxs-lookup"><span data-stu-id="1fd22-152">\- If using NTLM\\Kerberos auth, make sure you provided valid credentials</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="1fd22-153">Razones por las que se ha producido un error en la prueba</span><span class="sxs-lookup"><span data-stu-id="1fd22-153">Reasons why the test might have failed</span></span>

<span data-ttu-id="1fd22-154">Estas son algunas de las razones comunes por las que test-CsPhoneBootstrap podría fallar:</span><span class="sxs-lookup"><span data-stu-id="1fd22-154">Here are some common reasons why Test-CsPhoneBootstrap might fail:</span></span>

  - <span data-ttu-id="1fd22-155">Es posible que haya especificado una dirección SIP que no sea válida.</span><span class="sxs-lookup"><span data-stu-id="1fd22-155">You might have specified a SIP address that is not valid.</span></span> <span data-ttu-id="1fd22-156">Puede comprobar que una dirección SIP es correcta usando un comando como este:</span><span class="sxs-lookup"><span data-stu-id="1fd22-156">You can verify that a SIP address is correct by using a command such as this one:</span></span>
    
        Get-CsUser -Identity "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="1fd22-157">Es posible que haya especificado un PIN no válido.</span><span class="sxs-lookup"><span data-stu-id="1fd22-157">You might have specified a PIN that is not valid.</span></span> <span data-ttu-id="1fd22-158">Aunque no puede recuperar el número PIN del usuario, puede comprobar que el usuario, como mínimo, tiene un número PIN con un comando parecido a este:</span><span class="sxs-lookup"><span data-stu-id="1fd22-158">Although you can't retrieve the user’s PIN number, you can verify that the user at least has a PIN number by using a command similar to this:</span></span>
    
        Get-CsClientPinInfo -Identity "sip:kenmyer@litwareinc.com"

  - <span data-ttu-id="1fd22-159">Es posible que haya especificado un número de teléfono no válido.</span><span class="sxs-lookup"><span data-stu-id="1fd22-159">You might have specified a phone number that is not valid.</span></span> <span data-ttu-id="1fd22-160">Puede comprobar el teléfono de un usuario con un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="1fd22-160">You can verify a user’s phone by using a command similar to the following:</span></span>
    
        Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object LineUri

  - <span data-ttu-id="1fd22-161">El grupo de registradores no está habilitado para DHCP.</span><span class="sxs-lookup"><span data-stu-id="1fd22-161">The Registrar pool is not DHCP-enabled.</span></span> <span data-ttu-id="1fd22-162">Para determinar si su grupo de registradores está habilitado para DHCP, ejecute el cmdlet Get-CsRegistrarConfiguration y compruebe el valor de la propiedad EnableDHCPServer.</span><span class="sxs-lookup"><span data-stu-id="1fd22-162">To determine whether your Registrar pool is enabled for DHCP, run the Get-CsRegistrarConfiguration cmdlet and check the value of the EnableDHCPServer property.</span></span> <span data-ttu-id="1fd22-163">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="1fd22-163">For example:</span></span>
    
        Get-CsRegistrarConfiguration -Identity "global"

</div>

</div>

<span> </span>

</div>

</div>

</div>

