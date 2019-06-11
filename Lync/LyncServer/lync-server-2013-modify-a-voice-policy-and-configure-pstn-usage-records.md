---
title: 'Lync Server 2013: modificar una directiva de voz y configurar los registros de uso de RTC'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Modify a voice policy and configure PSTN usage records
ms:assetid: 6c53aaf5-218b-4bd4-8cea-31bc9d53f1bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398511(v=OCS.15)
ms:contentKeyID: 48184419
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bb7c4cdc47c0624b3d94d0dc52c527310f803d83
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827189"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-a-voice-policy-and-configure-pstn-usage-records-in-lync-server-2013"></a><span data-ttu-id="41f02-102">Modificar una directiva de voz y configurar los registros de uso de RTC en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="41f02-102">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="41f02-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="41f02-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="41f02-104">Siga estos pasos si desea modificar una directiva de voz.</span><span class="sxs-lookup"><span data-stu-id="41f02-104">Follow these steps if you want to modify a voice policy.</span></span> <span data-ttu-id="41f02-105">Si desea crear una nueva Directiva de voz, vea [crear una directiva de voz y configurar los registros de uso de RTC en Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md) para el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="41f02-105">If you want to create a new voice policy, see [Create a voice policy and configure PSTN usage records in Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md) for the procedure.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="41f02-106">Si un usuario se asigna a una directiva de voz no tiene ningún registro de uso de red telefónica pública conmutada (RTC) asociado, el usuario no puede realizar llamadas salientes.</span><span class="sxs-lookup"><span data-stu-id="41f02-106">If a user is assigned to a voice policy has no associated public switched telephone network (PSTN) usage records, the user cannot place outbound calls.</span></span> <span data-ttu-id="41f02-107">Para obtener una lista de todos los registros de uso de RTC disponibles en su implementación de telefonía IP empresarial y ver sus propiedades, consulte <A href="lync-server-2013-view-pstn-usage-records.md">ver los registros de uso de RTC en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="41f02-107">For a listing of all PSTN usage records available in your Enterprise Voice deployment and view their properties, see <A href="lync-server-2013-view-pstn-usage-records.md">View PSTN usage records in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-modify-a-voice-policy"></a><span data-ttu-id="41f02-108">Para modificar una directiva de voz</span><span class="sxs-lookup"><span data-stu-id="41f02-108">To modify a voice policy</span></span>

