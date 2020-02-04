---
title: 'Lync Server 2013: Crear o modificar un flujo de trabajo interactivo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify an interactive workflow
ms:assetid: bc7bb1bc-bf6a-4636-ae93-c56fa22613fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205213(v=OCS.15)
ms:contentKeyID: 48185260
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eec10d1d9c3281485078b2d7823978c429ea1be3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734390"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-an-interactive-workflow-in-lync-server-2013"></a><span data-ttu-id="26d12-102">Crear o modificar un flujo de trabajo interactivo en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="26d12-102">Create or modify an interactive workflow in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="26d12-103">_**Última modificación del tema:** 2013-09-11_</span><span class="sxs-lookup"><span data-stu-id="26d12-103">_**Topic Last Modified:** 2013-09-11_</span></span>

<span data-ttu-id="26d12-104">Use uno de los procedimientos siguientes para crear o modificar un flujo de trabajo interactivo.</span><span class="sxs-lookup"><span data-stu-id="26d12-104">Use one of the following procedures to create or modify an interactive workflow.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="26d12-105">Puede usar el shell de administración de Lync Server o la herramienta de configuración de grupos de respuesta para crear y modificar flujos de trabajo interactivos.</span><span class="sxs-lookup"><span data-stu-id="26d12-105">You can use Lync Server Management Shell or the Response Group Configuration Tool to create and modify interactive workflows.</span></span> <span data-ttu-id="26d12-106">Puede obtener acceso a la herramienta de configuración de grupos de respuesta desde el panel de control de Lync Server o abriendo la página web directamente desde un explorador web escribiendo la siguiente dirección URL: <STRONG>https://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="26d12-106">You can access the Response Group Configuration Tool from Lync Server Control Panel, or by opening the webpage directly from a web browser by typing the following URL: <STRONG>https://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>.</span></span>



</div>

<div>

## <a name="to-use-response-group-configuration-tool-to-create-or-modify-an-interactive-workflow"></a><span data-ttu-id="26d12-107">Para usar la herramienta de configuración de grupos de respuesta para crear o modificar un flujo de trabajo interactivo</span><span class="sxs-lookup"><span data-stu-id="26d12-107">To use Response Group Configuration Tool to create or modify an Interactive workflow</span></span>

1.  <span data-ttu-id="26d12-108">Inicie sesión como miembro del grupo RTCUniversalServerAdmins o como miembro de uno de los roles administrativos predefinidos que admiten el Grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="26d12-108">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="26d12-109">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="26d12-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="26d12-110">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="26d12-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="26d12-111">En la barra de navegación izquierda, haga clic en **Grupos de respuesta** y después en **Flujo de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="26d12-111">In the left navigation bar, click **Response Groups**, and then click **Workflow**.</span></span>

4.  <span data-ttu-id="26d12-112">En la página **Flujo de trabajo**, haga clic en **Crear o editar un flujo de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="26d12-112">On the **Workflow** page, click **Create or edit a workflow**.</span></span>

5.  <span data-ttu-id="26d12-113">En el campo de búsqueda **Seleccionar un servicio**, escriba total o parcialmente el nombre del servicio de **ApplicationServer** que hospeda el flujo de trabajo que desea crear o modificar.</span><span class="sxs-lookup"><span data-stu-id="26d12-113">In the **Select a Service** search field, type all or part of the name of the **ApplicationServer** service that hosts the workflow that you want to create or modify.</span></span> <span data-ttu-id="26d12-114">En la lista de servicios resultante, haga clic en el servicio que desee y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="26d12-114">In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="26d12-115">Se abrirá la herramienta de configuración de grupos de respuesta.</span><span class="sxs-lookup"><span data-stu-id="26d12-115">The Response Group Configuration Tool opens.</span></span> <span data-ttu-id="26d12-116">También puede abrir la herramienta de configuración de grupo de respuesta directamente desde un explorador web escribiendo la siguiente URL: <STRONG>https://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="26d12-116">You can also open the Response Group Configuration Tool directly from a web browser by typing the following URL: <STRONG>https://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>.</span></span>

    
    </div>

6.  <span data-ttu-id="26d12-117">Siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="26d12-117">Do one of the following:</span></span>
    
      - <span data-ttu-id="26d12-118">En **Crear un nuevo flujo de trabajo**, junto a **Interactivo**, haga clic en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="26d12-118">Under **Create a New Workflow**, next to **Interactive**, click **Create**.</span></span>
    
      - <span data-ttu-id="26d12-119">En **Administrar un flujo de trabajo existente**, localice el flujo de trabajo que desea cambiar y, a continuación, en **Acción**, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="26d12-119">Under **Manage an Existing Workflow**, locate the workflow you want to change, and then under **Action**, click **Edit**.</span></span>

7.  <span data-ttu-id="26d12-120">Si todavía no está listo para que los usuarios comiencen a llamar al flujo de trabajo, desactive la casilla **Activar el flujo de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="26d12-120">If you are not ready for users to start calling the workflow, clear the **Activate the workflow** check box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="26d12-p105">Si está creando un flujo de trabajo administrado, seleccione <STRONG>Activar el flujo de trabajo</STRONG>. Después de guardar el flujo de trabajo administrado activo, puede modificarlo y desactivarlo.</span><span class="sxs-lookup"><span data-stu-id="26d12-p105">If you are to creating a managed workflow, you need to select <STRONG>Activate the workflow</STRONG>. After you save the active, managed workflow, you can then modify and deactivate it.</span></span>

    
    </div>

