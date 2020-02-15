---
title: 'Lync Server 2013: modificación de certificados para movilidad'
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
ms.openlocfilehash: 54b42ba288c89f8735d3f7d13dee9a1944efe82b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048751"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modifying-certificates-for-mobility-in-lync-server-2013"></a><span data-ttu-id="3d13a-102">Modificación de certificados para movilidad en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3d13a-102">Modifying certificates for mobility in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3d13a-103">_**Última modificación del tema:** 2014-06-20_</span><span class="sxs-lookup"><span data-stu-id="3d13a-103">_**Topic Last Modified:** 2014-06-20_</span></span>

<span data-ttu-id="3d13a-104">Para admitir conexiones seguras entre el entorno de Lync y los clientes móviles, los certificados de capa de sockets seguros (SSL) para el grupo de directores, el grupo de servidores front-end y el proxy inverso deben actualizarse con un nombre alternativo de sujeto adicional ( SAN).</span><span class="sxs-lookup"><span data-stu-id="3d13a-104">To support secure connections between your Lync environment and your mobile clients, the Secure Socket Layer (SSL) certificates for your Director pool, Front End pool, and reverse proxy are going to need to be updated with some additional subject alternative name (SAN) entries.</span></span> <span data-ttu-id="3d13a-105">Si necesita consultar más detalles sobre los requisitos de certificados para la movilidad, consulte la sección requisitos [técnicos para la movilidad en Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md), pero básicamente necesitará obtener nuevos certificados de la entidad de certificación con las entradas de San adicionales incluidas y, a continuación, agregar dichos certificados con los pasos de este artículo.</span><span class="sxs-lookup"><span data-stu-id="3d13a-105">If you need to check out more details about the certificate requirements for mobility, see the Certificate Requirements section in [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md), but basically you’ll need to get new certificates from the Certificate Authority with the additional SAN entries included, and then add those certificates using this article’s steps.</span></span>

<span data-ttu-id="3d13a-106">Por supuesto, antes de empezar, suele ser una buena idea conocer los nombres de sujeto alternativos que ya tienen los certificados.</span><span class="sxs-lookup"><span data-stu-id="3d13a-106">Of course before you begin, it’s usually a good idea to know what subject alternative names your certificates already have.</span></span> <span data-ttu-id="3d13a-107">Si no está seguro de lo que ya está configurado, hay muchas formas de averiguarlo. Mientras que la opción se encuentra ahí para ejecutar **Get-CsCertificate** y otros comandos de PowerShell para ver esta información, (que analizaremos a continuación) de forma predeterminada, los datos se truncarán, por lo que es posible que no vea todas las propiedades que necesita.</span><span class="sxs-lookup"><span data-stu-id="3d13a-107">If you’re not sure what’s already been configured, there are a lot of ways to find out. While the option’s there to run the **Get-CsCertificate** and other PowerShell commands to view this information, (which we walk through below) by default that data will be truncated, so you may not get to see all the properties you need.</span></span> <span data-ttu-id="3d13a-108">Para obtener un buen vistazo al certificado y a todas sus propiedades, puede ir a Microsoft Management Console (MMC) y cargar el complemento certificados (que también trataremos a continuación), o puede simplemente comprobar el Asistente para la implementación de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3d13a-108">In order to get a good look at the certificate and all its properties, you can go to the Microsoft Management Console (MMC) and load the Certificates snap-in (which we also walk through below), or you can just check in the Lync Server Deployment Wizard.</span></span>

