---
title: 'Lync Server 2013: Comprobar o configurar la autenticación y la certificación en directorios virtuales IIS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Verify or configure authentication and certification on IIS virtual directories
ms:assetid: 3ca90be0-1d64-447c-807a-3a2ee3bf625e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429702(v=OCS.15)
ms:contentKeyID: 48183883
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0ae692f788d906d01852990490ace01f67eebe63
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850142"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-or-configure-authentication-and-certification-on-iis-virtual-directories-in-lync-server-2013"></a><span data-ttu-id="d314f-102">Comprobar o configurar la autenticación y la certificación en directorios virtuales IIS en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d314f-102">Verify or configure authentication and certification on IIS virtual directories in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d314f-103">_**Última modificación del tema:** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="d314f-103">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="d314f-104">Use el procedimiento siguiente para configurar el certificado en los directorios virtuales de servicios de Internet Information Server (IIS) o comprobar que el certificado está configurado correctamente.</span><span class="sxs-lookup"><span data-stu-id="d314f-104">Use the following procedure to configure the certificate on your Internet Information Services (IIS) virtual directories or verify that the certificate is configured correctly.</span></span> <span data-ttu-id="d314f-105">Realice el siguiente procedimiento en cada servidor que ejecute IIS en el grupo de servidores de Lync interno y en el director opcional. o servidores de grupo de directores.</span><span class="sxs-lookup"><span data-stu-id="d314f-105">Perform the following procedure on each server running IIS in your internal Lync Server pool and the optional Director.or Director pool servers.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="d314f-106">El procedimiento siguiente define un procedimiento para solicitar un certificado combinado que se usa para todos los propósitos de Lync Server, sitio Web interno y sitio web externo en IIS.</span><span class="sxs-lookup"><span data-stu-id="d314f-106">The following procedure defines a procedure to request a combined certificate that is used for all purposes Lync Server, Internal Web Site and External Web Site in IIS.</span></span> <span data-ttu-id="d314f-107">Lync Server 2010 presentó un conjunto de cmdlets de Windows&nbsp;PowerShell de Shell de administración de Lync Server para la administración de solicitudes de certificados, importaciones y asignaciones.</span><span class="sxs-lookup"><span data-stu-id="d314f-107">Lync Server 2010 introduced a set of Lync Server Management Shell&nbsp;Windows PowerShell cmdlets for the express purpose of managing certificate request, import, and assignment.</span></span> <span data-ttu-id="d314f-108">En el procedimiento se supone que hay una entidad de certificación (CA) implementada internamente que puede procesar la solicitud.</span><span class="sxs-lookup"><span data-stu-id="d314f-108">The procedure assumes that there is an internally deployed certification authority (CA) that can process the request.</span></span> <span data-ttu-id="d314f-109">Si usa certificados públicos para sus propósitos de Lync Server, o si su CA requiere una solicitud sin conexión, consulte la sintaxis detallada de este tema para obtener información sobre el parámetro-output.</span><span class="sxs-lookup"><span data-stu-id="d314f-109">If you use public certificates for your Lync Server purposes, or your CA requires an offline request, see the detailed syntax in this topic for information on the –Output parameter.</span></span> <span data-ttu-id="d314f-110"><A href="https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate">Solicitud-CsCertificate</A></span><span class="sxs-lookup"><span data-stu-id="d314f-110"><A href="https://docs.microsoft.com/powershell/module/skype/Request-CsCertificate">Request-CsCertificate</A></span></span>



</div>

<div>

## <a name="to-configure-authentication-and-certificates-on-iis-virtual-directories"></a><span data-ttu-id="d314f-111">Para configurar la autenticación y los certificados en directorios virtuales de IIS</span><span class="sxs-lookup"><span data-stu-id="d314f-111">To configure authentication and certificates on IIS virtual directories</span></span>

