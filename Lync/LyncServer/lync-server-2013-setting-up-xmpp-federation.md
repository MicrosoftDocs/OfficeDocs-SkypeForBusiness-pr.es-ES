---
title: 'Lync Server 2013: configuración de la Federación XMPP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up XMPP federation
ms:assetid: 5fda6cb7-8d4d-495d-90c7-601f1036e085
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204939(v=OCS.15)
ms:contentKeyID: 48184270
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4cb6b2904ee2a8883c492e570173e73bc001cc03
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48497527"
---
# <a name="setting-up-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="932ea-102">Configuración de la Federación XMPP en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="932ea-102">Setting up XMPP federation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="932ea-103">_**Última modificación del tema:** 2012-12-03_</span><span class="sxs-lookup"><span data-stu-id="932ea-103">_**Topic Last Modified:** 2012-12-03_</span></span>

<span data-ttu-id="932ea-p101">Para implementar el proxy XMPP en el servidor perimetral, debe configurar el servidor perimetral para la federación de XMPP. Para ello, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="932ea-p101">To deploy the XMPP Proxy on the Edge Server, you must configure the Edge Server for XMPP federation. To do this, you do the following steps.</span></span>

<div>

## <a name="setting-up-xmpp-federation"></a><span data-ttu-id="932ea-106">Configuración de la federación de XMPP</span><span class="sxs-lookup"><span data-stu-id="932ea-106">Setting Up XMPP Federation</span></span>

1.  <span data-ttu-id="932ea-107">Inicie sesión en el equipo en el que el asistente para la implementación de Lync Server esté instalado como miembro del grupo Admins. del dominio y el grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="932ea-107">Log on to the computer where the Lync Server Deployment Wizard is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="932ea-p102">En el servidor front-end, abra al Asistente para implementación de Lync Server. Haga clic en Instalar o actualizar el sistema Lync Server y, a continuación, haga clic en Instalar o desinstalar componentes de Lync Server. Haga clic en Ejecutar de nuevo.</span><span class="sxs-lookup"><span data-stu-id="932ea-p102">On the Front End server, open the Lync Server Deployment wizard. Click Install or Update Lync Server System, then click Setup or Remove Lync Server Components. Click Run Again.</span></span>

3.  <span data-ttu-id="932ea-p103">En Instalar componentes de Lync Server, haga clic en Siguiente. La pantalla de resumen mostrará las acciones a medida que se ejecutan. Una vez realizada la implementación, haga clic en Ver registro para ver los archivos de registro disponibles. Haga clic en Finalizar para completar la implementación.</span><span class="sxs-lookup"><span data-stu-id="932ea-p103">At Setup Lync Server components, click Next. The summary screen will show actions as they are executed. Once the deployment is done, click View Log to view available log files. Click Finish to complete the deployment.</span></span>

4.  <span data-ttu-id="932ea-p104">En el servidor perimetral, abra el Asistente para implementación de Lync Server. Haga clic en Instalar o actualizar el sistema Lync Server y, a continuación, haga clic en Instalar o desinstalar componentes de Lync Server. Haga clic en Ejecutar de nuevo.</span><span class="sxs-lookup"><span data-stu-id="932ea-p104">On the Edge server, open the Lync Server Deployment wizard. Click Install or Update Lync Server System, then click Setup or Remove Lync Server Components. Click Run Again.</span></span>

5.  <span data-ttu-id="932ea-p105">En Instalar componentes de Lync Server, haga clic en Siguiente. La pantalla de resumen mostrará las acciones a medida que se ejecutan. Una vez realizada la implementación, haga clic en Ver registro para ver los archivos de registro disponibles. Haga clic en Finalizar para completar la implementación.</span><span class="sxs-lookup"><span data-stu-id="932ea-p105">At Setup Lync Server components, click Next. The summary screen will show actions as they are executed. Once the deployment is done, click View Log to view available log files. Click Finish to complete the deployment.</span></span>

