---
title: Configurar la puerta de enlace XMPP en Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure XMPP gateway on Lync Server 2013
ms:assetid: c70282e0-b502-47e2-a0be-a32eb1faf99d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721881(v=OCS.15)
ms:contentKeyID: 49733816
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 30dc21ddbbfd5d65d6834ffa5a6181c5e4a13b1c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503187"
---
# <a name="configure-xmpp-gateway-on-lync-server-2013"></a><span data-ttu-id="19fd1-102">Configurar la puerta de enlace XMPP en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="19fd1-102">Configure XMPP gateway on Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="19fd1-103">_**Última modificación del tema:** 2013-10-28_</span><span class="sxs-lookup"><span data-stu-id="19fd1-103">_**Topic Last Modified:** 2013-10-28_</span></span>

<span data-ttu-id="19fd1-104">Los últimos pasos para migrar la puerta de enlace XMPP son configurar certificados para el servidor perimetral de Lync Server 2013, implementar la puerta de enlace XMPP de Lync Server 2013 y actualizar los registros DNS para la puerta de enlace XMPP.</span><span class="sxs-lookup"><span data-stu-id="19fd1-104">The final steps for migrating your XMPP Gateway are to configure certificates for the Lync Server 2013 Edge Server, deploy the Lync Server 2013 XMPP Gateway, and update the DNS records for the XMPP Gateway.</span></span> <span data-ttu-id="19fd1-105">Estos pasos deben realizarse paralelamente para minimizar el tiempo de inactividad de la puerta de enlace XMPP.</span><span class="sxs-lookup"><span data-stu-id="19fd1-105">These steps should be performed in parallel to minimize the down time of your XMPP Gateway.</span></span> <span data-ttu-id="19fd1-106">Es necesario mover todos los usuarios a la implementación de Microsoft Lync Server 2013 antes de realizar estos pasos.</span><span class="sxs-lookup"><span data-stu-id="19fd1-106">All users must be moved to your Microsoft Lync Server 2013 deployment before performing these steps.</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="19fd1-107">La Federación de XMPP no es compatible con los usuarios hospedados en aplicaciones de sucursal con funciones de supervivencia.</span><span class="sxs-lookup"><span data-stu-id="19fd1-107">XMPP federation is not supported for users who are homed on survivable branch appliances.</span></span> <span data-ttu-id="19fd1-108">Esto se aplica a ver la información de presencia y a intercambiar mensajes de mensajería instantánea.</span><span class="sxs-lookup"><span data-stu-id="19fd1-108">This applies to both seeing presence information and exchanging IM messages.</span></span>



</div>

<div>

## <a name="configure-xmpp-gateway-certificates-on-the-lync-server-2013-edge-server"></a><span data-ttu-id="19fd1-109">Configurar los certificados de la puerta de enlace XMPP en el servidor perimetral de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="19fd1-109">Configure XMPP Gateway Certificates on the Lync Server 2013 Edge Server</span></span>

1.  <span data-ttu-id="19fd1-110">En el servidor perimetral, en el Asistente para la implementación, junto al **Paso 3: Solicitar, instalar o asignar certificados**, haga clic en **Ejecutar de nuevo**.</span><span class="sxs-lookup"><span data-stu-id="19fd1-110">On the Edge Server, in the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="19fd1-111">Si es la primera vez que implementa el servidor perimetral, aparecerá Ejecutar en lugar de Ejecutar de nuevo.</span><span class="sxs-lookup"><span data-stu-id="19fd1-111">If you are deploying the Edge Server for the first time, you will see Run instead of Run Again.</span></span>

    
    </div>

2.  <span data-ttu-id="19fd1-112">En la página **Tareas de certificado disponibles**, haga clic en **Crear una nueva solicitud de certificado**.</span><span class="sxs-lookup"><span data-stu-id="19fd1-112">On the **Available Certificate Tasks** page, click **Create a new certificate request**.</span></span>

3.  <span data-ttu-id="19fd1-113">En la página **Solicitud de certificado**, haga clic en **Certificado perimetral externo**.</span><span class="sxs-lookup"><span data-stu-id="19fd1-113">On the **Certificate Request** page, click **External Edge Certificate**.</span></span>

