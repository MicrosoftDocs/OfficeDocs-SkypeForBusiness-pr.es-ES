---
title: 'Lync Server 2013: probar el acceso a la aplicación Web'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test Web App access
ms:assetid: 17d67ea3-f74d-4952-ac2b-92c0dacc8014
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767944(v=OCS.15)
ms:contentKeyID: 63969584
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2cdf0c4d974732b75a7ff83022c6bfbf1c4d8e80
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532937"
---
# <a name="test-web-app-access-in-lync-server-2013"></a><span data-ttu-id="0d006-102">Probar el acceso a la aplicación web en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0d006-102">Test Web App access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0d006-103">_**Última modificación del tema:** 2014-06-07_</span><span class="sxs-lookup"><span data-stu-id="0d006-103">_**Topic Last Modified:** 2014-06-07_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0d006-104">Programación de comprobación</span><span class="sxs-lookup"><span data-stu-id="0d006-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="0d006-105">Mensualmente</span><span class="sxs-lookup"><span data-stu-id="0d006-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d006-106">Herramienta de prueba</span><span class="sxs-lookup"><span data-stu-id="0d006-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="0d006-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0d006-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d006-108">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="0d006-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="0d006-109">Cuando se ejecuta de forma local mediante el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="0d006-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="0d006-110">Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet Test-CsWebApp.</span><span class="sxs-lookup"><span data-stu-id="0d006-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsWebApp cmdlet.</span></span> <span data-ttu-id="0d006-111">Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="0d006-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebApp&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="0d006-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="0d006-112">Description</span></span>

<span data-ttu-id="0d006-113">El cmdlet Test-CsWebApp comprueba que los usuarios autenticados pueden unirse a conferencias de Lync Server mediante Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="0d006-113">The Test-CsWebApp cmdlet verifies that authenticated users can join Lync Server conferences by using the Lync Web App.</span></span> <span data-ttu-id="0d006-114">Al ejecutar el cmdlet, Test-CsWebApp se pone en contacto con el servicio de vales web para obtener vales web para los usuarios especificados.</span><span class="sxs-lookup"><span data-stu-id="0d006-114">When you run the cmdlet, Test-CsWebApp contacts the Web Ticket service to obtain web tickets for the specified users.</span></span> <span data-ttu-id="0d006-115">Estos vales actúan efectivamente como "vales de admisión" para la Conferencia de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0d006-115">These tickets effectively act as ‘admission tickets” to the Lync Server conference.</span></span> <span data-ttu-id="0d006-116">Si se pueden recuperar los vales y si los usuarios se pueden autenticar, Test-CsWebApp se pondrá en contacto con Lync Server e intentará establecer conferencias independientes para la mensajería instantánea, el uso compartido de aplicaciones y la colaboración de datos.</span><span class="sxs-lookup"><span data-stu-id="0d006-116">If the tickets can be retrieved, and if the users can be authenticated, Test-CsWebApp will then contact Lync Server and attempt to establish separate conferences for instant messaging, application sharing, and data collaboration.</span></span>

<span data-ttu-id="0d006-117">Tenga en cuenta que Test-CsWebApp solo comprueba las API y las conexiones usadas para crear estas conferencias.</span><span class="sxs-lookup"><span data-stu-id="0d006-117">Note that Test-CsWebApp just verifies the APIs and connections used to create these conferences.</span></span> <span data-ttu-id="0d006-118">El cmdlet está diseñado para comprobar que Lync Web App puede usarse para crear conferencias y unirse a ellas.</span><span class="sxs-lookup"><span data-stu-id="0d006-118">The cmdlet is designed to verify that Lync Web App could be used to create and join conferences.</span></span> <span data-ttu-id="0d006-119">Sin embargo, en realidad no crea y lleva a cabo una conferencia.</span><span class="sxs-lookup"><span data-stu-id="0d006-119">However,, it does not actually create and conduct a conference.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="0d006-120">Ejecutar la prueba</span><span class="sxs-lookup"><span data-stu-id="0d006-120">Running the test</span></span>

<span data-ttu-id="0d006-121">El cmdlet Test-CsWebApp puede ejecutarse con un par de cuentas de prueba preconfiguradas o con las cuentas de dos usuarios que están habilitados para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0d006-121">The Test-CsWebApp cmdlet can be run using either a pair of preconfigured test accounts or the accounts of any two users who are enabled for Lync Server.</span></span> <span data-ttu-id="0d006-122">Para ejecutar esta comprobación mediante cuentas de prueba, solo tiene que especificar el nombre de dominio completo del grupo de Lync Server que se está probando.</span><span class="sxs-lookup"><span data-stu-id="0d006-122">To run this check using test accounts, you just have to specify the fully qualified domain name of the Lync Server pool being tested.</span></span> <span data-ttu-id="0d006-123">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0d006-123">For example:</span></span>

    Test-CsWebApp -TargetFqdn "atl-cs-001.litwareinc.com"

<span data-ttu-id="0d006-124">Para ejecutar esta comprobación con las cuentas de usuario reales, debe crear dos objetos de credenciales de Windows PowerShell (objetos que contienen el nombre de cuenta y la contraseña) para cada cuenta.</span><span class="sxs-lookup"><span data-stu-id="0d006-124">To run this check using actual user accounts, you must create two Windows PowerShell credentials objects (objects that contain the account name and password) for each account.</span></span> <span data-ttu-id="0d006-125">A continuación, debe incluir dichos objetos de credenciales y las direcciones SIP de las dos cuentas cuando llame a test-CsWebApp:</span><span class="sxs-lookup"><span data-stu-id="0d006-125">You must then include those credentials objects and the SIP addresses of the two accounts when you call Test-CsWebApp:</span></span>

    $cred1 = Get-Credential "litwareinc\kenmyer"
    $cred2 = Get-Credential "litwareinc\pilar"
    
    Test-CsWebApp -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $cred1 -User2SipAddress "sip:pilar@litwareinc.com" -User2Credential $cred2