6.  <span data-ttu-id="932ea-122">En el servidor perimetral, en el Asistente para implementación, junto al paso 3: petición, Solicitar, instalar o asignar certificados, haga clic en Ejecutar de nuevo.</span><span class="sxs-lookup"><span data-stu-id="932ea-122">On the Edge Server, in the Deployment Wizard, next to Step 3: Request, Install, or Assign Certificates, click Run again.</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="932ea-123">Si va a implementar el servidor perimetral por primera vez, verá Ejecutar en lugar de Ejecutar de nuevo.</span><span class="sxs-lookup"><span data-stu-id="932ea-123">If you are deploying the Edge Server for the first time, you will see Run instead of Run Again.</span></span>

    
    </div>

7.  <span data-ttu-id="932ea-124">En la página Tareas de certificado disponibles, haga clic en Crear una nueva solicitud de certificado.</span><span class="sxs-lookup"><span data-stu-id="932ea-124">On the Available Certificate Tasks page, click Create a new certificate request.</span></span>

8.  <span data-ttu-id="932ea-125">En la página solicitud de certificado, haga clic en certificado perimetral externo.</span><span class="sxs-lookup"><span data-stu-id="932ea-125">On the Certificate Request page, click External Edge Certificate.</span></span>

9.  <span data-ttu-id="932ea-126">En la página Solicitud retrasada o inmediata, seleccione la casilla Prepare ahora la solicitud, pero envíela más tarde.</span><span class="sxs-lookup"><span data-stu-id="932ea-126">On the Delayed or Immediate Request page, select the Prepare the request now, but send it later check box.</span></span>

10. <span data-ttu-id="932ea-127">En la página archivo de solicitud de certificado, escriba la ruta de acceso completa y el nombre de archivo del archivo en el que se va a guardar la solicitud (por ejemplo, c: \\ CERT \_ externos \_ Edge. cer).</span><span class="sxs-lookup"><span data-stu-id="932ea-127">On the Certificate Request File page, type the full path and file name of the file to which the request is to be saved (for example, c:\\cert\_exernal\_edge.cer).</span></span>

11. <span data-ttu-id="932ea-128">En la página Especificar plantilla de certificado alternativa, para utilizar una plantilla distinta a la plantilla de servidor web predeterminada, seleccione la casilla Usar plantilla de certificado alternativa para la entidad de certificación seleccionada.</span><span class="sxs-lookup"><span data-stu-id="932ea-128">On the Specify Alternate Certificate Template page, to use a template other than the default WebServer template, select the Use alternative certificate template for the selected certification authority check box.</span></span>

12. <span data-ttu-id="932ea-129">En la página Nombre y configuración de seguridad, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="932ea-129">On the Name and Security Settings page, do the following:</span></span>
    
    1.  <span data-ttu-id="932ea-130">En Nombre descriptivo, escriba un nombre para mostrar para el certificado.</span><span class="sxs-lookup"><span data-stu-id="932ea-130">In Friendly name, type a display name for the certificate</span></span>
    
    2.  <span data-ttu-id="932ea-131">En Longitud en bits, especifique la longitud en bits (normalmente, el valor predeterminado de 2048).</span><span class="sxs-lookup"><span data-stu-id="932ea-131">In Bit length, specify the bit length (typically, the default of 2048)</span></span>
    
    3.  <span data-ttu-id="932ea-132">Compruebe que la casilla Marcar clave privada de certificado como exportable está activada.</span><span class="sxs-lookup"><span data-stu-id="932ea-132">Verify that the Mark certificate private key as exportable check box is selected</span></span>

13. <span data-ttu-id="932ea-133">En la página Información de la organización, escriba el nombre de la organización y la unidad organizativa (por ejemplo, una división o departamento).</span><span class="sxs-lookup"><span data-stu-id="932ea-133">On the Organization Information page, type the name for the organization and the organizational unit (for example, a division or department)</span></span>

14. <span data-ttu-id="932ea-134">En la página Información geográfica, especifique la información de ubicación.</span><span class="sxs-lookup"><span data-stu-id="932ea-134">On the Geographical Information page, specify the location information</span></span>

15. <span data-ttu-id="932ea-p106">En la página Nombre de sujeto / Nombres alternativos de sujeto se muestra la información que rellena automáticamente el asistente. Si son necesarios nombres alternativos de sujeto adicionales, debe especificarlos en los dos pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="932ea-p106">On the Subject Name/Subject Alternate Names page, the information to be automatically populated by the wizard is displayed. If additional subject alternative names are needed, you specify them in the next two steps</span></span>

