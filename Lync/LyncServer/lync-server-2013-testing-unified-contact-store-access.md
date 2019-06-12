---
title: 'Lync Server 2013: probar el acceso a almacén de contactos unificado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing Unified Contact Store access
ms:assetid: 761f46bd-2e14-4f40-82b9-afa1eaa816b0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727309(v=OCS.15)
ms:contentKeyID: 63969621
ms.date: 05/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef1d8d8930b9e732faeef02c76d722331c726b67
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850313"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-unified-contact-store-access-in-lync-server-2013"></a><span data-ttu-id="ea7b7-102">Probar el acceso a almacén de contactos unificado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ea7b7-102">Testing Unified Contact Store access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ea7b7-103">_**Última modificación del tema:** 2015-05-15_</span><span class="sxs-lookup"><span data-stu-id="ea7b7-103">_**Topic Last Modified:** 2015-05-15_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ea7b7-104">Programación de verificación</span><span class="sxs-lookup"><span data-stu-id="ea7b7-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="ea7b7-105">Cada día</span><span class="sxs-lookup"><span data-stu-id="ea7b7-105">Daily</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ea7b7-106">Herramienta de prueba</span><span class="sxs-lookup"><span data-stu-id="ea7b7-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="ea7b7-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ea7b7-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ea7b7-108">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="ea7b7-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="ea7b7-109">Al ejecutarse de forma local con el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="ea7b7-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="ea7b7-110">Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol de RBAC que tenga permiso para ejecutar el cmdlet <strong>Test-CsUnifiedContactStore</strong> .</span><span class="sxs-lookup"><span data-stu-id="ea7b7-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the <strong>Test-CsUnifiedContactStore</strong> cmdlet.</span></span> <span data-ttu-id="ea7b7-111">Para ver una lista de todos los roles de RBAC que pueden usar este cmdlet, ejecute el siguiente comando en el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="ea7b7-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsUnifiedContactStore&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="ea7b7-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="ea7b7-112">Description</span></span>

<span data-ttu-id="ea7b7-113">El almacén de contactos unificado introducido en Lync Server 2013 ofrece a los administradores la opción de almacenar los contactos de un usuario en Microsoft Exchange Server 2013 en lugar de en Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ea7b7-113">The unified contact store introduced in Lync Server 2013 gives administrators the option of storing a user's contacts in Microsoft Exchange Server 2013 instead of in Lync Server.</span></span> <span data-ttu-id="ea7b7-114">Esto permite que el usuario tenga acceso al mismo conjunto de contactos de Outlook Web Access además de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="ea7b7-114">This allows the user to access the same set of contacts in Outlook Web Access in addition to Lync 2013.</span></span> <span data-ttu-id="ea7b7-115">(También puede seguir almacenando contactos en Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ea7b7-115">(Or, you can continue to store contacts in Lync Server.</span></span> <span data-ttu-id="ea7b7-116">En ese caso, los usuarios tendrán que mantener dos conjuntos de contactos distintos: uno para usar con Outlook y Outlook Web Access, y otro para usar con Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="ea7b7-116">In that case, users will have to maintain two separate sets of contacts: one for use with Outlook and Outlook Web Access, and one for use with Lync 2013.)</span></span>

<span data-ttu-id="ea7b7-117">Puede determinar si los contactos de un usuario se movieron o no al almacén de contactos unificado ejecutando el cmdlet **Test-CsUnifiedContactStore** .</span><span class="sxs-lookup"><span data-stu-id="ea7b7-117">You can determine whether or not a user's contacts were moved to the unified contact store by running the **Test-CsUnifiedContactStore** cmdlet.</span></span> <span data-ttu-id="ea7b7-118">El cmdlet **Test-CsUnifiedContactStore** tomará la cuenta de usuario especificada, se conectará al almacén de contactos unificado e intentará recuperar un contacto para el usuario.</span><span class="sxs-lookup"><span data-stu-id="ea7b7-118">The **Test-CsUnifiedContactStore** cmdlet will take the specified user account, connect to the unified contact store, and attempt to retrieve a contact for the user.</span></span> <span data-ttu-id="ea7b7-119">Si no se puede recuperar ningún contacto, el comando generará un error junto con el mensaje "no se ha recibido ningún contacto para el usuario.</span><span class="sxs-lookup"><span data-stu-id="ea7b7-119">If no contacts can be retrieved then the command will fail together with the message "No contacts were received for the user.</span></span> <span data-ttu-id="ea7b7-120">Compruebe que existen los contactos para el usuario.</span><span class="sxs-lookup"><span data-stu-id="ea7b7-120">Verify that contacts exist for the user."</span></span>

