---
title: 'Lync Server 2013: configurar certificados para servidores'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure certificates for servers
ms:assetid: e12e59b5-a146-4859-86ec-cabfc198c7b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398995(v=OCS.15)
ms:contentKeyID: 48185531
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3556c9147ddf2769e6a403de9e31edf31129d796
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205066"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-certificates-for-servers-in-lync-server-2013"></a><span data-ttu-id="a578c-102">Configurar certificados para servidores en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a578c-102">Configure certificates for servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a578c-103">_**Última modificación del tema:** 2013-03-17_</span><span class="sxs-lookup"><span data-stu-id="a578c-103">_**Topic Last Modified:** 2013-03-17_</span></span>

<span data-ttu-id="a578c-104">Para completar correctamente este procedimiento, debe haber iniciado sesión como un usuario miembro del grupo RTCUniversalServerAdmins o tener los permisos correctos delegados.</span><span class="sxs-lookup"><span data-stu-id="a578c-104">To successfully complete this procedure you should be logged on as a user who is a member of the RTCUniversalServerAdmins group or have the correct permissions delegated.</span></span> <span data-ttu-id="a578c-105">Para obtener más información sobre cómo delegar permisos, consulte [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="a578c-105">For details about delegating permissions, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span> <span data-ttu-id="a578c-106">Es probable que deba pertenecer a otros grupos en función de su organización y los requisitos para solicitar certificados.</span><span class="sxs-lookup"><span data-stu-id="a578c-106">Depending on your organization and requirements for requesting certificates, you may require other group memberships.</span></span> <span data-ttu-id="a578c-107">Consúltelo con el grupo que administra la entidad de certificación de la infraestructura de clave pública (PKI).</span><span class="sxs-lookup"><span data-stu-id="a578c-107">Consult with the group that manages your public key infrastructure (PKI) certification authority (CA).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a578c-108">Lync Server 2013 incluye compatibilidad con la serie SHA-2 (SHA-2, que usa longitudes implícitas de 224, 256, 384 o 512 bits) de algoritmos hash y de firma de compendio para conexiones de clientes que ejecutan Windows 7, Windows Server 2008 R2, Windows Server 2008, Windows Vista o Sistemas operativos Windows XP, además de Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="a578c-108">Lync Server 2013 includes support for the SHA-2 suite (SHA-2 uses digest lengths of 224, 256, 384 or 512 bits) of digest hash and signing algorithms for connections from clients running the Windows 7, Windows Server 2008 R2, Windows Server 2008, Windows Vista, or Windows XP operating systems, in addition to Lync Phone Edition.</span></span> <span data-ttu-id="a578c-109">Para admitir el acceso externo mediante el conjunto de aplicaciones SHA-2, el certificado externo lo emite una entidad de certificación pública que también puede emitir un certificado con el mismo Resumen de longitud de bits.</span><span class="sxs-lookup"><span data-stu-id="a578c-109">To support external access using the SHA-2 suite, the external certificate is issued by a public CA that also can issue a certificate with the same bit length digest.</span></span>



</div>

<div>


> [!WARNING]  
> <span data-ttu-id="a578c-110">La selección de qué algoritmo de firma y Resumen de hash depende de los clientes y los servidores que usarán el certificado, y de otros equipos y dispositivos con los que los clientes y servidores se comunicarán con quién también debe saber cómo usar los algoritmos que se usan en el emisor.</span><span class="sxs-lookup"><span data-stu-id="a578c-110">The selection of which hash digest and signing algorithm is dependent on the clients and the servers that will use the certificate, and other computers and devices that clients and servers will communicate with who must also know how to use the algorithms used in the certificate.</span></span> <span data-ttu-id="a578c-111">Para obtener información sobre qué longitudes de síntesis son compatibles en el sistema operativo y en algunas<A href="https://go.microsoft.com/fwlink/?linkid=287002">https://go.microsoft.com/fwlink/?LinkId=287002</A>aplicaciones cliente, consulte.</span><span class="sxs-lookup"><span data-stu-id="a578c-111">For information on which digest lengths are supported in the operating system and some client applications, see<A href="https://go.microsoft.com/fwlink/?linkid=287002">https://go.microsoft.com/fwlink/?LinkId=287002</A>.</span></span>



</div>

<span data-ttu-id="a578c-112">Cada servidor Standard Edition o servidor front-end requiere hasta cuatro certificados: el certificado oAuthTokenIssuer, un certificado predeterminado, un certificado Web interno y un certificado externo Web.</span><span class="sxs-lookup"><span data-stu-id="a578c-112">Each Standard Edition server or Front End Server requires up to four certificates: the oAuthTokenIssuer certificate, a default certificate, a web internal certificate, and a web external certificate.</span></span> <span data-ttu-id="a578c-113">No obstante, es posible solicitar y asignar un solo certificado predeterminado con las entradas de nombre alternativo de sujeto apropiadas, así como con el certificado oAuthTokenIssuer.</span><span class="sxs-lookup"><span data-stu-id="a578c-113">However, it is possible to request and assign a single default certificate with appropriate subject alternative name entries as well as the oAuthTokenIssuer certificate.</span></span> <span data-ttu-id="a578c-114">Para obtener más información sobre los requisitos de certificado, consulte [requisitos de certificados para servidores internos en Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md).</span><span class="sxs-lookup"><span data-stu-id="a578c-114">For details about the certificate requirements, see [Certificate requirements for internal servers in Lync Server 2013](lync-server-2013-certificate-requirements-for-internal-servers.md).</span></span> <span data-ttu-id="a578c-115">Para obtener más información sobre cómo solicitar, asignar e instalar el certificado oAuthTokenIssuer, consulte [Managing Server-to-Server Authentication (OAuth) and Partner Applications in Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)</span><span class="sxs-lookup"><span data-stu-id="a578c-115">For details about requesting, assigning and installing the oAuthTokenIssuer certificate, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)</span></span>