1.  <span data-ttu-id="41f02-109">Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="41f02-109">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="41f02-110">Para obtener más información, consulte [permisos de configuración de delegación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="41f02-110">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="41f02-111">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="41f02-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="41f02-112">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="41f02-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="41f02-113">En la barra de navegación izquierda, haga clic en **Enrutamiento de voz** y, después, en **Directiva de voz**.</span><span class="sxs-lookup"><span data-stu-id="41f02-113">In the left navigation bar, click **Voice Routing**, and then click **Voice Policy**.</span></span>

4.  <span data-ttu-id="41f02-114">En la página **Directiva de voz**, haga doble clic en el nombre de una directiva de voz.</span><span class="sxs-lookup"><span data-stu-id="41f02-114">On the **Voice Policy** page, double-click a voice policy name.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="41f02-p105">El ámbito y el nombre se establecieron cuando se creó la directiva de voz. No pueden modificarse.</span><span class="sxs-lookup"><span data-stu-id="41f02-p105">The scope and name were set when the voice policy was created. They cannot be changed.</span></span>

    
    </div>

5.  <span data-ttu-id="41f02-117">(Opcional) En **Editar directiva de voz**, especifique otra información descriptiva sobre la directiva de voz.</span><span class="sxs-lookup"><span data-stu-id="41f02-117">(Optional) In **Edit Voice Policy**, enter additional descriptive information for the voice policy.</span></span>

6.  <span data-ttu-id="41f02-118">Active o desactive las casillas siguientes para habilitar o deshabilitar cada una de las **Características de llamadas**:</span><span class="sxs-lookup"><span data-stu-id="41f02-118">Select or clear the following check boxes to enable or disable each of the **Calling features**:</span></span>
    
      - <span data-ttu-id="41f02-119">**Voice mail escape** evita que las llamadas se redirijan inmediatamente al sistema de correo de voz del teléfono móvil del usuario cuando está configurada la opción de llamadas simultáneas y el teléfono está desactivado, se ha quedado sin batería o está fuera de alcance.</span><span class="sxs-lookup"><span data-stu-id="41f02-119">**Voice mail escape** prevents calls from being immediately routed to the user’s mobile phone voice mail system when simultaneous ringing is configured and the phone is turned off, out of battery, or out of range.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="41f02-120">Esta característica solo se puede configurar a través del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="41f02-120">This feature is only configurable through the Lync Server Management Shell</span></span>

        
        </div>
    
      - <span data-ttu-id="41f02-121">El **desvío de llamadas** permite que los usuarios desvíen llamadas a otros teléfonos y dispositivos de cliente.</span><span class="sxs-lookup"><span data-stu-id="41f02-121">**Call forwarding** enables users to forward calls to other phones and client devices.</span></span> <span data-ttu-id="41f02-122">Lync Server 2013 proporciona un intervalo significativamente más amplio de opciones de configuración para el desvío de llamadas.</span><span class="sxs-lookup"><span data-stu-id="41f02-122">Lync Server 2013 provides a significantly wider range of configuration options for call forwarding.</span></span> <span data-ttu-id="41f02-123">Por ejemplo, si una organización no desea que las llamadas entrantes se desvíen externamente a la RTC, un administrador puede aplicar una directiva de voz especial para implementar esta restricción.</span><span class="sxs-lookup"><span data-stu-id="41f02-123">For example, if an organization does not want to allow incoming calls to be forwarded externally to the PSTN, an administrator can apply a special voice policy to deploy this restriction.</span></span> <span data-ttu-id="41f02-124">Está habilitado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="41f02-124">Enabled by default.</span></span>
    
      - <span data-ttu-id="41f02-125">La **delegación** permite a los usuarios especificar otros usuarios para que realicen y reciban llamadas en su nombre.</span><span class="sxs-lookup"><span data-stu-id="41f02-125">**Delegation** enables users to specify other users to send and receive calls on their behalf.</span></span> <span data-ttu-id="41f02-126">En Lync Server 2013, un delegado puede configurar la llamada simultánea que permite que las llamadas entrantes a su jefe suenen a todos los destinos de timbre simultáneo del delegado.</span><span class="sxs-lookup"><span data-stu-id="41f02-126">In Lync Server 2013, a delegate can configure simultaneous ringing that enables incoming calls to his or her manager to ring all of the delegate’s simultaneous ringing targets.</span></span> <span data-ttu-id="41f02-127">De esta forma, el delegado dispone de mayor flexibilidad a la hora de responder a las llamadas dirigidas administrador.</span><span class="sxs-lookup"><span data-stu-id="41f02-127">This provides the delegate with greater flexibility in responding to calls directed to the manager.</span></span> <span data-ttu-id="41f02-128">Esta opción está habilitada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="41f02-128">Enabled by default.</span></span>
    
      - <span data-ttu-id="41f02-p108">La **transferencia de llamadas** permite a los usuarios transferir llamadas a otros usuarios. Está opción está habilitada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="41f02-p108">**Call transfer** enables users to transfer calls to other users. Enabled by default.</span></span>
    
      - <span data-ttu-id="41f02-p109">El **estacionamiento de llamadas** permite que los usuarios pongan las llamadas en espera para que se puedan atender desde otro teléfono u otro cliente. Esta opción está deshabilitada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="41f02-p109">**Call park** enables users to park calls on hold, and then pick up the call from a different phone or client. Disabled by default.</span></span>
    
      - <span data-ttu-id="41f02-133">La **función de llamadas simultáneas** permite que las llamadas entrantes suenen en más teléfonos (por ejemplo, un móvil) u otros dispositivos de extremo.</span><span class="sxs-lookup"><span data-stu-id="41f02-133">**Simultaneous ringing** enables incoming calls to ring on additional phones (for example, a mobile phone) or other endpoint devices.</span></span> <span data-ttu-id="41f02-134">Lync Server 2013 proporciona un intervalo significativamente más amplio de opciones de configuración para llamadas simultáneas.</span><span class="sxs-lookup"><span data-stu-id="41f02-134">Lync Server 2013 provides a significantly wider range of configuration options for simultaneous ringing.</span></span> <span data-ttu-id="41f02-135">Está habilitada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="41f02-135">Enabled by default.</span></span>
    
      - <span data-ttu-id="41f02-136">La **llamada de equipo** permite a los usuarios de un equipo determinado responder llamadas por otros miembros del equipo.</span><span class="sxs-lookup"><span data-stu-id="41f02-136">**Team call** enables users on a defined team to answer calls for other members of the team.</span></span> <span data-ttu-id="41f02-137">Está habilitada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="41f02-137">Enabled by default.</span></span>
    
      - <span data-ttu-id="41f02-138">La reenrutación de **RTC** permite que las llamadas realizadas por los usuarios que tienen asignada esta directiva a otros usuarios de la empresa se vuelvan a enrutar en la red de telefonía pública conmutada (RTC) si la WAN está congestionada o no disponible.</span><span class="sxs-lookup"><span data-stu-id="41f02-138">**PSTN re-route** enables calls made by users who are assigned this policy to other enterprise users to be rerouted on the public switched telephone network (PSTN) if the WAN is congested or unavailable.</span></span> <span data-ttu-id="41f02-139">Está habilitado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="41f02-139">Enabled by default.</span></span>
    
      - <span data-ttu-id="41f02-140">La anulación de la **Directiva de ancho de banda** permite a los administradores anular las decisiones de directiva de control de admisión de llamadas (CAC) para un usuario en particular.</span><span class="sxs-lookup"><span data-stu-id="41f02-140">**Bandwidth policy override** enables administrators to override call admission control (CAC) policy decisions for a particular user.</span></span> <span data-ttu-id="41f02-141">Está deshabilitado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="41f02-141">Disabled by default.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="41f02-p114">La directiva se invalidará solo para llamadas entrantes dirigidas a dicho usuario, pero no para las llamadas salientes que realice el usuario. Una vez establecida la sesión, el consumo de ancho de banda se registrará de forma detallada. Este parámetro debe usarse con moderación.</span><span class="sxs-lookup"><span data-stu-id="41f02-p114">The policy will be overridden only for incoming calls to the user and not for outgoing calls that are placed by the user. After the session is established, the bandwidth consumption will be accurately recorded. This setting should be used sparingly.</span></span>

        
        </div>
    
      - <span data-ttu-id="41f02-145">El **seguimiento de llamadas** malintencionadas permite a los usuarios denunciar llamadas malintencionadas (como amenazas de bomba) mediante la interfaz de usuario del cliente, que a su vez marca las llamadas en los registros de detalles de llamadas (CDRs).</span><span class="sxs-lookup"><span data-stu-id="41f02-145">**Malicious call tracing** enables users to report malicious calls (such as bomb threats) using the client UI, which in turn flags the calls in the call detail records (CDRs).</span></span> <span data-ttu-id="41f02-146">Está deshabilitada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="41f02-146">Disabled by default.</span></span>

7.  <span data-ttu-id="41f02-147">Para asociar y configurar los registros de uso de RTC correspondientes a esta directiva de voz, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="41f02-147">To associate and configure PSTN usage records for this voice policy, do any of the following:</span></span>
    
      - <span data-ttu-id="41f02-p116">Para elegir uno o varios registros de una lista que contiene todos los registros de uso de RTC disponibles en la implementación de la Telefonía IP empresarial, haga clic en **Seleccionar**. Resalte los registros que desee asociar a esta directiva de voz y después haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="41f02-p116">To choose one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**. Highlight the records that you want to associate with this voice policy, and then click **OK**.</span></span>
    
      - <span data-ttu-id="41f02-150">Para quitar un registro de uso de RTC de esta directiva de voz, resalte el registro y haga clic en **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="41f02-150">To remove a PSTN usage record from this voice policy, highlight the record and click **Remove**.</span></span>
    
      - <span data-ttu-id="41f02-151">Para definir un nuevo registro de uso de RTC y asociarlo a esta directiva de voz:</span><span class="sxs-lookup"><span data-stu-id="41f02-151">To define a new PSTN usage record and associate it with this voice policy, do the following:</span></span>
        
        1.  <span data-ttu-id="41f02-152">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="41f02-152">Click **New**.</span></span>
        
        2.  <span data-ttu-id="41f02-p117">En el campo **Nombre**, escriba un nombre descriptivo único para el registro. Por ejemplo, puede que desee crear un registro de uso de RTC llamado **Redmond** para los empleados de Redmond a tiempo completo, y otro registro llamado **RedmondTemps** para los empleados temporales.</span><span class="sxs-lookup"><span data-stu-id="41f02-p117">In the **Name** field, enter a unique descriptive name for the record. For example, you may want to create a PSTN usage record named **Redmond** for full-time employees located in Redmond, and another record named **RedmondTemps** for temporary employees.</span></span>
            
            <div>
            

            > [!NOTE]  
            > <span data-ttu-id="41f02-p118">El nombre del registro de uso de RTC debe ser único dentro de la implementación de la Telefonía IP empresarial. Una vez guardado el registro, no se puede editar el campo <STRONG>Nombre</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="41f02-p118">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

            
            </div>
        
        3.  <span data-ttu-id="41f02-157">Use alguno de los métodos siguientes para asociar y configurar rutas para este registro de uso de RTC:</span><span class="sxs-lookup"><span data-stu-id="41f02-157">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="41f02-158">Para elegir una o más rutas de la lista de todas las rutas disponibles en la implementación de Telefonía IP empresarial, haga clic en **Seleccionar**, seleccione las rutas que desea asociar a este registro de uso de RTC y después haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="41f02-158">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
            
              - <span data-ttu-id="41f02-159">Para quitar una ruta del registro de uso de RTC, resalte la ruta y haga clic en **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="41f02-159">To remove a route from the PSTN usage record, highlight the route and click **Remove**.</span></span>
            
              - <span data-ttu-id="41f02-160">Para definir una nueva ruta y asociarla a este registro de uso de RTC, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="41f02-160">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="41f02-161">Para obtener más información, vea [crear una ruta de voz en Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="41f02-161">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="41f02-162">Para editar una ruta que ya esté asociada con este registro de uso de RTC, resalte la ruta y haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="41f02-162">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="41f02-163">Para obtener más información, vea [modificar una ruta de voz en Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="41f02-163">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        4.  <span data-ttu-id="41f02-164">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="41f02-164">Click **OK**.</span></span>
    
      - <span data-ttu-id="41f02-165">Para editar un registro de uso de RTC que ya esté asociado a esta directiva de voz, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="41f02-165">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>
        
        1.  <span data-ttu-id="41f02-166">Resalte el registro de uso de RTC que desee editar y haga clic en   **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="41f02-166">Highlight the PSTN usage record that you want to edit and click **Show details**.</span></span>
        
        2.  <span data-ttu-id="41f02-167">Use alguno de los métodos siguientes para asociar y configurar rutas para este registro de uso de RTC:</span><span class="sxs-lookup"><span data-stu-id="41f02-167">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="41f02-168">Para elegir una o más rutas de la lista de todas las rutas disponibles en la implementación de Telefonía IP empresarial, haga clic en **Seleccionar**, seleccione las rutas que desea asociar a este registro de uso de RTC y después haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="41f02-168">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
            
              - <span data-ttu-id="41f02-169">Para quitar una ruta de este registro de uso de RTC, resalte la ruta y haga clic en **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="41f02-169">To remove a route from this PSTN usage record, highlight the route and click **Remove**.</span></span>
            
              - <span data-ttu-id="41f02-170">Para definir una nueva ruta y asociarla a este registro de uso de RTC, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="41f02-170">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="41f02-171">Para obtener más información, vea [crear una ruta de voz en Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="41f02-171">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="41f02-172">Para editar una ruta que ya esté asociada con este registro de uso de RTC, resalte la ruta y haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="41f02-172">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="41f02-173">Para obtener más información, vea [modificar una ruta de voz en Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="41f02-173">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        3.  <span data-ttu-id="41f02-174">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="41f02-174">Click **OK**.</span></span>

8.  <span data-ttu-id="41f02-p123">Organice los registros de uso de RTC para lograr un rendimiento óptimo. Para cambiar la posición de registro en la lista, resalte el nombre del registro y haga clic en la flecha arriba o abajo.</span><span class="sxs-lookup"><span data-stu-id="41f02-p123">Arrange the PSTN usage records for optimum performance. To change a record’s position in the list, highlight the record name and click the up or down arrow.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="41f02-177">Es importante el orden en el que aparecen en la lista de la directiva de voz los registros de uso de RTC.</span><span class="sxs-lookup"><span data-stu-id="41f02-177">The order in which PSTN usage records are listed in the voice policy is significant.</span></span> <span data-ttu-id="41f02-178">Lync Server recorre la lista desde arriba hacia abajo.</span><span class="sxs-lookup"><span data-stu-id="41f02-178">Lync Server traverses the list from the top down.</span></span> <span data-ttu-id="41f02-179">Recomendamos ordenar la lista por frecuencia de uso, por ejemplo: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span><span class="sxs-lookup"><span data-stu-id="41f02-179">We recommend that you organize the list by frequency of use, for example: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span></span>

    
    </div>

9.  <span data-ttu-id="41f02-180">Para asociar y configurar registros de uso de RTC para el desvío de llamadas y las llamadas simultáneas en esta directiva de voz, haga una de las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="41f02-180">To associate and configure PSTN usage records for call forwarding and simultaneous ringing in this voice policy, do any of the following:</span></span>
    
      - <span data-ttu-id="41f02-181">Para usar los mismos registros de uso de RTC que esta directiva de voz, para el desvío de llamadas y las llamadas simultáneas, seleccione la opción **Distribuir con los usos de la RTC de llamada** en el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="41f02-181">To use the same PSTN usage records for call forwarding and simultaneous ringing as this voice policy, select the option **Route using the call PSTN usages** from the drop-down menu.</span></span>
    
      - <span data-ttu-id="41f02-182">Para permitir el desvío de llamadas y las llamadas simultáneas solo a los usuarios internos de Lync, seleccione enrutar **solo para usuarios internos de Lync** en el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="41f02-182">To allow call forwarding and simultaneous ringing to internal Lync users only, select **Route to internal Lync users only** from the drop-down menu.</span></span> <span data-ttu-id="41f02-183">Calls will not be forwarded to external PSTN numbers.</span><span class="sxs-lookup"><span data-stu-id="41f02-183">Calls will not be forwarded to external PSTN numbers.</span></span>
    
      - <span data-ttu-id="41f02-p126">Para especificar unos registros de uso de RTC para el desvío de llamadas y en las llamadas simultáneas distintos de los de esta directiva de voz, seleccione la opción **Distribuir con los usos de la RTC personalizados** en el menú desplegable. Esta opción muestra un control para seleccionar unos registros de uso de RTC existentes o bien para crear otros registros de uso de RTC específicos para el desvío de llamadas y las llamadas simultáneas.</span><span class="sxs-lookup"><span data-stu-id="41f02-p126">To specify different PSTN usage records for call forwarding and simultaneous ringing than those used for this voice policy, select the option **Route using custom PSTN usages** from the drop-down menu. This option displays a control to select existing PSTN usage records or to create new PSTN usage records, specifically for call forwarding and simultaneous ringing.</span></span>
        
          - <span data-ttu-id="41f02-p127">Para elegir uno o más registros de una lista de registros de uso de RTC para el desvío de llamadas y las llamadas simultáneas, haga clic en **Seleccionar**. Resalte los registros que desee asociar a esta directiva de desvío de llamadas y de llamadas simultáneas y después haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="41f02-p127">To choose one or more records from a list of PSTN usage records for call forwarding and simultaneous ringing, click **Select**. Highlight the records that you want to associate with this call forwarding and simultaneous ringing policy, and then click **OK**.</span></span>
        
          - <span data-ttu-id="41f02-188">Para quitar un registro de uso de RTC de esta directiva de desvío de llamadas y de llamadas simultáneas, resalte el registro y haga clic en **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="41f02-188">To remove a PSTN usage record from this call forwarding and simultaneous ringing policy, highlight the record and click **Remove**.</span></span>
        
          - <span data-ttu-id="41f02-189">Para definir un registro de uso de RTC nuevo y asociarlo a esta directiva de desvío de llamadas y de llamadas simultáneas, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="41f02-189">To define a new PSTN usage record and associate it with this call forwarding and simultaneous ringing policy, do the following:</span></span>
            
            1.  <span data-ttu-id="41f02-190">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="41f02-190">Click **New**.</span></span>
            
            2.  <span data-ttu-id="41f02-191">En el campo **Nombre**, escriba un nombre descriptivo único para el registro.</span><span class="sxs-lookup"><span data-stu-id="41f02-191">In the **Name** field, enter a unique descriptive name for the record.</span></span>
                
                <div>
                

                > [!NOTE]  
                > <span data-ttu-id="41f02-p128">El nombre del registro de uso de RTC debe ser único dentro de la implementación de la Telefonía IP empresarial. Una vez guardado el registro, no se puede editar el campo <STRONG>Nombre</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="41f02-p128">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

                
                </div>
            
            3.  <span data-ttu-id="41f02-194">Use alguno de los métodos siguientes para asociar y configurar rutas para este registro de uso de RTC:</span><span class="sxs-lookup"><span data-stu-id="41f02-194">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
                
                  - <span data-ttu-id="41f02-195">Para elegir una o más rutas de la lista de todas las rutas disponibles en la implementación de Telefonía IP empresarial, haga clic en **Seleccionar**, seleccione las rutas que desea asociar a este registro de uso de RTC y después haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="41f02-195">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
                
                  - <span data-ttu-id="41f02-196">Para quitar una ruta del registro de uso de RTC, resalte la ruta y haga clic en **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="41f02-196">To remove a route from the PSTN usage record, highlight the route and click **Remove**.</span></span>
                
                  - <span data-ttu-id="41f02-197">Para definir una nueva ruta y asociarla a este registro de uso de RTC, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="41f02-197">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="41f02-198">Para obtener más información, vea [crear una ruta de voz en Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="41f02-198">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
                
                  - <span data-ttu-id="41f02-199">Para editar una ruta que ya esté asociada con este registro de uso de RTC, resalte la ruta y haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="41f02-199">To edit a route that is already associated with this PSTN usage record, highlight the route, and then click **Show details**.</span></span> <span data-ttu-id="41f02-200">Para obtener más información, vea [modificar una ruta de voz en Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="41f02-200">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
            
            4.  <span data-ttu-id="41f02-201">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="41f02-201">Click **OK**.</span></span>
        
          - <span data-ttu-id="41f02-202">Para editar un registro de uso de RTC que ya esté asociado a esta directiva de voz, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="41f02-202">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>
            
            1.  <span data-ttu-id="41f02-203">Resalte el registro de uso de RTC que desee editar y haga clic en   **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="41f02-203">Highlight the PSTN usage record that you want to edit and click **Show details**.</span></span>
            
            2.  <span data-ttu-id="41f02-204">Use alguno de los métodos siguientes para asociar y configurar rutas para este registro de uso de RTC:</span><span class="sxs-lookup"><span data-stu-id="41f02-204">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
                
                  - <span data-ttu-id="41f02-205">Para elegir una o más rutas de la lista de todas las rutas disponibles en la implementación de Telefonía IP empresarial, haga clic en **Seleccionar**, seleccione las rutas que desea asociar a este registro de uso de RTC y después haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="41f02-205">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes you want to associate with this PSTN usage record, and then click **OK**.</span></span>
                
                  - <span data-ttu-id="41f02-206">Para quitar una ruta de este registro de uso de RTC, resalte la ruta y haga clic en **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="41f02-206">To remove a route from this PSTN usage record, highlight the route and click **Remove**.</span></span>
                
                  - <span data-ttu-id="41f02-207">Para definir una nueva ruta y asociarla a este registro de uso de RTC, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="41f02-207">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="41f02-208">Para obtener más información, vea [crear una ruta de voz en Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="41f02-208">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
                
                  - <span data-ttu-id="41f02-209">Para editar una ruta que ya esté asociada con este registro de uso de RTC, resalte la ruta y haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="41f02-209">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="41f02-210">Para obtener más información, vea [modificar una ruta de voz en Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="41f02-210">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
            
            3.  <span data-ttu-id="41f02-211">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="41f02-211">Click **OK**.</span></span>

10. <span data-ttu-id="41f02-p133">(Opcional) Especifique un número para probar la directiva de voz y haga clic en **Ir**. Los resultados de la prueba se muestran en **Número convertido para probar**.</span><span class="sxs-lookup"><span data-stu-id="41f02-p133">(Optional) Enter a number to test the voice policy and click **Go**. The test results are displayed under **Translated number to test**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="41f02-214">Puede guardar una directiva de voz que aún no pase la prueba y, a continuación, volver a configurarla más tarde.</span><span class="sxs-lookup"><span data-stu-id="41f02-214">You can save a voice policy that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="41f02-215">Para obtener más información, consulte <A href="lync-server-2013-test-voice-routing.md">probar el enrutamiento de voz en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="41f02-215">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

11. <span data-ttu-id="41f02-216">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="41f02-216">Click **OK**.</span></span>

12. <span data-ttu-id="41f02-217">En la página **Directiva de voz**, haga clic en **Confirmar** y después en **Confirmar todo**.</span><span class="sxs-lookup"><span data-stu-id="41f02-217">On the **Voice Policy** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="41f02-218">Al crear o modifica runa directiva de voz, debe ejecutar el comando <STRONG>Confirmar todo</STRONG> para publicar el cambio de configuración.</span><span class="sxs-lookup"><span data-stu-id="41f02-218">Whenever you create or modify a voice policy, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="41f02-219">Para obtener más información, vea <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">publicar cambios pendientes en la configuración de enrutamiento de voz en Lync Server 2013</A> en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="41f02-219">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

13. <span data-ttu-id="41f02-220">(Opcional) Voicemail Escape detecta que se ha respondido de forma inmediata a una llamada desde el correo de voz del teléfono móvil del usuario.</span><span class="sxs-lookup"><span data-stu-id="41f02-220">(Optional) Voicemail Escape detects that a call was immediately answered by the user’s mobile phone voice mail, and disconnects the call to the mobile phone voice mail.</span></span> <span data-ttu-id="41f02-221">Con esto se permite que la llamada siga sonando en los otros extremos del usuario y que el usuario pueda responder a la llamada.</span><span class="sxs-lookup"><span data-stu-id="41f02-221">This allows the call to continue to ring on the user’s other endpoints giving the user the opportunity to answer the call.</span></span> <span data-ttu-id="41f02-222">Para obtener más información sobre cómo configurar una directiva de correo de voz, vea [configurar la configuración de escape de correo de voz en Lync Server 2013](lync-server-2013-configuring-voice-mail-escape.md).</span><span class="sxs-lookup"><span data-stu-id="41f02-222">For details about how to configure a voice mail policy, see [Configuring voice mail escape in Lync Server 2013](lync-server-2013-configuring-voice-mail-escape.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="41f02-223">Vea también</span><span class="sxs-lookup"><span data-stu-id="41f02-223">See Also</span></span>


[<span data-ttu-id="41f02-224">Crear una directiva de voz y configurar los registros de uso de RTC en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="41f02-224">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="41f02-225">Ver los registros de uso de RTC en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="41f02-225">View PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-view-pstn-usage-records.md)  
[<span data-ttu-id="41f02-226">Crear una ruta de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="41f02-226">Create a voice route in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-route.md)  
[<span data-ttu-id="41f02-227">Modificar una ruta de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="41f02-227">Modify a voice route in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-route.md)  
[<span data-ttu-id="41f02-228">Publicar los cambios pendientes en la configuración del enrutamiento de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="41f02-228">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  
[<span data-ttu-id="41f02-229">Configurar el escape del correo de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="41f02-229">Configuring voice mail escape in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-mail-escape.md)  


[<span data-ttu-id="41f02-230">Probar el enrutamiento de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="41f02-230">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

