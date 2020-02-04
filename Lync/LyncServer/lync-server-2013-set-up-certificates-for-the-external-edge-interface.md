---
title: 'Lync Server 2013: Configurar certificados para la interfaz perimetral externa'
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
ms.openlocfilehash: c1c836191c19eeadd915d0263c89b52289f60fe9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764676"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-up-certificates-for-the-external-edge-interface-for-lync-server-2013"></a><span data-ttu-id="a5bc5-102">Configurar certificados para la interfaz perimetral externa en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a5bc5-102">Set up certificates for the external edge interface for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a5bc5-103">_**Última modificación del tema:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="a5bc5-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a5bc5-104">Cuando ejecute el Asistente para certificados, asegúrese de haber iniciado sesión con una cuenta que sea miembro de un grupo al que se le hayan asignado los permisos adecuados para el tipo de plantilla de certificado que va a usar.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-104">When you run the Certificate Wizard, ensure that you are logged in using an account that is a member of a group that has been assigned the appropriate permissions for the type of certificate template you will use.</span></span> <span data-ttu-id="a5bc5-105">De forma predeterminada, una solicitud de certificado de Lync Server usará la plantilla de certificado de servidor Web.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-105">By default, a Lync Server certificate request will use the Web Server certificate template.</span></span> <span data-ttu-id="a5bc5-106">Si usa una cuenta que sea miembro del grupo RTCUniversalServerAdmins para solicitar un certificado con esta plantilla, compruebe que el grupo tiene asignados los permisos de inscripción necesarios para usar esa plantilla.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-106">If you use an account that is a member of the RTCUniversalServerAdmins group to request a certificate using this template, verify that the group has been assigned the Enroll permissions required to use that template.</span></span>



</div>

<span data-ttu-id="a5bc5-107">Cada servidor perimetral requiere un certificado público en la interfaz entre la red perimetral e Internet, y el nombre alternativo de asunto del certificado debe contener los nombres externos del servicio perimetral de acceso y el servicio perimetral de conferencia web totalmente nombres de dominio calificados (FQDN).</span><span class="sxs-lookup"><span data-stu-id="a5bc5-107">Each Edge Server requires a public certificate on the interface between the perimeter network and the Internet, and the certificate’s subject alternative name must contain the external names of the Access Edge service and Web Conferencing Edge service fully qualified domain names (FQDNs).</span></span>