<span data-ttu-id="3d13a-109">Como se indicó anteriormente, los pasos siguientes le guiarán por el proceso de actualización de los certificados mediante el shell de administración de Lync Server y MMC.</span><span class="sxs-lookup"><span data-stu-id="3d13a-109">As noted above, the following steps will walk you through updating the certificates using the Lync Server Management Shell and the MMC.</span></span> <span data-ttu-id="3d13a-110">Si está interesado en usar el Asistente para certificados en el Asistente para la implementación de Lync Server en su lugar, puede comprobar la [configuración de certificados del Director en Lync server 2013](lync-server-2013-configure-certificates-for-the-director.md) para el director o el grupo de directores, si ha configurado uno (es posible que no tenga).</span><span class="sxs-lookup"><span data-stu-id="3d13a-110">If you’re interested in using the Certificate Wizard in the Lync Server Deployment Wizard for this instead, you can check [Configure certificates for the Director in Lync Server 2013](lync-server-2013-configure-certificates-for-the-director.md) out for the Director or Director pool, if you configured one (you may not have).</span></span> <span data-ttu-id="3d13a-111">Para el servidor front-end o el grupo de servidores front-end, querrá ver [configurar certificados para servidores en Lync Server 2013](lync-server-2013-configure-certificates-for-servers.md).</span><span class="sxs-lookup"><span data-stu-id="3d13a-111">For the Front End Server or Front End pool, you’ll want to see [Configure certificates for servers in Lync Server 2013](lync-server-2013-configure-certificates-for-servers.md).</span></span>

<span data-ttu-id="3d13a-112">Un último aspecto que se debe tener en cuenta es que puede tener un único certificado predeterminado en el entorno de Lync Server 2013 o puede tener certificados independientes para el valor predeterminado (que es todo excepto los servicios web), WebServicesExternal y WebServicesInternal.</span><span class="sxs-lookup"><span data-stu-id="3d13a-112">One last thing to keep in mind is that you may have a single Default certificate in your Lync Server 2013 environment, or you may have separate certificates for Default (which is everything but the web services), WebServicesExternal and WebServicesInternal.</span></span> <span data-ttu-id="3d13a-113">Independientemente de la configuración, estos pasos deben ayudarle.</span><span class="sxs-lookup"><span data-stu-id="3d13a-113">Whatever your configuration, these steps should help you out.</span></span>

<div>

## <a name="to-update-certificates-with-new-subject-alternative-names-using-the-lync-server-management-shell"></a><span data-ttu-id="3d13a-114">Para actualizar certificados con nombres alternativos de sujeto nuevos mediante el shell de administración de Lync Server</span><span class="sxs-lookup"><span data-stu-id="3d13a-114">To update certificates with new subject alternative names using the Lync Server Management Shell</span></span>

1.  <span data-ttu-id="3d13a-115">Debe iniciar sesión en el servidor de Lync Server 2013 con una cuenta que tenga derechos y permisos de administrador local.</span><span class="sxs-lookup"><span data-stu-id="3d13a-115">You need to log on to your Lync Server 2013 server using an account that has local administrator rights and permissions.</span></span> <span data-ttu-id="3d13a-116">Además, si está ejecutando la **solicitud-CsCertificate** de PowerShell en los pasos 12 y posteriores, la cuenta debe tener derechos para la entidad de certificación especificada (CA).</span><span class="sxs-lookup"><span data-stu-id="3d13a-116">Additionally, if you’re running the PowerShell **Request-CsCertificate** in Steps 12 and beyond, the account needs to have rights to the specified Certificate Authority (CA).</span></span>

2.  <span data-ttu-id="3d13a-117">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="3d13a-117">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="3d13a-118">Antes de poder asignar un certificado actualizado, deberá averiguar qué certificados se han asignado al servidor y para qué tipo de uso.</span><span class="sxs-lookup"><span data-stu-id="3d13a-118">Before you can assign an updated certificate, you’ll need to find out what certificates have been assigned to the server and for which type of use.</span></span> <span data-ttu-id="3d13a-119">En la línea de comandos, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3d13a-119">At the command line, type:</span></span>
    
        Get-CsCertificate

