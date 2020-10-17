---
title: 'Lync Server 2013: modificación de certificados para movilidad'
description: 'Lync Server 2013: modificación de certificados para movilidad.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modifying certificates for mobility
ms:assetid: 4e9107af-20f4-4c2a-8c98-ca35b39a4e2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690015(v=OCS.15)
ms:contentKeyID: 48184120
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 099122b1773c3f15d8ae0034ee5fa404225cdfd2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555856"
---
# <a name="modifying-certificates-for-mobility-in-lync-server-2013"></a><span data-ttu-id="37195-103">Modificación de certificados para movilidad en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37195-103">Modifying certificates for mobility in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="37195-104">_**Última modificación del tema:** 2014-06-20_</span><span class="sxs-lookup"><span data-stu-id="37195-104">_**Topic Last Modified:** 2014-06-20_</span></span>

<span data-ttu-id="37195-105">Para admitir conexiones seguras entre el entorno de Lync y los clientes móviles, los certificados de capa de sockets seguros (SSL) para el grupo de directores, el grupo de servidores front-end y el proxy inverso deben actualizarse con algunas entradas de nombre alternativo de sujeto (SAN) adicionales.</span><span class="sxs-lookup"><span data-stu-id="37195-105">To support secure connections between your Lync environment and your mobile clients, the Secure Socket Layer (SSL) certificates for your Director pool, Front End pool, and reverse proxy are going to need to be updated with some additional subject alternative name (SAN) entries.</span></span> <span data-ttu-id="37195-106">Si necesita consultar más detalles sobre los requisitos de certificados para la movilidad, consulte la sección requisitos [técnicos para la movilidad en Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md), pero básicamente necesitará obtener nuevos certificados de la entidad de certificación con las entradas de San adicionales incluidas y, a continuación, agregar dichos certificados con los pasos de este artículo.</span><span class="sxs-lookup"><span data-stu-id="37195-106">If you need to check out more details about the certificate requirements for mobility, see the Certificate Requirements section in [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md), but basically you’ll need to get new certificates from the Certificate Authority with the additional SAN entries included, and then add those certificates using this article’s steps.</span></span>

<span data-ttu-id="37195-107">Por supuesto, antes de empezar, suele ser una buena idea conocer los nombres de sujeto alternativos que ya tienen los certificados.</span><span class="sxs-lookup"><span data-stu-id="37195-107">Of course before you begin, it’s usually a good idea to know what subject alternative names your certificates already have.</span></span> <span data-ttu-id="37195-108">Si no está seguro de lo que ya está configurado, hay muchas formas de averiguarlo. Mientras que la opción se encuentra ahí para ejecutar **Get-CsCertificate** y otros comandos de PowerShell para ver esta información, (que analizaremos a continuación) de forma predeterminada, los datos se truncarán, por lo que es posible que no vea todas las propiedades que necesita.</span><span class="sxs-lookup"><span data-stu-id="37195-108">If you’re not sure what’s already been configured, there are a lot of ways to find out. While the option’s there to run the **Get-CsCertificate** and other PowerShell commands to view this information, (which we walk through below) by default that data will be truncated, so you may not get to see all the properties you need.</span></span> <span data-ttu-id="37195-109">Para obtener un buen vistazo al certificado y a todas sus propiedades, puede ir a Microsoft Management Console (MMC) y cargar el complemento certificados (que también trataremos a continuación), o puede simplemente comprobar el Asistente para la implementación de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="37195-109">In order to get a good look at the certificate and all its properties, you can go to the Microsoft Management Console (MMC) and load the Certificates snap-in (which we also walk through below), or you can just check in the Lync Server Deployment Wizard.</span></span>