4.  <span data-ttu-id="19fd1-114">En la página **Solicitud retrasada o inmediata**, active la casilla **Prepare ahora la solicitud, pero enviarla más tarde**.</span><span class="sxs-lookup"><span data-stu-id="19fd1-114">On the **Delayed or Immediate Request** page, select the **Prepare the request now, but send it later** check box.</span></span>

5.  <span data-ttu-id="19fd1-115">En la página **archivo de solicitud de certificado** , escriba la ruta de acceso completa y el nombre de archivo del archivo en el que se va a guardar la solicitud (por ejemplo, c: \\ CERT \_ externos \_ Edge. cer).</span><span class="sxs-lookup"><span data-stu-id="19fd1-115">On the **Certificate Request File** page, type the full path and file name of the file to which the request is to be saved (for example, c:\\cert\_exernal\_edge.cer).</span></span>

6.  <span data-ttu-id="19fd1-116">En la página **Especificar plantilla de certificado alternativa**, para usar una plantilla distinta a la plantilla predeterminada WebServer, active la casilla **Usar plantilla de certificado alternativa para la entidad de certificación seleccionada**.</span><span class="sxs-lookup"><span data-stu-id="19fd1-116">On the **Specify Alternate Certificate Template** page, to use a template other than the default WebServer template, select the **Use alternative certificate template for the selected certification authority** check box.</span></span>

7.  <span data-ttu-id="19fd1-117">En la página **Nombre y configuración de seguridad**, siga este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="19fd1-117">On the **Name and Security Settings** page, do the following:</span></span>
    
    1.  <span data-ttu-id="19fd1-118">En **Nombre descriptivo**, escriba un nombre para mostrar para el certificado.</span><span class="sxs-lookup"><span data-stu-id="19fd1-118">In **Friendly name**, type a display name for the certificate.</span></span>
    
    2.  <span data-ttu-id="19fd1-119">En **Longitud de bits**, especifique la longitud de bits (normalmente, el valor predeterminado es 2048).</span><span class="sxs-lookup"><span data-stu-id="19fd1-119">In **Bit length**, specify the bit length (typically, the default of 2048).</span></span>
    
    3.  <span data-ttu-id="19fd1-120">Compruebe que la casilla **Marcar la clave privada del certificado como exportable** esté seleccionada.</span><span class="sxs-lookup"><span data-stu-id="19fd1-120">Verify that the **Mark certificate private key as exportable** check box is selected.</span></span>

8.  <span data-ttu-id="19fd1-121">En la página **Información de la organización**, escriba un nombre para la organización y la unidad organizativa (por ejemplo, una división o departamento).</span><span class="sxs-lookup"><span data-stu-id="19fd1-121">On the **Organization Information** page, type the name for the organization and the organizational unit (for example, a division or department).</span></span>

9.  <span data-ttu-id="19fd1-122">En la página **Información geográfica**, escriba la información de ubicación.</span><span class="sxs-lookup"><span data-stu-id="19fd1-122">On the **Geographical Information** page, specify the location information.</span></span>

10. <span data-ttu-id="19fd1-p103">En la página **Nombre de sujeto/nombres alternativos de sujeto**, la información se rellenará automáticamente gracias al asistente que se muestra. Si necesita otros nombres alternativos de sujeto, especifíquelos en los dos pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="19fd1-p103">On the **Subject Name/Subject Alternate Names** page, the information to be automatically populated by the wizard is displayed. If additional subject alternative names are needed, you specify them in the next two steps.</span></span>

11. <span data-ttu-id="19fd1-125">En la página **configuración de dominio SIP en nombres alternativos de sujeto (San)** , active la casilla de verificación dominio para agregar un SIP.\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="19fd1-125">On the **SIP Domain Setting on Subject Alternate Names (SANs)** page, select the domain check box to add a sip.\<sipdomain\></span></span> <span data-ttu-id="19fd1-126">entrada a la lista de nombres alternativos de sujeto.</span><span class="sxs-lookup"><span data-stu-id="19fd1-126">entry to the subject alternative names list.</span></span>

