---
title: 'Lync Server 2013: comprobar los certificados de servidor de Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Check server certificates
ms:assetid: 7b0474e8-0efe-47f0-84eb-a1ba575dabfd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725210(v=OCS.15)
ms:contentKeyID: 63969620
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4f5e8465ce7f0343bea96ee6f0613b8725d0e540
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502707"
---
# <a name="check-lync-server-2013-server-certificates"></a><span data-ttu-id="48283-102">Comprobar los certificados de servidor de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="48283-102">Check Lync Server 2013 server certificates</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="48283-103">_**Última modificación del tema:** 2014-11-01_</span><span class="sxs-lookup"><span data-stu-id="48283-103">_**Topic Last Modified:** 2014-11-01_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="48283-104">Programación de comprobación</span><span class="sxs-lookup"><span data-stu-id="48283-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="48283-105">Mensualmente</span><span class="sxs-lookup"><span data-stu-id="48283-105">Monthly</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48283-106">Herramienta de prueba</span><span class="sxs-lookup"><span data-stu-id="48283-106">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="48283-107">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="48283-107">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48283-108">Permisos necesarios</span><span class="sxs-lookup"><span data-stu-id="48283-108">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="48283-109">Cuando se ejecuta de forma local mediante el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="48283-109">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="48283-110">Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet Get-CsCertificate.</span><span class="sxs-lookup"><span data-stu-id="48283-110">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Get-CsCertificate cmdlet.</span></span> <span data-ttu-id="48283-111">Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="48283-111">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Get-CsCertificate&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="48283-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="48283-112">Description</span></span>

<span data-ttu-id="48283-113">El cmdlet Get-CsCertificate permite recuperar información acerca de cada uno de los certificados de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="48283-113">The Get-CsCertificate cmdlet enables you to retrieve information about each of your Lync Server certificates.</span></span> <span data-ttu-id="48283-114">Esto es especialmente importante porque los certificados tienen una fecha de expiración integrada.</span><span class="sxs-lookup"><span data-stu-id="48283-114">That’s especially important because certificates have a built-in expiration date.</span></span> <span data-ttu-id="48283-115">Por ejemplo, los certificados emitidos de forma privada suelen expirar después de 12 meses.</span><span class="sxs-lookup"><span data-stu-id="48283-115">For example,, privately-issued certificates typically expire after 12 months.</span></span> <span data-ttu-id="48283-116">Si alguno de los certificados de Lync Server expira, perderá la funcionalidad adjunta hasta que el certificado se renueve o se reemplace.</span><span class="sxs-lookup"><span data-stu-id="48283-116">If any of your Lync Server certificates expire then you'll lose the accompanying functionality until that certificate is renewed or replaced.</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="48283-117">Ejecutar la prueba</span><span class="sxs-lookup"><span data-stu-id="48283-117">Running the test</span></span>

<span data-ttu-id="48283-118">Para obtener información acerca de cada uno de los certificados de Lync Server, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="48283-118">To return information about each of your Lync Server certificates just run the following command:</span></span>

`Get-CsCertificate`

<span data-ttu-id="48283-119">O bien, puede filtrar la información de los certificados de devolución según la fecha de expiración.</span><span class="sxs-lookup"><span data-stu-id="48283-119">Or, you can filter the return certificate information based on expiration date.</span></span> <span data-ttu-id="48283-120">Por ejemplo, este comando limita los datos devueltos a los certificados que expiran (no se puede usar después) el 1 de junio de 2014:</span><span class="sxs-lookup"><span data-stu-id="48283-120">For example, this command limits the returned data to certificates that expire (cannot be used after) June 1, 2014:</span></span>

`Get-CsCertificate | Where-Object {$_.NotAfter -lt "6/1/2014"}`

<span data-ttu-id="48283-121">Para obtener más información, consulte la documentación de ayuda del cmdlet Get-CsCertificate.</span><span class="sxs-lookup"><span data-stu-id="48283-121">For more information, see the Help documentation for the Get-CsCertificate cmdlet.</span></span>

<span data-ttu-id="48283-122">Tenga en cuenta que, aunque exista el cmdlet Test-CsCertificateConfiguration, no es muy útil para los administradores.</span><span class="sxs-lookup"><span data-stu-id="48283-122">Note that, although the Test-CsCertificateConfiguration cmdlet exists, it is not very useful to administrators.</span></span> <span data-ttu-id="48283-123">(En su lugar, el Asistente para certificados se usa principalmente con este cmdlet). Aunque el cmdlet funciona, la información que devuelve es de un valor mínimo, como se muestra en el siguiente ejemplo de salida:</span><span class="sxs-lookup"><span data-stu-id="48283-123">(Instead, that cmdlet is primarily used by the Certificate wizard.) Although the cmdlet works, the information that it returns is of minimal value as shown in the following output example:</span></span>