16. <span data-ttu-id="932ea-137">En la página Configuración de dominio SIP en nombres alternativos de sujeto (San), active la casilla de verificación dominio para agregar un SIP.\<sipdomain\></span><span class="sxs-lookup"><span data-stu-id="932ea-137">On the SIP Domain Setting on Subject Alternate Names (SANs) page, select the domain check box to add a sip.\<sipdomain\></span></span> <span data-ttu-id="932ea-138">entrada a la lista de nombres alternativos de sujeto.</span><span class="sxs-lookup"><span data-stu-id="932ea-138">entry to the subject alternative names list.</span></span>

17. <span data-ttu-id="932ea-139">En la página Configurar nombres alternativos de sujeto adicionales, especifique los nombres alternativos de sujeto adicionales que sean necesarios.</span><span class="sxs-lookup"><span data-stu-id="932ea-139">On the Configure Additional Subject Alternate Names page, specify any additional subject alternative names that are required</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="932ea-p108">Si está instalado el proxy XMPP, el nombre de dominio (por ejemplo, contoso.com) se rellena de forma predeterminada en las entradas de SAN. Si necesita más entradas, agréguelas en este paso.</span><span class="sxs-lookup"><span data-stu-id="932ea-p108">If the XMPP proxy is installed, by default the domain name (such as contoso.com) is populated in the SAN entries. If you require more entries, add them in this step.</span></span>

    
    </div>

18. <span data-ttu-id="932ea-142">En la página Resumen de la solicitud, revise la información del certificado que se usará para generar la solicitud.</span><span class="sxs-lookup"><span data-stu-id="932ea-142">On the Request Summary page, review the certificate information to be used to generate the request.</span></span>

19. <span data-ttu-id="932ea-143">Después de que los comandos terminen de ejecutarse, puede elegir Ver registro o hacer clic en Siguiente para continuar.</span><span class="sxs-lookup"><span data-stu-id="932ea-143">After the commands finish running, you can View Log, or click Next to continue.</span></span>

20. <span data-ttu-id="932ea-144">En la página Archivo de solicitud de certificado, puede ver el archivo de solicitud de firma del certificado generado (CSR) haciendo clic en Ver o salir del Asistente para certificados haciendo clic en Finalizar.</span><span class="sxs-lookup"><span data-stu-id="932ea-144">On the Certificate Request File page, you can view the generated certificate signing request (CSR) file by clicking View or exit the Certificate Wizard by clicking Finish.</span></span>

21. <span data-ttu-id="932ea-145">opie el archivo de solicitud y envíeselo a su entidad emisora de certificación pública.</span><span class="sxs-lookup"><span data-stu-id="932ea-145">Copy the request file and submit to your public certification authority.</span></span>

22. <span data-ttu-id="932ea-p109">Después de recibir, importar y asignar el certificado público, debe detener y reiniciar los servicios del servidor perimetral. Para ello, escriba en la consola de administración de Lync Server:</span><span class="sxs-lookup"><span data-stu-id="932ea-p109">After receiving, importing and assigning the public certificate, you must stop and restart the Edge Server services. You do this by typing in the Lync Server Management console:</span></span>
    
       ```PowerShell
        Stop-CsWindowsService
       ```
    
       ```PowerShell
        Start-CsWindowsService
       ```

