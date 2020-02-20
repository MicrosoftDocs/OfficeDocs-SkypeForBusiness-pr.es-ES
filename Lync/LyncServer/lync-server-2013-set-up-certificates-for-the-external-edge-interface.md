---
title: 'Lync Server 2013: configurar certificados para la interfaz perimetral externa'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set up certificates for the external edge interface
ms:assetid: 5d78182c-88d8-4483-95ad-74b17f2d5fac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398409(v=OCS.15)
ms:contentKeyID: 48184287
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0aadbc9603fb62a2dacf78129aef3bf448da2f05
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143410"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="set-up-certificates-for-the-external-edge-interface-for-lync-server-2013"></a><span data-ttu-id="7a2e1-102">Configurar certificados para la interfaz perimetral externa para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7a2e1-102">Set up certificates for the external edge interface for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7a2e1-103">_**Última modificación del tema:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="7a2e1-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="7a2e1-104">Al ejecutar el Asistente para certificados, asegúrese de que ha iniciado sesión usando una cuenta que es miembro de un grupo con los permisos asignados adecuados para el tipo de plantilla de certificado que use.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-104">When you run the Certificate Wizard, ensure that you are logged in using an account that is a member of a group that has been assigned the appropriate permissions for the type of certificate template you will use.</span></span> <span data-ttu-id="7a2e1-105">De forma predeterminada, una solicitud de certificado de Lync Server usará la plantilla de certificado del servidor Web.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-105">By default, a Lync Server certificate request will use the Web Server certificate template.</span></span> <span data-ttu-id="7a2e1-106">Si usa una cuenta que es miembro del grupo RTCUniversalServerAdmins para solicitar un certificado usando esta plantilla, compruebe que el grupo tenga asignados los permisos Inscribir necesarios para usar la plantilla.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-106">If you use an account that is a member of the RTCUniversalServerAdmins group to request a certificate using this template, verify that the group has been assigned the Enroll permissions required to use that template.</span></span>



</div>

<span data-ttu-id="7a2e1-107">Cada servidor perimetral requiere un certificado público en la interfaz entre la red perimetral e Internet. Asimismo, el nombre alternativo de sujeto del certificado debe contener los nombres externos de los nombres de dominio completos (FQDN) del servicio perimetral de acceso y del servicio perimetral de conferencia web.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-107">Each Edge Server requires a public certificate on the interface between the perimeter network and the Internet, and the certificate’s subject alternative name must contain the external names of the Access Edge service and Web Conferencing Edge service fully qualified domain names (FQDNs).</span></span>

