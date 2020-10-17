---
title: 'Lync Server 2013: crear una directiva de voz y configurar los registros de uso de RTC'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a voice policy and configure PSTN usage records
ms:assetid: e6ff27e0-e2d1-4445-840f-08f738200c20
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399027(v=OCS.15)
ms:contentKeyID: 48185693
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cbf6a0c8e6d1d2e72ba7381af41fe86f645b827d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501837"
---
# <a name="create-a-voice-policy-and-configure-pstn-usage-records-in-lync-server-2013"></a><span data-ttu-id="5fec2-102">Crear una directiva de voz y configurar los registros de uso de RTC en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5fec2-102">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5fec2-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="5fec2-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="5fec2-104">Siga estos pasos para crear una nueva directiva de voz.</span><span class="sxs-lookup"><span data-stu-id="5fec2-104">Follow these steps if you want to create a new voice policy.</span></span> <span data-ttu-id="5fec2-105">Si desea editar una directiva de voz, consulte [modificar una directiva de voz y configurar los registros de uso de RTC en Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md) para el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="5fec2-105">If you want to edit a voice policy, see [Modify a voice policy and configure PSTN usage records in Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md) for the procedure.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5fec2-106">Cada directiva de voz debe tener al menos un registro de uso de RTC asociado.</span><span class="sxs-lookup"><span data-stu-id="5fec2-106">Each voice policy must have at least one associated public switched telephone network (PSTN) usage record.</span></span> <span data-ttu-id="5fec2-107">Para ver una lista de todos los registros de uso de RTC disponibles en la implementación de telefonía IP empresarial y ver sus propiedades, consulte <A href="lync-server-2013-view-pstn-usage-records.md">Ver registros de uso de RTC en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="5fec2-107">To see a listing of all PSTN usage records available in your Enterprise Voice deployment and view their properties, see <A href="lync-server-2013-view-pstn-usage-records.md">View PSTN usage records in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-create-a-voice-policy"></a><span data-ttu-id="5fec2-108">Para crear una directiva de voz</span><span class="sxs-lookup"><span data-stu-id="5fec2-108">To create a voice policy</span></span>

