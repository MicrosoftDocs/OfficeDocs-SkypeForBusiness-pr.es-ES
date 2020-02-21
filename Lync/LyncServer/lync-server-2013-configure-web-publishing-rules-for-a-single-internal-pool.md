---
title: 'Lync Server 2013: configurar las reglas de publicación web para un solo grupo interno'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure web publishing rules for a single internal pool
ms:assetid: 86ff4b2a-1ba9-46a2-a175-8b19e00a49dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429712(v=OCS.15)
ms:contentKeyID: 48184725
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: adf6a1d777e16827f41d9a795fde54fca49750e1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204637"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-web-publishing-rules-for-a-single-internal-pool-in-lync-server-2013"></a><span data-ttu-id="5e021-102">Configurar las reglas de publicación web para un solo grupo de servidores interno en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5e021-102">Configure web publishing rules for a single internal pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5e021-103">_**Última modificación del tema:** 2014-07-07_</span><span class="sxs-lookup"><span data-stu-id="5e021-103">_**Topic Last Modified:** 2014-07-07_</span></span>

<span data-ttu-id="5e021-104">Microsoft Forefront Threat Management Gateway 2010 y enrutamiento de solicitudes de aplicaciones de Internet Information Server (IIS ARR) usa reglas de publicación web para publicar recursos internos, como una dirección URL de reunión, a los usuarios de Internet.</span><span class="sxs-lookup"><span data-stu-id="5e021-104">Microsoft Forefront Threat Management Gateway 2010 and Internet Information Server Application Request Routing (IIS ARR) uses web publishing rules to publish internal resources, such as a meeting URL, to users on the Internet.</span></span>

<span data-ttu-id="5e021-105">Además de las direcciones URL de los servicios web para los directorios virtuales, también debe crear reglas de publicación para direcciones URL sencillas, la dirección URL de LyncDiscover y el servidor de Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="5e021-105">In addition to the Web Services URLs for the virtual directories, you must also create publishing rules for simple URLs, the LyncDiscover URL, and the Office Web Apps Server.</span></span> <span data-ttu-id="5e021-106">Para cada URL sencilla, debe crear una regla individual en el proxy inverso que apunte a dicha URL sencilla.</span><span class="sxs-lookup"><span data-stu-id="5e021-106">For each simple URL, you must create an individual rule on the reverse proxy that points to that simple URL.</span></span>

<span data-ttu-id="5e021-107">Si va a implementar la movilidad y usar la detección automática, debe crear una regla de publicación para la URL del servicio Detección automática externa.</span><span class="sxs-lookup"><span data-stu-id="5e021-107">If you are deploying mobility and using automatic discovery, you need to create a publishing rule for the external Autodiscover Service URL.</span></span> <span data-ttu-id="5e021-108">La detección automática también requiere reglas de publicación para la dirección URL externa de servicios Web de Lync Server para el grupo de directores y el grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="5e021-108">Automatic discovery also requires publishing rules for the external Lync Server Web Services URL for your Director pool and Front End pool.</span></span> <span data-ttu-id="5e021-109">Para obtener información detallada sobre cómo crear las reglas de publicación web para la detección automática, consulte [configuración del proxy inverso para movilidad en Lync Server 2013](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md).</span><span class="sxs-lookup"><span data-stu-id="5e021-109">For details about creating the web publishing rules for automatic discovery, see [Configuring the reverse proxy for mobility in Lync Server 2013](lync-server-2013-configuring-the-reverse-proxy-for-mobility.md).</span></span>

<span data-ttu-id="5e021-110">Realice los siguientes procedimientos para crear las reglas de publicación web.</span><span class="sxs-lookup"><span data-stu-id="5e021-110">Use the following procedures to create web publishing rules.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5e021-111">En estos procedimientos se presupone que ha instalado la edición Standard Edition de Forefront Threat Management Gateway (TMG) 2010 o que ha instalado y configurado Internet Information Server con la extensión de enrutamiento de solicitud de aplicación (IIS ARR).</span><span class="sxs-lookup"><span data-stu-id="5e021-111">These procedures assume that you have installed the Standard Edition of Forefront Threat Management Gateway (TMG) 2010 or have installed and configured Internet Information Server with the Application request Routing (IIS ARR) extension.</span></span> <span data-ttu-id="5e021-112">Puede usar TMG o IIS ARR.</span><span class="sxs-lookup"><span data-stu-id="5e021-112">You use either TMG or IIS ARR.</span></span>



</div>

<div>

## <a name="to-create-a-web-server-publishing-rule-on-the-computer-running-tmg-2010"></a><span data-ttu-id="5e021-113">Para crear una regla de publicación de servidor web en el equipo que ejecuta TMG 2010</span><span class="sxs-lookup"><span data-stu-id="5e021-113">To create a web server publishing rule on the computer running TMG 2010</span></span>

1.  <span data-ttu-id="5e021-114">Haga clic en **Inicio**, diríjase a **Programas**, haga clic en **Microsoft Forefront TMG** y, a continuación, haga clic en **Administración de Forefront TMG**.</span><span class="sxs-lookup"><span data-stu-id="5e021-114">Click **Start**, select **Programs**, select **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="5e021-115">En el panel izquierdo, expanda **NombreDeServidor**, haga clic con el botón secundario en **Directiva de firewall**, elija **Nueva** y, a continuación, haga clic en **Regla de publicación de sitio web**.</span><span class="sxs-lookup"><span data-stu-id="5e021-115">In the left pane, expand **ServerName**, right-click **Firewall Policy**, select **New**, and then click **Web Site Publishing Rule**.</span></span>

3.  <span data-ttu-id="5e021-116">En la página **Asistente para nueva regla de publicación de web**, escriba un nombre para mostrar para la regla de publicación (por ejemplo, ReglaDescargasWebLyncServer).</span><span class="sxs-lookup"><span data-stu-id="5e021-116">On the **Welcome to the New Web Publishing Rule** page, type a display name for the publishing rule (for example, LyncServerWebDownloadsRule).</span></span>

4.  <span data-ttu-id="5e021-117">En la página **Seleccionar acción de regla**, seleccione **Permitir**.</span><span class="sxs-lookup"><span data-stu-id="5e021-117">On the **Select Rule Action** page, select **Allow**.</span></span>

5.  <span data-ttu-id="5e021-118">En la página **Tipo de publicación**, seleccione **Publicar un único sitio web o un equilibrador de carga**.</span><span class="sxs-lookup"><span data-stu-id="5e021-118">On the **Publishing Type** page, select **Publish a single Web site or load balancer**.</span></span>

