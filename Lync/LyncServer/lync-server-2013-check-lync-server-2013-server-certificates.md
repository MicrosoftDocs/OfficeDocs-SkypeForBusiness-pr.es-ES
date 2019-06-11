---
title: 'Lync Server 2013: comprobar certificados de servidor de Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Check server certificates
ms:assetid: 7b0474e8-0efe-47f0-84eb-a1ba575dabfd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725210(v=OCS.15)
ms:contentKeyID: 63969620
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dced86c93b7ec35cb410601f1d72720e25d156b0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842586"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="check-lync-server-2013-server-certificates"></a><span data-ttu-id="bf8c6-102">Comprobar certificados de servidor de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bf8c6-102">Check Lync Server 2013 server certificates</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bf8c6-103">_**Última modificación del tema:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="bf8c6-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bf8c6-104">Programación de verificación</span><span class="sxs-lookup"><span data-stu-id="bf8c6-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="bf8c6-105">Cada mes</span><span class="sxs-lookup"><span data-stu-id="bf8c6-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf8c6-106">Herramienta de prueba</span><span class="sxs-lookup"><span data-stu-id="bf8c6-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="bf8c6-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="bf8c6-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bf8c6-108">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="bf8c6-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="bf8c6-109">Al ejecutarse de forma local con el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="bf8c6-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="bf8c6-110">Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol de RBAC que tenga permiso para ejecutar el cmdlet Get-CsCertificate.</span><span class="sxs-lookup"><span data-stu-id="bf8c6-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Get-CsCertificate cmdlet.</span></span> <span data-ttu-id="bf8c6-111">Para ver una lista de todos los roles de RBAC que pueden usar este cmdlet, ejecute el siguiente comando en el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="bf8c6-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Get-CsCertificate&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="bf8c6-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="bf8c6-112">Description</span></span>

<span data-ttu-id="bf8c6-113">El cmdlet Get-CsCertificate le permite recuperar información acerca de cada uno de los certificados de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bf8c6-113">The Get-CsCertificate cmdlet enables you to retrieve information about each of your Lync Server certificates.</span></span> <span data-ttu-id="bf8c6-114">Esto es especialmente importante porque los certificados tienen una fecha de expiración integrada.</span><span class="sxs-lookup"><span data-stu-id="bf8c6-114">That’s especially important because certificates have a built-in expiration date.</span></span> <span data-ttu-id="bf8c6-115">Por ejemplo, los certificados emitidos de forma privada normalmente vencen después de 12 meses.</span><span class="sxs-lookup"><span data-stu-id="bf8c6-115">For example,, privately-issued certificates typically expire after 12 months.</span></span> <span data-ttu-id="bf8c6-116">Si alguno de los certificados de Lync Server vence, perderá la funcionalidad correspondiente hasta que se renueve o se reemplace el certificado.</span><span class="sxs-lookup"><span data-stu-id="bf8c6-116">If any of your Lync Server certificates expire then you'll lose the accompanying functionality until that certificate is renewed or replaced.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="bf8c6-117">Ejecutar la prueba</span><span class="sxs-lookup"><span data-stu-id="bf8c6-117">Running the test</span></span>

<span data-ttu-id="bf8c6-118">Para obtener información sobre cada uno de los certificados de Lync Server, simplemente ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="bf8c6-118">To return information about each of your Lync Server certificates just run the following command:</span></span>

`Get-CsCertificate`

<span data-ttu-id="bf8c6-119">O bien, puede filtrar la información del certificado devuelto según la fecha de expiración.</span><span class="sxs-lookup"><span data-stu-id="bf8c6-119">Or, you can filter the return certificate information based on expiration date.</span></span> <span data-ttu-id="bf8c6-120">Por ejemplo, este comando limita los datos devueltos a certificados que vencen (no se pueden usar después) 1 de junio de 2014:</span><span class="sxs-lookup"><span data-stu-id="bf8c6-120">For example, this command limits the returned data to certificates that expire (cannot be used after) June 1, 2014:</span></span>

`Get-CsCertificate | Where-Object {$_.NotAfter -lt "6/1/2014"}`

<span data-ttu-id="bf8c6-121">Para obtener más información, consulte la documentación de ayuda del cmdlet Get-CsCertificate.</span><span class="sxs-lookup"><span data-stu-id="bf8c6-121">For more information, see the Help documentation for the Get-CsCertificate cmdlet.</span></span>

<span data-ttu-id="bf8c6-122">Tenga en cuenta que, aunque exista el cmdlet test-CsCertificateConfiguration, no es muy útil para los administradores.</span><span class="sxs-lookup"><span data-stu-id="bf8c6-122">Note that, although the Test-CsCertificateConfiguration cmdlet exists, it is not very useful to administrators.</span></span> <span data-ttu-id="bf8c6-123">(En su lugar, el Asistente de certificados usa principalmente ese cmdlet). Aunque el cmdlet funcione, la información que devuelve es de un valor mínimo, tal y como se muestra en el siguiente ejemplo de salida:</span><span class="sxs-lookup"><span data-stu-id="bf8c6-123">(Instead, that cmdlet is primarily used by the Certificate wizard.) Although the cmdlet works, the information that it returns is of minimal value as shown in the following output example:</span></span>