1.  <span data-ttu-id="d314f-112">Para completar correctamente lo siguiente, debe haber iniciado sesión en el equipo (servidor front-end o director) donde están instalados los servicios web y ser administradores locales.</span><span class="sxs-lookup"><span data-stu-id="d314f-112">To successfully complete the following, you must be logged on to the computer (Front End Server or Director) where the web services are installed and be a local administrator.</span></span> <span data-ttu-id="d314f-113">Debe tener permisos de **lectura** e **inscripción** en la entidad de certificación de la que va a solicitar certificados, si la entidad emisora de certificados es la entidad de certificación de su organización.</span><span class="sxs-lookup"><span data-stu-id="d314f-113">You must have the **read** and **enroll** permissions on the certification authority that you will be requesting certificates from, if the certification authority is your organization’s certification authority.</span></span> <span data-ttu-id="d314f-114">No necesita permisos para la entidad emisora de certificados si va a configurar y enviar una solicitud de certificado sin conexión.</span><span class="sxs-lookup"><span data-stu-id="d314f-114">You do not need permissions to the certification authority if you will configure and send an offline certificate request.</span></span>

2.  <span data-ttu-id="d314f-115">Haga clic en **Inicio**, seleccione **todos los programas**, **herramientas administrativas**y, a continuación, haga clic en **Administrador de Internet Information Services (IIS)**.</span><span class="sxs-lookup"><span data-stu-id="d314f-115">Click **Start**, select **All Programs**, select **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>

3.  <span data-ttu-id="d314f-116">En el **Administrador de Internet Information Services (IIS)**, seleccione **ServerName**.</span><span class="sxs-lookup"><span data-stu-id="d314f-116">In **Internet Information Services (IIS) Manager**, select **ServerName**.</span></span> <span data-ttu-id="d314f-117">En la **vista características**, seleccione **certificados de servidor**, haga clic con el botón derecho y seleccione **abrir característica**.</span><span class="sxs-lookup"><span data-stu-id="d314f-117">In **Features View**, select **Server Certificates**, right-click and select **Open Feature**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="d314f-118">En la vista características de certificados de servidor, si hay certificados asignados al servidor, aparecerán aquí.</span><span class="sxs-lookup"><span data-stu-id="d314f-118">In the Server Certificates Feature View, if there are certificates assigned to the server, they will appear here.</span></span> <span data-ttu-id="d314f-119">Si hay un certificado que cumpla los requisitos para el sitio web externo en IIS, puede volver a usarlo.</span><span class="sxs-lookup"><span data-stu-id="d314f-119">If there is a certificate that matches the requirements for the External Web Site in IIS, you can re-use that certificate.</span></span> <span data-ttu-id="d314f-120">Para ver un certificado, haga clic con el botón derecho en el certificado y seleccione <STRONG>ver...</STRONG></span><span class="sxs-lookup"><span data-stu-id="d314f-120">To view a certificate, right-click the certificate and select <STRONG>View…</STRONG></span></span>

    
    </div>

4.  <span data-ttu-id="d314f-121">En el servidor front-end o director para el que va a solicitar el certificado, haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="d314f-121">On the Front End Server or Director that you are requesting the certificate for, click **Start**, select **All Programs**, select **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

5.  <span data-ttu-id="d314f-122">En el shell de administración de Lync Server, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d314f-122">In the Lync Server Management Shell, type the following:</span></span>
    
        Get-CsCertificate
    
    <span data-ttu-id="d314f-123">El resultado es una lista de los certificados que se encuentran actualmente en el servidor del almacén de certificados personal del equipo.</span><span class="sxs-lookup"><span data-stu-id="d314f-123">The output is a list of the certificates that are currently on the server in the Computer Personal certificate store.</span></span> <span data-ttu-id="d314f-124">Tenga en cuenta que en el certificado combinado (es decir, cuando el valor predeterminado, servicios Web internos y servicios web externos estén usando el mismo certificado) verá que la propiedad use se rellenará con default, WebServicesInternal y WebServicesExternal.</span><span class="sxs-lookup"><span data-stu-id="d314f-124">Note that in the combined certificate (that is, where the default, web services internal and web services external are using the same certificate) you will see that the Use property will be populated with Default, WebServicesInternal and WebServicesExternal.</span></span> <span data-ttu-id="d314f-125">Además, la propiedad Thumbprint será la misma para cada uno de los tipos de uso.</span><span class="sxs-lookup"><span data-stu-id="d314f-125">Also, the Thumbprint property will be the same for each of the Use types.</span></span> <span data-ttu-id="d314f-126">En este ejemplo se muestra un ejemplo de la salida de Get-CsCertificate:</span><span class="sxs-lookup"><span data-stu-id="d314f-126">An example output of Get-CsCertificate is shown in this example:</span></span>
    
    <span data-ttu-id="d314f-127">![Get-CsCertificate información sobre el estado actual de scert] (images/Gg429702.664f6326-6cd5-48e2-8235-fc3950ea43b4(OCS.15).jpg "Get-CsCertificate información sobre el estado actual de scert")</span><span class="sxs-lookup"><span data-stu-id="d314f-127">![Get-CsCertificate info on current scert status](images/Gg429702.664f6326-6cd5-48e2-8235-fc3950ea43b4(OCS.15).jpg "Get-CsCertificate info on current scert status")</span></span>