<span data-ttu-id="37195-110">Como se indicó anteriormente, los pasos siguientes le guiarán por el proceso de actualización de los certificados mediante el shell de administración de Lync Server y MMC.</span><span class="sxs-lookup"><span data-stu-id="37195-110">As noted above, the following steps will walk you through updating the certificates using the Lync Server Management Shell and the MMC.</span></span> <span data-ttu-id="37195-111">Si está interesado en usar el Asistente para certificados en el Asistente para la implementación de Lync Server en su lugar, puede comprobar la [configuración de certificados del Director en Lync server 2013](lync-server-2013-configure-certificates-for-the-director.md) para el director o el grupo de directores, si ha configurado uno (es posible que no tenga).</span><span class="sxs-lookup"><span data-stu-id="37195-111">If you’re interested in using the Certificate Wizard in the Lync Server Deployment Wizard for this instead, you can check [Configure certificates for the Director in Lync Server 2013](lync-server-2013-configure-certificates-for-the-director.md) out for the Director or Director pool, if you configured one (you may not have).</span></span> <span data-ttu-id="37195-112">Para el servidor front-end o el grupo de servidores front-end, querrá ver [configurar certificados para servidores en Lync Server 2013](lync-server-2013-configure-certificates-for-servers.md).</span><span class="sxs-lookup"><span data-stu-id="37195-112">For the Front End Server or Front End pool, you’ll want to see [Configure certificates for servers in Lync Server 2013](lync-server-2013-configure-certificates-for-servers.md).</span></span>

<span data-ttu-id="37195-113">Un último aspecto que se debe tener en cuenta es que puede tener un único certificado predeterminado en el entorno de Lync Server 2013 o puede tener certificados independientes para el valor predeterminado (que es todo excepto los servicios web), WebServicesExternal y WebServicesInternal.</span><span class="sxs-lookup"><span data-stu-id="37195-113">One last thing to keep in mind is that you may have a single Default certificate in your Lync Server 2013 environment, or you may have separate certificates for Default (which is everything but the web services), WebServicesExternal and WebServicesInternal.</span></span> <span data-ttu-id="37195-114">Independientemente de la configuración, estos pasos deben ayudarle.</span><span class="sxs-lookup"><span data-stu-id="37195-114">Whatever your configuration, these steps should help you out.</span></span>

<div>

## <a name="to-update-certificates-with-new-subject-alternative-names-using-the-lync-server-management-shell"></a><span data-ttu-id="37195-115">Para actualizar certificados con nombres alternativos de sujeto nuevos mediante el shell de administración de Lync Server</span><span class="sxs-lookup"><span data-stu-id="37195-115">To update certificates with new subject alternative names using the Lync Server Management Shell</span></span>

1.  <span data-ttu-id="37195-116">Debe iniciar sesión en el servidor de Lync Server 2013 con una cuenta que tenga derechos y permisos de administrador local.</span><span class="sxs-lookup"><span data-stu-id="37195-116">You need to log on to your Lync Server 2013 server using an account that has local administrator rights and permissions.</span></span> <span data-ttu-id="37195-117">Además, si está ejecutando la **solicitud-CsCertificate** de PowerShell en los pasos 12 y posteriores, la cuenta debe tener derechos para la entidad de certificación especificada (CA).</span><span class="sxs-lookup"><span data-stu-id="37195-117">Additionally, if you’re running the PowerShell **Request-CsCertificate** in Steps 12 and beyond, the account needs to have rights to the specified Certificate Authority (CA).</span></span>

2.  <span data-ttu-id="37195-118">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="37195-118">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="37195-119">Antes de poder asignar un certificado actualizado, deberá averiguar qué certificados se han asignado al servidor y para qué tipo de uso.</span><span class="sxs-lookup"><span data-stu-id="37195-119">Before you can assign an updated certificate, you’ll need to find out what certificates have been assigned to the server and for which type of use.</span></span> <span data-ttu-id="37195-120">En la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="37195-120">At the command line, type:</span></span>
    
        Get-CsCertificate

