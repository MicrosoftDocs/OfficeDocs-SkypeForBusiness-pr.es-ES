---
title: 'Lync Server 2013: capacidad de prueba para conectarse a un dominio federado'
description: 'Lync Server 2013: capacidad de prueba para conectarse a un dominio federado.'
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
ms.openlocfilehash: bf1f5bdef66d34b9ca2e39797df0b4ad32d9afde
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560826"
---
# <a name="testing-ability-to-connect-to-a-federated-domain-from-lync-server-2013"></a><span data-ttu-id="5af0e-103">Probar la capacidad de conectarse a un dominio federado desde Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5af0e-103">Testing ability to connect to a federated domain from Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5af0e-104">_**Última modificación del tema:** 2014-06-05_</span><span class="sxs-lookup"><span data-stu-id="5af0e-104">_**Topic Last Modified:** 2014-06-05_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5af0e-105">Programación de comprobación</span><span class="sxs-lookup"><span data-stu-id="5af0e-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="5af0e-106">Diario</span><span class="sxs-lookup"><span data-stu-id="5af0e-106">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5af0e-107">Herramienta de prueba</span><span class="sxs-lookup"><span data-stu-id="5af0e-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="5af0e-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5af0e-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5af0e-109">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="5af0e-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="5af0e-110">Cuando se ejecuta de forma local mediante el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="5af0e-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="5af0e-111">Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet Test-CsFederatedPartner.</span><span class="sxs-lookup"><span data-stu-id="5af0e-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsFederatedPartner cmdlet.</span></span> <span data-ttu-id="5af0e-112">Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="5af0e-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsFederatedPartner&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="5af0e-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="5af0e-113">Description</span></span>

<span data-ttu-id="5af0e-114">Test-CsFederatedPartner verifica su capacidad de conectarse con el dominio de un socio federado.</span><span class="sxs-lookup"><span data-stu-id="5af0e-114">Test-CsFederatedPartner verifies your ability to connect to the domain of a federated partner.</span></span> <span data-ttu-id="5af0e-115">Para comprobar la conectividad a un dominio, ese dominio debe estar incluido en la colección de dominios permitidos (federado).</span><span class="sxs-lookup"><span data-stu-id="5af0e-115">To verify the connectivity to a domain, that domain must be listed in the collection of allowed (federated) domains.</span></span> <span data-ttu-id="5af0e-116">Puede recuperar una lista de los dominios en la lista de dominios permitidos con este comando:</span><span class="sxs-lookup"><span data-stu-id="5af0e-116">You can retrieve a list of the domains on your allowed domains list by using this command:</span></span>

    Get-CsAllowedDomain

<span data-ttu-id="5af0e-117">Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) .</span><span class="sxs-lookup"><span data-stu-id="5af0e-117">For more information, see the Help documentation for the [Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) cmdlet.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="5af0e-118">Ejecutar la prueba</span><span class="sxs-lookup"><span data-stu-id="5af0e-118">Running the test</span></span>

<span data-ttu-id="5af0e-119">El cmdlet Test-FederatedPartner requiere dos datos: el FQDN del servidor perimetral y el FQDN del socio federado.</span><span class="sxs-lookup"><span data-stu-id="5af0e-119">The Test-FederatedPartner cmdlet requires two pieces of information: the FQDN of your Edge Server and the FQDN of the federated partner.</span></span> <span data-ttu-id="5af0e-120">Por ejemplo, este comando comprueba la capacidad de conectarse al dominio contoso.com:</span><span class="sxs-lookup"><span data-stu-id="5af0e-120">For example, this command tests the ability to connect to the domain contoso.com:</span></span>

    Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com"

<span data-ttu-id="5af0e-121">Este comando le permite probar las conexiones a todos los dominios que se encuentran en la lista de dominios permitidos:</span><span class="sxs-lookup"><span data-stu-id="5af0e-121">This command enables you to test the connections to all the domains currently on your allowed domains list:</span></span>

    Get-CsAllowedDomain | ForEach-Object {Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain $_.Identity}