<span data-ttu-id="a578c-116">Use el siguiente procedimiento para solicitar, asignar e instalar los certificados de servidor Standard Edition o front-end.</span><span class="sxs-lookup"><span data-stu-id="a578c-116">Use the following procedure to request, assign, and install the Standard Edition server or Front End Server certificates.</span></span> <span data-ttu-id="a578c-117">Repita el procedimiento para cada servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="a578c-117">Repeat the procedure for each Front End Server.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="a578c-118">En el siguiente procedimiento se describe cómo configurar certificados desde una PKI de empresa interna implementada por su organización y sin necesidad de conexión para procesar solicitudes.</span><span class="sxs-lookup"><span data-stu-id="a578c-118">The following procedure describes how to configure certificates from an internal enterprise PKI deployed by your organization and with offline request processing.</span></span> <span data-ttu-id="a578c-119">Para obtener información sobre cómo obtener certificados de una entidad de certificación pública, consulte <A href="lync-server-2013-certificate-requirements-for-internal-servers.md">requisitos de certificados para servidores internos en Lync Server 2013</A> en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="a578c-119">For information about obtaining certificates from a public CA, see <A href="lync-server-2013-certificate-requirements-for-internal-servers.md">Certificate requirements for internal servers in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="a578c-120">Además, este procedimiento describe cómo solicitar, asignar e instalar certificados durante la configuración del servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="a578c-120">Also, this procedure describes how to request, assign, and install certificates during set up of the Front End Server.</span></span> <span data-ttu-id="a578c-121">Si ha solicitado certificados por adelantado, tal como se describe en la sección <A href="lync-server-2013-request-certificates-in-advance-optional.md">solicitar certificados de antemano (opcional) para Lync Server 2013</A> de esta documentación de implementación, o no usa una PKI de empresa interna implementada en la organización para obtener certificados, debe modificar este procedimiento según corresponda.</span><span class="sxs-lookup"><span data-stu-id="a578c-121">If you requested certificates in advance, as described in the <A href="lync-server-2013-request-certificates-in-advance-optional.md">Request certificates in advance (optional) for Lync Server 2013</A> section of this Deployment documentation, or you do not use an internal enterprise PKI deployed in your organization to obtain certificates, you must modify this procedure as appropriate.</span></span>



</div>

<div>

## <a name="to-configure-certificates-for-a-front-end-server"></a><span data-ttu-id="a578c-122">Para configurar certificados para un servidor front-end</span><span class="sxs-lookup"><span data-stu-id="a578c-122">To configure certificates for a Front End Server</span></span>

1.  <span data-ttu-id="a578c-123">En el Asistente para la implementación de Lync Server, haga clic en **Ejecutar** junto al **paso 3: solicitar, instalar o asignar certificados**.</span><span class="sxs-lookup"><span data-stu-id="a578c-123">In the Lync Server Deployment Wizard, click **Run** next to **Step 3: Request, Install or Assign Certificates**.</span></span>