23. <span data-ttu-id="932ea-148">Para configurar DNS para la Federación XMPP, agregue el siguiente registro SRV a DNS externo: \_ XMPP-Server. \_ TPC.\<domain name\></span><span class="sxs-lookup"><span data-stu-id="932ea-148">To configure DNS for XMPP federation, you add the following SRV record to external DNS:\_xmpp-server.\_tcp.\<domain name\></span></span> <span data-ttu-id="932ea-149">El registro SRV se resolverá en el FQDN perimetral de acceso del servidor perimetral, con un valor de puerto de 5269.</span><span class="sxs-lookup"><span data-stu-id="932ea-149">The SRV record will resolve to the access edge FQDN of the Edge server, with a port value of 5269.</span></span> <span data-ttu-id="932ea-150">Además, puede configurar un registro de host ' A ' (por ejemplo, xmpp.contoso.com) que señale a la dirección IP del servidor perimetral de acceso.</span><span class="sxs-lookup"><span data-stu-id="932ea-150">Additionally, you configure an ‘A’ host record (for example, xmpp.contoso.com) that points to the IP address of the Access Edge Server.</span></span>
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > <span data-ttu-id="932ea-p111">Si tiene grupos de servidores perimetrales en varios sitios, conviene agregar varios registros SRV para la federación de XMPP. Agregue un registro SRV por cada grupo de servidores perimetrales que haya en la organización y asigne a cada uno de ellos una prioridad distinta. Cuando todos los grupos de servidores perimetrales estén ejecutándose, el que tenga la máxima prioridad se encargará de todas las solicitudes XMPP, pero si está inactivo, no será necesario agregar un nuevo registro SRV para recobrar la funcionalidad de federación de XMPP.</span><span class="sxs-lookup"><span data-stu-id="932ea-p111">If you have Edge pools in multiple sites, we recommend that you add multiple SRV records for XMPP federation. Add a SRV record for every Edge pool in your organization, and give each of those SRV records a different priority. When all Edge pools are running, XMPP requests will all be handled by the Edge pool with the first priority, but if that Edge pool goes down you won’t then have to add a new SRV record to regain XMPP federation functionality.</span></span>

    
    </div>

24. <span data-ttu-id="932ea-154">Configurar una nueva directiva de acceso externo para habilitar a todos los usuarios abriendo la Consola de administración de Lync Server en el servidor front-end y escriba:</span><span class="sxs-lookup"><span data-stu-id="932ea-154">Configure a new External Access Policy to enable all users by opening the Lync Server Management Shell on the Front End and typing:</span></span>
    
       ```PowerShell
        New-CsExternalAccessPolicy -Identity <name of policy to create.  If site scope, prepend with 'site:'> -EnableFederationAcces $true -EnablePublicCloudAccess $true
       ```
    
       ```PowerShell
        New-CsExternalAccessPolicy -Identity FedPic -EnableFederationAcces $true -EnablePublicCloudAccess $true
       ```
    
       ```PowerShell
        Get-CsUser | Grant-CsExternalAccessPolicy -PolicyName FedPic
       ```
    
    <span data-ttu-id="932ea-155">Habilite el acceso de XMPP para usuarios externos escribiendo:</span><span class="sxs-lookup"><span data-stu-id="932ea-155">Enable XMPP Access for External Users by typing:</span></span>
    
       ```PowerShell
        Set-CsExternalAccessPolicy -Identity <name of the policy being used> EnableXmppAccess $true
       ```
    
       ```PowerShell
        Set-CsExternalAccessPolicy -Identity FedPic -EnableXmppAccess $true
       ```

25. <span data-ttu-id="932ea-156">En el servidor perimetral en el que se implementa el proxy XMPP, abra un símbolo del sistema o una interfaz de línea de comandos de Windows PowerShell™ y escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="932ea-156">On the Edge Server where the XMPP Proxy is deployed, open a Command Prompt or a Windows PowerShell™ command-line interface and type the following:</span></span>
    
       ```PowerShell
        Netstat -ano | findstr 5269
       ```
    
       ```PowerShell
        Netstat -ano | findstr 23456
       ```
    
    <span data-ttu-id="932ea-157">El comando **netstat –ano** es un comando de estadísticas de red; los parámetros **–ano** solicitan que netstat muestre todas las conexiones y puertos de escucha (las direcciones y puertos se muestran en un formato numérico) y el identificador del proceso asociado a cada conexión.</span><span class="sxs-lookup"><span data-stu-id="932ea-157">The command **netstat –ano** is a network statistics command, the parameters **–ano** request that netstat display all connections and listening ports, address and ports are displayed in a numerical form, and that the owning process ID is associated with each connection.</span></span> <span data-ttu-id="932ea-158">El carácter **|** define una canalización para el siguiente comando, **Findstr**o Find String.</span><span class="sxs-lookup"><span data-stu-id="932ea-158">The character **|** defines a pipe to the next command, **findstr**, or find string.</span></span> <span data-ttu-id="932ea-159">El número 5269 y 23456 que se pasa a Findstr como parámetro indica a Findstr que busque en el resultado de netstat las cadenas 5269 y 23456.</span><span class="sxs-lookup"><span data-stu-id="932ea-159">The number 5269 and 23456 that is passed to findstr as a parameter instructs findstr to search the output of netstat for the strings 5269 and 23456.</span></span> <span data-ttu-id="932ea-160">Si XMPP está configurado correctamente, el resultado de los comandos debe dar como resultado la escucha y la conexión establecida, tanto en la interfaz externa (puerto 5269) como en la interfaz interna (Port 23456) del servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="932ea-160">If XMPP is correctly configured, the result of the commands should result in listening and established connections, both on the external (port 5269) and the internal (port 23456) interfaces of the Edge Server.</span></span>
    
    <span data-ttu-id="932ea-161">Si los comandos no devuelven unos puertos establecidos y de escucha en 5269 y 23456, compruebe lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="932ea-161">If the commands do not return established or listening ports on 5269 and 23456, check the following:</span></span>

