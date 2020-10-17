---
title: 'Lync Server 2013: configuración de certificados para la detección automática'
description: 'Lync Server 2013: configuración de certificados para la detección automática.'
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
ms.openlocfilehash: 98ab9eca92685eef8bccc500dc4a91efa891dec6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568726"
---
# <a name="configuring-certificates-for-autodiscover-in-lync-server-2013"></a><span data-ttu-id="0437c-103">Configuración de certificados para la detección automática en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0437c-103">Configuring certificates for Autodiscover in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0437c-104">_**Última modificación del tema:** 2012-12-12_</span><span class="sxs-lookup"><span data-stu-id="0437c-104">_**Topic Last Modified:** 2012-12-12_</span></span>

<span data-ttu-id="0437c-105">Los certificados para el grupo de directores, el grupo de servidores front-end y el proxy inverso requieren entradas de nombre alternativo de sujeto adicionales para admitir conexiones seguras con los clientes de Lync.</span><span class="sxs-lookup"><span data-stu-id="0437c-105">The certificates for your Director pool, Front End pool, and reverse proxy require additional subject alternative name entries to support secure connections with Lync clients.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0437c-106">Puede usar el cmdlet <STRONG>Get-CsCertificate</STRONG> para ver información sobre los certificados asignados actualmente.</span><span class="sxs-lookup"><span data-stu-id="0437c-106">You can use the <STRONG>Get-CsCertificate</STRONG> cmdlet to view information about the currently assigned certificates.</span></span> <span data-ttu-id="0437c-107">Sin embargo, la vista predeterminada trunca las propiedades del certificado y no muestra todos los valores de la propiedad SubjectAlternativeNames.</span><span class="sxs-lookup"><span data-stu-id="0437c-107">However, the default view truncates the properties of the certificate and does not display all values in the SubjectAlternativeNames property.</span></span> <span data-ttu-id="0437c-108">Puede usar los cmdlets <STRONG>Get-CsCertificate</STRONG>, <STRONG>Request-</STRONG>CsCertificate y <STRONG>Set-CsCertificate</STRONG> para ver alguna información y solicitar y asignar certificados.</span><span class="sxs-lookup"><span data-stu-id="0437c-108">You can use the <STRONG>Get-CsCertificate</STRONG> , <STRONG>Request-</STRONG>CsCertificate and the <STRONG>Set-CsCertificate</STRONG> cmdlets to view some information and to request and assign certificates.</span></span> <span data-ttu-id="0437c-109">Sin embargo, no es el mejor método que hay que usar si no está seguro de las propiedades de los nombres alternativos del sujeto (SAN) sobre el certificado actual.</span><span class="sxs-lookup"><span data-stu-id="0437c-109">However, it’s not the best method to use if you are unsure of the properties of the subject alternative names (SAN) on the current certificate.</span></span> <span data-ttu-id="0437c-110">Para ver el certificado y todos los miembros de la propiedad, se recomienda usar el complemento certificados en <EM>Microsoft Management Console (MMC)</EM> o usar el Asistente para la implementación de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0437c-110">To view the certificate and all property members, it is suggested to use the Certificates snap-in the <EM>Microsoft Management Console (MMC)</EM> or to use the Lync Server Deployment Wizard.</span></span> <span data-ttu-id="0437c-111">En el Asistente para la implementación de Lync Server, puede usar el Asistente para certificados para ver las propiedades del certificado.</span><span class="sxs-lookup"><span data-stu-id="0437c-111">In the Lync Server Deployment Wizard, you can use the Certificate Wizard to view the certificate properties.</span></span> <span data-ttu-id="0437c-112">Los procedimientos para ver, solicitar y asignar un certificado mediante el shell de administración de Lync Server y <EM>Microsoft Management Console (MMC)</EM> se detallan en los siguientes procedimientos.</span><span class="sxs-lookup"><span data-stu-id="0437c-112">The procedures for viewing, requesting and assigning a certificate using the Lync Server Management Shell and the <EM>Microsoft Management Console (MMC)</EM> are detailed in the following procedures.</span></span> <span data-ttu-id="0437c-113">Para usar el Asistente para la implementación de Lync Server, vea los detalles aquí si ha implementado el director o el grupo de directores opcional: <A href="lync-server-2013-configure-certificates-for-the-director.md">Configure los certificados para el Director en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="0437c-113">To use the Lync Server Deployment Wizard, see details here if you have deployed the optional Director or Director pool: <A href="lync-server-2013-configure-certificates-for-the-director.md">Configure certificates for the Director in Lync Server 2013</A>.</span></span> <span data-ttu-id="0437c-114">Para el servidor front-end o el grupo de servidores front-end, vea los detalles aquí: <A href="lync-server-2013-configure-certificates-for-servers.md">configurar certificados para servidores en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="0437c-114">For the Front End Server or Front End pool, see the details here: <A href="lync-server-2013-configure-certificates-for-servers.md">Configure certificates for servers in Lync Server 2013</A>.</span></span><BR><span data-ttu-id="0437c-115">Los primeros pasos de este procedimiento son los pasos de preparación, para orientarle en cuanto a qué papel juegan los certificados actuales.</span><span class="sxs-lookup"><span data-stu-id="0437c-115">The initial steps in this procedure are preparation steps, to orient you as to what role the current certificates play.</span></span> <span data-ttu-id="0437c-116">De forma predeterminada, los certificados no tendrán un lyncdiscover. &lt; sipdomain &gt; o lyncdiscoverinternal. &lt; &gt; entrada de nombre de dominio interno a menos que haya instalado previamente servicios de movilidad o haya preparado los certificados con antelación.</span><span class="sxs-lookup"><span data-stu-id="0437c-116">By default, the certificates will not have a lyncdiscover.&lt;sipdomain&gt; or lyncdiscoverinternal.&lt;internal domain name&gt; entry unless you have previously installed Mobility Services or have prepared your certificates in advance.</span></span> <span data-ttu-id="0437c-117">Este procedimiento usa el nombre de dominio SIP de ejemplo para 'contoso.com' y el nombre de dominio interno de ejemplo 'contoso.net'.</span><span class="sxs-lookup"><span data-stu-id="0437c-117">This procedure uses the example SIP domain name ‘contoso.com’ and the example internal domain name ‘contoso.net’.</span></span><BR><span data-ttu-id="0437c-118">La configuración de certificado predeterminada para Lync Server 2013 y Lync Server 2010 es usar un único certificado (denominado "predeterminado") con los propósitos predeterminados (para todos los propósitos excepto para los servicios web), WebServicesExternal y WebServicesInternal.</span><span class="sxs-lookup"><span data-stu-id="0437c-118">The default certificate configuration for Lync Server 2013 and Lync Server 2010 is to use a single certificate (named ‘Default’) with the purposes Default (for all purposes except for the web services), WebServicesExternal and WebServicesInternal.</span></span> <span data-ttu-id="0437c-119">Una configuración opcional es usar certificados independientes para cada propósito.</span><span class="sxs-lookup"><span data-stu-id="0437c-119">An optional configuration is to use separate certificates for each purpose.</span></span> <span data-ttu-id="0437c-120">Los certificados se pueden administrar con el shell de administración de Lync Server y los cmdlets de Windows PowerShell, o mediante el Asistente para certificados en el Asistente para la implementación de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0437c-120">Certificates can be managed by using the Lync Server Management Shell and Windows PowerShell cmdlets, or by using the Certificate Wizard in the Lync Server Deployment Wizard.</span></span>



