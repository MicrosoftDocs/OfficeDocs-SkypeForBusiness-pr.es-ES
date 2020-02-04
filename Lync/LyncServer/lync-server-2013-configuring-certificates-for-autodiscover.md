---
title: 'Lync Server 2013: configuración de certificados para la detección automática'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring certificates for Autodiscover
ms:assetid: 1842191d-df9a-41e0-9286-08c25f9b5dca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945617(v=OCS.15)
ms:contentKeyID: 51541453
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c1f2a89cf317a0ea5bead4bb24eba1469ef1108e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758338"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-certificates-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="49809-102">Configuración de certificados para la detección automática en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="49809-102">Configuring certificates for Autodiscover in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="49809-103">_**Última modificación del tema:** 2012-12-12_</span><span class="sxs-lookup"><span data-stu-id="49809-103">_**Topic Last Modified:** 2012-12-12_</span></span>

<span data-ttu-id="49809-104">Los certificados para el grupo de directores, el grupo front-end y el proxy inverso requieren entradas de nombre alternativo adicionales para admitir conexiones seguras con clientes de Lync.</span><span class="sxs-lookup"><span data-stu-id="49809-104">The certificates for your Director pool, Front End pool, and reverse proxy require additional subject alternative name entries to support secure connections with Lync clients.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="49809-105">Puede usar el cmdlet <STRONG>Get-CsCertificate</STRONG> para ver información sobre los certificados asignados actualmente.</span><span class="sxs-lookup"><span data-stu-id="49809-105">You can use the <STRONG>Get-CsCertificate</STRONG> cmdlet to view information about the currently assigned certificates.</span></span> <span data-ttu-id="49809-106">Sin embargo, la vista predeterminada trunca las propiedades del certificado y no muestra todos los valores de la propiedad SubjectAlternativeNames.</span><span class="sxs-lookup"><span data-stu-id="49809-106">However, the default view truncates the properties of the certificate and does not display all values in the SubjectAlternativeNames property.</span></span> <span data-ttu-id="49809-107">Puede usar los cmdlets <STRONG>Get-CsCertificate</STRONG> , <STRONG>request-</STRONG>CsCertificate y <STRONG>set-CsCertificate</STRONG> para ver cierta información y para solicitar y asignar certificados.</span><span class="sxs-lookup"><span data-stu-id="49809-107">You can use the <STRONG>Get-CsCertificate</STRONG> , <STRONG>Request-</STRONG>CsCertificate and the <STRONG>Set-CsCertificate</STRONG> cmdlets to view some information and to request and assign certificates.</span></span> <span data-ttu-id="49809-108">Sin embargo, no es el mejor método de uso si no está seguro de las propiedades de los nombres alternativos de asunto (SAN) en el certificado actual.</span><span class="sxs-lookup"><span data-stu-id="49809-108">However, it’s not the best method to use if you are unsure of the properties of the subject alternative names (SAN) on the current certificate.</span></span> <span data-ttu-id="49809-109">Para ver el certificado y todos los miembros de la propiedad, se recomienda usar el complemento certificados en <EM>Microsoft Management Console (MMC)</EM> o usar el Asistente para la implementación de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="49809-109">To view the certificate and all property members, it is suggested to use the Certificates snap-in the <EM>Microsoft Management Console (MMC)</EM> or to use the Lync Server Deployment Wizard.</span></span> <span data-ttu-id="49809-110">En el Asistente para la implementación de Lync Server, puede usar el Asistente para la implementación de certificados para ver las propiedades del certificado.</span><span class="sxs-lookup"><span data-stu-id="49809-110">In the Lync Server Deployment Wizard, you can use the Certificate Wizard to view the certificate properties.</span></span> <span data-ttu-id="49809-111">Los procedimientos para ver, solicitar y asignar un certificado mediante el shell de administración de Lync Server y <EM>Microsoft Management Console (MMC)</EM> se detallan en los procedimientos siguientes.</span><span class="sxs-lookup"><span data-stu-id="49809-111">The procedures for viewing, requesting and assigning a certificate using the Lync Server Management Shell and the <EM>Microsoft Management Console (MMC)</EM> are detailed in the following procedures.</span></span> <span data-ttu-id="49809-112">Para usar el Asistente para la implementación de Lync Server, vea detalles aquí si ha implementado el grupo opcional de directores o directores: <A href="lync-server-2013-configure-certificates-for-the-director.md">configurar certificados para el Director en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="49809-112">To use the Lync Server Deployment Wizard, see details here if you have deployed the optional Director or Director pool: <A href="lync-server-2013-configure-certificates-for-the-director.md">Configure certificates for the Director in Lync Server 2013</A>.</span></span> <span data-ttu-id="49809-113">Para el servidor front-end o el grupo front-end, consulte los detalles aquí: <A href="lync-server-2013-configure-certificates-for-servers.md">configurar certificados para servidores en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="49809-113">For the Front End Server or Front End pool, see the details here: <A href="lync-server-2013-configure-certificates-for-servers.md">Configure certificates for servers in Lync Server 2013</A>.</span></span><BR><span data-ttu-id="49809-114">Los pasos iniciales de este procedimiento son pasos de preparación para orientarse en cuanto a la función de reproducción de los certificados actuales.</span><span class="sxs-lookup"><span data-stu-id="49809-114">The initial steps in this procedure are preparation steps, to orient you as to what role the current certificates play.</span></span> <span data-ttu-id="49809-115">De forma predeterminada, los certificados no tendrán un lyncdiscover. &lt;sipdomain&gt; o lyncdiscoverinternal. &lt;nombre&gt; de dominio interno, a menos que haya instalado previamente servicios de movilidad o haya preparado los certificados con antelación.</span><span class="sxs-lookup"><span data-stu-id="49809-115">By default, the certificates will not have a lyncdiscover.&lt;sipdomain&gt; or lyncdiscoverinternal.&lt;internal domain name&gt; entry unless you have previously installed Mobility Services or have prepared your certificates in advance.</span></span> <span data-ttu-id="49809-116">Este procedimiento usa el ejemplo de nombre de dominio SIP ' contoso.com ' y el nombre de dominio interno ' contoso.net ' de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="49809-116">This procedure uses the example SIP domain name ‘contoso.com’ and the example internal domain name ‘contoso.net’.</span></span><BR><span data-ttu-id="49809-117">La configuración de certificado predeterminada para Lync Server 2013 y Lync Server 2010 es usar un único certificado (denominado ' predeterminado ') con los propósitos predeterminados (para todos los propósitos excepto los servicios web), WebServicesExternal y WebServicesInternal.</span><span class="sxs-lookup"><span data-stu-id="49809-117">The default certificate configuration for Lync Server 2013 and Lync Server 2010 is to use a single certificate (named ‘Default’) with the purposes Default (for all purposes except for the web services), WebServicesExternal and WebServicesInternal.</span></span> <span data-ttu-id="49809-118">Una configuración opcional es usar certificados independientes para cada propósito.</span><span class="sxs-lookup"><span data-stu-id="49809-118">An optional configuration is to use separate certificates for each purpose.</span></span> <span data-ttu-id="49809-119">Los certificados se pueden administrar mediante el shell de administración de Lync Server y los cmdlets de Windows PowerShell, o bien mediante el Asistente para certificados del Asistente para la implementación de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="49809-119">Certificates can be managed by using the Lync Server Management Shell and Windows PowerShell cmdlets, or by using the Certificate Wizard in the Lync Server Deployment Wizard.</span></span>



