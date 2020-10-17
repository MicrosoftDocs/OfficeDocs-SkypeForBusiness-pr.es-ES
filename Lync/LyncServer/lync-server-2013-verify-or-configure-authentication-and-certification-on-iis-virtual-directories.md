---
title: 'Lync Server 2013: comprobar o configurar la autenticación y la certificación en los directorios virtuales de IIS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify or configure authentication and certification on IIS virtual directories
ms:assetid: 3ca90be0-1d64-447c-807a-3a2ee3bf625e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429702(v=OCS.15)
ms:contentKeyID: 48183883
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c07fc83680fd6b1d3f4d0d24429165ff9cc5ca65
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518617"
---
# <a name="verify-or-configure-authentication-and-certification-on-iis-virtual-directories-in-lync-server-2013"></a><span data-ttu-id="e94ae-102">Comprobar o configurar la autenticación y la certificación en directorios virtuales de IIS en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e94ae-102">Verify or configure authentication and certification on IIS virtual directories in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e94ae-103">_**Última modificación del tema:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="e94ae-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="e94ae-104">Use el siguiente procedimiento para configurar el certificado en los directorios virtuales de Internet Information Services (IIS) o comprobar que el certificado está configurado correctamente.</span><span class="sxs-lookup"><span data-stu-id="e94ae-104">Use the following procedure to configure the certificate on your Internet Information Services (IIS) virtual directories or verify that the certificate is configured correctly.</span></span> <span data-ttu-id="e94ae-105">Realice el procedimiento siguiente en cada servidor que ejecute IIS en el grupo de servidores interno de Lync Server y en el director opcional o en los servidores de grupos de directores.</span><span class="sxs-lookup"><span data-stu-id="e94ae-105">Perform the following procedure on each server running IIS in your internal Lync Server pool and the optional Director.or Director pool servers.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e94ae-106">El siguiente procedimiento define un procedimiento para solicitar un certificado combinado que se usa para todos los propósitos Lync Server, sitio Web interno y sitio web externo de IIS.</span><span class="sxs-lookup"><span data-stu-id="e94ae-106">The following procedure defines a procedure to request a combined certificate that is used for all purposes Lync Server, Internal Web Site and External Web Site in IIS.</span></span> <span data-ttu-id="e94ae-107">Lync Server 2010 incorporó un conjunto de cmdlets de Windows PowerShell de Shell de administración de Lync Server &nbsp; para el propósito expreso de administrar la solicitud de certificados, la importación y la asignación.</span><span class="sxs-lookup"><span data-stu-id="e94ae-107">Lync Server 2010 introduced a set of Lync Server Management Shell&nbsp;Windows PowerShell cmdlets for the express purpose of managing certificate request, import, and assignment.</span></span> <span data-ttu-id="e94ae-108">Este procedimiento supone que existe una entidad de certificación (CA) implementada internamente que puede procesar la solicitud.</span><span class="sxs-lookup"><span data-stu-id="e94ae-108">The procedure assumes that there is an internally deployed certification authority (CA) that can process the request.</span></span> <span data-ttu-id="e94ae-109">Si usa certificados públicos para los propósitos de Lync Server o la CA requiere una solicitud sin conexión, consulte la sintaxis detallada de este tema para obtener información sobre el parámetro – output.</span><span class="sxs-lookup"><span data-stu-id="e94ae-109">If you use public certificates for your Lync Server purposes, or your CA requires an offline request, see the detailed syntax in this topic for information on the –Output parameter.</span></span> <span data-ttu-id="e94ae-110"><A href="https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate">Solicitud-CsCertificate</A></span><span class="sxs-lookup"><span data-stu-id="e94ae-110"><A href="https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate">Request-CsCertificate</A></span></span>



</div>

<div>

## <a name="to-configure-authentication-and-certificates-on-iis-virtual-directories"></a><span data-ttu-id="e94ae-111">Configuración de la autenticación y los certificados en los directorios virtuales IIS</span><span class="sxs-lookup"><span data-stu-id="e94ae-111">To configure authentication and certificates on IIS virtual directories</span></span>