4.  <span data-ttu-id="37195-121">Revise el resultado del paso anterior para ver si un único certificado se ha asignado para varios usos o si se ha asignado un certificado diferente para cada uso.</span><span class="sxs-lookup"><span data-stu-id="37195-121">Review the output from the previous step to see whether a single certificate has been assigned for multiple uses, or whether a different certificate is assigned for each use.</span></span> <span data-ttu-id="37195-122">Busque en el parámetro use para averiguar cómo se usa un certificado.</span><span class="sxs-lookup"><span data-stu-id="37195-122">Look in the Use parameter to find out how a certificate’s being used.</span></span> <span data-ttu-id="37195-123">Compara el parámetro Huella digital de los certificados mostrados para ver si el mismo certificado tiene varios usos.</span><span class="sxs-lookup"><span data-stu-id="37195-123">Compare the Thumbprint parameter for the displayed certificates to see if the same certificate has multiple uses.</span></span> <span data-ttu-id="37195-124">Mantenga el ojo del parámetro Thumbprint.</span><span class="sxs-lookup"><span data-stu-id="37195-124">Keep your eye on the Thumbprint parameter.</span></span>

5.  <span data-ttu-id="37195-125">Actualice el certificado.</span><span class="sxs-lookup"><span data-stu-id="37195-125">Update the certificate.</span></span> <span data-ttu-id="37195-126">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="37195-126">At the command line, type:</span></span>
    
        Set-CsCertificate -Type <type of certificate as displayed in the Use parameter> -Thumbprint <unique identifier>
    
    <span data-ttu-id="37195-127">Por ejemplo, si el cmdlet **Get-CsCertificate** muestra un certificado con uso predeterminado, otro con uso de WebServicesInternal y otro con uso de WebServicesExternal, y todos tenían el mismo valor de huella digital, en la línea de comandos debe escribir:</span><span class="sxs-lookup"><span data-stu-id="37195-127">For example, if the **Get-CsCertificate** cmdlet displayed a certificate with Use of Default, another with a Use of WebServicesInternal, and another with a Use of WebServicesExternal, and they all had the same Thumbprint value, at the command line, you should type:</span></span>
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
    
    <span data-ttu-id="37195-128">**Importante:**</span><span class="sxs-lookup"><span data-stu-id="37195-128">**Important:**</span></span>
    
    <span data-ttu-id="37195-129">Si se asigna un certificado independiente para cada uso (por lo que el valor de la huella digital que ha comprobado arriba es diferente para cada certificado), es fundamental que **no** ejecute el cmdlet **set-CsCertificate** con varios tipos, como en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="37195-129">If a separate certificate is assigned for each use (so the Thumbprint value you checked above is different for each certificate), it’s vital that you **don’t** run the **Set-CsCertificate** cmdlet with multiple types, as in the example above.</span></span> <span data-ttu-id="37195-130">En este caso, ejecute el cmdlet **Set-CsCertificate** por separado para cada uso.</span><span class="sxs-lookup"><span data-stu-id="37195-130">In this case, run the **Set-CsCertificate** cmdlet separately for each use.</span></span> <span data-ttu-id="37195-131">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="37195-131">For example:</span></span>
    
        Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>

6.  <span data-ttu-id="37195-132">Para ver el certificado (o certificados), haga clic en **Inicio**, haga clic en **Ejecutar...**.</span><span class="sxs-lookup"><span data-stu-id="37195-132">To view the certificate (or certificates), click **Start**, click **Run…**.</span></span> <span data-ttu-id="37195-133">Escriba MMC para abrir Microsoft Management Console.</span><span class="sxs-lookup"><span data-stu-id="37195-133">Type MMC to open the Microsoft Management Console.</span></span>

7.  <span data-ttu-id="37195-134">En el menú de MMC, seleccione **Archivo**, **Agregar o quitar complemento…**, Certificados.</span><span class="sxs-lookup"><span data-stu-id="37195-134">From the MMC menu, select **File**, select **Add/Remove snap-in…**, select Certificates.</span></span> <span data-ttu-id="37195-135">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="37195-135">Click **Add**.</span></span> <span data-ttu-id="37195-136">Cuando se le pida, seleccione **Cuenta de equipo** y luego haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="37195-136">When prompted, select **Computer account**, then click **Next**.</span></span>