</div>

<div>

## <a name="to-update-certificates-with-new-subject-alternative-names-using-the-lync-server-management-shell"></a><span data-ttu-id="49809-120">Para actualizar certificados con nombres alternativos de asunto nuevos mediante el shell de administración de Lync Server</span><span class="sxs-lookup"><span data-stu-id="49809-120">To update certificates with new subject alternative names using the Lync Server Management Shell</span></span>

1.  <span data-ttu-id="49809-121">Inicie sesión en el equipo con una cuenta que tenga derechos y permisos de administrador local.</span><span class="sxs-lookup"><span data-stu-id="49809-121">Log on to the computer using an account that has local administrator rights and permissions.</span></span>

2.  <span data-ttu-id="49809-122">Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="49809-122">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="49809-123">Averigüe qué certificados se han asignado al servidor y para qué tipo de uso.</span><span class="sxs-lookup"><span data-stu-id="49809-123">Find out what certificates have been assigned to the server and for which type of use.</span></span> <span data-ttu-id="49809-124">Necesitas esta información en el siguiente paso para asignar el certificado actualizado.</span><span class="sxs-lookup"><span data-stu-id="49809-124">You need this information in the next step to assign the updated certificate.</span></span> <span data-ttu-id="49809-125">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="49809-125">At the command line, type:</span></span>
    
        Get-CsCertificate

