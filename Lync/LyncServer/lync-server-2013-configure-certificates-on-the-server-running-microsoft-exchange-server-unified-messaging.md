---
title: 'Lync Server 2013: configurar certificados en el servidor que ejecuta la mensajería unificada de Microsoft Exchange Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure certificates on the server running Microsoft Exchange Server Unified Messaging
ms:assetid: 74c883b4-cef6-41a9-b2eb-7212be32fea4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398564(v=OCS.15)
ms:contentKeyID: 48184521
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfc9ed0f51b3f534d5967c7195cc39736a4ecae9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842412"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging"></a><span data-ttu-id="9277c-102">Configurar certificados en el servidor que ejecuta la mensajería unificada de Microsoft Exchange Server</span><span class="sxs-lookup"><span data-stu-id="9277c-102">Configure certificates on the server running Microsoft Exchange Server Unified Messaging</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9277c-103">_**Última modificación del tema:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="9277c-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="9277c-104">Si ha implementado la mensajería unificada de Exchange (UM), como se describe en [planeamiento de la integración de mensajería unificada de Exchange en Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) en la documentación de planeación y desea proporcionar características de mensajería unificada de Exchange a los usuarios de voz de empresa de su organización, puede usar los procedimientos siguientes para configurar el certificado en el servidor que ejecuta la mensajería unificada de Exchange.</span><span class="sxs-lookup"><span data-stu-id="9277c-104">If you have deployed Exchange Unified Messaging (UM), as described in [Planning for Exchange Unified Messaging integration in Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) in the Planning documentation, and you want to provide Exchange UM features to Enterprise Voice users in your organization, you can use the following procedures to configure the certificate on the server running Exchange UM.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="9277c-105">En el caso de los certificados internos, tanto los servidores que ejecutan Lync Server 2013 como los servidores que ejecutan Microsoft Exchange deben tener certificados de entidad raíz de confianza que sean de confianza mutuamente.</span><span class="sxs-lookup"><span data-stu-id="9277c-105">For internal certificates, both the servers running Lync Server 2013 and the servers running Microsoft Exchange must have trusted root authority certificates that are mutually trusted.</span></span> <span data-ttu-id="9277c-106">La entidad de certificación (CA) puede ser la misma o una entidad de certificación diferente, siempre que los servidores tengan el certificado raíz de la entidad de certificación registrado en su almacén de certificados de entidad de certificación raíz de confianza.</span><span class="sxs-lookup"><span data-stu-id="9277c-106">The certification authority (CA) can either be the same, or a different certification authority, as long as the servers have the certification authority’s root certificate registered in their trusted root authority certificate store.</span></span>



</div>

<span data-ttu-id="9277c-107">El servidor de Exchange debe estar configurado con un certificado de servidor para poder conectarse a Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="9277c-107">The Exchange Server must be configured with a server certificate in order to connect to Lync Server 2013:</span></span>

1.  <span data-ttu-id="9277c-108">Descargue el certificado de CA para el servidor de Exchange.</span><span class="sxs-lookup"><span data-stu-id="9277c-108">Download the CA certificate for the Exchange Server.</span></span>

2.  <span data-ttu-id="9277c-109">Instale el certificado de CA para el servidor de Exchange.</span><span class="sxs-lookup"><span data-stu-id="9277c-109">Install the CA certificate for the Exchange Server.</span></span>

3.  <span data-ttu-id="9277c-110">Compruebe que la entidad emisora de certificados se encuentra en la lista de entidades emisoras raíz de confianza del servidor de Exchange.</span><span class="sxs-lookup"><span data-stu-id="9277c-110">Verify that the CA is in the list of trusted root CAs of the Exchange Server.</span></span>

4.  <span data-ttu-id="9277c-111">Cree una solicitud de certificado para el servidor de Exchange e instale el certificado.</span><span class="sxs-lookup"><span data-stu-id="9277c-111">Create a certificate request for the Exchange Server and install the certificate.</span></span>

5.  <span data-ttu-id="9277c-112">Asigne el certificado para el servidor de Exchange.</span><span class="sxs-lookup"><span data-stu-id="9277c-112">Assign the certificate for the Exchange Server.</span></span>