6.  <span data-ttu-id="5e021-119">En la página **Seguridad de conexión de servidor**, seleccione **Usar SSL para conectar al servidor web o la granja de servidores publicados**.</span><span class="sxs-lookup"><span data-stu-id="5e021-119">On the **Server Connection Security** page, select **Use SSL to connect to the published Web server or server farm**.</span></span>

7.  <span data-ttu-id="5e021-120">En la página **Detalles internos de publicación**, escriba el nombre de dominio completo (FQDN) de la granja de servidores web internos que hospeda su contenido de reuniones y de la Libreta de direcciones en el cuadro **Nombre interno del sitio**.</span><span class="sxs-lookup"><span data-stu-id="5e021-120">On the **Internal Publishing Details** page, type the fully qualified domain name (FQDN) of the internal web farm that hosts your meeting content and Address Book content in the **Internal Site name** box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5e021-121">Si el servidor interno es un servidor Standard Edition, este FQDN corresponde al servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="5e021-121">If your internal server is a Standard Edition server, this FQDN is the Standard Edition server FQDN.</span></span> <span data-ttu-id="5e021-122">Si el servidor interno es un grupo de servidores front-end, el FQDN es una IP virtual (VIP) de equilibrador de carga de hardware que equilibra la carga de los servidores de la granja de servidores web internos.</span><span class="sxs-lookup"><span data-stu-id="5e021-122">If your internal server is a Front End pool, this FQDN is a hardware load balancer virtual IP (VIP) that load balances the internal web farm servers.</span></span> <span data-ttu-id="5e021-123">El servidor TMG debe poder resolver el FQDN como la dirección IP del servidor web interno.</span><span class="sxs-lookup"><span data-stu-id="5e021-123">The TMG server must be able to resolve the FQDN to the IP address of the internal web server.</span></span> <span data-ttu-id="5e021-124">Si el servidor de TMG no puede resolver el FQDN en la dirección IP correcta, puede seleccionar <STRONG>usar un nombre de equipo o una dirección IP para conectarse al servidor publicado</STRONG>y, a continuación, en el cuadro <STRONG>dirección IP</STRONG> <STRONG>o nombre de equipo</STRONG> , escriba la dirección IP del servidor Web interno.</span><span class="sxs-lookup"><span data-stu-id="5e021-124">If the TMG server is not able to resolve the FQDN to the proper IP address, you can select <STRONG>Use a computer name or IP address to connect to the published server</STRONG>, and then in the <STRONG>Computer name or</STRONG> <STRONG>IP address</STRONG> box, type the IP address of the internal web server.</span></span> <span data-ttu-id="5e021-125">Si lo hace así, asegúrese de que el puerto 53 esté abierto en el servidor TMG y de que pueda alcanzar un servidor DNS que resida en la red perimetral.</span><span class="sxs-lookup"><span data-stu-id="5e021-125">If you do this, you must ensure that port 53 is open on the TMG server and that it can reach a DNS server that resides in the perimeter network.</span></span> <span data-ttu-id="5e021-126">También puede usar entradas en el archivo de hosts local para facilitar la resolución de nombres.</span><span class="sxs-lookup"><span data-stu-id="5e021-126">You can also use entries in the local hosts file to provide name resolution.</span></span>

    
    </div>

8.  <span data-ttu-id="5e021-127">En la página **detalles internos de publicación** , en el cuadro **ruta de acceso (opcional)** , escriba \*\* / \*\* como la ruta de acceso de la carpeta que se va a publicar.</span><span class="sxs-lookup"><span data-stu-id="5e021-127">On the **Internal Publishing Details** page, in the **Path (optional)** box, type **/\*** as the path of the folder to be published.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5e021-p105">En el asistente para publicar un sitio web solo se puede especificar una ruta de acceso. Las rutas adicionales se agregarán mediante la modificación de las propiedades de la regla.</span><span class="sxs-lookup"><span data-stu-id="5e021-p105">In the website publishing wizard you can only specify one path. Additional paths can be added by modifying the properties of the rule.</span></span>

    
    </div>

9.  <span data-ttu-id="5e021-130">En la página **Detalles de nombre público**, confirme que se haya seleccionado **Este nombre de dominio** en la opción **Aceptar peticiones para**, y escriba el FQDN de la granja de servicios web externos en el cuadro **Nombre público**.</span><span class="sxs-lookup"><span data-stu-id="5e021-130">On the **Public Name Details** page, confirm that **This domain name** is selected under **Accept Requests for**, type the external Web Services FQDN, in the **Public Name** box.</span></span>

10. <span data-ttu-id="5e021-131">En la página **Seleccionar escucha de web**, haga clic en **Nueva** para abrir el Asistente para nueva definición de escucha de web.</span><span class="sxs-lookup"><span data-stu-id="5e021-131">On **Select Web Listener** page, click **New** to open the New Web Listener Definition Wizard.</span></span>

11. <span data-ttu-id="5e021-132">En la página **Este es el Asistente para nueva escucha de web**, escriba el nombre de la escucha de web en el cuadro **Nombre de la escucha de web** (por ejemplo, ServidoresWebLyncServer).</span><span class="sxs-lookup"><span data-stu-id="5e021-132">On the **Welcome to the New Web Listener Wizard** page, type a name for the web listener in the **Web listener name** box (for example, LyncServerWebServers).</span></span>

12. <span data-ttu-id="5e021-133">En la página **Seguridad de la conexión de cliente**, seleccione **Requerir conexiones seguras SSL con los clientes**.</span><span class="sxs-lookup"><span data-stu-id="5e021-133">On the **Client Connection Security** page, select **Require SSL secured connections with clients**.</span></span>

13. <span data-ttu-id="5e021-134">En la página **Direcciones IP de escucha de web**, seleccione **Externa** y, a continuación, haga clic en **Seleccionar direcciones IP**.</span><span class="sxs-lookup"><span data-stu-id="5e021-134">On the **Web Listener IP Address** page, select **External**, and then click **Select IP Addresses**.</span></span>

14. <span data-ttu-id="5e021-135">En la página **Selección de IP de la escucha externa**, seleccione **Direcciones IP especificadas en el equipo de Forefront TMG en la red seleccionada**, seleccione la dirección IP correspondiente y haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="5e021-135">On the **External Listener IP selection** page, select **Specified IP address on the Forefront TMG computer in the selected network**, select the appropriate IP address, click **Add**.</span></span>

15. <span data-ttu-id="5e021-136">En la página **Certificados SSL de escucha**, seleccione **Asignar un certificado a cada dirección IP**, seleccione la dirección IP asociada al FQDN web externo y haga clic en **Seleccionar certificado**.</span><span class="sxs-lookup"><span data-stu-id="5e021-136">On the **Listener SSL Certificates** page, select **Assign a certificate for each IP address**, select the IP address that is associated with the external web FQDN, and then click **Select Certificate**.</span></span>