4.  <span data-ttu-id="49809-126">Mire la salida del paso anterior para ver si se asigna un único certificado para varios usos o si se asigna un certificado diferente para cada uso.</span><span class="sxs-lookup"><span data-stu-id="49809-126">Look in the output from the previous step to see whether a single certificate is assigned for multiple uses or whether a different certificate is assigned for each use.</span></span> <span data-ttu-id="49809-127">Busque el parámetro use para saber cómo se usa un certificado.</span><span class="sxs-lookup"><span data-stu-id="49809-127">Look in the Use parameter to find out how a certificate is used.</span></span> <span data-ttu-id="49809-128">Compare el parámetro de la huella digital de los certificados mostrados para ver si el mismo certificado tiene varios usos.</span><span class="sxs-lookup"><span data-stu-id="49809-128">Compare the Thumbprint parameter for the displayed certificates to see if the same certificate has multiple uses.</span></span>

5.  <span data-ttu-id="49809-129">Actualice el certificado.</span><span class="sxs-lookup"><span data-stu-id="49809-129">Update the certificate.</span></span> <span data-ttu-id="49809-130">En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="49809-130">At the command line, type:</span></span>
    
        Set-CsCertificate -Type <type of certificate as displayed in the Use parameter> -Thumbprint <unique identifier>
    
    <span data-ttu-id="49809-131">Por ejemplo, si el cmdlet **Get-CsCertificate** muestra un certificado con el uso predeterminado, otro con el uso de WebServicesInternal y otro con el uso de WebServicesExternal, y todos tenían el mismo valor de huella digital, en la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="49809-131">For example, if the **Get-CsCertificate** cmdlet displayed a certificate with Use of Default, another with a Use of WebServicesInternal, and another with a Use of WebServicesExternal, and they all had the same Thumbprint value, at the command line, type:</span></span>
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
    
    <span data-ttu-id="49809-132">**Importante:**</span><span class="sxs-lookup"><span data-stu-id="49809-132">**Important:**</span></span>
    
    <span data-ttu-id="49809-133">Si se asigna un certificado independiente para cada uso (el valor de la huella digital es diferente para cada certificado), es importante que no ejecute el cmdlet **set-CsCertificate** con varios tipos.</span><span class="sxs-lookup"><span data-stu-id="49809-133">If a separate certificate is assigned for each use (the Thumbprint value is different for each certificate), it is important that you do not run the **Set-CsCertificate** cmdlet with multiple types.</span></span> <span data-ttu-id="49809-134">En este caso, ejecute el cmdlet **set-CsCertificate** por separado para cada uso.</span><span class="sxs-lookup"><span data-stu-id="49809-134">In this case, run the **Set-CsCertificate** cmdlet separately for each use.</span></span> <span data-ttu-id="49809-135">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="49809-135">For example:</span></span>
    
        Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>

6.  <span data-ttu-id="49809-136">Para ver el certificado, haga clic en **Inicio**, haga clic en **Ejecutar...**.</span><span class="sxs-lookup"><span data-stu-id="49809-136">To view the certificate, click **Start**, click **Run…**.</span></span> <span data-ttu-id="49809-137">Escriba MMC para abrir la consola de administración de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="49809-137">Type MMC to open the Microsoft Management Console.</span></span>