<span data-ttu-id="ea7b7-121">Tenga en cuenta que el cmdlet **Test-CsUnifiedContactStore** fallará si el usuario ha migrado correctamente al almacén de contactos unificado, pero no tiene ningún contacto en su lista de contactos.</span><span class="sxs-lookup"><span data-stu-id="ea7b7-121">Note that the **Test-CsUnifiedContactStore** cmdlet will fail if the user has successfully migrated to the unified contact store but has no contacts on his or her Contacts list.</span></span> <span data-ttu-id="ea7b7-122">El usuario especificado debe tener al menos un contacto para que el cmdlet **Test-CsUnifiedContactStore** se complete correctamente.</span><span class="sxs-lookup"><span data-stu-id="ea7b7-122">The specified user must have at least one contact for the **Test-CsUnifiedContactStore** cmdlet to complete successfully.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="ea7b7-123">Ejecutar la prueba</span><span class="sxs-lookup"><span data-stu-id="ea7b7-123">Running the test</span></span>

<span data-ttu-id="ea7b7-124">Los comandos que se muestran en el siguiente ejemplo determinan si los\\contactos para el usuario litwareinc kenmyer pueden encontrarse en el almacén de contactos unificado.</span><span class="sxs-lookup"><span data-stu-id="ea7b7-124">The commands shown in the following example determine whether contacts for the user litwareinc\\kenmyer can be found in the unified contact store.</span></span> <span data-ttu-id="ea7b7-125">Para ello, el primer comando del ejemplo usa el cmdlet **Get-Credential** para crear un objeto de credenciales de la interfaz de línea de comandos de Windows PowerShell\\para el usuario litwareinc kenmyer.</span><span class="sxs-lookup"><span data-stu-id="ea7b7-125">To do this, the first command in the example uses the **Get-Credential** cmdlet to create a Windows PowerShell command-line interface credentials object for the user litwareinc\\kenmyer.</span></span> <span data-ttu-id="ea7b7-126">Tenga en cuenta que debe proporcionar la contraseña de esta cuenta para crear un objeto de credenciales válido y asegurarse de que el cmdlet **Test-CsUnifiedContactStore** puede ejecutar su comprobación.</span><span class="sxs-lookup"><span data-stu-id="ea7b7-126">Note that you must supply the password for this account to create a valid credentials object and to make sure that the **Test-CsUnifiedContactStore** cmdlet can run its check.</span></span>

<span data-ttu-id="ea7b7-127">El segundo comando del ejemplo usa el objeto de credenciales proporcionado ($x) y la dirección SIP del usuario litwareinc\\kenmyer para determinar si se pueden encontrar sus contactos en el almacén de contactos unificado.</span><span class="sxs-lookup"><span data-stu-id="ea7b7-127">The second command in the example uses the supplied credentials object ($x) and the SIP address of the user litwareinc\\kenmyer to determine whether his contacts can be found in the unified contact store.</span></span>

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsUnifiedContactStore -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="ea7b7-128">Determinar el éxito o el fracaso</span><span class="sxs-lookup"><span data-stu-id="ea7b7-128">Determining success or failure</span></span>

