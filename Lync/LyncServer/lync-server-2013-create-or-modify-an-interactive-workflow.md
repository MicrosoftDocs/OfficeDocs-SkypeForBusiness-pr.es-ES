---
title: 'Lync Server 2013: crear o modificar un flujo de trabajo interactivo'
description: 'Lync Server 2013: crear o modificar un flujo de trabajo interactivo.'
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
ms.openlocfilehash: 470a073322c48c351dbfdfb24ce376731b3e7512
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546996"
---
# <a name="create-or-modify-an-interactive-workflow-in-lync-server-2013"></a><span data-ttu-id="31710-103">Crear o modificar un flujo de trabajo interactivo en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="31710-103">Create or modify an interactive workflow in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="31710-104">_**Última modificación del tema:** 2013-09-11_</span><span class="sxs-lookup"><span data-stu-id="31710-104">_**Topic Last Modified:** 2013-09-11_</span></span>

<span data-ttu-id="31710-105">Use uno de los siguientes procedimientos para crear o modificar un flujo de trabajo interactivo.</span><span class="sxs-lookup"><span data-stu-id="31710-105">Use one of the following procedures to create or modify an interactive workflow.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="31710-106">Puede usar el shell de administración de Lync Server o la herramienta de configuración de grupos de respuesta para crear y modificar flujos de trabajo interactivos.</span><span class="sxs-lookup"><span data-stu-id="31710-106">You can use Lync Server Management Shell or the Response Group Configuration Tool to create and modify interactive workflows.</span></span> <span data-ttu-id="31710-107">Puede obtener acceso a la herramienta Configuración del grupo de respuesta desde el panel de control de Lync Server o abriendo la página web directamente desde un explorador web escribiendo la siguiente dirección URL: <STRONG>https://</STRONG> &lt; fqdngrupoweb &gt; <STRONG>/RgsConfig</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="31710-107">You can access the Response Group Configuration Tool from Lync Server Control Panel, or by opening the webpage directly from a web browser by typing the following URL: <STRONG>https://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>.</span></span>



</div>

<div>

## <a name="to-use-response-group-configuration-tool-to-create-or-modify-an-interactive-workflow"></a><span data-ttu-id="31710-108">Para usar la herramienta de configuración de grupo de respuesta para crear o modificar un flujo de trabajo interactivo</span><span class="sxs-lookup"><span data-stu-id="31710-108">To use Response Group Configuration Tool to create or modify an Interactive workflow</span></span>

1.  <span data-ttu-id="31710-109">Inicie sesión como miembro del grupo RTCUniversalServerAdmins, o como miembro de un rol administrativo predefinido que admita el grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="31710-109">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="31710-110">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="31710-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="31710-111">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="31710-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="31710-112">En la barra de navegación izquierda, haga clic en **Grupos de respuesta** y, a continuación, en **Flujo de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="31710-112">In the left navigation bar, click **Response Groups**, and then click **Workflow**.</span></span>

4.  <span data-ttu-id="31710-113">En la página **Flujo de trabajo**, haga clic en **Crear o editar flujo de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="31710-113">On the **Workflow** page, click **Create or edit a workflow**.</span></span>

5.  <span data-ttu-id="31710-114">En el campo de búsqueda **Seleccionar un servicio** escriba total o parcialmente el nombre del servicio de **ApplicationServer** que hospeda el flujo de trabajo que desea crear o modificar.</span><span class="sxs-lookup"><span data-stu-id="31710-114">In the **Select a Service** search field, type all or part of the name of the **ApplicationServer** service that hosts the workflow that you want to create or modify.</span></span> <span data-ttu-id="31710-115">En la lista de resultados que aparece, haga clic en el servicio que desea y en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="31710-115">In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="31710-116">Se abre la herramienta de configuración del grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="31710-116">The Response Group Configuration Tool opens.</span></span> <span data-ttu-id="31710-117">También puede abrir la herramienta de configuración del grupo de respuesta directamente desde un explorador Web; para ello, escriba la siguiente dirección URL: <STRONG>https://</STRONG> &lt; fqdngrupoweb &gt; <STRONG>/RgsConfig</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="31710-117">You can also open the Response Group Configuration Tool directly from a web browser by typing the following URL: <STRONG>https://</STRONG>&lt;webPoolFqdn&gt;<STRONG>/RgsConfig</STRONG>.</span></span>

    
    </div>

6.  <span data-ttu-id="31710-118">Haga una de las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="31710-118">Do one of the following:</span></span>
    
      - <span data-ttu-id="31710-119">En **Crear un nuevo flujo de trabajo**, junto a **Interactivo**, haga clic en **Crear**.</span><span class="sxs-lookup"><span data-stu-id="31710-119">Under **Create a New Workflow**, next to **Interactive**, click **Create**.</span></span>
    
      - <span data-ttu-id="31710-120">En **Administrar un flujo de trabajo existente**, busque el flujo de trabajo que desea cambiar y, en **Acción**, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="31710-120">Under **Manage an Existing Workflow**, locate the workflow you want to change, and then under **Action**, click **Edit**.</span></span>

7.  <span data-ttu-id="31710-121">Si todavía no está listo para que los usuarios comiencen a llamar al flujo de trabajo, desactive la casilla **Activar el flujo de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="31710-121">If you are not ready for users to start calling the workflow, clear the **Activate the workflow** check box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="31710-p105">Si desea crear un flujo de trabajo administrado, active <STRONG>Activar el flujo de trabajo</STRONG>. Cuando guarde el flujo de trabajo administrado activo, puede modificarlo o desactivarlo.</span><span class="sxs-lookup"><span data-stu-id="31710-p105">If you are to creating a managed workflow, you need to select <STRONG>Activate the workflow</STRONG>. After you save the active, managed workflow, you can then modify and deactivate it.</span></span>

    
    </div>