8.  <span data-ttu-id="26d12-123">Para permitir que los usuarios federados puedan llamar al grupo, active la casilla **Habilitar para federación**.</span><span class="sxs-lookup"><span data-stu-id="26d12-123">To allow federated users to call the group, select the **Enable for federation** check box.</span></span> <span data-ttu-id="26d12-124">También debe tener una directiva de acceso externo que se aplique a la aplicación de grupo de respuesta configurada para la Federación.</span><span class="sxs-lookup"><span data-stu-id="26d12-124">You must also have an external access policy that applies to the Response Group application configured for federation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="26d12-125">La Directiva de acceso externo global se aplica a la aplicación de grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="26d12-125">The global external access policy applies to the Response Group application.</span></span> <span data-ttu-id="26d12-126">Puede configurar la directiva global para la Federación de grupos de respuesta mediante el panel de control de Lync Server o mediante el cmdlet <STRONG>set-CsExternalAccessPolicy</STRONG> para establecer el parámetro EnableOutsideAccess en true.</span><span class="sxs-lookup"><span data-stu-id="26d12-126">You can configure the global policy for response group federation by using Lync Server Control Panel or by using the <STRONG>Set-CsExternalAccessPolicy</STRONG> cmdlet to set the EnableOutsideAccess parameter to True.</span></span> <span data-ttu-id="26d12-127">Recuerde que la configuración de la directiva global se aplica a todos los usuarios, a menos que se les haya asignado una directiva de usuario o de sitio.</span><span class="sxs-lookup"><span data-stu-id="26d12-127">Keep in mind that global policy settings apply to all users unless they are assigned a site or user policy.</span></span> <span data-ttu-id="26d12-128">Por lo tanto, antes de cambiar la configuración de los grupos de respuesta, asegúrese de que la configuración de la federación cumpla los requisitos de la organización.</span><span class="sxs-lookup"><span data-stu-id="26d12-128">Therefore, before changing this setting for response groups, make sure that the federation setting meets the requirements of your organization.</span></span> <span data-ttu-id="26d12-129">Para obtener más información sobre cómo se aplican las directivas a los usuarios, vea <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">administrar la Directiva de acceso externo en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="26d12-129">For details about how policies apply to users, see <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">Manage external access policy in Lync Server 2013</A>.</span></span> <span data-ttu-id="26d12-130">Para obtener más información sobre la configuración de Federación, consulte <STRONG>set-CsExternalAccessPolicy</STRONG> en la documentación del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="26d12-130">For details about the federation setting, see <STRONG>Set-CsExternalAccessPolicy</STRONG> in Lync Server Management Shell documentation.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="26d12-131">Los usuarios que se hospedan en Lync Online no pueden realizar llamadas a grupos de respuesta hospedados en una implementación local.</span><span class="sxs-lookup"><span data-stu-id="26d12-131">Users who are hosted in Lync Online can’t place calls to response groups that are hosted in an on-premise deployment.</span></span> <span data-ttu-id="26d12-132">Esto sucede en ambas implementaciones híbridas y en los casos en los que una implementación local se federa con una implementación de Lync Online.</span><span class="sxs-lookup"><span data-stu-id="26d12-132">This is true in both hybrid deployments and in cases where an on-premise deployment is federated with a Lync Online deployment.</span></span>

    
    </div>

9.  <span data-ttu-id="26d12-133">Para ocultar la identidad de los agentes durante las llamadas, active la casilla **Habilitar anonimato de agente**.</span><span class="sxs-lookup"><span data-stu-id="26d12-133">To hide the identity of agents during calls, select the **Enable agent anonymity** check box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="26d12-p109">Las llamadas anónimas no pueden empezar con mensajería instantánea (MI) ni un vídeo, aunque el agente o la persona que llame pueda agregar MI o un vídeo después de establecer la llamada. Asimismo, un agente anónimo puede poner llamadas en espera, transferir llamadas (tanto transferencias a otras líneas como consultas), además de estacionar y recuperar llamadas. Las llamadas anónimas no admiten conferencias, uso compartido de aplicaciones ni de escritorio, transferencia de archivos, función de pizarra, colaboración de datos y grabación de llamadas. Los agentes que usen el complemento VDI de Lync pueden recibir llamadas entrantes anónimas, pero no realizar llamadas salientes anónimas.</span><span class="sxs-lookup"><span data-stu-id="26d12-p109">Anonymous calls cannot start with instant messaging (IM) or video, although the agent or the caller can add IM and video after the call is established. An anonymous agent can also put calls on hold, transfer calls (both blind and consultative transfers), and park and retrieve calls. Anonymous calls do not support conferencing, application sharing and desktop sharing, file transfer, whiteboarding and data collaboration, and call recording. Agents using the Lync VDI Plugin can receive incoming calls anonymously, but they cannot make outgoing calls anonymously.</span></span>

    
    </div>

10. <span data-ttu-id="26d12-138">En **Especifique la dirección del grupo que recibirá las llamadas**, escriba la dirección del identificador uniforme de recursos (URI) del SIP primario del grupo que responderá las llamadas al flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="26d12-138">Under **Enter the address of the group that will receive the calls**, type the primary SIP uniform resource identifier (URI) address of the group that will answer calls to the workflow.</span></span>

11. <span data-ttu-id="26d12-139">En **Nombre para mostrar**, escriba el nombre que desea mostrar para el flujo de trabajo (por ejemplo, Grupo de respuesta IVR de ventas).</span><span class="sxs-lookup"><span data-stu-id="26d12-139">In **Display name**, type the name that you want to display for the workflow (for example, Sales IVR Response Group).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="26d12-140">No incluyas los caracteres&lt;"" o&gt;"" en el nombre para mostrar.</span><span class="sxs-lookup"><span data-stu-id="26d12-140">Do not include the "&lt;" or "&gt;" characters in the display name.</span></span> <span data-ttu-id="26d12-141">No use los siguientes nombres para mostrar porque están reservados: Observador de presencia de RGS o Servicio de anuncio.</span><span class="sxs-lookup"><span data-stu-id="26d12-141">Do not use the following display names because they are reserved: RGS Presence Watcher or Announcement Service.</span></span>

    
    </div>

12. <span data-ttu-id="26d12-142">En **Número de teléfono**, escriba el URI de línea para el grupo de respuesta (por ejemplo, +14255550165).</span><span class="sxs-lookup"><span data-stu-id="26d12-142">In **Telephone number**, type the line URI for the response group (for example, +14255550165).</span></span>