12. <span data-ttu-id="19fd1-127">En la página **Configurar nombres alternativos de sujeto adicionales**, especifique cualquier nombre alternativo del firmante adicional que necesite.</span><span class="sxs-lookup"><span data-stu-id="19fd1-127">On the **Configure Additional Subject Alternate Names** page, specify any additional subject alternative names that are required.</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="19fd1-p105">Si el proxy de XMPP está instalado, las entradas SAN se cumplimentan de forma predeterminada con el nombre de dominio (por ejemplo, contoso.com). Si necesita más entradas, agréguelas en este paso.</span><span class="sxs-lookup"><span data-stu-id="19fd1-p105">If the XMPP proxy is installed, by default the domain name (such as contoso.com) is populated in the SAN entries. If you require more entries, add them in this step.</span></span>

    
    </div>

13. <span data-ttu-id="19fd1-130">En la página **Resumen de la solicitud**, revise la información del certificado que va a usar para generar la solicitud.</span><span class="sxs-lookup"><span data-stu-id="19fd1-130">On the **Request Summary** page, review the certificate information to be used to generate the request.</span></span>

14. <span data-ttu-id="19fd1-131">Una vez que los comandos terminen de ejecutarse, puede **Ver el registro** o hacer clic en Siguiente para continuar.</span><span class="sxs-lookup"><span data-stu-id="19fd1-131">After the commands finish running, you can **View Log**, or click Next to continue.</span></span>

15. <span data-ttu-id="19fd1-132">En la página **Archivo de solicitud de certificados**, puede ver el archivo de solicitud de firma de certificado (CSR) que se ha generado. Para ello, haga clic en **Ver** o haga clic en **Finalizar** para salir del Asistente para certificados.</span><span class="sxs-lookup"><span data-stu-id="19fd1-132">On the **Certificate Request File** page, you can view the generated certificate signing request (CSR) file by clicking **View** or exit the Certificate Wizard by clicking **Finish**.</span></span>

16. <span data-ttu-id="19fd1-133">Copie el archivo de solicitud y envíelo a la entidad de certificación pública.</span><span class="sxs-lookup"><span data-stu-id="19fd1-133">Copy the request file and submit to your public certification authority.</span></span>

17. <span data-ttu-id="19fd1-p106">Después de recibir, importar y asignar el certificado público, debe detener y reiniciar los servicios del servidor perimetral. Para ello, escriba en la consola de administración de Lync Server:</span><span class="sxs-lookup"><span data-stu-id="19fd1-p106">After receiving, importing and assigning the public certificate, you must stop and restart the Edge Server services. You do this by typing in the Lync Server Management console:</span></span>
    
        Stop-CsWindowsService

      &nbsp;
    
        Start-CsWindowsService

</div>

<div>

## <a name="configure-a-new-lync-server-2013-xmpp-gateway"></a><span data-ttu-id="19fd1-136">Configurar una nueva puerta de enlace XMPP de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="19fd1-136">Configure a new Lync Server 2013 XMPP Gateway</span></span>

1.  <span data-ttu-id="19fd1-137">Abra Panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="19fd1-137">Open Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="19fd1-138">En el barra de navegación izquierda, haga clic en **Federación y acceso externo** y en **Socios federados de XMPP**.</span><span class="sxs-lookup"><span data-stu-id="19fd1-138">In the left navigation bar, click **Federation and External Access** and then click **XMPP Federated Partners**.</span></span>

3.  <span data-ttu-id="19fd1-139">Para crear una configuración, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="19fd1-139">To create a new configuration, click **New**.</span></span>

4.  <span data-ttu-id="19fd1-140">Defina la configuración siguiente:</span><span class="sxs-lookup"><span data-stu-id="19fd1-140">Define the following settings:</span></span>