8.  <span data-ttu-id="31710-124">Para permitir que los usuarios federados puedan llamar al grupo, active la casilla **Habilitar para federación**.</span><span class="sxs-lookup"><span data-stu-id="31710-124">To allow federated users to call the group, select the **Enable for federation** check box.</span></span> <span data-ttu-id="31710-125">También debe tener una directiva de acceso externo que se aplique a la aplicación de grupo de respuesta configurada para la Federación.</span><span class="sxs-lookup"><span data-stu-id="31710-125">You must also have an external access policy that applies to the Response Group application configured for federation.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="31710-126">La Directiva de acceso externo global se aplica a la aplicación grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="31710-126">The global external access policy applies to the Response Group application.</span></span> <span data-ttu-id="31710-127">Puede configurar la directiva global para la Federación de grupos de respuesta mediante el panel de control de Lync Server o mediante el cmdlet <STRONG>set-CsExternalAccessPolicy</STRONG> para establecer el parámetro EnableOutsideAccess en true.</span><span class="sxs-lookup"><span data-stu-id="31710-127">You can configure the global policy for response group federation by using Lync Server Control Panel or by using the <STRONG>Set-CsExternalAccessPolicy</STRONG> cmdlet to set the EnableOutsideAccess parameter to True.</span></span> <span data-ttu-id="31710-128">Tenga en cuenta que la configuración de directiva global se aplicará a todos los usuarios a menos que estén asignados a un sitio o a una directiva de usuario.</span><span class="sxs-lookup"><span data-stu-id="31710-128">Keep in mind that global policy settings apply to all users unless they are assigned a site or user policy.</span></span> <span data-ttu-id="31710-129">Por lo tanto, antes de modificar este parámetro de los grupos de respuesta, asegurese de que la configuración de federación cumple con los requisitos de su organización.</span><span class="sxs-lookup"><span data-stu-id="31710-129">Therefore, before changing this setting for response groups, make sure that the federation setting meets the requirements of your organization.</span></span> <span data-ttu-id="31710-130">Para obtener más información sobre cómo se aplican las directivas a los usuarios, consulte <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">Manage external Access Policy in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="31710-130">For details about how policies apply to users, see <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">Manage external access policy in Lync Server 2013</A>.</span></span> <span data-ttu-id="31710-131">Para obtener más información sobre la configuración de Federación, consulte <STRONG>set-CsExternalAccessPolicy</STRONG> en la documentación del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="31710-131">For details about the federation setting, see <STRONG>Set-CsExternalAccessPolicy</STRONG> in Lync Server Management Shell documentation.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="31710-132">Los usuarios hospedados en Lync Online no pueden realizar llamadas a grupos de respuesta hospedados en una implementación local.</span><span class="sxs-lookup"><span data-stu-id="31710-132">Users who are hosted in Lync Online can’t place calls to response groups that are hosted in an on-premise deployment.</span></span> <span data-ttu-id="31710-133">Esto se aplica tanto en las implementaciones híbridas como en los casos en los que una implementación local se federe con una implementación de Lync Online.</span><span class="sxs-lookup"><span data-stu-id="31710-133">This is true in both hybrid deployments and in cases where an on-premise deployment is federated with a Lync Online deployment.</span></span>

    
    </div>

9.  <span data-ttu-id="31710-134">Para ocultar la identidad de los agentes durante las llamadas, active la casilla **Habilitar anonimato de agente**.</span><span class="sxs-lookup"><span data-stu-id="31710-134">To hide the identity of agents during calls, select the **Enable agent anonymity** check box.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="31710-135">Las llamadas anónimas no se pueden iniciar con mensajería instantánea o vídeo, pese a que el agente o el autor de la llamada pueden agregar mensajería instantánea y vídeo después de establecer la llamada.</span><span class="sxs-lookup"><span data-stu-id="31710-135">Anonymous calls cannot start with instant messaging (IM) or video, although the agent or the caller can add IM and video after the call is established.</span></span> <span data-ttu-id="31710-136">Asimismo, un agente anónimo puede poner llamadas en espera, transferir llamadas (tanto transferencias a otras líneas como consultas), además de estacionar y recuperar llamadas.</span><span class="sxs-lookup"><span data-stu-id="31710-136">An anonymous agent can also put calls on hold, transfer calls (both blind and consultative transfers), and park and retrieve calls.</span></span> <span data-ttu-id="31710-137">Las llamadas anónimas no admiten conferencias, uso compartido de aplicaciones ni de escritorio, transferencia de archivos, función de pizarra, colaboración de datos y grabación de llamadas.</span><span class="sxs-lookup"><span data-stu-id="31710-137">Anonymous calls do not support conferencing, application sharing and desktop sharing, file transfer, whiteboarding and data collaboration, and call recording.</span></span> <span data-ttu-id="31710-138">Los agentes que usan el complemento Lync VDI pueden recibir llamadas entrantes de forma anónima, pero no pueden realizar llamadas salientes de forma anónima.</span><span class="sxs-lookup"><span data-stu-id="31710-138">Agents using the Lync VDI Plugin can receive incoming calls anonymously, but they cannot make outgoing calls anonymously.</span></span>

    
    </div>

10. <span data-ttu-id="31710-139">En **Especifique la dirección del grupo que recibirá las llamadas**, escriba la dirección del identificador uniforme de recursos (URI) del SIP primario del grupo que responderá a las llamadas del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="31710-139">Under **Enter the address of the group that will receive the calls**, type the primary SIP uniform resource identifier (URI) address of the group that will answer calls to the workflow.</span></span>

11. <span data-ttu-id="31710-140">En **Nombre para mostrar**, escriba el nombre que desea mostrar para el flujo de trabajo (por ejemplo, Grupo de respuesta IVR de ventas).</span><span class="sxs-lookup"><span data-stu-id="31710-140">In **Display name**, type the name that you want to display for the workflow (for example, Sales IVR Response Group).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="31710-141">No incluya los caracteres " &lt; " ni "" &gt; en el nombre para mostrar.</span><span class="sxs-lookup"><span data-stu-id="31710-141">Do not include the "&lt;" or "&gt;" characters in the display name.</span></span> <span data-ttu-id="31710-142">No utilice los nombres para mostrar siguientes porque están reservados: Observador de presencia de RGS o Servicio de anuncio.</span><span class="sxs-lookup"><span data-stu-id="31710-142">Do not use the following display names because they are reserved: RGS Presence Watcher or Announcement Service.</span></span>

    
    </div>