<span data-ttu-id="5af0e-122">Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) .</span><span class="sxs-lookup"><span data-stu-id="5af0e-122">For more information, see the Help documentation for the [Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="5af0e-123">Determinar si se ha realizado correctamente o erróneo</span><span class="sxs-lookup"><span data-stu-id="5af0e-123">Determining success or failure</span></span>

<span data-ttu-id="5af0e-124">Si se puede establecer contacto con el dominio especificado, recibirá un resultado similar al siguiente con la propiedad result marcada como **correcta:**</span><span class="sxs-lookup"><span data-stu-id="5af0e-124">If the specified domain can be contacted, you'll receive output similar to this with the Result property marked as **Success:**</span></span>

<span data-ttu-id="5af0e-125">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="5af0e-125">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="5af0e-126">Resultado: correcto</span><span class="sxs-lookup"><span data-stu-id="5af0e-126">Result : Success</span></span>

<span data-ttu-id="5af0e-127">Latencia: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="5af0e-127">Latency : 00:00:00</span></span>

<span data-ttu-id="5af0e-128">Error</span><span class="sxs-lookup"><span data-stu-id="5af0e-128">Error :</span></span>

<span data-ttu-id="5af0e-129">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="5af0e-129">Diagnosis :</span></span>

<span data-ttu-id="5af0e-130">Si no se puede establecer contacto con el dominio especificado, el resultado se mostrará como error y la información adicional se registrará en las propiedades error y diagnosis:</span><span class="sxs-lookup"><span data-stu-id="5af0e-130">If the specified domain cannot be contacted, then the Result will be shown as Failure, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="5af0e-131">TargetFqdn: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="5af0e-131">TargetFqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="5af0e-132">Resultado: error</span><span class="sxs-lookup"><span data-stu-id="5af0e-132">Result : Failure</span></span>

<span data-ttu-id="5af0e-133">Latencia: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="5af0e-133">Latency : 00:00:00</span></span>

<span data-ttu-id="5af0e-134">Error: 504, tiempo de espera del servidor</span><span class="sxs-lookup"><span data-stu-id="5af0e-134">Error : 504, Server time-out</span></span>

<span data-ttu-id="5af0e-135">Diagnosis: ErrorCode = 2, Source = ATL-CS-001. litwareinc. com, Reason = vea</span><span class="sxs-lookup"><span data-stu-id="5af0e-135">Diagnosis : ErrorCode=2, Source=atl-cs-001.litwareinc.com,Reason=See</span></span>

<span data-ttu-id="5af0e-136">código de respuesta y frase de motivo.</span><span class="sxs-lookup"><span data-stu-id="5af0e-136">response code and reason phrase.</span></span>

<span data-ttu-id="5af0e-137">Microsoft. RTC. Signaling. DiagnosticHeader</span><span class="sxs-lookup"><span data-stu-id="5af0e-137">Microsoft.Rtc.Signaling.DiagnosticHeader</span></span>

<span data-ttu-id="5af0e-138">Por ejemplo, la salida anterior indica que la prueba produjo un error debido a un error de tiempo de espera del servidor.</span><span class="sxs-lookup"><span data-stu-id="5af0e-138">For example, the previous output states that the test failed because of a server time-out error.</span></span> <span data-ttu-id="5af0e-139">Normalmente, esto indica problemas de conectividad de red o problemas al contactar con el servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="5af0e-139">This typically indicates either network connectivity problems or problems contacting the Edge Server.</span></span>

<span data-ttu-id="5af0e-140">Si Test-CsFederatedPartner da error, es posible que desee volver a ejecutar la prueba, pero esta vez incluya el parámetro verbose:</span><span class="sxs-lookup"><span data-stu-id="5af0e-140">If Test-CsFederatedPartner fails, then you might want to rerun the test, this time including the Verbose parameter:</span></span>

    Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com" -Verbose

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="5af0e-141">Motivos por los que se ha producido un error en la prueba</span><span class="sxs-lookup"><span data-stu-id="5af0e-141">Reasons why the test might have failed</span></span>

<span data-ttu-id="5af0e-142">Estas son algunas de las razones comunes por las que Test-CsFederatedPartner podría producir un error:</span><span class="sxs-lookup"><span data-stu-id="5af0e-142">Here are some common reasons why Test-CsFederatedPartner might fail:</span></span>

  - <span data-ttu-id="5af0e-143">Es posible que el servidor perimetral no esté disponible.</span><span class="sxs-lookup"><span data-stu-id="5af0e-143">The Edge Server might not be available.</span></span> <span data-ttu-id="5af0e-144">Puede usar este comando para los FQDN de los servidores perimetrales:</span><span class="sxs-lookup"><span data-stu-id="5af0e-144">You can the FQDNs of your Edge Servers by using this command:</span></span>
    
        Get-CsService -EdgeServer | Select-Object PoolFqdn
    
    <span data-ttu-id="5af0e-145">Después, puede hacer ping a cada servidor perimetral para comprobar que se puede tener acceso a él a través de la red.</span><span class="sxs-lookup"><span data-stu-id="5af0e-145">You can then ping each Edge Server to verify that it can be accessed over the network.</span></span> <span data-ttu-id="5af0e-146">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="5af0e-146">For example:</span></span>
    
        ping atl-edge-001.litwareinc.com

  - <span data-ttu-id="5af0e-147">Es posible que el dominio especificado no aparezca en la lista de dominios permitidos.</span><span class="sxs-lookup"><span data-stu-id="5af0e-147">The specified domain might not be listed on the allowed domains list.</span></span> <span data-ttu-id="5af0e-148">Para comprobar los dominios que se agregaron a la lista de dominios permitidos, use este comando:</span><span class="sxs-lookup"><span data-stu-id="5af0e-148">To verify the domains that were added to the allowed domains list, use this command:</span></span>
    
        Get-CsAllowedDomain
    
    <span data-ttu-id="5af0e-149">Si quiere ver una lista de dominios con los que los usuarios no se pudieron comunicar, use este comando:</span><span class="sxs-lookup"><span data-stu-id="5af0e-149">If you’d like to see a list of domains that users were blocked from communicating with, then use this command:</span></span>
    
        Get-CsBlockedDomain

</div>

</div>

<span> </span>

</div>

</div>

</div>

