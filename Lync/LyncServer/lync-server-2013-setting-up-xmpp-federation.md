---
title: 'Lync Server 2013: Configurar la federación XMPP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up XMPP federation
ms:assetid: 5fda6cb7-8d4d-495d-90c7-601f1036e085
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204939(v=OCS.15)
ms:contentKeyID: 48184270
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6bad6bf4e2b09296e21aec75e206ba867415754a
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992055"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="b3152-102">Configurar la federación XMPP en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b3152-102">Setting up XMPP federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b3152-103">_**Última modificación del tema:** 2012-12-03_</span><span class="sxs-lookup"><span data-stu-id="b3152-103">_**Topic Last Modified:** 2012-12-03_</span></span>

<span data-ttu-id="b3152-104">Para implementar el proxy XMPP en el servidor perimetral, debe configurar el servidor perimetral para la Federación de XMPP.</span><span class="sxs-lookup"><span data-stu-id="b3152-104">To deploy the XMPP Proxy on the Edge Server, you must configure the Edge Server for XMPP federation.</span></span> <span data-ttu-id="b3152-105">Para ello, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="b3152-105">To do this, you do the following steps.</span></span>

<div>

## <a name="setting-up-xmpp-federation"></a><span data-ttu-id="b3152-106">Configuración de la Federación XMPP</span><span class="sxs-lookup"><span data-stu-id="b3152-106">Setting Up XMPP Federation</span></span>

1.  <span data-ttu-id="b3152-107">Inicie sesión en el equipo donde está instalado el Asistente para la implementación de Lync Server como miembro del grupo administradores de dominio y el grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="b3152-107">Log on to the computer where the Lync Server Deployment Wizard is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="b3152-108">En el servidor front-end, abra el Asistente para la implementación de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b3152-108">On the Front End server, open the Lync Server Deployment wizard.</span></span> <span data-ttu-id="b3152-109">Haga clic en instalar o actualizar el sistema Lync Server y, a continuación, haga clic en configurar o quitar los componentes de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b3152-109">Click Install or Update Lync Server System, then click Setup or Remove Lync Server Components.</span></span> <span data-ttu-id="b3152-110">Vuelva a hacer clic en ejecutar.</span><span class="sxs-lookup"><span data-stu-id="b3152-110">Click Run Again.</span></span>

3.  <span data-ttu-id="b3152-111">En instalación de los componentes de Lync Server, haga clic en siguiente.</span><span class="sxs-lookup"><span data-stu-id="b3152-111">At Setup Lync Server components, click Next.</span></span> <span data-ttu-id="b3152-112">La pantalla resumen mostrará las acciones a medida que se ejecutan.</span><span class="sxs-lookup"><span data-stu-id="b3152-112">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="b3152-113">Una vez que haya finalizado la implementación, haga clic en Ver registro para ver los archivos de registro disponibles.</span><span class="sxs-lookup"><span data-stu-id="b3152-113">Once the deployment is done, click View Log to view available log files.</span></span> <span data-ttu-id="b3152-114">Haga clic en finalizar para completar la implementación.</span><span class="sxs-lookup"><span data-stu-id="b3152-114">Click Finish to complete the deployment.</span></span>

4.  <span data-ttu-id="b3152-115">En el servidor perimetral, abra el Asistente para la implementación de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b3152-115">On the Edge server, open the Lync Server Deployment wizard.</span></span> <span data-ttu-id="b3152-116">Haga clic en instalar o actualizar el sistema Lync Server y, a continuación, haga clic en configurar o quitar los componentes de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b3152-116">Click Install or Update Lync Server System, then click Setup or Remove Lync Server Components.</span></span> <span data-ttu-id="b3152-117">Vuelva a hacer clic en ejecutar.</span><span class="sxs-lookup"><span data-stu-id="b3152-117">Click Run Again.</span></span>

5.  <span data-ttu-id="b3152-118">En instalación de los componentes de Lync Server, haga clic en siguiente.</span><span class="sxs-lookup"><span data-stu-id="b3152-118">At Setup Lync Server components, click Next.</span></span> <span data-ttu-id="b3152-119">La pantalla resumen mostrará las acciones a medida que se ejecutan.</span><span class="sxs-lookup"><span data-stu-id="b3152-119">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="b3152-120">Una vez que haya finalizado la implementación, haga clic en Ver registro para ver los archivos de registro disponibles.</span><span class="sxs-lookup"><span data-stu-id="b3152-120">Once the deployment is done, click View Log to view available log files.</span></span> <span data-ttu-id="b3152-121">Haga clic en finalizar para completar la implementación.</span><span class="sxs-lookup"><span data-stu-id="b3152-121">Click Finish to complete the deployment.</span></span>