13. <span data-ttu-id="26d12-143">En **Número para mostrar**, escriba el número tal como desea que aparezca para el grupo de respuesta (por ejemplo, +1 (425) 555-0165).</span><span class="sxs-lookup"><span data-stu-id="26d12-143">In **Display number**, type the number as you want it to appear for the response group (for example, +1 (425) 555-0165).</span></span>

14. <span data-ttu-id="26d12-144">Faculta En **Descripción**, escriba una descripción para el flujo de trabajo que desea que aparezca en la tarjeta de contacto en el cliente de Lync.</span><span class="sxs-lookup"><span data-stu-id="26d12-144">(Optional) In **Description**, type a description for the workflow that you want to appear on the contact card in the Lync client.</span></span>

15. <span data-ttu-id="26d12-145">En **Tipo de flujo de trabajo**, seleccione **Administrado** si este flujo de trabajo va a ser administrado por un administrador de grupos de respuesta.</span><span class="sxs-lookup"><span data-stu-id="26d12-145">In **Workflow Type**, select **Managed** if this workflow will be managed by a Response Group Manager.</span></span> <span data-ttu-id="26d12-146">Siga este procedimiento para asignar administradores de grupos de respuesta al flujo de trabajo:</span><span class="sxs-lookup"><span data-stu-id="26d12-146">Do the following to assign Response Group Managers to the workflow:</span></span>
    
    1.  <span data-ttu-id="26d12-147">Escriba el URI del SIP de un administrador para este flujo de trabajo y haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="26d12-147">Type the SIP URI of a manager for this workflow, and click **Add**..</span></span>
    
    2.  <span data-ttu-id="26d12-148">Escriba el URI del SIP de otros administradores para agregar al flujo de trabajo y haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="26d12-148">Type the SIP URI of additional managers to add to the workflow, and click **Add**..</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="26d12-p112">A todos los usuarios designados como administradores de un grupo de respuestas se les asigna el rol CsResponseGroupManager. Los usuarios a los que no se haya asignado este rol no pueden administrar grupos de respuesta.</span><span class="sxs-lookup"><span data-stu-id="26d12-p112">Every user who is designated as a manager of a response group must be assigned the CsResponseGroupManager role. If users are not assigned this role, they cannot manage response groups.</span></span>

    
    </div>

16. <span data-ttu-id="26d12-151">En **Paso 2 Seleccionar un idioma**, haga clic en el idioma que se usará para el reconocimiento de voz y texto a voz.</span><span class="sxs-lookup"><span data-stu-id="26d12-151">Under **Step 2 Select a Language**, click the language to use for speech recognition and text-to-speech.</span></span>

17. <span data-ttu-id="26d12-152">Si desea definir un mensaje de bienvenida, en el **Paso 3 Configurar un mensaje de bienvenida**, active la casilla **Reproducir un mensaje de bienvenida** y luego lleve a cabo uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="26d12-152">If you want to configure a welcome message, under **Step 3 Configure a Welcome Message**, select the **Play a welcome message** check box, and then do one of the following:</span></span>
    
      - <span data-ttu-id="26d12-153">Para escribir el mensaje de bienvenida como texto que se convertirá en voz para el autor de la llamada, haga clic en **Usar texto a voz** y después escriba el mensaje de bienvenida en el cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="26d12-153">To enter the welcome message as text that is converted to speech for callers, click **Use text-to-speech**, and then type the welcome message in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="26d12-p113">No incluya etiquetas HTML en el texto que especifique. Si incluye etiquetas HTML, recibirá un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="26d12-p113">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
    
      - <span data-ttu-id="26d12-p114">Para usar una grabación de archivos de Wave o Windows Media Audio para el mensaje de bienvenida, haga clic en **Seleccionar una grabación**. Si desea cargar un nuevo archivo de audio, haga clic en el vínculo de **una grabación**. En la nueva ventana de explorador, haga clic en **Examinar**, seleccione el archivo de audio que desea usar y haga clic en **Abrir**. Haga clic en **Cargar** para cargar el archivo de audio.</span><span class="sxs-lookup"><span data-stu-id="26d12-p114">To use a Wave or Windows Media Audio file recording for the welcome message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the audio file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="26d12-160">Todos los archivos de audio proporcionados por el usuario deben cumplir ciertos requisitos.</span><span class="sxs-lookup"><span data-stu-id="26d12-160">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="26d12-161">Para obtener detalles sobre los formatos de archivo admitidos, consulte <A href="lync-server-2013-technical-requirements-for-response-group.md">requisitos técnicos para el grupo de respuesta de Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="26d12-161">For details about supported file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

18. <span data-ttu-id="26d12-162">En **Paso 4 Especificar horario comercial**, en el cuadro **Su zona horaria**, haga clic en la zona horaria del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="26d12-162">Under **Step 4 Specify Your Business Hours**, in the **Your time zone** box, click the time zone of the workflow.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="26d12-p116">La zona horaria se refiere a la zona donde residen los autores de llamadas y los agentes del flujo de trabajo. Se usa para calcular las horas de apertura y cierre. Por ejemplo, si el flujo de trabajo está configurado para usar la zona horaria Hora oriental de América del Norte y el flujo de trabajo está programado para abrir a las 7:00 y cerrar a 23:00, se supone que las horas de apertura y cierre son las 7:00 (Hora del este) y las 23:00 (Hora del este) respectivamente. Escriba las horas en la notación de 24 horas.</span><span class="sxs-lookup"><span data-stu-id="26d12-p116">The time zone is the time zone where the callers and agents of the workflow reside. It is used to calculate the open and close hours. For example, if the workflow is configured to use the North American Eastern Time zone and the workflow is scheduled to open at 7:00 A.M. and close at 11:00 P.M., the open and close times are assumed to be 7:00 Eastern Time and 11:00 Eastern Time respectively. (You must enter the times in 24-hour time notation.)</span></span>

    
    </div>