<span data-ttu-id="7a2e1-108">Para obtener más información sobre este y otros requisitos de certificado, consulte [requisitos de certificados para el acceso de usuarios externos en Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="7a2e1-108">For details about this and other certificate requirements, see [Certificate requirements for external user access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span></span>

<span data-ttu-id="7a2e1-109">Para obtener una lista de entidades de certificación (CA) públicas que proporcionan certificados que cumplen los requisitos específicos para los certificados de comunicaciones unificadas y que se han asociado con Microsoft para garantizar que funcionan con el Asistente para certificados de Lync Server 2013, consulte el artículo 929395 de Microsoft Knowledge base, "asociados de certificados de [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834)comunicaciones unificadas para Exchange Server y para Communications Server" en.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-109">For a list of public certification authorities (CAs) that provide certificates that comply with specific requirements for unified communications certificates and have partnered with Microsoft to ensure they work with the Lync Server 2013 Certificate Wizard, see Microsoft Knowledge Base article 929395, "Unified Communications Certificate Partners for Exchange Server and for Communications Server," at [https://go.microsoft.com/fwlink/p/?linkId=202834](https://go.microsoft.com/fwlink/p/?linkid=202834).</span></span>

<div>

## <a name="configuring-certificates-on-the-external-interfaces"></a><span data-ttu-id="7a2e1-110">Configurar los certificados en las interfaces externas</span><span class="sxs-lookup"><span data-stu-id="7a2e1-110">Configuring Certificates on the External Interfaces</span></span>

<span data-ttu-id="7a2e1-111">Para configurar un certificado en la interfaz perimetral externa de un sitio, use los procedimientos de esta sección para:</span><span class="sxs-lookup"><span data-stu-id="7a2e1-111">To set up a certificate on the external edge interface at a site, use the procedures in this section to do the following:</span></span>

  - <span data-ttu-id="7a2e1-112">Crear la solicitud de certificado para la interfaz externa del servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-112">Create the certificate request for the external interface of the Edge Server.</span></span>

  - <span data-ttu-id="7a2e1-113">Enviar la solicitud a la entidad de certificación pública.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-113">Submit the request to your public CA.</span></span>

  - <span data-ttu-id="7a2e1-114">Importar el certificado en la interfaz externa de cada servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-114">Import the certificate for the external interface of each Edge Server.</span></span>

  - <span data-ttu-id="7a2e1-115">Asignar el certificado a la interfaz externa de cada servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-115">Assign the certificate for the external interface of each Edge Server.</span></span>

  - <span data-ttu-id="7a2e1-p102">Si su implementación tiene varios servidores perimetrales, exporte los certificados junto con su clave privada y cópielos a los demás servidores perimetrales. A continuación, en cada servidor perimetral, impórtelo y asígnelo tal como se ha descrito anteriormente. Repita este procedimiento con todos los servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-p102">If your deployment includes multiple Edge Servers, export the certificate along with its private key, and then copy it to the other Edge Servers. Then, for each Edge Server, import it and assign it as previously described. Repeat this procedure for each Edge Server.</span></span>

<span data-ttu-id="7a2e1-p103">Puede solicitar certificados públicos directamente a una autoridad de certificación pública (CA) (como, por ejemplo, desde el sitio web de una CA pública). Los procedimientos de esta sección usan el Asistente para certificados para la mayoría de tareas de certificados. Si decide solicitar directamente un certificado a una CA pública, entonces no tendrá que modificar cada procedimiento según sea apropiado para solicitar, transportar e importar el certificado, así como para importar la cadena de certificados.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-p103">You can request public certificates directly from a public certification authority (CA) (such as from the website of a public CA). The procedures in this section use the Certificate Wizard for most certificate tasks. If you chose to request a certificate directly from a public CA, then you will need to modify each procedure as appropriate to request, transport, and import the certificate and also to import the certificate chain.</span></span>

<span data-ttu-id="7a2e1-p104">Cuando solicite un certificado a una entidad de certificación externa, las credenciales proporcionadas deben tener derechos para solicitar un certificado a dicha entidad. Cada entidad de certificación tiene una directiva de seguridad que define qué credenciales (es decir, qué nombres de usuario y grupo específicos) se permiten para solicitar, emitir, administrar o leer certificados.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-p104">When you request a certificate from an External CA, the credentials provided must have rights to request a certificate from that CA. Each CA has a security policy that defines which credentials (that is, specific user and group names) are allowed to request, issue, manage, or read certificates.</span></span>

<span data-ttu-id="7a2e1-124">Si decide usar la Microsoft Management Console (MMC) de los certificados para importar la cadena de certificados y los certificados, deberá importarlos al almacén de certificados del equipo.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-124">If you decide to use the Certificates Microsoft Management Console (MMC) to import the certificate chain and certificate, you must import them to the certificate store for the computer.</span></span> <span data-ttu-id="7a2e1-125">Si los importa al almacén de certificados de usuario o servicio, el certificado no estará disponible para su asignación en el Asistente para certificados de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-125">If you import them to the user or service certificate store, the certificate will not be available for assignment in the Lync Server 2013 Certificate Wizard.</span></span>

<div>

## <a name="to-create-the-certificate-request-for-the-external-interface-of-the-edge-server"></a><span data-ttu-id="7a2e1-126">Para crear la solicitud de certificado para la interfaz externa del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="7a2e1-126">To create the certificate request for the external interface of the Edge Server</span></span>

1.  <span data-ttu-id="7a2e1-127">En el servidor perimetral, en el Asistente para la implementación, junto al **Paso 3: Solicitar, instalar o asignar certificados**, haga clic en **Ejecutar de nuevo**.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-127">On the Edge Server, in the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7a2e1-128">Si su organización desea admitir la conectividad de mensajería instantánea pública con AOL, no puede usar al Asistente para la implementación de Lync Server para solicitar el certificado.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-128">If your organization wants to support public instant messaging (IM) connectivity with AOL, you cannot use the Lync Server Deployment Wizard to request the certificate.</span></span> <span data-ttu-id="7a2e1-129">En su lugar, se deben realizar los pasos descritos en "Para crear una solicitud de certificado para la interfaz externa del servidor perimetral para permitir la conectividad de mensajería instantánea pública con AOL" que encontrará más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-129">Instead, perform the steps in the “To create a certificate request for the external interface of the Edge Server to support public IM connectivity with AOL” procedure later in this topic.</span></span><BR><span data-ttu-id="7a2e1-130">Si tiene varios servidores perimetrales en una ubicación de un grupo de servidores, puede ejecutar el Asistente para certificados de Lync Server 2013 en cualquiera de los servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-130">If you have multiple Edge Servers in one location in a pool, you can run the Lync Server 2013 Certificate Wizard on any one of the Edge Servers.</span></span>

    
    </div>

2.  <span data-ttu-id="7a2e1-131">En la página **Tareas de certificado disponibles**, haga clic en **Crear una nueva solicitud de certificado**.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-131">On the **Available Certificate Tasks** page, click **Create a new certificate request**.</span></span>

3.  <span data-ttu-id="7a2e1-132">En la página **Solicitud de certificado**, haga clic en **Certificado perimetral externo**.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-132">On the **Certificate Request** page, click **External Edge Certificate**.</span></span>

4.  <span data-ttu-id="7a2e1-133">En la página **Solicitud retrasada o inmediata**, active la casilla **Prepare ahora la solicitud, pero enviarla más tarde**.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-133">On the **Delayed or Immediate Request** page, select the **Prepare the request now, but send it later** check box.</span></span>

5.  <span data-ttu-id="7a2e1-134">En la **Página archivo de solicitud de certificado** , escriba la ruta de acceso completa y el nombre de archivo del archivo en el que se va a guardar la solicitud\\(\_por\_ejemplo, c: CERT externos Edge. cer).</span><span class="sxs-lookup"><span data-stu-id="7a2e1-134">On the **Certificate Request File** page, type the full path and file name of the file to which the request is to be saved (for example, c:\\cert\_exernal\_edge.cer).</span></span>

6.  <span data-ttu-id="7a2e1-135">En la página **Especificar plantilla de certificado alternativa**, para usar una plantilla distinta a la plantilla predeterminada WebServer, active la casilla **Usar plantilla de certificado alternativa para la entidad de certificación seleccionada**.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-135">On the **Specify Alternate Certificate Template** page, to use a template other than the default WebServer template, select the **Use alternative certificate template for the selected certification authority** check box.</span></span>

7.  <span data-ttu-id="7a2e1-136">En la página **Nombre y configuración de seguridad**, siga este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="7a2e1-136">On the **Name and Security Settings** page, do the following:</span></span>
    
      - <span data-ttu-id="7a2e1-137">En **Nombre descriptivo**, escriba un nombre para mostrar para el certificado.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-137">In **Friendly name**, type a display name for the certificate.</span></span>
    
      - <span data-ttu-id="7a2e1-138">En **Longitud de bits**, especifique la longitud de bits (normalmente, el valor predeterminado es **2048**).</span><span class="sxs-lookup"><span data-stu-id="7a2e1-138">In **Bit length**, specify the bit length (typically, the default of **2048**).</span></span>
    
      - <span data-ttu-id="7a2e1-139">Compruebe que la casilla **Marcar la clave privada del certificado como exportable** esté seleccionada.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-139">Verify that the **Mark certificate private key as exportable** check box is selected.</span></span>

8.  <span data-ttu-id="7a2e1-140">En la página **Información de la organización**, escriba un nombre para la organización y la unidad organizativa (por ejemplo, una división o departamento).</span><span class="sxs-lookup"><span data-stu-id="7a2e1-140">On the **Organization Information** page, type the name for the organization and the organizational unit (for example, a division or department).</span></span>

9.  <span data-ttu-id="7a2e1-141">En la página **Información geográfica**, escriba la información de ubicación.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-141">On the **Geographical Information** page, specify the location information.</span></span>

10. <span data-ttu-id="7a2e1-p107">En la página **Nombre de sujeto/nombres alternativos de sujeto**, la información se rellenará automáticamente gracias al asistente que se muestra. Si necesita otros nombres alternativos de sujeto, especifíquelos en los dos pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-p107">On the **Subject Name/Subject Alternate Names** page, the information to be automatically populated by the wizard is displayed. If additional subject alternative names are needed, you specify them in the next two steps.</span></span>

11. <span data-ttu-id="7a2e1-144">En la página **configuración de dominio SIP en nombres alternativos de sujeto (San)** , active la casilla de verificación dominio para agregar un SIP. \<entrada\> sipdomain a la lista de nombres alternativos de sujeto.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-144">On the **SIP Domain Setting on Subject Alternate Names (SANs)** page, select the domain check box to add a sip.\<sipdomain\> entry to the subject alternative names list.</span></span>

12. <span data-ttu-id="7a2e1-145">En la página **Configurar nombres alternativos de sujeto**, especifique cualquier nombre alternativo de sujeto adicional que necesite.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-145">On the **Configure Additional Subject Alternate Names** page, specify any additional subject alternative names that are required.</span></span>

13. <span data-ttu-id="7a2e1-146">En la página **Resumen de la solicitud**, revise la información del certificado que va a usar para generar la solicitud.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-146">On the **Request Summary** page, review the certificate information to be used to generate the request.</span></span>

14. <span data-ttu-id="7a2e1-147">Cuando finalice la ejecución de los comandos, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7a2e1-147">After the commands finish running, do the following:</span></span>
    
      - <span data-ttu-id="7a2e1-148">Para visualizar el registro de la solicitud de certificación, haga clic en **Ver registro**.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-148">To view the log for the certificate request, click **View Log**.</span></span>
    
      - <span data-ttu-id="7a2e1-149">Para completar la solicitud de certificación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-149">To complete the certificate request, click **Next**.</span></span>

15. <span data-ttu-id="7a2e1-150">En la página **Archivo de solicitud de certificados**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7a2e1-150">On the **Certificate Request File** page, do the following:</span></span>
    
      - <span data-ttu-id="7a2e1-151">Para visualizar el archivo de solicitud de firma de certificado (CSR) que se ha generado, haga clic en **Ver**.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-151">To view the generated certificate signing request (CSR) file, click **View**.</span></span>
    
      - <span data-ttu-id="7a2e1-152">Para cerrar el asistente, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-152">To close the wizard, click **Finish**.</span></span>

16. <span data-ttu-id="7a2e1-153">Copie el archivo de resultados en una ubicación donde pueda enviarlo a la entidad de certificación pública.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-153">Copy the output file to a location where you can submit it to the public CA.</span></span>

</div>

<div>

## <a name="to-create-a-certificate-request-for-the-external-interface-of-the-edge-server-to-support-public-im-connectivity-with-aol"></a><span data-ttu-id="7a2e1-154">Para crear una solicitud de certificado para la interfaz externa del servidor perimetral para permitir la conectividad de mensajería instantánea pública con AOL</span><span class="sxs-lookup"><span data-stu-id="7a2e1-154">To create a certificate request for the external interface of the Edge Server to support public IM connectivity with AOL</span></span>

1.  <span data-ttu-id="7a2e1-155">Cuando la plantilla requerida esté disponible para la CA, use el siguiente cmdlet de Windows PowerShell desde el servidor perimetral para solicitar el certificado:</span><span class="sxs-lookup"><span data-stu-id="7a2e1-155">When the required template is available to the CA, use the following Windows PowerShell cmdlet from at the Edge Server to request the certificate:</span></span>
    
        Request-CsCertificate -New -Type AccessEdgeExternal  -Output C:\ <certfilename.txt or certfilename.csr>  -ClientEku $true -Template <template name>
    
    <span data-ttu-id="7a2e1-156">El nombre de certificado predeterminado de la plantilla que se proporciona en Lync Server 2013 es servidor Web.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-156">The default certificate name of the template provided in Lync Server 2013 is Web Server.</span></span> <span data-ttu-id="7a2e1-157">Especifique el nombre \<\> de la plantilla solo si necesita usar una plantilla que sea diferente de la plantilla predeterminada.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-157">Only specify the \<template name\> if you need to use a template that is different from the default template.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7a2e1-158">Si su organización desea admitir la conectividad de mensajería instantánea pública con AOL, debe usar Windows PowerShell en lugar del Asistente para certificados para solicitar que el certificado se asigne al perímetro externo para el servicio perimetral de acceso.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-158">If your organization wants to support public IM connectivity with AOL, you must use Windows PowerShell instead of the Certificate Wizard to request the certificate to be assigned to the external edge for the Access Edge service.</span></span> <span data-ttu-id="7a2e1-159">Esto se debe a que la plantilla del servidor Web de Lync Server 2013 que el Asistente para solicitud de certificados usa para solicitar un certificado no admite la configuración de EKU del cliente.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-159">This is because the Lync Server 2013 Web Server template that the Certificate Wizard uses to request a certificate does not support client EKU configuration.</span></span> <span data-ttu-id="7a2e1-160">Antes de usar Windows PowerShell para crear el certificado, el administrador de la entidad de certificación debe crear e implementar una nueva plantilla que admita EKU de cliente.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-160">Before using Windows PowerShell to create the certificate, the CA administrator must create and deploy a new template that supports client EKU.</span></span>

    
    </div>

</div>

<div>

## <a name="to-submit-a-request-to-a-public-certification-authority"></a><span data-ttu-id="7a2e1-161">Para enviar una solicitud a una entidad de certificación pública</span><span class="sxs-lookup"><span data-stu-id="7a2e1-161">To submit a request to a public certification authority</span></span>

1.  <span data-ttu-id="7a2e1-162">Abra el archivo de resultados.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-162">Open the output file.</span></span>

2.  <span data-ttu-id="7a2e1-163">Copie y pegue el contenido de la Solicitud de firma de certificado (CSR).</span><span class="sxs-lookup"><span data-stu-id="7a2e1-163">Copy and paste the contents of the Certificate Signing Request (CSR).</span></span>

3.  <span data-ttu-id="7a2e1-164">Si se le solicita, especifique lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7a2e1-164">If prompted, specify the following:</span></span>
    
      - <span data-ttu-id="7a2e1-165">**Microsoft** como la plataforma de servidor.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-165">**Microsoft** as the server platform.</span></span>
    
      - <span data-ttu-id="7a2e1-166">**IIS** como la versión.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-166">**IIS** as the version.</span></span>
    
      - <span data-ttu-id="7a2e1-167">**Web Server** como el tipo de uso.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-167">**Web Server** as the usage type.</span></span>
    
      - <span data-ttu-id="7a2e1-168">**PKCS7** como el formato de respuesta.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-168">**PKCS7** as the response format.</span></span>

4.  <span data-ttu-id="7a2e1-169">Después de que la entidad de certificación pública compruebe toda la información, recibirá un mensaje de correo electrónico con el texto requerido para el certificado.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-169">When the public CA has verified your information, you will receive an email message containing text required for your certificate.</span></span>

5.  <span data-ttu-id="7a2e1-170">Copie el texto del mensaje de correo electrónico y guarde el contenido en un archivo de texto (.txt) en su equipo local.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-170">Copy the text from the email message and save the contents in a text file (.txt) on your local computer.</span></span>

</div>

<div>

## <a name="to-import-the-certificate-for-the-external-interface-of-the-edge-server"></a><span data-ttu-id="7a2e1-171">Para importar el certificado para la interfaz externa del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="7a2e1-171">To import the certificate for the external interface of the Edge Server</span></span>

1.  <span data-ttu-id="7a2e1-172">Inicie sesión como miembro del grupo Administradores en el mismo servidor perimetral en el que creó la solicitud de certificado.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-172">Log on as a member of the Administrators group to the same Edge Server on which you created the certificate request.</span></span>

2.  <span data-ttu-id="7a2e1-173">En el Asistente para la implementación, en la página **Implementar el servidor perimetral**, junto a **Paso 3: Solicitar, instalar o asignar certificados**, haga clic en **Ejecutar de nuevo**.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-173">In the Deployment Wizard, on the **Deploy Edge Server** page, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>

3.  <span data-ttu-id="7a2e1-174">En la página **Tareas de certificado disponibles**, haga clic en **Importar un certificado de un archivo .P7b, .pfx o .cer**.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-174">On the **Available Certificate Tasks** page, click **Import a certificate from a .p7b, pfx or .cer file**.</span></span>

4.  <span data-ttu-id="7a2e1-p110">En la página **Importar certificado**, haga clic en **Examinar** para localizar y seleccionar el certificado que ha solicitado para la interfaz externa del servidor perimetral (también puede escribir la ruta completa y el nombre de archivo). Si el certificado contiene una clave privada, seleccione **El archivo del certificado contiene la clave privada del certificado** y escriba la contraseña de la clave privada. Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-p110">On the **Import Certificate** page, click **Browse** to locate and select the certificate that you requested for the external interface of the Edge Server (or, you can type the full path and file name). If the certificate contains a private key, select **Certificate file contains certificate’s private key** and type the password for the private key. Click **Next**.</span></span>

5.  <span data-ttu-id="7a2e1-178">En la página **Importar resumen de certificado**, revise el resumen y, entonces, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-178">On **Import Certificate Summary** page, review the summary and then click **Next**.</span></span>

6.  <span data-ttu-id="7a2e1-179">En **Ejecutar comandos**, revise los resultados de la importación, haga clic en **Ver registro** si necesita más información y, entonces, haga clic en **Finalizar** para completar la importación del certificado.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-179">On **Executing Commands**, review the results of the import, click **View Log** for more information as needed, and then click **Finish** to complete the certificate import.</span></span>

7.  <span data-ttu-id="7a2e1-p111">Si está configurando un grupo de servidores perimetral, exporte el certificado con su clave privada como se indica en el procedimiento "Para exportar el certificado con la clave privada para servidores perimetrales de un grupo" que encontrará más adelante en este tema. Copie el archivo del certificado exportado en los servidores perimetrales e impórtelo en el almacén del equipo de cada servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-p111">If you are configuring an Edge Server pool, export the certificate with its private key as outlined in the “To export the certificate with the private key for Edge Servers in a pool” procedure later in this topic. Copy the exported certificate file to the other Edge Servers, and import it into the computer store on each Edge Server.</span></span>

</div>

<div>

## <a name="to-export-the-certificate-with-the-private-key-for-edge-servers-in-a-pool"></a><span data-ttu-id="7a2e1-182">Para exportar el certificado con la clave privada para servidores perimetrales de un grupo</span><span class="sxs-lookup"><span data-stu-id="7a2e1-182">To export the certificate with the private key for Edge Servers in a pool</span></span>

1.  <span data-ttu-id="7a2e1-183">Inicie sesión como miembro del grupo Administradores en el mismo servidor perimetral en el que desea importar el certificado.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-183">Log on as a member of the Administrators group to the same Edge Server on which you imported the certificate.</span></span>

2.  <span data-ttu-id="7a2e1-184">Haga clic en **Inicio**, en **Ejecutar** y escriba **MMC**.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-184">Click **Start**, click **Run**, and type **MMC**.</span></span>

3.  <span data-ttu-id="7a2e1-185">En la consola Microsoft Management Console (MMC), haga clic en **Archivo** y, entonces, haga clic en **Agregar o quitar complemento**.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-185">In the Microsoft Management Console (MMC) console, click **File**, and then click **Add/Remove Snap-in**.</span></span>

4.  <span data-ttu-id="7a2e1-186">En **Agregar o quitar complemento**, haga clic en **Certificados** y, entonces, en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-186">In **Add or Remove Snap-ins**, click **Certificates**, and then click **Add**.</span></span>

5.  <span data-ttu-id="7a2e1-187">En el cuadro de diálogo **Certificados**, seleccione **Cuenta de equipo**, haga clic en **Siguiente**, seleccione **Equipo local: (el equipo en el que se ejecuta esta consola)** en **Seleccionar equipo**, haga clic en **Finalizar** y, después, en **Aceptar** para finalizar la configuración de la consola MMC.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-187">In the **Certificates** dialog box, select **Computer account**, click **Next**, select **Local computer: (the computer this console is running on)** in **Select Computer**, click **Finish** and then click **OK** to complete configuration of the MMC console.</span></span>

6.  <span data-ttu-id="7a2e1-188">Haga doble clic en **Certificados (equipo local)** para ampliar los almacenes de certificados, haga doble clic en **Personal** y, a continuación, haga doble clic en **Certificados**.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-188">Double-click **Certificates (Local Computer)** to expand the certificate stores, double-click **Personal**, and then double-click **Certificates**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="7a2e1-p112">Si no hay certificados en el almacén Certificados Personal para el equipo local, no habrá una clave privada asociada al certificado que se importó. Revise los pasos para la solicitud y la importación. Si el problema continúa, póngase en contacto con su administrador o proveedor de entidades de certificación.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-p112">If there are no certificates in the Certificates Personal store for the local computer, there is no private key associated with the certificate that was imported. Review the request and import steps. If the problem persists, contact your certification authority administrator or provider.</span></span>

    
    </div>

7.  <span data-ttu-id="7a2e1-192">En el **almacén Certificados Personal del equipo local**, haga clic con el botón secundario en el certificado que va a exportar, haga clic en **Todas las tareas** y, a continuación, haga clic en **Exportar**.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-192">In the **Certificates Personal store for the local computer**, right-click the certificate that you are exporting, click **All Tasks**, and then click **Export**.</span></span>

8.  <span data-ttu-id="7a2e1-193">En el asistente para exportación de certificados, haga clic en **Siguiente**, seleccione **Exportar la clave privada** y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-193">In the Certificate Export Wizard, click **Next**, select **Yes, export the private key**, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7a2e1-p113">Si la opción <STRONG>Exportar la clave privada</STRONG> no se encuentra disponible, se deberá a que no se marcó la clave privada asociada a este certificado para la exportación. Tendrá que solicitar de nuevo el certificado y, antes de que se inicie la exportación, deberá asegurarse de que el certificado está marcado para que se exporte la clave privada. Póngase en contacto con el administrador o proveedor de entidades de certificación.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-p113">If the selection <STRONG>Yes, export the private key</STRONG> is not available, the private key associated with this certificate was not marked for export. You will need to request the certificate again, ensuring that the certificate is marked to allow for the export of the private key before you can continue with the export. Contact your certification authority administrator or provider.</span></span>

    
    </div>

9.  <span data-ttu-id="7a2e1-197">En el cuadro de diálogo formatos de archivo de exportación, seleccione **intercambio\#de información personal: PKCS 12 (. PFX)** y, a continuación, seleccione lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7a2e1-197">On the Export File Formats dialog, select **Personal Information Exchange – PKCS\#12 (.PFX)** and then select the following:</span></span>
    
      - <span data-ttu-id="7a2e1-198">Si es posible, incluir todos los certificados en la ruta de acceso de certificación</span><span class="sxs-lookup"><span data-stu-id="7a2e1-198">Include all certificates in the certification path if possible</span></span>
    
      - <span data-ttu-id="7a2e1-199">Exportar todas las propiedades extendidas</span><span class="sxs-lookup"><span data-stu-id="7a2e1-199">Export all extended properties</span></span>
        
        <div>
        

        > [!WARNING]  
        > <span data-ttu-id="7a2e1-p114">Cuando exporte el certificado desde un servidor perimetral, no seleccione <STRONG>Eliminar la clave privada si la exportación es correcta</STRONG>. Al seleccionar esta opción es necesario importar el certificado y la clave privada a este servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-p114">When exporting the certificate from an Edge server, do not select <STRONG>Delete the private key if the export is successful</STRONG>. Selecting this option will require that you import the certificate and the private key to this Edge server.</span></span>

        
        </div>

10. <span data-ttu-id="7a2e1-202">Haga clic en  \*\*Siguiente \*\*.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-202">Click **Next**.</span></span>

11. <span data-ttu-id="7a2e1-203">Escriba una contraseña para la clave privada, vuelva a escribirla para confirmarla y, entonces, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-203">Type a password for the private key, type the password again to confirm, and then click **Next**.</span></span>

12. <span data-ttu-id="7a2e1-p115">Escriba la ruta y nombre de archivo del certificado exportado, utilizando la extensión de archivo .pfx. La ruta debe estar accesible para todos los demás servidores perimetrales del grupo o disponible para el transporte mediante medios extraíbles, por ejemplo, una unidad flash USB. Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-p115">Type a path and file name for the exported certificate, using a file extension of .pfx. The path must either be accessible to all other Edge servers in the pool or available to transport by means of removable media - for example, a USB flash drive. Click **Next**.</span></span>

13. <span data-ttu-id="7a2e1-207">Revise el resumen en **Finalización del Asistente para exportación de certificados** y, a continuación, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-207">Review the summary in **Completing the Certificate Export Wizard**, and then click **Finish**.</span></span>

14. <span data-ttu-id="7a2e1-208">En el cuadro de diálogo que indica que la exportación se ha completado correctamente, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-208">In the successful export dialog box, click **OK**.</span></span>

15. <span data-ttu-id="7a2e1-209">Importe el archivo de certificado exportado en los demás servidores perimetrales siguiendo los pasos descritos en el procedimiento “Para importar el certificado para la interfaz externa del servidor perimetral”, que encontrará más arriba en este tema.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-209">Import the exported certificate file to the other Edge servers following the steps outlined in the “To import the certificate for the external interface of the Edge Server” procedure earlier in this topic.</span></span>

</div>

<div>

## <a name="to-assign-the-certificate-for-the-external-interface-of-the-edge-server"></a><span data-ttu-id="7a2e1-210">Para asignar el certificado para la interfaz externa del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="7a2e1-210">To assign the certificate for the external interface of the Edge Server</span></span>

1.  <span data-ttu-id="7a2e1-211">En cada servidor perimetral, en el Asistente para la implementación, junto al **Paso 3: Solicitar, instalar o asignar certificados**, haga clic en **Ejecutar de nuevo**.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-211">On each Edge Server, in the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>

2.  <span data-ttu-id="7a2e1-212">En la página **Tareas de certificado disponibles**, haga clic en **Asignar un certificado existente**.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-212">On the **Available Certificate Tasks** page, click **Assign an existing certificate**.</span></span>

3.  <span data-ttu-id="7a2e1-213">En la página **Asignación del certificado**, haga clic en **Certificado perimetral externo** y active la casilla **Usos avanzados de certificados**.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-213">On the **Certificate Assignment** page, click **External Edge Certificate** and select the **Advanced Certificate Usages** check box.</span></span>

4.  <span data-ttu-id="7a2e1-214">En la página **Usos avanzados de certificados**, active todas las casillas para asignar el certificado para todos los usos.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-214">On the **Advanced Certificate Usages** page, select all check boxes to assign the certificate for all usages.</span></span>

5.  <span data-ttu-id="7a2e1-215">En la página **Almacén de certificado**, seleccione el certificado público que solicitó e importó para la interfaz externa del servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-215">On the **Certificate Store** page, select the public certificate that you requested and imported for the external interface of the Edge Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7a2e1-216">Si el certificado que solicitó e importó no está en la lista, uno de los métodos para solucionar el problema consiste en comprobar que el nombre de sujeto y los nombres alternativos de sujeto del certificado cumplen todos los requisitos para el certificado y, si importó manualmente el certificado y la cadena de certificados en lugar de usar los procedimientos anteriores, que el certificado se encuentre en el almacén de certificados correcto (el almacén de certificados del equipo, no el almacén de certificados del usuario o del servicio).</span><span class="sxs-lookup"><span data-stu-id="7a2e1-216">If the certificate you requested and imported is not in the list, one of the trouble shooting methods is to verify that subject name and subject alternative names of the certificate meet all requirements for the certificate and, if you manually imported the certificate and certificate chain instead of using the preceding procedures, that the certificate is in the correct certificate store (the computer certificate store, not the user or service certificate store).</span></span>

    
    </div>

6.  <span data-ttu-id="7a2e1-217">En la página **Resumen de asignación de certificados**, revise su configuración y, a continuación, haga clic en **Siguiente** para asignar los certificados.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-217">On the **Certificate Assignment Summary** page, review your settings, and then click **Next** to assign the certificates.</span></span>

7.  <span data-ttu-id="7a2e1-218">En la página de finalización del asistente, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-218">On the wizard completion page, click **Finish**.</span></span>

8.  <span data-ttu-id="7a2e1-219">Después de usar este procedimiento para asignar el certificado perimetral, abra el complemento Certificado en cada servidor, expanda **Certificados (equipo local)**, expanda **Personal**, haga clic en **Certificados** y, finalmente, compruebe que el certificado aparezca en el panel de detalles.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-219">After using this procedure to assign the edge certificate, open the Certificate snap-in on each server, expand **Certificates (Local computer)**, expand **Personal**, click **Certificates**, and then verify in the details pane that the certificate is listed.</span></span>

9.  <span data-ttu-id="7a2e1-220">Si la implementación incluye varios servidores perimetrales, repita este procedimiento con todos los servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="7a2e1-220">If your deployment includes multiple Edge Servers, repeat this procedure for each Edge Server.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