8.  <span data-ttu-id="37195-137">Si este es el servidor en el que se encuentra el certificado, seleccione **equipo local**.</span><span class="sxs-lookup"><span data-stu-id="37195-137">If this is the server where the certificate’s located, select **Local computer**.</span></span> <span data-ttu-id="37195-138">Si el certificado está ubicado en otro equipo, debe seleccionar **otro equipo**y, a continuación, puede escribir el nombre de dominio completo del equipo, o bien hacer clic en **examinar** en **Escriba el nombre de objeto a seleccionar**y escribir el nombre del equipo.</span><span class="sxs-lookup"><span data-stu-id="37195-138">If the certificate’s located on another computer, you should select **Another computer**, and then you can either type in the fully qualified domain name of the computer, or click **Browse** in **Enter the object name to select**, and type the name of the computer.</span></span> <span data-ttu-id="37195-139">Haga clic en **Comprobar nombres**.</span><span class="sxs-lookup"><span data-stu-id="37195-139">Click **Check Names**.</span></span> <span data-ttu-id="37195-140">Cuando se resuelva el nombre del equipo, se mostrará subrayado.</span><span class="sxs-lookup"><span data-stu-id="37195-140">When the name of the computer resolves, it’ll be underlined.</span></span> <span data-ttu-id="37195-141">Haga clic en **Aceptar** y luego en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="37195-141">Click **OK**, then click **Finish**.</span></span> <span data-ttu-id="37195-142">Haga clic en **Aceptar** para confirmar la selección y cerrar el cuadro de diálogo **Agregar o quitar complementos**.</span><span class="sxs-lookup"><span data-stu-id="37195-142">Click **OK** to commit the selection and close the **Add or Remove Snap-ins** dialog.</span></span>

9.  <span data-ttu-id="37195-p113">Para ver las propiedades del certificado, expanda **Certificados**, **Personal** y seleccione **Certificados**. Seleccione el certificado que desea ver, haga clic en el certificado y seleccione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="37195-p113">To view the properties of the certificate, expand **Certificates**, expand **Personal**, and select **Certificates**. Select the certificate to view, right-click on the certificate and select **Open**.</span></span>

10. <span data-ttu-id="37195-p114">En la vista **Certificado**, seleccione **Detalles**. Desde aquí, puede elegir el nombre de sujeto del certificado seleccionando **Sujeto** y se muestran el nombre del sujeto asignado y propiedades asociadas.</span><span class="sxs-lookup"><span data-stu-id="37195-p114">In the **Certificate** view, select **Details**. From here, you can select the certificate subject name by selecting **Subject** and the assigned subject name and associated properties are displayed.</span></span>

