---
title: 'Lync Server 2013: configurar certificados para la interfaz perimetral interna'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set up certificates for the internal edge interface
ms:assetid: a1963cc9-87c5-4935-86c0-6bedc6afd0ac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412750(v=OCS.15)
ms:contentKeyID: 48184949
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c34e1d0d4e87bffbf28ba600ab23d849fd664423
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182193"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="set-up-certificates-for-the-internal-edge-interface-in-lync-server-2013"></a><span data-ttu-id="52693-102">Configurar certificados para la interfaz perimetral interna en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52693-102">Set up certificates for the internal edge interface in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="52693-103">_**Última modificación del tema:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="52693-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="52693-104">Al ejecutar el Asistente para certificados, asegúrese de que ha iniciado sesión usando una cuenta que es miembro de un grupo con los permisos asignados adecuados para el tipo de plantilla de certificado que use.</span><span class="sxs-lookup"><span data-stu-id="52693-104">When you run the Certificate Wizard, ensure that you are logged in using an account that is a member of a group that has been assigned the appropriate permissions for the type of certificate template you will use.</span></span> <span data-ttu-id="52693-105">De forma predeterminada, una solicitud de certificado 2013 de Lync Server usará la plantilla de certificado del servidor Web.</span><span class="sxs-lookup"><span data-stu-id="52693-105">By default, a Lync Server 2013 certificate request will use the Web Server certificate template.</span></span> <span data-ttu-id="52693-106">Si usa una cuenta que es miembro del grupo RTCUniversalServerAdmins para solicitar un certificado usando esta plantilla, compruebe que el grupo tenga asignados los permisos Inscribir necesarios para usar la plantilla.</span><span class="sxs-lookup"><span data-stu-id="52693-106">If you use an account that is a member of the RTCUniversalServerAdmins group to request a certificate using this template, verify that the group has been assigned the Enroll permissions required to use that template.</span></span>



</div>

<span data-ttu-id="52693-p102">En la interfaz interna de cada servidor perimetral se necesita un único certificado. Estos certificados pueden ser emitidos por una entidad de certificación (CA) de empresa interna o por una CA pública. Si su organización tiene una CA interna implementada, puede ahorrarse el gasto que supone usar certificados públicos mediante el uso de la CA interna para emitir el certificado para la interfaz interna. Puede usar una CA interna de Windows Server 2008 o una CA de Windows Server 2008 R2 para crear estos certificados.</span><span class="sxs-lookup"><span data-stu-id="52693-p102">A single certificate is required on the internal interface of each Edge Server. Certificates for the internal interface can be issued by an internal enterprise certification authority (CA) or a public CA. If your organization has an internal CA deployed you can save on the expense of using public certificates by using the internal CA to issue the certificate for the internal interface. You can use an internal Windows Server 2008 CA or Windows Server 2008 R2 CA to create these certificates.</span></span>

