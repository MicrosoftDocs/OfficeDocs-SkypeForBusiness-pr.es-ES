---
title: Configurar la puerta de enlace XMPP en Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure XMPP gateway on Lync Server 2013
ms:assetid: 00777a34-cc36-4992-9459-08c14543ef6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687953(v=OCS.15)
ms:contentKeyID: 49733538
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82c7cec94a65a35f4f5141950c4691fec0b28706
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723200"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-xmpp-gateway-on-lync-server-2013"></a><span data-ttu-id="d97a3-102">Configurar la puerta de enlace XMPP en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d97a3-102">Configure XMPP gateway on Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d97a3-103">_**Última modificación del tema:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="d97a3-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="d97a3-104">Al configurar directivas para la compatibilidad de los socios federados protocolo de presencia y mensajería extensible (XMPP), las directivas se aplican a los usuarios de XMPP Federated Domains, pero no a los usuarios de proveedores de servicios de mensajería instantánea (mi) protocolo de inicio de sesión (SIP) (por ejemplo, Windows Live) o dominios federados de SIP.</span><span class="sxs-lookup"><span data-stu-id="d97a3-104">When you configure policies for support of extensible messaging and presence protocol (XMPP) federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers (for example, Windows Live), or SIP federated domains.</span></span> <span data-ttu-id="d97a3-105">Configure un socio de XMPP federado para cada dominio de XMPP federado que desee permitir a los usuarios que añadan contactos y se comuniquen con ellos.</span><span class="sxs-lookup"><span data-stu-id="d97a3-105">You configure an XMPP Federated Partner for each XMPP federated domain that you want to allow your users to add contacts and communicate with.</span></span> <span data-ttu-id="d97a3-106">Una vez que las directivas están instaladas, las tareas adicionales incluyen la configuración de los certificados de la puerta de enlace XMPP, la implementación de la puerta de enlace XMPP de Lync Server 2013 y, por último, la actualización de los registros DNS para la puerta de enlace XMPP.</span><span class="sxs-lookup"><span data-stu-id="d97a3-106">Once the policies are in place, additional tasks include configuring the XMPP Gateway certificates, deploying the Lync Server 2013 XMPP Gateway, and finally updating the DNS records for the XMPP Gateway.</span></span>

<div>

## <a name="configure-xmpp-gateway-certificates-on-the-lync-server-2013-edge-server"></a><span data-ttu-id="d97a3-107">Configurar certificados de puerta de enlace XMPP en el servidor perimetral 2013 de Lync Server</span><span class="sxs-lookup"><span data-stu-id="d97a3-107">Configure XMPP Gateway Certificates on the Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="d97a3-108">En el servidor perimetral, en el Asistente para la implementación, junto al **paso 3: solicitar, instalar o asignar certificados**, haga clic en **Ejecutar de nuevo**.</span><span class="sxs-lookup"><span data-stu-id="d97a3-108">On the Edge Server, in the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="d97a3-109">Si está implementando el servidor perimetral por primera vez, verá ejecutar en lugar de volver a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="d97a3-109">If you are deploying the Edge Server for the first time, you will see Run instead of Run Again.</span></span>

    
    </div>

2.  <span data-ttu-id="d97a3-110">En la página **Tareas de certificado disponibles**, haga clic en **Crear una nueva solicitud de certificado**.</span><span class="sxs-lookup"><span data-stu-id="d97a3-110">On the **Available Certificate Tasks** page, click **Create a new certificate request**.</span></span>

3.  <span data-ttu-id="d97a3-111">En la página **solicitud de certificado** , haga clic en certificado de **borde externo**.</span><span class="sxs-lookup"><span data-stu-id="d97a3-111">On the **Certificate Request** page, click **External Edge Certificate**.</span></span>

4.  <span data-ttu-id="d97a3-112">En la página **solicitud inmediata o demorada** , active la casilla **preparar la solicitud ahora pero enviarla más tarde** .</span><span class="sxs-lookup"><span data-stu-id="d97a3-112">On the **Delayed or Immediate Request** page, select the **Prepare the request now, but send it later** check box.</span></span>