<span data-ttu-id="bf8c6-124">Uso de la huella digital</span><span class="sxs-lookup"><span data-stu-id="bf8c6-124">Thumbprint Use</span></span>

<span data-ttu-id="bf8c6-125">\---------- ---</span><span class="sxs-lookup"><span data-stu-id="bf8c6-125"></span></span>

<span data-ttu-id="bf8c6-126">A9D51A2911C74FABFF7F2A8A994B20857D399107 predeterminado</span><span class="sxs-lookup"><span data-stu-id="bf8c6-126">A9D51A2911C74FABFF7F2A8A994B20857D399107 Default</span></span>

</div>

<div>

## <a name="reviewing-the-output"></a><span data-ttu-id="bf8c6-127">Revisar la salida</span><span class="sxs-lookup"><span data-stu-id="bf8c6-127">Reviewing the output</span></span>

<span data-ttu-id="bf8c6-128">El cmdlet Get-CsCertificate devuelve información similar a la siguiente para cada uno de los certificados de Lync Server:</span><span class="sxs-lookup"><span data-stu-id="bf8c6-128">The Get-CsCertificate cmdlet returns information similar to the following for each of your Lync Server certificates:</span></span>

<span data-ttu-id="bf8c6-129">Emisor: CN = FabrikamCA</span><span class="sxs-lookup"><span data-stu-id="bf8c6-129">Issuer : CN=FabrikamCA</span></span>

<span data-ttu-id="bf8c6-130">Nopérezer: 12/28/2015 3:35:41 PM</span><span class="sxs-lookup"><span data-stu-id="bf8c6-130">NotAfter : 12/28/2015 3:35:41 PM</span></span>

<span data-ttu-id="bf8c6-131">NotBefore: 1/2/2014 12:49:37 PM</span><span class="sxs-lookup"><span data-stu-id="bf8c6-131">NotBefore : 1/2/2014 12:49:37 PM</span></span>

<span data-ttu-id="bf8c6-132">SerialNumber: 611BB01200000000000C</span><span class="sxs-lookup"><span data-stu-id="bf8c6-132">SerialNumber : 611BB01200000000000C</span></span>

<span data-ttu-id="bf8c6-133">Asunto: CN = LYNC-SE.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="bf8c6-133">Subject : CN=LYNC-SE.fabrikam.com</span></span>

<span data-ttu-id="bf8c6-134">AlternativeNames: {sip.fabrikam.com, LYNC-SE.fabrikam.com,</span><span class="sxs-lookup"><span data-stu-id="bf8c6-134">AlternativeNames : {sip.fabrikam.com, LYNC-SE.fabrikam.com,</span></span>

<span data-ttu-id="bf8c6-135">meet.fabrikam.com, admin.fabrikam.com...}</span><span class="sxs-lookup"><span data-stu-id="bf8c6-135">meet.fabrikam.com, admin.fabrikam.com...}</span></span>

<span data-ttu-id="bf8c6-136">Huella digital: A9D51A2911C74FABFF7F2A8A994B20857D399107</span><span class="sxs-lookup"><span data-stu-id="bf8c6-136">Thumbprint : A9D51A2911C74FABFF7F2A8A994B20857D399107</span></span>

<span data-ttu-id="bf8c6-137">Uso: predeterminado</span><span class="sxs-lookup"><span data-stu-id="bf8c6-137">Use : Default</span></span>

<span data-ttu-id="bf8c6-138">Como regla general, los principales problemas relacionados con los certificados de Lync Server incluyen fechas y horas, como cuando los certificados surten efecto (NotBefore) o cuando vencen (novalente).</span><span class="sxs-lookup"><span data-stu-id="bf8c6-138">As a rule, the top issues involving Lync Server certificates involve dates and times, such as when certificates take effect (NotBefore) or when they expire (NotAfter).</span></span> <span data-ttu-id="bf8c6-139">Como estas fechas y horas son tan importantes, es posible que desee limitar los datos devueltos a información como el uso de certificados, el número de serie del certificado y la fecha de expiración del certificado; después, puede revisar rápidamente todos los certificados y cuándo vencerán.</span><span class="sxs-lookup"><span data-stu-id="bf8c6-139">Because these dates and times are so important, you might want to limit the returned data to information such as the certificate use, the certificate serial number, and the certificate expiration date; then you can quickly review all the certificates and when they will expire.</span></span> <span data-ttu-id="bf8c6-140">Para obtener solo esa información, use el comando junto con las opciones que se muestran:</span><span class="sxs-lookup"><span data-stu-id="bf8c6-140">To return just that information, use the command together with the options as shown:</span></span>