1.  <span data-ttu-id="e94ae-112">Para completar correctamente lo siguiente, debe iniciar sesión en el equipo (servidor front-end o director) donde están instalados los servicios web y ser un administrador local.</span><span class="sxs-lookup"><span data-stu-id="e94ae-112">To successfully complete the following, you must be logged on to the computer (Front End Server or Director) where the web services are installed and be a local administrator.</span></span> <span data-ttu-id="e94ae-113">Debe tener permisos de **lectura** e **inscripción** en la entidad de certificación a la que solicitará los certificados, si la entidad de certificación es la entidad de certificación de su organización.</span><span class="sxs-lookup"><span data-stu-id="e94ae-113">You must have the **read** and **enroll** permissions on the certification authority that you will be requesting certificates from, if the certification authority is your organization’s certification authority.</span></span> <span data-ttu-id="e94ae-114">No necesitará permisos de la entidad de certificación si configura y envía una solicitud de certificado fuera de línea.</span><span class="sxs-lookup"><span data-stu-id="e94ae-114">You do not need permissions to the certification authority if you will configure and send an offline certificate request.</span></span>

2.  <span data-ttu-id="e94ae-115">Haga clic en **Inicio**, seleccione **Todos los programas**, seleccione **Herramientas administrativas** y, a continuación, haga clic en **Administrador de Internet Information Services (IIS)**.</span><span class="sxs-lookup"><span data-stu-id="e94ae-115">Click **Start**, select **All Programs**, select **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>

3.  <span data-ttu-id="e94ae-p104">En **Administrador de Internet Information Services (IIS)**, seleccione **ServerName**. En **Vista Características**, seleccione **Certificados de servidor**, haga clic con el botón secundario y seleccione **Abrir característica**.</span><span class="sxs-lookup"><span data-stu-id="e94ae-p104">In **Internet Information Services (IIS) Manager**, select **ServerName**. In **Features View**, select **Server Certificates**, right-click and select **Open Feature**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="e94ae-p105">En la Vista Características de certificados de servidor, si hay certificados asignados al servidor, aparecerán aquí. Si hay un certificado que coincide con los requisitos del sitio web externo en IIS, puede volver a utilizar este certificado. Para ver un certificado, haga clic con el botón secundario en el certificado y seleccione <STRONG>Ver…</STRONG></span><span class="sxs-lookup"><span data-stu-id="e94ae-p105">In the Server Certificates Feature View, if there are certificates assigned to the server, they will appear here. If there is a certificate that matches the requirements for the External Web Site in IIS, you can re-use that certificate. To view a certificate, right-click the certificate and select <STRONG>View…</STRONG></span></span>

    
    </div>

4.  <span data-ttu-id="e94ae-121">En el servidor front-end o director para el que va a solicitar el certificado, haga clic en **Inicio**, seleccione **todos los programas**, seleccione **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="e94ae-121">On the Front End Server or Director that you are requesting the certificate for, click **Start**, select **All Programs**, select **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