4.  <span data-ttu-id="3d13a-120">Revise el resultado del paso anterior para ver si un único certificado se ha asignado para varios usos o si se ha asignado un certificado diferente para cada uso.</span><span class="sxs-lookup"><span data-stu-id="3d13a-120">Review the output from the previous step to see whether a single certificate has been assigned for multiple uses, or whether a different certificate is assigned for each use.</span></span> <span data-ttu-id="3d13a-121">Busque en el parámetro use para averiguar cómo se usa un certificado.</span><span class="sxs-lookup"><span data-stu-id="3d13a-121">Look in the Use parameter to find out how a certificate’s being used.</span></span> <span data-ttu-id="3d13a-122">Compara el parámetro Huella digital de los certificados mostrados para ver si el mismo certificado tiene varios usos.</span><span class="sxs-lookup"><span data-stu-id="3d13a-122">Compare the Thumbprint parameter for the displayed certificates to see if the same certificate has multiple uses.</span></span> <span data-ttu-id="3d13a-123">Mantenga el ojo del parámetro Thumbprint.</span><span class="sxs-lookup"><span data-stu-id="3d13a-123">Keep your eye on the Thumbprint parameter.</span></span>

5.  <span data-ttu-id="3d13a-124">Actualice el certificado.</span><span class="sxs-lookup"><span data-stu-id="3d13a-124">Update the certificate.</span></span> <span data-ttu-id="3d13a-125">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="3d13a-125">At the command line, type:</span></span>
    
        Set-CsCertificate -Type <type of certificate as displayed in the Use parameter> -Thumbprint <unique identifier>
    
    <span data-ttu-id="3d13a-126">Por ejemplo, si el cmdlet **Get-CsCertificate** muestra un certificado con uso predeterminado, otro con uso de WebServicesInternal y otro con uso de WebServicesExternal, y todos tenían el mismo valor de huella digital, en la línea de comandos debe escribir:</span><span class="sxs-lookup"><span data-stu-id="3d13a-126">For example, if the **Get-CsCertificate** cmdlet displayed a certificate with Use of Default, another with a Use of WebServicesInternal, and another with a Use of WebServicesExternal, and they all had the same Thumbprint value, at the command line, you should type:</span></span>
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
    
    <span data-ttu-id="3d13a-127">**Importante:**</span><span class="sxs-lookup"><span data-stu-id="3d13a-127">**Important:**</span></span>
    
    <span data-ttu-id="3d13a-128">Si se asigna un certificado independiente para cada uso (por lo que el valor de la huella digital que ha comprobado arriba es diferente para cada certificado), es fundamental que **no** ejecute el cmdlet **set-CsCertificate** con varios tipos, como en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="3d13a-128">If a separate certificate is assigned for each use (so the Thumbprint value you checked above is different for each certificate), it’s vital that you **don’t** run the **Set-CsCertificate** cmdlet with multiple types, as in the example above.</span></span> <span data-ttu-id="3d13a-129">En este caso, ejecute el cmdlet **Set-CsCertificate** por separado para cada uso.</span><span class="sxs-lookup"><span data-stu-id="3d13a-129">In this case, run the **Set-CsCertificate** cmdlet separately for each use.</span></span> <span data-ttu-id="3d13a-130">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="3d13a-130">For example:</span></span>
    
        Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>

6.  <span data-ttu-id="3d13a-131">Para ver el certificado (o certificados), haga clic en **Inicio**, haga clic en **Ejecutar...**.</span><span class="sxs-lookup"><span data-stu-id="3d13a-131">To view the certificate (or certificates), click **Start**, click **Run…**.</span></span> <span data-ttu-id="3d13a-132">Escriba MMC para abrir Microsoft Management Console.</span><span class="sxs-lookup"><span data-stu-id="3d13a-132">Type MMC to open the Microsoft Management Console.</span></span>

7.  <span data-ttu-id="3d13a-133">En el menú de MMC, seleccione **Archivo**, **Agregar o quitar complemento…**, Certificados.</span><span class="sxs-lookup"><span data-stu-id="3d13a-133">From the MMC menu, select **File**, select **Add/Remove snap-in…**, select Certificates.</span></span> <span data-ttu-id="3d13a-134">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="3d13a-134">Click **Add**.</span></span> <span data-ttu-id="3d13a-135">Cuando se le pida, seleccione **Cuenta de equipo** y luego haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="3d13a-135">When prompted, select **Computer account**, then click **Next**.</span></span>