5.  <span data-ttu-id="d97a3-113">En la **Página archivo de solicitud de certificado** , escriba la ruta de acceso completa y el nombre del archivo en el que se va a guardar la solicitud (por\\ejemplo\_,\_c: CERT la Edge. cer).</span><span class="sxs-lookup"><span data-stu-id="d97a3-113">On the **Certificate Request File** page, type the full path and file name of the file to which the request is to be saved (for example, c:\\cert\_exernal\_edge.cer).</span></span>

6.  <span data-ttu-id="d97a3-114">En la página **especificar plantilla de certificado alternativa** , para usar una plantilla distinta de la plantilla predeterminada de WebServer, seleccione la casilla **Usar plantilla de certificado alternativa para la entidad emisora de certificados seleccionada** .</span><span class="sxs-lookup"><span data-stu-id="d97a3-114">On the **Specify Alternate Certificate Template** page, to use a template other than the default WebServer template, select the **Use alternative certificate template for the selected certification authority** check box.</span></span>

7.  <span data-ttu-id="d97a3-115">En la página **nombre y configuración de seguridad** , haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d97a3-115">On the **Name and Security Settings** page, do the following:</span></span>
    
    1.  <span data-ttu-id="d97a3-116">En **nombre descriptivo**, escriba un nombre para mostrar para el certificado.</span><span class="sxs-lookup"><span data-stu-id="d97a3-116">In **Friendly name**, type a display name for the certificate.</span></span>
    
    2.  <span data-ttu-id="d97a3-117">En **longitud bit**, especifique la longitud en bits (normalmente, el valor predeterminado de 2048).</span><span class="sxs-lookup"><span data-stu-id="d97a3-117">In **Bit length**, specify the bit length (typically, the default of 2048).</span></span>
    
    3.  <span data-ttu-id="d97a3-118">Compruebe que la casilla **marcar clave privada de certificado como exportable** está activada.</span><span class="sxs-lookup"><span data-stu-id="d97a3-118">Verify that the **Mark certificate private key as exportable** check box is selected.</span></span>

8.  <span data-ttu-id="d97a3-119">En la página información de la **organización** , escriba el nombre de la organización y la unidad organizativa (por ejemplo, una división o un departamento).</span><span class="sxs-lookup"><span data-stu-id="d97a3-119">On the **Organization Information** page, type the name for the organization and the organizational unit (for example, a division or department).</span></span>

9.  <span data-ttu-id="d97a3-120">En la página **información geográfica** , especifique la información de ubicación.</span><span class="sxs-lookup"><span data-stu-id="d97a3-120">On the **Geographical Information** page, specify the location information.</span></span>

10. <span data-ttu-id="d97a3-121">En la página **nombre de sujeto/nombres alternativos de asunto** , se muestra la información que el asistente rellenará automáticamente.</span><span class="sxs-lookup"><span data-stu-id="d97a3-121">On the **Subject Name/Subject Alternate Names** page, the information to be automatically populated by the wizard is displayed.</span></span> <span data-ttu-id="d97a3-122">Si se necesitan nombres alternativos adicionales, debe especificarlos en los dos pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="d97a3-122">If additional subject alternative names are needed, you specify them in the next two steps.</span></span>

11. <span data-ttu-id="d97a3-123">En la página **configuración del dominio SIP en la página de nombres alternativos de asunto (San)** , seleccione la casilla dominio para agregar un SIP. \<sipdomain\> entrada a la lista de nombres alternativos de asunto.</span><span class="sxs-lookup"><span data-stu-id="d97a3-123">On the **SIP Domain Setting on Subject Alternate Names (SANs)** page, select the domain check box to add a sip.\<sipdomain\> entry to the subject alternative names list.</span></span>