6.  <span data-ttu-id="d314f-128">En el shell de administración de Lync Server, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d314f-128">In the Lync Server Management Shell, type the following:</span></span>
    
        Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -CA <CA Server FQDN\CA Instance> -Verbose -DomainName "<FQDN entries to be added to the Subject Alternative Name>"
    
    <span data-ttu-id="d314f-129">Donde el comando completo tendría el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d314f-129">Where the full command would appear like following example:</span></span>
    
        Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -CA dc01.contoso.net\contoso-DC01-CA -Verbose -DomainName "LyncdiscoverInternal.Contoso.com,Lyncdiscover.Contoso.com"
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="d314f-130">De forma predeterminada, Request-CsCertificate rellenará el nombre del asunto con el nombre del servidor o grupo de servidores y llenará las entradas en el nombre de asunto alternativo con el servidor FQDN, FQDN del grupo, FQDN de dirección URL simple y FQDN de los servicios Web internos y externos.</span><span class="sxs-lookup"><span data-stu-id="d314f-130">By default, Request-CsCertificate will populate the subject name with the server or pool name and populate entries in the subject alternative name with the server FQDN, pool FQDN, Simple URL FQDNs, and internal and external web services FQDNs.</span></span> <span data-ttu-id="d314f-131">Para ello, hace referencia al documento de topología de su implementación.</span><span class="sxs-lookup"><span data-stu-id="d314f-131">It does this by referencing to the topology document in your deployment.</span></span> <span data-ttu-id="d314f-132">Si falta un valor y ha especificado el parámetro – verbose, se le notificará que los valores calculados y reales de los nombres alternativos son diferentes, pero no le informan los valores que faltan.</span><span class="sxs-lookup"><span data-stu-id="d314f-132">If there is a missing value and you have specified the –Verbose parameter, you will be notified that the computed and actual values for alternative names are different, but it does not inform you which values are missing.</span></span> <span data-ttu-id="d314f-133">Le proporciona el valor calculado completo al que hace referencia el cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d314f-133">It does supply you with the entire computed value that the cmdlet references.</span></span> <span data-ttu-id="d314f-134">Use la cadena de nombres alternativos calculados en la salida para volver a solicitar un nuevo certificado que incluirá todos los valores.</span><span class="sxs-lookup"><span data-stu-id="d314f-134">Use the computed alternative names string in the output to re-request a new certificate that will include all values.</span></span>

    
    </div>
    
    <span data-ttu-id="d314f-135">![Resultado de la solicitud del certificado mediante la solicitud-CsCertifica] (images/Gg429702.9e59a657-fa75-4454-8fd3-57c81e829f7b(OCS.15).jpg "Resultado de la solicitud del certificado mediante la solicitud-CsCertifica")</span><span class="sxs-lookup"><span data-stu-id="d314f-135">![Output from cert request using Request-CsCertifica](images/Gg429702.9e59a657-fa75-4454-8fd3-57c81e829f7b(OCS.15).jpg "Output from cert request using Request-CsCertifica")</span></span>

