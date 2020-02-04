---
title: 'Lync Server 2013: Modificación de certificados para movilidad'
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
ms.openlocfilehash: 150dc8c7b4021e1e2c7ccab6ccc71823c01c388e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756874"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modifying-certificates-for-mobility-in-lync-server-2013"></a><span data-ttu-id="38139-102">Modificación de certificados para movilidad en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="38139-102">Modifying certificates for mobility in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="38139-103">_**Última modificación del tema:** 2014-06-20_</span><span class="sxs-lookup"><span data-stu-id="38139-103">_**Topic Last Modified:** 2014-06-20_</span></span>

<span data-ttu-id="38139-104">Para admitir conexiones seguras entre su entorno de Lync y sus clientes móviles, los certificados de nivel de socket seguro (SSL) para el grupo de directores, el grupo front-end y el proxy inverso deben actualizarse con un nombre alternativo de asunto adicional ( SAN).</span><span class="sxs-lookup"><span data-stu-id="38139-104">To support secure connections between your Lync environment and your mobile clients, the Secure Socket Layer (SSL) certificates for your Director pool, Front End pool, and reverse proxy are going to need to be updated with some additional subject alternative name (SAN) entries.</span></span> <span data-ttu-id="38139-105">Si necesita consultar más detalles sobre los requisitos de certificados para la movilidad, consulte la sección requisitos técnicos de la [movilidad en Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md), pero básicamente tendrá que obtener nuevos certificados de la entidad emisora de certificados con las entradas de San adicionales incluidas y, después, agregar esos certificados siguiendo los pasos de este artículo.</span><span class="sxs-lookup"><span data-stu-id="38139-105">If you need to check out more details about the certificate requirements for mobility, see the Certificate Requirements section in [Technical requirements for mobility in Lync Server 2013](lync-server-2013-technical-requirements-for-mobility.md), but basically you’ll need to get new certificates from the Certificate Authority with the additional SAN entries included, and then add those certificates using this article’s steps.</span></span>

<span data-ttu-id="38139-106">Por supuesto que antes de empezar, suele ser una buena idea saber qué nombres alternativos de sujeto ya tienen los certificados.</span><span class="sxs-lookup"><span data-stu-id="38139-106">Of course before you begin, it’s usually a good idea to know what subject alternative names your certificates already have.</span></span> <span data-ttu-id="38139-107">Si no está seguro de lo que ya está configurado, hay muchas formas de averiguarlo. Si bien la opción está allí para ejecutar **Get-CsCertificate** y otros comandos de PowerShell para ver esta información, (que trataremos a continuación) de forma predeterminada, se truncarán los datos, por lo que es posible que no vea todas las propiedades que necesita.</span><span class="sxs-lookup"><span data-stu-id="38139-107">If you’re not sure what’s already been configured, there are a lot of ways to find out. While the option’s there to run the **Get-CsCertificate** and other PowerShell commands to view this information, (which we walk through below) by default that data will be truncated, so you may not get to see all the properties you need.</span></span> <span data-ttu-id="38139-108">Para obtener un buen aspecto del certificado y de todas sus propiedades, puede ir a Microsoft Management Console (MMC) y cargar el complemento certificados (que también trataremos a continuación), o bien, puede simplemente comprobar el Asistente para la implementación de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="38139-108">In order to get a good look at the certificate and all its properties, you can go to the Microsoft Management Console (MMC) and load the Certificates snap-in (which we also walk through below), or you can just check in the Lync Server Deployment Wizard.</span></span>

