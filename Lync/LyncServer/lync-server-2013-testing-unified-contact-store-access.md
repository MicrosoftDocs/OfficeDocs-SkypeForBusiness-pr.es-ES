---
title: 'Lync Server 2013: probar el acceso al almacén de contactos unificado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Unified Contact Store access
ms:assetid: 761f46bd-2e14-4f40-82b9-afa1eaa816b0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727309(v=OCS.15)
ms:contentKeyID: 63969621
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6022d7651a99c2165961ed8cb8852048c10779ff
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141236"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-unified-contact-store-access-in-lync-server-2013"></a><span data-ttu-id="aefd8-102">Probar el acceso al almacén de contactos unificado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aefd8-102">Testing Unified Contact Store access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aefd8-103">_**Última modificación del tema:** 2015-05-15_</span><span class="sxs-lookup"><span data-stu-id="aefd8-103">_**Topic Last Modified:** 2015-05-15_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aefd8-104">Programación de comprobación</span><span class="sxs-lookup"><span data-stu-id="aefd8-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="aefd8-105">Diario</span><span class="sxs-lookup"><span data-stu-id="aefd8-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aefd8-106">Herramienta de prueba</span><span class="sxs-lookup"><span data-stu-id="aefd8-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="aefd8-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="aefd8-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aefd8-108">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="aefd8-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="aefd8-109">Cuando se ejecuta de forma local mediante el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="aefd8-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="aefd8-110">Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet <strong>Test-CsUnifiedContactStore</strong> .</span><span class="sxs-lookup"><span data-stu-id="aefd8-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsUnifiedContactStore</strong> cmdlet.</span></span> <span data-ttu-id="aefd8-111">Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="aefd8-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsUnifiedContactStore&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="aefd8-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="aefd8-112">Description</span></span>

<span data-ttu-id="aefd8-113">El almacén de contactos unificados que se presenta en Lync Server 2013 ofrece a los administradores la opción de almacenar los contactos de un usuario en Microsoft Exchange Server 2013 en lugar de en Lync Server.</span><span class="sxs-lookup"><span data-stu-id="aefd8-113">The unified contact store introduced in Lync Server 2013 gives administrators the option of storing a user's contacts in Microsoft Exchange Server 2013 instead of in Lync Server.</span></span> <span data-ttu-id="aefd8-114">Esto permite al usuario tener acceso al mismo conjunto de contactos de Outlook Web Access, además de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="aefd8-114">This allows the user to access the same set of contacts in Outlook Web Access in addition to Lync 2013.</span></span> <span data-ttu-id="aefd8-115">(O bien, puede seguir almacenando contactos en Lync Server.</span><span class="sxs-lookup"><span data-stu-id="aefd8-115">(Or, you can continue to store contacts in Lync Server.</span></span> <span data-ttu-id="aefd8-116">En ese caso, los usuarios tendrán que mantener dos conjuntos de contactos distintos: uno para usar con Outlook y Outlook Web Access, y otro para usarlo con Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="aefd8-116">In that case, users will have to maintain two separate sets of contacts: one for use with Outlook and Outlook Web Access, and one for use with Lync 2013.)</span></span>

<span data-ttu-id="aefd8-117">Puede determinar si los contactos de un usuario se movieron o no al almacén de contactos unificado ejecutando el cmdlet **Test-CsUnifiedContactStore** .</span><span class="sxs-lookup"><span data-stu-id="aefd8-117">You can determine whether or not a user's contacts were moved to the unified contact store by running the **Test-CsUnifiedContactStore** cmdlet.</span></span> <span data-ttu-id="aefd8-118">El cmdlet **Test-CsUnifiedContactStore** tomará la cuenta de usuario especificada, se conectará al almacén de contactos unificado e intentará recuperar un contacto para el usuario.</span><span class="sxs-lookup"><span data-stu-id="aefd8-118">The **Test-CsUnifiedContactStore** cmdlet will take the specified user account, connect to the unified contact store, and attempt to retrieve a contact for the user.</span></span> <span data-ttu-id="aefd8-119">Si no se pueden recuperar contactos, el comando producirá un error junto con el mensaje "no se recibió ningún contacto para el usuario.</span><span class="sxs-lookup"><span data-stu-id="aefd8-119">If no contacts can be retrieved then the command will fail together with the message "No contacts were received for the user.</span></span> <span data-ttu-id="aefd8-120">Verifique que los contactos existan para el usuario".</span><span class="sxs-lookup"><span data-stu-id="aefd8-120">Verify that contacts exist for the user."</span></span>