</div>

<div>

## <a name="troubleshooting-xmpp-federation"></a><span data-ttu-id="932ea-162">Solucionar problemas de la federación XMPP</span><span class="sxs-lookup"><span data-stu-id="932ea-162">Troubleshooting XMPP Federation</span></span>

1.  <span data-ttu-id="932ea-163">Haga lo siguiente para saber si el proxy XMPP se está ejecutando:</span><span class="sxs-lookup"><span data-stu-id="932ea-163">To determine if the XMPP Proxy is running, do the following:</span></span>

2.  <span data-ttu-id="932ea-164">Inicie sesión en el servidor perimetral que ejecuta el servicio de proxy XMPP como miembro del grupo del administrador local.</span><span class="sxs-lookup"><span data-stu-id="932ea-164">Log on to the Edge server that is running the XMPP Proxy service as a member of the local administrator’s group.</span></span>

3.  <span data-ttu-id="932ea-165">Haga clic sucesivamente en **Inicio**, **Todos los programas**, **Herramientas administrativas** y **Servicios**.</span><span class="sxs-lookup"><span data-stu-id="932ea-165">Click **Start**, click **All Programs**, click **Administrative Tools**, click **Services**</span></span>

4.  <span data-ttu-id="932ea-p113">En Servicios, busque el proxy de puerta de enlace de traducción de XMPP de Lync Server. Este servicio debe estar en estado **Iniciado**; si no lo está, haga clic en el icono **Iniciar** de la barra de herramientas. El icono se mostrará como una flecha verde que apunta hacia la derecha.</span><span class="sxs-lookup"><span data-stu-id="932ea-p113">In Services, locate Lync Server XMPP Translating Gateway Proxy. The service should be in the **Started** state. If it is not started, click the **Start** icon in the toolbar. The icon appears as a green, right-pointing arrow.</span></span>

5.  <span data-ttu-id="932ea-p114">Confirme que el servicio ha cambiado a **Iniciado**. Si así es, cierre **Servicios** y prosiga.</span><span class="sxs-lookup"><span data-stu-id="932ea-p114">Confirm that the service has changed to **Started**. If it has successfully started, close **Services** and continue.</span></span>
    
    <span data-ttu-id="932ea-172">Si el servicio no se ha iniciado, abra el Visor de eventos desde Herramientas administrativas y consulte los errores y advertencias en la sección **Lync Server** de **Registros de aplicaciones y servicios**.</span><span class="sxs-lookup"><span data-stu-id="932ea-172">If ther service has not successfully started, from Administrative Tools, open Event Viewer and refer to the errors and warnings in the **Lync Server** portion under **Applications and Services Logs**.</span></span>