<span data-ttu-id="38139-109">Como se mencionó anteriormente, los pasos siguientes le guiarán en la actualización de certificados mediante el shell de administración de Lync Server y MMC.</span><span class="sxs-lookup"><span data-stu-id="38139-109">As noted above, the following steps will walk you through updating the certificates using the Lync Server Management Shell and the MMC.</span></span> <span data-ttu-id="38139-110">Si está interesado en usar el Asistente para certificados en el Asistente para la implementación de Lync Server, en su lugar, puede comprobar la [configuración de certificados para el director de Lync server 2013](lync-server-2013-configure-certificates-for-the-director.md) para el grupo de directores o directores, si ha configurado uno (es posible que no lo tenga).</span><span class="sxs-lookup"><span data-stu-id="38139-110">If you’re interested in using the Certificate Wizard in the Lync Server Deployment Wizard for this instead, you can check [Configure certificates for the Director in Lync Server 2013](lync-server-2013-configure-certificates-for-the-director.md) out for the Director or Director pool, if you configured one (you may not have).</span></span> <span data-ttu-id="38139-111">Para el servidor front-end o el grupo front-end, querrá ver [configurar certificados para servidores en Lync Server 2013](lync-server-2013-configure-certificates-for-servers.md).</span><span class="sxs-lookup"><span data-stu-id="38139-111">For the Front End Server or Front End pool, you’ll want to see [Configure certificates for servers in Lync Server 2013](lync-server-2013-configure-certificates-for-servers.md).</span></span>

<span data-ttu-id="38139-112">Un último aspecto que se debe tener en cuenta es que puede tener un único certificado predeterminado en el entorno de Lync Server 2013, o puede que tenga certificados separados de forma predeterminada (que es todo menos los servicios web), WebServicesExternal y WebServicesInternal.</span><span class="sxs-lookup"><span data-stu-id="38139-112">One last thing to keep in mind is that you may have a single Default certificate in your Lync Server 2013 environment, or you may have separate certificates for Default (which is everything but the web services), WebServicesExternal and WebServicesInternal.</span></span> <span data-ttu-id="38139-113">Independientemente de la configuración, estos pasos le ayudarán.</span><span class="sxs-lookup"><span data-stu-id="38139-113">Whatever your configuration, these steps should help you out.</span></span>

<div>

## <a name="to-update-certificates-with-new-subject-alternative-names-using-the-lync-server-management-shell"></a><span data-ttu-id="38139-114">Para actualizar certificados con nombres alternativos de asunto nuevos mediante el shell de administración de Lync Server</span><span class="sxs-lookup"><span data-stu-id="38139-114">To update certificates with new subject alternative names using the Lync Server Management Shell</span></span>

1.  <span data-ttu-id="38139-115">Debe iniciar sesión en su servidor de Lync Server 2013 con una cuenta que tenga derechos y permisos de administrador local.</span><span class="sxs-lookup"><span data-stu-id="38139-115">You need to log on to your Lync Server 2013 server using an account that has local administrator rights and permissions.</span></span> <span data-ttu-id="38139-116">Además, si está ejecutando el CsCertificate de **solicitud** de PowerShell en los pasos 12 y posteriores, la cuenta debe tener derechos para la entidad emisora de certificados especificada (CA).</span><span class="sxs-lookup"><span data-stu-id="38139-116">Additionally, if you’re running the PowerShell **Request-CsCertificate** in Steps 12 and beyond, the account needs to have rights to the specified Certificate Authority (CA).</span></span>

2.  <span data-ttu-id="38139-117">Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="38139-117">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="38139-118">Antes de poder asignar un certificado actualizado, tendrá que averiguar qué certificados se han asignado al servidor y para qué tipo de uso.</span><span class="sxs-lookup"><span data-stu-id="38139-118">Before you can assign an updated certificate, you’ll need to find out what certificates have been assigned to the server and for which type of use.</span></span> <span data-ttu-id="38139-119">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="38139-119">At the command line, type:</span></span>
    
        Get-CsCertificate