12. <span data-ttu-id="d97a3-124">En la página **configurar otros nombres alternativos de asunto** , especifique los nombres alternativos adicionales que sean obligatorios.</span><span class="sxs-lookup"><span data-stu-id="d97a3-124">On the **Configure Additional Subject Alternate Names** page, specify any additional subject alternative names that are required.</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="d97a3-125">Si el proxy XMPP está instalado, de forma predeterminada, el nombre de dominio (por ejemplo, contoso.com) se rellena en las entradas SAN.</span><span class="sxs-lookup"><span data-stu-id="d97a3-125">If the XMPP proxy is installed, by default the domain name (such as contoso.com) is populated in the SAN entries.</span></span> <span data-ttu-id="d97a3-126">Si necesita más entradas, agréguelos en este paso.</span><span class="sxs-lookup"><span data-stu-id="d97a3-126">If you require more entries, add them in this step.</span></span>

    
    </div>

13. <span data-ttu-id="d97a3-127">En la página **solicitar Resumen** , revise la información del certificado que se va a usar para generar la solicitud.</span><span class="sxs-lookup"><span data-stu-id="d97a3-127">On the **Request Summary** page, review the certificate information to be used to generate the request.</span></span>

14. <span data-ttu-id="d97a3-128">Cuando termine de ejecutarse los comandos, puede **ver el registro**o hacer clic en **siguiente** para continuar.</span><span class="sxs-lookup"><span data-stu-id="d97a3-128">After the commands finish running, you can **View Log**, or click **Next** to continue.</span></span>

15. <span data-ttu-id="d97a3-129">En la página de **archivo de solicitud de certificado** , puede ver el archivo de solicitud de firma de certificado generado (CSR) haciendo clic en ver o salir del asistente de certificados haciendo clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="d97a3-129">On the **Certificate Request File** page, you can view the generated certificate signing request (CSR) file by clicking View or exit the Certificate Wizard by clicking **Finish**.</span></span>

16. <span data-ttu-id="d97a3-130">Copie el archivo de solicitud y envíelo a la entidad emisora de certificados pública.</span><span class="sxs-lookup"><span data-stu-id="d97a3-130">Copy the request file and submit to your public certification authority.</span></span>

17. <span data-ttu-id="d97a3-131">Después de recibir, importar y asignar el certificado público, debe detener y reiniciar los servicios del servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="d97a3-131">After receiving, importing and assigning the public certificate, you must stop and restart the Edge Server services.</span></span> <span data-ttu-id="d97a3-132">Esto se hace escribiendo en la consola de administración de Lync Server:</span><span class="sxs-lookup"><span data-stu-id="d97a3-132">You do this by typing in the Lync Server Management console:</span></span>
    
       ```console
        Stop-CsWindowsService
       ```
    
       ```console
        Start-CsWindowsService
       ```

</div>

<div>

## <a name="configure-a-new-lync-server-2013-xmpp-gateway"></a><span data-ttu-id="d97a3-133">Configurar una nueva puerta de enlace de Lync Server 2013 XMPP</span><span class="sxs-lookup"><span data-stu-id="d97a3-133">Configure a new Lync Server 2013 XMPP Gateway</span></span>

1.  <span data-ttu-id="d97a3-134">Abra el Panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d97a3-134">Open Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="d97a3-135">En la barra de navegación izquierda, haga clic en **Federación y acceso externo** y, a continuación, haga clic en **XMPP federados**.</span><span class="sxs-lookup"><span data-stu-id="d97a3-135">In the left navigation bar, click **Federation and External Access** and then click **XMPP Federated Partners**.</span></span>

3.  <span data-ttu-id="d97a3-136">Para crear una configuración nueva, haga clic en **nuevo**.</span><span class="sxs-lookup"><span data-stu-id="d97a3-136">To create a new configuration, click **New**.</span></span>

4.  <span data-ttu-id="d97a3-137">Defina la configuración siguiente:</span><span class="sxs-lookup"><span data-stu-id="d97a3-137">Define the following settings:</span></span>