7.  <span data-ttu-id="49809-138">En el menú MMC, seleccione **archivo**, seleccione **Agregar o quitar complemento...**, seleccione certificados.</span><span class="sxs-lookup"><span data-stu-id="49809-138">From the MMC menu, select **File**, select **Add/Remove snap-in…**, select Certificates.</span></span> <span data-ttu-id="49809-139">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="49809-139">Click **Add**.</span></span> <span data-ttu-id="49809-140">Cuando se le solicite, seleccione **cuenta de equipo**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="49809-140">When prompted, select **Computer account**, then click **Next**.</span></span>

8.  <span data-ttu-id="49809-141">Si el certificado se encuentra en este equipo, seleccione **equipo local**.</span><span class="sxs-lookup"><span data-stu-id="49809-141">If the certificate is located on this computer, select **Local computer**.</span></span> <span data-ttu-id="49809-142">Si el certificado se encuentra en otro equipo, seleccione **otro equipo**, escriba el nombre de dominio completo del equipo o haga clic en **examinar** en **Escriba el nombre de objeto para seleccionar**, escriba el nombre del equipo.</span><span class="sxs-lookup"><span data-stu-id="49809-142">If the certificate is located on another computer, select **Another computer**, type in the fully qualified domain name of the computer or click **Browse** In **Enter the object name to select**, type the name of the computer.</span></span> <span data-ttu-id="49809-143">Haga clic en **Comprobar nombres**.</span><span class="sxs-lookup"><span data-stu-id="49809-143">Click **Check Names**.</span></span> <span data-ttu-id="49809-144">Cuando el nombre del equipo se resuelva, estará subrayado.</span><span class="sxs-lookup"><span data-stu-id="49809-144">When the name of the computer is resolved, it will be underlined.</span></span> <span data-ttu-id="49809-145">Haga clic en **Aceptar**y, después, en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="49809-145">Click **OK**, then click **Finish**.</span></span> <span data-ttu-id="49809-146">Haga clic en **Aceptar** para confirmar la selección y cerrar el cuadro de diálogo **Agregar o quitar complementos** .</span><span class="sxs-lookup"><span data-stu-id="49809-146">Click **OK** to commit the selection and close the **Add or Remove Snap-ins** dialog.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="49809-147">Si el certificado no se muestra en la consola, asegúrese de que no ha seleccionado el usuario o el servicio.</span><span class="sxs-lookup"><span data-stu-id="49809-147">If the certificate does not show up in the console, ensure that you have not selected User or Service.</span></span> <span data-ttu-id="49809-148">Debes seleccionar equipo o no podrás encontrar el certificado de probper.</span><span class="sxs-lookup"><span data-stu-id="49809-148">You must select Computer, or you will not be able to locate the probper certificate.</span></span>

    
    </div>

9.  <span data-ttu-id="49809-149">Para ver las propiedades del certificado, expanda **certificados**, expanda **personal**y seleccione **certificados**.</span><span class="sxs-lookup"><span data-stu-id="49809-149">To view the properties of the certificate, expand **Certificates**, expand **Personal**, and select **Certificates**.</span></span> <span data-ttu-id="49809-150">Seleccione el certificado que desea ver, haga clic con el botón derecho en el certificado y seleccione **abrir**.</span><span class="sxs-lookup"><span data-stu-id="49809-150">Select the certificate to view, right-click on the certificate and select **Open**.</span></span>

10. <span data-ttu-id="49809-151">En la vista del **certificado** , seleccione **detalles**.</span><span class="sxs-lookup"><span data-stu-id="49809-151">In the **Certificate** view, select **Details**.</span></span> <span data-ttu-id="49809-152">Desde aquí, puede seleccionar el nombre del sujeto del certificado seleccionando **asunto** y se muestran el nombre del asunto asignado y las propiedades asociadas.</span><span class="sxs-lookup"><span data-stu-id="49809-152">From here, you can select the certificate subject name by selecting **Subject** and the assigned subject name and associated properties are displayed.</span></span>