19. <span data-ttu-id="26d12-168">Para seleccionar el tipo de programación de horario comercial que quiere usar, siga uno de los procedimientos siguientes:</span><span class="sxs-lookup"><span data-stu-id="26d12-168">Select the type of business hours schedule you want to use by doing one of the following:</span></span>
    
      - <span data-ttu-id="26d12-169">Para usar una programación predefinida de horario comercial, haga clic en **Usar una programación preestablecida** y después seleccione el horario que desea utilizar en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="26d12-169">To use a predefined schedule of business hours, click **Use a preset schedule**, and then select the schedule you want to use from the drop-down list.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="26d12-170">Debe definir al menos una programación preestablecida previamente para poder seleccionar esta opción.</span><span class="sxs-lookup"><span data-stu-id="26d12-170">You must have defined at least one preset schedule previously to be able to select this option.</span></span> <span data-ttu-id="26d12-171">Puede definir programaciones preestablecidas con el cmdlet <STRONG>New-CSRgsHoursOfBusiness</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="26d12-171">You define preset schedules by using the <STRONG>New-CSRgsHoursOfBusiness</STRONG> cmdlet.</span></span> <span data-ttu-id="26d12-172">Para obtener más información, consulte <A href="lync-server-2013-optional-define-response-group-business-hours.md">(opcional) definir las horas de trabajo del grupo de respuesta en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="26d12-172">For details, see <A href="lync-server-2013-optional-define-response-group-business-hours.md">(Optional) Define Response Group business hours in Lync Server 2013</A>.</span></span> <span data-ttu-id="26d12-173">Cuando selecciona una programación preestablecida, <STRONG>Día</STRONG>, <STRONG>Abrir</STRONG> y <STRONG>Cerrar</STRONG> se rellenan automáticamente con los días y las horas en los que el grupo de respuesta se encuentra disponible.</span><span class="sxs-lookup"><span data-stu-id="26d12-173">When you select a preset schedule, <STRONG>Day</STRONG>, <STRONG>Open</STRONG>, and <STRONG>Close</STRONG> are automatically filled with the days and hours that the response group is available.</span></span>

        
        </div>
    
      - <span data-ttu-id="26d12-174">Para usar una programación personalizada que se aplique solo a este flujo de trabajo, haga clic en **Usar una programación personalizada**.</span><span class="sxs-lookup"><span data-stu-id="26d12-174">To use a custom schedule that applies only to this workflow, click **Use a custom schedule**.</span></span>

20. <span data-ttu-id="26d12-175">Si está creando una programación personalizada para este flujo de trabajo, haga clic en las casillas correspondientes a los días de la semana durante los que se encuentra disponible el grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="26d12-175">If you are creating a custom schedule for this workflow, click the check boxes for the days of the week that the response group is available.</span></span>

21. <span data-ttu-id="26d12-176">Para crear una programación personalizada, escriba las horas de   **Abrir** y **Cerrar** en las que el grupo de respuesta se encuentra disponible.</span><span class="sxs-lookup"><span data-stu-id="26d12-176">If you are creating a custom schedule, type the **Open** and **Close** hours when the response group available.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="26d12-p118">Las horas de <STRONG>Abrir</STRONG> y <STRONG>Cerrar</STRONG> deben mostrarse en formato de 24 horas. Por ejemplo, si en su oficina se trabaja de 9 a 5 y se cierra al mediodía para el almuerzo, el horario comercial se especificará de la siguiente manera: <STRONG>Abrir</STRONG> 9:00, <STRONG>Cerrar</STRONG> 12:00, <STRONG>Abrir</STRONG> 13:00 y <STRONG>Cerrar</STRONG> 17:00.</span><span class="sxs-lookup"><span data-stu-id="26d12-p118">The <STRONG>Open</STRONG> and <STRONG>Close</STRONG> hours must be in 24-hour time notation. For example, if your office works a 9-to-5 work day and closes at noon for lunch, the business hours are specified as <STRONG>Open</STRONG> 9:00, <STRONG>Close</STRONG> 12:00, <STRONG>Open</STRONG> 13:00, and <STRONG>Close</STRONG> 17:00.</span></span>

    
    </div>

22. <span data-ttu-id="26d12-179">Si desea reproducir un mensaje cuando la oficina no esté abierta, active la casilla **Reproducir un mensaje cuando el grupo de respuesta esté fuera del horario comercial** y después especifique el mensaje que se va a reproducir siguiendo uno de los procedimientos siguientes:</span><span class="sxs-lookup"><span data-stu-id="26d12-179">If you want to play a message when the office is not open, select the **Play a message when the response group is outside of business hours** check box, and then specify the message to play by doing one of the following:</span></span>
    
      - <span data-ttu-id="26d12-180">Para escribir el mensaje como texto que se convertirá en voz para el autor de la llamada, haga clic en **Usar texto a voz** y después escriba el mensaje de bienvenida en el cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="26d12-180">To enter the message as text that is converted to speech for the caller, click **Use text-to-speech**, and then type the message in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="26d12-181">No incluya etiquetas HTML en el texto que especifique.</span><span class="sxs-lookup"><span data-stu-id="26d12-181">Do not include HTML tags in the text you enter.</span></span> <span data-ttu-id="26d12-182">Si incluye etiquetas HTML, recibirá un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="26d12-182">If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
    
      - <span data-ttu-id="26d12-p120">Para usar una grabación en un archivo de audio para el mensaje, haga clic en **Seleccionar una grabación**. Si desea cargar un archivo de audio nuevo, haga clic en el vínculo **una grabación**. En la nueva ventana del explorador, haga clic en **Examinar**, seleccione el archivo que desea usar y después haga clic en **Abrir**. Haga clic en **Cargar** para cargar el archivo de audio.</span><span class="sxs-lookup"><span data-stu-id="26d12-p120">To use an audio file recording for the message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="26d12-187">Todos los archivos de audio proporcionados por el usuario deben cumplir ciertos requisitos.</span><span class="sxs-lookup"><span data-stu-id="26d12-187">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="26d12-188">Para obtener detalles sobre los formatos de archivo admitidos, consulte <A href="lync-server-2013-technical-requirements-for-response-group.md">requisitos técnicos para el grupo de respuesta de Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="26d12-188">For details about supported file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