<span data-ttu-id="ea7b7-129">Si el acceso al almacén de contactos está configurado correctamente, recibirá una salida similar a la siguiente, con la propiedad result marcada como **correcta:**</span><span class="sxs-lookup"><span data-stu-id="ea7b7-129">If access to the contact store is configured correctly, you'll receive output similar to this, with the Result property marked as **Success:**</span></span>

<span data-ttu-id="ea7b7-130">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="ea7b7-130">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="ea7b7-131">Resultado: éxito</span><span class="sxs-lookup"><span data-stu-id="ea7b7-131">Result : Success</span></span>

<span data-ttu-id="ea7b7-132">Latencia: 00:00:14.9862716</span><span class="sxs-lookup"><span data-stu-id="ea7b7-132">Latency : 00:00:14.9862716</span></span>

<span data-ttu-id="ea7b7-133">Mensaje de error:</span><span class="sxs-lookup"><span data-stu-id="ea7b7-133">Error Message :</span></span>

<span data-ttu-id="ea7b7-134">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="ea7b7-134">Diagnosis :</span></span>

<span data-ttu-id="ea7b7-135">Si el acceso al almacén de contactos no está configurado correctamente, el resultado se mostrará como **error**y la información adicional se registrará en las propiedades de error y diagnóstico:</span><span class="sxs-lookup"><span data-stu-id="ea7b7-135">If access to the contact store is not configured correctly, the Result will be shown as **Failure**, and additional information will be recorded in the Error and Diagnosis properties:</span></span>

<span data-ttu-id="ea7b7-136">ADVERTENCIA: no se pudo leer el número de puerto del registrador para el nombre completo</span><span class="sxs-lookup"><span data-stu-id="ea7b7-136">WARNING: Failed to read Registrar port number for the given fully qualified</span></span>

<span data-ttu-id="ea7b7-137">nombre de dominio (FQDN).</span><span class="sxs-lookup"><span data-stu-id="ea7b7-137">domain name (FQDN).</span></span> <span data-ttu-id="ea7b7-138">Usando el número de puerto predeterminado del registrador.</span><span class="sxs-lookup"><span data-stu-id="ea7b7-138">Using default Registrar port number.</span></span> <span data-ttu-id="ea7b7-139">Excepción</span><span class="sxs-lookup"><span data-stu-id="ea7b7-139">Exception:</span></span>

<span data-ttu-id="ea7b7-140">System. InvalidOperationException: no se encontró ningún clúster coincidente en la topología.</span><span class="sxs-lookup"><span data-stu-id="ea7b7-140">System.InvalidOperationException: No matching cluster found in topology.</span></span>

<span data-ttu-id="ea7b7-141">en</span><span class="sxs-lookup"><span data-stu-id="ea7b7-141">at</span></span>

<span data-ttu-id="ea7b7-142">Microsoft. RTC. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri</span><span class="sxs-lookup"><span data-stu-id="ea7b7-142">Microsoft.Rtc.Management.SyntheticTransactions.SipSyntheticTransaction.TryRetri</span></span>

<span data-ttu-id="ea7b7-143">eveRegistrarPortFromTopology (Int32& registrarPortNumber)</span><span class="sxs-lookup"><span data-stu-id="ea7b7-143">eveRegistrarPortFromTopology(Int32& registrarPortNumber)</span></span>

<span data-ttu-id="ea7b7-144">FQDN de destino: atl-cs-001.litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="ea7b7-144">Target Fqdn : atl-cs-001.litwareinc.com</span></span>

<span data-ttu-id="ea7b7-145">Resultado: error</span><span class="sxs-lookup"><span data-stu-id="ea7b7-145">Result : Failure</span></span>

<span data-ttu-id="ea7b7-146">Latencia: 00:00:00</span><span class="sxs-lookup"><span data-stu-id="ea7b7-146">Latency : 00:00:00</span></span>

<span data-ttu-id="ea7b7-147">Mensaje de error: 10060, error al intentar la conexión porque la persona conectada</span><span class="sxs-lookup"><span data-stu-id="ea7b7-147">Error Message : 10060, A connection attempt failed because the connected party</span></span>