<div>

## <a name="to-download-the-ca-certificate"></a><span data-ttu-id="9277c-113">Para descargar el certificado de la entidad emisora</span><span class="sxs-lookup"><span data-stu-id="9277c-113">To download the CA certificate</span></span>

1.  <span data-ttu-id="9277c-114">En el servidor que ejecuta la mensajería unificada de Exchange, haga clic en **Inicio**, haga clic en **ejecutar**, escriba **http://\<nombre del servidor\>CA**emisora/certsrv y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9277c-114">On the server running Exchange UM, click **Start**, click **Run**, type **http://\<name of your Issuing CA Server\>/certsrv**, and then click **OK**.</span></span>

2.  <span data-ttu-id="9277c-115">En **seleccionar una tarea**, haga clic en **descargar un certificado de CA, una cadena de certificados o una CRL**.</span><span class="sxs-lookup"><span data-stu-id="9277c-115">Under **Select a task**, click **Download a CA certificate, certificate chain, or CRL**.</span></span>

3.  <span data-ttu-id="9277c-116">En **descargar un certificado de CA, una cadena de certificados o una CRL**, seleccione el **método de codificación para base 64**y, después, haga clic en **Descargar certificado de CA**.</span><span class="sxs-lookup"><span data-stu-id="9277c-116">Under **Download a CA Certificate, Certificate Chain, or CRL**, select **Encoding Method to Base 64**, and then click **Download CA certificate**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9277c-117">También puede especificar la codificación de las reglas de codificación distintivas (DER) en este paso.</span><span class="sxs-lookup"><span data-stu-id="9277c-117">You can also specify Distinguished Encoding Rules (DER) encoding at this step.</span></span> <span data-ttu-id="9277c-118">Si selecciona la codificación DER, el tipo de archivo en el paso siguiente de este procedimiento y en el paso 10 de <STRONG>para instalar el certificado de la entidad emisora</STRONG> es. p7b en lugar de. cer.</span><span class="sxs-lookup"><span data-stu-id="9277c-118">If you select DER encoding, the file type in the next step of this procedure and in step 10 of <STRONG>To Install the CA certificate</STRONG> is .p7b rather than .cer.</span></span>

    
    </div>

4.  <span data-ttu-id="9277c-119">En el cuadro de diálogo **descarga de archivos** , haga clic en **Guardar**y, a continuación, guarde el archivo en el disco duro del servidor.</span><span class="sxs-lookup"><span data-stu-id="9277c-119">In the **File Download** dialog box, click **Save**, and then save the file to the hard disk on the server.</span></span> <span data-ttu-id="9277c-120">(El archivo tendrá una extensión. cer o. p7b, en función de la codificación que haya seleccionado en el paso anterior).</span><span class="sxs-lookup"><span data-stu-id="9277c-120">(The file will have either a .cer or a .p7b file extension, depending on the encoding that you selected in the previous step.)</span></span>

</div>

<div>

## <a name="to-install-the-ca-certificate"></a><span data-ttu-id="9277c-121">Para instalar el certificado de CA</span><span class="sxs-lookup"><span data-stu-id="9277c-121">To install the CA certificate</span></span>

1.  <span data-ttu-id="9277c-122">En el servidor que ejecuta la mensajería unificada de Exchange, abra Microsoft Management Console (MMC) haciendo clic en **Inicio**, haga clic en **Ejecutar**, escriba **MMC** en el cuadro **abrir** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9277c-122">On the server running Exchange UM, open Microsoft Management Console (MMC) by clicking **Start**, clicking **Run**, typing **mmc** in the **Open** box, and then clicking **OK**.</span></span>

2.  <span data-ttu-id="9277c-123">En el menú **archivo** , haga clic en **Agregar o quitar complemento**y, a continuación, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="9277c-123">On the **File** menu, click **Add/Remove Snap-in**, and then click **Add**.</span></span>

3.  <span data-ttu-id="9277c-124">En el cuadro **Agregar complementos independientes** , haga clic en **certificados**y, a continuación, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="9277c-124">In the **Add Standalone Snap-ins** box, click **Certificates**, and then click **Add**.</span></span>