</div>

<div>

## <a name="to-update-certificates-with-new-subject-alternative-names-using-the-lync-server-management-shell"></a><span data-ttu-id="0437c-121">Para actualizar certificados con nombres alternativos de sujeto nuevos mediante el shell de administración de Lync Server</span><span class="sxs-lookup"><span data-stu-id="0437c-121">To update certificates with new subject alternative names using the Lync Server Management Shell</span></span>

1.  <span data-ttu-id="0437c-122">Inicie sesión en el equipo usando una cuenta con derechos y permisos de administrador</span><span class="sxs-lookup"><span data-stu-id="0437c-122">Log on to the computer using an account that has local administrator rights and permissions.</span></span>

2.  <span data-ttu-id="0437c-123">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="0437c-123">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="0437c-p104">Averigüe qué certificados se han asignado al servidor y para qué tipo de uso. Esta información es necesaria en el paso siguiente para asignar el certificado actualizado. En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="0437c-p104">Find out what certificates have been assigned to the server and for which type of use. You need this information in the next step to assign the updated certificate. At the command line, type:</span></span>
    
        Get-CsCertificate

4.  <span data-ttu-id="0437c-p105">Compruebe en los resultados del paso anterior si se ha asignado un solo certificado para varios usos o un certificado distinto para cada uso. Mire el parámetro Uso para averiguar cómo se usa un certificado. Compara el parámetro Huella digital de los certificados mostrados para ver si el mismo certificado tiene varios usos.</span><span class="sxs-lookup"><span data-stu-id="0437c-p105">Look in the output from the previous step to see whether a single certificate is assigned for multiple uses or whether a different certificate is assigned for each use. Look in the Use parameter to find out how a certificate is used. Compare the Thumbprint parameter for the displayed certificates to see if the same certificate has multiple uses.</span></span>