12. <span data-ttu-id="31710-143">En **Número de teléfono**, especifique el URI de línea para el grupo de respuesta (por ejemplo, +14255550165).</span><span class="sxs-lookup"><span data-stu-id="31710-143">In **Telephone number**, type the line URI for the response group (for example, +14255550165).</span></span>

13. <span data-ttu-id="31710-144">En **Número para mostrar**, escriba el número tal como desea que aparezca para el grupo de respuesta (por ejemplo, +1 (425) 555-0165).</span><span class="sxs-lookup"><span data-stu-id="31710-144">In **Display number**, type the number as you want it to appear for the response group (for example, +1 (425) 555-0165).</span></span>

14. <span data-ttu-id="31710-145">Opcional En **Descripción**, escriba una descripción para el flujo de trabajo que desea que aparezca en la tarjeta de contacto en el cliente de Lync.</span><span class="sxs-lookup"><span data-stu-id="31710-145">(Optional) In **Description**, type a description for the workflow that you want to appear on the contact card in the Lync client.</span></span>

15. <span data-ttu-id="31710-146">En **Tipo de flujo de trabajo**, seleccione **Administrado** si un administrador de grupos de respuesta va a administrar este flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="31710-146">In **Workflow Type**, select **Managed** if this workflow will be managed by a Response Group Manager.</span></span> <span data-ttu-id="31710-147">Haga lo siguiente para asignar administradores del grupo de respuesta al flujo de trabajo:</span><span class="sxs-lookup"><span data-stu-id="31710-147">Do the following to assign Response Group Managers to the workflow:</span></span>
    
    1.  <span data-ttu-id="31710-148">Escriba el URI del SIP de un administrador para este flujo de trabajo y haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="31710-148">Type the SIP URI of a manager for this workflow, and click **Add**..</span></span>
    
    2.  <span data-ttu-id="31710-149">Escriba el URI del SIP de otros administradores para agregar al flujo de trabajo y haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="31710-149">Type the SIP URI of additional managers to add to the workflow, and click **Add**..</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="31710-p112">El rol CsResponseGroupManager debe asignarse a todos los usuarios que se designen como administradores de un grupo de respuesta. De lo contrario, no podrán administrar los grupos de respuesta.</span><span class="sxs-lookup"><span data-stu-id="31710-p112">Every user who is designated as a manager of a response group must be assigned the CsResponseGroupManager role. If users are not assigned this role, they cannot manage response groups.</span></span>

    
    </div>

16. <span data-ttu-id="31710-152">En **Paso 2 Seleccionar un idioma**, haga clic en el idioma que se usará para el reconocimiento de voz y texto a voz.</span><span class="sxs-lookup"><span data-stu-id="31710-152">Under **Step 2 Select a Language**, click the language to use for speech recognition and text-to-speech.</span></span>

17. <span data-ttu-id="31710-153">Si desea definir un mensaje de bienvenida, en el **Paso 3 Configurar un mensaje de bienvenida**, active la casilla **Reproducir un mensaje de bienvenida** y, a continuación, lleve a cabo uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="31710-153">If you want to configure a welcome message, under **Step 3 Configure a Welcome Message**, select the **Play a welcome message** check box, and then do one of the following:</span></span>
    
      - <span data-ttu-id="31710-154">Para escribir el mensaje de bienvenida como texto que se convertirá en voz para los autores de llamadas, haga clic en **Usar texto a voz** y, a continuación, escriba el mensaje de bienvenida en el cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="31710-154">To enter the welcome message as text that is converted to speech for callers, click **Use text-to-speech**, and then type the welcome message in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="31710-p113">No incluya etiquetas HTML en el texto que especifique. Si incluye etiquetas HTML, recibirá un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="31710-p113">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
    
      - <span data-ttu-id="31710-p114">Para utilizar una grabación en archivo de Wave o Windows Media para el mensaje de bienvenida, haga clic en **Seleccionar una grabación**. Si desea cargar un archivo de audio nuevo, haga clic en el vínculo **una grabación**. En la nueva ventana del explorador, haga clic en **Examinar**, seleccione el archivo de audio que desea utilizar y, a continuación, haga clic en **Abrir**. Haga clic en **Cargar** para cargar el archivo de audio.</span><span class="sxs-lookup"><span data-stu-id="31710-p114">To use a Wave or Windows Media Audio file recording for the welcome message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the audio file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="31710-161">Todos los archivos de audio proporcionados por el usuario deben cumplir ciertos requisitos.</span><span class="sxs-lookup"><span data-stu-id="31710-161">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="31710-162">Para obtener más información sobre los formatos de archivo compatibles, consulte <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical Requirements for Response Group in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="31710-162">For details about supported file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

18. <span data-ttu-id="31710-163">En **Paso 4 Especificar horario de oficina**, en el cuadro **Su zona horaria**, haga clic en la zona horaria del flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="31710-163">Under **Step 4 Specify Your Business Hours**, in the **Your time zone** box, click the time zone of the workflow.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="31710-p116">La zona horaria se refiere a la zona donde residen los autores de llamadas y los agentes del flujo de trabajo. Se usa para calcular las horas de apertura y cierre. Por ejemplo, si el flujo de trabajo está configurado para usar la zona horaria Hora oriental de América del Norte y el flujo de trabajo está programado para abrir a las 7:00 y cerrar a 23:00, se supone que las horas de apertura y cierre son las 7:00 (Hora del este) y las 23:00 (Hora del este) respectivamente. Escriba las horas en la notación de 24 horas.</span><span class="sxs-lookup"><span data-stu-id="31710-p116">The time zone is the time zone where the callers and agents of the workflow reside. It is used to calculate the open and close hours. For example, if the workflow is configured to use the North American Eastern Time zone and the workflow is scheduled to open at 7:00 A.M. and close at 11:00 P.M., the open and close times are assumed to be 7:00 Eastern Time and 11:00 Eastern Time respectively. (You must enter the times in 24-hour time notation.)</span></span>

    
    </div>