<span data-ttu-id="48283-124">Uso de la huella digital</span><span class="sxs-lookup"><span data-stu-id="48283-124">Thumbprint Use</span></span>

<span data-ttu-id="48283-125">\---------- ---</span><span class="sxs-lookup"><span data-stu-id="48283-125">\---------- ---</span></span>

<span data-ttu-id="48283-126">Valor predeterminado A9D51A2911C74FABFF7F2A8A994B20857D399107</span><span class="sxs-lookup"><span data-stu-id="48283-126">A9D51A2911C74FABFF7F2A8A994B20857D399107 Default</span></span>

</div>

<div>

## <a name="reviewing-the-output"></a><span data-ttu-id="48283-127">Revisión del resultado</span><span class="sxs-lookup"><span data-stu-id="48283-127">Reviewing the output</span></span>

<span data-ttu-id="48283-128">El cmdlet Get-CsCertificate devuelve información similar a la siguiente para cada uno de los certificados de Lync Server:</span><span class="sxs-lookup"><span data-stu-id="48283-128">The Get-CsCertificate cmdlet returns information similar to the following for each of your Lync Server certificates:</span></span>

<span data-ttu-id="48283-129">Issuer: CN = FabrikamCA</span><span class="sxs-lookup"><span data-stu-id="48283-129">Issuer : CN=FabrikamCA</span></span>

<span data-ttu-id="48283-130">Noolaetaer: 12/28/2015 3:35:41 PM</span><span class="sxs-lookup"><span data-stu-id="48283-130">NotAfter : 12/28/2015 3:35:41 PM</span></span>

<span data-ttu-id="48283-131">NotBefore: 1/2/2014 12:49:37 PM</span><span class="sxs-lookup"><span data-stu-id="48283-131">NotBefore : 1/2/2014 12:49:37 PM</span></span>

<span data-ttu-id="48283-132">SerialNumber: 611BB01200000000000C</span><span class="sxs-lookup"><span data-stu-id="48283-132">SerialNumber : 611BB01200000000000C</span></span>

<span data-ttu-id="48283-133">Asunto: CN = LYNC-SE.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="48283-133">Subject : CN=LYNC-SE.fabrikam.com</span></span>

<span data-ttu-id="48283-134">AlternativeNames: {sip.fabrikam.com, LYNC-SE.fabrikam.com,</span><span class="sxs-lookup"><span data-stu-id="48283-134">AlternativeNames : {sip.fabrikam.com, LYNC-SE.fabrikam.com,</span></span>

<span data-ttu-id="48283-135">meet.fabrikam.com, admin.fabrikam.com...}</span><span class="sxs-lookup"><span data-stu-id="48283-135">meet.fabrikam.com, admin.fabrikam.com...}</span></span>

<span data-ttu-id="48283-136">Huella digital: A9D51A2911C74FABFF7F2A8A994B20857D399107</span><span class="sxs-lookup"><span data-stu-id="48283-136">Thumbprint : A9D51A2911C74FABFF7F2A8A994B20857D399107</span></span>

<span data-ttu-id="48283-137">Uso: predeterminado</span><span class="sxs-lookup"><span data-stu-id="48283-137">Use : Default</span></span>

<span data-ttu-id="48283-138">Como regla general, los principales problemas relacionados con los certificados de Lync Server son fechas y horas, como cuando los certificados surten efecto (NotBefore) o cuando expiran (noolaetaer).</span><span class="sxs-lookup"><span data-stu-id="48283-138">As a rule, the top issues involving Lync Server certificates involve dates and times, such as when certificates take effect (NotBefore) or when they expire (NotAfter).</span></span> <span data-ttu-id="48283-139">Como estas fechas y horas son tan importantes, es posible que desee limitar los datos devueltos a información como el uso del certificado, el número de serie del certificado y la fecha de expiración del certificado; a continuación, puede revisar rápidamente todos los certificados y cuándo expirarán.</span><span class="sxs-lookup"><span data-stu-id="48283-139">Because these dates and times are so important, you might want to limit the returned data to information such as the certificate use, the certificate serial number, and the certificate expiration date; then you can quickly review all the certificates and when they will expire.</span></span> <span data-ttu-id="48283-140">Para devolver solo esa información, use el comando junto con las opciones, como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="48283-140">To return just that information, use the command together with the options as shown:</span></span>