5.  <span data-ttu-id="e94ae-122">En el shell de administración de Lync Server, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e94ae-122">In the Lync Server Management Shell, type the following:</span></span>
    
        Get-CsCertificate
    
    <span data-ttu-id="e94ae-p106">El resultado es una lista de los certificados que están actualmente en el servidor del almacén de certificados personales del equipo. Ten en cuenta que en el certificado combinado (es decir, donde los servicios web internos y los servicios web externos predeterminados están utilizando el mismo certificado), verá que la propiedad de uso se rellenará con predeterminado, WebServicesInternal y WebServicesExternal. Además, la propiedad huella digital será la misma para cada uno de los tipos de uso. En este ejemplo se muestra un resultado de ejemplo de Get-CsCertificate:</span><span class="sxs-lookup"><span data-stu-id="e94ae-p106">The output is a list of the certificates that are currently on the server in the Computer Personal certificate store. Note that in the combined certificate (that is, where the default, web services internal and web services external are using the same certificate) you will see that the Use property will be populated with Default, WebServicesInternal and WebServicesExternal. Also, the Thumbprint property will be the same for each of the Use types. An example output of Get-CsCertificate is shown in this example:</span></span>
    
    <span data-ttu-id="e94ae-127">![Get-CsCertificate información sobre el estado de scert actual](images/Gg429702.664f6326-6cd5-48e2-8235-fc3950ea43b4(OCS.15).jpg "Get-CsCertificate información sobre el estado scert actual")</span><span class="sxs-lookup"><span data-stu-id="e94ae-127">![Get-CsCertificate info on current scert status](images/Gg429702.664f6326-6cd5-48e2-8235-fc3950ea43b4(OCS.15).jpg "Get-CsCertificate info on current scert status")</span></span>

6.  <span data-ttu-id="e94ae-128">En el shell de administración de Lync Server, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e94ae-128">In the Lync Server Management Shell, type the following:</span></span>
    
        Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -CA <CA Server FQDN\CA Instance> -Verbose -DomainName "<FQDN entries to be added to the Subject Alternative Name>"
    
    <span data-ttu-id="e94ae-129">Donde el comando completo aparecería como en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e94ae-129">Where the full command would appear like following example:</span></span>
    
        Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -CA dc01.contoso.net\contoso-DC01-CA -Verbose -DomainName "LyncdiscoverInternal.Contoso.com,Lyncdiscover.Contoso.com"
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="e94ae-p107">De modo predeterminado, Request-CsCertificate rellenará el nombre de asunto con el nombre del servidor o del grupo de servidores y rellenará las entradas en el nombre alternativo del asunto con el servidor FQDN, el grupo de servidores FQDN, los FQDN de URL simples y los FQDN de los servicios web internos y externos. Esto lo hace haciendo referencia al documento de topología de su implementación. Si falta un valor y ha especificado el parámetro –Verbose, se le notificará que los valores calculados y reales de los nombres alternativos son diferentes, pero no se le informará de los valores que faltan. Se le proporcionará el valor calculado completo al que hace referencia el cmdlet. Utilice la cadena de nombres alternativos calculados en el resultado para volver a solicitar un nuevo certificado que incluya todos los valores</span><span class="sxs-lookup"><span data-stu-id="e94ae-p107">By default, Request-CsCertificate will populate the subject name with the server or pool name and populate entries in the subject alternative name with the server FQDN, pool FQDN, Simple URL FQDNs, and internal and external web services FQDNs. It does this by referencing to the topology document in your deployment. If there is a missing value and you have specified the –Verbose parameter, you will be notified that the computed and actual values for alternative names are different, but it does not inform you which values are missing. It does supply you with the entire computed value that the cmdlet references. Use the computed alternative names string in the output to re-request a new certificate that will include all values.</span></span>

    
    </div>
    
    <span data-ttu-id="e94ae-135">![Resultado de la solicitud del certificado mediante request-CsCertifica](images/Gg429702.9e59a657-fa75-4454-8fd3-57c81e829f7b(OCS.15).jpg "Resultado de la solicitud del certificado mediante Request-CsCertifica")</span><span class="sxs-lookup"><span data-stu-id="e94ae-135">![Output from cert request using Request-CsCertifica](images/Gg429702.9e59a657-fa75-4454-8fd3-57c81e829f7b(OCS.15).jpg "Output from cert request using Request-CsCertifica")</span></span>