6.  <span data-ttu-id="b3152-122">En el servidor perimetral, en el Asistente para la implementación, junto al paso 3: solicitar, instalar o asignar certificados, haga clic en ejecutar de nuevo.</span><span class="sxs-lookup"><span data-stu-id="b3152-122">On the Edge Server, in the Deployment Wizard, next to Step 3: Request, Install, or Assign Certificates, click Run again.</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="b3152-123">Si está implementando el servidor perimetral por primera vez, verá ejecutar en lugar de volver a ejecutar.</span><span class="sxs-lookup"><span data-stu-id="b3152-123">If you are deploying the Edge Server for the first time, you will see Run instead of Run Again.</span></span>

    
    </div>

7.  <span data-ttu-id="b3152-124">En la página Tareas de certificado disponibles, haga clic en Crear una nueva solicitud de certificado.</span><span class="sxs-lookup"><span data-stu-id="b3152-124">On the Available Certificate Tasks page, click Create a new certificate request.</span></span>

8.  <span data-ttu-id="b3152-125">En la página solicitud de certificado, haga clic en certificado de borde externo.</span><span class="sxs-lookup"><span data-stu-id="b3152-125">On the Certificate Request page, click External Edge Certificate.</span></span>

9.  <span data-ttu-id="b3152-126">En la página solicitud inmediata o demorada, active la casilla preparar la solicitud ahora pero enviarla más tarde.</span><span class="sxs-lookup"><span data-stu-id="b3152-126">On the Delayed or Immediate Request page, select the Prepare the request now, but send it later check box.</span></span>

10. <span data-ttu-id="b3152-127">En la página archivo de solicitud de certificado, escriba la ruta de acceso completa y el nombre del archivo en el que se va a guardar la solicitud (por\\ejemplo\_,\_c: CERT la Edge. cer).</span><span class="sxs-lookup"><span data-stu-id="b3152-127">On the Certificate Request File page, type the full path and file name of the file to which the request is to be saved (for example, c:\\cert\_exernal\_edge.cer).</span></span>

11. <span data-ttu-id="b3152-128">En la página especificar plantilla de certificado alternativa, para usar una plantilla distinta de la plantilla predeterminada de WebServer, seleccione la casilla Usar plantilla de certificado alternativa para la entidad emisora de certificados seleccionada.</span><span class="sxs-lookup"><span data-stu-id="b3152-128">On the Specify Alternate Certificate Template page, to use a template other than the default WebServer template, select the Use alternative certificate template for the selected certification authority check box.</span></span>

12. <span data-ttu-id="b3152-129">En la página   Nombre y configuración de seguridad, siga este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="b3152-129">On the Name and Security Settings page, do the following:</span></span>
    
    1.  <span data-ttu-id="b3152-130">En nombre descriptivo, escriba un nombre para mostrar para el certificado.</span><span class="sxs-lookup"><span data-stu-id="b3152-130">In Friendly name, type a display name for the certificate</span></span>
    
    2.  <span data-ttu-id="b3152-131">En longitud bit, especifique la longitud en bits (normalmente, el valor predeterminado de 2048).</span><span class="sxs-lookup"><span data-stu-id="b3152-131">In Bit length, specify the bit length (typically, the default of 2048)</span></span>
    
    3.  <span data-ttu-id="b3152-132">Compruebe que la casilla marcar clave privada de certificado como exportable está seleccionada</span><span class="sxs-lookup"><span data-stu-id="b3152-132">Verify that the Mark certificate private key as exportable check box is selected</span></span>

13. <span data-ttu-id="b3152-133">En la página información de la organización, escriba el nombre de la organización y la unidad organizativa (por ejemplo, una división o un departamento).</span><span class="sxs-lookup"><span data-stu-id="b3152-133">On the Organization Information page, type the name for the organization and the organizational unit (for example, a division or department)</span></span>

14. <span data-ttu-id="b3152-134">En la página información geográfica, especifique la información de ubicación</span><span class="sxs-lookup"><span data-stu-id="b3152-134">On the Geographical Information page, specify the location information</span></span>