<span data-ttu-id="0d006-126">Para obtener más información, consulte el tema de ayuda del cmdlet [Test-CsWebApp](https://docs.microsoft.com/powershell/module/skype/Test-CsWebApp) .</span><span class="sxs-lookup"><span data-stu-id="0d006-126">For more information, see the help topic for the [Test-CsWebApp](https://docs.microsoft.com/powershell/module/skype/Test-CsWebApp) cmdlet.</span></span> <span data-ttu-id="0d006-127">Tenga en cuenta que Test-CsWebApp quedó en desuso para su uso en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0d006-127">Note that Test-CsWebApp was deprecated for use on Lync Server 2013.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="0d006-128">Determinar si se ha realizado correctamente o erróneo</span><span class="sxs-lookup"><span data-stu-id="0d006-128">Determining success or failure</span></span>

<span data-ttu-id="0d006-129">Si Test-CsWebApp puede unir a los usuarios a sus conferencias, el cmdlet devolverá el resultado de la prueba correcto:</span><span class="sxs-lookup"><span data-stu-id="0d006-129">If Test-CsWebApp can join the users to their conferences, the cmdlet will return the test result Success:</span></span>

<span data-ttu-id="0d006-130">FQDN de destino:</span><span class="sxs-lookup"><span data-stu-id="0d006-130">Target Fqdn :</span></span>

<span data-ttu-id="0d006-131">Resultado: correcto</span><span class="sxs-lookup"><span data-stu-id="0d006-131">Result : Success</span></span>

<span data-ttu-id="0d006-132">Latencia: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="0d006-132">Latency : 00:00:00</span></span>

<span data-ttu-id="0d006-133">Mensaje de error:</span><span class="sxs-lookup"><span data-stu-id="0d006-133">Error Message :</span></span>

<span data-ttu-id="0d006-134">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="0d006-134">Diagnosis :</span></span>

<span data-ttu-id="0d006-135">Si los usuarios no pueden unirse a las conferencias necesarias, el resultado de la prueba se marcará como error.</span><span class="sxs-lookup"><span data-stu-id="0d006-135">If the users cannot join the necessary conferences then the test result will be marked as Failure.</span></span> <span data-ttu-id="0d006-136">Por lo general, Test-CsWebApp también devolverá un mensaje de error detallado y un diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="0d006-136">Typically Test-CsWebApp will also report back a detailed error message and diagnosis:</span></span>

<span data-ttu-id="0d006-137">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="0d006-137">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="0d006-138">Resultado: error</span><span class="sxs-lookup"><span data-stu-id="0d006-138">Result : Failure</span></span>

<span data-ttu-id="0d006-139">Latencia: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="0d006-139">Latency : 00:00:00</span></span>

<span data-ttu-id="0d006-140">Mensaje de error: no se recibió ninguna respuesta para el servicio Web-Ticket</span><span class="sxs-lookup"><span data-stu-id="0d006-140">Error Message : No response received for Web-Ticket service</span></span>

<span data-ttu-id="0d006-141">Diagnóstico: la solicitud HTTP no está autorizada con el cliente</span><span class="sxs-lookup"><span data-stu-id="0d006-141">Diagnosis : The HTTP request is unauthorized with client</span></span>

<span data-ttu-id="0d006-142">esquema de autenticación ' NTLM '.</span><span class="sxs-lookup"><span data-stu-id="0d006-142">authentication scheme 'Ntlm'.</span></span> <span data-ttu-id="0d006-143">La autenticación</span><span class="sxs-lookup"><span data-stu-id="0d006-143">The authentication</span></span>

<span data-ttu-id="0d006-144">el encabezado recibido del servidor era ' Negotiate, NTLM '.</span><span class="sxs-lookup"><span data-stu-id="0d006-144">header received from the server was 'Negotiate,NTLM'.</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="0d006-145">Motivos por los que se ha producido un error en la prueba</span><span class="sxs-lookup"><span data-stu-id="0d006-145">Reasons why the test might have failed</span></span>

<span data-ttu-id="0d006-146">Los errores de Test-CsWebApp suelen implicar errores de autenticación de usuario.</span><span class="sxs-lookup"><span data-stu-id="0d006-146">Test-CsWebApp failures typically involve user authentication errors.</span></span> <span data-ttu-id="0d006-147">Si Test-CsWebApp da error, primero debe comprobar que los usuarios especificados tengan cuentas de usuario válidas y que estén habilitados para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0d006-147">If Test-CsWebApp fails, you should first verify that the specified users have valid user accounts and are enabled for Lync Server.</span></span> <span data-ttu-id="0d006-148">Puede recuperar la información de la cuenta con un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="0d006-148">You can retrieve account information by using a command similar to this:</span></span>

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

<span data-ttu-id="0d006-149">Si la propiedad Enabled no es igual a true o si se produce un error en el comando, significa que el usuario no tiene una cuenta de Lync Server válida. También debe comprobar que las contraseñas que proporcionó al cmdlet son válidas.</span><span class="sxs-lookup"><span data-stu-id="0d006-149">If the Enabled property is not equal to True or if the command fails, that means that the user does not have a valid Lync Server account.You should also verify that the passwords that you supplied to the cmdlet are valid.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