7.  <span data-ttu-id="e94ae-136">En el shell de administración de Lync Server, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e94ae-136">In the Lync Server Management Shell, type the following:</span></span>
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Thumbprint of certificate to use>
    
    <span data-ttu-id="e94ae-137">Donde el comando completo aparecería como en el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e94ae-137">Where the full command would appear like following example:</span></span>
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint 466D9BB0E8B928B65AF38FA2D9F41E1B301ECE9D
    
    <span data-ttu-id="e94ae-138">para>El resultado del cmdlet Set-CsCertificate mostrará que se ha asignado el mismo certificado (identificado por la huella digital del certificado) para el uso predeterminado, WebServicesExternal y WebServicesInternal u</span><span class="sxs-lookup"><span data-stu-id="e94ae-138">The output from the Set-CsCertificate cmdlet will show that the same certificate (identified by the thumbprint of the certificate) is assigned for the Default, WebServicesExternal and WebServicesInternal usage.</span></span>
    
    <span data-ttu-id="e94ae-139">![Resultado de Set-CsCertificate en IIS WebExt](images/Gg429702.dd451c9d-7b49-4408-8071-c868cb1e678c(OCS.15).jpg "Resultado de Set-CsCertificate en IIS WebExt")</span><span class="sxs-lookup"><span data-stu-id="e94ae-139">![Output from Set-CsCertificate on IIS WebExt](images/Gg429702.dd451c9d-7b49-4408-8071-c868cb1e678c(OCS.15).jpg "Output from Set-CsCertificate on IIS WebExt")</span></span>

</div>

<div>

## <a name="to-verify-or-configure-authentication-and-certificates-on-iis-virtual-directories"></a><span data-ttu-id="e94ae-140">Para comprobar o configurar la autenticación y la certificación en directorios virtuales de IIS</span><span class="sxs-lookup"><span data-stu-id="e94ae-140">To verify or configure authentication and certificates on IIS virtual directories</span></span>

1.  <span data-ttu-id="e94ae-141">Haga clic en **Inicio**, elija **Todos los programas**, elija **Herramientas administrativas** y, a continuación, haga clic en **Administrador de Internet Information Services (IIS)**.</span><span class="sxs-lookup"><span data-stu-id="e94ae-141">Click **Start**, select **All Programs**, select **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>

2.  <span data-ttu-id="e94ae-142">En el **Administrador de Internet Information Services (IIS)**, expanda **ServerName**y, a continuación, expanda **sitios**.</span><span class="sxs-lookup"><span data-stu-id="e94ae-142">In **Internet Information Services (IIS) Manager**, expand **ServerName**, and then expand **Sites**.</span></span>

3.  <span data-ttu-id="e94ae-143">Haga clic con el botón secundario en **Sitio web externo de Lync Server** y, a continuación, haga clic en **Modificar enlaces**</span><span class="sxs-lookup"><span data-stu-id="e94ae-143">Right-click **Lync Server External Web Site**, and then click **Edit Bindings**</span></span>

4.  <span data-ttu-id="e94ae-144">Compruebe que https está asociado al puerto 4443 y haga clic en **https**.</span><span class="sxs-lookup"><span data-stu-id="e94ae-144">Verify that https is associated with port 4443, and then click **https**.</span></span>

5.  <span data-ttu-id="e94ae-145">Seleccione la entrada HTTPS, haga clic en **Editar**y, a continuación, compruebe que Lync Server WebServicesExternalCertificate está enlazado a este protocolo.</span><span class="sxs-lookup"><span data-stu-id="e94ae-145">Select the HTTPS entry, click **Edit**, and then verify that Lync Server WebServicesExternalCertificate is bound to this protocol.</span></span> <span data-ttu-id="e94ae-146">Compare la huella digital del cmdlet Set-CsCertificate para asegurar que el certificado esperado está correctamente asociado con el enlace HTTPS.</span><span class="sxs-lookup"><span data-stu-id="e94ae-146">Compare the thumbprint from the Set-CsCertificate cmdlet to ensure that the expected certificate is correctly associated with the HTTPS binding.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e94ae-147">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e94ae-147">See Also</span></span>


[<span data-ttu-id="e94ae-148">Get-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="e94ae-148">Get-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCertificate)  
[<span data-ttu-id="e94ae-149">Set-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="e94ae-149">Set-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