<span data-ttu-id="aefd8-121">Tenga en cuenta que se producirá un error en el cmdlet **Test-CsUnifiedContactStore** si el usuario se migró correctamente al almacén de contactos unificados, pero no tiene contactos en su lista de contactos.</span><span class="sxs-lookup"><span data-stu-id="aefd8-121">Note that the **Test-CsUnifiedContactStore** cmdlet will fail if the user has successfully migrated to the unified contact store but has no contacts on his or her Contacts list.</span></span> <span data-ttu-id="aefd8-122">El usuario especificado debe tener al menos un contacto para que el cmdlet **Test-CsUnifiedContactStore** se complete correctamente.</span><span class="sxs-lookup"><span data-stu-id="aefd8-122">The specified user must have at least one contact for the **Test-CsUnifiedContactStore** cmdlet to complete successfully.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="aefd8-123">Ejecutar la prueba</span><span class="sxs-lookup"><span data-stu-id="aefd8-123">Running the test</span></span>

<span data-ttu-id="aefd8-124">Los comandos que se muestran en el siguiente ejemplo determinan si se\\pueden encontrar los contactos del usuario litwareinc kenmyer en el almacén de contactos unificados.</span><span class="sxs-lookup"><span data-stu-id="aefd8-124">The commands shown in the following example determine whether contacts for the user litwareinc\\kenmyer can be found in the unified contact store.</span></span> <span data-ttu-id="aefd8-125">Para ello, el primer comando del ejemplo usa el cmdlet **Get-Credential** para crear un objeto de credenciales de interfaz de línea de comandos de Windows PowerShell para\\el usuario litwareinc kenmyer.</span><span class="sxs-lookup"><span data-stu-id="aefd8-125">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credentials object for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="aefd8-126">Tenga en cuenta que debe proporcionar la contraseña de esta cuenta para crear un objeto de credenciales válido y asegurarse de que el cmdlet **Test-CsUnifiedContactStore** puede ejecutar su comprobación.</span><span class="sxs-lookup"><span data-stu-id="aefd8-126">Note that you must supply the password for this account to create a valid credentials object and to make sure that the **Test-CsUnifiedContactStore** cmdlet can run its check.</span></span>

<span data-ttu-id="aefd8-127">El segundo comando del ejemplo usa el objeto de credenciales proporcionado ($x) y la dirección SIP del usuario litwareinc\\kenmyer para determinar si se pueden encontrar sus contactos en el almacén de contactos unificados.</span><span class="sxs-lookup"><span data-stu-id="aefd8-127">The second command in the example uses the supplied credentials object ($x) and the SIP address of the user litwareinc\\kenmyer to determine whether his contacts can be found in the unified contact store.</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsUnifiedContactStore -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="aefd8-128">Determinar si se ha realizado correctamente o erróneo</span><span class="sxs-lookup"><span data-stu-id="aefd8-128">Determining success or failure</span></span>

<span data-ttu-id="aefd8-129">Si el acceso al almacén de contactos está configurado correctamente, recibirá un resultado similar a este, con la propiedad result marcada como **correcta:**</span><span class="sxs-lookup"><span data-stu-id="aefd8-129">If access to the contact store is configured correctly, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="aefd8-130">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="aefd8-130">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="aefd8-131">Resultado: correcto</span><span class="sxs-lookup"><span data-stu-id="aefd8-131">Result : Success</span></span>

<span data-ttu-id="aefd8-132">Latencia: 00:00:14.9862716</span><span class="sxs-lookup"><span data-stu-id="aefd8-132">Latency : 00:00:14.9862716</span></span>

<span data-ttu-id="aefd8-133">Mensaje de error:</span><span class="sxs-lookup"><span data-stu-id="aefd8-133">Error Message :</span></span>

<span data-ttu-id="aefd8-134">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="aefd8-134">Diagnosis :</span></span>

<span data-ttu-id="aefd8-135">Si el acceso al almacén de contactos no está configurado correctamente, el resultado se mostrará como **error**y la información adicional se registrará en las propiedades error y diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="aefd8-135">If access to the contact store is not configured correctly, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="aefd8-136">ADVERTENCIA: no se pudo leer el número de puerto del registrador para el certificado completo</span><span class="sxs-lookup"><span data-stu-id="aefd8-136">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="aefd8-137">nombre de dominio (FQDN).</span><span class="sxs-lookup"><span data-stu-id="aefd8-137">domain name (FQDN).</span></span> <span data-ttu-id="aefd8-138">Se usará el número de puerto del registrador predeterminado.</span><span class="sxs-lookup"><span data-stu-id="aefd8-138">Using default Registrar port number.</span></span> <span data-ttu-id="aefd8-139">Excepción</span><span class="sxs-lookup"><span data-stu-id="aefd8-139">Exception:</span></span>