5.  <span data-ttu-id="19fd1-141">**Dominio principal**     (Obligatorio).</span><span class="sxs-lookup"><span data-stu-id="19fd1-141">**Primary domain**    (Required).</span></span> <span data-ttu-id="19fd1-142">El dominio principal es el dominio base del socio XMPP.</span><span class="sxs-lookup"><span data-stu-id="19fd1-142">The primary domain is the base domain of the XMPP partner.</span></span> <span data-ttu-id="19fd1-143">Por ejemplo, escriba **fabrikam.com** en el nombre de dominio del socio XMPP.</span><span class="sxs-lookup"><span data-stu-id="19fd1-143">For example, you would enter **fabrikam.com** for the XMPP partner domain name.</span></span> <span data-ttu-id="19fd1-144">Esta es una entrada obligatoria.</span><span class="sxs-lookup"><span data-stu-id="19fd1-144">This is a required entry.</span></span>

6.  <span data-ttu-id="19fd1-145">**Descripción**     La descripción es para notas u otra información de identificación para esta configuración específica.</span><span class="sxs-lookup"><span data-stu-id="19fd1-145">**Description**   The description is for notes or other identifying information for this particular configuration.</span></span> <span data-ttu-id="19fd1-146">Este campo es opcional.</span><span class="sxs-lookup"><span data-stu-id="19fd1-146">This entry is optional.</span></span>

7.  <span data-ttu-id="19fd1-147">**Dominios adicionales**     Los dominios adicionales son dominios que forman parte del dominio del socio XMPP y que deben incluirse como parte de la comunicación de XMPP permitida.</span><span class="sxs-lookup"><span data-stu-id="19fd1-147">**Additional domains**   Additional domains are domains that are a part of your XMPP partner’s domain that should be included as part of the allowed XMPP communication.</span></span> <span data-ttu-id="19fd1-148">Por ejemplo, si el dominio principal es **fabrikam.com**, se enumerará el resto de los dominios por debajo de fabrikam.com con los que se comunicará por medio de XMPP.</span><span class="sxs-lookup"><span data-stu-id="19fd1-148">For example, if the primary domain is **fabrikam.com**, then you would list all other domains that are under fabrikam.com that you will communicate with by way of XMPP.</span></span>