5.  <span data-ttu-id="d97a3-138">**Dominio principal (**     obligatorio).</span><span class="sxs-lookup"><span data-stu-id="d97a3-138">**Primary domain**    (Required).</span></span> <span data-ttu-id="d97a3-139">El dominio principal es el dominio base del socio XMPP.</span><span class="sxs-lookup"><span data-stu-id="d97a3-139">The primary domain is the base domain of the XMPP partner.</span></span> <span data-ttu-id="d97a3-140">Por ejemplo, tendría que escribir **fabrikam.com** para el nombre de dominio del socio XMPP.</span><span class="sxs-lookup"><span data-stu-id="d97a3-140">For example, you would enter **fabrikam.com** for the XMPP partner domain name.</span></span> <span data-ttu-id="d97a3-141">Esta es una entrada obligatoria.</span><span class="sxs-lookup"><span data-stu-id="d97a3-141">This is a required entry.</span></span>

6.  <span data-ttu-id="d97a3-142">**Descripción**   la descripción es para notas u otras informaciones identificativas para esta configuración en particular.</span><span class="sxs-lookup"><span data-stu-id="d97a3-142">**Description**   The description is for notes or other identifying information for this particular configuration.</span></span> <span data-ttu-id="d97a3-143">Esta entrada es opcional.</span><span class="sxs-lookup"><span data-stu-id="d97a3-143">This entry is optional.</span></span>

7.  <span data-ttu-id="d97a3-144">**Dominios adicionales los**   dominios adicionales son dominios que forman parte del dominio del asociado XMPP y que deben incluirse como parte de la comunicación XMPP permitida.</span><span class="sxs-lookup"><span data-stu-id="d97a3-144">**Additional domains**   Additional domains are domains that are a part of your XMPP partner’s domain that should be included as part of the allowed XMPP communication.</span></span> <span data-ttu-id="d97a3-145">Por ejemplo, si el dominio principal es **fabrikam.com**, se mostrarán todos los demás dominios de fabrikam.com con los que se comunicará mediante XMPP.</span><span class="sxs-lookup"><span data-stu-id="d97a3-145">For example, if the primary domain is **fabrikam.com**, then you would list all other domains that are under fabrikam.com that you will communicate with by way of XMPP.</span></span>