19. <span data-ttu-id="31710-169">Para seleccionar el tipo de programación de horario de oficina que quiere usar, siga uno de los procedimientos siguientes:</span><span class="sxs-lookup"><span data-stu-id="31710-169">Select the type of business hours schedule you want to use by doing one of the following:</span></span>
    
      - <span data-ttu-id="31710-170">Para utilizar una programación predefinida de horario de oficina, haga clic en **Utilizar una programación preestablecida** y, a continuación, seleccione el horario que desea utilizar en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="31710-170">To use a predefined schedule of business hours, click **Use a preset schedule**, and then select the schedule you want to use from the drop-down list.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="31710-171">Debe definir al menos una programación preestablecida previamente para poder seleccionar esta opción.</span><span class="sxs-lookup"><span data-stu-id="31710-171">You must have defined at least one preset schedule previously to be able to select this option.</span></span> <span data-ttu-id="31710-172">Puede definir programaciones preestablecidas con el cmdlet <STRONG>New-CSRgsHoursOfBusiness</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="31710-172">You define preset schedules by using the <STRONG>New-CSRgsHoursOfBusiness</STRONG> cmdlet.</span></span> <span data-ttu-id="31710-173">Para obtener más información, consulte <A href="lync-server-2013-optional-define-response-group-business-hours.md">(optional) define Response Group Business hours in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="31710-173">For details, see <A href="lync-server-2013-optional-define-response-group-business-hours.md">(Optional) Define Response Group business hours in Lync Server 2013</A>.</span></span> <span data-ttu-id="31710-174">Cuando selecciona una programación preestablecida, <STRONG>Día</STRONG>, <STRONG>Abrir</STRONG> y <STRONG>Cerrar</STRONG> se rellenan automáticamente con los días y las horas en los que el grupo de respuesta se encuentra disponible.</span><span class="sxs-lookup"><span data-stu-id="31710-174">When you select a preset schedule, <STRONG>Day</STRONG>, <STRONG>Open</STRONG>, and <STRONG>Close</STRONG> are automatically filled with the days and hours that the response group is available.</span></span>

        
        </div>
    
      - <span data-ttu-id="31710-175">Para utilizar una programación personalizada que se aplique únicamente a este flujo de trabajo, haga clic en **Usar programación personalizada**.</span><span class="sxs-lookup"><span data-stu-id="31710-175">To use a custom schedule that applies only to this workflow, click **Use a custom schedule**.</span></span>

20. <span data-ttu-id="31710-176">Si está creando una programación personalizada para este flujo de trabajo, haga clic en las casillas correspondientes a los días de la semana durante los que se encuentra disponible el grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="31710-176">If you are creating a custom schedule for this workflow, click the check boxes for the days of the week that the response group is available.</span></span>

21. <span data-ttu-id="31710-177">Si está creando una programación personalizada, especifique las horas en **Abrir** y **Cerrar** durante las que estará disponible el grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="31710-177">If you are creating a custom schedule, type the **Open** and **Close** hours when the response group available.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="31710-p118">Las horas en <STRONG>Abrir</STRONG> y <STRONG>Cerrar</STRONG> deben mostrarse en formato de 24 horas. Por ejemplo, si en su oficina se trabaja de 9 a 5 y se cierra al mediodía para el almuerzo, el horario de oficina queda representado como <STRONG>Abrir</STRONG> 9:00, <STRONG>Cerrar</STRONG> 12:00, <STRONG>Abrir</STRONG> 13:00 y <STRONG>Cerrar</STRONG> 17:00.</span><span class="sxs-lookup"><span data-stu-id="31710-p118">The <STRONG>Open</STRONG> and <STRONG>Close</STRONG> hours must be in 24-hour time notation. For example, if your office works a 9-to-5 work day and closes at noon for lunch, the business hours are specified as <STRONG>Open</STRONG> 9:00, <STRONG>Close</STRONG> 12:00, <STRONG>Open</STRONG> 13:00, and <STRONG>Close</STRONG> 17:00.</span></span>

    
    </div>

22. <span data-ttu-id="31710-180">Si desea reproducir un mensaje cuando la oficina no esté abierta, active la casilla **Reproducir un mensaje cuando el grupo de respuesta no está en horario de oficina** y, a continuación, especifique el mensaje que se va a reproducir mediante uno de los procedimientos siguientes:</span><span class="sxs-lookup"><span data-stu-id="31710-180">If you want to play a message when the office is not open, select the **Play a message when the response group is outside of business hours** check box, and then specify the message to play by doing one of the following:</span></span>
    
      - <span data-ttu-id="31710-181">Para escribir el mensaje como texto que se convertirá en voz para el autor de la llamada, haga clic en **Usar texto a voz** y, a continuación, escriba el mensaje de bienvenida en el cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="31710-181">To enter the message as text that is converted to speech for the caller, click **Use text-to-speech**, and then type the message in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="31710-p119">No incluya etiquetas HTML en el texto que especifique. Si incluye etiquetas HTML, recibirá un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="31710-p119">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
    
      - <span data-ttu-id="31710-p120">Para utilizar una grabación en un archivo de audio para el mensaje, haga clic en **Seleccionar una grabación**. Si desea cargar un archivo de audio nuevo, haga clic en el vínculo **una grabación**. En la nueva ventana del explorador, haga clic en **Examinar**, seleccione el archivo que desea utilizar y, a continuación, haga clic en **Abrir**. Haga clic en **Cargar** para cargar el archivo de audio.</span><span class="sxs-lookup"><span data-stu-id="31710-p120">To use an audio file recording for the message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="31710-188">Todos los archivos de audio suministrados por el usuario deben cumplir determinados requisitos.</span><span class="sxs-lookup"><span data-stu-id="31710-188">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="31710-189">Para obtener más información sobre los formatos de archivo compatibles, consulte <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical Requirements for Response Group in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="31710-189">For details about supported file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