4.  <span data-ttu-id="9277c-125">En el cuadro de diálogo **Complemento de certificados**, haga clic en **Cuenta de equipo** y luego haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="9277c-125">In the **Certificate snap-in** dialog box, click **Computer account**, and then click **Next**.</span></span>

5.  <span data-ttu-id="9277c-126">En el cuadro de diálogo **seleccionar equipo** , compruebe que la casilla **equipo local: (el equipo en el que se está ejecutando esta consola)** está activada y, a continuación, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="9277c-126">In the **Select Computer** dialog box, verify that the **Local computer: (the computer this console is running on)** check box is selected, and then click **Finish**.</span></span>

6.  <span data-ttu-id="9277c-127">Haga clic en **cerrar**y, a continuación, en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9277c-127">Click **Close**, and then click **OK**.</span></span>

7.  <span data-ttu-id="9277c-128">En el árbol de consola, expanda **certificados (equipo local)**, expanda **entidades emisoras raíz de confianza**y, a continuación, haga clic en **certificados**.</span><span class="sxs-lookup"><span data-stu-id="9277c-128">In the console tree, expand **Certificates (Local Computer)**, expand **Trusted Root Certification Authorities**, and then click **Certificates**.</span></span>

8.  <span data-ttu-id="9277c-129">Haga clic con el botón secundario en **certificados**, seleccione **todas las tareas**y haga clic en **importar**.</span><span class="sxs-lookup"><span data-stu-id="9277c-129">Right-click **Certificates**, click **All Tasks**, and click **Import**.</span></span>

9.  <span data-ttu-id="9277c-130">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="9277c-130">Click **Next**.</span></span>