8.  <span data-ttu-id="19fd1-149">**Tipo**     de socio El **tipo de socio** es un valor obligatorio.</span><span class="sxs-lookup"><span data-stu-id="19fd1-149">**Partner type**   The **Partner type** is a required setting.</span></span> <span data-ttu-id="19fd1-150">Debe elegir uno de los siguientes para describir y aplicar los contactos que pueden agregarse.</span><span class="sxs-lookup"><span data-stu-id="19fd1-150">You must choose one of the following to describe and enforce what contacts can be added.</span></span> <span data-ttu-id="19fd1-151">Puede seleccionar entre:</span><span class="sxs-lookup"><span data-stu-id="19fd1-151">You can select from:</span></span>
    
      - <span data-ttu-id="19fd1-152">**Federado**     Un tipo de socio **federado** representa un alto nivel de confianza entre la implementación de Lync Server y el socio XMPP.</span><span class="sxs-lookup"><span data-stu-id="19fd1-152">**Federated**   A **Federated** partner type represents a high level of trust between the Lync Server deployment and the XMPP partner.</span></span><span data-ttu-id="19fd1-153">Este tipo socio es aconsejable para federarse con los servidores de XMPP en la misma empresa o si hay una relación comercial establecida.</span><span class="sxs-lookup"><span data-stu-id="19fd1-153">  This partner type is recommended for federating with XMPP servers within the same enterprise or where there is an established business relationship.</span></span><span data-ttu-id="19fd1-154">Los contactos de XMPP en los socios federados pueden:</span><span class="sxs-lookup"><span data-stu-id="19fd1-154">  XMPP contacts in Federated partners can:</span></span>
        
        1.  <span data-ttu-id="19fd1-155">Agregar los contactos de Lync y ver su presencia sin autorización expresa del usuario de Lync.</span><span class="sxs-lookup"><span data-stu-id="19fd1-155">Add Lync contacts and view their presence without express authorization from the Lync user.</span></span>
        
        2.  <span data-ttu-id="19fd1-156">Enviar mensajes instantáneos a los contactos de Lync con independencia de que el usuario de Lync los haya agregado a su lista de contactos.</span><span class="sxs-lookup"><span data-stu-id="19fd1-156">Send instant messages to Lync contacts whether or not the Lync user has added them into their contact list.</span></span>
        
        3.  <span data-ttu-id="19fd1-157">Ver las notas de estado del usuario de Lync.</span><span class="sxs-lookup"><span data-stu-id="19fd1-157">See a Lync user’s status notes.</span></span>
    
      - <span data-ttu-id="19fd1-158">**Comprobada pública**     Un socio **comprobado público** es un proveedor de XMPP público en el que se confía para comprobar la identidad de sus usuarios.</span><span class="sxs-lookup"><span data-stu-id="19fd1-158">**Public verified**   A **Public verified** partner is a public XMPP provider that is trusted to verify the identity of its users.</span></span><span data-ttu-id="19fd1-159">Los contactos de XMPP en las redes públicas verificadas pueden agregar contactos de Lync, ver su presencia y enviarles mensajes instantáneos sin autorización expresa de los usuarios de Lync.</span><span class="sxs-lookup"><span data-stu-id="19fd1-159">  XMPP contacts in Public Verified networks can add Lync contacts and view their presence and send instant messages to them without express authorization from the Lync users.</span></span><span data-ttu-id="19fd1-160">Los contactos de XMPP de las redes públicas verificadas no pueden ver las notas de estado de los usuarios de Lync.</span><span class="sxs-lookup"><span data-stu-id="19fd1-160">  XMPP contacts in public verified networks never see a Lync users’ status notes.</span></span><span data-ttu-id="19fd1-161">Este valor no se recomienda.</span><span class="sxs-lookup"><span data-stu-id="19fd1-161">  This setting is not recommended.</span></span>
    
      - <span data-ttu-id="19fd1-162">No **comprobados públicos**     Un socio no **comprobado público** es un proveedor de XMPP público que no es de confianza para comprobar la identidad de sus usuarios.</span><span class="sxs-lookup"><span data-stu-id="19fd1-162">**Public unverified**   A **Public unverified** partner is a public XMPP provider that is not trusted to verify the identity of its users.</span></span><span data-ttu-id="19fd1-163">Los usuarios de XMPP de las redes públicas no verificadas solo pueden comunicarse con los usuarios de Lync si estos lo han autorizado expresamente y los han agregado a su lista de contactos.</span><span class="sxs-lookup"><span data-stu-id="19fd1-163">  XMPP users on Public Unverified networks cannot communicate with Lync users unless the Lync user has expressly authorized them by adding them to the contact list.</span></span><span data-ttu-id="19fd1-164">Los usuarios de XMPP de las redes públicas no verificadas no pueden ver las notas de estado de los usuarios de Lync.</span><span class="sxs-lookup"><span data-stu-id="19fd1-164">  XMPP users on public unverified networks never see Lync users’ status notes.</span></span><span data-ttu-id="19fd1-165">Este valor no se recomienda para las federaciones con proveedores de XMPP públicos, como Google Talk.</span><span class="sxs-lookup"><span data-stu-id="19fd1-165">  This setting is recommended for any federation with public XMPP providers such as Google Talk.</span></span>