8.  <span data-ttu-id="3d13a-136">Si este es el servidor en el que se encuentra el certificado, seleccione **equipo local**.</span><span class="sxs-lookup"><span data-stu-id="3d13a-136">If this is the server where the certificate’s located, select **Local computer**.</span></span> <span data-ttu-id="3d13a-137">Si el certificado está ubicado en otro equipo, debe seleccionar **otro equipo**y, a continuación, puede escribir el nombre de dominio completo del equipo, o bien hacer clic en **examinar** en **Escriba el nombre de objeto a seleccionar**y escribir el nombre del equipo.</span><span class="sxs-lookup"><span data-stu-id="3d13a-137">If the certificate’s located on another computer, you should select **Another computer**, and then you can either type in the fully qualified domain name of the computer, or click **Browse** in **Enter the object name to select**, and type the name of the computer.</span></span> <span data-ttu-id="3d13a-138">Haga clic en **Comprobar nombres**.</span><span class="sxs-lookup"><span data-stu-id="3d13a-138">Click **Check Names**.</span></span> <span data-ttu-id="3d13a-139">Cuando se resuelva el nombre del equipo, se mostrará subrayado.</span><span class="sxs-lookup"><span data-stu-id="3d13a-139">When the name of the computer resolves, it’ll be underlined.</span></span> <span data-ttu-id="3d13a-140">Haga clic en **Aceptar** y luego en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="3d13a-140">Click **OK**, then click **Finish**.</span></span> <span data-ttu-id="3d13a-141">Haga clic en **Aceptar** para confirmar la selección y cerrar el cuadro de diálogo **Agregar o quitar complementos**.</span><span class="sxs-lookup"><span data-stu-id="3d13a-141">Click **OK** to commit the selection and close the **Add or Remove Snap-ins** dialog.</span></span>

9.  <span data-ttu-id="3d13a-p113">Para ver las propiedades del certificado, expanda **Certificados**, **Personal** y seleccione **Certificados**. Seleccione el certificado que desea ver, haga clic en el certificado y seleccione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="3d13a-p113">To view the properties of the certificate, expand **Certificates**, expand **Personal**, and select **Certificates**. Select the certificate to view, right-click on the certificate and select **Open**.</span></span>

10. <span data-ttu-id="3d13a-p114">En la vista **Certificado**, seleccione **Detalles**. Desde aquí, puede elegir el nombre de sujeto del certificado seleccionando **Sujeto** y se muestran el nombre del sujeto asignado y propiedades asociadas.</span><span class="sxs-lookup"><span data-stu-id="3d13a-p114">In the **Certificate** view, select **Details**. From here, you can select the certificate subject name by selecting **Subject** and the assigned subject name and associated properties are displayed.</span></span>