15. <span data-ttu-id="b3152-135">En la página nombre de sujeto/nombres alternativos de asunto, se muestra la información que el asistente rellenará automáticamente.</span><span class="sxs-lookup"><span data-stu-id="b3152-135">On the Subject Name/Subject Alternate Names page, the information to be automatically populated by the wizard is displayed.</span></span> <span data-ttu-id="b3152-136">Si se necesitan nombres alternativos de asunto adicionales, debe especificarlos en los dos pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="b3152-136">If additional subject alternative names are needed, you specify them in the next two steps</span></span>

16. <span data-ttu-id="b3152-137">En la página Configuración del dominio SIP en la página de nombres alternativos de asunto (San), seleccione la casilla dominio para agregar un SIP. \<sipdomain\> entrada a la lista de nombres alternativos de asunto.</span><span class="sxs-lookup"><span data-stu-id="b3152-137">On the SIP Domain Setting on Subject Alternate Names (SANs) page, select the domain check box to add a sip.\<sipdomain\> entry to the subject alternative names list.</span></span>

17. <span data-ttu-id="b3152-138">En la página configurar otros nombres alternativos de asunto, especifique los nombres alternativos de asunto adicionales necesarios</span><span class="sxs-lookup"><span data-stu-id="b3152-138">On the Configure Additional Subject Alternate Names page, specify any additional subject alternative names that are required</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="b3152-139">Si el proxy XMPP está instalado, de forma predeterminada, el nombre de dominio (por ejemplo, contoso.com) se rellena en las entradas SAN.</span><span class="sxs-lookup"><span data-stu-id="b3152-139">If the XMPP proxy is installed, by default the domain name (such as contoso.com) is populated in the SAN entries.</span></span> <span data-ttu-id="b3152-140">Si necesita más entradas, agréguelos en este paso.</span><span class="sxs-lookup"><span data-stu-id="b3152-140">If you require more entries, add them in this step.</span></span>

    
    </div>

18. <span data-ttu-id="b3152-141">En la página solicitar Resumen, revise la información del certificado que se va a usar para generar la solicitud.</span><span class="sxs-lookup"><span data-stu-id="b3152-141">On the Request Summary page, review the certificate information to be used to generate the request.</span></span>

19. <span data-ttu-id="b3152-142">Cuando termine de ejecutarse los comandos, puede ver el registro o hacer clic en siguiente para continuar.</span><span class="sxs-lookup"><span data-stu-id="b3152-142">After the commands finish running, you can View Log, or click Next to continue.</span></span>

20. <span data-ttu-id="b3152-143">En la página de archivo de solicitud de certificado, puede ver el archivo de solicitud de firma de certificado generado (CSR) haciendo clic en ver o salir del asistente de certificados haciendo clic en finalizar.</span><span class="sxs-lookup"><span data-stu-id="b3152-143">On the Certificate Request File page, you can view the generated certificate signing request (CSR) file by clicking View or exit the Certificate Wizard by clicking Finish.</span></span>

21. <span data-ttu-id="b3152-144">Copie el archivo de solicitud y envíelo a la entidad emisora de certificados pública.</span><span class="sxs-lookup"><span data-stu-id="b3152-144">Copy the request file and submit to your public certification authority.</span></span>

22. <span data-ttu-id="b3152-145">Después de recibir, importar y asignar el certificado público, debe detener y reiniciar los servicios del servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="b3152-145">After receiving, importing and assigning the public certificate, you must stop and restart the Edge Server services.</span></span> <span data-ttu-id="b3152-146">Esto se hace escribiendo en la consola de administración de Lync Server:</span><span class="sxs-lookup"><span data-stu-id="b3152-146">You do this by typing in the Lync Server Management console:</span></span>
    
       ```PowerShell
        Stop-CsWindowsService
       ```
    
       ```PowerShell
        Start-CsWindowsService
       ```