9.  <span data-ttu-id="19fd1-166">**Tipo de conexión:** define las diversas reglas y valores de rellamada.</span><span class="sxs-lookup"><span data-stu-id="19fd1-166">**Connection Type:** Defines the various rules and dialback settings.</span></span>
    
      - <span data-ttu-id="19fd1-167">**Negociación TLS**     Define las reglas de negociación de TLS.</span><span class="sxs-lookup"><span data-stu-id="19fd1-167">**TLS Negotiation**   Defines the TLS negotiation rules.</span></span> <span data-ttu-id="19fd1-168">Un servicio de XMPP puede requerir TLS, determinar que TLS es opcional o definir que TLS no se admite.</span><span class="sxs-lookup"><span data-stu-id="19fd1-168">An XMPP service can require TLS, can make TLS optional, or you define that TLS is not supported.</span></span> <span data-ttu-id="19fd1-169">Si se opta por la posibilidad opcional, es el servicio de XMPP quien decide si la negociación es obligatoria.</span><span class="sxs-lookup"><span data-stu-id="19fd1-169">Choosing Optional leaves the requirement up to the XMPP service for a mandatory-to-negotiate decision.</span></span> <span data-ttu-id="19fd1-170">Para ver todos los valores y detalles posibles para la negociación de SASL, TLS y devolución, incluidas las configuraciones de error conocidas y no válidas, vea [configuración de la negociación para socios federados XMPP en Lync Server 2013](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md).</span><span class="sxs-lookup"><span data-stu-id="19fd1-170">To view all possible settings and details for SASL, TLS and Dialback negotiation –including not valid and known error configurations - see [Negotiation settings for XMPP federated partners in Lync Server 2013](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md).</span></span>
        
          - <span></span>  
            <span data-ttu-id="19fd1-171">**Es necesario**     El servicio XMPP requiere negociación TLS.</span><span class="sxs-lookup"><span data-stu-id="19fd1-171">**Required**   The XMPP service requires TLS negotiation.</span></span>
        
          - <span></span>  
            <span data-ttu-id="19fd1-172">**Opcional**     El servicio XMPP indica que TLS es de negociación obligatoria.</span><span class="sxs-lookup"><span data-stu-id="19fd1-172">**Optional**   The XMPP service indicates that TLS is mandatory-to-negotiate.</span></span>
        
          - <span></span>  
            <span data-ttu-id="19fd1-173">**No se admite**     El servicio XMPP no admite TLS.</span><span class="sxs-lookup"><span data-stu-id="19fd1-173">**Not Supported**   The XMPP service does not support TLS.</span></span>
    
      - <span data-ttu-id="19fd1-174">**Negociación SASL**     Define las reglas de negociación de SASL.</span><span class="sxs-lookup"><span data-stu-id="19fd1-174">**SASL negotiation**   Defines the SASL negotiation rules.</span></span> <span data-ttu-id="19fd1-175">Un servicio de XMPP puede requerir SASL, determinar que SASL sea opcional o definir que SASL no se admite.</span><span class="sxs-lookup"><span data-stu-id="19fd1-175">An XMPP service can require SASL, can make SASL optional, or you define that SASL is not supported.</span></span> <span data-ttu-id="19fd1-176">Si se opta por la posibilidad opcional, es el servicio de XMPP de socio quien decide si la negociación es obligatoria.</span><span class="sxs-lookup"><span data-stu-id="19fd1-176">Choosing Optional leaves the requirement up to the partner XMPP service for a mandatory-to-negotiate decision.</span></span>
        
          - <span></span>  
            <span data-ttu-id="19fd1-177">**Es necesario**     El servicio XMPP requiere negociación SASL.</span><span class="sxs-lookup"><span data-stu-id="19fd1-177">**Required**   The XMPP service requires SASL negotiation.</span></span>
        
          - <span></span>  
            <span data-ttu-id="19fd1-178">**Opcional**     El servicio XMPP indica que SASL es de negociación obligatoria.</span><span class="sxs-lookup"><span data-stu-id="19fd1-178">**Optional**   The XMPP service indicates that SASL is mandatory-to-negotiate.</span></span>
        
          - <span></span>  
            <span data-ttu-id="19fd1-179">**No se admite**     El servicio XMPP no admite SASL.</span><span class="sxs-lookup"><span data-stu-id="19fd1-179">**Not Supported**   The XMPP service does not support SASL.</span></span>
    
      - <span data-ttu-id="19fd1-180">**Servidor de soporte devolución negociación** El proceso de negociación del servidor de soporte devolución usa el sistema de nombres de dominio (DNS) y un servidor autorizado para comprobar que la solicitud procede de un socio de XMPP válido.</span><span class="sxs-lookup"><span data-stu-id="19fd1-180">**Support server dialback negotiation** The support server dialback negotiation process uses the domain name system (DNS) and an authoritative server to verify that the request came from a valid XMPP partner.</span></span> <span data-ttu-id="19fd1-181">Para ello, el servidor de origen crea un mensaje de un tipo específico con una clave de rellamada y busca al servidor en el DNS.</span><span class="sxs-lookup"><span data-stu-id="19fd1-181">To do this, the originating server creates a message of a specific type with a generated dialback key and looks up the receiving server in DNS.</span></span> <span data-ttu-id="19fd1-182">El servidor de origen envía la clave en un flujo XML al resultado de la búsqueda de DNS, en principio, el servidor destinatario.</span><span class="sxs-lookup"><span data-stu-id="19fd1-182">The originating server sends the key in an XML stream to the resulting DNS lookup, presumably the receiving server.</span></span> <span data-ttu-id="19fd1-183">A recibir la clave por el flujo XML, el servidor destinatario no responde al servidor de origen, sino que envía la clave a un servidor de autorización conocido.</span><span class="sxs-lookup"><span data-stu-id="19fd1-183">On receipt of the key over the XML stream, the receiving server does not respond to the originating server, but sends the key to a known authoritative server.</span></span> <span data-ttu-id="19fd1-184">Este verifica que la validez de la clave.</span><span class="sxs-lookup"><span data-stu-id="19fd1-184">The authoritative server verifies that the key is either valid or not valid.</span></span> <span data-ttu-id="19fd1-185">Si no lo es, el servidor destinatario no responde al servidor de origen.</span><span class="sxs-lookup"><span data-stu-id="19fd1-185">If not valid, the receiving server does not respond to the originating server.</span></span> <span data-ttu-id="19fd1-186">Si lo es, el servidor destinatario informa al servidor de origen de que la identidad y la clave son válidas, y la conversación puede iniciarse.</span><span class="sxs-lookup"><span data-stu-id="19fd1-186">If the key is valid, the receiving server informs the originating server that the identity and key is valid and the conversation can commence.</span></span>
        
        <span data-ttu-id="19fd1-187">Existen dos estados válidos en la **negociación de rellamada**:</span><span class="sxs-lookup"><span data-stu-id="19fd1-187">There are two valid states for **Dialback negotiation**:</span></span>
        
          - <span></span>  
            <span data-ttu-id="19fd1-188">**True**     El servidor XMPP está configurado para usar la negociación de devolución si se debe recibir una solicitud de un servidor de origen.</span><span class="sxs-lookup"><span data-stu-id="19fd1-188">**True**   The XMPP server is configured to use Dialback negotiation if a request should be received from an originating server.</span></span>
        
          - <span></span>  
            <span data-ttu-id="19fd1-189">**False**     El servidor XMPP no está configurado para usar la negociación de devolución y si se debe recibir una solicitud de un servidor de origen, se ignorará.</span><span class="sxs-lookup"><span data-stu-id="19fd1-189">**False**   The XMPP server is not configured to use Dialback negotiation and if a request should be received from an originating server, it will be ignored.</span></span>