2.  <span data-ttu-id="a578c-124">En la página **Asistente para certificados**, haga clic en **Solicitud**.</span><span class="sxs-lookup"><span data-stu-id="a578c-124">On the **Certificate Wizard** page, click **Request**.</span></span>

3.  <span data-ttu-id="a578c-125">En la página **Solicitud de certificado**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="a578c-125">On the **Certificate Request** page, click **Next**.</span></span>

4.  <span data-ttu-id="a578c-p107">En la página **Solicitudes retrasadas o inmediatas**, acepte la opción predeterminada **Envíe la solicitud inmediatamente a una entidad de certificación en línea** haciendo clic en **Siguiente**. La CA interna con inscripción en línea automática debe estar disponible si selecciona esta opción. Si elige la opción para retrasar la solicitud, se le pedirá un nombre y una ubicación para guardar el archivo de solicitud de certificado. La solicitud de certificado debe ser presentada y procesada por una CA de su organización o bien por una CA pública. Después, tendrá que importar la respuesta de certificado y asignarla al rol de certificado apropiado.</span><span class="sxs-lookup"><span data-stu-id="a578c-p107">On the **Delayed or Immediate Requests** page, you can accept the default **Send the request immediately to an online certification authority** option by clicking **Next**. The internal CA with automatic online enrollment must be available if you select this option. If you choose the option to delay the request, you will be prompted for a name and location to save the certificate request file. The certificate request must be presented and processed by a CA either inside your organization, or by a public CA. You will then need to import the certificate response and assign it to the proper certificate role.</span></span>

5.  <span data-ttu-id="a578c-131">En la página elegir una entidad de certificación **(CA)** , seleccione la opción **seleccionar una entidad de certificación de la lista detectada en el entorno** y, a continuación, seleccione una entidad de certificación conocida (mediante registro en los servicios de dominio de Active Directory) de la lista.</span><span class="sxs-lookup"><span data-stu-id="a578c-131">On the **Choose a Certificate Authority (CA)** page, select the **Select a CA from the list detected in your environment** option, and then select a known (through registration in Active Directory Domain Services) CA from the list.</span></span> <span data-ttu-id="a578c-132">O bien, seleccione la opción **Especificar otra entidad de certificación**, escriba el nombre de otra CA en el cuadro y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="a578c-132">Or, select the **Specify another certification authority** option, enter the name of another CA in the box, and then click **Next**.</span></span>

6.  <span data-ttu-id="a578c-p109">En la página **Cuenta de entidad de certificación**, se solicitan sus credenciales para solicitar y procesar la solicitud de certificado en la CA. Debe haber determinado si es necesario un nombre de usuario y una contraseña para solicitar un certificado por adelantado. Su administrador de CA tendrá la información necesaria y es posible que deba ayudarle en este paso. Si tiene que especificar credenciales alternativas, seleccione la casilla, escriba un nombre de usuario y una contraseña en los cuadros de texto y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="a578c-p109">On the **Certificate Authority Account** page, you are prompted for credentials to request and process the certificate request at the CA. You should have determined if a user name and password is necessary to request a certificate in advance. Your CA administrator will have the required information and may have to assist you in this step. If you need to supply alternate credentials, select the check box, provide a user name and password in the text boxes, and then click **Next**.</span></span>

7.  <span data-ttu-id="a578c-137">En la página **Especificar plantilla de certificado alternativa**, haga clic en **Siguiente** para usar la plantilla de servidor web predeterminada.</span><span class="sxs-lookup"><span data-stu-id="a578c-137">On the **Specify Alternate Certificate Template** page, to use the default Web Server template, click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a578c-p110">Si su organización ha creado una plantilla para usar como alternativa a la plantilla de la CA de servidor web predeterminada, seleccione la casilla y escriba el nombre de la plantilla alternativa. Necesitará el nombre de la plantilla definido por el administrador de CA.</span><span class="sxs-lookup"><span data-stu-id="a578c-p110">If your organization has created a template for use as an alternative for the default Web server CA template, select the check box, and then enter the name of the alternate template. You will need the template name as defined by the CA administrator.</span></span>

    
    </div>