<span data-ttu-id="ea7b7-148">no respondió correctamente después de un período de tiempo, o</span><span class="sxs-lookup"><span data-stu-id="ea7b7-148">did not properly respond after a period of time, or</span></span>

<span data-ttu-id="ea7b7-149">error en la conexión establecida porque el host conectado tiene</span><span class="sxs-lookup"><span data-stu-id="ea7b7-149">established connection failed because connected host has</span></span>

<span data-ttu-id="ea7b7-150">Error al responder 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="ea7b7-150">failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="ea7b7-151">Excepción interna: error en el intento de conexión porque el</span><span class="sxs-lookup"><span data-stu-id="ea7b7-151">Inner Exception:A connection attempt failed because the</span></span>

<span data-ttu-id="ea7b7-152">la parte conectada no respondió correctamente después de un período de</span><span class="sxs-lookup"><span data-stu-id="ea7b7-152">connected party did not properly respond after a period of</span></span>

<span data-ttu-id="ea7b7-153">hora o error de conexión establecida porque el host conectado</span><span class="sxs-lookup"><span data-stu-id="ea7b7-153">time, or established connection failed because connected host</span></span>

<span data-ttu-id="ea7b7-154">Error al responder 10.188.116.96:5061</span><span class="sxs-lookup"><span data-stu-id="ea7b7-154">has failed to respond 10.188.116.96:5061</span></span>

<span data-ttu-id="ea7b7-155">Diagnóstico</span><span class="sxs-lookup"><span data-stu-id="ea7b7-155">Diagnosis :</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="ea7b7-156">Razones por las que se ha producido un error en la prueba</span><span class="sxs-lookup"><span data-stu-id="ea7b7-156">Reasons why the test might have failed</span></span>

<span data-ttu-id="ea7b7-157">Estas son algunas de las razones comunes por las que **Test-CsUnifiedContactStore** podría fallar:</span><span class="sxs-lookup"><span data-stu-id="ea7b7-157">Here are some common reasons why **Test-CsUnifiedContactStore** might fail:</span></span>

  - <span data-ttu-id="ea7b7-158">Se proporcionó un valor de parámetro incorrecto.</span><span class="sxs-lookup"><span data-stu-id="ea7b7-158">An incorrect parameter value was supplied.</span></span> <span data-ttu-id="ea7b7-159">Si se usa, los parámetros opcionales deben estar configurados correctamente o se producirá un error en la prueba.</span><span class="sxs-lookup"><span data-stu-id="ea7b7-159">If used, the optional parameters must be configured correctly or the test will fail.</span></span> <span data-ttu-id="ea7b7-160">Vuelva a ejecutar el comando sin los parámetros opcionales y vea si se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="ea7b7-160">Rerun the command without the optional parameters and see whether that succeeds.</span></span>

  - <span data-ttu-id="ea7b7-161">No se pudo conectar con el almacén de contactos unificado y no se pudo recuperar un contacto para el usuario.</span><span class="sxs-lookup"><span data-stu-id="ea7b7-161">Connect to the unified contact store failed, and the attempt to retrieve a contact for the user was not possible.</span></span> <span data-ttu-id="ea7b7-162">Es posible que haya problemas de conectividad de red.</span><span class="sxs-lookup"><span data-stu-id="ea7b7-162">There may be network connectivity issues.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ea7b7-163">Vea también</span><span class="sxs-lookup"><span data-stu-id="ea7b7-163">See Also</span></span>


[<span data-ttu-id="ea7b7-164">New-CsUserServicesPolicy</span><span class="sxs-lookup"><span data-stu-id="ea7b7-164">New-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsUserServicesPolicy)  
[<span data-ttu-id="ea7b7-165">Set-CsUserServicesPolicy</span><span class="sxs-lookup"><span data-stu-id="ea7b7-165">Set-CsUserServicesPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsUserServicesPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