7.  <span data-ttu-id="d314f-136">En el shell de administración de Lync Server, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d314f-136">In the Lync Server Management Shell, type the following:</span></span>
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Thumbprint of certificate to use>
    
    <span data-ttu-id="d314f-137">Donde el comando completo tendría el siguiente ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d314f-137">Where the full command would appear like following example:</span></span>
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint 466D9BB0E8B928B65AF38FA2D9F41E1B301ECE9D
    
    <span data-ttu-id="d314f-138">El resultado del cmdlet Set-CsCertificate mostrará que el mismo certificado (identificado por la huella digital del certificado) se asigna al uso predeterminado, WebServicesExternal y WebServicesInternal.</span><span class="sxs-lookup"><span data-stu-id="d314f-138">The output from the Set-CsCertificate cmdlet will show that the same certificate (identified by the thumbprint of the certificate) is assigned for the Default, WebServicesExternal and WebServicesInternal usage.</span></span>
    
    <span data-ttu-id="d314f-139">![Resultado de set-CsCertificate en IIS webext] (images/Gg429702.dd451c9d-7b49-4408-8071-c868cb1e678c(OCS.15).jpg "Resultado de set-CsCertificate en IIS webext")</span><span class="sxs-lookup"><span data-stu-id="d314f-139">![Output from Set-CsCertificate on IIS WebExt](images/Gg429702.dd451c9d-7b49-4408-8071-c868cb1e678c(OCS.15).jpg "Output from Set-CsCertificate on IIS WebExt")</span></span>

</div>

<div>

## <a name="to-verify-or-configure-authentication-and-certificates-on-iis-virtual-directories"></a><span data-ttu-id="d314f-140">Para comprobar o configurar la autenticación y los certificados en los directorios virtuales de IIS</span><span class="sxs-lookup"><span data-stu-id="d314f-140">To verify or configure authentication and certificates on IIS virtual directories</span></span>

1.  <span data-ttu-id="d314f-141">Haga clic en **Inicio**, seleccione **todos los programas**, **herramientas administrativas**y, a continuación, haga clic en **Administrador de Internet Information Services (IIS)**.</span><span class="sxs-lookup"><span data-stu-id="d314f-141">Click **Start**, select **All Programs**, select **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>

2.  <span data-ttu-id="d314f-142">En el **Administrador de Internet Information Services (IIS)**, expanda **ServerName**y, a continuación, expanda **sites**.</span><span class="sxs-lookup"><span data-stu-id="d314f-142">In **Internet Information Services (IIS) Manager**, expand **ServerName**, and then expand **Sites**.</span></span>

3.  <span data-ttu-id="d314f-143">Haga clic con el botón secundario en **sitio web externo de Lync Server**y, a continuación, haga clic en **Editar enlaces**</span><span class="sxs-lookup"><span data-stu-id="d314f-143">Right-click **Lync Server External Web Site**, and then click **Edit Bindings**</span></span>

4.  <span data-ttu-id="d314f-144">Compruebe que https está asociado con el puerto 4443 y, a continuación, haga clic en **https**.</span><span class="sxs-lookup"><span data-stu-id="d314f-144">Verify that https is associated with port 4443, and then click **https**.</span></span>

5.  <span data-ttu-id="d314f-145">Seleccione la entrada HTTPS, haga clic en **Editar**y, a continuación, compruebe que Lync Server WebServicesExternalCertificate está enlazado a este protocolo.</span><span class="sxs-lookup"><span data-stu-id="d314f-145">Select the HTTPS entry, click **Edit**, and then verify that Lync Server WebServicesExternalCertificate is bound to this protocol.</span></span> <span data-ttu-id="d314f-146">Compare la huella digital del cmdlet Set-CsCertificate para asegurarse de que el certificado esperado esté correctamente asociado con el enlace HTTPS.</span><span class="sxs-lookup"><span data-stu-id="d314f-146">Compare the thumbprint from the Set-CsCertificate cmdlet to ensure that the expected certificate is correctly associated with the HTTPS binding.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d314f-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="d314f-147">See Also</span></span>


[<span data-ttu-id="d314f-148">Get-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="d314f-148">Get-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCertificate)  
[<span data-ttu-id="d314f-149">Set-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="d314f-149">Set-CsCertificate</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