5.  <span data-ttu-id="0437c-p106">Actualice el certificado. En la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="0437c-p106">Update the certificate. At the command line, type:</span></span>
    
        Set-CsCertificate -Type <type of certificate as displayed in the Use parameter> -Thumbprint <unique identifier>
    
    <span data-ttu-id="0437c-132">Por ejemplo, si el cmdlet **Get-CsCertificate** ha mostrado un certificado con uso de Predeterminado, otro con uso de WebServicesInternal y otro con uso de WebServicesExternal, y todos tienen el mismo valor de huella digital, en la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="0437c-132">For example, if the **Get-CsCertificate** cmdlet displayed a certificate with Use of Default, another with a Use of WebServicesInternal, and another with a Use of WebServicesExternal, and they all had the same Thumbprint value, at the command line, type:</span></span>
    
        Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
    
    <span data-ttu-id="0437c-133">**Importante:**</span><span class="sxs-lookup"><span data-stu-id="0437c-133">**Important:**</span></span>
    
    <span data-ttu-id="0437c-134">Si se asigna un certificado distinto para cada uso (el valor de huella digital es diferente para cada certificado), es importante que no ejecute el cmdlet **Set-CsCertificate** con varios tipos.</span><span class="sxs-lookup"><span data-stu-id="0437c-134">If a separate certificate is assigned for each use (the Thumbprint value is different for each certificate), it is important that you do not run the **Set-CsCertificate** cmdlet with multiple types.</span></span> <span data-ttu-id="0437c-135">En este caso, ejecute el cmdlet **Set-CsCertificate** por separado para cada uso.</span><span class="sxs-lookup"><span data-stu-id="0437c-135">In this case, run the **Set-CsCertificate** cmdlet separately for each use.</span></span> <span data-ttu-id="0437c-136">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0437c-136">For example:</span></span>
    
        Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
        Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>

6.  <span data-ttu-id="0437c-p108">Para ver el certificado, haga clic en **Inicio**, **Ejecutar…**. Escriba MMC para abrir Microsoft Management Console.</span><span class="sxs-lookup"><span data-stu-id="0437c-p108">To view the certificate, click **Start**, click **Run…**. Type MMC to open the Microsoft Management Console.</span></span>

7.  <span data-ttu-id="0437c-p109">En el menú de MMC, seleccione **Archivo**, **Agregar o quitar complemento…**, Certificados. Haga clic en **Agregar**. Cuando se le pida, seleccione **Cuenta de equipo** y luego haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="0437c-p109">From the MMC menu, select **File**, select **Add/Remove snap-in…**, select Certificates. Click **Add**. When prompted, select **Computer account**, then click **Next**.</span></span>