11. <span data-ttu-id="49809-153">Para ver los nombres alternativos del asunto asignados, seleccione **nombre alternativo del asunto**.</span><span class="sxs-lookup"><span data-stu-id="49809-153">To view the assigned subject alternative names, select **Subject Alternative Name**.</span></span> <span data-ttu-id="49809-154">Se muestran todos los nombres alternativos del asunto asignados.</span><span class="sxs-lookup"><span data-stu-id="49809-154">All assigned subject alternative names are displayed.</span></span> <span data-ttu-id="49809-155">De forma predeterminada, los nombres alternativos de asunto que se encuentran en la propiedad son de tipo **DNS** .</span><span class="sxs-lookup"><span data-stu-id="49809-155">The subject alternative names that are found in the property are of type **DNS Name** by default.</span></span> <span data-ttu-id="49809-156">Debería ver los siguientes miembros (que deben ser nombres de dominio totalmente cualificados, como se representa en host DNS (si es IPv6 AAAA) los registros:</span><span class="sxs-lookup"><span data-stu-id="49809-156">You should see the following members (all of which should be fully qualified domain names as represented in DNS host (A or, if IPv6 AAAA) records:</span></span>
    
      - <span data-ttu-id="49809-157">Nombre de grupo para este grupo o el nombre de un servidor si no es un grupo</span><span class="sxs-lookup"><span data-stu-id="49809-157">Pool name for this pool, or the single server name if this is not a pool</span></span>
    
      - <span data-ttu-id="49809-158">Nombre del servidor al que está asignado el certificado</span><span class="sxs-lookup"><span data-stu-id="49809-158">Server name that the certificate is assigned to</span></span>
    
      - <span data-ttu-id="49809-159">Registros de dirección URL simples, que suelen reunirse y marcar</span><span class="sxs-lookup"><span data-stu-id="49809-159">Simple URL records, typically meet and dialin</span></span>
    
      - <span data-ttu-id="49809-160">Nombres externos de servicios web y internos de servicios web (por ejemplo, webpool01.contoso.net, webpool01.contoso.com), en función de las opciones seleccionadas en las selecciones del generador de topología y de los servicios web reemplazados.</span><span class="sxs-lookup"><span data-stu-id="49809-160">Web services internal and Web services external names (for example, webpool01.contoso.net, webpool01.contoso.com), based on choices made in Topology Builder and over-ridden web services selections.</span></span>
    
      - <span data-ttu-id="49809-161">Si ya está asignado, la lyncdiscover. \<sipdomain\> y lyncdiscoverinternal. \<sipdomain\> registros.</span><span class="sxs-lookup"><span data-stu-id="49809-161">If already assigned, the lyncdiscover.\<sipdomain\> and lyncdiscoverinternal.\<sipdomain\> records.</span></span>
    
    <span data-ttu-id="49809-162">El último elemento es lo que más le interesa: si existe una lyncdiscover y lyncdiscoverinternal de SAN.</span><span class="sxs-lookup"><span data-stu-id="49809-162">The last item is what you are most interested in – if there is a lyncdiscover and lyncdiscoverinternal SAN entry.</span></span>
    
    <span data-ttu-id="49809-163">Una vez que tenga esta información, puede cerrar la vista certificado y MMC.</span><span class="sxs-lookup"><span data-stu-id="49809-163">Once you have this information, you can close the certificate view and the MMC.</span></span>

12. <span data-ttu-id="49809-164">Si es un servicio de detección automática, es decir, el lyncdiscover. \>nombre\> de dominio y lyncdiscoverinternal. \<nombre\> de dominio (según se trata de un certificado externo o interno) no se encuentra el nombre alternativo de asunto y está usando un único certificado predeterminado para los tipos predeterminados, WebServicesInternal y WebServiceExternal, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="49809-164">If an Autodiscover Service, meaning the lyncdiscover.\>domain name\> and lyncdiscoverinternal.\<domain name\> (based on if this is an external or internal certificate) subject alternative name is missing, and you are using a single Default certificate for the Default, WebServicesInternal and WebServiceExternal types, do the following:</span></span>
    
      - <span data-ttu-id="49809-165">En el símbolo del sistema del shell de administración de Lync Server, escriba:</span><span class="sxs-lookup"><span data-stu-id="49809-165">At the Lync Server Management Shell command line prompt, type:</span></span>
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="49809-166">Si tiene muchos dominios SIP, no puede usar el nuevo parámetro AllSipDomain.</span><span class="sxs-lookup"><span data-stu-id="49809-166">If you have many SIP domains, you cannot use the new AllSipDomain parameter.</span></span> <span data-ttu-id="49809-167">En su lugar, debe usar el parámetro DomainName.</span><span class="sxs-lookup"><span data-stu-id="49809-167">Instead, you must use DomainName parameter.</span></span> <span data-ttu-id="49809-168">Al usar el parámetro DomainName, debe definir el FQDN para los registros lyncdiscoverinternal y lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="49809-168">When you use the DomainName parameter, you must define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="49809-169">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="49809-169">For example:</span></span>
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - <span data-ttu-id="49809-170">Para asignar el certificado, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="49809-170">To assign the certificate, type the following:</span></span>
        
            Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        <span data-ttu-id="49809-171">Donde "huella digital" es la huella digital que se muestra para el certificado recién emitido.</span><span class="sxs-lookup"><span data-stu-id="49809-171">Where “Thumbprint” is the thumbprint displayed for the newly issued certificate.</span></span>

13. <span data-ttu-id="49809-172">En el caso de que falten nombres alternativos de sujeto de detección automática internos al usar certificados independientes para default, WebServicesInternal y WebServicesExternal, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="49809-172">For a missing internal Autodiscover subject alternative names when using separate certificates for Default, WebServicesInternal, and WebServicesExternal, do the following:</span></span>
    
      - <span data-ttu-id="49809-173">En el símbolo del sistema del shell de administración de Lync Server, escriba:</span><span class="sxs-lookup"><span data-stu-id="49809-173">At the Lync Server Management Shell command line prompt, type:</span></span>
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="49809-174">Si tiene muchos dominios SIP, no puede usar el nuevo parámetro AllSipDomain.</span><span class="sxs-lookup"><span data-stu-id="49809-174">If you have many SIP domains, you cannot use the new AllSipDomain parameter.</span></span> <span data-ttu-id="49809-175">En su lugar, debe usar el parámetro DomainName.</span><span class="sxs-lookup"><span data-stu-id="49809-175">Instead, you must use DomainName parameter.</span></span> <span data-ttu-id="49809-176">Al usar el parámetro DomainName, debe usar un prefijo adecuado para el FQDN del dominio SIP.</span><span class="sxs-lookup"><span data-stu-id="49809-176">When you use the DomainName parameter, you must use an appropriate prefix for the SIP domain FQDN.</span></span> <span data-ttu-id="49809-177">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="49809-177">For example:</span></span>
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - <span data-ttu-id="49809-178">Para un nombre alternativo externo de asunto de detección automática, en la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="49809-178">For a missing external Autodiscover subject alternative name, at the command line, type:</span></span>
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="49809-179">Si tiene muchos dominios SIP, no puede usar el nuevo parámetro AllSipDomain.</span><span class="sxs-lookup"><span data-stu-id="49809-179">If you have many SIP domains, you cannot use the new AllSipDomain parameter.</span></span> <span data-ttu-id="49809-180">En su lugar, debe usar el parámetro DomainName.</span><span class="sxs-lookup"><span data-stu-id="49809-180">Instead, you must use DomainName parameter.</span></span> <span data-ttu-id="49809-181">Al usar el parámetro DomainName, debe usar un prefijo adecuado para el FQDN del dominio SIP.</span><span class="sxs-lookup"><span data-stu-id="49809-181">When you use the DomainName parameter, you must use an appropriate prefix for the SIP domain FQDN.</span></span> <span data-ttu-id="49809-182">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="49809-182">For example:</span></span>
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
    
      - <span data-ttu-id="49809-183">Para asignar los tipos de certificado individuales, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="49809-183">To assign the individual certificate types, type the following:</span></span>
        
            Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        <span data-ttu-id="49809-184">Donde "huella digital" es la huella digital que se muestra para los certificados individuales recién emitidos.</span><span class="sxs-lookup"><span data-stu-id="49809-184">Where “Thumbprint” is the thumbprint displayed for the newly issued individual certificates.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