10. <span data-ttu-id="9277c-131">Haga clic en **examinar** para buscar el archivo y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="9277c-131">Click **Browse** to locate the file, and then click **Next**.</span></span> <span data-ttu-id="9277c-132">(El archivo tendrá una extensión. cer o. p7b, en función de la codificación que haya seleccionado en el paso 3 de **para descargar el certificado de la entidad emisora**.</span><span class="sxs-lookup"><span data-stu-id="9277c-132">(The file will have either a .cer or a .p7b file extension, depending on the encoding that you selected in step 3 of **To download the CA certificate**.</span></span>

11. <span data-ttu-id="9277c-133">Haga clic en **colocar todos los certificados en el siguiente almacén**.</span><span class="sxs-lookup"><span data-stu-id="9277c-133">Click **Place All Certificates in the following store**.</span></span>

12. <span data-ttu-id="9277c-134">Haga clic en **examinar**y seleccione **entidades emisoras de certificados raíz de confianza**.</span><span class="sxs-lookup"><span data-stu-id="9277c-134">Click **Browse**, and then select **Trusted Root Certification Authorities**.</span></span>

13. <span data-ttu-id="9277c-135">Haga clic en **siguiente** para comprobar la configuración y, a continuación, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="9277c-135">Click **Next** to verify the settings, and then click **Finish**.</span></span>

</div>

<div>

## <a name="to-verify-that-the-ca-is-in-the-list-of-trusted-root-cas"></a><span data-ttu-id="9277c-136">Para comprobar que la entidad emisora está en la lista de entidades emisoras raíz de confianza</span><span class="sxs-lookup"><span data-stu-id="9277c-136">To verify that the CA is in the list of trusted root CAs</span></span>

1.  <span data-ttu-id="9277c-137">En el servidor que ejecuta la mensajería unificada de Exchange, en MMC expanda **certificados (equipo local)**, expanda **entidades emisoras raíz de confianza**y, a continuación, haga clic en **certificados**.</span><span class="sxs-lookup"><span data-stu-id="9277c-137">On the server running Exchange UM, in MMC expand **Certificates (Local Computer)**, expand **Trusted Root Certification Authorities**, and then click **Certificates**.</span></span>

2.  <span data-ttu-id="9277c-138">En el panel de detalles, compruebe que la entidad emisora está en la lista de entidades emisoras de confianza.</span><span class="sxs-lookup"><span data-stu-id="9277c-138">In the details pane, verify that your CA is on the list of trusted CAs.</span></span>

</div>

<div>

## <a name="to-configure-exchange-server-2013-um-with-lync-server"></a><span data-ttu-id="9277c-139">Para configurar la mensajería unificada de Exchange Server 2013 con Lync Server</span><span class="sxs-lookup"><span data-stu-id="9277c-139">To configure Exchange Server 2013 UM with Lync Server</span></span>

1.  <span data-ttu-id="9277c-140">Para obtener más información, consulte "integrar la mensajería unificada de Exchange 2013 con Lync Server" [http://go.microsoft.com/fwlink/p/?LinkId=265372](http://go.microsoft.com/fwlink/p/?linkid=265372)en la documentación de Exchange Server en.</span><span class="sxs-lookup"><span data-stu-id="9277c-140">For details, see "Integrate Exchange 2013 UM with Lync Server" in the Exchange Server documentation at [http://go.microsoft.com/fwlink/p/?LinkId=265372](http://go.microsoft.com/fwlink/p/?linkid=265372).</span></span>

</div>

<div>

## <a name="to-create-a-certificate-request-and-install-the-certificate-on-exchange-server-2007-sp1"></a><span data-ttu-id="9277c-141">Para crear una solicitud de certificado e instalar el certificado en Exchange Server 2007 (SP1)</span><span class="sxs-lookup"><span data-stu-id="9277c-141">To create a certificate request and install the certificate on Exchange Server 2007 (SP1)</span></span>

1.  <span data-ttu-id="9277c-142">En el servidor que ejecuta la mensajería unificada de Exchange, haga clic en **Inicio**, haga clic en **Ejecutar**,**\>** escriba **http://\<** nombre del servidor CA emisora/certsrv y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9277c-142">On the server running Exchange UM, click **Start**, click **Run**, type **http://\<** name of your Issuing CA Server**\>/certsrv**, and then click **OK**.</span></span>

2.  <span data-ttu-id="9277c-143">En **seleccionar una tarea**, haga clic en **solicitar un certificado**.</span><span class="sxs-lookup"><span data-stu-id="9277c-143">Under **Select a task**, click **Request a Certificate**.</span></span>

3.  <span data-ttu-id="9277c-144">En **solicitar un certificado**, haga clic en **solicitud de certificado avanzada**.</span><span class="sxs-lookup"><span data-stu-id="9277c-144">Under **Request a Certificate**, click **Advanced certificate request**.</span></span>

4.  <span data-ttu-id="9277c-145">En **solicitud de certificado avanzada**, haga clic en **crear y enviar una solicitud a esta CA**.</span><span class="sxs-lookup"><span data-stu-id="9277c-145">Under **Advanced Certificate Request**, click **Create and submit a request to this CA**.</span></span>

5.  <span data-ttu-id="9277c-146">En **solicitud de certificado avanzada**, seleccione **servidor Web** u otra plantilla de certificado de servidor configurada para la autenticación de servidor.</span><span class="sxs-lookup"><span data-stu-id="9277c-146">Under **Advanced Certificate Request**, select **Web server** or another server certificate template configured for server authentication.</span></span>

6.  <span data-ttu-id="9277c-147">En **información de identificación para plantillas sin conexión**, en el cuadro **nombre** , escriba el nombre de dominio completo (FQDN) del servidor de Exchange.</span><span class="sxs-lookup"><span data-stu-id="9277c-147">Under **Identifying Information for Offline Template**, in the **Name** box, type the fully qualified domain name (FQDN) of the Exchange Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9277c-148">Debe especificar el nombre de dominio completo del servidor de Exchange para que las comunicaciones funcionen.</span><span class="sxs-lookup"><span data-stu-id="9277c-148">You must enter the FQDN of the Exchange Server for communications to work.</span></span>

    
    </div>

7.  <span data-ttu-id="9277c-149">En **Opciones de clave**, haga clic en la casilla **almacenar el certificado en el almacén de certificados del equipo local** .</span><span class="sxs-lookup"><span data-stu-id="9277c-149">Under **Key Options**, click the **Store certificate in the local computer certificate store** check box.</span></span>

8.  <span data-ttu-id="9277c-150">Haga clic en el botón **Enviar** en la parte inferior de la Página Web.</span><span class="sxs-lookup"><span data-stu-id="9277c-150">Click the **Submit** button in the bottom of the webpage.</span></span>

9.  <span data-ttu-id="9277c-151">En el cuadro de diálogo que se abre pidiendo confirmación, haga clic en **sí**.</span><span class="sxs-lookup"><span data-stu-id="9277c-151">In the dialog box that opens asking for confirmation, click **Yes**.</span></span>

10. <span data-ttu-id="9277c-152">En la página certificado emitido, en **certificado emitido**, haga clic en **instalar este certificado**.</span><span class="sxs-lookup"><span data-stu-id="9277c-152">On the Certificate Issued page, under **Certificate Issued**, click **Install this certificate**.</span></span>

11. <span data-ttu-id="9277c-153">En el cuadro de diálogo que se abre pidiendo confirmación, haga clic en **sí**.</span><span class="sxs-lookup"><span data-stu-id="9277c-153">In the dialog box that opens asking for confirmation, click **Yes**.</span></span>

12. <span data-ttu-id="9277c-154">Compruebe que aparece el mensaje "su nuevo certificado se ha instalado correctamente".</span><span class="sxs-lookup"><span data-stu-id="9277c-154">Verify that the message "Your new certificate has been successfully installed" appears.</span></span>

</div>

<div>

## <a name="to-create-a-certificate-on-exchange-server-2010"></a><span data-ttu-id="9277c-155">Para crear un certificado en Exchange Server 2010</span><span class="sxs-lookup"><span data-stu-id="9277c-155">To create a certificate on Exchange Server 2010</span></span>

1.  <span data-ttu-id="9277c-156">Inicie sesión en el servidor que ejecuta la mensajería unificada de Exchange con los derechos de usuario apropiados.</span><span class="sxs-lookup"><span data-stu-id="9277c-156">Log on to the server running Exchange UM with appropriate user rights.</span></span> <span data-ttu-id="9277c-157">Para obtener más información, vea "permisos de acceso [http://go.microsoft.com/fwlink/p/?linkId=195499](http://go.microsoft.com/fwlink/p/?linkid=195499)de cliente" en.</span><span class="sxs-lookup"><span data-stu-id="9277c-157">For details, see "Client Access Permissions" at [http://go.microsoft.com/fwlink/p/?linkId=195499](http://go.microsoft.com/fwlink/p/?linkid=195499).</span></span>

2.  <span data-ttu-id="9277c-158">Para crear el certificado, consulte los procedimientos siguientes:</span><span class="sxs-lookup"><span data-stu-id="9277c-158">Refer to the following procedures to create the certificate:</span></span>
    
    1.  <span data-ttu-id="9277c-159">"Crear un nuevo certificado de Exchange" en[http://go.microsoft.com/fwlink/p/?linkId=195494](http://go.microsoft.com/fwlink/p/?linkid=195494)</span><span class="sxs-lookup"><span data-stu-id="9277c-159">"Create a New Exchange Certificate" at [http://go.microsoft.com/fwlink/p/?linkId=195494](http://go.microsoft.com/fwlink/p/?linkid=195494)</span></span>
    
    2.  <span data-ttu-id="9277c-160">"Importar un certificado de Exchange" en[http://go.microsoft.com/fwlink/p/?linkId=195496](http://go.microsoft.com/fwlink/p/?linkid=195496)</span><span class="sxs-lookup"><span data-stu-id="9277c-160">"Import an Exchange Certificate" at [http://go.microsoft.com/fwlink/p/?linkId=195496](http://go.microsoft.com/fwlink/p/?linkid=195496)</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9277c-161">Para el <STRONG>nombre del sujeto</STRONG>del certificado, debe especificar el FQDN del servidor de Exchange para que funcionen las comunicaciones.</span><span class="sxs-lookup"><span data-stu-id="9277c-161">For the certificate <STRONG>Subject Name</STRONG>, you must enter the FQDN of the Exchange Server for communications to work.</span></span>

    
    </div>

</div>

<div>

## <a name="to-assign-the-certificate-on-exchange-server-2007-sp1"></a><span data-ttu-id="9277c-162">Para asignar el certificado en Exchange Server 2007 (SP1)</span><span class="sxs-lookup"><span data-stu-id="9277c-162">To assign the certificate on Exchange Server 2007 (SP1)</span></span>

1.  <span data-ttu-id="9277c-163">En el servidor que ejecuta la mensajería unificada de Exchange, abra MMC.</span><span class="sxs-lookup"><span data-stu-id="9277c-163">On the server running Exchange UM, open MMC.</span></span>

2.  <span data-ttu-id="9277c-164">En el árbol de consola, expanda **personal** y, a continuación, haga clic en **certificados**.</span><span class="sxs-lookup"><span data-stu-id="9277c-164">In the console tree, expand **Personal** and then click **Certificates**.</span></span>

3.  <span data-ttu-id="9277c-165">En el panel de detalles, compruebe que aparece certificado personal.</span><span class="sxs-lookup"><span data-stu-id="9277c-165">In the details pane, verify that personal certificate is displayed.</span></span>

4.  <span data-ttu-id="9277c-166">Haga doble clic en el certificado para leer sus detalles y comprobar que es válido.</span><span class="sxs-lookup"><span data-stu-id="9277c-166">Double-click the certificate to read its details and verify that it is valid.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9277c-167">Puede demorar unos minutos antes de que el certificado se muestre como válido.</span><span class="sxs-lookup"><span data-stu-id="9277c-167">It may take a few minutes before the certificate displays as valid.</span></span>

    
    </div>

5.  <span data-ttu-id="9277c-168">Reinicie el servicio de mensajería unificada de Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="9277c-168">Restart the Microsoft Exchange Unified Messaging service.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9277c-169">El servidor que ejecuta la mensajería unificada de Exchange Server 2007 SP1 recupera automáticamente el certificado correcto.</span><span class="sxs-lookup"><span data-stu-id="9277c-169">The server running Exchange Server 2007 SP1 Unified Messaging automatically retrieves the correct certificate.</span></span>

    
    </div>

6.  <span data-ttu-id="9277c-170">Abra el visor de eventos y busque el identificador de evento 1112, que especifica qué certificado ha recuperado el servidor que ejecuta la mensajería unificada de Exchange Server 2007 SP1.</span><span class="sxs-lookup"><span data-stu-id="9277c-170">Open Event Viewer and look for Event ID 1112, which specifies what certificate the server running Exchange Server 2007 SP1 Unified Messaging has retrieved.</span></span>

</div>

<div>

## <a name="to-assign-the-certificate-on-exchange-server-2010"></a><span data-ttu-id="9277c-171">Para asignar el certificado en Exchange Server 2010</span><span class="sxs-lookup"><span data-stu-id="9277c-171">To assign the certificate on Exchange Server 2010</span></span>

1.  <span data-ttu-id="9277c-172">Inicie sesión en el servidor que ejecuta la mensajería unificada de Exchange con los derechos de usuario apropiados.</span><span class="sxs-lookup"><span data-stu-id="9277c-172">Log on to the server running Exchange UM with appropriate user rights.</span></span> <span data-ttu-id="9277c-173">Para obtener más información, vea "permisos de acceso [http://go.microsoft.com/fwlink/p/?linkId=195499](http://go.microsoft.com/fwlink/p/?linkid=195499)de cliente" en.</span><span class="sxs-lookup"><span data-stu-id="9277c-173">For details, see "Client Access Permissions" at [http://go.microsoft.com/fwlink/p/?linkId=195499](http://go.microsoft.com/fwlink/p/?linkid=195499).</span></span>

2.  <span data-ttu-id="9277c-174">Para obtener el procedimiento para asignar el certificado, consulte "asignar servicios a un certificado" [http://go.microsoft.com/fwlink/p/?linkId=195497](http://go.microsoft.com/fwlink/p/?linkid=195497)en.</span><span class="sxs-lookup"><span data-stu-id="9277c-174">For the procedure to assign the certificate, see "Assign Services to a Certificate" at [http://go.microsoft.com/fwlink/p/?linkId=195497](http://go.microsoft.com/fwlink/p/?linkid=195497).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