8.  <span data-ttu-id="d97a3-146">**Tipo de socio**   el **tipo de socio** es un valor obligatorio.</span><span class="sxs-lookup"><span data-stu-id="d97a3-146">**Partner type**   The **Partner type** is a required setting.</span></span> <span data-ttu-id="d97a3-147">Debe elegir una de las siguientes opciones para describir y exigir qué contactos se pueden agregar.</span><span class="sxs-lookup"><span data-stu-id="d97a3-147">You must choose one of the following to describe and enforce what contacts can be added.</span></span> <span data-ttu-id="d97a3-148">Puede seleccionar:</span><span class="sxs-lookup"><span data-stu-id="d97a3-148">You can select from:</span></span>
    
      - <span data-ttu-id="d97a3-149">**Federado** Un tipo de socio **federado** representa un alto nivel de confianza entre la implementación de Lync Server y el socio XMPP.</span><span class="sxs-lookup"><span data-stu-id="d97a3-149">**Federated** A **Federated** partner type represents a high level of trust between the Lync Server deployment and the XMPP partner.</span></span><span data-ttu-id="d97a3-150">Este tipo de socio es recomendable para la Federación con servidores XMPP dentro de la misma empresa o cuando existe una relación comercial establecida.</span><span class="sxs-lookup"><span data-stu-id="d97a3-150">  This partner type is recommended for federating with XMPP servers within the same enterprise or where there is an established business relationship.</span></span><span data-ttu-id="d97a3-151">Los contactos XMPP de los socios federados pueden:</span><span class="sxs-lookup"><span data-stu-id="d97a3-151">  XMPP contacts in Federated partners can:</span></span>
        
        1.  <span data-ttu-id="d97a3-152">Agregar contactos de Lync y ver su presencia sin autorización expresa por parte del usuario de Lync.</span><span class="sxs-lookup"><span data-stu-id="d97a3-152">Add Lync contacts and view their presence without express authorization from the Lync user.</span></span>
        
        2.  <span data-ttu-id="d97a3-153">Enviar mensajes instantáneos a los contactos de Lync si el usuario de Lync los ha agregado a su lista de contactos.</span><span class="sxs-lookup"><span data-stu-id="d97a3-153">Send instant messages to Lync contacts whether or not the Lync user has added them into their contact list.</span></span>
        
        3.  <span data-ttu-id="d97a3-154">Vea las notas de estado de un usuario de Lync.</span><span class="sxs-lookup"><span data-stu-id="d97a3-154">See a Lync user’s status notes.</span></span>
    
      - <span data-ttu-id="d97a3-155">**Pública verificada** un socio **verificado públicamente** es un proveedor de XMPP público en el que se confía para comprobar la identidad de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="d97a3-155">**Public verified** A **Public verified** partner is a public XMPP provider that is trusted to verify the identity of its users.</span></span><span data-ttu-id="d97a3-156">Los contactos XMPP pueden agregar contactos de Lync y ver su estado de presencia y enviarles mensajes instantáneos sin autorización expresa de los usuarios de Lync.</span><span class="sxs-lookup"><span data-stu-id="d97a3-156">  XMPP contacts in Public Verified networks can add Lync contacts and view their presence and send instant messages to them without express authorization from the Lync users.</span></span><span data-ttu-id="d97a3-157">Los contactos XMPP de las redes públicas verificadas nunca ven las notas de estado de los usuarios de Lync.</span><span class="sxs-lookup"><span data-stu-id="d97a3-157">  XMPP contacts in public verified networks never see a Lync users’ status notes.</span></span><span data-ttu-id="d97a3-158">No se recomienda esta opción.</span><span class="sxs-lookup"><span data-stu-id="d97a3-158">  This setting is not recommended.</span></span>
    
      - <span data-ttu-id="d97a3-159">No se ha **comprobado el público** Un socio **público no verificado** es un proveedor de XMPP público en el que no se confía para comprobar la identidad de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="d97a3-159">**Public unverified** A **Public unverified** partner is a public XMPP provider that is not trusted to verify the identity of its users.</span></span><span data-ttu-id="d97a3-160">Los usuarios XMPP de redes públicas no verificadas no pueden comunicarse con los usuarios de Lync a menos que el usuario de Lync los haya autorizado expresamente agregándolos a la lista de contactos.</span><span class="sxs-lookup"><span data-stu-id="d97a3-160">  XMPP users on Public Unverified networks cannot communicate with Lync users unless the Lync user has expressly authorized them by adding them to the contact list.</span></span><span data-ttu-id="d97a3-161">Los usuarios XMPP de redes públicas sin verificar nunca ven las notas de estado de los usuarios de Lync.</span><span class="sxs-lookup"><span data-stu-id="d97a3-161">  XMPP users on public unverified networks never see Lync users’ status notes.</span></span><span data-ttu-id="d97a3-162">Se recomienda esta opción para cualquier federación con proveedores de XMPP público, como Google Talk.</span><span class="sxs-lookup"><span data-stu-id="d97a3-162">  This setting is recommended for any federation with public XMPP providers such as Google Talk.</span></span>