23. <span data-ttu-id="31710-190">Especifique cómo abordar las llamadas tras la reproducción del mensaje (si se ha configurado uno):</span><span class="sxs-lookup"><span data-stu-id="31710-190">Specify how to handle calls after the message is played (if a message is configured):</span></span>
    
      - <span data-ttu-id="31710-191">Para desconectar la llamada, haga clic en **Desconectar llamada**.</span><span class="sxs-lookup"><span data-stu-id="31710-191">To disconnect the call, click **Disconnect Call**.</span></span>
    
      - <span data-ttu-id="31710-192">Para desviar la llamada al correo de voz, haga clic en **Desviar a correo de voz** y, a continuación, escriba la dirección del correo de voz.</span><span class="sxs-lookup"><span data-stu-id="31710-192">To forward the call to voice mail, click **Forward to voice mail**, and then type the voice mail address.</span></span> <span data-ttu-id="31710-193">El formato de la dirección de correo de voz es \<username\> @ \<domainname\> (por ejemplo, Bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="31710-193">The format for the voice mail address is \<username\>@\<domainname\> (for example, bob@contoso.com).</span></span>
    
      - <span data-ttu-id="31710-194">Para desviar la llamada a otro usuario, haga clic en **Desviar a URI de SIP** y, a continuación, escriba la dirección de un usuario.</span><span class="sxs-lookup"><span data-stu-id="31710-194">To forward the call to another user, click **Forward to SIP URI**, and then type a user address.</span></span> <span data-ttu-id="31710-195">El formato de la dirección de usuario es \<username\> @ \<domainname\> .</span><span class="sxs-lookup"><span data-stu-id="31710-195">The format for the user address is \<username\>@\<domainname\>.</span></span>
    
      - <span data-ttu-id="31710-196">Para desviar la llamada a otro número de teléfono, haga clic en **Desviar a número de teléfono** y, a continuación, escriba el número de teléfono.</span><span class="sxs-lookup"><span data-stu-id="31710-196">To forward the call to another telephone number, click **Forward to telephone number**, and then type the telephone number.</span></span> <span data-ttu-id="31710-197">El formato del número de teléfono es \<number\> @ \<domainname\> (por ejemplo, + 14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="31710-197">The format for the telephone number is \<number\>@\<domainname\> (for example, +14255550121@contoso.com).</span></span> <span data-ttu-id="31710-198">El nombre de dominio se usa para enrutar al autor de la llamada al destino correcto.</span><span class="sxs-lookup"><span data-stu-id="31710-198">The domain name is used to route the caller to the correct destination.</span></span>

24. <span data-ttu-id="31710-199">En **Paso 5 Especificar días festivos**, haga clic en las casillas para uno o más conjuntos de días festivos que definan los días en los que el grupo de respuesta no esté laboralmente disponible.</span><span class="sxs-lookup"><span data-stu-id="31710-199">Under **Step 5 Specify Your Holidays**, click the check boxes for one or more sets of holidays that define the days when the response group is closed for business.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="31710-200">Debe definir las vacaciones y los conjuntos de vacaciones antes de configurar el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="31710-200">You need to define holidays and holiday sets before you configure the workflow.</span></span> <span data-ttu-id="31710-201">Use los cmdlets <STRONG>New-CsRgsHoliday</STRONG> y <STRONG>New-CsRgsHolidaySet</STRONG> para definir las vacaciones y los conjuntos de vacaciones.</span><span class="sxs-lookup"><span data-stu-id="31710-201">Use the <STRONG>New-CsRgsHoliday</STRONG> and <STRONG>New-CsRgsHolidaySet</STRONG> cmdlets to define holidays and holiday sets.</span></span> <span data-ttu-id="31710-202">Para obtener más información, consulte <A href="lync-server-2013-optional-define-response-group-holiday-sets.md">(opcional) definir conjuntos de días festivos para grupos de respuesta en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="31710-202">For details, see <A href="lync-server-2013-optional-define-response-group-holiday-sets.md">(Optional) Define Response Group holiday sets in Lync Server 2013</A>.</span></span>

    
    </div>

25. <span data-ttu-id="31710-203">Si desea reproducir un mensaje durante los días festivos, active la casilla **Reproducir un mensaje durante los días festivos** y, a continuación, especifique el mensaje que se va a reproducir mediante uno de los siguientes procedimientos:</span><span class="sxs-lookup"><span data-stu-id="31710-203">If you want to play a message on holidays, select the **Play a message during holidays** check box, and then specify the message to play by doing one of the following:</span></span>
    
      - <span data-ttu-id="31710-204">Para escribir el mensaje como texto que se convertirá en voz para el autor de la llamada, haga clic en **Usar texto a voz** y, a continuación, escriba el mensaje de bienvenida en el cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="31710-204">To enter the message as text that is converted to speech for the caller, click **Use text-to-speech**, and then type the message in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="31710-p126">No incluya etiquetas HTML en el texto que especifique. Si incluye etiquetas HTML, recibirá un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="31710-p126">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
    
      - <span data-ttu-id="31710-p127">Para utilizar una grabación en un archivo de audio para el mensaje, haga clic en **Seleccionar una grabación**. Si desea cargar un archivo de audio nuevo, haga clic en el vínculo **una grabación**. En la nueva ventana del explorador, haga clic en **Examinar**, seleccione el archivo que desea utilizar y, a continuación, haga clic en **Abrir**. Haga clic en **Cargar** para cargar el archivo de audio.</span><span class="sxs-lookup"><span data-stu-id="31710-p127">To use an audio file recording for the message, click **Select a recording**. If you want to upload a new audio file, click the **a recording** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="31710-211">Todos los archivos de audio suministrados por el usuario deben cumplir determinados requisitos.</span><span class="sxs-lookup"><span data-stu-id="31710-211">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="31710-212">Para obtener más información sobre los formatos de archivo de audio admitidos, consulte <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical Requirements for Response Group in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="31710-212">For details about supported audio file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

26. <span data-ttu-id="31710-213">Especifique cómo abordar las llamadas tras la reproducción del mensaje (si se ha configurado uno):</span><span class="sxs-lookup"><span data-stu-id="31710-213">Specify how to handle calls after the message is played (if a message is configured):</span></span>
    
      - <span data-ttu-id="31710-214">Para desconectar la llamada, haga clic en **Desconectar llamada**.</span><span class="sxs-lookup"><span data-stu-id="31710-214">To disconnect the call, click **Disconnect Call**.</span></span>
    
      - <span data-ttu-id="31710-215">Para desviar la llamada al correo de voz, haga clic en **Desviar a correo de voz** y, a continuación, escriba la dirección del correo de voz.</span><span class="sxs-lookup"><span data-stu-id="31710-215">To forward the call to voice mail, click **Forward to voice mail**, and then type the voice mail address.</span></span> <span data-ttu-id="31710-216">El formato de la dirección de correo de voz es \<username\> @ \<domainname\> (por ejemplo, Bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="31710-216">The format for the voice mail address is \<username\>@\<domainname\> (for example, bob@contoso.com).</span></span>
    
      - <span data-ttu-id="31710-217">Para desviar la llamada a otro usuario, haga clic en **Desviar a URI de SIP** y, a continuación, escriba la dirección de un usuario.</span><span class="sxs-lookup"><span data-stu-id="31710-217">To forward the call to another user, click **Forward to SIP URI**, and then type a user address.</span></span> <span data-ttu-id="31710-218">El formato de la dirección de usuario es \<username\> @ \<domainname\> .</span><span class="sxs-lookup"><span data-stu-id="31710-218">The format for the user address is \<username\>@\<domainname\>.</span></span>
    
      - <span data-ttu-id="31710-219">Para desviar la llamada a otro número de teléfono, haga clic en **Desviar a número de teléfono** y, a continuación, escriba el número de teléfono.</span><span class="sxs-lookup"><span data-stu-id="31710-219">To forward the call to another telephone number, click **Forward to telephone number**, and then type the telephone number.</span></span> <span data-ttu-id="31710-220">El formato del número de teléfono es \<number\> @ \<domainname\> (por ejemplo, + 14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="31710-220">The format for the telephone number is \<number\>@\<domainname\> (for example, +14255550121@contoso.com).</span></span> <span data-ttu-id="31710-221">El nombre de dominio se usa para enrutar al autor de la llamada al destino correcto.</span><span class="sxs-lookup"><span data-stu-id="31710-221">The domain name is used to route the caller to the correct destination.</span></span>

27. <span data-ttu-id="31710-222">En el **Paso 6 Configurar música en espera**, elija lo que desea que escuchen los autores de las llamadas mientras esperan a un agente siguiendo uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="31710-222">Under **Step 6 Configure Music on Hold**, choose what you want callers to listen to while waiting for an agent by doing one of the following:</span></span>
    
      - <span data-ttu-id="31710-223">Para usar la grabación predeterminada de música en espera, haga clic en **Usar predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="31710-223">To use the default music on-hold recording, click **Use default**.</span></span>
    
      - <span data-ttu-id="31710-p132">Para utilizar una grabación en un archivo de audio para la música en espera, haga clic en **Seleccionar una música**. Si desea cargar un archivo de audio nuevo, haga clic en el vínculo **un archivo de música**. En la nueva ventana del explorador, haga clic en **Examinar**, seleccione el archivo que desea utilizar y, a continuación, haga clic en **Abrir**. Haga clic en **Cargar** para cargar el archivo de audio.</span><span class="sxs-lookup"><span data-stu-id="31710-p132">To use an audio file recording for the on-hold music, click **Select a music file**. If you want to upload a new audio file, click the **a music file** link. In the new browser window, click **Browse**, select the file that you want to use, and then click **Open**. Click **Upload** to load the audio file.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="31710-228">Todos los archivos de audio proporcionados por el usuario deben cumplir ciertos requisitos.</span><span class="sxs-lookup"><span data-stu-id="31710-228">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="31710-229">Para obtener más información sobre los formatos de archivo compatibles, consulte <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical Requirements for Response Group in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="31710-229">For details about supported file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

28. <span data-ttu-id="31710-230">En **Paso 7 Configurar respuesta de voz interactiva**, bajo el encabezado **El usuario oirá el siguiente texto o mensaje grabado**, especifique la pregunta que se va a formular a los autores de las llamadas de la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="31710-230">Under **Step 7 Configure Interactive Voice Response**, under the **The user will hear the following text or recorded message** heading, specify the question to ask callers as follows:</span></span>
    
      - <span data-ttu-id="31710-231">Para escribir la pregunta en formato de texto, haga clic en **Usar texto a voz** y, a continuación, escriba la pregunta en el cuadro de texto.</span><span class="sxs-lookup"><span data-stu-id="31710-231">To enter the question in text format, click **Use text-to-speech**, and type the question in the text box.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="31710-p134">No incluya etiquetas HTML en el texto que especifique. Si incluye etiquetas HTML, recibirá un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="31710-p134">Do not include HTML tags in the text you enter. If you include HTML tags, you will receive an error message.</span></span>

        
        </div>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="31710-234">El motor de síntesis de texto a voz traduce el símbolo "#" como la palabra "número".</span><span class="sxs-lookup"><span data-stu-id="31710-234">The "#" symbol is translated by the text-to-speech engine as the word "number".</span></span> <span data-ttu-id="31710-235">Si necesita hacer referencia a la tecla # en el mensaje, debe usar el nombre de la tecla, en lugar del símbolo.</span><span class="sxs-lookup"><span data-stu-id="31710-235">If you need to refer to the # key, you should use the key name, rather than the symbol, in your prompt.</span></span> <span data-ttu-id="31710-236">Por ejemplo, "Para hablar con el departamento de ventas, presione la tecla almohadilla".</span><span class="sxs-lookup"><span data-stu-id="31710-236">For example, "To talk to sales, press the pound key."</span></span>

        
        </div>
    
      - <span data-ttu-id="31710-p136">Para utilizar un archivo de audio pregrabado que contenga la pregunta, haga clic en **Seleccionar una grabación** y, a continuación, en el vínculo **una grabación** para cargar el archivo. En la nueva ventana del explorador, haga clic en **Examinar**, seleccione el archivo de audio y, a continuación, haga clic en **Abrir**. Haga clic en **Cargar** para cargar el archivo y, a continuación, de forma opcional, podrá escribir la pregunta en el cuadro de texto (esto permite que la pregunta y la respuesta del autor de la llamada se desvíen al agente encargado de responder).</span><span class="sxs-lookup"><span data-stu-id="31710-p136">To use a prerecorded audio file that contains the question, click **Select a recording**, and then click the **a recording** link to upload the file. In the new browser window, click **Browse**, select the audio file, and then click **Open**. Click **Upload** to load the file, and then optionally you can type the question in the text box (this enables the question, and the caller’s response, to be forwarded to the responding agent).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="31710-240">Todos los archivos de audio proporcionados por el usuario deben cumplir ciertos requisitos.</span><span class="sxs-lookup"><span data-stu-id="31710-240">All user-provided audio files must meet certain requirements.</span></span> <span data-ttu-id="31710-241">Para obtener más información sobre los formatos de archivo compatibles, consulte <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical Requirements for Response Group in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="31710-241">For details about supported file formats, see <A href="lync-server-2013-technical-requirements-for-response-group.md">Technical requirements for Response Group in Lync Server 2013</A>.</span></span>

        
        </div>

29. <span data-ttu-id="31710-242">En **Respuesta 1**, especifique la primera respuesta posible a la pregunta de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="31710-242">Under **Response 1**, specify the first possible answer to the question by doing the following:</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="31710-p138">No utilice comillas (") en las respuestas de voz. Las comillas producen un error en la respuesta interactiva de voz (IVR).</span><span class="sxs-lookup"><span data-stu-id="31710-p138">Do not use quotation marks (") in any voice responses. Quotation marks cause the IVR to fail.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="31710-245">Puede permitir que los autores de las llamadas respondan mediante voz, el teclado alfanumérico o ambas cosas.</span><span class="sxs-lookup"><span data-stu-id="31710-245">You can choose to allow callers to answer using speech, alphanumeric keypad input, or both.</span></span>

    
    </div>
    
      - <span data-ttu-id="31710-246">Si desea permitir al autor de la llamada que responda mediante voz, escriba la respuesta en **Escribir una respuesta de voz**.</span><span class="sxs-lookup"><span data-stu-id="31710-246">If you want to allow the caller to respond using speech, enter the answer in **Enter a voice response**.</span></span>
    
      - <span data-ttu-id="31710-247">Si desea permitir al autor de la llamada que responda presionando una tecla del teclado numérico, haga clic en **Dígito** y en el dígito del teclado numérico.</span><span class="sxs-lookup"><span data-stu-id="31710-247">If you want to allow the caller to respond by pressing a key on the keypad, in **Digit**, click the keypad digit.</span></span>

30. <span data-ttu-id="31710-248">Especifique si desea enrutar al autor de la llamada a una cola o hacer otra pregunta, de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="31710-248">Specify whether to route the caller to a queue, or to ask another question as follows:</span></span>
    
      - <span data-ttu-id="31710-249">Para enrutar al autor de la llamada hacia una cola, haga clic en **Enviar a una cola** y, en **Seleccionar una cola**, haga clic en la cola que desee utilizar.</span><span class="sxs-lookup"><span data-stu-id="31710-249">To route the caller to a queue, click **Send to a queue**, and in **Select a queue**, click the queue that you want to use.</span></span>
    
      - <span data-ttu-id="31710-p139">Para hacer otra pregunta, haga clic en **Formular otra pregunta** y en **Usar texto a voz**, escriba la pregunta o haga clic en **Seleccionar una grabación**. Use los grupos de respuesta de esta sección para especificar hasta cuatro respuestas posibles para la pregunta adicional y la cola que se desea usar para cada respuesta. Para especificar una tercera o cuarta respuesta posible, haga clic en las casillas **Respuesta 3** o **Respuesta 4** respectivamente.</span><span class="sxs-lookup"><span data-stu-id="31710-p139">To ask another question, click **Ask another question**, and then click **Use text-to-speech** and type the question, or click **Select a recording**. Use the response groupings in this section to specify up to four possible responses to the additional question and the queue to use for each response. To specify a third or fourth possible response, click the **Response 3** check box or the **Response 4** check box.</span></span>

31. <span data-ttu-id="31710-p140">Especifique hasta otras tres respuestas posibles para la pregunta original. Para ello, repita los pasos 28 y 29 para especificar las posibles respuestas y la acción que se debe seguir con cada respuesta. Para especificar una tercera o cuarta respuesta posible, haga clic en las casillas **Respuesta 3** o **Respuesta 4** respectivamente.</span><span class="sxs-lookup"><span data-stu-id="31710-p140">Specify up to three more possible answers to the original question by repeating steps 28 and 29 to specify the possible responses and the action to take for each response. To specify a third or fourth possible answer, click the **Response 3** check box or the **Response 4** check box.</span></span>

32. <span data-ttu-id="31710-255">Haga clic en **Implementar**.</span><span class="sxs-lookup"><span data-stu-id="31710-255">Click **Deploy**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-an-interactive-workflow"></a><span data-ttu-id="31710-256">Para usar Windows PowerShell para crear o modificar un flujo de trabajo interactivo</span><span class="sxs-lookup"><span data-stu-id="31710-256">To use Windows PowerShell to create or modify an Interactive workflow</span></span>

1.  <span data-ttu-id="31710-257">Inicie sesión como miembro del grupo RTCUniversalServerAdmins, o como miembro de un rol administrativo predefinido que admita el grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="31710-257">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="31710-258">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="31710-258">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="31710-p141">Recupere el nombre del servicio para el servicio del grupo de respuesta y asígnelo a una variable. En la línea de comandos, ejecute:</span><span class="sxs-lookup"><span data-stu-id="31710-p141">Retrieve the service name for the Response Group service and assign it to a variable. At the command line, run:</span></span>
    
        $serviceId="service:"+(Get-CSService | ?{$_.Applications -like "*RGS*"}).ServiceId;

4.  <span data-ttu-id="31710-p142">Un flujo de trabajo interactivo requiere dos o más colas y dos o más grupos de agentes. En primer lugar, cree los grupos de agentes. Ejecute:</span><span class="sxs-lookup"><span data-stu-id="31710-p142">An interactive workflow requires two or more queues and two or more agent groups. First, create the agent groups. Run:</span></span>
    
        $AGSupport = New-CsRgsAgentGroup -Parent $serviceId -Name "Technical Support" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:agent1@contoso.com", "sip:agent2@contoso.com")]
        $AGSales = New-CsRgsAgentGroup -Parent $serviceId -Name "Sales Team" [-AgentAlertTime "20"] [-ParticipationPolicy "Informal"] [-RoutingMethod LongestIdle] [-AgentsByUri("sip:bob@contoso.com", "sip:alice@contoso.com")]

5.  <span data-ttu-id="31710-p143">Cree las colas. Ejecute:</span><span class="sxs-lookup"><span data-stu-id="31710-p143">Create the queues. Run:</span></span>
    
        $QSupport = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Support" -AgentGroupIDList($AG-Support.Identity)
        $QSales = New-CsRgsQueue -Parent $ServiceId -Name "Contoso Sales" -AgentGroupIDList($AG-Sales.Identity)

6.  <span data-ttu-id="31710-p144">Cree el primer aviso de grupo de respuesta. Ejecute:</span><span class="sxs-lookup"><span data-stu-id="31710-p144">Create the first response group prompt. Run:</span></span>
    
        $SupportPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please be patient while we connect you with Contoso Technical Support."

7.  <span data-ttu-id="31710-p145">A continuación, cree la acción que debe realizarse tras el aviso. Ejecute:</span><span class="sxs-lookup"><span data-stu-id="31710-p145">Then create the action to be performed after the prompt. Run:</span></span>
    
        $SupportAction = New-CsRgsCallAction -Prompt $SupportPrompt -Action TransferToQueue -QueueID $QSupport.Identity

8.  <span data-ttu-id="31710-p146">Cree la primera respuesta de grupo de respuesta. Ejecute:</span><span class="sxs-lookup"><span data-stu-id="31710-p146">Create the first response group answer. Run:</span></span>
    
        $SupportAnswer = New-CsRgsAnswer -Action $SupportAction [-DtmfResponse 1]

9.  <span data-ttu-id="31710-p147">Ahora cree el segundo aviso, y la acción de llamada y la respuesta correspondientes. En primer lugar, cree el aviso. Ejecute:</span><span class="sxs-lookup"><span data-stu-id="31710-p147">Now create the second prompt, call action, and answer. First create the prompt. Run:</span></span>
    
        $SalesPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Please hold while we connect you with Contoso Sales."

10. <span data-ttu-id="31710-p148">Cree la segunda acción de llamada. Ejecute:</span><span class="sxs-lookup"><span data-stu-id="31710-p148">Create the second call action. Run:</span></span>
    
        $SalesAction = New-CsRgsCallAction -Prompt $SalesPrompt -Action TransferToQueue -QueueID $QSales.Identity

11. <span data-ttu-id="31710-p149">Cree la segunda respuesta de grupo de respuesta. Ejecute:</span><span class="sxs-lookup"><span data-stu-id="31710-p149">Create the second response group answer. Run:</span></span>
    
        $SalesAnswer = New-CsRgsAnswer -Action $SalesAction [-DtmfResponse 2]

12. <span data-ttu-id="31710-p150">Cree el aviso de nivel superior. Ejecute:</span><span class="sxs-lookup"><span data-stu-id="31710-p150">Create the top-level prompt. Run:</span></span>
    
        $TopLevelPrompt = New-CsRgsPrompt -TextToSpeechPrompt "Thank you for calling Contoso. For Technical Support, press 1. For a Sales Representative, press 2."

13. <span data-ttu-id="31710-p151">Cree la pregunta de nivel superior. Ejecute:</span><span class="sxs-lookup"><span data-stu-id="31710-p151">Create the top-level question. Run:</span></span>
    
        $TopLevelQuestion = New-CsRgsQuestion -Prompt $TopLevelPrompt [-AnswerList ($SupportAnswer, $SalesAnswer)]

14. <span data-ttu-id="31710-p152">Ahora cree el flujo de trabajo. Ejecute:</span><span class="sxs-lookup"><span data-stu-id="31710-p152">Now create the workflow. Run:</span></span>
    
        $IVRAction = New-CsRgsCallAction -Action TransferToQuestion [-Question $Question]
        $IVRWorkflow = New-CsRgsWorkflow -Parent $ServiceId -Name "Contoso Helpdesk" [-Description "The Contoso Helpdesk line."] -PrimaryUri "sip:helpdesk@contoso.com" [-LineUri tel:+14255554321] [-DisplayNumber "+1 (425) 555-4321"] [-Active $true] [-Anonymous $true] [-DefaultAction $IVRAction] [-Managed $true] [-ManagersByURI ("sip:mindy@contoso.com", "sip:bob@contoso.com")]
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="31710-p153">El rol CsResponseGroupManager debe asignarse a todos los usuarios que se designen como administradores de un grupo de respuesta. De lo contrario, no podrán administrar los grupos de respuesta.</span><span class="sxs-lookup"><span data-stu-id="31710-p153">All users who have been designated as manager of a response group must be assigned th CsResponseGroupManager role. If users are not assigned this role, they cannot manage response groups.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