8.  <span data-ttu-id="a578c-p111">En la página **Nombre y configuración de seguridad**, especifique un **Solo nombre** que debe permitirle identificar el certificado y el propósito. Si lo deja en blanco, se generará un nombre automáticamente. Establezca la **Longitud en bits** de la clave o acepte el valor predeterminado de 2048 bits. Active la casilla **Marcar la clave privada del certificado como exportable** si determina que el certificado y la clave privada deben moverse o copiarse a otros sistemas y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="a578c-p111">On the **Name and Security Settings** page, specify a **Friendly Name** that should allow you to identify the certificate and purpose. If you leave it blank, a name will be generated automatically. Set the **Bit length** of the key, or accept the default of 2048 bits. Select the **Mark the certificate’s private key as exportable** if you determine that the certificate and private key needs to be moved or copied to other systems, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a578c-144">Lync Server 2013 tiene requisitos mínimos para una clave privada exportable.</span><span class="sxs-lookup"><span data-stu-id="a578c-144">Lync Server 2013 has minimal requirements for an exportable private key.</span></span> <span data-ttu-id="a578c-145">Uno de estos sitios se encuentra en los servidores perimetrales en un grupo de servidores, donde el servicio de autenticación relé multimedia usa copias del certificado, en lugar de certificados individuales para cada instancia en el grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="a578c-145">One such place is on the Edge Servers in a pool, where the Media Relay Authentication Service uses copies of the certificate, rather than individual certificates for each instance in the pool.</span></span>

    
    </div>

9.  <span data-ttu-id="a578c-146">En la página **Información de la organización**, si lo desea, proporcione información de la organización y después haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="a578c-146">On the **Organization Information** page, optionally provide organization information, and then click **Next**.</span></span>

10. <span data-ttu-id="a578c-147">En la página **Información geográfica**, si lo desea, escriba información geográfica y después haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="a578c-147">On the **Geographical Information** page, optionally provide geographical information, and then click **Next**.</span></span>

11. <span data-ttu-id="a578c-148">En la página **Nombre del sujeto o nombres alternativos del sujeto**, revise los nombres alternativos del sujeto que se van a agregar y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="a578c-148">On the **Subject Name / Subject Alternate Names** page, review the subject alternative names that will be added, and then click **Next**.</span></span>

12. <span data-ttu-id="a578c-149">En la página **Configuración del dominio SIP**, active la casilla **Dominio SIP** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="a578c-149">On the **SIP Domain setting** page, select the **SIP Domain**, and then click **Next**.</span></span>

13. <span data-ttu-id="a578c-150">En la página **Configurar nombres alternativos de sujeto adicionales**, agregue los nombres alternativos de sujeto adicionales que desee, incluido cualquiera que piense que puede ser necesario para dominios SIP adicionales en el futuro, y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="a578c-150">On the **Configure Additional Subject Alternate Names** page, add any additional required subject alternative names, including any that might be required for additional SIP domains in the future, and then click **Next**.</span></span>

14. <span data-ttu-id="a578c-p113">En la página **Resumen de la solicitud de certificados**, revise la información del resumen. Si la información es correcta, haga clic en **Siguiente**. Si necesita corregir o modificar una configuración, haga clic en **Atrás** para ir a la página pertinente y realizar la corrección o modificación.</span><span class="sxs-lookup"><span data-stu-id="a578c-p113">On the **Certificate Request Summary** page, review the information in the summary. If the information is correct, click **Next**. If you need to correct or modify a setting, click **Back** to the proper page to make the correction or modification.</span></span>

15. <span data-ttu-id="a578c-154">En la página **Ejecución de comandos**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="a578c-154">On the **Executing Commands** page, click **Next**.</span></span>