10. <span data-ttu-id="19fd1-190">Haga clic en **Confirmar** para guardar los cambios en la directiva de sitio o usuario.</span><span class="sxs-lookup"><span data-stu-id="19fd1-190">Click **Commit** to save your changes to the site or user policy.</span></span>

</div>

<div>

## <a name="update-dns-records-for-lync-server-2013-xmpp-gateway"></a><span data-ttu-id="19fd1-191">Actualizar los registros de DNS para la puerta de enlace XMPP de Lync server 2013</span><span class="sxs-lookup"><span data-stu-id="19fd1-191">Update DNS Records for Lync Server 2013 XMPP Gateway</span></span>

1.  <span data-ttu-id="19fd1-192">Para configurar DNS para la Federación XMPP, agregue el siguiente registro SRV a su DNS externo: \_ XMPP-Server. \_ TPC.\<domain name\></span><span class="sxs-lookup"><span data-stu-id="19fd1-192">To configure DNS for XMPP federation, you add the following SRV record to your external DNS:\_xmpp-server.\_tcp.\<domain name\></span></span> <span data-ttu-id="19fd1-193">El registro SRV se resolverá en el FQDN perimetral de acceso del servidor perimetral, con un valor de puerto de 5269.</span><span class="sxs-lookup"><span data-stu-id="19fd1-193">The SRV record will resolve to the Access Edge FQDN of the Edge server, with a port value of 5269.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