`Get-CsCertificate | Select-Object Use, SerialNumber, NotAfter | Sort-Object NotAfter`

<span data-ttu-id="48283-141">Ese comando devuelve datos similares a los siguientes, con los certificados ordenados según su fecha de expiración:</span><span class="sxs-lookup"><span data-stu-id="48283-141">That command returns data similar to the following, with the certificates sorted in order of their expiration date:</span></span>

<span data-ttu-id="48283-142">Usar SerialNumber noolaetaer</span><span class="sxs-lookup"><span data-stu-id="48283-142">Use SerialNumber NotAfter</span></span>

<span data-ttu-id="48283-143">\--- ------------ --------</span><span class="sxs-lookup"><span data-stu-id="48283-143">\--- ------------ --------</span></span>

<span data-ttu-id="48283-144">Valor predeterminado 611BB01200000000000C 12/28/2015 3:35:41 PM</span><span class="sxs-lookup"><span data-stu-id="48283-144">Default 611BB01200000000000C 12/28/2015 3:35:41 PM</span></span>

<span data-ttu-id="48283-145">WebServicesInteral 32980AA20BBB20000191 02/15/2016 2:16:12 PM</span><span class="sxs-lookup"><span data-stu-id="48283-145">WebServicesInteral 32980AA20BBB20000191 02/15/2016 2:16:12 PM</span></span>

<span data-ttu-id="48283-146">WebServicesExternal 0451B012003872651A0C 02/20/2016 7:11:58 AM</span><span class="sxs-lookup"><span data-stu-id="48283-146">WebServicesExternal 0451B012003872651A0C 02/20/2016 7:11:58 AM</span></span>

<span data-ttu-id="48283-147">Si tiene problemas con el certificado, es posible que desee revisar la AlternativeNames configurada para un certificado.</span><span class="sxs-lookup"><span data-stu-id="48283-147">If you have certificate problems, you might want to review the AlternativeNames configured for a certificate.</span></span> <span data-ttu-id="48283-148">A primera vista, parece ser un problema.</span><span class="sxs-lookup"><span data-stu-id="48283-148">At first glance, that seems to be a problem.</span></span> <span data-ttu-id="48283-149">De forma predeterminada, y según el tamaño de la ventana de la consola, Get-CsCertificate posible que no pueda mostrar todos los nombres:</span><span class="sxs-lookup"><span data-stu-id="48283-149">By default, and depending on the size of your console window, Get-CsCertificate might not be able to display all the names:</span></span>

<span data-ttu-id="48283-150">AlternativeNames: {sip.fabrikam.com, LYNC.fabrikam.com,</span><span class="sxs-lookup"><span data-stu-id="48283-150">AlternativeNames : {sip.fabrikam.com, LYNC.fabrikam.com,</span></span>

<span data-ttu-id="48283-151">meet.fabrikam.com, admin. Fabrika...}</span><span class="sxs-lookup"><span data-stu-id="48283-151">meet.fabrikam.com, admin.fabrika...}</span></span>

<span data-ttu-id="48283-152">Para ver todos los nombres alternativos asignados a un certificado use un comando similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="48283-152">To see all the alternative names assigned to a certificate use a command similar to this one:</span></span>

`Get-CsCertificate | Where-Object {$_.SerialNumber -eq "611BB01200000000000C"} | Select-Object -ExpandProperty AlternativeNames`

<span data-ttu-id="48283-153">Eso debería mostrar todos los nombres alternativos en el certificado:</span><span class="sxs-lookup"><span data-stu-id="48283-153">That should show you all of the alternative names on the certificate:</span></span>

<span data-ttu-id="48283-154">sip.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="48283-154">sip.fabrikam.com</span></span>

<span data-ttu-id="48283-155">LYNC.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="48283-155">LYNC.fabrikam.com</span></span>

<span data-ttu-id="48283-156">meet.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="48283-156">meet.fabrikam.com</span></span>

<span data-ttu-id="48283-157">admin.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="48283-157">admin.fabrikam.com</span></span>

<span data-ttu-id="48283-158">LYNC-SE.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="48283-158">LYNC-SE.fabrikam.com</span></span>

<span data-ttu-id="48283-159">Dialin.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="48283-159">Dialin.fabrikam.com</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="48283-160">Consulte también</span><span class="sxs-lookup"><span data-stu-id="48283-160">See Also</span></span>


[<span data-ttu-id="48283-161">Get-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="48283-161">Get-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