1.  <span data-ttu-id="5fec2-109">Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro de la función CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="5fec2-109">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="5fec2-110">Para obtener más información, consulte [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="5fec2-110">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="5fec2-111">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5fec2-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="5fec2-112">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="5fec2-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="5fec2-113">En la barra de navegación izquierda, haga clic en **Enrutamiento de voz** y luego en **Directiva de voz**.</span><span class="sxs-lookup"><span data-stu-id="5fec2-113">In the left navigation bar, click **Voice Routing** and then click **Voice Policy**.</span></span>

4.  <span data-ttu-id="5fec2-114">En la página **Directiva de voz**, haga clic en **Nueva** y seleccione el ámbito de la nueva directiva:</span><span class="sxs-lookup"><span data-stu-id="5fec2-114">On the **Voice Policy** page, click **New** and then select a scope for the new policy:</span></span>
    
      - <span data-ttu-id="5fec2-p105">La **directiva de sitio** se aplica a todo un sitio, excepto a los usuarios o grupos que estén asignados a una directiva de usuario. Si selecciona Sitio al definir el ámbito de la directiva, elija un sitio en el cuadro de diálogo **Seleccionar un sitio**. Si ya se creó una directiva de voz para un sitio, el sitio no aparecerá en el cuadro de diálogo **Seleccionar un sitio**.</span><span class="sxs-lookup"><span data-stu-id="5fec2-p105">**Site policy** applies to an entire site, except any users or groups that are assigned to a user policy. If you select Site for a policy scope, choose the site from the **Select a Site** dialog box. If a voice policy has already been created for a site, the site does not appear in the **Select a Site** dialog box.</span></span>
    
      - <span data-ttu-id="5fec2-118">La **directiva de usuario** se puede aplicar a usuarios o grupos concretos.</span><span class="sxs-lookup"><span data-stu-id="5fec2-118">**User policy** can be applied to specified users or groups.</span></span>

5.  <span data-ttu-id="5fec2-119">Si el ámbito de una directiva de voz es Usuario, escriba un nombre descriptivo para la directiva en el campo **Nombre**.</span><span class="sxs-lookup"><span data-stu-id="5fec2-119">If the voice policy scope is User, enter a descriptive name for the policy in the **Name** field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5fec2-120">Si el ámbito de la directiva de voz es Sitio, el campo <STRONG>Nombre</STRONG> de la <STRONG>Nueva directiva de voz</STRONG> se rellena automáticamente con el nombre del sitio y no se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="5fec2-120">If the voice policy scope is Site, the <STRONG>Name</STRONG> field in <STRONG>New Voice Policy</STRONG> is prepopulated with the site name and cannot be changed.</span></span>

    
    </div>

6.  <span data-ttu-id="5fec2-121">(Opcional) Añada información descriptiva sobre la directiva de voz.</span><span class="sxs-lookup"><span data-stu-id="5fec2-121">(Optional) Enter additional descriptive information for the voice policy.</span></span>

7.  <span data-ttu-id="5fec2-122">Active o desactive las siguientes casillas para habilitar o deshabilitar cada una de las **Características de llamada** de esta directiva de voz:</span><span class="sxs-lookup"><span data-stu-id="5fec2-122">Select or clear the following check boxes to enable or disable each of the **Calling features** for this voice policy:</span></span>
    
      - <span data-ttu-id="5fec2-123">**Voice mail escape** evita que las llamadas se redirijan inmediatamente al sistema de correo de voz del teléfono móvil del usuario cuando está configurada la opción de llamadas simultáneas y el teléfono está desactivado, se ha quedado sin batería o está fuera de alcance.</span><span class="sxs-lookup"><span data-stu-id="5fec2-123">**Voice mail escape** prevents calls from being immediately routed to the user’s mobile phone voice mail system when simultaneous ringing is configured and the phone is turned off, out of battery, or out of range.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="5fec2-124">Esta característica solo se puede configurar a través del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5fec2-124">This feature is only configurable through the Lync Server Management Shell</span></span>

        
        </div>
    
      - <span data-ttu-id="5fec2-125">El **desvío de llamadas** permite que los usuarios desvíen llamadas a otros teléfonos y dispositivos de cliente.</span><span class="sxs-lookup"><span data-stu-id="5fec2-125">**Call forwarding** enables users to forward calls to other phones and client devices.</span></span> <span data-ttu-id="5fec2-126">Lync Server 2013 proporciona una gama de opciones de configuración mucho más amplia para el desvío de llamadas.</span><span class="sxs-lookup"><span data-stu-id="5fec2-126">Lync Server 2013 provides a significantly wider range of configuration options for call forwarding.</span></span> <span data-ttu-id="5fec2-127">Por ejemplo, si una organización no desea que las llamadas entrantes se desvíen externamente a la Red telefónica conmutada (RTC), un administrador puede aplicar una directiva de voz especial para implementar esta restricción.</span><span class="sxs-lookup"><span data-stu-id="5fec2-127">For example, if an organization does not want to allow incoming calls to be forwarded externally to the PSTN, an administrator can apply a special voice policy to deploy this restriction.</span></span> <span data-ttu-id="5fec2-128">Habilitada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="5fec2-128">Enabled by default.</span></span>
    
      - <span data-ttu-id="5fec2-129">La **delegación** permite a los usuarios especificar otros usuarios para que realicen y reciban llamadas en su nombre.</span><span class="sxs-lookup"><span data-stu-id="5fec2-129">**Delegation** enables users to specify other users to send and receive calls on their behalf.</span></span> <span data-ttu-id="5fec2-130">En Lync Server 2013, un delegado puede configurar las llamadas simultáneas que permite que las llamadas entrantes a su administrador puedan llamar a todos los destinos de llamadas simultáneas del delegado.</span><span class="sxs-lookup"><span data-stu-id="5fec2-130">In Lync Server 2013, a delegate can configure simultaneous ringing that enables incoming calls to his or her manager to ring all of the delegate’s simultaneous ringing targets.</span></span> <span data-ttu-id="5fec2-131">Así pues, el delegado dispone de una mayor flexibilidad para responder a las llamadas dirigidas a su superior.</span><span class="sxs-lookup"><span data-stu-id="5fec2-131">This provides the delegate with greater flexibility in responding to calls directed to the manager.</span></span> <span data-ttu-id="5fec2-132">Habilitada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="5fec2-132">Enabled by default.</span></span>
    
      - <span data-ttu-id="5fec2-p108">La **transferencia de llamadas** permite a los usuarios transferir llamadas a otros usuarios. Opción habilitada habitualmente.</span><span class="sxs-lookup"><span data-stu-id="5fec2-p108">**Call transfer** enables users to transfer calls to other users. Enabled by default.</span></span>
    
      - <span data-ttu-id="5fec2-p109">El **estacionamiento de llamadas** permite a los usuarios poner llamadas en espera y después recibir la llamada de otro teléfono o cliente. Opción deshabilitada habitualmente.</span><span class="sxs-lookup"><span data-stu-id="5fec2-p109">**Call park** enables users to park calls on hold and then pick up the call from a different phone or client. Disabled by default.</span></span>
    
      - <span data-ttu-id="5fec2-137">**Llamadas simultáneas** permite que las llamadas entrantes suenen en otros teléfonos (por ejemplo, un teléfono móvil) o en otros dispositivos de extremo.</span><span class="sxs-lookup"><span data-stu-id="5fec2-137">**Simultaneous ringing** enables incoming calls to ring on additional phones (for example, a mobile phone) or other endpoint devices.</span></span> <span data-ttu-id="5fec2-138">Lync Server 2013 proporciona una gama de opciones de configuración mucho más amplia para las llamadas simultáneas.</span><span class="sxs-lookup"><span data-stu-id="5fec2-138">Lync Server 2013 provides a significantly wider range of configuration options for simultaneous ringing.</span></span> <span data-ttu-id="5fec2-139">Habilitada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="5fec2-139">Enabled by default.</span></span>
    
      - <span data-ttu-id="5fec2-p111">**Llamada de equipo** permite a los usuarios de un equipo definido responder a las llamadas en lugar de otros miembros del equipo. Habilitada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="5fec2-p111">**Team call** enables users on a defined team to answer calls for other members of the team. Enabled by default.</span></span>
    
      - <span data-ttu-id="5fec2-p112">**Volver a enrutar en RTC** permite que las llamadas realizadas por usuarios que tienen asignada esta directiva a otros usuarios de la empresa se puedan volver a redirigir en la red telefónica conmutada (RTC) si la red WAN está saturada o no disponible. Opción habilitada habitualmente.</span><span class="sxs-lookup"><span data-stu-id="5fec2-p112">**PSTN re-route** enables calls made by users who are assigned this policy to other enterprise users to be rerouted on the public switched telephone network (PSTN) if the WAN is congested or unavailable. Enabled by default.</span></span>
    
      - <span data-ttu-id="5fec2-p113">El **reemplazo de directiva de ancho de banda** permite a los administradores reemplazar las decisiones de la directiva de control de admisión de llamadas para un usuario concreto. Opción deshabilitada habitualmente.</span><span class="sxs-lookup"><span data-stu-id="5fec2-p113">**Bandwidth policy override** enables administrators to override call admission control policy decisions for a particular user. Disabled by default.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="5fec2-p114">La directiva se reemplazará solo para las llamadas entrantes que reciba el usuario, y no para las llamadas salientes que realice el usuario. Una vez establecida la sesión, se justificará detalladamente el consumo de ancho de banda. Esta configuración se debe usar con moderación, y recomendamos evitarla para tomar las decisiones correctas en el control de admisión de llamadas.</span><span class="sxs-lookup"><span data-stu-id="5fec2-p114">The policy will be overridden only for incoming calls to the user and not for outgoing calls that are placed by the user. After the session is established, the bandwidth consumption will be accurately recorded. This setting should be used sparingly and should be reserved for appropriate call admission control decisions.</span></span>

        
        </div>
    
      - <span data-ttu-id="5fec2-p115">**Seguimiento de llamadas malintencionadas** permite a los usuarios informar sobre llamadas malintencionadas (como amenazas de bomba) usando la interfaz de usuario del cliente, y hace que la llamada quede señalada en los registros de detalles de llamadas. Opción deshabilitada habitualmente.</span><span class="sxs-lookup"><span data-stu-id="5fec2-p115">**Malicious call tracing** enables users to report malicious calls (such as bomb threats) by using the client UI, which in turn flags the calls in the call detail records (CDRs). Disabled by default.</span></span>

8.  <span data-ttu-id="5fec2-151">Para asociar y configurar los registros de uso de RTC correspondientes a esta directiva de voz, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="5fec2-151">To associate and configure PSTN usage records for this voice policy, do any of the following:</span></span>
    
      - <span data-ttu-id="5fec2-p116">Para elegir uno o más registros en una lista de todos los registros de uso de RTC disponibles en la implementación de Telefonía IP empresarial, haga clic en **Seleccionar**. Resalte los registros que desee asociar a esta directiva de voz y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5fec2-p116">To choose one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**. Highlight the records that you want to associate with this voice policy, and then click **OK**.</span></span>
    
      - <span data-ttu-id="5fec2-154">Para quitar el registro de uso de RTC de esta directiva de voz, seleccione el registro y haga clic en **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="5fec2-154">To remove a PSTN usage record from this voice policy, highlight the record and click **Remove**.</span></span>
    
      - <span data-ttu-id="5fec2-155">Para definir un nuevo registro de uso de RTC y asociarlo con esta directiva de voz, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5fec2-155">To define a new PSTN usage record and associate it with this voice policy, do the following:</span></span>
        
        1.  <span data-ttu-id="5fec2-156">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="5fec2-156">Click **New**.</span></span>
        
        2.  <span data-ttu-id="5fec2-p117">En el campo **Nombre**, escriba un nombre descriptivo único para el registro. Por ejemplo, puede que desee crear un registro de uso de RTC llamado **Redmond** para los empleados de Redmond a tiempo completo, y otro llamado **RedmondTemps** para los empleados temporales.</span><span class="sxs-lookup"><span data-stu-id="5fec2-p117">In the **Name** field, enter a unique descriptive name for the record. For example, you may want to create a PSTN usage record named **Redmond** for full-time employees located in Redmond, and another named **RedmondTemps** for temporary employees.</span></span>
            
            <div>
            

            > [!NOTE]  
            > <span data-ttu-id="5fec2-p118">El nombre del registro de uso de RTC debe ser único dentro de la implementación de Telefonía IP empresarial. Una vez guardado el registro, no se puede editar el campo <STRONG>Nombre</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="5fec2-p118">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

            
            </div>
        
        3.  <span data-ttu-id="5fec2-161">Utilice alguno de los métodos siguientes para asociar y configurar rutas para este registro de uso de RTC:</span><span class="sxs-lookup"><span data-stu-id="5fec2-161">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="5fec2-162">Para elegir una o más rutas de la lista de todas las rutas disponibles en la implementación de la Telefonía IP empresarial, haga clic en **Seleccionar**, resalte las rutas que desee asociar con este registro de uso de RTC y después haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5fec2-162">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
            
              - <span data-ttu-id="5fec2-163">Para quitar una ruta del registro de uso de RTC, resalte la ruta y después haga clic en **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="5fec2-163">To remove a route from the PSTN usage record, highlight the route, and then click **Remove**.</span></span>
            
              - <span data-ttu-id="5fec2-164">Para definir una ruta nueva y asociarla con este registro de uso de RTC, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="5fec2-164">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="5fec2-165">Para obtener más información, consulte [crear una ruta de voz en Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="5fec2-165">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="5fec2-166">Para editar una ruta que ya esté asociada con este registro de uso de RTC, resalte la ruta y haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="5fec2-166">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="5fec2-167">Para obtener más información, consulte [modificar una ruta de voz en Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="5fec2-167">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        4.  <span data-ttu-id="5fec2-168">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5fec2-168">Click **OK**.</span></span>
    
      - <span data-ttu-id="5fec2-169">Para editar un registro de uso de RTC ya asociado a esta directiva de voz:</span><span class="sxs-lookup"><span data-stu-id="5fec2-169">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>
        
        1.  <span data-ttu-id="5fec2-170">Resalte el registro de uso de RTC que desea editar y haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="5fec2-170">Highlight the PSTN usage record that you want to edit, and then click **Show details**.</span></span>
        
        2.  <span data-ttu-id="5fec2-171">Use alguno de los métodos siguientes para asociar y configurar rutas para este registro de uso de RTC:</span><span class="sxs-lookup"><span data-stu-id="5fec2-171">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="5fec2-172">Para elegir una o más rutas de la lista de todas las rutas disponibles en la implementación de Telefonía IP empresarial, haga clic en **Seleccionar**, seleccione las rutas que desea asociar a este registro de uso de RTC y después haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5fec2-172">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes you want to associate with this PSTN usage record, and then click **OK**.</span></span>
            
              - <span data-ttu-id="5fec2-173">Para quitar una ruta de este registro de uso de RTC, resalte la ruta y después haga clic en **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="5fec2-173">To remove a route from this PSTN usage record, highlight the route, and then click **Remove**.</span></span>
            
              - <span data-ttu-id="5fec2-174">Para definir una ruta nueva y asociarla con este registro de uso de RTC, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="5fec2-174">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="5fec2-175">Para obtener más información, consulte [crear una ruta de voz en Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="5fec2-175">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="5fec2-176">Para editar una ruta que ya está asociado a este registro de uso de RTC, resalte la ruta y haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="5fec2-176">To edit a route that is already associated with this PSTN usage record, highlight the route and lick **Show details**.</span></span> <span data-ttu-id="5fec2-177">Para obtener más información, consulte [modificar una ruta de voz en Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="5fec2-177">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        3.  <span data-ttu-id="5fec2-178">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5fec2-178">Click **OK**.</span></span>

9.  <span data-ttu-id="5fec2-p123">Organice los registros de uso de RTC para lograr un rendimiento óptimo. Para cambiar la posición de un registro de la lista, resalte el nombre del registro y haga clic en la flecha arriba o abajo.</span><span class="sxs-lookup"><span data-stu-id="5fec2-p123">Arrange the PSTN usage records for optimum performance. To change a record’s position in the list, highlight the record name and click the up or down arrow.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="5fec2-181">Es importante el orden en el que aparecen en la lista de la directiva de voz los registros de uso de RTC.</span><span class="sxs-lookup"><span data-stu-id="5fec2-181">The order in which PSTN usage records are listed in the voice policy is significant.</span></span> <span data-ttu-id="5fec2-182">Lync Server recorre la lista desde arriba hacia abajo.</span><span class="sxs-lookup"><span data-stu-id="5fec2-182">Lync Server traverses the list from the top down.</span></span> <span data-ttu-id="5fec2-183">Se recomienda ordenar la lista por frecuencia de uso, por ejemplo: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span><span class="sxs-lookup"><span data-stu-id="5fec2-183">We recommend that you organize the list by frequency of use, for example: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span></span>

    
    </div>

10. <span data-ttu-id="5fec2-184">Para asociar y configurar los registros de uso de RTC correspondientes al desvío de llamadas y a las llamadas simultáneas de esta directiva de voz, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="5fec2-184">To associate and configure PSTN usage records for call forwarding and simultaneous ringing in this voice policy, do any of the following:</span></span>
    
      - <span data-ttu-id="5fec2-185">Para usar los mismos registros de uso de RTC que esta directiva de voz, para el desvío de llamadas y las llamadas simultáneas, seleccione la opción **Redirigir con los usos de PSTN** en el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="5fec2-185">To use the same PSTN usage records for call forwarding and simultaneous ringing as this voice policy, select the option **Route using the call PSTN usages** from the drop-down menu.</span></span>
    
      - <span data-ttu-id="5fec2-p125">Para permitir el desvío de llamadas y las llamadas simultáneas solo para los usuarios de Lync internos, seleccione la opción **Redirigir a usuarios de Lync internos únicamente** en el menú desplegable. Las llamadas no se desviarán a los números de RTC externos.</span><span class="sxs-lookup"><span data-stu-id="5fec2-p125">To allow call forwarding and simultaneous ringing to internal Lync users only, select the option **Route to internal Lync users only** from the drop-down menu. Calls will not be forwarded to external PSTN numbers.</span></span>
    
      - <span data-ttu-id="5fec2-p126">Para usar unos registros de uso de RTC para el desvío de llamadas y las llamadas simultáneas que no sean los que se usan para esta directiva de voz, seleccione la opción **Redirigir con usos de PSTN personalizados** en el menú desplegable. Esta opción muestra un control para seleccionar registros de uso de RTC o crear nuevos registros de uso de RTC destinados concretamente a desviar llamadas o a realizar llamadas simultáneas.</span><span class="sxs-lookup"><span data-stu-id="5fec2-p126">To specify different PSTN usage records for call forwarding and simultaneous ringing than used for this voice policy, select the option **Route using custom PSTN usages** from the drop-down menu. This option displays a control to select existing PSTN usage records or create new PSTN usage records specifically for call forwarding and simultaneous ringing.</span></span>
        
          - <span data-ttu-id="5fec2-p127">Para elegir uno o más registros de una lista de registros de uso de RTC para el desvío de llamadas y las llamadas simultáneas, haga clic en **Seleccionar**. Resalte los registros que desee asociar a esta directiva de desvío de llamadas y de llamadas simultáneas y después haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5fec2-p127">To choose one or more records from a list of PSTN usage records for call forwarding and simultaneous ringing, click **Select**. Highlight the records that you want to associate with this call forwarding and simultaneous ringing policy, and then click **OK**.</span></span>
        
          - <span data-ttu-id="5fec2-192">Para quitar un registro de uso de RTC de esta directiva de desvío de llamadas y llamadas simultáneas, resalte el registro y haga clic en **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="5fec2-192">To remove a PSTN usage record from this call forwarding and simultaneous ringing policy, highlight the record and click **Remove**.</span></span>
        
          - <span data-ttu-id="5fec2-193">Para definir un nuevo registro de uso de RTC y asociarlo a esta directiva de desvío de llamadas y llamadas simultáneas:</span><span class="sxs-lookup"><span data-stu-id="5fec2-193">To define a new PSTN usage record and associate it with this call forwarding and simultaneous ringing policy, do the following:</span></span>
            
            1.  <span data-ttu-id="5fec2-194">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="5fec2-194">Click **New**.</span></span>
            
            2.  <span data-ttu-id="5fec2-195">En el campo **Nombre**, escriba un nombre descriptivo único para el registro.</span><span class="sxs-lookup"><span data-stu-id="5fec2-195">In the **Name** field, enter a unique descriptive name for the record.</span></span>
                
                <div>
                

                > [!NOTE]  
                > <span data-ttu-id="5fec2-p128">El nombre del registro de uso de RTC debe ser único dentro de la implementación de Telefonía IP empresarial. Una vez guardado el registro, no se puede editar el campo <STRONG>Nombre</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="5fec2-p128">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

                
                </div>
            
            3.  <span data-ttu-id="5fec2-198">Utilice alguno de los métodos siguientes para asociar y configurar rutas para este registro de uso de RTC:</span><span class="sxs-lookup"><span data-stu-id="5fec2-198">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
                
                  - <span data-ttu-id="5fec2-199">Para elegir una o más rutas de la lista de todas las rutas disponibles en la implementación de Telefonía IP empresarial, haga clic en **Seleccionar**, resalte las rutas que desee asociar con este registro de uso de RTC y, después, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5fec2-199">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
                
                  - <span data-ttu-id="5fec2-200">Para quitar una ruta del registro de uso de RTC, resalte la ruta y haga clic en **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="5fec2-200">To remove a route from the PSTN usage record, highlight the route and click **Remove**.</span></span>
                
                  - <span data-ttu-id="5fec2-201">Para definir una ruta nueva y asociarla con este registro de uso de RTC, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="5fec2-201">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="5fec2-202">Para obtener más información, consulte [crear una ruta de voz en Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="5fec2-202">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
                
                  - <span data-ttu-id="5fec2-203">Para editar una ruta que ya esté asociada con este registro de uso de RTC, resalte la ruta y haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="5fec2-203">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="5fec2-204">Para obtener más información, consulte [modificar una ruta de voz en Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="5fec2-204">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
            
            4.  <span data-ttu-id="5fec2-205">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5fec2-205">Click **OK**.</span></span>
        
          - <span data-ttu-id="5fec2-206">Para editar un registro de uso de RTC que ya esté asociado a esta directiva de voz, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="5fec2-206">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>
            
            1.  <span data-ttu-id="5fec2-207">Resalte el registro de uso de RTC que desee editar y haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="5fec2-207">Highlight the PSTN usage record you want to edit and click **Show details**.</span></span>
            
            2.  <span data-ttu-id="5fec2-208">Use alguno de los métodos siguientes para asociar y configurar rutas para este registro de uso de RTC:</span><span class="sxs-lookup"><span data-stu-id="5fec2-208">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
                
                  - <span data-ttu-id="5fec2-209">Para elegir una o más rutas de la lista de todas las rutas disponibles en la implementación de Telefonía IP empresarial, haga clic en **Seleccionar**, resalte las rutas que desee asociar con este registro de uso de RTC y, después, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5fec2-209">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
                
                  - <span data-ttu-id="5fec2-210">Para quitar una ruta de este registro de uso de RTC, resalte la ruta y haga clic en **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="5fec2-210">To remove a route from this PSTN usage record, highlight the route and click **Remove**.</span></span>
                
                  - <span data-ttu-id="5fec2-211">Para definir una ruta nueva y asociarla con este registro de uso de RTC, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="5fec2-211">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="5fec2-212">Para obtener más información, consulte [crear una ruta de voz en Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="5fec2-212">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
                
                  - <span data-ttu-id="5fec2-213">Para editar una ruta que ya esté asociada con este registro de uso de RTC, resalte la ruta y haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="5fec2-213">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="5fec2-214">Para obtener más información, consulte [modificar una ruta de voz en Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="5fec2-214">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
            
            3.  <span data-ttu-id="5fec2-215">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5fec2-215">Click **OK**.</span></span>

11. <span data-ttu-id="5fec2-p133">(Opcional) Especifique un número para probar la directiva de voz y haga clic en **Ir**. Los resultados de la prueba se muestran en **Número convertido para probar**.</span><span class="sxs-lookup"><span data-stu-id="5fec2-p133">(Optional) Enter a number to test the voice policy and click **Go**. The test results are displayed under **Translated number to test**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5fec2-218">Puede guardar una directiva de voz que no haya pasado la prueba aún y volver a configurarla más adelante.</span><span class="sxs-lookup"><span data-stu-id="5fec2-218">You can save a voice policy that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="5fec2-219">Para obtener más información, consulte <A href="lync-server-2013-test-voice-routing.md">probar el enrutamiento de voz en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="5fec2-219">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

12. <span data-ttu-id="5fec2-220">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5fec2-220">Click **OK**.</span></span>

13. <span data-ttu-id="5fec2-221">En la página **Directiva de voz**, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**.</span><span class="sxs-lookup"><span data-stu-id="5fec2-221">On the **Voice Policy** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5fec2-222">Siempre que cree o modifique una directiva de voz, ejecute el comando <STRONG>Confirmar todo</STRONG> para publicar el cambio en la configuración.</span><span class="sxs-lookup"><span data-stu-id="5fec2-222">Any time you create or modify a voice policy, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="5fec2-223">Para obtener más información, consulte <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish Pending changes to the Voice Routing Configuration en Lync Server 2013</A> en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="5fec2-223">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

14. <span data-ttu-id="5fec2-224">(Opcional) El desvío de correo de voz desconecta las llamadas al correo de voz de un teléfono móvil cuando detecta que el correo de voz del teléfono del usuario responde automáticamente a la llamada.</span><span class="sxs-lookup"><span data-stu-id="5fec2-224">(Optional) Voicemail Escape detects that a call was immediately answered by the user’s mobile phone voice mail, and disconnects the call to the mobile phone voice mail.</span></span> <span data-ttu-id="5fec2-225">Con esto se permite que la llamada siga sonando en los otros extremos del usuario y que el usuario pueda responder a la llamada.</span><span class="sxs-lookup"><span data-stu-id="5fec2-225">This allows the call to continue to ring on the user’s other endpoints giving the user the opportunity to answer the call.</span></span> <span data-ttu-id="5fec2-226">Para obtener más información sobre cómo configurar una directiva de correo de voz, consulte [Configuring Voice Mail escape in Lync Server 2013](lync-server-2013-configuring-voice-mail-escape.md).</span><span class="sxs-lookup"><span data-stu-id="5fec2-226">For details on how to configure a voice mail policy, see [Configuring voice mail escape in Lync Server 2013](lync-server-2013-configuring-voice-mail-escape.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5fec2-227">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5fec2-227">See Also</span></span>


[<span data-ttu-id="5fec2-228">Modificar una directiva de voz y configurar los registros de uso de RTC en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5fec2-228">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="5fec2-229">Ver los registros de uso de RTC en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5fec2-229">View PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-view-pstn-usage-records.md)  
[<span data-ttu-id="5fec2-230">Crear una ruta de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5fec2-230">Create a voice route in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-route.md)  
[<span data-ttu-id="5fec2-231">Modificar una ruta de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5fec2-231">Modify a voice route in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-route.md)  
[<span data-ttu-id="5fec2-232">Publicar los cambios pendientes en la configuración del enrutamiento de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5fec2-232">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  
[<span data-ttu-id="5fec2-233">Configurar el escape de correo de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5fec2-233">Configuring voice mail escape in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-mail-escape.md)  


[<span data-ttu-id="5fec2-234">Probar el enrutamiento de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5fec2-234">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