16. <span data-ttu-id="5e021-137">En la página **Seleccionar certificado**, seleccione el certificado que coincida con los nombres públicos especificados en el paso 9 y haga clic en **Seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="5e021-137">On the **Select Certificate** page, select the certificate that matches the public names specified in step 9, click **Select**.</span></span>

17. <span data-ttu-id="5e021-138">En la página **Configuración de autenticación**, seleccione **Sin autenticación**.</span><span class="sxs-lookup"><span data-stu-id="5e021-138">On the **Authentication Setting** page, select **No Authentication**.</span></span>

18. <span data-ttu-id="5e021-139">En la página **Configuración de inicio de sesión único**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="5e021-139">On the **Single Sign On Setting** page, click **Next**.</span></span>

19. <span data-ttu-id="5e021-140">En la página **Finalización del Asistente para nueva escucha de web**, compruebe que la configuración de **Escucha de web** es correcta y haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="5e021-140">On the **Completing the Web Listener Wizard** page, verify that the **Web listener** settings are correct, and then click **Finish**.</span></span>

20. <span data-ttu-id="5e021-141">En la página **Delegación de la autenticación**, seleccione **Sin delegación, pero el cliente se puede autenticar directamente**.</span><span class="sxs-lookup"><span data-stu-id="5e021-141">On the **Authentication Delegation** page, select **No delegation, but client may authenticate directly**.</span></span>

21. <span data-ttu-id="5e021-142">En la página **Conjunto de usuarios**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="5e021-142">On the **User Set** page, click **Next**.</span></span>

22. <span data-ttu-id="5e021-143">En la página **Finalización del Asistente para nueva regla de publicación de web**, compruebe que los parámetros de la regla de publicación de web sean correctos y, a continuación, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="5e021-143">On the **Completing the New Web Publishing Rule Wizard** page, verify that the web publishing rule settings are correct, and then click **Finish**.</span></span>

23. <span data-ttu-id="5e021-144">Haga clic en **Aplicar** en el panel de detalles para guardar los cambios y actualizar la configuración.</span><span class="sxs-lookup"><span data-stu-id="5e021-144">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

</div>

<div>

## <a name="to-create-a-web-server-publishing-rule-on-the-computer-running-iis-arr"></a><span data-ttu-id="5e021-145">Para crear una regla de publicación de servidor Web en el equipo que ejecuta IIS ARR</span><span class="sxs-lookup"><span data-stu-id="5e021-145">To create a web server publishing rule on the computer running IIS ARR</span></span>

1.  <span data-ttu-id="5e021-146">Enlace el certificado que va a usar para el proxy inverso en el protocolo HTTPS.</span><span class="sxs-lookup"><span data-stu-id="5e021-146">Bind the certificate that you will use for the reverse proxy to the HTTPS protocol.</span></span> <span data-ttu-id="5e021-147">Haga clic en **Inicio**, seleccione **programas**, seleccione **herramientas administrativas**y, a continuación, haga clic en **Administrador de Internet Information Services (IIS)**.</span><span class="sxs-lookup"><span data-stu-id="5e021-147">Click **Start**, select **Programs**, select **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5e021-148">Puede encontrar ayuda adicional, capturas de pantalla y orientación sobre la implementación y la configuración de IIS ARR en el artículo de NextHop <A href="https://go.microsoft.com/fwlink/?linkid=293391">mediante el uso de IIS ARR como proxy inverso para Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="5e021-148">Additional help, screen shots and guidance on deploying and configuring IIS ARR can be found in the NextHop article <A href="https://go.microsoft.com/fwlink/?linkid=293391">Using IIS ARR as a Reverse Proxy for Lync Server 2013</A>.</span></span>

    
    </div>

2.  <span data-ttu-id="5e021-149">Si aún no lo ha hecho, importe el certificado que va a usar para el proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="5e021-149">If you have not already done so, import the certificate that you will use for the reverse proxy.</span></span> <span data-ttu-id="5e021-150">En el **Administrador de Internet Information Services (IIS)**, haga clic en el nombre del servidor de proxy inverso en el tamaño del lado izquierdo de la consola.</span><span class="sxs-lookup"><span data-stu-id="5e021-150">In **Internet Information Services (IIS) Manager**, click the reverse proxy server name on the left-hand size of the console.</span></span> <span data-ttu-id="5e021-151">En la mitad de la consola, en **IIS** , busque los **certificados de servidor**.</span><span class="sxs-lookup"><span data-stu-id="5e021-151">In the middle of the console under **IIS** locate **Server Certificates**.</span></span> <span data-ttu-id="5e021-152">Haga clic con el botón secundario en **certificados de servidor** y seleccione **abrir característica**.</span><span class="sxs-lookup"><span data-stu-id="5e021-152">Right-click **Server Certificates** and select **Open feature**.</span></span>

3.  <span data-ttu-id="5e021-153">En la parte derecha de la consola, haga clic en **Importar..**..</span><span class="sxs-lookup"><span data-stu-id="5e021-153">On the right hand side of the console, click **Import…**.</span></span> <span data-ttu-id="5e021-154">Escriba la ruta de acceso y el nombre de archivo del certificado con la extensión o haga clic en **...**</span><span class="sxs-lookup"><span data-stu-id="5e021-154">Type the path and filename of the certificate with the extension, or click **…**</span></span> <span data-ttu-id="5e021-155">para buscar el certificado.</span><span class="sxs-lookup"><span data-stu-id="5e021-155">to browse for the certificate.</span></span> <span data-ttu-id="5e021-156">Seleccione el certificado y haga clic en **abrir**.</span><span class="sxs-lookup"><span data-stu-id="5e021-156">Select the certificate and click **Open**.</span></span> <span data-ttu-id="5e021-157">Proporcione la contraseña usada para proteger la clave privada (si ha asignado una contraseña al exportar el certificado y la clave privada).</span><span class="sxs-lookup"><span data-stu-id="5e021-157">Supply the password used to protect the private key (if you assigned a password when exporting the certificate and private key).</span></span> <span data-ttu-id="5e021-158">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5e021-158">Click **OK**.</span></span> <span data-ttu-id="5e021-159">Si la importación del certificado se ha realizado correctamente, el certificado aparecerá como una entrada en la mitad de la consola como entrada en los **certificados de servidor**.</span><span class="sxs-lookup"><span data-stu-id="5e021-159">If the certificate import was successful, the certificate will appear as an entry in the middle of the console as an entry in **Server Certificates**.</span></span>