4.  <span data-ttu-id="38139-120">Revise la salida del paso anterior para ver si se ha asignado un certificado para varios usos, o si se ha asignado un certificado diferente para cada uso.</span><span class="sxs-lookup"><span data-stu-id="38139-120">Review the output from the previous step to see whether a single certificate has been assigned for multiple uses, or whether a different certificate is assigned for each use.</span></span> <span data-ttu-id="38139-121">Busque el parámetro use para saber cómo se usa un certificado.</span><span class="sxs-lookup"><span data-stu-id="38139-121">Look in the Use parameter to find out how a certificate’s being used.</span></span> <span data-ttu-id="38139-122">Compare el parámetro de la huella digital de los certificados mostrados para ver si el mismo certificado tiene varios usos.</span><span class="sxs-lookup"><span data-stu-id="38139-122">Compare the Thumbprint parameter for the displayed certificates to see if the same certificate has multiple uses.</span></span> <span data-ttu-id="38139-123">Mantén el ojo del parámetro de la huella digital.</span><span class="sxs-lookup"><span data-stu-id="38139-123">Keep your eye on the Thumbprint parameter.</span></span>

5.  <span data-ttu-id="38139-124">Actualice el certificado.</span><span class="sxs-lookup"><span data-stu-id="38139-124">Update the certificate.</span></span> <span data-ttu-id="38139-125">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="38139-125">At the command line, type:</span></span>
    
        Set-CsCertificate -Type <type of certificate as displayed in the Use parameter> -Thumbprint <unique identifier>
    
    <span data-ttu-id="38139-126">Por ejemplo, si el cmdlet **Get-CsCertificate** muestra un certificado con el uso predeterminado, otro con el uso de WebServicesInternal y otro con el uso de WebServicesExternal, y todos tenían el mismo valor de huella digital, en la línea de comandos, debe escribir:</span><span class="sxs-lookup"><span data-stu-id="38139-126">For example, if the **Get-CsCertificate** cmdlet displayed a certificate with Use of Default, another with a Use of WebServicesInternal, and another with a Use of WebServicesExternal, and they all had the same Thumbprint value, at the command line, you should type:</span></span>
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
    
    <span data-ttu-id="38139-127">**Importante:**</span><span class="sxs-lookup"><span data-stu-id="38139-127">**Important:**</span></span>
    
    <span data-ttu-id="38139-128">Si se asigna un certificado independiente para cada uso (por lo que el valor de la huella digital que ha activado anteriormente es diferente para cada certificado), es fundamental que **no** ejecute el cmdlet **set-CsCertificate** con varios tipos, como en el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="38139-128">If a separate certificate is assigned for each use (so the Thumbprint value you checked above is different for each certificate), it’s vital that you **don’t** run the **Set-CsCertificate** cmdlet with multiple types, as in the example above.</span></span> <span data-ttu-id="38139-129">En este caso, ejecute el cmdlet **set-CsCertificate** por separado para cada uso.</span><span class="sxs-lookup"><span data-stu-id="38139-129">In this case, run the **Set-CsCertificate** cmdlet separately for each use.</span></span> <span data-ttu-id="38139-130">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="38139-130">For example:</span></span>
    
        Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>

6.  <span data-ttu-id="38139-131">Para ver el certificado (o certificados), haga clic en **Inicio**, haga clic en **Ejecutar...**.</span><span class="sxs-lookup"><span data-stu-id="38139-131">To view the certificate (or certificates), click **Start**, click **Run…**.</span></span> <span data-ttu-id="38139-132">Escriba MMC para abrir la consola de administración de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="38139-132">Type MMC to open the Microsoft Management Console.</span></span>

7.  <span data-ttu-id="38139-133">En el menú MMC, seleccione **archivo**, seleccione **Agregar o quitar complemento...**, seleccione certificados.</span><span class="sxs-lookup"><span data-stu-id="38139-133">From the MMC menu, select **File**, select **Add/Remove snap-in…**, select Certificates.</span></span> <span data-ttu-id="38139-134">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="38139-134">Click **Add**.</span></span> <span data-ttu-id="38139-135">Cuando se le solicite, seleccione **cuenta de equipo**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="38139-135">When prompted, select **Computer account**, then click **Next**.</span></span>