23. <span data-ttu-id="b3152-147">Para configurar DNS para la Federación XMPP, agregue el siguiente registro SRV a DNS externo:\_XMPP-Server. \_TCP. \<nombre\> de dominio el registro SRV se resolverá en el FQDN perimetral de acceso del servidor perimetral, con un valor de puerto de 5269.</span><span class="sxs-lookup"><span data-stu-id="b3152-147">To configure DNS for XMPP federation, you add the following SRV record to external DNS:\_xmpp-server.\_tcp.\<domain name\> The SRV record will resolve to the access edge FQDN of the Edge server, with a port value of 5269.</span></span> <span data-ttu-id="b3152-148">Además, puede configurar un registro de host ' A ' (por ejemplo, xmpp.contoso.com) que apunte a la dirección IP del servidor perimetral de acceso.</span><span class="sxs-lookup"><span data-stu-id="b3152-148">Additionally, you configure an ‘A’ host record (for example, xmpp.contoso.com) that points to the IP address of the Access Edge Server.</span></span>
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="b3152-149">Si tiene grupos de bordes en varios sitios, le recomendamos que agregue varios registros SRV para la Federación XMPP.</span><span class="sxs-lookup"><span data-stu-id="b3152-149">If you have Edge pools in multiple sites, we recommend that you add multiple SRV records for XMPP federation.</span></span> <span data-ttu-id="b3152-150">Agregue un registro SRV para cada grupo perimetral de su organización y asigne una prioridad diferente a cada uno de los registros SRV.</span><span class="sxs-lookup"><span data-stu-id="b3152-150">Add a SRV record for every Edge pool in your organization, and give each of those SRV records a different priority.</span></span> <span data-ttu-id="b3152-151">Cuando se ejecutan todos los grupos de bordes, las solicitudes XMPP se gestionarán en el grupo Edge con la primera prioridad, pero si ese grupo de Edge deja de funcionar, no tendrá que agregar un nuevo registro SRV para recuperar la funcionalidad de Federación de XMPP.</span><span class="sxs-lookup"><span data-stu-id="b3152-151">When all Edge pools are running, XMPP requests will all be handled by the Edge pool with the first priority, but if that Edge pool goes down you won’t then have to add a new SRV record to regain XMPP federation functionality.</span></span>

    
    </div>

24. <span data-ttu-id="b3152-152">Configure una nueva Directiva de acceso externo para habilitar a todos los usuarios abriendo el shell de administración de Lync Server en el front-end y escribiendo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b3152-152">Configure a new External Access Policy to enable all users by opening the Lync Server Management Shell on the Front End and typing:</span></span>
    
       ```PowerShell
        New-CsExternalAccessPolicy -Identity <name of policy to create.  If site scope, prepend with 'site:'> -EnableFederationAcces $true -EnablePublicCloudAccess $true
       ```
    
       ```PowerShell
        New-CsExternalAccessPolicy -Identity FedPic -EnableFederationAcces $true -EnablePublicCloudAccess $true
       ```
    
       ```PowerShell
        Get-CsUser | Grant-CsExternalAccessPolicy -PolicyName FedPic
       ```
    
    <span data-ttu-id="b3152-153">Habilite el acceso XMPP para los usuarios externos escribiendo:</span><span class="sxs-lookup"><span data-stu-id="b3152-153">Enable XMPP Access for External Users by typing:</span></span>
    
       ```PowerShell
        Set-CsExternalAccessPolicy -Identity <name of the policy being used> EnableXmppAccess $true
       ```
    
       ```PowerShell
        Set-CsExternalAccessPolicy -Identity FedPic -EnableXmppAccess $true
       ```

