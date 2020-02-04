---
title: 'Lync Server 2013: capacidad de probar la conexión a un dominio federado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing ability to connect to a federated domain
ms:assetid: d8ccfade-ef54-47a4-9f87-36213a635ce5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743840(v=OCS.15)
ms:contentKeyID: 63969653
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f18a8c703b085fe559b3a979ac72d9c0b0dfe38f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746020"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-connect-to-a-federated-domain-from-lync-server-2013"></a><span data-ttu-id="8361c-102">Capacidad de prueba para conectarse a un dominio federado desde Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8361c-102">Testing ability to connect to a federated domain from Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8361c-103">_**Última modificación del tema:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="8361c-103">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8361c-104">Programación de verificación</span><span class="sxs-lookup"><span data-stu-id="8361c-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="8361c-105">Cada día</span><span class="sxs-lookup"><span data-stu-id="8361c-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8361c-106">Herramienta de prueba</span><span class="sxs-lookup"><span data-stu-id="8361c-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="8361c-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8361c-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8361c-108">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="8361c-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="8361c-109">Al ejecutarse de forma local con el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="8361c-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="8361c-110">Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol de RBAC que tenga permiso para ejecutar el cmdlet test-CsFederatedPartner.</span><span class="sxs-lookup"><span data-stu-id="8361c-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsFederatedPartner cmdlet.</span></span> <span data-ttu-id="8361c-111">Para ver una lista de todos los roles de RBAC que pueden usar este cmdlet, ejecute el siguiente comando en el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="8361c-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsFederatedPartner&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="8361c-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="8361c-112">Description</span></span>

<span data-ttu-id="8361c-113">Prueba-CsFederatedPartner comprueba su capacidad de conectar con el dominio de un socio federado.</span><span class="sxs-lookup"><span data-stu-id="8361c-113">Test-CsFederatedPartner verifies your ability to connect to the domain of a federated partner.</span></span> <span data-ttu-id="8361c-114">Para comprobar la conectividad a un dominio, ese dominio debe aparecer en la colección de dominios permitidos (federados).</span><span class="sxs-lookup"><span data-stu-id="8361c-114">To verify the connectivity to a domain, that domain must be listed in the collection of allowed (federated) domains.</span></span> <span data-ttu-id="8361c-115">Puede recuperar una lista de los dominios en la lista de dominios permitidos con este comando:</span><span class="sxs-lookup"><span data-stu-id="8361c-115">You can retrieve a list of the domains on your allowed domains list by using this command:</span></span>

    Get-CsAllowedDomain