8.  <span data-ttu-id="38139-136">Si este es el servidor donde se encuentra el certificado, seleccione **equipo local**.</span><span class="sxs-lookup"><span data-stu-id="38139-136">If this is the server where the certificate’s located, select **Local computer**.</span></span> <span data-ttu-id="38139-137">Si el certificado se encuentra en otro equipo, debe seleccionar **otro equipo**y, a continuación, puede escribir el nombre de dominio completo del equipo o hacer clic en **examinar** , escriba el nombre de **objeto que desea seleccionar**y escriba el nombre del equipo.</span><span class="sxs-lookup"><span data-stu-id="38139-137">If the certificate’s located on another computer, you should select **Another computer**, and then you can either type in the fully qualified domain name of the computer, or click **Browse** in **Enter the object name to select**, and type the name of the computer.</span></span> <span data-ttu-id="38139-138">Haga clic en **Comprobar nombres**.</span><span class="sxs-lookup"><span data-stu-id="38139-138">Click **Check Names**.</span></span> <span data-ttu-id="38139-139">Cuando se resuelva el nombre del equipo, aparecerá subrayado.</span><span class="sxs-lookup"><span data-stu-id="38139-139">When the name of the computer resolves, it’ll be underlined.</span></span> <span data-ttu-id="38139-140">Haga clic en **Aceptar**y, después, en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="38139-140">Click **OK**, then click **Finish**.</span></span> <span data-ttu-id="38139-141">Haga clic en **Aceptar** para confirmar la selección y cerrar el cuadro de diálogo **Agregar o quitar complementos** .</span><span class="sxs-lookup"><span data-stu-id="38139-141">Click **OK** to commit the selection and close the **Add or Remove Snap-ins** dialog.</span></span>

9.  <span data-ttu-id="38139-142">Para ver las propiedades del certificado, expanda **certificados**, expanda **personal**y seleccione **certificados**.</span><span class="sxs-lookup"><span data-stu-id="38139-142">To view the properties of the certificate, expand **Certificates**, expand **Personal**, and select **Certificates**.</span></span> <span data-ttu-id="38139-143">Seleccione el certificado que desea ver, haga clic con el botón derecho en el certificado y seleccione **abrir**.</span><span class="sxs-lookup"><span data-stu-id="38139-143">Select the certificate to view, right-click on the certificate and select **Open**.</span></span>

10. <span data-ttu-id="38139-144">En la vista del **certificado** , seleccione **detalles**.</span><span class="sxs-lookup"><span data-stu-id="38139-144">In the **Certificate** view, select **Details**.</span></span> <span data-ttu-id="38139-145">Desde aquí, puede seleccionar el nombre del sujeto del certificado seleccionando **asunto** y se muestran el nombre del asunto asignado y las propiedades asociadas.</span><span class="sxs-lookup"><span data-stu-id="38139-145">From here, you can select the certificate subject name by selecting **Subject** and the assigned subject name and associated properties are displayed.</span></span>