25. <span data-ttu-id="b3152-154">En el servidor perimetral donde se implementa el proxy XMPP, abra un símbolo del sistema o una interfaz de línea de comandos de Windows PowerShell™ y escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b3152-154">On the Edge Server where the XMPP Proxy is deployed, open a Command Prompt or a Windows PowerShell™ command-line interface and type the following:</span></span>
    
       ```PowerShell
        Netstat -ano | findstr 5269
       ```
    
       ```PowerShell
        Netstat -ano | findstr 23456
       ```
    
    <span data-ttu-id="b3152-155">El comando **netstat – ano** es un comando de estadísticas de red, los parámetros **– ano** solicitar que netstat muestre todas las conexiones y los puertos de escucha, la dirección y los puertos se muestran en un formato numérico, y que el identificador del proceso propietario está asociado con cada conexión.</span><span class="sxs-lookup"><span data-stu-id="b3152-155">The command **netstat –ano** is a network statistics command, the parameters **–ano** request that netstat display all connections and listening ports, address and ports are displayed in a numerical form, and that the owning process ID is associated with each connection.</span></span> <span data-ttu-id="b3152-156">El carácter **|** define una canalización para el siguiente comando, **Findstr**o Find String.</span><span class="sxs-lookup"><span data-stu-id="b3152-156">The character **|** defines a pipe to the next command, **findstr**, or find string.</span></span> <span data-ttu-id="b3152-157">El número 5269 y 23456 que se pasa a Findstr como parámetro indica a Findstr que busque en la salida de netstat las cadenas 5269 y 23456.</span><span class="sxs-lookup"><span data-stu-id="b3152-157">The number 5269 and 23456 that is passed to findstr as a parameter instructs findstr to search the output of netstat for the strings 5269 and 23456.</span></span> <span data-ttu-id="b3152-158">Si XMPP está configurado correctamente, el resultado de los comandos debe dar como resultado conexiones y conexiones establecidas, tanto en la interfaz externa (puerto 5269) como en la interfaz interna (puerto 23456) del servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="b3152-158">If XMPP is correctly configured, the result of the commands should result in listening and established connections, both on the external (port 5269) and the internal (port 23456) interfaces of the Edge Server.</span></span>
    
    <span data-ttu-id="b3152-159">Si los comandos no devuelven puertos establecidos o que atienden en 5269 y 23456, compruebe lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b3152-159">If the commands do not return established or listening ports on 5269 and 23456, check the following:</span></span>

</div>

<div>

## <a name="troubleshooting-xmpp-federation"></a><span data-ttu-id="b3152-160">Solución de problemas de Federación de XMPP</span><span class="sxs-lookup"><span data-stu-id="b3152-160">Troubleshooting XMPP Federation</span></span>

1.  <span data-ttu-id="b3152-161">Para determinar si el proxy XMPP se está ejecutando, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b3152-161">To determine if the XMPP Proxy is running, do the following:</span></span>

2.  <span data-ttu-id="b3152-162">Inicie sesión en el servidor perimetral que está ejecutando el servicio de proxy XMPP como miembro del grupo de administradores locales.</span><span class="sxs-lookup"><span data-stu-id="b3152-162">Log on to the Edge server that is running the XMPP Proxy service as a member of the local administrator’s group.</span></span>

3.  <span data-ttu-id="b3152-163">Haga clic en **Inicio**, en **todos los programas**, en **herramientas administrativas**y en **servicios** .</span><span class="sxs-lookup"><span data-stu-id="b3152-163">Click **Start**, click **All Programs**, click **Administrative Tools**, click **Services**</span></span>

4.  <span data-ttu-id="b3152-164">En servicios, localice el proxy de puerta de enlace de Lync Server XMPP.</span><span class="sxs-lookup"><span data-stu-id="b3152-164">In Services, locate Lync Server XMPP Translating Gateway Proxy.</span></span> <span data-ttu-id="b3152-165">El servicio debe estar en estado de **Inicio** .</span><span class="sxs-lookup"><span data-stu-id="b3152-165">The service should be in the **Started** state.</span></span> <span data-ttu-id="b3152-166">Si no se ha iniciado, haga clic en el icono **Inicio** de la barra de herramientas.</span><span class="sxs-lookup"><span data-stu-id="b3152-166">If it is not started, click the **Start** icon in the toolbar.</span></span> <span data-ttu-id="b3152-167">El icono aparece como una flecha verde que señala hacia la derecha.</span><span class="sxs-lookup"><span data-stu-id="b3152-167">The icon appears as a green, right-pointing arrow.</span></span>

5.  <span data-ttu-id="b3152-168">Confirme que el servicio ha cambiado a **iniciado**.</span><span class="sxs-lookup"><span data-stu-id="b3152-168">Confirm that the service has changed to **Started**.</span></span> <span data-ttu-id="b3152-169">Si se ha iniciado correctamente, cierra **servicios** y continúa.</span><span class="sxs-lookup"><span data-stu-id="b3152-169">If it has successfully started, close **Services** and continue.</span></span>
    
    <span data-ttu-id="b3152-170">Si el servicio no se ha iniciado correctamente, en herramientas administrativas, abra visor de eventos y consulte los errores y advertencias en la parte de **Lync Server** en **registros de aplicaciones y servicios**.</span><span class="sxs-lookup"><span data-stu-id="b3152-170">If ther service has not successfully started, from Administrative Tools, open Event Viewer and refer to the errors and warnings in the **Lync Server** portion under **Applications and Services Logs**.</span></span>