<span data-ttu-id="8361c-116">Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) .</span><span class="sxs-lookup"><span data-stu-id="8361c-116">For more information, see the Help documentation for the [Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="8361c-117">Ejecutar la prueba</span><span class="sxs-lookup"><span data-stu-id="8361c-117">Running the test</span></span>

<span data-ttu-id="8361c-118">El cmdlet test-FederatedPartner requiere dos datos: el FQDN de su servidor perimetral y el FQDN del socio federado.</span><span class="sxs-lookup"><span data-stu-id="8361c-118">The Test-FederatedPartner cmdlet requires two pieces of information: the FQDN of your Edge Server and the FQDN of the federated partner.</span></span> <span data-ttu-id="8361c-119">Por ejemplo, este comando prueba la capacidad de conectar con el dominio contoso.com:</span><span class="sxs-lookup"><span data-stu-id="8361c-119">For example, this command tests the ability to connect to the domain contoso.com:</span></span>

    Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com"

<span data-ttu-id="8361c-120">Este comando le permite probar las conexiones a todos los dominios que se encuentran en la lista de dominios permitidos:</span><span class="sxs-lookup"><span data-stu-id="8361c-120">This command enables you to test the connections to all the domains currently on your allowed domains list:</span></span>

    Get-CsAllowedDomain | ForEach-Object {Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain $_.Identity}

<span data-ttu-id="8361c-121">Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) .</span><span class="sxs-lookup"><span data-stu-id="8361c-121">For more information, see the Help documentation for the [Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="8361c-122">Determinar el éxito o el fracaso</span><span class="sxs-lookup"><span data-stu-id="8361c-122">Determining success or failure</span></span>

<span data-ttu-id="8361c-123">Si se puede contactar con el dominio especificado, recibirá una salida similar a la siguiente, con la propiedad result marcada como **correcta:**</span><span class="sxs-lookup"><span data-stu-id="8361c-123">If the specified domain can be contacted, you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="8361c-124">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="8361c-124">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="8361c-125">Resultado: éxito</span><span class="sxs-lookup"><span data-stu-id="8361c-125">Result : Success</span></span>

<span data-ttu-id="8361c-126">Latencia: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="8361c-126">Latency : 00:00:00</span></span>

<span data-ttu-id="8361c-127">:</span><span class="sxs-lookup"><span data-stu-id="8361c-127">Error :</span></span>

<span data-ttu-id="8361c-128">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="8361c-128">Diagnosis :</span></span>

<span data-ttu-id="8361c-129">Si no se puede contactar con el dominio especificado, el resultado se mostrará como erróneo y la información adicional se registrará en las propiedades de diagnóstico y errores:</span><span class="sxs-lookup"><span data-stu-id="8361c-129">If the specified domain cannot be contacted, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="8361c-130">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="8361c-130">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="8361c-131">Resultado: error</span><span class="sxs-lookup"><span data-stu-id="8361c-131">Result : Failure</span></span>

<span data-ttu-id="8361c-132">Latencia: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="8361c-132">Latency : 00:00:00</span></span>

<span data-ttu-id="8361c-133">Error: 504, tiempo de espera del servidor</span><span class="sxs-lookup"><span data-stu-id="8361c-133">Error : 504, Server time-out</span></span>

<span data-ttu-id="8361c-134">Diagnosis: ErrorCode = 2, Source = ATL-CS-001. litwareinc. com, razón = ver</span><span class="sxs-lookup"><span data-stu-id="8361c-134">Diagnosis : ErrorCode=2, Source=atl-cs-001.litwareinc.com,Reason=See</span></span>

<span data-ttu-id="8361c-135">código de respuesta y frase de motivo.</span><span class="sxs-lookup"><span data-stu-id="8361c-135">response code and reason phrase.</span></span>

<span data-ttu-id="8361c-136">Microsoft. RTC. Signaling. DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="8361c-136">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="8361c-137">Por ejemplo, la salida anterior indica que no se pudo realizar la prueba debido a un error de tiempo de espera del servidor.</span><span class="sxs-lookup"><span data-stu-id="8361c-137">For example, the previous output states that the test failed because of a server time-out error.</span></span> <span data-ttu-id="8361c-138">Normalmente, esto indica problemas de conectividad de red o problemas para ponerse en contacto con el servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="8361c-138">This typically indicates either network connectivity problems or problems contacting the Edge Server.</span></span>

<span data-ttu-id="8361c-139">Si prueba-CsFederatedPartner da error, es posible que desee volver a ejecutar la prueba, esta vez incluido el parámetro detallado:</span><span class="sxs-lookup"><span data-stu-id="8361c-139">If Test-CsFederatedPartner fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com" -Verbose

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="8361c-140">Razones por las que se ha producido un error en la prueba</span><span class="sxs-lookup"><span data-stu-id="8361c-140">Reasons why the test might have failed</span></span>

<span data-ttu-id="8361c-141">Estas son algunas de las razones comunes por las que test-CsFederatedPartner podría fallar:</span><span class="sxs-lookup"><span data-stu-id="8361c-141">Here are some common reasons why Test-CsFederatedPartner might fail:</span></span>

  - <span data-ttu-id="8361c-142">Es posible que el servidor perimetral no esté disponible.</span><span class="sxs-lookup"><span data-stu-id="8361c-142">The Edge Server might not be available.</span></span> <span data-ttu-id="8361c-143">Puede usar los FQDN de los servidores perimetrales con este comando:</span><span class="sxs-lookup"><span data-stu-id="8361c-143">You can the FQDNs of your Edge Servers by using this command:</span></span>
    
        Get-CsService -EdgeServer | Select-Object PoolFqdn
    
    <span data-ttu-id="8361c-144">Después, puede hacer ping a cada servidor perimetral para comprobar que se puede tener acceso a él a través de la red.</span><span class="sxs-lookup"><span data-stu-id="8361c-144">You can then ping each Edge Server to verify that it can be accessed over the network.</span></span> <span data-ttu-id="8361c-145">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8361c-145">For example:</span></span>
    
        ping atl-edge-001.litwareinc.com

  - <span data-ttu-id="8361c-146">Es posible que el dominio especificado no aparezca en la lista de dominios permitidos.</span><span class="sxs-lookup"><span data-stu-id="8361c-146">The specified domain might not be listed on the allowed domains list.</span></span> <span data-ttu-id="8361c-147">Para comprobar los dominios que se han agregado a la lista de dominios permitidos, use este comando:</span><span class="sxs-lookup"><span data-stu-id="8361c-147">To verify the domains that were added to the allowed domains list, use this command:</span></span>
    
        Get-CsAllowedDomain
    
    <span data-ttu-id="8361c-148">Si desea ver una lista de los dominios con los que los usuarios no pueden comunicarse, use este comando:</span><span class="sxs-lookup"><span data-stu-id="8361c-148">If you’d like to see a list of domains that users were blocked from communicating with, then use this command:</span></span>
    
        Get-CsBlockedDomain

</div>

</div>

<span> </span>

</div>

</div>

</div>