9.  <span data-ttu-id="d97a3-163">**Tipo de conexión:** Define las diversas reglas y la configuración de Dialback.</span><span class="sxs-lookup"><span data-stu-id="d97a3-163">**Connection Type:** Defines the various rules and dialback settings.</span></span>
    
      - <span data-ttu-id="d97a3-164">**La negociación**   TLS define las reglas de negociación de TLS.</span><span class="sxs-lookup"><span data-stu-id="d97a3-164">**TLS Negotiation**   Defines the TLS negotiation rules.</span></span> <span data-ttu-id="d97a3-165">Un servicio XMPP puede requerir TLS, puede hacer que TLS sea opcional o usted define que no se admite la TLS.</span><span class="sxs-lookup"><span data-stu-id="d97a3-165">An XMPP service can require TLS, can make TLS optional, or you define that TLS is not supported.</span></span> <span data-ttu-id="d97a3-166">Si elige opcional, el requisito quedará en el servicio XMPP para una decisión obligatoria para la negociación.</span><span class="sxs-lookup"><span data-stu-id="d97a3-166">Choosing Optional leaves the requirement up to the XMPP service for a mandatory-to-negotiate decision.</span></span> <span data-ttu-id="d97a3-167">Para ver todas las configuraciones posibles y los detalles de la negociación SASL, TLS y Dialback, incluidas las configuraciones no válidas y de errores conocidos, vea [configuración de la negociación para socios de XMPP federados en Lync Server 2013](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md)</span><span class="sxs-lookup"><span data-stu-id="d97a3-167">To view all possible settings and details for SASL, TLS and Dialback negotiation – including not valid and known error configurations - see [Negotiation settings for XMPP federated partners in Lync Server 2013](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md)</span></span>
        
           - <span data-ttu-id="d97a3-168">**Requerido**   el servicio XMPP requiere la negociación de TLS.</span><span class="sxs-lookup"><span data-stu-id="d97a3-168">**Required**   The XMPP service requires TLS negotiation.</span></span>
        
           - <span data-ttu-id="d97a3-169">**Opcional**   el servicio XMPP indica que TLS es obligatorio para negociar.</span><span class="sxs-lookup"><span data-stu-id="d97a3-169">**Optional**   The XMPP service indicates that TLS is mandatory-to-negotiate.</span></span>
        
           - <span data-ttu-id="d97a3-170">**No admitido**   el servicio XMPP no admite TLS.</span><span class="sxs-lookup"><span data-stu-id="d97a3-170">**Not Supported**   The XMPP service does not support TLS.</span></span>
    
      - <span data-ttu-id="d97a3-171">**La negociación**   SASL define las reglas de negociación de SASL.</span><span class="sxs-lookup"><span data-stu-id="d97a3-171">**SASL negotiation**   Defines the SASL negotiation rules.</span></span> <span data-ttu-id="d97a3-172">Un servicio XMPP puede requerir SASL, puede hacer que SASL sea opcional o usted define que SASL no es compatible.</span><span class="sxs-lookup"><span data-stu-id="d97a3-172">An XMPP service can require SASL, can make SASL optional, or you define that SASL is not supported.</span></span> <span data-ttu-id="d97a3-173">Si elige opcional, el servicio XMPP del socio dejará de ser necesario para una decisión obligatoria para la negociación.</span><span class="sxs-lookup"><span data-stu-id="d97a3-173">Choosing Optional leaves the requirement up to the partner XMPP service for a mandatory-to-negotiate decision.</span></span>
        
           - <span data-ttu-id="d97a3-174">**Requerido**   el servicio XMPP requiere negociación SASL.</span><span class="sxs-lookup"><span data-stu-id="d97a3-174">**Required**   The XMPP service requires SASL negotiation.</span></span>
        
           - <span data-ttu-id="d97a3-175">**Opcional**   el servicio XMPP indica que SASL es obligatorio para negociar.</span><span class="sxs-lookup"><span data-stu-id="d97a3-175">**Optional**   The XMPP service indicates that SASL is mandatory-to-negotiate.</span></span>
        
           - <span data-ttu-id="d97a3-176">**No admitido**   el servicio XMPP no admite SASL.</span><span class="sxs-lookup"><span data-stu-id="d97a3-176">**Not Supported**   The XMPP service does not support SASL.</span></span>
    
      - <span data-ttu-id="d97a3-177">**Soporte de servidor de soporte Dialback negociación** El proceso de negociación del servidor de soporte Dialback usa el sistema de nombres de dominio (DNS) y un servidor autorizado para comprobar que la solicitud procede de un socio XMPP válido.</span><span class="sxs-lookup"><span data-stu-id="d97a3-177">**Support server dialback negotiation** The support server dialback negotiation process uses the domain name system (DNS) and an authoritative server to verify that the request came from a valid XMPP partner.</span></span> <span data-ttu-id="d97a3-178">Para ello, el servidor de origen crea un mensaje de un tipo específico con una clave de Dialback generada y busca el servidor de recepción en DNS.</span><span class="sxs-lookup"><span data-stu-id="d97a3-178">To do this, the originating server creates a message of a specific type with a generated dialback key and looks up the receiving server in DNS.</span></span> <span data-ttu-id="d97a3-179">El servidor de origen envía la clave en una secuencia XML a la búsqueda DNS resultante, supuestamente el servidor de recepción.</span><span class="sxs-lookup"><span data-stu-id="d97a3-179">The originating server sends the key in an XML stream to the resulting DNS lookup, presumably the receiving server.</span></span> <span data-ttu-id="d97a3-180">Al recibir la clave sobre la secuencia XML, el servidor de recepción no responde al servidor de origen, pero envía la clave a un servidor conocido de autorización.</span><span class="sxs-lookup"><span data-stu-id="d97a3-180">On receipt of the key over the XML stream, the receiving server does not respond to the originating server, but sends the key to a known authoritative server.</span></span> <span data-ttu-id="d97a3-181">El servidor autorizado verifica que la clave sea válida o no válida.</span><span class="sxs-lookup"><span data-stu-id="d97a3-181">The authoritative server verifies that the key is either valid or not valid.</span></span> <span data-ttu-id="d97a3-182">Si no es válido, el servidor de recepción no responde al servidor de origen.</span><span class="sxs-lookup"><span data-stu-id="d97a3-182">If not valid, the receiving server does not respond to the originating server.</span></span> <span data-ttu-id="d97a3-183">Si la clave es válida, el servidor receptor informa al servidor de origen de que la identidad y la clave son válidas y que la conversación puede comenzar.</span><span class="sxs-lookup"><span data-stu-id="d97a3-183">If the key is valid, the receiving server informs the originating server that the identity and key is valid and the conversation can commence.</span></span>
        
        <span data-ttu-id="d97a3-184">Existen dos Estados válidos para la **negociación de Dialback**:</span><span class="sxs-lookup"><span data-stu-id="d97a3-184">There are two valid states for **Dialback negotiation**:</span></span>
        
           - <span data-ttu-id="d97a3-185">**True**   : el servidor XMPP está configurado para usar la negociación de Dialback si se debe recibir una solicitud de un servidor de origen.</span><span class="sxs-lookup"><span data-stu-id="d97a3-185">**True**   The XMPP server is configured to use Dialback negotiation if a request should be received from an originating server.</span></span>
        
           - <span data-ttu-id="d97a3-186">**False**   el servidor XMPP no está configurado para usar la negociación de Dialback y, si se debe recibir una solicitud de un servidor de origen, se pasará por alto.</span><span class="sxs-lookup"><span data-stu-id="d97a3-186">**False**   The XMPP server is not configured to use Dialback negotiation and if a request should be received from an originating server, it will be ignored.</span></span>