8.  <span data-ttu-id="0437c-142">Si el certificado está ubicado en este equipo, seleccione **equipo local**.</span><span class="sxs-lookup"><span data-stu-id="0437c-142">If the certificate is located on this computer, select **Local computer**.</span></span> <span data-ttu-id="0437c-143">Si el certificado se encuentra en otro PC, seleccione **Otro equipo**, escriba el nombre de dominio completo del PC o haga clic en **Examinar** En **Escriba el nombre de objeto a seleccionar**, escriba el nombre del PC.</span><span class="sxs-lookup"><span data-stu-id="0437c-143">If the certificate is located on another computer, select **Another computer**, type in the fully qualified domain name of the computer or click **Browse** In **Enter the object name to select**, type the name of the computer.</span></span> <span data-ttu-id="0437c-144">Haga clic en **Comprobar nombres**.</span><span class="sxs-lookup"><span data-stu-id="0437c-144">Click **Check Names**.</span></span> <span data-ttu-id="0437c-145">Cuando se resuelva el nombre del equipo, se subrayará.</span><span class="sxs-lookup"><span data-stu-id="0437c-145">When the name of the computer is resolved, it will be underlined.</span></span> <span data-ttu-id="0437c-146">Haga clic en **Aceptar** y luego en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="0437c-146">Click **OK**, then click **Finish**.</span></span> <span data-ttu-id="0437c-147">Haga clic en **Aceptar** para confirmar la selección y cerrar el cuadro de diálogo **Agregar o quitar complementos**.</span><span class="sxs-lookup"><span data-stu-id="0437c-147">Click **OK** to commit the selection and close the **Add or Remove Snap-ins** dialog.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="0437c-148">Si el certificado no aparece en la consola, asegúrese de que no ha seleccionado usuario o servicio.</span><span class="sxs-lookup"><span data-stu-id="0437c-148">If the certificate does not show up in the console, ensure that you have not selected User or Service.</span></span> <span data-ttu-id="0437c-149">Debe seleccionar equipo o no podrá ubicar el certificado probper.</span><span class="sxs-lookup"><span data-stu-id="0437c-149">You must select Computer, or you will not be able to locate the probper certificate.</span></span>

    
    </div>

9.  <span data-ttu-id="0437c-p112">Para ver las propiedades del certificado, expanda **Certificados**, **Personal** y seleccione **Certificados**. Seleccione el certificado que desea ver, haga clic en el certificado y seleccione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="0437c-p112">To view the properties of the certificate, expand **Certificates**, expand **Personal**, and select **Certificates**. Select the certificate to view, right-click on the certificate and select **Open**.</span></span>

10. <span data-ttu-id="0437c-p113">En la vista **Certificado**, seleccione **Detalles**. Desde aquí, puede elegir el nombre de sujeto del certificado seleccionando **Sujeto** y se muestran el nombre del sujeto asignado y propiedades asociadas.</span><span class="sxs-lookup"><span data-stu-id="0437c-p113">In the **Certificate** view, select **Details**. From here, you can select the certificate subject name by selecting **Subject** and the assigned subject name and associated properties are displayed.</span></span>