<span data-ttu-id="52693-111">Para obtener más información sobre este y otros requisitos de certificado, consulte [requisitos de certificados para el acceso de usuarios externos en Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="52693-111">For details about this and other certificate requirements, see [Certificate requirements for external user access in Lync Server 2013](lync-server-2013-certificate-requirements-for-external-user-access.md).</span></span>

<span data-ttu-id="52693-112">Para definir certificados en la interfaz perimetral interna en un sitio, siga los procedimientos descritos en esta sección para hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="52693-112">To set up certificates on the internal edge interface at a site, use the procedures in this section to do the following:</span></span>

1.  <span data-ttu-id="52693-113">Descargue la cadena de certificación de CA para la interfaz interna en cada servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="52693-113">Download the CA certification chain for the internal interface to each Edge Server.</span></span>

2.  <span data-ttu-id="52693-114">Importe la cadena de certificación de CA para la interfaz interna en cada servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="52693-114">Import the CA certification chain for the internal interface, on each Edge Server.</span></span>

3.  <span data-ttu-id="52693-115">Cree la solicitud de certificado para la interfaz interna en un servidor perimetral, denominado primer servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="52693-115">Create the certificate request for the internal interface, on one Edge Server, called the first Edge Server.</span></span>

4.  <span data-ttu-id="52693-116">Importe el certificado para la interfaz interna en el primer servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="52693-116">Import the certificate for the internal interface on the first Edge Server.</span></span>

5.  <span data-ttu-id="52693-117">Importe el certificado en los demás servidores perimetrales de este sitio (o en los servidores implementados detrás del equilibrador de carga).</span><span class="sxs-lookup"><span data-stu-id="52693-117">Import the certificate on the other Edge Servers at this site (or deployed behind this load balancer).</span></span>

6.  <span data-ttu-id="52693-118">Asigne el certificado para la interfaz interna de cada servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="52693-118">Assign the certificate for the internal interface of every Edge Server.</span></span>

<span data-ttu-id="52693-119">Si tiene más de un sitio con servidores perimetrales (es decir, una topología perimetral de varios sitios) o distintos conjuntos de servidores perimetrales implementados detrás de diferentes equilibradores de carga, debe seguir estos pasos en cada sitio que tenga servidores perimetrales y en cada conjunto de servidores perimetrales implementados detrás de un equilibrador de carga diferente.</span><span class="sxs-lookup"><span data-stu-id="52693-119">If you have more than one site with Edge Servers (that is, a multiple-site edge topology), or separate sets of Edge Servers deployed behind different load balancers, you need to follow these steps for each site that has Edge Servers, and for each set of Edge Servers deployed behind a different load balancer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="52693-120">Los pasos de los procedimientos descritos en esta sección se basan en el&nbsp;uso de una CA de&nbsp;Windows&nbsp;Server 2008, Windows Server 2008 R2 CA, Windows server 2012 CA o Windows Server 2012 R2 CA para crear un certificado para cada servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="52693-120">The steps for procedures in this section are based on using a Windows Server&nbsp;2008 CA, Windows Server&nbsp;2008&nbsp;R2 CA, Windows Server 2012 CA, or Windows Server 2012 R2 CA to create a certificate for each Edge Server.</span></span> <span data-ttu-id="52693-121">Para obtener instrucciones detalladas sobre cómo usar cualquier otra CA, vea la documentación relacionada.</span><span class="sxs-lookup"><span data-stu-id="52693-121">For step-by-step guidance for any other CA, consult the documentation for that CA.</span></span> <span data-ttu-id="52693-122">De forma predeterminada, todos los usuarios autenticados tienen los derechos de usuario adecuados para solicitar certificados.</span><span class="sxs-lookup"><span data-stu-id="52693-122">By default, all authenticated users have the appropriate user rights to request certificates.</span></span><BR><span data-ttu-id="52693-p104">Los procedimientos descritos en esta sección se basan en la creación de solicitudes de certificado en el servidor perimetral como parte del proceso de implementación de servidores perimetrales. Es posible crear solicitudes de certificado mediante el servidor front-end. Puede usarlo para completar la solicitud de certificado antes de lo previsto en el proceso de planeación e implementación, antes de iniciar la implementación de los servidores perimetrales. Para ello, asegúrese de que el certificado que solicite pueda exportarse con una clave privada.</span><span class="sxs-lookup"><span data-stu-id="52693-p104">The procedures in this section are based on creating certificate requests on the Edge Server as part of the Edge Server deployment process. It is possible to create certificate requests using the Front End Server. You can do this to complete the certificate request early in the planning and deployment process, before you start deployment of the Edge Servers. To do this, you must ensure that the certificate you request is defined with an exportable private key.</span></span><BR><span data-ttu-id="52693-p105">En los procedimientos descritos en esta sección se usa un archivo .cer y un archivo .p7b para el certificado. Si usa un tipo de archivo distinto, modifique los procedimientos de la forma pertinente.</span><span class="sxs-lookup"><span data-stu-id="52693-p105">The procedures in this section describe using a .cer and a .p7b file for the certificate. If you use a different type of file, modify these procedures as appropriate.</span></span>



</div>

<div>

## <a name="to-download-the-ca-certification-chain-for-the-internal-interface-using-certsrv-web-site"></a><span data-ttu-id="52693-129">Para descargar la cadena de certificación de CA de la interfaz interna mediante el sitio web certsrv</span><span class="sxs-lookup"><span data-stu-id="52693-129">To download the CA certification chain for the internal interface using certsrv Web site</span></span>

1.  <span data-ttu-id="52693-130">Inicie sesión en un servidor de Lync Server 2013 en la red interna (es decir, no en el servidor perimetral) como miembro del grupo de **administradores** .</span><span class="sxs-lookup"><span data-stu-id="52693-130">Log on to an Lync Server 2013 server in the internal network (that is, not the Edge Server) as a member of the **Administrators** group.</span></span>

2.  <span data-ttu-id="52693-131">Ejecute el comando siguiente en el símbolo del sistema; para ello, haga clic en **Inicio**, en **Ejecutar** y escriba:</span><span class="sxs-lookup"><span data-stu-id="52693-131">Run the following command at a command prompt by clicking **Start**, clicking **Run**, and then typing the following:</span></span>
    
        https://<name of your Issuing CA Server>/certsrv
    
    <span data-ttu-id="52693-132">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="52693-132">For example:</span></span>
    
        https://ca01.contoso.net/certsrv
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="52693-133">Si usa una CA de empresa de Windows Server 2008 o Windows Server 2008 R2, debe usar https, en lugar de http.</span><span class="sxs-lookup"><span data-stu-id="52693-133">If you are using a Windows Server 2008 or Windows Server 2008 R2 enterprise CA, you must use https, not http.</span></span>

    
    </div>

3.  <span data-ttu-id="52693-134">En la página web certsrv de la CA que emite el certificado, en **Seleccione una tarea**, haga clic en **Descargar certificado de CA, cadena de certificados o CRL**.</span><span class="sxs-lookup"><span data-stu-id="52693-134">On the issuing CA’s certsrv web page, under **Select a task**, click **Download a CA certificate, certificate chain, or CRL**.</span></span>

4.  <span data-ttu-id="52693-135">En **Descargar certificado de CA, cadena de certificados o CRL**, haga clic en **Descargar cadena de certificados de CA**.</span><span class="sxs-lookup"><span data-stu-id="52693-135">Under **Download a CA Certificate, Certificate Chain, or CRL**, click **Download CA certificate chain**.</span></span>

5.  <span data-ttu-id="52693-136">En el cuadro de diálogo **Descarga de archivos**, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="52693-136">In the **File Download** dialog box, click **Save**.</span></span>

6.  <span data-ttu-id="52693-137">Guarde el archivo .p7b en el disco duro del servidor y, a continuación, cópielo en una carpeta en cada servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="52693-137">Save the .p7b file to the hard disk drive on the server, and then copy it to a folder on each Edge Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="52693-p106">El archivo .p7b contiene todos los certificados que figuran en la ruta de certificación. Para ver la ruta de certificación, abra el certificado de servidor y haga clic en la ruta de certificación.</span><span class="sxs-lookup"><span data-stu-id="52693-p106">The .p7b file contains all of the certificates that are in the certification path. To view the certification path, open the server certificate and click the certification path.</span></span>

    
    </div>

</div>

<div>

## <a name="to-export-the-ca-certification-chain-for-the-internal-interface-using-mmc"></a><span data-ttu-id="52693-140">Para exportar la cadena de certificación de CA de la interfaz interna mediante MMC</span><span class="sxs-lookup"><span data-stu-id="52693-140">To export the CA certification chain for the internal interface using MMC</span></span>

1.  <span data-ttu-id="52693-141">Puede exportar el certificado raíz de la entidad de certificación desde cualquier equipo unido a un dominio mediante Microsoft Management Console (MMC).</span><span class="sxs-lookup"><span data-stu-id="52693-141">You can export the CA root certificate from any domain joined machine using the Microsoft Management Console (MMC).</span></span> <span data-ttu-id="52693-142">Haga clic en **Inicio**, elija **Ejecutar** y escriba **MMC**.</span><span class="sxs-lookup"><span data-stu-id="52693-142">Click **Start**, click **Run**, and then type **MMC**.</span></span>

2.  <span data-ttu-id="52693-143">En la consola MMC, haga clic en **Archivo** y en **Agregar o quitar**.</span><span class="sxs-lookup"><span data-stu-id="52693-143">In the MMC console, click **File**, click **Add/Remove**.</span></span>

3.  <span data-ttu-id="52693-p108">En la lista del cuadro de diálogo **Agregar o quitar complemento**, seleccione **Certificados** y luego haga clic en **Agregar**. Cuando se le indique, seleccione **Cuenta de equipo**. En el cuadro de diálogo **Seleccionar equipo**, seleccione **Equipo local**. Haga clic en **Finalizar**. Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="52693-p108">From the **Add or Remove Snap-ins** dialog list, select **Certificates**, then click **Add**. When prompted, select **Computer Account**. On the **Select Computer** dialog, select **Local Computer**. Click **Finish**. Click **OK**.</span></span>

4.  <span data-ttu-id="52693-p109">Expanda **Certificados (equipo local)**. Expanda **Entidades de certificación raíz de confianza**, seleccione **Certificados**.</span><span class="sxs-lookup"><span data-stu-id="52693-p109">Expand **Certificates (Local Computer)**. Expand **Trusted Root Certification Authorities**, select **Certificates**.</span></span>

5.  <span data-ttu-id="52693-p110">Haga clic en el certificado raíz emitido por su CA. Haga clic con el botón secundario en el certificado, seleccione **Todas las tareas**, seleccione **Exportar**. Se abrirá el **Asistente para exportación de certificados**.</span><span class="sxs-lookup"><span data-stu-id="52693-p110">Click the root certificate issued by your CA. Right click the certificate, select **All Tasks**, select **Export**. The **Certificate Export Wizard** will open.</span></span>

6.  <span data-ttu-id="52693-154">En el **Asistente para exportación de certificados**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="52693-154">In the **Certificate Export Wizard**, click **Next**.</span></span>

7.  <span data-ttu-id="52693-155">En el cuadro de diálogo **Formato de archivo de exportación**, seleccione un formato para exportar.</span><span class="sxs-lookup"><span data-stu-id="52693-155">On the **Export File Format** dialog, select a format to export to.</span></span> <span data-ttu-id="52693-156">Se recomienda el **estándar de sintaxis de mensajes criptográficos \#: certificados PKCS 7 (. P7B)**.</span><span class="sxs-lookup"><span data-stu-id="52693-156">We recommend the **Cryptographic Message Syntax Standard – PKCS \#7 Certificates (.P7B)**.</span></span> <span data-ttu-id="52693-157">Si selecciona el **estándar de sintaxis de mensajes criptográficos: \#certificados PKCS 7 (. P7B)**, seleccione la casilla **incluir todos los certificados en la ruta de certificación si es posible** para exportar la cadena de certificados, incluido el certificado de CA raíz y los certificados de CA intermedios.</span><span class="sxs-lookup"><span data-stu-id="52693-157">If you select the **Cryptographic Message Syntax Standard – PKCS \#7 Certificates (.P7B)**, select the **Include all certificates in the certification path if possible** checkbox to export the certificate chain, including the root CA certificate and any Intermediate CA certificates.</span></span> <span data-ttu-id="52693-158">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="52693-158">Click **Next**.</span></span>

8.  <span data-ttu-id="52693-p112">En el cuadro de diálogo **Archivo que se va a exportar** de la entrada de nombre de archivo, escriba una ruta y nombre de archivo para el certificado exportado (la extensión predeterminada es .p7b). De manera opcional, haga clic en **Examinar**, localice un directorio en el que colocar el certificado exportado y especifique un nombre para el certificado exportado. Haga clic en **Guardar**. Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="52693-p112">On the **File to Export** dialog in the file name entry, type a path and file name (default extension is .p7b) for the exported certificate. Optionally, click **Browse**, locate a directory to place the exported certificate in and provide a name for the exported certificate. Click **Save**. Click **Next**.</span></span>

9.  <span data-ttu-id="52693-p113">Repase el resumen de acciones y haga clic en **Finalizar** para completar la exportación del certificado. Haga clic en **Aceptar** para confirmar si la exportación se ha completado correctamente.</span><span class="sxs-lookup"><span data-stu-id="52693-p113">Review the summary of actions, and click **Finish** to complete the export of the certificate. Click **OK** to confirm the successful export.</span></span>

</div>

<div>

## <a name="to-import-the-ca-certification-chain-for-the-internal-interface"></a><span data-ttu-id="52693-165">Para importar la cadena de certificación de CA para la interfaz interna</span><span class="sxs-lookup"><span data-stu-id="52693-165">To import the CA certification chain for the internal interface</span></span>

1.  <span data-ttu-id="52693-166">En cada servidor perimetral, abra Microsoft Management Console (MMC). Para ello, haga clic en **Inicio**, en **Ejecutar**, escriba **mmc** en el cuadro **Abrir** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="52693-166">On each Edge Server, open the Microsoft Management Console (MMC) by clicking **Start**, clicking **Run**, typing **mmc** in the **Open** box, and then clicking **OK**.</span></span>

2.  <span data-ttu-id="52693-167">En el menú **Archivo**, haga clic en **Agregar o quitar complemento** y, a continuación, en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="52693-167">On the **File** menu, click **Add/Remove Snap-in**, and then click **Add**.</span></span>

3.  <span data-ttu-id="52693-168">En el cuadro **Agregar complementos independientes**, haga clic en **Certificados** y, a continuación, en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="52693-168">In the **Add Standalone Snap-ins** box, click **Certificates**, and then click **Add**.</span></span>

4.  <span data-ttu-id="52693-169">En el cuadro de diálogo **Complemento de certificados**, haga clic en **Cuenta de equipo** y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="52693-169">In the **Certificate snap-in** dialog box, click **Computer account**, and then click **Next**.</span></span>

5.  <span data-ttu-id="52693-170">En el cuadro de diálogo **Seleccionar equipo**, asegúrese de que la casilla **Equipo local: (el equipo en el que se está ejecutando esta consola)** esté activada y, a continuación, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="52693-170">In the **Select Computer** dialog box, ensure that the **Local computer: (the computer this console is running on)** check box is selected, and then click **Finish**.</span></span>

6.  <span data-ttu-id="52693-171">Haga clic en **Cerrar** y, a continuación, en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="52693-171">Click **Close**, and then click **OK**.</span></span>

7.  <span data-ttu-id="52693-172">En el árbol de la consola, expanda **Certificados (equipo local)**, haga clic con el botón secundario en **Entidades de certificación raíz de confianza**, elija **Todas las tareas** y, a continuación, haga clic en **Importar**.</span><span class="sxs-lookup"><span data-stu-id="52693-172">In the console tree, expand **Certificates (Local Computer)**, right-click **Trusted Root Certification Authorities**, point to **All Tasks**, and then click **Import**.</span></span>

8.  <span data-ttu-id="52693-173">En el asistente, en **Archivo para importar**, especifique el nombre de archivo del certificado (es decir, el nombre del archivo que especificó al descargar la cadena de certificación de CA para la interfaz interna en el procedimiento anterior).</span><span class="sxs-lookup"><span data-stu-id="52693-173">In the wizard, in **File to Import**, specify the file name of the certificate (that is, the name of that you specified when you downloaded the CA certification chain for the internal interface in the previous procedure).</span></span>

9.  <span data-ttu-id="52693-174">Repita este procedimiento en todos los servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="52693-174">Repeat this procedure on each Edge Server.</span></span>

</div>

<div>

## <a name="to-create-the-certificate-request-for-the-internal-interface"></a><span data-ttu-id="52693-175">Para crear la solicitud de certificado para la interfaz interna</span><span class="sxs-lookup"><span data-stu-id="52693-175">To create the certificate request for the internal interface</span></span>

1.  <span data-ttu-id="52693-176">En uno de los servidores perimetrales, inicie el Asistente para la implementación y junto a **Paso 3: Solicitar, instalar o asignar certificados**, haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="52693-176">On one of the Edge Servers, start the Deployment Wizard, and next to **Step 3: Request, Install, or Assign Certificates**, click **Run**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="52693-177">Si tiene varios servidores perimetrales en una ubicación de un grupo de servidores, puede ejecutar el Asistente para certificados en cualquiera de los servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="52693-177">If you have multiple Edge Servers in one location in a pool, you can run the Certificate Wizard on any one of the Edge Servers.</span></span><BR><span data-ttu-id="52693-178">Después de ejecutar el Paso 3 por primera vez, el botón pasará a mostrar <STRONG>Ejecutar de nuevo</STRONG> y no se mostrará una marca de verificación verde que indica la correcta finalización de la tarea hasta que todos los certificados requeridos se hayan solicitado, instalado y asignado.</span><span class="sxs-lookup"><span data-stu-id="52693-178">After you run Step 3 the first time, the button changes to <STRONG>Run again</STRONG>, and a green check mark that indicates successful completion of the task is not displayed until all require certificates have been requested, installed, and assigned.</span></span>

    
    </div>

2.  <span data-ttu-id="52693-179">En la página **Tareas de certificado disponibles**, haga clic en **Crear una nueva solicitud de certificado**.</span><span class="sxs-lookup"><span data-stu-id="52693-179">On the **Available Certificate Tasks** page, click **Create a new certificate request**.</span></span>

3.  <span data-ttu-id="52693-180">En la página \*\*Solicitud de certificado \*\*, haga clic en \*\*Siguiente \*\*.</span><span class="sxs-lookup"><span data-stu-id="52693-180">On the **Certificate Request** page, click **Next**.</span></span>

4.  <span data-ttu-id="52693-181">En la página **Solicitudes retrasadas o inmediatas**, haga clic en **Prepare ahora la solicitud, pero envíela más tarde**.</span><span class="sxs-lookup"><span data-stu-id="52693-181">On the **Delayed or Immediate Requests** page, click **Prepare the request now, but send it later**.</span></span>

5.  <span data-ttu-id="52693-182">En la página **archivo de solicitud de certificado** , escriba la ruta de acceso completa y el nombre de archivo en el que se va a guardar la solicitud (por ejemplo, **c:\\CERT\_Internal\_Edge. cer**).</span><span class="sxs-lookup"><span data-stu-id="52693-182">On the **Certificate Request File** page, type the full path and file name to which the request is to be saved (for example, **c:\\cert\_internal\_edge.cer**).</span></span>

6.  <span data-ttu-id="52693-183">En la página **Especificar plantilla de certificado alternativa**, para usar una plantilla distinta a la plantilla predeterminada WebServer, active la casilla **Usar plantilla de certificado alternativa para la entidad de certificación seleccionada**.</span><span class="sxs-lookup"><span data-stu-id="52693-183">On the **Specify Alternate Certificate Template** page, to use a template other than the default WebServer template, select the **Use alternative certificate template for the selected Certificate Authority** check box.</span></span>

7.  <span data-ttu-id="52693-184">En la página **Nombre y configuración de seguridad**, siga este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="52693-184">On the **Name and Security Settings** page, do the following:</span></span>
    
      - <span data-ttu-id="52693-185">En **Nombre descriptivo**, escriba un nombre para mostrar para el certificado (por ejemplo, perímetro interno).</span><span class="sxs-lookup"><span data-stu-id="52693-185">In **Friendly name**, type a display name for the certificate (for example, Internal Edge).</span></span>
    
      - <span data-ttu-id="52693-186">En **Longitud de bits**, especifique la longitud de bits (normalmente, el valor predeterminado es **2048**).</span><span class="sxs-lookup"><span data-stu-id="52693-186">In **Bit length**, specify the bit length (typically, the default of **2048**).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="52693-187">Las longitudes de bits mayores son más seguras, pero afectan de forma negativa a la velocidad.</span><span class="sxs-lookup"><span data-stu-id="52693-187">Higher bit lengths offer more security, but they have a negative impact on speed.</span></span>

        
        </div>
    
      - <span data-ttu-id="52693-188">Si el certificado debe poder exportarse, active la casilla **Marcar la clave privada del certificado como exportable**.</span><span class="sxs-lookup"><span data-stu-id="52693-188">If the certificate needs to be exportable, select the **Mark certificate private key as exportable** check box.</span></span>

8.  <span data-ttu-id="52693-189">En la página **Información de la organización**, escriba un nombre para la organización y la unidad organizativa (por ejemplo, una división o departamento).</span><span class="sxs-lookup"><span data-stu-id="52693-189">On the **Organization Information** page, type the name for the organization and the organizational unit (OU) (for example, a division or department).</span></span>

9.  <span data-ttu-id="52693-190">En la página **Información geográfica**, escriba la información de ubicación.</span><span class="sxs-lookup"><span data-stu-id="52693-190">On the **Geographical Information** page, specify the location information.</span></span>

10. <span data-ttu-id="52693-191">En la página **Nombre de sujeto/nombres alternativos de sujeto**, la información se rellenará automáticamente gracias al asistente que se muestra.</span><span class="sxs-lookup"><span data-stu-id="52693-191">On the **Subject Name/Subject Alternate Names** page, the information to be automatically populated by the wizard is displayed.</span></span>

11. <span data-ttu-id="52693-192">En la página **Configurar nombres alternativos de sujeto**, especifique cualquier nombre alternativo de sujeto adicional que necesite.</span><span class="sxs-lookup"><span data-stu-id="52693-192">On the **Configure Additional Subject Alternate Names** page, specify any additional subject alternative names that are required.</span></span>

12. <span data-ttu-id="52693-193">En la página **Resumen de la solicitud**, revise la información del certificado que se va a usar para generar la solicitud.</span><span class="sxs-lookup"><span data-stu-id="52693-193">On the **Request Summary** page, review the certificate information that is going to be used to generate the request.</span></span>

13. <span data-ttu-id="52693-194">Una vez completados los comandos, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="52693-194">After the commands complete, do the following:</span></span>
    
      - <span data-ttu-id="52693-195">Para visualizar el registro de la solicitud de certificación, haga clic en **Ver registro**.</span><span class="sxs-lookup"><span data-stu-id="52693-195">To view the log for the certificate request, click **View Log**.</span></span>
    
      - <span data-ttu-id="52693-196">Para completar la solicitud de certificación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="52693-196">To complete the certificate request, click **Next**.</span></span>

14. <span data-ttu-id="52693-197">En la página **Archivo de solicitud de certificados**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="52693-197">On the **Certificate Request File** page, do the following:</span></span>
    
      - <span data-ttu-id="52693-198">Para visualizar el archivo de solicitud de firma de certificado (CSR) que se ha generado, haga clic en **Ver**.</span><span class="sxs-lookup"><span data-stu-id="52693-198">To view the generated certificate signing request (CSR) file, click **View**.</span></span>
    
      - <span data-ttu-id="52693-199">Para cerrar el asistente, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="52693-199">To close the wizard, click **Finish**.</span></span>

15. <span data-ttu-id="52693-200">Envíe este archivo a su CA (por correo electrónico u otro método compatible con la organización para su CA de empresa) y, cuando reciba el archivo de respuesta, copie el nuevo certificado en este equipo de modo que esté disponible para importarlo.</span><span class="sxs-lookup"><span data-stu-id="52693-200">Submit this file to your CA (by email or other method supported by your organization for your enterprise CA) and, when you receive the response file, copy the new certificate to this computer so that it is available for import.</span></span>

</div>

<div>

## <a name="to-import-the-certificate-for-the-internal-interface"></a><span data-ttu-id="52693-201">Para importar el certificado para la interfaz interna</span><span class="sxs-lookup"><span data-stu-id="52693-201">To import the certificate for the internal interface</span></span>

1.  <span data-ttu-id="52693-202">Inicie sesión en el servidor perimetral donde haya creado la solicitud de certificado como miembro del grupo de administradores locales.</span><span class="sxs-lookup"><span data-stu-id="52693-202">Log on to the Edge Server on which you created the certificate request as a member of the local Administrators group.</span></span>

2.  <span data-ttu-id="52693-203">En el Asistente para la implementación, junto a **Paso 3: Solicitar, instalar o asignar certificados**, haga clic en **Ejecutar de nuevo**.</span><span class="sxs-lookup"><span data-stu-id="52693-203">In the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>
    
    <span data-ttu-id="52693-204">Después de ejecutar el Paso 3 por primera vez, el botón pasará a mostrar **Ejecutar de nuevo**, pero no se mostrará una marca de verificación verde que indica la correcta finalización de la tarea hasta que todos los certificados requeridos se hayan solicitado, instalado y asignado.</span><span class="sxs-lookup"><span data-stu-id="52693-204">After you run Step 3 the first time, the button changes to **Run again**, but a green check mark (indicating successful completion of the task) is not displayed until all require certificates have been requested, installed, and assigned.</span></span>

3.  <span data-ttu-id="52693-205">En la página **Tareas de certificado disponibles**, haga clic en **Importar un certificado de un archivo .P7b, .pfx o .cer**.</span><span class="sxs-lookup"><span data-stu-id="52693-205">On the **Available Certificate Tasks** page, click **Import a certificate from a .P7b, .pfx or .cer file**.</span></span>

4.  <span data-ttu-id="52693-206">En la página **Importar certificado**, escriba la ruta de acceso completa y el nombre de archivo del certificado que haya solicitado y recibido para la interfaz interna de este servidor perimetral (o haga clic en **Examinar** para buscar y seleccionar el archivo).</span><span class="sxs-lookup"><span data-stu-id="52693-206">On the **Import Certificate** page, type the full path and file name of the certificate that you requested and received for the internal interface of this Edge Server (or, click **Browse** to locate and select the file).</span></span>

5.  <span data-ttu-id="52693-207">Si va a importar certificados para otros miembros del grupo de servidores que contengan una clave privada, active la casilla **El archivo del certificado contiene clave privada de certificado** y especifique la contraseña.</span><span class="sxs-lookup"><span data-stu-id="52693-207">If you are importing certificates for other members of the pool a certificate containing a private key, select the **Certificate file contains certifcate’s private key** check box and specify the password.</span></span>

</div>

<div>

## <a name="to-export-the-certificate-with-the-private-key-for-edge-servers-in-a-pool"></a><span data-ttu-id="52693-208">Para exportar el certificado con la clave privada para servidores perimetrales de un grupo</span><span class="sxs-lookup"><span data-stu-id="52693-208">To export the certificate with the private key for Edge Servers in a pool</span></span>

1.  <span data-ttu-id="52693-209">Inicie sesión como miembro del grupo Administradores en el mismo servidor perimetral en el que desea importar el certificado.</span><span class="sxs-lookup"><span data-stu-id="52693-209">Log on as a member of the Administrators group to the same Edge Server on which you imported the certificate.</span></span>

2.  <span data-ttu-id="52693-210">Haga clic en **Inicio**, en **Ejecutar** y escriba **MMC**.</span><span class="sxs-lookup"><span data-stu-id="52693-210">Click **Start**, click **Run**, and type **MMC**.</span></span>

3.  <span data-ttu-id="52693-211">Desde la consola MMC, haga clic en **Archivo**, haga clic en **Agregar o quitar complemento**.</span><span class="sxs-lookup"><span data-stu-id="52693-211">From the MMC console, click **File**, click **Add/Remove Snap-in**.</span></span>

4.  <span data-ttu-id="52693-212">En la página Agregar o quitar complemento, haga clic en **Certificados** y en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="52693-212">From Add or Remove Snap-ins page, click **Certificates**, click **Add**.</span></span>

5.  <span data-ttu-id="52693-p114">En el cuadro de diálogo del complemento certificados, seleccione **Cuenta de equipo**. Haga clic en **Siguiente**. En Seleccionar equipo, marque **Equipo local (el equipo en el que se está ejecutando esta consola)**. Haga clic en **Finalizar**. Haga clic en **Aceptar** para completar la configuración de la consola MMC.</span><span class="sxs-lookup"><span data-stu-id="52693-p114">In the Certificates snap-in dialog, select **Computer account**. Click **Next**. In Select Computer, select **Local computer: (the computer this console is running on)**. Click **Finish**. Click **OK** to complete configuration of the MMC console.</span></span>

6.  <span data-ttu-id="52693-p115">Haga doble clic en **Certificados (equipo local)** para ampliar los almacenes de certificados. Haga doble clic en **Personal** y doble clic de nuevo en **Certificados**.</span><span class="sxs-lookup"><span data-stu-id="52693-p115">Double-click **Certificates (Local Computer)** to expand the certificate stores. Double-click **Personal**, then double-click **Certificates**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="52693-p116">Si no hay certificados en el almacén Certificados Personal para el equipo local, no habrá una clave privada asociada al certificado que se importó. Revise los pasos para la solicitud y la importación. Si el problema continúa, póngase en contacto con su administrador o proveedor de entidades de certificación.</span><span class="sxs-lookup"><span data-stu-id="52693-p116">If there are no certificates in the Certificates Personal store for the local computer, there is no private key associated with the certificate that was imported. Review the request and import steps. If the problem persists, contact your certification authority administrator or provider.</span></span>

    
    </div>

7.  <span data-ttu-id="52693-p117">En el almacén Certificados Personal del equipo local, haga clic con el botón secundario en el certificado que va a exportar. Haga clic en **Todas las tareas** y en **Exportar**.</span><span class="sxs-lookup"><span data-stu-id="52693-p117">In the Certificates Personal store for the local computer, right-click the certificate that you are exporting. Click **All Tasks**, click **Export**.</span></span>

8.  <span data-ttu-id="52693-p118">En el asistente para exportación de certificados, haga clic en **Siguiente**. Seleccione **Exportar la clave privada** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="52693-p118">In the Certificate Export Wizard, click **Next**. Select **Yes, export the private key**. Click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="52693-p119">Si la opción <STRONG>Exportar la clave privada</STRONG> no se encuentra disponible, se deberá a que no se marcó la clave privada asociada a este certificado para la exportación. Tendrá que solicitar de nuevo el certificado y, antes de que se inicie la exportación, deberá asegurarse de que el certificado está marcado para que se exporte la clave privada. Póngase en contacto con el administrador o proveedor de entidades de certificación.</span><span class="sxs-lookup"><span data-stu-id="52693-p119">If the selection <STRONG>Yes, export the private key</STRONG> is not available, the private key associated with this certificate was not marked for export. You will need to request the certificate again, ensuring that the certificate is marked to allow for the export of the private key before you can continue with the export. Contact your certification authority administrator or provider.</span></span>

    
    </div>

9.  <span data-ttu-id="52693-231">En el cuadro de diálogo formatos de archivo de exportación, seleccione **intercambio\#de información personal: PKCS 12 (. PFX)** y, a continuación, seleccione lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="52693-231">On the Export File Formats dialog, select **Personal Information Exchange – PKCS\#12 (.PFX)** and then select the following:</span></span>
    
      - <span data-ttu-id="52693-232">Si es posible, incluir todos los certificados en la ruta de acceso de certificación</span><span class="sxs-lookup"><span data-stu-id="52693-232">Include all certificates in the certification path if possible</span></span>
    
      - <span data-ttu-id="52693-233">Exportar todas las propiedades extendidas</span><span class="sxs-lookup"><span data-stu-id="52693-233">Export all extended properties</span></span>
        
        <div>
        

        > [!WARNING]  
        > <span data-ttu-id="52693-p120">Cuando exporte el certificado desde un servidor perimetral, no seleccione <STRONG>Eliminar la clave privada si la exportación es correcta</STRONG>. Al seleccionar esta opción es necesario importar el certificado y la clave privada a este servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="52693-p120">When exporting the certificate from an Edge server, do not select <STRONG>Delete the private key if the export is successful</STRONG>. Selecting this option will require that you import the certificate and the private key to this Edge server.</span></span>

        
        </div>
    
    <span data-ttu-id="52693-236">Haga clic en \*\*Siguiente \*\* para continuar.</span><span class="sxs-lookup"><span data-stu-id="52693-236">Click **Next** to continue.</span></span>

10. <span data-ttu-id="52693-p121">Si desea asignar una contraseña para proteger la clave privada, escriba dicha contraseña. Vuelva a escribir la contraseña para confirmarla. Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="52693-p121">If you want to assign password to protect the private key, type a password for the private key. Re-enter the password to confirm. Click **Next**.</span></span>

11. <span data-ttu-id="52693-p122">Escriba la ruta y nombre de archivo del certificado exportado, utilizando la extensión de archivo .pfx. La ruta debe estar accesible para todos los demás servidores perimetrales del grupo o disponible para el transporte mediante medios extraíbles, por ejemplo, una unidad flash USB. Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="52693-p122">Type a path and file name for the exported certificate, using a file extension of .pfx. The path must either be accessible to all other Edge servers in the pool or available to transport by means of removable media - for example, a USB flash drive. Click **Next**.</span></span>

12. <span data-ttu-id="52693-p123">Revise el resumen del cuadro de diálogo del asistente para exportación de certificados y haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="52693-p123">Review the summary on the Completing the Certificate Export Wizard dialog. Click **Finish**.</span></span>

13. <span data-ttu-id="52693-245">Haga clic en **Aceptar** cuando el cuadro de diálogo informe de que la exportación ha concluido correctamente</span><span class="sxs-lookup"><span data-stu-id="52693-245">Click **OK** in the successful export dialog.</span></span>

14. <span data-ttu-id="52693-246">Importe el archivo de certificado exportado a los demás servidores perimetrales siguiendo los pasos descritos en los procedimientos de [configuración de certificados para la interfaz perimetral externa para Lync Server 2013](lync-server-2013-set-up-certificates-for-the-external-edge-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="52693-246">Import the exported certificate file to the other Edge servers following the steps outlined in the [Set up certificates for the external edge interface for Lync Server 2013](lync-server-2013-set-up-certificates-for-the-external-edge-interface.md) procedures.</span></span>

</div>

<div>

## <a name="to-assign-the-internal-certificate-on-the-edge-servers"></a><span data-ttu-id="52693-247">Para asignar el certificado interno en los servidores perimetrales</span><span class="sxs-lookup"><span data-stu-id="52693-247">To assign the internal certificate on the Edge Servers</span></span>

1.  <span data-ttu-id="52693-248">En cada servidor perimetral, en el Asistente para la implementación, junto a **Paso 3: Solicitar, instalar o asignar certificados**, haga clic en **Ejecutar de nuevo**.</span><span class="sxs-lookup"><span data-stu-id="52693-248">On each Edge Server, in the Deployment Wizard, next to **Step 3: Request, Install, or Assign Certificates**, click **Run again**.</span></span>

2.  <span data-ttu-id="52693-249">En la página **Tareas de certificado disponibles**, haga clic en **Asignar un certificado existente**.</span><span class="sxs-lookup"><span data-stu-id="52693-249">On the **Available Certificate Tasks** page, click **Assign an existing certificate**.</span></span>

3.  <span data-ttu-id="52693-250">En la página **Asignación del certificado**, seleccione **Interfaz perimetral interna** en la lista.</span><span class="sxs-lookup"><span data-stu-id="52693-250">On the **Certificate Assignment** page, select **Edge Internal** in the list.</span></span>

4.  <span data-ttu-id="52693-251">En la página **Almacén de certificados**, seleccione el certificado que importó para el perímetro interno (en el procedimiento anterior).</span><span class="sxs-lookup"><span data-stu-id="52693-251">On the **Certificate Store** page, select the certificate that you imported for the internal edge (from the previous procedure).</span></span>

5.  <span data-ttu-id="52693-252">En la página **Resumen de asignación de certificados**, revise su configuración y, a continuación, haga clic en **Siguiente** para asignar los certificados.</span><span class="sxs-lookup"><span data-stu-id="52693-252">On the **Certificate Assignment Summary** page, review your settings, and then click **Next** to assign the certificates.</span></span>

6.  <span data-ttu-id="52693-253">En la página de finalización del asistente, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="52693-253">On the wizard completion page, click **Finish**.</span></span>

7.  <span data-ttu-id="52693-254">Después de asignar el certificado de perímetro interno, abra el complemento Certificado en cada servidor, expanda **Certificados (equipo local)**, expanda **Personal**, haga clic en **Certificados** y, a continuación, compruebe que aparezca el certificado de perímetro interno en el panel de detalles.</span><span class="sxs-lookup"><span data-stu-id="52693-254">After using this procedure to assign the internal edge certificate, open the Certificate snap-in on each server, expand **Certificates (Local computer)**, expand **Personal**, click **Certificates**, and then verify in the details pane that the internal edge certificate is listed.</span></span>

8.  <span data-ttu-id="52693-255">Si la implementación incluye varios servidores perimetrales, repita este procedimiento con todos los servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="52693-255">If your deployment includes multiple Edge Servers, repeat this procedure for each Edge Server.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