10. <span data-ttu-id="d97a3-187">Haga clic en **confirmar** para guardar los cambios en el sitio o en la Directiva de usuario.</span><span class="sxs-lookup"><span data-stu-id="d97a3-187">Click **Commit** to save your changes to the site or user policy.</span></span>

</div>

<div>

## <a name="update-dns-records-for-lync-server-2013-xmpp-gateway"></a><span data-ttu-id="d97a3-188">Actualizar registros DNS para Lync Server 2013 puerta de enlace XMPP</span><span class="sxs-lookup"><span data-stu-id="d97a3-188">Update DNS Records for Lync Server 2013 XMPP Gateway</span></span>

1.  <span data-ttu-id="d97a3-189">Para configurar DNS para la Federación XMPP, agregue el siguiente registro SRV a su DNS externo:\_XMPP-Server. \_TCP. \<nombre\> de dominio el registro SRV se resolverá en el FQDN perimetral de acceso del servidor perimetral, con un valor de puerto de 5269.</span><span class="sxs-lookup"><span data-stu-id="d97a3-189">To configure DNS for XMPP federation, you add the following SRV record to your external DNS:\_xmpp-server.\_tcp.\<domain name\> The SRV record will resolve to the Access Edge FQDN of the Edge server, with a port value of 5269.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