11. <span data-ttu-id="3d13a-146">Para ver los nombres alternativos del sujeto asignados, seleccione **Nombre alternativo del sujeto**.</span><span class="sxs-lookup"><span data-stu-id="3d13a-146">To view the assigned subject alternative names, select **Subject Alternative Name**.</span></span> <span data-ttu-id="3d13a-147">Todos los nombres alternativos de sujeto asignados se muestran aquí.</span><span class="sxs-lookup"><span data-stu-id="3d13a-147">All assigned subject alternative names are displayed here.</span></span> <span data-ttu-id="3d13a-148">Los nombres alternativos de sujeto que se encuentran aquí son del tipo **nombre DNS** de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="3d13a-148">The subject alternative names found here are of type **DNS Name** by default.</span></span> <span data-ttu-id="3d13a-149">Debe ver los siguientes miembros (todos los cuales deben ser nombres de dominio completos representados en los registros del host de DNS (A o, si IPv6 AAAA):</span><span class="sxs-lookup"><span data-stu-id="3d13a-149">You should see the following members (all of which should be fully qualified domain names as represented in DNS host (A or, if IPv6 AAAA) records:</span></span>
    
      - <span data-ttu-id="3d13a-150">Nombre de grupo para este grupo o el nombre de servidor único si no se trata de un grupo de servidores</span><span class="sxs-lookup"><span data-stu-id="3d13a-150">Pool name for this pool, or the single server name if this isn’t a pool</span></span>
    
      - <span data-ttu-id="3d13a-151">Nombre del servidor al que está asignado el certificado</span><span class="sxs-lookup"><span data-stu-id="3d13a-151">Server name that the certificate is assigned to</span></span>
    
      - <span data-ttu-id="3d13a-152">Registros de direcciones URL simples, normalmente reunión y marcación</span><span class="sxs-lookup"><span data-stu-id="3d13a-152">Simple URL records, typically meet and dialin</span></span>
    
      - <span data-ttu-id="3d13a-153">Nombres externos de servicios Web internos y servicios web (por ejemplo, webpool01.contoso.net, webpool01.contoso.com), en función de las elecciones realizadas en el generador de topologías y las selecciones de servicios web invalidadas.</span><span class="sxs-lookup"><span data-stu-id="3d13a-153">Web services internal and Web services external names (for example, webpool01.contoso.net, webpool01.contoso.com), based on choices made in Topology Builder and over-ridden web services selections.</span></span>
    
      - <span data-ttu-id="3d13a-154">Si ya está asignado, el lyncdiscover. \<sipdomain\> y lyncdiscoverinternal. \<sipdomain\> registros.</span><span class="sxs-lookup"><span data-stu-id="3d13a-154">If already assigned, the lyncdiscover.\<sipdomain\> and lyncdiscoverinternal.\<sipdomain\> records.</span></span>
    
    <span data-ttu-id="3d13a-155">El último elemento es lo que más le interesa: si hay una entrada de SAN de lyncdiscover y lyncdiscoverinternal.</span><span class="sxs-lookup"><span data-stu-id="3d13a-155">The last item is what you’re most interested in – if there’s a lyncdiscover and lyncdiscoverinternal SAN entry.</span></span>
    
    <span data-ttu-id="3d13a-156">Repita estos pasos si tiene varios certificados que comprobar.</span><span class="sxs-lookup"><span data-stu-id="3d13a-156">Repeat these steps if you have multiple certificates to check.</span></span> <span data-ttu-id="3d13a-157">Una vez que tenga esta información, puede cerrar la vista de certificado y MMC.</span><span class="sxs-lookup"><span data-stu-id="3d13a-157">Once you have this information, you can close the certificate view and the MMC.</span></span>

12. <span data-ttu-id="3d13a-158">Si falta un nombre alternativo del sujeto del servicio Detección automática, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3d13a-158">If an Autodiscover Service subject alternative name is missing, and you are using a single Default certificate for the Default, WebServicesInternal and WebServiceExternal types, do the following:</span></span>
    
      - <span data-ttu-id="3d13a-159">En el símbolo del sistema de la línea de comandos del shell de administración de Lync Server, escriba:</span><span class="sxs-lookup"><span data-stu-id="3d13a-159">At the Lync Server Management Shell command line prompt, type:</span></span>
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="3d13a-160">Si tiene varios dominios SIP, no puede usar el nuevo parámetro AllSipDomain.</span><span class="sxs-lookup"><span data-stu-id="3d13a-160">If you have many SIP domains, you can’t use the new AllSipDomain parameter.</span></span> <span data-ttu-id="3d13a-161">En su lugar, debe usar el parámetro DomainName.</span><span class="sxs-lookup"><span data-stu-id="3d13a-161">Instead, you need to use the DomainName parameter.</span></span> <span data-ttu-id="3d13a-162">Cuando usa el parámetro DomainName, tiene que definir el FQDN para los registros lyncdiscoverinternal y lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="3d13a-162">When you use the DomainName parameter, you’ve got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="3d13a-163">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="3d13a-163">For example:</span></span>
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - <span data-ttu-id="3d13a-164">Para asignar el certificado, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3d13a-164">To assign the certificate, type the following:</span></span>
        
            Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        <span data-ttu-id="3d13a-165">Donde “Huella digital” es la huella digital mostrada para el certificado que acaba de emitir.</span><span class="sxs-lookup"><span data-stu-id="3d13a-165">Where “Thumbprint” is the thumbprint displayed for the newly issued certificate.</span></span>

13. <span data-ttu-id="3d13a-166">Para que falte un SAN de detección automática interna cuando use certificados independientes para default, WebServicesInternal y WebServicesExternal, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3d13a-166">For a missing internal Autodiscover SAN when using separate certificates for Default, WebServicesInternal, and WebServicesExternal, do the following:</span></span>
    
      - <span data-ttu-id="3d13a-167">En el símbolo del sistema de la línea de comandos del shell de administración de Lync Server, escriba:</span><span class="sxs-lookup"><span data-stu-id="3d13a-167">At the Lync Server Management Shell command line prompt, type:</span></span>
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="3d13a-168">Si tiene varios dominios SIP, no puede usar el nuevo parámetro AllSipDomain.</span><span class="sxs-lookup"><span data-stu-id="3d13a-168">If you have many SIP domains, you can’t use the new AllSipDomain parameter.</span></span> <span data-ttu-id="3d13a-169">En su lugar, debe usar el parámetro DomainName.</span><span class="sxs-lookup"><span data-stu-id="3d13a-169">Instead, you need to use the DomainName parameter.</span></span> <span data-ttu-id="3d13a-170">Cuando usa el parámetro DomainName, tiene que usar un prefijo adecuado para el FQDN de dominio SIP.</span><span class="sxs-lookup"><span data-stu-id="3d13a-170">When you use the DomainName parameter, you’ve got to use an appropriate prefix for the SIP domain FQDN.</span></span> <span data-ttu-id="3d13a-171">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="3d13a-171">For example:</span></span>
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - <span data-ttu-id="3d13a-172">Para un nombre alternativo de sujeto del servicio Detección automática externa, en la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="3d13a-172">For a missing external Autodiscover subject alternative name, at the command line, type:</span></span>
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="3d13a-173">Si tiene varios dominios SIP, no puede usar el nuevo parámetro AllSipDomain.</span><span class="sxs-lookup"><span data-stu-id="3d13a-173">If you have many SIP domains, you can’t use the new AllSipDomain parameter.</span></span> <span data-ttu-id="3d13a-174">En su lugar, debe usar el parámetro DomainName.</span><span class="sxs-lookup"><span data-stu-id="3d13a-174">Instead, you need to use the DomainName parameter.</span></span> <span data-ttu-id="3d13a-175">Cuando usa el parámetro DomainName, tiene que usar un prefijo adecuado para el FQDN de dominio SIP.</span><span class="sxs-lookup"><span data-stu-id="3d13a-175">When you use the DomainName parameter, you’ve got to use an appropriate prefix for the SIP domain FQDN.</span></span> <span data-ttu-id="3d13a-176">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="3d13a-176">For example:</span></span>
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
    
      - <span data-ttu-id="3d13a-177">Para asignar tipos de certificados individuales, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3d13a-177">To assign the individual certificate types, type the following:</span></span>
        
            Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        <span data-ttu-id="3d13a-178">Donde “Huella digital” es la huella digital mostrada para el certificado individual que acaba de emitir.</span><span class="sxs-lookup"><span data-stu-id="3d13a-178">Where “Thumbprint” is the thumbprint displayed for the newly issued individual certificates.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="3d13a-179">Solo para tener en cuenta, los pasos 12 y 13 solo deben ejecutarse si la cuenta que los ejecuta tiene acceso a la entidad de certificación con los permisos adecuados.</span><span class="sxs-lookup"><span data-stu-id="3d13a-179">Just to note, Steps 12 and 13 should be run only if the account running them has access to the Certificate Authority with appropriate permissions.</span></span> <span data-ttu-id="3d13a-180">Si no puede iniciar sesión con una cuenta que tiene estos permisos, o si está usando una entidad de certificación pública o remota para los certificados, necesitará solicitarlos mediante el Asistente para la implementación de Lync Server, que se toca en la parte superior de la artículo.</span><span class="sxs-lookup"><span data-stu-id="3d13a-180">If you are unable to log in with an account that’s got those permissions, or if you’re using a public or remote Certificate Authority for your certificates, you would need to request them through the Lync Server Deployment Wizard, which was touched on at the top of the article.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