`Get-CsCertificate | Select-Object Use, SerialNumber, NotAfter | Sort-Object NotAfter`

<span data-ttu-id="bf8c6-141">Ese comando devuelve datos similares a los siguientes, con los certificados ordenados por su fecha de expiración:</span><span class="sxs-lookup"><span data-stu-id="bf8c6-141">That command returns data similar to the following, with the certificates sorted in order of their expiration date:</span></span>

<span data-ttu-id="bf8c6-142">Usar SerialNumber alpérezer</span><span class="sxs-lookup"><span data-stu-id="bf8c6-142">Use SerialNumber NotAfter</span></span>

<span data-ttu-id="bf8c6-143">\--- ------------ --------</span><span class="sxs-lookup"><span data-stu-id="bf8c6-143"></span></span>

<span data-ttu-id="bf8c6-144">611BB01200000000000C predeterminados 12/28/2015 3:35:41 P.M.</span><span class="sxs-lookup"><span data-stu-id="bf8c6-144">Default 611BB01200000000000C 12/28/2015 3:35:41 PM</span></span>

<span data-ttu-id="bf8c6-145">WebServicesInteral 32980AA20BBB20000191 02/15/2016 2:16:12 PM</span><span class="sxs-lookup"><span data-stu-id="bf8c6-145">WebServicesInteral 32980AA20BBB20000191 02/15/2016 2:16:12 PM</span></span>

<span data-ttu-id="bf8c6-146">WebServicesExternal 0451B012003872651A0C 02/20/2016 7:11:58 AM</span><span class="sxs-lookup"><span data-stu-id="bf8c6-146">WebServicesExternal 0451B012003872651A0C 02/20/2016 7:11:58 AM</span></span>

<span data-ttu-id="bf8c6-147">Si tiene problemas con el certificado, es posible que desee revisar el AlternativeNames configurado para un certificado.</span><span class="sxs-lookup"><span data-stu-id="bf8c6-147">If you have certificate problems, you might want to review the AlternativeNames configured for a certificate.</span></span> <span data-ttu-id="bf8c6-148">A primera vista, parece ser un problema.</span><span class="sxs-lookup"><span data-stu-id="bf8c6-148">At first glance, that seems to be a problem.</span></span> <span data-ttu-id="bf8c6-149">De forma predeterminada, y según el tamaño de la ventana de la consola, Get-CsCertificate podría no mostrar todos los nombres:</span><span class="sxs-lookup"><span data-stu-id="bf8c6-149">By default, and depending on the size of your console window, Get-CsCertificate might not be able to display all the names:</span></span>

<span data-ttu-id="bf8c6-150">AlternativeNames: {sip.fabrikam.com, LYNC.fabrikam.com,</span><span class="sxs-lookup"><span data-stu-id="bf8c6-150">AlternativeNames : {sip.fabrikam.com, LYNC.fabrikam.com,</span></span>

<span data-ttu-id="bf8c6-151">meet.fabrikam.com, admin. Fabrika...}</span><span class="sxs-lookup"><span data-stu-id="bf8c6-151">meet.fabrikam.com, admin.fabrika...}</span></span>

<span data-ttu-id="bf8c6-152">Para ver todos los nombres alternativos asignados a un certificado, use un comando similar a este:</span><span class="sxs-lookup"><span data-stu-id="bf8c6-152">To see all the alternative names assigned to a certificate use a command similar to this one:</span></span>

`Get-CsCertificate | Where-Object {$_.SerialNumber -eq "611BB01200000000000C"} | Select-Object -ExpandProperty AlternativeNames`

<span data-ttu-id="bf8c6-153">Que le mostrarán todos los nombres alternativos en el certificado:</span><span class="sxs-lookup"><span data-stu-id="bf8c6-153">That should show you all of the alternative names on the certificate:</span></span>

<span data-ttu-id="bf8c6-154">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="bf8c6-154">sip.fabrikam.com</span></span>

<span data-ttu-id="bf8c6-155">LYNC.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="bf8c6-155">LYNC.fabrikam.com</span></span>

<span data-ttu-id="bf8c6-156">meet.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="bf8c6-156">meet.fabrikam.com</span></span>

<span data-ttu-id="bf8c6-157">admin.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="bf8c6-157">admin.fabrikam.com</span></span>

<span data-ttu-id="bf8c6-158">LYNC-SE.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="bf8c6-158">LYNC-SE.fabrikam.com</span></span>

<span data-ttu-id="bf8c6-159">Dialin.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="bf8c6-159">Dialin.fabrikam.com</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bf8c6-160">Vea también</span><span class="sxs-lookup"><span data-stu-id="bf8c6-160">See Also</span></span>


[<span data-ttu-id="bf8c6-161">Get-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="bf8c6-161">Get-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