<span data-ttu-id="a5bc5-108">Para obtener más información sobre este y otros requisitos de certificado, consulte [requisitos de certificados para el acceso de usuarios externos en Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="a5bc5-108">For details about this and other certificate requirements, see [Certificate requirements for external user access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span></span>

<span data-ttu-id="a5bc5-109">Para obtener una lista de entidades de certificación (CA) públicas que proporcionen certificados que cumplan con los requisitos específicos para certificados de comunicaciones unificadas y que se hayan asociado con Microsoft para asegurarse de que funcionan con el Asistente para certificados de Lync Server 2013, consulte el artículo 929395 de Microsoft Knowledge base, "asociados [http://go.microsoft.com/fwlink/p/?linkId=202834](http://go.microsoft.com/fwlink/p/?linkid=202834)de certificados de comunicaciones unificadas para Exchange Server y Communications Server", en.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-109">For a list of public certification authorities (CAs) that provide certificates that comply with specific requirements for unified communications certificates and have partnered with Microsoft to ensure they work with the Lync Server 2013 Certificate Wizard, see Microsoft Knowledge Base article 929395, "Unified Communications Certificate Partners for Exchange Server and for Communications Server," at [http://go.microsoft.com/fwlink/p/?linkId=202834](http://go.microsoft.com/fwlink/p/?linkid=202834).</span></span>

<div>

## <a name="configuring-certificates-on-the-external-interfaces"></a><span data-ttu-id="a5bc5-110">Configurar certificados en las interfaces externas</span><span class="sxs-lookup"><span data-stu-id="a5bc5-110">Configuring Certificates on the External Interfaces</span></span>

<span data-ttu-id="a5bc5-111">Para configurar un certificado en la interfaz de borde externo en un sitio, siga los procedimientos de esta sección para hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a5bc5-111">To set up a certificate on the external edge interface at a site, use the procedures in this section to do the following:</span></span>

  - <span data-ttu-id="a5bc5-112">Cree la solicitud de certificado para la interfaz externa del servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-112">Create the certificate request for the external interface of the Edge Server.</span></span>

  - <span data-ttu-id="a5bc5-113">Envíe la solicitud a la entidad emisora de certificados pública.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-113">Submit the request to your public CA.</span></span>

  - <span data-ttu-id="a5bc5-114">Importe el certificado de la interfaz externa de cada servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-114">Import the certificate for the external interface of each Edge Server.</span></span>

  - <span data-ttu-id="a5bc5-115">Asigne el certificado de la interfaz externa de cada servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-115">Assign the certificate for the external interface of each Edge Server.</span></span>

  - <span data-ttu-id="a5bc5-116">Si su implementación incluye varios servidores perimetrales, exporte el certificado junto con su clave privada y, a continuación, cópielo en los otros servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-116">If your deployment includes multiple Edge Servers, export the certificate along with its private key, and then copy it to the other Edge Servers.</span></span> <span data-ttu-id="a5bc5-117">A continuación, para cada servidor perimetral, impórtelo y asígnelo como se ha descrito anteriormente.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-117">Then, for each Edge Server, import it and assign it as previously described.</span></span> <span data-ttu-id="a5bc5-118">Repita este procedimiento para cada servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-118">Repeat this procedure for each Edge Server.</span></span>

<span data-ttu-id="a5bc5-119">Puede solicitar certificados públicos directamente desde una entidad de certificación (CA) pública (como desde el sitio web de una entidad de certificación pública).</span><span class="sxs-lookup"><span data-stu-id="a5bc5-119">You can request public certificates directly from a public certification authority (CA) (such as from the website of a public CA).</span></span> <span data-ttu-id="a5bc5-120">Los procedimientos de esta sección usan el Asistente de certificados para la mayoría de las tareas de certificados.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-120">The procedures in this section use the Certificate Wizard for most certificate tasks.</span></span> <span data-ttu-id="a5bc5-121">Si decide solicitar un certificado directamente desde una entidad de certificación pública, tendrá que modificar cada procedimiento como corresponda para solicitar, transportar e importar el certificado, así como para importar la cadena de certificados.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-121">If you chose to request a certificate directly from a public CA, then you will need to modify each procedure as appropriate to request, transport, and import the certificate and also to import the certificate chain.</span></span>

<span data-ttu-id="a5bc5-122">Cuando solicite un certificado de una entidad emisora externa, las credenciales proporcionadas deben tener derechos para solicitar un certificado de esa entidad.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-122">When you request a certificate from an External CA, the credentials provided must have rights to request a certificate from that CA.</span></span> <span data-ttu-id="a5bc5-123">Cada CA tiene una directiva de seguridad que define qué credenciales (es decir, nombres de usuarios y grupos específicos) pueden solicitar, emitir, administrar o leer certificados.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-123">Each CA has a security policy that defines which credentials (that is, specific user and group names) are allowed to request, issue, manage, or read certificates.</span></span>

<span data-ttu-id="a5bc5-124">Si decide usar los certificados Microsoft Management Console (MMC) para importar la cadena de certificados y el certificado, debe importarlos en el almacén de certificados para el equipo.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-124">If you decide to use the Certificates Microsoft Management Console (MMC) to import the certificate chain and certificate, you must import them to the certificate store for the computer.</span></span> <span data-ttu-id="a5bc5-125">Si los importa al almacén de certificados de usuario o servicio, el certificado no estará disponible para su asignación en el Asistente para certificados de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-125">If you import them to the user or service certificate store, the certificate will not be available for assignment in the Lync Server 2013 Certificate Wizard.</span></span>

<div>

## <a name="to-create-the-certificate-request-for-the-external-interface-of-the-edge-server"></a><span data-ttu-id="a5bc5-126">Para crear la solicitud de certificado para la interfaz externa del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="a5bc5-126">To create the certificate request for the external interface of the Edge Server</span></span>

1.  <span data-ttu-id="a5bc5-127">En el servidor perimetral, en el Asistente para la implementación, junto al **paso 3: solicitar, instalar o asignar certificados**, haga clic en **Ejecutar de nuevo**.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-127">On the Edge Server, in the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a5bc5-128">Si su organización desea admitir la conectividad de mensajería instantánea (mi) pública con AOL, no puede usar el Asistente para la implementación de Lync Server para solicitar el certificado.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-128">If your organization wants to support public instant messaging (IM) connectivity with AOL, you cannot use the Lync Server Deployment Wizard to request the certificate.</span></span> <span data-ttu-id="a5bc5-129">En su lugar, realice los pasos de la sección "para crear una solicitud de certificado para la interfaz externa del servidor perimetral para admitir la conectividad de mensajería instantánea pública con AOL" más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-129">Instead, perform the steps in the “To create a certificate request for the external interface of the Edge Server to support public IM connectivity with AOL” procedure later in this topic.</span></span><BR><span data-ttu-id="a5bc5-130">Si tiene varios servidores perimetrales en una ubicación de un grupo, puede ejecutar el Asistente para certificados de Lync Server 2013 en cualquiera de los servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-130">If you have multiple Edge Servers in one location in a pool, you can run the Lync Server 2013 Certificate Wizard on any one of the Edge Servers.</span></span>

    
    </div>

2.  <span data-ttu-id="a5bc5-131">En la página **Tareas de certificado disponibles**, haga clic en **Crear una nueva solicitud de certificado**.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-131">On the **Available Certificate Tasks** page, click **Create a new certificate request**.</span></span>

3.  <span data-ttu-id="a5bc5-132">En la página **solicitud de certificado** , haga clic en certificado de **borde externo**.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-132">On the **Certificate Request** page, click **External Edge Certificate**.</span></span>

4.  <span data-ttu-id="a5bc5-133">En la página **solicitud inmediata o demorada** , active la casilla **preparar la solicitud ahora pero enviarla más tarde** .</span><span class="sxs-lookup"><span data-stu-id="a5bc5-133">On the **Delayed or Immediate Request** page, select the **Prepare the request now, but send it later** check box.</span></span>

5.  <span data-ttu-id="a5bc5-134">En la **Página archivo de solicitud de certificado** , escriba la ruta de acceso completa y el nombre del archivo en el que se va a guardar la solicitud (por\\ejemplo\_,\_c: CERT la Edge. cer).</span><span class="sxs-lookup"><span data-stu-id="a5bc5-134">On the **Certificate Request File** page, type the full path and file name of the file to which the request is to be saved (for example, c:\\cert\_exernal\_edge.cer).</span></span>

6.  <span data-ttu-id="a5bc5-135">En la página **especificar plantilla de certificado alternativa** , para usar una plantilla distinta de la plantilla predeterminada de WebServer, seleccione la casilla **Usar plantilla de certificado alternativa para la entidad emisora de certificados seleccionada** .</span><span class="sxs-lookup"><span data-stu-id="a5bc5-135">On the **Specify Alternate Certificate Template** page, to use a template other than the default WebServer template, select the **Use alternative certificate template for the selected certification authority** check box.</span></span>

7.  <span data-ttu-id="a5bc5-136">En la página **nombre y configuración de seguridad** , haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a5bc5-136">On the **Name and Security Settings** page, do the following:</span></span>
    
      - <span data-ttu-id="a5bc5-137">En **nombre descriptivo**, escriba un nombre para mostrar para el certificado.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-137">In **Friendly name**, type a display name for the certificate.</span></span>
    
      - <span data-ttu-id="a5bc5-138">En **longitud bit**, especifique la longitud en bits (normalmente, el valor predeterminado de **2048**).</span><span class="sxs-lookup"><span data-stu-id="a5bc5-138">In **Bit length**, specify the bit length (typically, the default of **2048**).</span></span>
    
      - <span data-ttu-id="a5bc5-139">Compruebe que la casilla **marcar clave privada de certificado como exportable** está activada.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-139">Verify that the **Mark certificate private key as exportable** check box is selected.</span></span>

8.  <span data-ttu-id="a5bc5-140">En la página información de la **organización** , escriba el nombre de la organización y la unidad organizativa (por ejemplo, una división o un departamento).</span><span class="sxs-lookup"><span data-stu-id="a5bc5-140">On the **Organization Information** page, type the name for the organization and the organizational unit (for example, a division or department).</span></span>

9.  <span data-ttu-id="a5bc5-141">En la página **información geográfica** , especifique la información de ubicación.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-141">On the **Geographical Information** page, specify the location information.</span></span>

10. <span data-ttu-id="a5bc5-142">En la página **nombre de sujeto/nombres alternativos de asunto** , se muestra la información que el asistente rellenará automáticamente.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-142">On the **Subject Name/Subject Alternate Names** page, the information to be automatically populated by the wizard is displayed.</span></span> <span data-ttu-id="a5bc5-143">Si se necesitan nombres alternativos adicionales, debe especificarlos en los dos pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-143">If additional subject alternative names are needed, you specify them in the next two steps.</span></span>

11. <span data-ttu-id="a5bc5-144">En la página **configuración del dominio SIP en la página de nombres alternativos de asunto (San)** , seleccione la casilla dominio para agregar un SIP. \<sipdomain\> entrada a la lista de nombres alternativos de asunto.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-144">On the **SIP Domain Setting on Subject Alternate Names (SANs)** page, select the domain check box to add a sip.\<sipdomain\> entry to the subject alternative names list.</span></span>

12. <span data-ttu-id="a5bc5-145">En la página **configurar otros nombres alternativos de asunto** , especifique los nombres alternativos adicionales que sean obligatorios.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-145">On the **Configure Additional Subject Alternate Names** page, specify any additional subject alternative names that are required.</span></span>

13. <span data-ttu-id="a5bc5-146">En la página **solicitar Resumen** , revise la información del certificado que se va a usar para generar la solicitud.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-146">On the **Request Summary** page, review the certificate information to be used to generate the request.</span></span>

14. <span data-ttu-id="a5bc5-147">Cuando termine de ejecutarse los comandos, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a5bc5-147">After the commands finish running, do the following:</span></span>
    
      - <span data-ttu-id="a5bc5-148">Para ver el registro de la solicitud de certificado, haga clic en **Ver registro**.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-148">To view the log for the certificate request, click **View Log**.</span></span>
    
      - <span data-ttu-id="a5bc5-149">Para completar la solicitud de certificado, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-149">To complete the certificate request, click **Next**.</span></span>

15. <span data-ttu-id="a5bc5-150">En la página **archivo de solicitud de certificado** , haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a5bc5-150">On the **Certificate Request File** page, do the following:</span></span>
    
      - <span data-ttu-id="a5bc5-151">Para ver el archivo de solicitud de firma de certificado generado (CSR), haga clic en **Ver**.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-151">To view the generated certificate signing request (CSR) file, click **View**.</span></span>
    
      - <span data-ttu-id="a5bc5-152">Para cerrar el asistente, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-152">To close the wizard, click **Finish**.</span></span>

16. <span data-ttu-id="a5bc5-153">Copie el archivo de salida en una ubicación en la que pueda enviarlo a la entidad emisora de certificados pública.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-153">Copy the output file to a location where you can submit it to the public CA.</span></span>

</div>

<div>

## <a name="to-create-a-certificate-request-for-the-external-interface-of-the-edge-server-to-support-public-im-connectivity-with-aol"></a><span data-ttu-id="a5bc5-154">Para crear una solicitud de certificado para la interfaz externa del servidor perimetral para admitir la conectividad de mensajería instantánea pública con AOL</span><span class="sxs-lookup"><span data-stu-id="a5bc5-154">To create a certificate request for the external interface of the Edge Server to support public IM connectivity with AOL</span></span>

1.  <span data-ttu-id="a5bc5-155">Cuando la plantilla requerida esté disponible para la CA, use el siguiente cmdlet de Windows PowerShell en el servidor perimetral para solicitar el certificado:</span><span class="sxs-lookup"><span data-stu-id="a5bc5-155">When the required template is available to the CA, use the following Windows PowerShell cmdlet from at the Edge Server to request the certificate:</span></span>
    
        Request-CsCertificate -New -Type AccessEdgeExternal  -Output C:\ <certfilename.txt or certfilename.csr>  -ClientEku $true -Template <template name>
    
    <span data-ttu-id="a5bc5-156">El nombre de certificado predeterminado de la plantilla proporcionada en Lync Server 2013 es servidor Web.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-156">The default certificate name of the template provided in Lync Server 2013 is Web Server.</span></span> <span data-ttu-id="a5bc5-157">Especifique el nombre \<\> de la plantilla únicamente si necesita usar una plantilla distinta de la predeterminada.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-157">Only specify the \<template name\> if you need to use a template that is different from the default template.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a5bc5-158">Si su organización desea admitir la conectividad de mensajería instantánea pública con AOL, debe usar Windows PowerShell en lugar del asistente de certificados para solicitar que el certificado se asigne al borde externo del servicio perimetral de acceso.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-158">If your organization wants to support public IM connectivity with AOL, you must use Windows PowerShell instead of the Certificate Wizard to request the certificate to be assigned to the external edge for the Access Edge service.</span></span> <span data-ttu-id="a5bc5-159">Esto se debe a que la plantilla de servidor Web de Lync Server 2013 que usa el Asistente para solicitar un certificado no admite la configuración de EKU de cliente.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-159">This is because the Lync Server 2013 Web Server template that the Certificate Wizard uses to request a certificate does not support client EKU configuration.</span></span> <span data-ttu-id="a5bc5-160">Antes de usar Windows PowerShell para crear el certificado, el administrador de la CA debe crear e implementar una nueva plantilla que admita EKU de cliente.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-160">Before using Windows PowerShell to create the certificate, the CA administrator must create and deploy a new template that supports client EKU.</span></span>

    
    </div>

</div>

<div>

## <a name="to-submit-a-request-to-a-public-certification-authority"></a><span data-ttu-id="a5bc5-161">Para enviar una solicitud a una entidad de certificación pública</span><span class="sxs-lookup"><span data-stu-id="a5bc5-161">To submit a request to a public certification authority</span></span>

1.  <span data-ttu-id="a5bc5-162">Abra el archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-162">Open the output file.</span></span>

2.  <span data-ttu-id="a5bc5-163">Copie y pegue el contenido de la solicitud de firma de certificado (CSR).</span><span class="sxs-lookup"><span data-stu-id="a5bc5-163">Copy and paste the contents of the Certificate Signing Request (CSR).</span></span>

3.  <span data-ttu-id="a5bc5-164">Si se le solicita, especifique lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a5bc5-164">If prompted, specify the following:</span></span>
    
      - <span data-ttu-id="a5bc5-165">**Microsoft** como la plataforma de servidor.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-165">**Microsoft** as the server platform.</span></span>
    
      - <span data-ttu-id="a5bc5-166">**IIS** como la versión.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-166">**IIS** as the version.</span></span>
    
      - <span data-ttu-id="a5bc5-167">**Servidor Web** como el tipo de uso.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-167">**Web Server** as the usage type.</span></span>
    
      - <span data-ttu-id="a5bc5-168">**Pkcs7** como formato de respuesta.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-168">**PKCS7** as the response format.</span></span>

4.  <span data-ttu-id="a5bc5-169">Cuando la entidad emisora pública haya verificado su información, recibirá un mensaje de correo electrónico con el texto necesario para su certificado.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-169">When the public CA has verified your information, you will receive an email message containing text required for your certificate.</span></span>

5.  <span data-ttu-id="a5bc5-170">Copie el texto del mensaje de correo electrónico y guarde el contenido en un archivo de texto (. txt) en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-170">Copy the text from the email message and save the contents in a text file (.txt) on your local computer.</span></span>

</div>

<div>

## <a name="to-import-the-certificate-for-the-external-interface-of-the-edge-server"></a><span data-ttu-id="a5bc5-171">Para importar el certificado de la interfaz externa del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="a5bc5-171">To import the certificate for the external interface of the Edge Server</span></span>

1.  <span data-ttu-id="a5bc5-172">Inicie sesión como miembro del grupo administradores en el mismo servidor perimetral en el que creó la solicitud de certificado.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-172">Log on as a member of the Administrators group to the same Edge Server on which you created the certificate request.</span></span>

2.  <span data-ttu-id="a5bc5-173">En el Asistente para la implementación, en la página **implementar servidor perimetral** , junto al **paso 3: solicitar, instalar o asignar certificados**, haga clic en **Ejecutar de nuevo**.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-173">In the Deployment Wizard, on the **Deploy Edge Server** page, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>

3.  <span data-ttu-id="a5bc5-174">En la página **tareas de certificados disponibles** , haga clic en **importar un certificado desde un archivo. p7b, pfx o. cer**.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-174">On the **Available Certificate Tasks** page, click **Import a certificate from a .p7b, pfx or .cer file**.</span></span>

4.  <span data-ttu-id="a5bc5-175">En la página **importar certificado** , haga clic en **examinar** para buscar y seleccionar el certificado que solicitó para la interfaz externa del servidor perimetral (o bien, puede escribir la ruta de acceso completa y el nombre de archivo).</span><span class="sxs-lookup"><span data-stu-id="a5bc5-175">On the **Import Certificate** page, click **Browse** to locate and select the certificate that you requested for the external interface of the Edge Server (or, you can type the full path and file name).</span></span> <span data-ttu-id="a5bc5-176">Si el certificado contiene una clave privada, seleccione **archivo de certificado contiene la clave privada del certificado** y escriba la contraseña de la clave privada.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-176">If the certificate contains a private key, select **Certificate file contains certificate’s private key** and type the password for the private key.</span></span> <span data-ttu-id="a5bc5-177">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-177">Click **Next**.</span></span>

5.  <span data-ttu-id="a5bc5-178">En la página **Resumen de importación de certificado** , revise el Resumen y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-178">On **Import Certificate Summary** page, review the summary and then click **Next**.</span></span>

6.  <span data-ttu-id="a5bc5-179">En **ejecutar comandos**, revise los resultados de la importación, haga clic en **Ver registro** para obtener más información según sea necesario y, a continuación, haga clic en **Finalizar** para completar la importación del certificado.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-179">On **Executing Commands**, review the results of the import, click **View Log** for more information as needed, and then click **Finish** to complete the certificate import.</span></span>

7.  <span data-ttu-id="a5bc5-180">Si está configurando un grupo de servidores perimetrales, exporte el certificado con su clave privada, tal como se describe en el procedimiento "para exportar el certificado con la clave privada para servidores perimetrales en un grupo" más adelante en este tema.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-180">If you are configuring an Edge Server pool, export the certificate with its private key as outlined in the “To export the certificate with the private key for Edge Servers in a pool” procedure later in this topic.</span></span> <span data-ttu-id="a5bc5-181">Copie el archivo de certificado exportado en los otros servidores perimetrales e impórtelo en el almacén de equipos de cada servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-181">Copy the exported certificate file to the other Edge Servers, and import it into the computer store on each Edge Server.</span></span>

</div>

<div>

## <a name="to-export-the-certificate-with-the-private-key-for-edge-servers-in-a-pool"></a><span data-ttu-id="a5bc5-182">Para exportar el certificado con la clave privada para servidores perimetrales en un grupo de servidores</span><span class="sxs-lookup"><span data-stu-id="a5bc5-182">To export the certificate with the private key for Edge Servers in a pool</span></span>

1.  <span data-ttu-id="a5bc5-183">Inicie sesión como miembro del grupo administradores en el mismo servidor perimetral en el que importó el certificado.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-183">Log on as a member of the Administrators group to the same Edge Server on which you imported the certificate.</span></span>

2.  <span data-ttu-id="a5bc5-184">Haga clic en **Inicio**, haga clic en **Ejecutar**y escriba **MMC**.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-184">Click **Start**, click **Run**, and type **MMC**.</span></span>

3.  <span data-ttu-id="a5bc5-185">En la consola de Microsoft Management Console (MMC), haga clic en **archivo**y, a continuación, haga clic en **Agregar o quitar complemento**.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-185">In the Microsoft Management Console (MMC) console, click **File**, and then click **Add/Remove Snap-in**.</span></span>

4.  <span data-ttu-id="a5bc5-186">En **Agregar o quitar complementos**, haga clic en **certificados**y, a continuación, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-186">In **Add or Remove Snap-ins**, click **Certificates**, and then click **Add**.</span></span>

5.  <span data-ttu-id="a5bc5-187">En el cuadro de diálogo **certificados** , seleccione **cuenta de equipo**, haga clic en **siguiente**, seleccione **equipo local: (el equipo en el que se está ejecutando esta consola)** en **seleccionar equipo**, haga clic en **Finalizar** y, a continuación, haga clic en **Aceptar** para completar la configuración de la consola MMC.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-187">In the **Certificates** dialog box, select **Computer account**, click **Next**, select **Local computer: (the computer this console is running on)** in **Select Computer**, click **Finish** and then click **OK** to complete configuration of the MMC console.</span></span>

6.  <span data-ttu-id="a5bc5-188">Haga doble clic en **certificados (equipo local)** para expandir los almacenes de certificados, haga doble clic en **personal**y, a continuación, haga doble clic en **certificados**.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-188">Double-click **Certificates (Local Computer)** to expand the certificate stores, double-click **Personal**, and then double-click **Certificates**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="a5bc5-189">Si no hay certificados en el almacén personal de certificados para el equipo local, no hay ninguna clave privada asociada al certificado que se importó.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-189">If there are no certificates in the Certificates Personal store for the local computer, there is no private key associated with the certificate that was imported.</span></span> <span data-ttu-id="a5bc5-190">Revise los pasos de la solicitud e importar.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-190">Review the request and import steps.</span></span> <span data-ttu-id="a5bc5-191">Si el problema persiste, póngase en contacto con el administrador o el proveedor de su entidad de certificación.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-191">If the problem persists, contact your certification authority administrator or provider.</span></span>

    
    </div>

7.  <span data-ttu-id="a5bc5-192">En el **almacén personal de certificados del equipo local**, haga clic con el botón secundario en el certificado que va a exportar, haga clic en **todas las tareas**y, a continuación, haga clic en **exportar**.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-192">In the **Certificates Personal store for the local computer**, right-click the certificate that you are exporting, click **All Tasks**, and then click **Export**.</span></span>

8.  <span data-ttu-id="a5bc5-193">En el Asistente para exportación de certificados, haga clic en **siguiente**, seleccione **sí, exportar la clave privada**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-193">In the Certificate Export Wizard, click **Next**, select **Yes, export the private key**, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a5bc5-194">Si la selección <STRONG>sí, exportar la clave privada</STRONG> no está disponible, la clave privada asociada a este certificado no se marcó para exportar.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-194">If the selection <STRONG>Yes, export the private key</STRONG> is not available, the private key associated with this certificate was not marked for export.</span></span> <span data-ttu-id="a5bc5-195">Tendrá que volver a solicitar el certificado, lo que garantiza que el certificado estará marcado para permitir la exportación de la clave privada antes de poder continuar con la exportación.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-195">You will need to request the certificate again, ensuring that the certificate is marked to allow for the export of the private key before you can continue with the export.</span></span> <span data-ttu-id="a5bc5-196">Póngase en contacto con el administrador o proveedor de su entidad de certificación.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-196">Contact your certification authority administrator or provider.</span></span>

    
    </div>

9.  <span data-ttu-id="a5bc5-197">En el cuadro de diálogo Exportar formatos de archivo, seleccione **intercambio de\#información personal – PKCS 12 (. PFX)** y, a continuación, seleccione lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a5bc5-197">On the Export File Formats dialog, select **Personal Information Exchange – PKCS\#12 (.PFX)** and then select the following:</span></span>
    
      - <span data-ttu-id="a5bc5-198">Incluir todos los certificados en la ruta de certificación si es posible</span><span class="sxs-lookup"><span data-stu-id="a5bc5-198">Include all certificates in the certification path if possible</span></span>
    
      - <span data-ttu-id="a5bc5-199">Exportar todas las propiedades extendidas</span><span class="sxs-lookup"><span data-stu-id="a5bc5-199">Export all extended properties</span></span>
        
        <div>
        

        > [!WARNING]  
        > <span data-ttu-id="a5bc5-200">Al exportar el certificado desde un servidor perimetral, no seleccione <STRONG>eliminar la clave privada si la exportación es correcta</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-200">When exporting the certificate from an Edge server, do not select <STRONG>Delete the private key if the export is successful</STRONG>.</span></span> <span data-ttu-id="a5bc5-201">Si selecciona esta opción, necesitará importar el certificado y la clave privada a este servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-201">Selecting this option will require that you import the certificate and the private key to this Edge server.</span></span>

        
        </div>

10. <span data-ttu-id="a5bc5-202">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-202">Click **Next**.</span></span>

11. <span data-ttu-id="a5bc5-203">Escriba una contraseña para la clave privada, vuelva a escribir la contraseña para confirmarla y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-203">Type a password for the private key, type the password again to confirm, and then click **Next**.</span></span>

12. <span data-ttu-id="a5bc5-204">Escriba la ruta y el nombre de archivo del certificado exportado, con la extensión de archivo .pfx.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-204">Type a path and file name for the exported certificate, using a file extension of .pfx.</span></span> <span data-ttu-id="a5bc5-205">La ruta de acceso debe ser accesible para todos los demás servidores perimetrales del grupo o disponible para el transporte por medio de medios extraíbles, por ejemplo, una unidad flash USB.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-205">The path must either be accessible to all other Edge servers in the pool or available to transport by means of removable media - for example, a USB flash drive.</span></span> <span data-ttu-id="a5bc5-206">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-206">Click **Next**.</span></span>

13. <span data-ttu-id="a5bc5-207">Revise el resumen en **completar el Asistente para exportación de certificados**y, a continuación, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-207">Review the summary in **Completing the Certificate Export Wizard**, and then click **Finish**.</span></span>

14. <span data-ttu-id="a5bc5-208">En el cuadro de diálogo exportación correcta, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-208">In the successful export dialog box, click **OK**.</span></span>

15. <span data-ttu-id="a5bc5-209">Importe el archivo de certificado exportado a los otros servidores perimetrales siguiendo los pasos indicados en el procedimiento "para importar el certificado de la interfaz externa del servidor perimetral" descrito anteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-209">Import the exported certificate file to the other Edge servers following the steps outlined in the “To import the certificate for the external interface of the Edge Server” procedure earlier in this topic.</span></span>

</div>

<div>

## <a name="to-assign-the-certificate-for-the-external-interface-of-the-edge-server"></a><span data-ttu-id="a5bc5-210">Para asignar el certificado para la interfaz externa del servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="a5bc5-210">To assign the certificate for the external interface of the Edge Server</span></span>

1.  <span data-ttu-id="a5bc5-211">En cada servidor perimetral, en el Asistente para la implementación, junto al **paso 3: solicitar, instalar o asignar certificados**, haga clic en **Ejecutar de nuevo**.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-211">On each Edge Server, in the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>

2.  <span data-ttu-id="a5bc5-212">En la página **tareas de certificados disponibles** , haga clic en **asignar un certificado existente**.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-212">On the **Available Certificate Tasks** page, click **Assign an existing certificate**.</span></span>

3.  <span data-ttu-id="a5bc5-213">En la página **asignación de certificado** , haga clic en certificado de **borde externo** y seleccione la casilla de verificación **uso avanzado de certificados** .</span><span class="sxs-lookup"><span data-stu-id="a5bc5-213">On the **Certificate Assignment** page, click **External Edge Certificate** and select the **Advanced Certificate Usages** check box.</span></span>

4.  <span data-ttu-id="a5bc5-214">En la página **uso de certificados avanzado** , active todas las casillas para asignar el certificado para todos los usos.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-214">On the **Advanced Certificate Usages** page, select all check boxes to assign the certificate for all usages.</span></span>

5.  <span data-ttu-id="a5bc5-215">En la página **almacén de certificados** , seleccione el certificado público que solicitó e importó para la interfaz externa del servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-215">On the **Certificate Store** page, select the public certificate that you requested and imported for the external interface of the Edge Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a5bc5-216">Si el certificado solicitado y importado no está en la lista, uno de los métodos de solución de problemas es comprobar que el nombre del sujeto y el asunto de los nombres alternativos del certificado cumplen con todos los requisitos del certificado y, si ha importado manualmente el la cadena de certificados y certificados en lugar de usar los procedimientos anteriores, que el certificado está en el almacén de certificados correcto (el almacén de certificados del equipo, no el almacén de certificados del usuario o servicio).</span><span class="sxs-lookup"><span data-stu-id="a5bc5-216">If the certificate you requested and imported is not in the list, one of the trouble shooting methods is to verify that subject name and subject alternative names of the certificate meet all requirements for the certificate and, if you manually imported the certificate and certificate chain instead of using the preceding procedures, that the certificate is in the correct certificate store (the computer certificate store, not the user or service certificate store).</span></span>

    
    </div>

6.  <span data-ttu-id="a5bc5-217">En la página **Resumen de asignación de certificado** , revise la configuración y, a continuación, haga clic en **siguiente** para asignar los certificados.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-217">On the **Certificate Assignment Summary** page, review your settings, and then click **Next** to assign the certificates.</span></span>

7.  <span data-ttu-id="a5bc5-218">En la página de finalización del asistente, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-218">On the wizard completion page, click **Finish**.</span></span>

8.  <span data-ttu-id="a5bc5-219">Después de usar este procedimiento para asignar el certificado perimetral, abra el complemento certificado en cada servidor, expanda **certificados (equipo local)**, expanda **personal**, haga clic en **certificados**y, después, compruebe en el panel de detalles que aparece el certificado.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-219">After using this procedure to assign the edge certificate, open the Certificate snap-in on each server, expand **Certificates (Local computer)**, expand **Personal**, click **Certificates**, and then verify in the details pane that the certificate is listed.</span></span>

9.  <span data-ttu-id="a5bc5-220">Si su implementación incluye varios servidores perimetrales, repita este procedimiento para cada servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="a5bc5-220">If your deployment includes multiple Edge Servers, repeat this procedure for each Edge Server.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