16. <span data-ttu-id="a578c-155">En la página **Estado de solicitud del certificado en línea**, revise la información devuelta.</span><span class="sxs-lookup"><span data-stu-id="a578c-155">On the **Online Certificate Request Status** page, review the information returned.</span></span> <span data-ttu-id="a578c-156">Tenga en cuenta que el certificado se emitió e instaló en el almacén de certificados local.</span><span class="sxs-lookup"><span data-stu-id="a578c-156">You should note that the certificate was issued and installed into the local certificate store.</span></span> <span data-ttu-id="a578c-157">Si se informa de que se ha emitido e instalado, pero que no es válido, asegúrese de que el certificado raíz de la CA se haya instalado en el almacén de CA raíz de confianza del servidor.</span><span class="sxs-lookup"><span data-stu-id="a578c-157">If it is reported as having been issued and installed, but is not valid, make sure that the CA root certificate has been installed in the server’s Trusted Root CA store.</span></span> <span data-ttu-id="a578c-158">Consulte la documentación de la CA para obtener información sobre cómo recuperar un certificado de CA de raíz de confianza.</span><span class="sxs-lookup"><span data-stu-id="a578c-158">Refer to your CA documentation on how to retrieve a Trusted Root CA certificate.</span></span> <span data-ttu-id="a578c-159">Si necesita ver el certificado recuperado, haga clic en **Ver detalles del certificado**.</span><span class="sxs-lookup"><span data-stu-id="a578c-159">If you need to view the retrieved certificate, click **View Certificate Details**.</span></span> <span data-ttu-id="a578c-160">La casilla **Asignar este certificado a los usos de certificado de Lync Server** está activada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="a578c-160">By default, the check box for **Assign the certificate to Lync Server certificate usages** is checked.</span></span> <span data-ttu-id="a578c-161">Si desea asignar manualmente el certificado, active la casilla y haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="a578c-161">If you want to manually assign the certificate, clear the check box, and then click **Finish**.</span></span>

17. <span data-ttu-id="a578c-p115">Si ha activado la casilla **Asignar este certificado a los usos de certificado de Lync Server** en la página anterior, aparecerá la página **Asignación del certificado**. Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="a578c-p115">If you cleared the check box for **Assign the certificate to Lync Server certificate usages** on the previous page, you will be presented with the **Certificate Assignment** page. Click **Next**.</span></span>

18. <span data-ttu-id="a578c-p116">En la página **Almacén de certificados**, seleccione el certificado solicitado. Si desea ver el certificado, haga clic en **Ver detalles del certificado** y en **Siguiente** para continuar.</span><span class="sxs-lookup"><span data-stu-id="a578c-p116">On the **Certificate Store** page, select the certificate that you requested. If you want to view the certificate, click **View Certificate Details**, and then click **Next** to continue.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a578c-p117">Si en la página <STRONG>Estado de solicitud del certificado en línea</STRONG> se ha notificado algún problema con el certificado, como que el certificado no es válido, ver el certificado real puede resultarle de ayuda para resolver el problema. Dos problemas específicos que pueden hacer que un certificado no sea válido son que falte el certificado de CA de raíz de confianza mencionado anteriormente o que falte una clave privada asociada con el certificado. Consulte la documentación de su CA para resolver estos dos problemas.</span><span class="sxs-lookup"><span data-stu-id="a578c-p117">If the <STRONG>Online Certificate Request Status</STRONG> page reported an issue with the certificate, such as the certificate not being valid, viewing the actual certificate can assist in resolving the issue. Two specific issues that can cause a certificate to not be valid is the previously mentioned missing Trusted Root CA certificate, and a missing private key that is associated with the certificate. Refer to your CA documentation to resolve these two issues.</span></span>

    
    </div>

19. <span data-ttu-id="a578c-169">En la página **Resumen de asignación de certificados** , revise la información que se presenta para asegurarse de que este sea el certificado que debe asignarse y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="a578c-169">On the **Certificate Assignment Summary** page, review the information presented to make sure that this is the certificate that should be assigned, and then click **Next**.</span></span>

20. <span data-ttu-id="a578c-p118">En la página **Ejecutando comandos**, revise el resultado del comando. Haga clic en **Ver registro** si desea revisar el proceso de asignación o si se ha emitido algún error o advertencia. Cuando termine, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="a578c-p118">On the **Executing Commands** page, review the output of the command. Click **View Log** if you want to review the assignment process or if there was an error or warning issued. When you are finished with your review, click **Finish**.</span></span>

21. <span data-ttu-id="a578c-173">En la página **Asistente para certificados**, compruebe que el **Estado** del certificado sea “Asignado” y haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="a578c-173">On the **Certificate Wizard** page, verify that the **Status** of the certificate is “Assigned,” and then click **Close**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a578c-174">Consulta también</span><span class="sxs-lookup"><span data-stu-id="a578c-174">See Also</span></span>


[<span data-ttu-id="a578c-175">Requisitos de infraestructura de certificados para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a578c-175">Certificate infrastructure requirements for Lync Server 2013</span></span>](lync-server-2013-certificate-infrastructure-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