4.  <span data-ttu-id="5e021-160">Asignar el certificado para su uso con HTTPS.</span><span class="sxs-lookup"><span data-stu-id="5e021-160">Assign the certificate for use by HTTPS.</span></span> <span data-ttu-id="5e021-161">En la parte izquierda de la consola, seleccione el **sitio web predeterminado** del servidor IIS.</span><span class="sxs-lookup"><span data-stu-id="5e021-161">On the left-hand side of the console, select the **Default Web Site** of the IIS server.</span></span> <span data-ttu-id="5e021-162">En la parte derecha, haga clic en **enlaces...**.</span><span class="sxs-lookup"><span data-stu-id="5e021-162">On the right-hand side, click **Bindings…**.</span></span> <span data-ttu-id="5e021-163">En el cuadro de diálogo **enlaces de sitios** , haga clic en **Agregar..**..</span><span class="sxs-lookup"><span data-stu-id="5e021-163">In the **Site Bindings** dialog, click **Add…**.</span></span> <span data-ttu-id="5e021-164">En el cuadro de diálogo **Agregar enlace de sitio** , en **tipo:**, seleccione **https**.</span><span class="sxs-lookup"><span data-stu-id="5e021-164">On the **Add Site Binding** dialog under **Type:**, select **https**.</span></span> <span data-ttu-id="5e021-165">La selección de https le permitirá seleccionar el certificado que se usará para HTTPS.</span><span class="sxs-lookup"><span data-stu-id="5e021-165">Selecting https will allow you to select the certificate to use for https.</span></span> <span data-ttu-id="5e021-166">En **certificado SSL:**, seleccione el certificado que importó para el proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="5e021-166">Under **SSL certificate:**, select the certificate that you imported for the reverse proxy.</span></span> <span data-ttu-id="5e021-167">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5e021-167">Click **OK**.</span></span> <span data-ttu-id="5e021-168">A continuación, haga clic en **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="5e021-168">Then, click **Close**.</span></span> <span data-ttu-id="5e021-169">El certificado se enlaza ahora al proxy inverso para la capa de sockets seguros (SSL) y la seguridad de la capa de transporte (TLS).</span><span class="sxs-lookup"><span data-stu-id="5e021-169">The certificate is now bound to the reverse proxy for secure socket layer (SSL) and transport layer security (TLS).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="5e021-170">Si recibe una advertencia al cerrar los cuadros de diálogo de enlaces que faltan los certificados intermedios, deberá buscar e importar el certificado de la entidad de certificación raíz de la entidad de certificación pública y los certificados de CA intermedios.</span><span class="sxs-lookup"><span data-stu-id="5e021-170">If you receive a warning when closing the Bindings dialogs that intermediate certificates are missing, you need to locate and import the public CA root authority certificate and any intermediate CA certificates.</span></span> <span data-ttu-id="5e021-171">Consulte las instrucciones de la entidad de certificación pública desde la que solicitó el certificado y siga las instrucciones para solicitar e importar una cadena de certificados.</span><span class="sxs-lookup"><span data-stu-id="5e021-171">Consult the instructions at the public CA that you requested your certificate from and follow the instructions to request and import a certificate chain.</span></span> <span data-ttu-id="5e021-172">Si exportó el certificado desde el servidor perimetral, puede exportar el certificado de la entidad de certificación raíz y los certificados de CA intermedia asociados con el servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="5e021-172">If you exported the certificate from your Edge Server, you can export the root CA certificate and any intermediate CA certificates associated with the Edge Server.</span></span> <span data-ttu-id="5e021-173">Importe el certificado de la CA raíz en el almacén de entidades de certificación raíz de confianza del equipo (no debe confundirse con el almacén de usuario) en el almacén de entidades de certificación intermedias del equipo.</span><span class="sxs-lookup"><span data-stu-id="5e021-173">Import the root CA certificate into the Computer’s (not to be confused with the User store) Trusted Root Certification Authorities store and intermediate certificates into the Computer’s Intermediate Certification Authorities store.</span></span>

    
    </div>

5.  <span data-ttu-id="5e021-174">En la parte izquierda de la consola, debajo del nombre del servidor IIS, haga clic con el botón secundario en **granjas de servidores** y haga clic en **crear granja de servidores...**</span><span class="sxs-lookup"><span data-stu-id="5e021-174">On the left-hand side of the console below the IIS server name, right-click **Server Farms** then click **Create Server Farm…**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5e021-175">Si no ve el nodo <STRONG>granjas de servidores</STRONG> , debe instalar el enrutamiento de solicitud de aplicación.</span><span class="sxs-lookup"><span data-stu-id="5e021-175">If you do not see the <STRONG>Server Farms</STRONG> node, you need to install Application Request Routing.</span></span> <span data-ttu-id="5e021-176">Para obtener más información, consulte <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">configuración de servidores proxy inversos para Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="5e021-176">For details, see <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up reverse proxy servers for Lync Server 2013</A>.</span></span>

    
    </div>
    
    <span data-ttu-id="5e021-177">En el cuadro de diálogo **crear granja** de servidores del nombre de la **granja de servidores**, escriba un nombre (puede ser un nombre descriptivo con fines de identificación) para la primera dirección URL.</span><span class="sxs-lookup"><span data-stu-id="5e021-177">On the **Create Server Farm** dialog in **Server farm name**, type the a name (this can be a friendly name for identification purposes) for the first URL.</span></span> <span data-ttu-id="5e021-178">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="5e021-178">Click **Next**.</span></span>