23. <span data-ttu-id="26d12-189">Especifique cómo abordar las llamadas tras la reproducción del mensaje (si se ha configurado uno):</span><span class="sxs-lookup"><span data-stu-id="26d12-189">Specify how to handle calls after the message is played (if a message is configured):</span></span>
    
      - <span data-ttu-id="26d12-190">Para desconectar la llamada, haga clic en **Desconectar llamada**.</span><span class="sxs-lookup"><span data-stu-id="26d12-190">To disconnect the call, click **Disconnect Call**.</span></span>
    
      - <span data-ttu-id="26d12-191">Para desviar la llamada al correo de voz, haga clic en **Desviar a correo de voz** y escriba la dirección de correo de voz.</span><span class="sxs-lookup"><span data-stu-id="26d12-191">To forward the call to voice mail, click **Forward to voice mail**, and then type the voice mail address.</span></span> <span data-ttu-id="26d12-192">El formato de la dirección de correo de \<voz\>@\<es\> nombre de usuario nombreDeDominio (por ejemplo, Bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="26d12-192">The format for the voice mail address is \<username\>@\<domainname\> (for example, bob@contoso.com).</span></span>
    
      - <span data-ttu-id="26d12-193">Para desviar la llamada a otro usuario, haga clic en **Desviar a URI del SIP** y escriba la dirección de usuario.</span><span class="sxs-lookup"><span data-stu-id="26d12-193">To forward the call to another user, click **Forward to SIP URI**, and then type a user address.</span></span> <span data-ttu-id="26d12-194">El formato de la dirección de usuario \<es\>@\<nombre\>de usuario nombreDeDominio.</span><span class="sxs-lookup"><span data-stu-id="26d12-194">The format for the user address is \<username\>@\<domainname\>.</span></span>
    
      - <span data-ttu-id="26d12-195">Para desviar la llamada a otro número de teléfono, haga clic en **Desviar a número de teléfono** y escriba el número de teléfono.</span><span class="sxs-lookup"><span data-stu-id="26d12-195">To forward the call to another telephone number, click **Forward to telephone number**, and then type the telephone number.</span></span> <span data-ttu-id="26d12-196">El formato del número de teléfono es \<\>@\<domainname\> (por ejemplo, + 14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="26d12-196">The format for the telephone number is \<number\>@\<domainname\> (for example, +14255550121@contoso.com).</span></span> <span data-ttu-id="26d12-197">El nombre de dominio se usa para redirigir al autor de la llamada al destino correcto.</span><span class="sxs-lookup"><span data-stu-id="26d12-197">The domain name is used to route the caller to the correct destination.</span></span>

24. <span data-ttu-id="26d12-198">En **Paso 5 Especificar vacaciones**, haga clic en las casillas para uno o más conjuntos de vacaciones que definan los días en los que el grupo de respuesta no esté laboralmente disponible.</span><span class="sxs-lookup"><span data-stu-id="26d12-198">Under **Step 5 Specify Your Holidays**, click the check boxes for one or more sets of holidays that define the days when the response group is closed for business.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="26d12-199">Defina las vacaciones y los conjuntos de vacaciones antes de configurar el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="26d12-199">You need to define holidays and holiday sets before you configure the workflow.</span></span> <span data-ttu-id="26d12-200">Para ello, use los cmdlets <STRONG>New-CsRgsHoliday</STRONG> y <STRONG>New-CsRgsHolidaySet</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="26d12-200">Use the <STRONG>New-CsRgsHoliday</STRONG> and <STRONG>New-CsRgsHolidaySet</STRONG> cmdlets to define holidays and holiday sets.</span></span> <span data-ttu-id="26d12-201">Para obtener más información, consulte <A href="lync-server-2013-optional-define-response-group-holiday-sets.md">(opcional) definir conjuntos de días festivos de grupos de respuesta en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="26d12-201">For details, see <A href="lync-server-2013-optional-define-response-group-holiday-sets.md">(Optional) Define Response Group holiday sets in Lync Server 2013</A>.</span></span>

    
    </div>

25. <span data-ttu-id="26d12-202">Si desea reproducir un mensaje durante las vacaciones, active la casilla **Reproducir un mensaje durante las vacaciones** y después especifique el mensaje que se va a reproducir con uno de los siguientes procedimientos:</span><span class="sxs-lookup"><span data-stu-id="26d12-202">If you want to play a message on holidays, select the **Play a message during holidays** check box, and then specify the message to play by doing one of the following:</span></span>
    
      - <span data-ttu-id="26d12-203">Para escribir el mensaje como texto que se convertirá en voz para el autor de la llamada, haga clic en **Usar texto a voz** y después escriba el mensaje de bienvenida en el cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="26d12-203">To enter the message as text that is converted to speech for the caller, click **Use text-to-speech**, and then type the message in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="26d12-204">No incluya etiquetas HTML en el texto que especifique.</span><span class="sxs-lookup"><span data-stu-id="26d12-204">Do not include HTML tags in the text you enter.</span></span> <span data-ttu-id="26d12-205">Si incluye etiquetas HTML, recibirá un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="26d12-205">If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
    
      - <span data-ttu-id="26d12-p127">Para usar una grabación en un archivo de audio para el mensaje, haga clic en **Seleccionar una grabación**. Si desea cargar un archivo de audio nuevo, haga clic en el vínculo **una grabación**. En la nueva ventana del explorador, haga clic en **Examinar**, seleccione el archivo que desea usar y después haga clic en **Abrir**. Haga clic en **Cargar** para cargar el archivo de audio.</span><span class="sxs-lookup"><span data-stu-id="26d12-p127">To use an audio file recording for the message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="26d12-210">Todos los archivos de audio proporcionados por el usuario deben cumplir ciertos requisitos.</span><span class="sxs-lookup"><span data-stu-id="26d12-210">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="26d12-211">Para obtener detalles sobre los formatos de archivo de audio admitidos, consulte <A href="lync-server-2013-technical-requirements-for-response-group.md">requisitos técnicos para el grupo de respuesta de Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="26d12-211">For details about supported audio file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

26. <span data-ttu-id="26d12-212">Especifique cómo abordar las llamadas tras la reproducción del mensaje (si se ha configurado uno):</span><span class="sxs-lookup"><span data-stu-id="26d12-212">Specify how to handle calls after the message is played (if a message is configured):</span></span>
    
      - <span data-ttu-id="26d12-213">Para desconectar la llamada, haga clic en **Desconectar llamada**.</span><span class="sxs-lookup"><span data-stu-id="26d12-213">To disconnect the call, click **Disconnect Call**.</span></span>
    
      - <span data-ttu-id="26d12-214">Para desviar la llamada al correo de voz, haga clic en **Desviar a correo de voz** y escriba la dirección de correo de voz.</span><span class="sxs-lookup"><span data-stu-id="26d12-214">To forward the call to voice mail, click **Forward to voice mail**, and then type the voice mail address.</span></span> <span data-ttu-id="26d12-215">El formato de la dirección de correo de \<voz\>@\<es\> nombre de usuario nombreDeDominio (por ejemplo, Bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="26d12-215">The format for the voice mail address is \<username\>@\<domainname\> (for example, bob@contoso.com).</span></span>
    
      - <span data-ttu-id="26d12-216">Para desviar la llamada a otro usuario, haga clic en **Desviar a URI del SIP** y escriba la dirección de usuario.</span><span class="sxs-lookup"><span data-stu-id="26d12-216">To forward the call to another user, click **Forward to SIP URI**, and then type a user address.</span></span> <span data-ttu-id="26d12-217">El formato de la dirección de usuario \<es\>@\<nombre\>de usuario nombreDeDominio.</span><span class="sxs-lookup"><span data-stu-id="26d12-217">The format for the user address is \<username\>@\<domainname\>.</span></span>
    
      - <span data-ttu-id="26d12-218">Para desviar la llamada a otro número de teléfono, haga clic en **Desviar a número de teléfono** y escriba el número de teléfono.</span><span class="sxs-lookup"><span data-stu-id="26d12-218">To forward the call to another telephone number, click **Forward to telephone number**, and then type the telephone number.</span></span> <span data-ttu-id="26d12-219">El formato del número de teléfono es \<\>@\<domainname\> (por ejemplo, + 14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="26d12-219">The format for the telephone number is \<number\>@\<domainname\> (for example, +14255550121@contoso.com).</span></span> <span data-ttu-id="26d12-220">El nombre de dominio se usa para redirigir al autor de la llamada al destino correcto.</span><span class="sxs-lookup"><span data-stu-id="26d12-220">The domain name is used to route the caller to the correct destination.</span></span>

27. <span data-ttu-id="26d12-221">En **Paso 6 Configurar música en espera**, elija lo que desea que escuchen los autores de las llamadas mientras esperan a un agente con uno de los procedimientos siguientes:</span><span class="sxs-lookup"><span data-stu-id="26d12-221">Under **Step 6 Configure Music on Hold**, choose what you want callers to listen to while waiting for an agent by doing one of the following:</span></span>
    
      - <span data-ttu-id="26d12-222">Para usar la grabación de música en espera predeterminada, haga clic en **Predeterminada**.</span><span class="sxs-lookup"><span data-stu-id="26d12-222">To use the default music on-hold recording, click **Use default**.</span></span>
    
      - <span data-ttu-id="26d12-p132">Para usar una grabación de archivo de audio para la música en espera, haga clic en **Seleccionar un archivo de música**. Si desea cargar un nuevo archivo de audio, haga clic en el vínculo de   **un archivo de música**. En la nueva ventana de explorador, haga clic en **Examinar**, seleccione el archivo de audio que desea usar y haga clic en **Abrir**. Haga clic en **Cargar** para cargar el archivo de audio.</span><span class="sxs-lookup"><span data-stu-id="26d12-p132">To use an audio file recording for the on-hold music, click **Select a music file**. If you want to upload a new audio file, click the **a music file** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="26d12-227">Todos los archivos de audio proporcionados por el usuario deben cumplir ciertos requisitos.</span><span class="sxs-lookup"><span data-stu-id="26d12-227">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="26d12-228">Para obtener detalles sobre los formatos de archivo admitidos, consulte <A href="lync-server-2013-technical-requirements-for-response-group.md">requisitos técnicos para el grupo de respuesta de Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="26d12-228">For details about supported file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

28. <span data-ttu-id="26d12-229">En **Paso 7 Configurar una respuesta interactiva de voz**, en   **El usuario escuchará el siguiente texto o mensaje grabado**, especifique la pregunta que desea formular a los autores de las llamadas, como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="26d12-229">Under **Step 7 Configure Interactive Voice Response**, under the **The user will hear the following text or recorded message** heading, specify the question to ask callers as follows:</span></span>
    
      - <span data-ttu-id="26d12-230">Para especificar la pregunta en formato de texto, haga clic en **Usar texto a voz** y escriba la pregunta en el cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="26d12-230">To enter the question in text format, click **Use text-to-speech**, and type the question in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="26d12-p134">No incluya etiquetas HTML en el texto que especifique. Si incluye etiquetas HTML, recibirá un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="26d12-p134">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="26d12-233">El motor de conversión de texto a voz traduce el símbolo "#" como la palabra "número".</span><span class="sxs-lookup"><span data-stu-id="26d12-233">The "#" symbol is translated by the text-to-speech engine as the word "number".</span></span> <span data-ttu-id="26d12-234">Si necesita hacer referencia a la tecla #, debe usar el nombre de tecla, en lugar de el símbolo, en el mensaje de asistencia por voz.</span><span class="sxs-lookup"><span data-stu-id="26d12-234">If you need to refer to the # key, you should use the key name, rather than the symbol, in your prompt.</span></span> <span data-ttu-id="26d12-235">Por ejemplo, "Para hablar con el departamento de ventas, presione la tecla almohadilla".</span><span class="sxs-lookup"><span data-stu-id="26d12-235">For example, "To talk to sales, press the pound key."</span></span>

        
        </div>
    
      - <span data-ttu-id="26d12-p136">Para usar un archivo de audio pregrabado que contiene la pregunta, haga clic en **Seleccionar una grabación** y en el vínculo **una grabación** para cargar el archivo. En la nueva ventana de explorador, haga clic en **Examinar**, seleccione el archivo de audio y haga clic en **Abrir**. Haga clic en **Cargar** para cargar el archivo y, si lo desea, puede escribir la pregunta en el cuadro de texto (esto permite desviar la pregunta y la respuesta del autor de la llamada al agente de respuesta).</span><span class="sxs-lookup"><span data-stu-id="26d12-p136">To use a prerecorded audio file that contains the question, click **Select a recording**, and then click the **a recording** link to upload the file. In the new browser window, click **Browse**, select the audio file, and then click **Open**. Click **Upload** to load the file, and then optionally you can type the question in the text box (this enables the question, and the caller’s response, to be forwarded to the responding agent).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="26d12-239">Todos los archivos de audio proporcionados por el usuario deben cumplir ciertos requisitos.</span><span class="sxs-lookup"><span data-stu-id="26d12-239">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="26d12-240">Para obtener detalles sobre los formatos de archivo admitidos, consulte <A href="lync-server-2013-technical-requirements-for-response-group.md">requisitos técnicos para el grupo de respuesta de Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="26d12-240">For details about supported file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

29. <span data-ttu-id="26d12-241">En **Respuesta 1**, especifique la primera respuesta posible a la pregunta con este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="26d12-241">Under **Response 1**, specify the first possible answer to the question by doing the following:</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="26d12-p138">No use comillas (") en las respuestas de voz porque provocan un error de IVR.</span><span class="sxs-lookup"><span data-stu-id="26d12-p138">Do not use quotation marks (") in any voice responses. Quotation marks cause the IVR to fail.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="26d12-244">Puede elegir si los autores de la llamada pueden responder con voz, con el teclado alfanumérico o con ambos.</span><span class="sxs-lookup"><span data-stu-id="26d12-244">You can choose to allow callers to answer using speech, alphanumeric keypad input, or both.</span></span>

    
    </div>
    
      - <span data-ttu-id="26d12-245">Si desea permitir que el autor de la llamada responda con voz, escriba la respuesta en **Especificar una respuesta de voz**.</span><span class="sxs-lookup"><span data-stu-id="26d12-245">If you want to allow the caller to respond using speech, enter the answer in **Enter a voice response**.</span></span>
    
      - <span data-ttu-id="26d12-246">Si desea permitir que el autor de la llamada presione una tecla del teclado para responder, en **Dígito**, haga clic en el dígito del teclado.</span><span class="sxs-lookup"><span data-stu-id="26d12-246">If you want to allow the caller to respond by pressing a key on the keypad, in **Digit**, click the keypad digit.</span></span>

30. <span data-ttu-id="26d12-247">Para especificar si desea redirigir al autor de la llamada a una cola o hacer otra pregunta, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="26d12-247">Specify whether to route the caller to a queue, or to ask another question as follows:</span></span>
    
      - <span data-ttu-id="26d12-248">Para redirigir al autor de la llamada a una cola, haga clic en **Enviar a una cola** y, en **Seleccionar una cola**, haga clic en la cola que desea usar.</span><span class="sxs-lookup"><span data-stu-id="26d12-248">To route the caller to a queue, click **Send to a queue**, and in **Select a queue**, click the queue that you want to use.</span></span>
    
      - <span data-ttu-id="26d12-p139">Para hacer otra pregunta, haga clic en **Formular otra pregunta**, en **Usar texto a voz** y escriba la pregunta o haga clic en **Seleccionar una grabación**. Use los grupos de respuesta de esta sección para especificar hasta cuatro respuestas posibles para la pregunta adicional y la cola que se desea usar para cada respuesta. Para especificar una tercera o cuarta respuesta posible, haga clic en las casillas **Respuesta 3** o **Respuesta 4**, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="26d12-p139">To ask another question, click **Ask another question**, and then click **Use text-to-speech** and type the question, or click **Select a recording**. Use the response groupings in this section to specify up to four possible responses to the additional question and the queue to use for each response. To specify a third or fourth possible response, click the **Response 3** check box or the **Response 4** check box.</span></span>

31. <span data-ttu-id="26d12-p140">Especifique hasta otras tres respuestas posibles para la pregunta original. Para ello, repita los pasos 28 y 29 para especificar las posibles respuestas y la acción que se debe seguir con cada respuesta. Para especificar una tercera o cuarta respuesta posible, haga clic en las casillas **Respuesta 3** o **Respuesta 4**, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="26d12-p140">Specify up to three more possible answers to the original question by repeating steps 28 and 29 to specify the possible responses and the action to take for each response. To specify a third or fourth possible answer, click the **Response 3** check box or the **Response 4** check box.</span></span>

32. <span data-ttu-id="26d12-254">Haga clic en **Implementar**.</span><span class="sxs-lookup"><span data-stu-id="26d12-254">Click **Deploy**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-an-interactive-workflow"></a><span data-ttu-id="26d12-255">Para usar Windows PowerShell para crear o modificar un flujo de trabajo interactivo</span><span class="sxs-lookup"><span data-stu-id="26d12-255">To use Windows PowerShell to create or modify an Interactive workflow</span></span>

1.  <span data-ttu-id="26d12-256">Inicie sesión como miembro del grupo RTCUniversalServerAdmins o como miembro de uno de los roles administrativos predefinidos que admiten el Grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="26d12-256">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="26d12-257">Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="26d12-257">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="26d12-p141">Recupere el nombre de servicio del servicio Grupo de respuestas y asígnelo a una variable. En la línea de comandos, ejecute:</span><span class="sxs-lookup"><span data-stu-id="26d12-p141">Retrieve the service name for the Response Group service and assign it to a variable. At the command line, run:</span></span>
    
        $serviceId="service:"+(Get-CSService | ?{$_.Applications -like "*RGS*"}).ServiceId;

4.  <span data-ttu-id="26d12-p142">Un flujo de trabajo interactivo requiere dos o más colas y dos o más grupos de agentes. En primer lugar, cree los grupos de agentes. Ejecute:</span><span class="sxs-lookup"><span data-stu-id="26d12-p142">An interactive workflow requires two or more queues and two or more agent groups. First, create the agent groups. Run:</span></span>
    
        $AGSupport = New-CsRgsAgentGroup -Parent $serviceId -Name "Technical Support" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:agent1@contoso.com", "sip:agent2@contoso.com")]
        $AGSales = New-CsRgsAgentGroup -Parent $serviceId -Name "Sales Team" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:bob@contoso.com", "sip:alice@contoso.com")]

5.  <span data-ttu-id="26d12-p143">Cree las colas. Ejecute:</span><span class="sxs-lookup"><span data-stu-id="26d12-p143">Create the queues. Run:</span></span>
    
        $QSupport = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Support" -AgentGroupIDList($AG-Support.Identity)
        $QSales = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Sales" -AgentGroupIDList($AG-Sales.Identity)

6.  <span data-ttu-id="26d12-p144">Cree el primer aviso del grupo de respuestas. Ejecute:</span><span class="sxs-lookup"><span data-stu-id="26d12-p144">Create the first response group prompt. Run:</span></span>
    
        $SupportPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please be patient while we connect you with Contoso Technical Support."

7.  <span data-ttu-id="26d12-p145">A continuación, cree la acción que debe realizarse tras el aviso. Ejecute:</span><span class="sxs-lookup"><span data-stu-id="26d12-p145">Then create the action to be performed after the prompt. Run:</span></span>
    
        $SupportAction = New-CsRgsCallAction -Prompt $SupportPrompt -Action TransferToQueue -QueueID $QSupport.Identity

8.  <span data-ttu-id="26d12-p146">Cree la primera respuesta del grupo de respuestas. Ejecute:</span><span class="sxs-lookup"><span data-stu-id="26d12-p146">Create the first response group answer. Run:</span></span>
    
        $SupportAnswer = New-CsRgsAnswer -Action $SupportAction [-DtmfResponse 1]

9.  <span data-ttu-id="26d12-p147">Ahora cree el segundo aviso, y la acción de llamada y la respuesta correspondientes. En primer lugar, cree el aviso. Ejecute:</span><span class="sxs-lookup"><span data-stu-id="26d12-p147">Now create the second prompt, call action, and answer. First create the prompt. Run:</span></span>
    
        $SalesPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please hold while we connect you with Contoso Sales."

10. <span data-ttu-id="26d12-p148">Cree la segunda acción de llamada. Ejecute:</span><span class="sxs-lookup"><span data-stu-id="26d12-p148">Create the second call action. Run:</span></span>
    
        $SalesAction = New-CsRgsCallAction -Prompt $SalesPrompt -Action TransferToQueue -QueueID $QSales.Identity

11. <span data-ttu-id="26d12-p149">Cree la segunda respuesta del grupo de respuestas. Ejecute:</span><span class="sxs-lookup"><span data-stu-id="26d12-p149">Create the second response group answer. Run:</span></span>
    
        $SalesAnswer = New-CsRgsAnswer -Action $SalesAction [-DtmfResponse 2]

12. <span data-ttu-id="26d12-p150">Cree el aviso de nivel superior. Ejecute:</span><span class="sxs-lookup"><span data-stu-id="26d12-p150">Create the top-level prompt. Run:</span></span>
    
        $TopLevelPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Thank you for calling Contoso. For Technical Support, press 1. For a Sales Representative, press 2."

13. <span data-ttu-id="26d12-p151">Cree la pregunta de nivel superior. Ejecute:</span><span class="sxs-lookup"><span data-stu-id="26d12-p151">Create the top-level question. Run:</span></span>
    
        $TopLevelQuestion = New-CsRgsQuestion -Prompt $TopLevelPrompt [-AnswerList ($SupportAnswer, $SalesAnswer)]

14. <span data-ttu-id="26d12-p152">Ahora cree el flujo de trabajo. Ejecute:</span><span class="sxs-lookup"><span data-stu-id="26d12-p152">Now create the workflow. Run:</span></span>
    
        $IVRAction = New-CsRgsCallAction -Action TransferToQuestion [-Question $Question]
        $IVRWorkflow = New-CsRgsWorkflow -Parent $ServiceId -Name "Contoso Helpdesk" [-Description "The Contoso Helpdesk line."] -PrimaryUri "sip:helpdesk@contoso.com" [-LineUri tel:+14255554321] [-DisplayNumber "+1 (425) 555-4321"] [-Active $true] [-Anonymous $true] [-DefaultAction $IVRAction] [-Managed $true] [-ManagersByURI ("sip:mindy@contoso.com", "sip:bob@contoso.com")]
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="26d12-p153">El rol CsResponseGroupManager debe asignarse a todos los usuarios que se designen como administradores de un grupo de respuesta. De lo contrario, no podrán administrar los grupos de respuestas.</span><span class="sxs-lookup"><span data-stu-id="26d12-p153">All users who have been designated as manager of a response group must be assigned th CsResponseGroupManager role. If users are not assigned this role, they cannot manage response groups.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