11. <span data-ttu-id="38139-146">Para ver los nombres alternativos del asunto asignados, seleccione **nombre alternativo del asunto**.</span><span class="sxs-lookup"><span data-stu-id="38139-146">To view the assigned subject alternative names, select **Subject Alternative Name**.</span></span> <span data-ttu-id="38139-147">Aquí se muestran todos los nombres alternativos del asunto asignados.</span><span class="sxs-lookup"><span data-stu-id="38139-147">All assigned subject alternative names are displayed here.</span></span> <span data-ttu-id="38139-148">Los nombres alternativos de asunto que se encuentran aquí son de tipo **DNS** de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="38139-148">The subject alternative names found here are of type **DNS Name** by default.</span></span> <span data-ttu-id="38139-149">Debería ver los siguientes miembros (que deben ser nombres de dominio totalmente cualificados, como se representa en host DNS (si es IPv6 AAAA) los registros:</span><span class="sxs-lookup"><span data-stu-id="38139-149">You should see the following members (all of which should be fully qualified domain names as represented in DNS host (A or, if IPv6 AAAA) records:</span></span>
    
      - <span data-ttu-id="38139-150">Nombre de grupo para este grupo o el nombre de servidor único si no se trata de un grupo</span><span class="sxs-lookup"><span data-stu-id="38139-150">Pool name for this pool, or the single server name if this isn’t a pool</span></span>
    
      - <span data-ttu-id="38139-151">Nombre del servidor al que está asignado el certificado</span><span class="sxs-lookup"><span data-stu-id="38139-151">Server name that the certificate is assigned to</span></span>
    
      - <span data-ttu-id="38139-152">Registros de dirección URL simples, que suelen reunirse y marcar</span><span class="sxs-lookup"><span data-stu-id="38139-152">Simple URL records, typically meet and dialin</span></span>
    
      - <span data-ttu-id="38139-153">Nombres externos de servicios web y internos de servicios web (por ejemplo, webpool01.contoso.net, webpool01.contoso.com), en función de las opciones seleccionadas en las selecciones del generador de topología y de los servicios web reemplazados.</span><span class="sxs-lookup"><span data-stu-id="38139-153">Web services internal and Web services external names (for example, webpool01.contoso.net, webpool01.contoso.com), based on choices made in Topology Builder and over-ridden web services selections.</span></span>
    
      - <span data-ttu-id="38139-154">Si ya está asignado, la lyncdiscover. \<sipdomain\> y lyncdiscoverinternal. \<sipdomain\> registros.</span><span class="sxs-lookup"><span data-stu-id="38139-154">If already assigned, the lyncdiscover.\<sipdomain\> and lyncdiscoverinternal.\<sipdomain\> records.</span></span>
    
    <span data-ttu-id="38139-155">El último elemento es lo que te interesa más interesado: si hay una lyncdiscover y lyncdiscoverinternal de SAN.</span><span class="sxs-lookup"><span data-stu-id="38139-155">The last item is what you’re most interested in – if there’s a lyncdiscover and lyncdiscoverinternal SAN entry.</span></span>
    
    <span data-ttu-id="38139-156">Repita estos pasos si tiene varios certificados para comprobar.</span><span class="sxs-lookup"><span data-stu-id="38139-156">Repeat these steps if you have multiple certificates to check.</span></span> <span data-ttu-id="38139-157">Una vez que tenga esta información, puede cerrar la vista certificado y MMC.</span><span class="sxs-lookup"><span data-stu-id="38139-157">Once you have this information, you can close the certificate view and the MMC.</span></span>

12. <span data-ttu-id="38139-158">Si falta un nombre alternativo de asunto del servicio de detección automática y está usando un único certificado predeterminado para los tipos predeterminados, WebServicesInternal y WebServiceExternal, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="38139-158">If an Autodiscover Service subject alternative name is missing, and you are using a single Default certificate for the Default, WebServicesInternal and WebServiceExternal types, do the following:</span></span>
    
      - <span data-ttu-id="38139-159">En el símbolo del sistema del shell de administración de Lync Server, escriba:</span><span class="sxs-lookup"><span data-stu-id="38139-159">At the Lync Server Management Shell command line prompt, type:</span></span>
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="38139-160">Si tiene muchos dominios SIP, no puede usar el nuevo parámetro AllSipDomain.</span><span class="sxs-lookup"><span data-stu-id="38139-160">If you have many SIP domains, you can’t use the new AllSipDomain parameter.</span></span> <span data-ttu-id="38139-161">En su lugar, debe usar el parámetro DomainName.</span><span class="sxs-lookup"><span data-stu-id="38139-161">Instead, you need to use the DomainName parameter.</span></span> <span data-ttu-id="38139-162">Cuando use el parámetro DomainName, tendrá que definir el FQDN para los registros lyncdiscoverinternal y lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="38139-162">When you use the DomainName parameter, you’ve got to define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="38139-163">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="38139-163">For example:</span></span>
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - <span data-ttu-id="38139-164">Para asignar el certificado, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="38139-164">To assign the certificate, type the following:</span></span>
        
            Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        <span data-ttu-id="38139-165">Donde "huella digital" es la huella digital que se muestra para el certificado recién emitido.</span><span class="sxs-lookup"><span data-stu-id="38139-165">Where “Thumbprint” is the thumbprint displayed for the newly issued certificate.</span></span>

13. <span data-ttu-id="38139-166">Para una SAN interna de detección automática que falta al usar certificados independientes para default, WebServicesInternal y WebServicesExternal, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="38139-166">For a missing internal Autodiscover SAN when using separate certificates for Default, WebServicesInternal, and WebServicesExternal, do the following:</span></span>
    
      - <span data-ttu-id="38139-167">En el símbolo del sistema del shell de administración de Lync Server, escriba:</span><span class="sxs-lookup"><span data-stu-id="38139-167">At the Lync Server Management Shell command line prompt, type:</span></span>
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="38139-168">Si tiene muchos dominios SIP, no puede usar el nuevo parámetro AllSipDomain.</span><span class="sxs-lookup"><span data-stu-id="38139-168">If you have many SIP domains, you can’t use the new AllSipDomain parameter.</span></span> <span data-ttu-id="38139-169">En su lugar, debe usar el parámetro DomainName.</span><span class="sxs-lookup"><span data-stu-id="38139-169">Instead, you need to use the DomainName parameter.</span></span> <span data-ttu-id="38139-170">Cuando use el parámetro DomainName, tendrá que usar un prefijo adecuado para el FQDN del dominio SIP.</span><span class="sxs-lookup"><span data-stu-id="38139-170">When you use the DomainName parameter, you’ve got to use an appropriate prefix for the SIP domain FQDN.</span></span> <span data-ttu-id="38139-171">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="38139-171">For example:</span></span>
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - <span data-ttu-id="38139-172">Para un nombre alternativo externo de asunto de detección automática, en la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="38139-172">For a missing external Autodiscover subject alternative name, at the command line, type:</span></span>
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="38139-173">Si tiene muchos dominios SIP, no puede usar el nuevo parámetro AllSipDomain.</span><span class="sxs-lookup"><span data-stu-id="38139-173">If you have many SIP domains, you can’t use the new AllSipDomain parameter.</span></span> <span data-ttu-id="38139-174">En su lugar, debe usar el parámetro DomainName.</span><span class="sxs-lookup"><span data-stu-id="38139-174">Instead, you need to use the DomainName parameter.</span></span> <span data-ttu-id="38139-175">Cuando use el parámetro DomainName, tendrá que usar un prefijo adecuado para el FQDN del dominio SIP.</span><span class="sxs-lookup"><span data-stu-id="38139-175">When you use the DomainName parameter, you’ve got to use an appropriate prefix for the SIP domain FQDN.</span></span> <span data-ttu-id="38139-176">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="38139-176">For example:</span></span>
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
    
      - <span data-ttu-id="38139-177">Para asignar los tipos de certificado individuales, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="38139-177">To assign the individual certificate types, type the following:</span></span>
        
            Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        <span data-ttu-id="38139-178">Donde "huella digital" es la huella digital que se muestra para los certificados individuales recién emitidos.</span><span class="sxs-lookup"><span data-stu-id="38139-178">Where “Thumbprint” is the thumbprint displayed for the newly issued individual certificates.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="38139-179">Solo para tener en cuenta, los pasos 12 y 13 solo se deben ejecutar si la cuenta que los ejecuta tiene acceso a la entidad emisora de certificados con los permisos adecuados.</span><span class="sxs-lookup"><span data-stu-id="38139-179">Just to note, Steps 12 and 13 should be run only if the account running them has access to the Certificate Authority with appropriate permissions.</span></span> <span data-ttu-id="38139-180">Si no puede iniciar sesión con una cuenta que tiene esos permisos, o si usa una entidad emisora de certificados pública o remota para sus certificados, necesitará solicitarlos mediante el Asistente para la implementación de Lync Server, que se ha tocado en la parte superior de la Knowledge.</span><span class="sxs-lookup"><span data-stu-id="38139-180">If you are unable to log in with an account that’s got those permissions, or if you’re using a public or remote Certificate Authority for your certificates, you would need to request them through the Lync Server Deployment Wizard, which was touched on at the top of the article.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