11. <span data-ttu-id="0437c-154">Para ver los nombres alternativos del sujeto asignados, seleccione **Nombre alternativo del sujeto**.</span><span class="sxs-lookup"><span data-stu-id="0437c-154">To view the assigned subject alternative names, select **Subject Alternative Name**.</span></span> <span data-ttu-id="0437c-155">Aparecen todos los nombres alternativos del sujeto asignado.</span><span class="sxs-lookup"><span data-stu-id="0437c-155">All assigned subject alternative names are displayed.</span></span> <span data-ttu-id="0437c-156">De forma predeterminada, los nombres alternativos del sujeto que se encuentran en la propiedad son de tipo **Nombre de DNS**.</span><span class="sxs-lookup"><span data-stu-id="0437c-156">The subject alternative names that are found in the property are of type **DNS Name** by default.</span></span> <span data-ttu-id="0437c-157">Debe ver los siguientes miembros (todos los cuales deben ser nombres de dominio completos representados en los registros del host de DNS (A o, si IPv6 AAAA):</span><span class="sxs-lookup"><span data-stu-id="0437c-157">You should see the following members (all of which should be fully qualified domain names as represented in DNS host (A or, if IPv6 AAAA) records:</span></span>
    
      - <span data-ttu-id="0437c-158">Nombre del grupo para este grupo o el nombre del servidor si no es un grupo</span><span class="sxs-lookup"><span data-stu-id="0437c-158">Pool name for this pool, or the single server name if this is not a pool</span></span>
    
      - <span data-ttu-id="0437c-159">Nombre del servidor al que está asignado el certificado</span><span class="sxs-lookup"><span data-stu-id="0437c-159">Server name that the certificate is assigned to</span></span>
    
      - <span data-ttu-id="0437c-160">Registros de direcciones URL simples, normalmente reunión y marcación</span><span class="sxs-lookup"><span data-stu-id="0437c-160">Simple URL records, typically meet and dialin</span></span>
    
      - <span data-ttu-id="0437c-161">Nombres externos de servicios Web internos y servicios web (por ejemplo, webpool01.contoso.net, webpool01.contoso.com), en función de las elecciones realizadas en el generador de topologías y las selecciones de servicios web invalidadas.</span><span class="sxs-lookup"><span data-stu-id="0437c-161">Web services internal and Web services external names (for example, webpool01.contoso.net, webpool01.contoso.com), based on choices made in Topology Builder and over-ridden web services selections.</span></span>
    
      - <span data-ttu-id="0437c-162">Si ya está asignado, el lyncdiscover.\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="0437c-162">If already assigned, the lyncdiscover.\<sipdomain\></span></span> <span data-ttu-id="0437c-163">y lyncdiscoverinternal.\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="0437c-163">and lyncdiscoverinternal.\<sipdomain\></span></span> <span data-ttu-id="0437c-164">registro.</span><span class="sxs-lookup"><span data-stu-id="0437c-164">records.</span></span>
    
    <span data-ttu-id="0437c-165">El último elemento es lo que más le interesa; si hay una entrada SAN de lyncdiscover y lyncdiscoverinternal.</span><span class="sxs-lookup"><span data-stu-id="0437c-165">The last item is what you are most interested in – if there is a lyncdiscover and lyncdiscoverinternal SAN entry.</span></span>
    
    <span data-ttu-id="0437c-166">Una vez que tenga esta información, puede cerrar la vista de certificado y MMC.</span><span class="sxs-lookup"><span data-stu-id="0437c-166">Once you have this information, you can close the certificate view and the MMC.</span></span>

12. <span data-ttu-id="0437c-167">Si es un servicio de detección automática, lo que significa lyncdiscover. \> nombre \> de dominio y lyncdiscoverinternal.\<domain name\></span><span class="sxs-lookup"><span data-stu-id="0437c-167">If an Autodiscover Service, meaning the lyncdiscover.\>domain name\> and lyncdiscoverinternal.\<domain name\></span></span> <span data-ttu-id="0437c-168">(en función de si se trata de un certificado externo o interno) no se encuentra el nombre alternativo del firmante y está usando un único certificado predeterminado para los tipos predeterminados, WebServicesInternal y WebServiceExternal, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0437c-168">(based on if this is an external or internal certificate) subject alternative name is missing, and you are using a single Default certificate for the Default, WebServicesInternal and WebServiceExternal types, do the following:</span></span>
    
      - <span data-ttu-id="0437c-169">En el símbolo del sistema de la línea de comandos del shell de administración de Lync Server, escriba:</span><span class="sxs-lookup"><span data-stu-id="0437c-169">At the Lync Server Management Shell command line prompt, type:</span></span>
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="0437c-170">Si tiene muchos dominios SIP, no puede usar el nuevo parámetro AllSipDomain.</span><span class="sxs-lookup"><span data-stu-id="0437c-170">If you have many SIP domains, you cannot use the new AllSipDomain parameter.</span></span> <span data-ttu-id="0437c-171">En su lugar, debe utilizar el parámetro DomainName.</span><span class="sxs-lookup"><span data-stu-id="0437c-171">Instead, you must use DomainName parameter.</span></span> <span data-ttu-id="0437c-172">Cuando use el parámetro DomainName, debe definir el FQDN para los registros de lyncdiscoverinternal y lyncdiscover.</span><span class="sxs-lookup"><span data-stu-id="0437c-172">When you use the DomainName parameter, you must define the FQDN for the lyncdiscoverinternal and lyncdiscover records.</span></span> <span data-ttu-id="0437c-173">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0437c-173">For example:</span></span>
        
            Request-CsCertificate -New -Type Default,WebServicesInternal,WebServicesExternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - <span data-ttu-id="0437c-174">Para asignar el certificado, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0437c-174">To assign the certificate, type the following:</span></span>
        
            Set-CsCertificate -Type Default,WebServicesInternal,WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        <span data-ttu-id="0437c-175">Donde “Huella digital” es la huella digital mostrada para el certificado que acaba de emitir.</span><span class="sxs-lookup"><span data-stu-id="0437c-175">Where “Thumbprint” is the thumbprint displayed for the newly issued certificate.</span></span>

13. <span data-ttu-id="0437c-176">Cuando faltan los nombres alternativos del sujeto de Detección automática internos al usar certificados separados en Default, WebServicesInternal y WebServicesExternal, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0437c-176">For a missing internal Autodiscover subject alternative names when using separate certificates for Default, WebServicesInternal, and WebServicesExternal, do the following:</span></span>
    
      - <span data-ttu-id="0437c-177">En el símbolo del sistema de la línea de comandos del shell de administración de Lync Server, escriba:</span><span class="sxs-lookup"><span data-stu-id="0437c-177">At the Lync Server Management Shell command line prompt, type:</span></span>
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="0437c-p118">Si tiene muchos dominios SIP, no puede usar el nuevo parámetro AllSipDomain. En su lugar, debe usar el parámetro DomainName. Al usar el parámetro DomainName, debe usar un prefijo adecuado para el FQDN del dominio SIP. Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0437c-p118">If you have many SIP domains, you cannot use the new AllSipDomain parameter. Instead, you must use DomainName parameter. When you use the DomainName parameter, you must use an appropriate prefix for the SIP domain FQDN. For example:</span></span>
        
            Request-CsCertificate -New -Type WebServicesInternal -Ca dc\myca -DomainName "LyncdiscoverInternal.contoso.com, LyncdiscoverInternal.contoso.net" -verbose
    
      - <span data-ttu-id="0437c-182">Para un nombre alternativo de sujeto del servicio Detección automática externa, en la línea de comandos, escriba:</span><span class="sxs-lookup"><span data-stu-id="0437c-182">For a missing external Autodiscover subject alternative name, at the command line, type:</span></span>
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -AllSipDomain -verbose
        
        <span data-ttu-id="0437c-p119">Si tiene muchos dominios SIP, no puede usar el nuevo parámetro AllSipDomain. En su lugar, debe usar el parámetro DomainName. Al usar el parámetro DomainName, debe usar un prefijo adecuado para el FQDN del dominio SIP. Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0437c-p119">If you have many SIP domains, you cannot use the new AllSipDomain parameter. Instead, you must use DomainName parameter. When you use the DomainName parameter, you must use an appropriate prefix for the SIP domain FQDN. For example:</span></span>
        
            Request-CsCertificate -New -Type WebServicesExternal -Ca dc\myca -DomainName "Lyncdiscover.contoso.com, Lyncdiscover.contoso.net" -verbose
    
      - <span data-ttu-id="0437c-187">Para asignar tipos de certificados individuales, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0437c-187">To assign the individual certificate types, type the following:</span></span>
        
            Set-CsCertificate -Type Default -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesInternal -Thumbprint <Certificate Thumbprint>
            Set-CsCertificate -Type WebServicesExternal -Thumbprint <Certificate Thumbprint>
        
        <span data-ttu-id="0437c-188">Donde “Huella digital” es la huella digital mostrada para el certificado individual que acaba de emitir.</span><span class="sxs-lookup"><span data-stu-id="0437c-188">Where “Thumbprint” is the thumbprint displayed for the newly issued individual certificates.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