6.  <span data-ttu-id="932ea-173">Cuando el servicio **Puerta de enlace de traducción de XMPP de Lync Server** se esté ejecutando, vuelva a comprobar los comandos netstat que empleamos anteriormente.</span><span class="sxs-lookup"><span data-stu-id="932ea-173">Once the **Lync Server XMPP Translating Gateway** service is running, recheck the netstat commands used previously.</span></span> <span data-ttu-id="932ea-174">Si no ve sesiones establecidas o en escucha, compruebe y asegúrese de que la **ruta de Federación de XMPP** esté correctamente configurada en el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="932ea-174">If you are not seeing established or listening sessions, check and ensure that the **XMPP Federation Route** is correctly configured in Topology Builder</span></span>

7.  <span data-ttu-id="932ea-175">Inicie sesión en el equipo en el que Topology Builder esté instalado como miembro del grupo Admins. del dominio y el grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="932ea-175">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

8.  <span data-ttu-id="932ea-176">Inicie el generador de topologías: haga clic en **Inicio**, haga clic en **todos los programas**, haga clic en **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topologías de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="932ea-176">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

9.  <span data-ttu-id="932ea-177">En el generador de topologías, seleccione el sitio de la ruta de Federación XMPP y revise para confirmar que la **asignación de ruta de Federación del sitio** para la **Federación XMPP** muestra el servidor perimetral o el grupo de servidores perimetrales como la asignación de ruta de Federación XMPP seleccionada.</span><span class="sxs-lookup"><span data-stu-id="932ea-177">In Topology Builder, select the site for the XMPP federation route and review to confirm that the **Site federation route assignment** for **XMPP federation** shows your Edge Server or Edge pool as the selected XMPP federation route assignment.</span></span>
    
    <span data-ttu-id="932ea-178">Si la asignación de ruta es incorrecta o no se ha establecido, haga clic con el botón secundario en el sitio y haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="932ea-178">If the route assignment is incorrect or is not set, right-click the site, click **Edit Properties**.</span></span> <span data-ttu-id="932ea-179">Active la casilla Federación XMPP y, a continuación, seleccione el servidor perimetral o el grupo de servidores perimetrales correctos.</span><span class="sxs-lookup"><span data-stu-id="932ea-179">Select the XMPP federation check box and then select the correct Edge Server or Edge pool.</span></span>

10. <span data-ttu-id="932ea-180">Publique la topología.</span><span class="sxs-lookup"><span data-stu-id="932ea-180">Publish the topology.</span></span> <span data-ttu-id="932ea-181">Para obtener más información, consulte [publicar la topología en Lync Server 2013](lync-server-2013-publish-your-topology.md)</span><span class="sxs-lookup"><span data-stu-id="932ea-181">For details, see [Publish your topology in Lync Server 2013](lync-server-2013-publish-your-topology.md)</span></span>
    
    <div class=" ">
    

    > [!TIP]  
    > <span data-ttu-id="932ea-182">Aunque no es necesario y normalmente no es necesario, es posible que necesite reiniciar los servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="932ea-182">Though not required and typically not necessary, you may find that you will need to restart the Edge Servers</span></span>

    
    </div>

11. <span data-ttu-id="932ea-183">Con el proceso netstat usado anteriormente, confirme que el servidor perimetral ya está escuchando o ha establecido sesiones en los puertos 5269 y 23456.</span><span class="sxs-lookup"><span data-stu-id="932ea-183">Using the netstat process used previously, confirm that the Edge Server is now listening or has established sessions on port 5269 and port 23456.</span></span>

12. <span data-ttu-id="932ea-184">Si sigue sin ver las sesiones que espera, consulte el Visor de eventos para ver las causas que pueden intervenir en el problema de comunicación.</span><span class="sxs-lookup"><span data-stu-id="932ea-184">If you still are not seeing the expected sessions, check the Event Viewer for possible contributing causes for the communication problem.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="932ea-185">Consulte también</span><span class="sxs-lookup"><span data-stu-id="932ea-185">See Also</span></span>


[<span data-ttu-id="932ea-186">Configuración XMPP de ejemplo en Lync Server 2013: Federación XMPP con Google Talk</span><span class="sxs-lookup"><span data-stu-id="932ea-186">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</span></span>](lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md)  


[<span data-ttu-id="932ea-187">Administrar socios federados XMPP en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="932ea-187">Manage XMPP federated partners in Lync Server 2013</span></span>](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