11. <span data-ttu-id="37195-147">Para ver los nombres alternativos del sujeto asignados, seleccione **Nombre alternativo del sujeto**.</span><span class="sxs-lookup"><span data-stu-id="37195-147">To view the assigned subject alternative names, select **Subject Alternative Name**.</span></span> <span data-ttu-id="37195-148">Todos los nombres alternativos de sujeto asignados se muestran aquí.</span><span class="sxs-lookup"><span data-stu-id="37195-148">All assigned subject alternative names are displayed here.</span></span> <span data-ttu-id="37195-149">Los nombres alternativos de sujeto que se encuentran aquí son del tipo **nombre DNS** de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="37195-149">The subject alternative names found here are of type **DNS Name** by default.</span></span> <span data-ttu-id="37195-150">Debe ver los siguientes miembros (todos los cuales deben ser nombres de dominio completos representados en los registros del host de DNS (A o, si IPv6 AAAA):</span><span class="sxs-lookup"><span data-stu-id="37195-150">You should see the following members (all of which should be fully qualified domain names as represented in DNS host (A or, if IPv6 AAAA) records:</span></span>
    
      - <span data-ttu-id="37195-151">Nombre de grupo para este grupo o el nombre de servidor único si no se trata de un grupo de servidores</span><span class="sxs-lookup"><span data-stu-id="37195-151">Pool name for this pool, or the single server name if this isn’t a pool</span></span>
    
      - <span data-ttu-id="37195-152">Nombre del servidor al que está asignado el certificado</span><span class="sxs-lookup"><span data-stu-id="37195-152">Server name that the certificate is assigned to</span></span>
    
      - <span data-ttu-id="37195-153">Registros de direcciones URL simples, normalmente reunión y marcación</span><span class="sxs-lookup"><span data-stu-id="37195-153">Simple URL records, typically meet and dialin</span></span>
    
      - <span data-ttu-id="37195-154">Nombres externos de servicios Web internos y servicios web (por ejemplo, webpool01.contoso.net, webpool01.contoso.com), en función de las elecciones realizadas en el generador de topologías y las selecciones de servicios web invalidadas.</span><span class="sxs-lookup"><span data-stu-id="37195-154">Web services internal and Web services external names (for example, webpool01.contoso.net, webpool01.contoso.com), based on choices made in Topology Builder and over-ridden web services selections.</span></span>
    
      - <span data-ttu-id="37195-155">Si ya está asignado, el lyncdiscover.\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="37195-155">If already assigned, the lyncdiscover.\<sipdomain\></span></span> <span data-ttu-id="37195-156">y lyncdiscoverinternal.\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="37195-156">and lyncdiscoverinternal.\<sipdomain\></span></span> <span data-ttu-id="37195-157">registro.</span><span class="sxs-lookup"><span data-stu-id="37195-157">records.</span></span>
    
    <span data-ttu-id="37195-158">El último elemento es lo que más le interesa: si hay una entrada de SAN de lyncdiscover y lyncdiscoverinternal.</span><span class="sxs-lookup"><span data-stu-id="37195-158">The last item is what you’re most interested in – if there’s a lyncdiscover and lyncdiscoverinternal SAN entry.</span></span>
    
    <span data-ttu-id="37195-159">Repita estos pasos si tiene varios certificados que comprobar.</span><span class="sxs-lookup"><span data-stu-id="37195-159">Repeat these steps if you have multiple certificates to check.</span></span> <span data-ttu-id="37195-160">Una vez que tenga esta información, puede cerrar la vista de certificado y MMC.</span><span class="sxs-lookup"><span data-stu-id="37195-160">Once you have this information, you can close the certificate view and the MMC.</span></span>

12. <span data-ttu-id="37195-161">Si falta un nombre alternativo del sujeto del servicio Detección automática, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="37195-161">If an Autodiscover Service subject alternative name is missing, and you are using a single Default certificate for the Default, WebServicesInternal and WebServiceExternal types, do the following:</span></span>
    
      - <span data-ttu-id="37195-162">En el símbolo del sistema de la línea de comandos del shell de administración de Lync Server, escriba:</span><span class="sxs-lookup"><span data-stu-id="37195-162">At the Lync Server Management Shell command line prompt, type:</span></span>
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="37195-163">Si tiene varios dominios SIP, no puede usar el nuevo parámetro AllSipDomain.</span><span class="sxs-lookup"><span data-stu-id="37195-163">If you have many SIP domains, you can’t use the new AllSipDomain parameter.</span></span> <span data-ttu-id="37195-164">En su lugar, debe usar el parámetro DomainName.</span><span class="sxs-lookup"><span data-stu-id="37195-164">Instead, you need to use the DomainName parameter.</span></span> <span data-ttu-id="37195-165">Cuando usa el parámetro DomainName, tiene que definir el FQDN para los registros lyncdiscoverinternal y lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="37195-165">When you use the DomainName parameter, you’ve got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="37195-166">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="37195-166">For example:</span></span>
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - <span data-ttu-id="37195-167">Para asignar el certificado, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="37195-167">To assign the certificate, type the following:</span></span>
        
            Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        <span data-ttu-id="37195-168">Donde “Huella digital” es la huella digital mostrada para el certificado que acaba de emitir.</span><span class="sxs-lookup"><span data-stu-id="37195-168">Where “Thumbprint” is the thumbprint displayed for the newly issued certificate.</span></span>

13. <span data-ttu-id="37195-169">Para que falte un SAN de detección automática interna cuando use certificados independientes para default, WebServicesInternal y WebServicesExternal, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="37195-169">For a missing internal Autodiscover SAN when using separate certificates for Default, WebServicesInternal, and WebServicesExternal, do the following:</span></span>
    
      - <span data-ttu-id="37195-170">En el símbolo del sistema de la línea de comandos del shell de administración de Lync Server, escriba:</span><span class="sxs-lookup"><span data-stu-id="37195-170">At the Lync Server Management Shell command line prompt, type:</span></span>
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="37195-171">Si tiene varios dominios SIP, no puede usar el nuevo parámetro AllSipDomain.</span><span class="sxs-lookup"><span data-stu-id="37195-171">If you have many SIP domains, you can’t use the new AllSipDomain parameter.</span></span> <span data-ttu-id="37195-172">En su lugar, debe usar el parámetro DomainName.</span><span class="sxs-lookup"><span data-stu-id="37195-172">Instead, you need to use the DomainName parameter.</span></span> <span data-ttu-id="37195-173">Cuando usa el parámetro DomainName, tiene que usar un prefijo adecuado para el FQDN de dominio SIP.</span><span class="sxs-lookup"><span data-stu-id="37195-173">When you use the DomainName parameter, you’ve got to use an appropriate prefix for the SIP domain FQDN.</span></span> <span data-ttu-id="37195-174">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="37195-174">For example:</span></span>
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - <span data-ttu-id="37195-175">Para un nombre alternativo de sujeto del servicio Detección automática externa, en la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="37195-175">For a missing external Autodiscover subject alternative name, at the command line, type:</span></span>
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="37195-176">Si tiene varios dominios SIP, no puede usar el nuevo parámetro AllSipDomain.</span><span class="sxs-lookup"><span data-stu-id="37195-176">If you have many SIP domains, you can’t use the new AllSipDomain parameter.</span></span> <span data-ttu-id="37195-177">En su lugar, debe usar el parámetro DomainName.</span><span class="sxs-lookup"><span data-stu-id="37195-177">Instead, you need to use the DomainName parameter.</span></span> <span data-ttu-id="37195-178">Cuando usa el parámetro DomainName, tiene que usar un prefijo adecuado para el FQDN de dominio SIP.</span><span class="sxs-lookup"><span data-stu-id="37195-178">When you use the DomainName parameter, you’ve got to use an appropriate prefix for the SIP domain FQDN.</span></span> <span data-ttu-id="37195-179">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="37195-179">For example:</span></span>
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
    
      - <span data-ttu-id="37195-180">Para asignar tipos de certificados individuales, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="37195-180">To assign the individual certificate types, type the following:</span></span>
        
            Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        <span data-ttu-id="37195-181">Donde “Huella digital” es la huella digital mostrada para el certificado individual que acaba de emitir.</span><span class="sxs-lookup"><span data-stu-id="37195-181">Where “Thumbprint” is the thumbprint displayed for the newly issued individual certificates.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="37195-182">Solo para tener en cuenta, los pasos 12 y 13 solo deben ejecutarse si la cuenta que los ejecuta tiene acceso a la entidad de certificación con los permisos adecuados.</span><span class="sxs-lookup"><span data-stu-id="37195-182">Just to note, Steps 12 and 13 should be run only if the account running them has access to the Certificate Authority with appropriate permissions.</span></span> <span data-ttu-id="37195-183">Si no puede iniciar sesión con una cuenta que tiene estos permisos, o si está usando una entidad de certificación pública o remota para los certificados, necesitará solicitarlos mediante el Asistente para la implementación de Lync Server, que se ha tocado en la parte superior del artículo.</span><span class="sxs-lookup"><span data-stu-id="37195-183">If you are unable to log in with an account that’s got those permissions, or if you’re using a public or remote Certificate Authority for your certificates, you would need to request them through the Lync Server Deployment Wizard, which was touched on at the top of the article.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