6.  <span data-ttu-id="5e021-179">En el cuadro de diálogo **Agregar servidor** en **dirección de servidor**, escriba el nombre de dominio completo (FQDN) de los servicios web externos en el servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="5e021-179">On the **Add Server** dialog in **Server Address**, type the fully qualified domain name (FQDN) of the external web services on your Front End Server.</span></span> <span data-ttu-id="5e021-180">Los nombres que se usarán aquí para fines de ejemplo son los mismos que se usan en la sección de planeación para el proxy inverso, el proxy inverso de certificados inverso [en Lync Server 2013](lync-server-2013-certificate-summary-reverse-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="5e021-180">The names that will be used here for example purposes are the same that are used in the Planning section for the reverse proxy, [Certificate summary - Reverse proxy in Lync Server 2013](lync-server-2013-certificate-summary-reverse-proxy.md).</span></span> <span data-ttu-id="5e021-181">Al hacer referencia a la planificación del proxy inverso, `webext.contoso.com`escribimos el FQDN.</span><span class="sxs-lookup"><span data-stu-id="5e021-181">Referring to the reverse proxy planning, we type the FQDN `webext.contoso.com`.</span></span> <span data-ttu-id="5e021-182">Confirme que la casilla de verificación situada junto a **en línea** está seleccionada.</span><span class="sxs-lookup"><span data-stu-id="5e021-182">Confirm that the checkbox next to **Online** is selected.</span></span> <span data-ttu-id="5e021-183">Haga clic en **Agregar** para agregar el servidor al grupo de servidores web para esta configuración.</span><span class="sxs-lookup"><span data-stu-id="5e021-183">Click **Add** to add the server to the pool of web servers for this configuration.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="5e021-184">Lync Server usa equilibradores de carga de hardware para agrupar el director y los servidores front-end para el tráfico HTTP y HTTPS.</span><span class="sxs-lookup"><span data-stu-id="5e021-184">Lync Server uses hardware load balancers to pool Director and Front End Servers for HTTP and HTTPS traffic.</span></span> <span data-ttu-id="5e021-185">Solo deberá proporcionar un FQDN cuando agregue un servidor a la granja de servidores de IIS ARR.</span><span class="sxs-lookup"><span data-stu-id="5e021-185">You will only supply one FQDN when adding a server to the IIS ARR Server Farm.</span></span> <span data-ttu-id="5e021-186">El FQDN será el servidor front-end o el Director en las configuraciones de servidores no agrupados, o el FQDN del equilibrador de carga de hardware configurado para los grupos de servidores.</span><span class="sxs-lookup"><span data-stu-id="5e021-186">The FQDN will be the Front End Server or Director in non-pooled server configurations, or the FQDN of the configured hardware load balancer for server pools.</span></span> <span data-ttu-id="5e021-187">El único método admitido para equilibrar la carga del tráfico HTTP y HTTPS es mediante equilibradores de carga de hardware.</span><span class="sxs-lookup"><span data-stu-id="5e021-187">The only supported method to load balance HTTP and HTTPS traffic is by using hardware load balancers.</span></span>

    
    </div>

7.  <span data-ttu-id="5e021-188">En el cuadro de diálogo **Agregar servidor** , haga clic en **Configuración avanzada..**..</span><span class="sxs-lookup"><span data-stu-id="5e021-188">On the **Add Server** dialog, click **Advanced settings…**.</span></span> <span data-ttu-id="5e021-189">Se abrirá un cuadro de diálogo para definir el enrutamiento de solicitudes de aplicación para las solicitudes al FQDN configurado.</span><span class="sxs-lookup"><span data-stu-id="5e021-189">This opens a dialog to define application request routing for requests to the configured FQDN.</span></span> <span data-ttu-id="5e021-190">El objetivo es redefinir el puerto que se usa cuando IIS ARR procesa la solicitud.</span><span class="sxs-lookup"><span data-stu-id="5e021-190">The purpose is to redefine what port is used when the request is processed by IIS ARR.</span></span>
    
    <span data-ttu-id="5e021-191">De forma predeterminada, el puerto HTTP de destino debe definirse como 8080.</span><span class="sxs-lookup"><span data-stu-id="5e021-191">By default, the destination HTTP port must be defined as 8080.</span></span> <span data-ttu-id="5e021-192">Haga clic en junto al **httpPort 80** actual y establezca el valor en **8080**.</span><span class="sxs-lookup"><span data-stu-id="5e021-192">Click next to the current **httpPort 80** and set the value to **8080**.</span></span> <span data-ttu-id="5e021-193">Haga clic en junto al **httpsPort 443** actual y establezca el valor en **4443**.</span><span class="sxs-lookup"><span data-stu-id="5e021-193">Click next to the current **httpsPort 443** and set the value to **4443**.</span></span> <span data-ttu-id="5e021-194">Deje el parámetro **Weight** en 100.</span><span class="sxs-lookup"><span data-stu-id="5e021-194">Leave the **weight** parameter at 100.</span></span> <span data-ttu-id="5e021-195">Si es necesario, puede redefinir los pesos para una regla determinada una vez que tiene las estadísticas de línea base.</span><span class="sxs-lookup"><span data-stu-id="5e021-195">If needed, you can redefine weights for a given rule once you have baseline statistics.</span></span> <span data-ttu-id="5e021-196">Haga clic en **Finalizar** para completar esta parte de la configuración de la regla.</span><span class="sxs-lookup"><span data-stu-id="5e021-196">Click **Finish** to complete this part of the rule configuration.</span></span>

8.  <span data-ttu-id="5e021-197">Es posible que vea un cuadro de diálogo de reescritura de reglas que le informa de que el administrador de IIS puede crear una regla de reescritura de dirección URL para redirigir todas las solicitudes entrantes a la granja de servidores automáticamente.</span><span class="sxs-lookup"><span data-stu-id="5e021-197">You may see a dialog Rewrite Rules that informs you that IIS Manager can create a URL rewrite rule to route all incoming requests to the server farm automatically.</span></span> <span data-ttu-id="5e021-198">Haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="5e021-198">Click **Yes**.</span></span> <span data-ttu-id="5e021-199">Las reglas se ajustarán manualmente, pero si se selecciona Sí, se establecerá la configuración inicial..</span><span class="sxs-lookup"><span data-stu-id="5e021-199">You will adjust the rules manually, but selecting Yes sets the initial configuration..</span></span>

9.  <span data-ttu-id="5e021-200">Haga clic en el nombre de la granja de servidores que acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="5e021-200">Click the name of the server farm that you have just created.</span></span> <span data-ttu-id="5e021-201">En **granja de servidores** de la vista características del administrador de IIS, haga doble clic en **almacenamiento en caché**.</span><span class="sxs-lookup"><span data-stu-id="5e021-201">Under **Server Farm** in IIS Manager Features View, you double-click **Caching**.</span></span> <span data-ttu-id="5e021-202">Anule la selección de **Habilitar caché de disco**.</span><span class="sxs-lookup"><span data-stu-id="5e021-202">Deselect **Enable disk cache**.</span></span> <span data-ttu-id="5e021-203">Haga clic en **aplicar** en el lado derecho.</span><span class="sxs-lookup"><span data-stu-id="5e021-203">Click **Apply** on the right-hand side.</span></span>

10. <span data-ttu-id="5e021-204">Haga clic en el nombre de la granja de servidores.</span><span class="sxs-lookup"><span data-stu-id="5e021-204">Click the name of the server farm.</span></span> <span data-ttu-id="5e021-205">En **granja de servidores** de la vista características del administrador de IIS, haga doble clic en **proxy**.</span><span class="sxs-lookup"><span data-stu-id="5e021-205">Under **Server Farm** in IIS Manager Features View, you double-click **Proxy**.</span></span> <span data-ttu-id="5e021-206">En la página Configuración de proxy, cambie el valor de **tiempo de espera (segundos)** a un valor apropiado para su implementación.</span><span class="sxs-lookup"><span data-stu-id="5e021-206">On the Proxy settings page change the value for **Time-out (seconds)** to a value appropriate for your deployment.</span></span> <span data-ttu-id="5e021-207">Haga clic en **aplicar** para guardar el cambio.</span><span class="sxs-lookup"><span data-stu-id="5e021-207">Click **Apply** to save the change.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="5e021-208">El valor de tiempo de espera de proxy es un número que variará de una implementación a una implementación.</span><span class="sxs-lookup"><span data-stu-id="5e021-208">The Proxy Time-out value is a number that will vary from deployment to deployment.</span></span> <span data-ttu-id="5e021-209">Debe supervisar la implementación y modificar el valor de la mejor experiencia para los clientes.</span><span class="sxs-lookup"><span data-stu-id="5e021-209">You should monitor your deployment and modify the value for the best experience for clients.</span></span> <span data-ttu-id="5e021-210">Es posible que pueda establecer el valor como mínimo como 200.</span><span class="sxs-lookup"><span data-stu-id="5e021-210">You may be able to set the value as low as 200.</span></span> <span data-ttu-id="5e021-211">Si va a admitir clientes móviles de Lync en su entorno, debe establecer el valor en 960 para permitir el tiempo de espera de notificaciones de inserción desde Office 365 que tenga un valor de tiempo de espera de 900.</span><span class="sxs-lookup"><span data-stu-id="5e021-211">If you are supporting Lync mobile clients in your environment, you should set the value to 960 to allow for push notifications timeout from Office 365 which have a time-out value of 900.</span></span> <span data-ttu-id="5e021-212">Es muy probable que necesite aumentar el valor de tiempo de espera para evitar desconexiones de clientes cuando el valor es demasiado bajo o disminuir el número si las conexiones a través del proxy no se desconectan y se devuelven mucho después de que el cliente se desconecte.</span><span class="sxs-lookup"><span data-stu-id="5e021-212">It is very likely that you will need to increase the time-out value to avoid client disconnects when the value is too low or decrease the number if connections through the proxy do not disconnect and clear long after the client has disconnected.</span></span> <span data-ttu-id="5e021-213">La supervisión y la alineación de base, que es la normal para el entorno, es la única forma precisa de determinar si la configuración correcta es para este valor.</span><span class="sxs-lookup"><span data-stu-id="5e021-213">Monitoring and base-lining what is normal for your environment is the only accurate means to determine where the right setting is for this value.</span></span>

    
    </div>

11. <span data-ttu-id="5e021-214">Haga clic en el nombre de la granja de servidores.</span><span class="sxs-lookup"><span data-stu-id="5e021-214">Click the name of the server farm.</span></span> <span data-ttu-id="5e021-215">En **granja de servidores** de la vista características del administrador de IIS, haga doble clic en **reglas de enrutamiento**.</span><span class="sxs-lookup"><span data-stu-id="5e021-215">Under **Server Farm** in IIS Manager Features View, you double-click **Routing Rules**.</span></span> <span data-ttu-id="5e021-216">En el cuadro de diálogo reglas de enrutamiento, en enrutamiento, desactive la casilla junto a habilitar la descarga de SSL.</span><span class="sxs-lookup"><span data-stu-id="5e021-216">On the Routing Rules dialog under Routing, clear the checkbox next to Enable SSL offloading.</span></span> <span data-ttu-id="5e021-217">Si la posibilidad de desactivar la casilla de verificación no está disponible, marque la casilla de verificación **usar reescritura de URL para inspeccionar las solicitudes entrantes**.</span><span class="sxs-lookup"><span data-stu-id="5e021-217">If the ability to clear the checkbox is not available, select the checkbox for **Use URL Rewrite to inspect incoming requests**.</span></span> <span data-ttu-id="5e021-218">Haga clic en **aplicar** para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="5e021-218">Click **Apply** to save your changes.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="5e021-219">No se admite la descarga de SSL por parte del proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="5e021-219">SSL Offloading by the reverse proxy is not supported.</span></span>

    
    </div>

12. <span data-ttu-id="5e021-220">Repita los pasos 5-11 para cada dirección URL que deba pasar a través del proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="5e021-220">Repeat Steps 5-11 for each URL that must pass through the reverse proxy.</span></span> <span data-ttu-id="5e021-221">Una lista común sería la siguiente:</span><span class="sxs-lookup"><span data-stu-id="5e021-221">A common list would be the following:</span></span>
    
      - <span data-ttu-id="5e021-222">Servicios web del servidor front-end externo: webext.contoso.com (ya configurado por el recorrido inicial)</span><span class="sxs-lookup"><span data-stu-id="5e021-222">Front End Server Web services external: webext.contoso.com (already configured by initial walk through)</span></span>
    
      - <span data-ttu-id="5e021-223">Servicios Web de Director externo para Director: webdirext.contoso.com (opcional si se implementa un director)</span><span class="sxs-lookup"><span data-stu-id="5e021-223">Director Web services external for Director: webdirext.contoso.com (Optional if a Director is deployed)</span></span>
    
      - <span data-ttu-id="5e021-224">Dirección URL sencilla cumplir: meet.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5e021-224">Simple URL meet: meet.contoso.com</span></span>
    
      - <span data-ttu-id="5e021-225">Marcado de dirección URL simple: dialin.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5e021-225">Simple URL dialin: dialin.contoso.com</span></span>
    
      - <span data-ttu-id="5e021-226">Dirección URL de detección automática de Lync: lyncdiscover.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5e021-226">Lync Autodiscover URL: lyncdiscover.contoso.com</span></span>
    
      - <span data-ttu-id="5e021-227">Dirección URL de Office Web Apps Server: officewebapps01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5e021-227">Office Web Apps Server URL: officewebapps01.contoso.com</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="5e021-228">La dirección URL del servidor de Office Web Apps usará una dirección de httpsPort diferente.</span><span class="sxs-lookup"><span data-stu-id="5e021-228">The URL for the Office Web Apps Server will use a different httpsPort address.</span></span> <span data-ttu-id="5e021-229">En el paso 7, defina <STRONG>httpsPort</STRONG> como <STRONG>443</STRONG> y <STRONG>httpPort</STRONG> como puerto <STRONG>80</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="5e021-229">In step 7, you define the <STRONG>httpsPort</STRONG> as <STRONG>443</STRONG> and the <STRONG>httpPort</STRONG> as port <STRONG>80</STRONG>.</span></span> <span data-ttu-id="5e021-230">El resto de las opciones de configuración son iguales.</span><span class="sxs-lookup"><span data-stu-id="5e021-230">All other configuration settings are the same.</span></span>

        
        </div>

13. <span data-ttu-id="5e021-231">En la parte izquierda de la consola, haga clic en el nombre del servidor IIS.</span><span class="sxs-lookup"><span data-stu-id="5e021-231">On the left-hand side of the console, click the IIS server name.</span></span> <span data-ttu-id="5e021-232">En la mitad de la consola, busque **URL Rewrite** en **IIS**.</span><span class="sxs-lookup"><span data-stu-id="5e021-232">In the middle of the console, locate **URL Rewrite** under **IIS**.</span></span> <span data-ttu-id="5e021-233">Haga doble clic en reescribir URL para abrir la configuración de las reglas de reescritura de URL.</span><span class="sxs-lookup"><span data-stu-id="5e021-233">Double-click URL Rewrite to open the URL Rewrite rules configuration.</span></span> <span data-ttu-id="5e021-234">Debe ver las reglas para cada granja de servidores que creó en los pasos anteriores.</span><span class="sxs-lookup"><span data-stu-id="5e021-234">You should see rules for each Server Farm that you created in the previous steps.</span></span> <span data-ttu-id="5e021-235">Si no lo hace, asegúrese de hacer clic en el nombre del **servidor IIS** inmediatamente debajo del nodo **Página de inicio** en la consola del administrador de Internet Information Server.</span><span class="sxs-lookup"><span data-stu-id="5e021-235">If you do not, confirm that you clicked on the **IIS Server** name immediately below the **Start Page** node in the Internet Information Server Manager console.</span></span>

14. <span data-ttu-id="5e021-236">En el cuadro de diálogo de **reescritura de direcciones URL** , con webext.contoso.com como ejemplo, el nombre completo de la regla tal como se muestra es **\_ARR webext.contoso.com\_loadbalance\_SSL**.</span><span class="sxs-lookup"><span data-stu-id="5e021-236">In the **URL Rewrite** dialog, using webext.contoso.com as an example, the full name of the rule as displayed is **ARR\_webext.contoso.com\_loadbalance\_SSL**.</span></span>
    
      - <span data-ttu-id="5e021-237">Haga doble clic en la regla para abrir el cuadro de diálogo **Editar regla de entrada** .</span><span class="sxs-lookup"><span data-stu-id="5e021-237">Double-click the rule to open the **Edit Inbound Rule** dialog.</span></span>
    
      - <span data-ttu-id="5e021-238">Haga clic en **Agregar...**</span><span class="sxs-lookup"><span data-stu-id="5e021-238">Click **Add…**</span></span> <span data-ttu-id="5e021-239">en el cuadro de diálogo **condiciones** .</span><span class="sxs-lookup"><span data-stu-id="5e021-239">on the **Conditions** dialog.</span></span>
    
      - <span data-ttu-id="5e021-240">En la **entrada de condición** de **Agregar condición** :, escriba **{http\_host}**.</span><span class="sxs-lookup"><span data-stu-id="5e021-240">On the **Add Condition** in **Condition input:** type **{HTTP\_HOST}**.</span></span> <span data-ttu-id="5e021-241">(A medida que escribe, aparece un cuadro de diálogo que le permitirá seleccionar la condición).</span><span class="sxs-lookup"><span data-stu-id="5e021-241">(As you type, a dialog appears that will let you select the condition).</span></span> <span data-ttu-id="5e021-242">en **comprobar si la cadena de entrada:** selecciona **coincide con el patrón**.</span><span class="sxs-lookup"><span data-stu-id="5e021-242">under **Check if input string:** select **Matches the Pattern**.</span></span> <span data-ttu-id="5e021-243">En el \*\*\*\* tipo **\*** de entrada de patrón.</span><span class="sxs-lookup"><span data-stu-id="5e021-243">In the **Pattern input** type **\***.</span></span> <span data-ttu-id="5e021-244">Se debe seleccionar **omitir mayúsculas y minúsculas** .</span><span class="sxs-lookup"><span data-stu-id="5e021-244">**Ignore case** should be selected.</span></span> <span data-ttu-id="5e021-245">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5e021-245">Click **OK**.</span></span>
    
      - <span data-ttu-id="5e021-246">Desplácese hacia abajo en el cuadro de diálogo **Editar regla de entrada** para buscar el cuadro de diálogo de **acción** .</span><span class="sxs-lookup"><span data-stu-id="5e021-246">Scroll down in the **Edit Inbound Rule** dialog to locate the **Action** dialog.</span></span> <span data-ttu-id="5e021-247">**Tipo de acción:** debe establecerse en **enrutar a granja de servidores**, **esquema:** set en **https://**, **granja de servidores:** establezca en la dirección URL a la que se aplica esta regla.</span><span class="sxs-lookup"><span data-stu-id="5e021-247">**Action Type:** should be set to **Route to Server Farm**, **Scheme:** set to **https://**, **Server farm:** set to the URL that this rule applies to.</span></span> <span data-ttu-id="5e021-248">Para este ejemplo, debe establecerse en **webext.contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="5e021-248">For this example, this should be set to **webext.contoso.com**.</span></span> <span data-ttu-id="5e021-249">**Path:** se establece en **/{R: 0}**</span><span class="sxs-lookup"><span data-stu-id="5e021-249">**Path:** is set to **/{R:0}**</span></span>
    
      - <span data-ttu-id="5e021-250">Haga clic en **aplicar** para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="5e021-250">Click **Apply** to save your changes.</span></span> <span data-ttu-id="5e021-251">Haga clic en **volver a reglas** para volver a las reglas de reescritura de direcciones URL.</span><span class="sxs-lookup"><span data-stu-id="5e021-251">Click **Back to Rules** to return to the URL Rewrite rules.</span></span>

15. <span data-ttu-id="5e021-252">Repita el procedimiento definido en el paso 14 para cada una de las reglas de reescritura de SSL que haya definido, una por dirección URL de granja de servidores.</span><span class="sxs-lookup"><span data-stu-id="5e021-252">Repeat the procedure defined in Step 14 for each of the SSL rewrite rules that you have defined, one per Server Farm URL.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="5e021-253">De forma predeterminada, las reglas HTTP también se crean y se indican mediante nombres similares a las reglas de SSL.</span><span class="sxs-lookup"><span data-stu-id="5e021-253">By default, HTTP rules are created as well and are denoted by the similar naming to the SSL rules.</span></span> <span data-ttu-id="5e021-254">En nuestro ejemplo actual, la regla HTTP se denominaría <STRONG>ARR_webext. contoso. com_loadbalance</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="5e021-254">For our current example, the HTTP rule would be named <STRONG>ARR_webext.contoso.com_loadbalance</STRONG>.</span></span> <span data-ttu-id="5e021-255">No es necesario realizar modificaciones en estas reglas, por lo que se pueden ignorar sin problemas.</span><span class="sxs-lookup"><span data-stu-id="5e021-255">No modifications are needed to these rules and they can be safely ignored.</span></span>

    
    </div>

</div>

<div>

## <a name="to-modify-the-properties-of-the-web-publishing-rule-in-tmg-2010"></a><span data-ttu-id="5e021-256">Para modificar las propiedades de la regla de publicación web en TMG 2010</span><span class="sxs-lookup"><span data-stu-id="5e021-256">To modify the properties of the web publishing rule in TMG 2010</span></span>

1.  <span data-ttu-id="5e021-257">Haga clic en **Inicio**, elija **programas**, seleccione **Microsoft Forefront TMG**y, a continuación, haga clic en administración de **Forefront TMG**.</span><span class="sxs-lookup"><span data-stu-id="5e021-257">Click **Start**, point to **Programs**, select **Microsoft Forefront TMG**, and then click **Forefront TMG Management**.</span></span>

2.  <span data-ttu-id="5e021-258">En el panel izquierdo, expanda **NombreDeServidor** y haga clic en **Directiva de firewall**.</span><span class="sxs-lookup"><span data-stu-id="5e021-258">In the left pane, expand **ServerName**, and then click **Firewall Policy**.</span></span>

3.  <span data-ttu-id="5e021-259">En el panel de detalles, haga clic con el botón secundario en la regla de publicación de servidor web que ha creado en el procedimiento anterior (por ejemplo, ReglaExternaLyncServer) y, a continuación, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="5e021-259">In the details pane, right-click the web server publishing rule that you created in the previous procedure (for example, LyncServerExternalRule), and then click **Properties**.</span></span>

4.  <span data-ttu-id="5e021-260">En la página **Propiedades**, en la pestaña **Desde**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5e021-260">On the **Properties** page, on the **From** tab, do the following:</span></span>
    
      - <span data-ttu-id="5e021-261">En la lista **Esta regla se aplica al tráfico de estos orígenes**, haga clic en **En cualquier lugar** y, a continuación, haga clic en **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="5e021-261">In the **This rule applies to traffic from these sources** list, click **Anywhere**, and then click **Remove**.</span></span>
    
      - <span data-ttu-id="5e021-262">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="5e021-262">Click **Add**.</span></span>
    
      - <span data-ttu-id="5e021-263">En **Agregar entidades de red**, expanda **Redes**, haga clic en **Externa**, haga clic en **Agregar** y, a continuación, haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="5e021-263">In **Add Network Entities**, expand **Networks**, click **External**, click **Add**, and then click **Close**.</span></span>

5.  <span data-ttu-id="5e021-264">En la pestaña **Para**, compruebe que está activada la casilla **Reenviar el encabezado de host original en lugar del real**.</span><span class="sxs-lookup"><span data-stu-id="5e021-264">On the **To** tab, ensure that the **Forward the original host header instead of the actual one** check box is selected.</span></span>

6.  <span data-ttu-id="5e021-265">En la pestaña **Protocolo de puente**, active la casilla **Redirigir la solicitud al puerto SSL** y, a continuación, especifique el puerto **4443**.</span><span class="sxs-lookup"><span data-stu-id="5e021-265">On the **Bridging** tab, select the **Redirect request to SSL port** check box, and then specify port **4443**.</span></span>

7.  <span data-ttu-id="5e021-266">En la pestaña **Nombre público**, agregue las URL sencillas (por ejemplo, meet.contoso.com y dialin.contoso.com).</span><span class="sxs-lookup"><span data-stu-id="5e021-266">On the **Public Name** tab, add the simple URLs (for example, meet.contoso.com and dialin.contoso.com).</span></span>

8.  <span data-ttu-id="5e021-267">Haga clic en **Aplicar** para guardar los cambios y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5e021-267">Click **Apply** to save changes, and then click **OK**.</span></span>

9.  <span data-ttu-id="5e021-268">Haga clic en **Aplicar** en el panel de detalles para guardar los cambios y actualizar la configuración.</span><span class="sxs-lookup"><span data-stu-id="5e021-268">Click **Apply** in the details pane to save the changes and update the configuration.</span></span>

</div>

<div>

## <a name="to-modify-the-properties-of-the-web-publishing-rule-in-iis-arr"></a><span data-ttu-id="5e021-269">Para modificar las propiedades de la regla de publicación web en IIS ARR</span><span class="sxs-lookup"><span data-stu-id="5e021-269">To modify the properties of the web publishing rule in IIS ARR</span></span>

1.  <span data-ttu-id="5e021-270">Haga clic en **Inicio**, seleccione **programas**, seleccione **herramientas administrativas**y, a continuación, haga clic en **Administrador de Internet Information Services (IIS)**.</span><span class="sxs-lookup"><span data-stu-id="5e021-270">Click **Start**, select **Programs**, select **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>

2.  <span data-ttu-id="5e021-271">En la parte izquierda de la consola, haga clic en el nombre del servidor IIS.</span><span class="sxs-lookup"><span data-stu-id="5e021-271">On the left-hand side of the console, click the IIS server name.</span></span>

3.  <span data-ttu-id="5e021-272">En la mitad de la consola, busque **URL Rewrite** en **IIS**.</span><span class="sxs-lookup"><span data-stu-id="5e021-272">In the middle of the console, locate **URL Rewrite** under **IIS**.</span></span> <span data-ttu-id="5e021-273">Haga doble clic en reescribir URL para abrir la configuración de las reglas de reescritura de URL.</span><span class="sxs-lookup"><span data-stu-id="5e021-273">Double-click URL Rewrite to open the URL Rewrite rules configuration.</span></span>

4.  <span data-ttu-id="5e021-274">Haga doble clic en la regla que debe modificar.</span><span class="sxs-lookup"><span data-stu-id="5e021-274">Double-click the rule that you need to modify.</span></span> <span data-ttu-id="5e021-275">Realice las modificaciones que sean necesarias en la **dirección URL**, **las condiciones**, **las variables de servidor** o la **acción**de coincidencia.</span><span class="sxs-lookup"><span data-stu-id="5e021-275">Make your modifications, as needed, in **Match URL**, **Conditions**, **Server Variables** or **Action**.</span></span>

5.  <span data-ttu-id="5e021-276">Haga clic en **aplicar** para confirmar los cambios.</span><span class="sxs-lookup"><span data-stu-id="5e021-276">Click **Apply** to commit your changes.</span></span> <span data-ttu-id="5e021-277">Haga clic en **volver a reglas** para modificar otras reglas o cierre la consola del **Administrador de IIS** si ha terminado con los cambios.</span><span class="sxs-lookup"><span data-stu-id="5e021-277">Click **Back to Rules** to modify other rules, or close the **IIS Manager** console if you are done with your changes.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