6.  <span data-ttu-id="b3152-171">Una vez que se esté ejecutando el servicio de **puerta de enlace de Lync Server XMPP** , vuelva a comprobar los comandos netstat usados previamente.</span><span class="sxs-lookup"><span data-stu-id="b3152-171">Once the **Lync Server XMPP Translating Gateway** service is running, recheck the netstat commands used previously.</span></span> <span data-ttu-id="b3152-172">Si no ve las sesiones de establecimiento o escucha, compruebe y asegúrese de que la **ruta de Federación de XMPP** esté correctamente configurada en el generador de topología</span><span class="sxs-lookup"><span data-stu-id="b3152-172">If you are not seeing established or listening sessions, check and ensure that the **XMPP Federation Route** is correctly configured in Topology Builder</span></span>

7.  <span data-ttu-id="b3152-173">Inicie sesión en el equipo donde se encuentre instalado el Generador de topologías como miembro del grupo Administradores del dominio y el grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="b3152-173">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

8.  <span data-ttu-id="b3152-174">Iniciar generador de topología: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topología de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="b3152-174">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

9.  <span data-ttu-id="b3152-175">En el generador de topologías, seleccione el sitio de la ruta y revisión de la Federación XMPP para confirmar que la asignación de enrutamiento de la **Federación de sitios** para la **Federación XMPP** muestra el servidor perimetral o el grupo perimetral como la asignación de ruta de Federación XMPP seleccionada.</span><span class="sxs-lookup"><span data-stu-id="b3152-175">In Topology Builder, select the site for the XMPP federation route and review to confirm that the **Site federation route assignment** for **XMPP federation** shows your Edge Server or Edge pool as the selected XMPP federation route assignment.</span></span>
    
    <span data-ttu-id="b3152-176">Si la asignación de ruta es incorrecta o no está configurada, haga clic con el botón secundario en el sitio y haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="b3152-176">If the route assignment is incorrect or is not set, right-click the site, click **Edit Properties**.</span></span> <span data-ttu-id="b3152-177">Seleccione la casilla Federación de XMPP y, a continuación, seleccione el servidor perimetral o el grupo de límites correctos.</span><span class="sxs-lookup"><span data-stu-id="b3152-177">Select the XMPP federation check box and then select the correct Edge Server or Edge pool.</span></span>

10. <span data-ttu-id="b3152-178">Publique la topología.</span><span class="sxs-lookup"><span data-stu-id="b3152-178">Publish the topology.</span></span> <span data-ttu-id="b3152-179">Para obtener más información, vea [publicar una topología en Lync Server 2013](lync-server-2013-publish-your-topology.md)</span><span class="sxs-lookup"><span data-stu-id="b3152-179">For details, see [Publish your topology in Lync Server 2013](lync-server-2013-publish-your-topology.md)</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="b3152-180">Aunque no es obligatorio y generalmente no es necesario, es posible que tenga que reiniciar los servidores perimetrales</span><span class="sxs-lookup"><span data-stu-id="b3152-180">Though not required and typically not necessary, you may find that you will need to restart the Edge Servers</span></span>

    
    </div>

11. <span data-ttu-id="b3152-181">Con el proceso de netstat usado anteriormente, confirme que el servidor perimetral está escuchando o ha establecido sesiones en el puerto 5269 y en el puerto 23456.</span><span class="sxs-lookup"><span data-stu-id="b3152-181">Using the netstat process used previously, confirm that the Edge Server is now listening or has established sessions on port 5269 and port 23456.</span></span>

12. <span data-ttu-id="b3152-182">Si sigue sin ver las sesiones esperadas, compruebe en el visor de eventos si se producen posibles causas de contribución por el problema de comunicación.</span><span class="sxs-lookup"><span data-stu-id="b3152-182">If you still are not seeing the expected sessions, check the Event Viewer for possible contributing causes for the communication problem.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b3152-183">Vea también</span><span class="sxs-lookup"><span data-stu-id="b3152-183">See Also</span></span>


[<span data-ttu-id="b3152-184">Configuración XMPP de ejemplo en Lync Server 2013 - Federación XMPP con Google Talk</span><span class="sxs-lookup"><span data-stu-id="b3152-184">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</span></span>](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[<span data-ttu-id="b3152-185">Administrar socios federados XMPP para su organización en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b3152-185">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