<span data-ttu-id="aefd8-140">System. InvalidOperationException: no se encontró ningún clúster que coincida en la topología.</span><span class="sxs-lookup"><span data-stu-id="aefd8-140">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="aefd8-141">Veamos</span><span class="sxs-lookup"><span data-stu-id="aefd8-141">at</span></span>

<span data-ttu-id="aefd8-142">Microsoft. RTC. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri</span><span class="sxs-lookup"><span data-stu-id="aefd8-142">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="aefd8-143">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="aefd8-143">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="aefd8-144">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="aefd8-144">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="aefd8-145">Resultado: error</span><span class="sxs-lookup"><span data-stu-id="aefd8-145">Result : Failure</span></span>

<span data-ttu-id="aefd8-146">Latencia: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="aefd8-146">Latency : 00:00:00</span></span>

<span data-ttu-id="aefd8-147">Mensaje de error: 10060, se ha producido un error en el intento de conexión porque la entidad conectada</span><span class="sxs-lookup"><span data-stu-id="aefd8-147">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="aefd8-148">no respondió correctamente después de un período de tiempo o</span><span class="sxs-lookup"><span data-stu-id="aefd8-148">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="aefd8-149">error en la conexión establecida porque el host conectado tiene</span><span class="sxs-lookup"><span data-stu-id="aefd8-149">established connection failed because connected host has</span></span>

<span data-ttu-id="aefd8-150">no se pudo responder 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="aefd8-150">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="aefd8-151">Excepción interna: error en el intento de conexión porque el</span><span class="sxs-lookup"><span data-stu-id="aefd8-151">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="aefd8-152">la parte conectada no respondió correctamente después de un período de</span><span class="sxs-lookup"><span data-stu-id="aefd8-152">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="aefd8-153">tiempo o error de conexión establecida debido a que el host conectado</span><span class="sxs-lookup"><span data-stu-id="aefd8-153">time, or established connection failed because connected host</span></span>

<span data-ttu-id="aefd8-154">Error al responder 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="aefd8-154">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="aefd8-155">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="aefd8-155">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="aefd8-156">Motivos por los que se ha producido un error en la prueba</span><span class="sxs-lookup"><span data-stu-id="aefd8-156">Reasons why the test might have failed</span></span>

<span data-ttu-id="aefd8-157">Estas son algunas de las razones comunes por las que **Test-CsUnifiedContactStore** podría fallar:</span><span class="sxs-lookup"><span data-stu-id="aefd8-157">Here are some common reasons why **Test-CsUnifiedContactStore** might fail:</span></span>

  - <span data-ttu-id="aefd8-158">Se ha suministrado un valor de parámetro incorrecto.</span><span class="sxs-lookup"><span data-stu-id="aefd8-158">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="aefd8-159">Si se usa, los parámetros opcionales deben configurarse correctamente o se producirá un error en la prueba.</span><span class="sxs-lookup"><span data-stu-id="aefd8-159">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="aefd8-160">Vuelva a ejecutar el comando sin los parámetros opcionales y vea si se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="aefd8-160">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="aefd8-161">No se pudo conectar con el almacén de contactos unificados y no fue posible intentar recuperar un contacto para el usuario.</span><span class="sxs-lookup"><span data-stu-id="aefd8-161">Connect to the unified contact store failed, and the attempt to retrieve a contact for the user was not possible.</span></span> <span data-ttu-id="aefd8-162">Es posible que haya problemas de conectividad de red.</span><span class="sxs-lookup"><span data-stu-id="aefd8-162">There may be network connectivity issues.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="aefd8-163">Vea también</span><span class="sxs-lookup"><span data-stu-id="aefd8-163">See Also</span></span>


[<span data-ttu-id="aefd8-164">New-CsUserServicesPolicy</span><span class="sxs-lookup"><span data-stu-id="aefd8-164">New-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsUserServicesPolicy)  
[<span data-ttu-id="aefd8-165">Set-CsUserServicesPolicy</span><span class="sxs-lookup"><span data-stu-id="aefd8-165">Set-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsUserServicesPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

