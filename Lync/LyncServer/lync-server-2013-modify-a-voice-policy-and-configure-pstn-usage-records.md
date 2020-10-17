---
title: 'Lync Server 2013: modificar una directiva de voz y configurar los registros de uso de RTC'
description: 'Lync Server 2013: modificar una directiva de voz y configurar los registros de uso de RTC.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify a voice policy and configure PSTN usage records
ms:assetid: 6c53aaf5-218b-4bd4-8cea-31bc9d53f1bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398511(v=OCS.15)
ms:contentKeyID: 48184419
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e26d6c8654ebf758f8b5a185c21468443e0451a9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559376"
---
# <a name="modify-a-voice-policy-and-configure-pstn-usage-records-in-lync-server-2013"></a><span data-ttu-id="0a44e-103">Modificar una directiva de voz y configurar los registros de uso de RTC en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0a44e-103">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0a44e-104">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="0a44e-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="0a44e-105">Siga los pasos siguientes si desea modificar una directiva de voz.</span><span class="sxs-lookup"><span data-stu-id="0a44e-105">Follow these steps if you want to modify a voice policy.</span></span> <span data-ttu-id="0a44e-106">Si desea crear una nueva Directiva de voz, consulte [crear una directiva de voz y configurar registros de uso de RTC en Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md) para el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="0a44e-106">If you want to create a new voice policy, see [Create a voice policy and configure PSTN usage records in Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md) for the procedure.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0a44e-107">Si se asigna a un usuario una directiva de voz sin registros de uso de la Red telefónica conmutada (RTC) asociados, el usuario no podrá realizar llamadas salientes.</span><span class="sxs-lookup"><span data-stu-id="0a44e-107">If a user is assigned to a voice policy has no associated public switched telephone network (PSTN) usage records, the user cannot place outbound calls.</span></span> <span data-ttu-id="0a44e-108">Para obtener una lista de todos los registros de uso de RTC disponibles en la implementación de telefonía IP empresarial y ver sus propiedades, consulte <A href="lync-server-2013-view-pstn-usage-records.md">Ver registros de uso de RTC en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="0a44e-108">For a listing of all PSTN usage records available in your Enterprise Voice deployment and view their properties, see <A href="lync-server-2013-view-pstn-usage-records.md">View PSTN usage records in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-modify-a-voice-policy"></a><span data-ttu-id="0a44e-109">Para modificar una directiva de voz</span><span class="sxs-lookup"><span data-stu-id="0a44e-109">To modify a voice policy</span></span>

1.  <span data-ttu-id="0a44e-110">Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro de la función CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="0a44e-110">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="0a44e-111">Para obtener más información, consulte [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="0a44e-111">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="0a44e-112">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0a44e-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="0a44e-113">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="0a44e-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="0a44e-114">En la barra de navegación izquierda, haga clic en **Enrutamiento de voz** y, después, en **Directiva de voz**.</span><span class="sxs-lookup"><span data-stu-id="0a44e-114">In the left navigation bar, click **Voice Routing**, and then click **Voice Policy**.</span></span>

4.  <span data-ttu-id="0a44e-115">En la página **Directiva de voz**, haga doble clic en el nombre de una directiva de voz.</span><span class="sxs-lookup"><span data-stu-id="0a44e-115">On the **Voice Policy** page, double-click a voice policy name.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0a44e-p105">El ámbito y el nombre se establecieron cuando se creó la directiva de voz. No pueden modificarse.</span><span class="sxs-lookup"><span data-stu-id="0a44e-p105">The scope and name were set when the voice policy was created. They cannot be changed.</span></span>

    
    </div>

5.  <span data-ttu-id="0a44e-118">(Opcional) En **Editar directiva de voz**, especifique otra información descriptiva sobre la directiva de voz.</span><span class="sxs-lookup"><span data-stu-id="0a44e-118">(Optional) In **Edit Voice Policy**, enter additional descriptive information for the voice policy.</span></span>

6.  <span data-ttu-id="0a44e-119">Active o desactive las casillas siguientes para habilitar o deshabilitar cada una de las **Características de llamadas**:</span><span class="sxs-lookup"><span data-stu-id="0a44e-119">Select or clear the following check boxes to enable or disable each of the **Calling features**:</span></span>
    
      - <span data-ttu-id="0a44e-120">**Desvío de correo de voz** impide que las llamadas se enruten inmediatamente al sistema de correo de voz del teléfono móvil del usuario cuando se ha configurado las llamadas simultáneas y el teléfono está apagado, no tiene batería o está fuera de cobertura.</span><span class="sxs-lookup"><span data-stu-id="0a44e-120">**Voice mail escape** prevents calls from being immediately routed to the user’s mobile phone voice mail system when simultaneous ringing is configured and the phone is turned off, out of battery, or out of range.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="0a44e-121">Esta característica solo se puede configurar a través del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0a44e-121">This feature is only configurable through the Lync Server Management Shell</span></span>

        
        </div>
    
      - <span data-ttu-id="0a44e-122">El **desvío de llamadas** permite que los usuarios desvíen llamadas a otros teléfonos y dispositivos de cliente.</span><span class="sxs-lookup"><span data-stu-id="0a44e-122">**Call forwarding** enables users to forward calls to other phones and client devices.</span></span> <span data-ttu-id="0a44e-123">Lync Server 2013 proporciona una gama de opciones de configuración mucho más amplia para el desvío de llamadas.</span><span class="sxs-lookup"><span data-stu-id="0a44e-123">Lync Server 2013 provides a significantly wider range of configuration options for call forwarding.</span></span> <span data-ttu-id="0a44e-124">Por ejemplo, si una organización no desea que las llamadas entrantes se desvíen externamente a la Red telefónica conmutada (RTC), un administrador puede aplicar una directiva de voz especial para implementar esta restricción.</span><span class="sxs-lookup"><span data-stu-id="0a44e-124">For example, if an organization does not want to allow incoming calls to be forwarded externally to the PSTN, an administrator can apply a special voice policy to deploy this restriction.</span></span> <span data-ttu-id="0a44e-125">Habilitada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="0a44e-125">Enabled by default.</span></span>
    
      - <span data-ttu-id="0a44e-126">La **delegación** permite a los usuarios especificar otros usuarios para que realicen y reciban llamadas en su nombre.</span><span class="sxs-lookup"><span data-stu-id="0a44e-126">**Delegation** enables users to specify other users to send and receive calls on their behalf.</span></span> <span data-ttu-id="0a44e-127">En Lync Server 2013, un delegado puede configurar las llamadas simultáneas que permite que las llamadas entrantes a su administrador puedan llamar a todos los destinos de llamadas simultáneas del delegado.</span><span class="sxs-lookup"><span data-stu-id="0a44e-127">In Lync Server 2013, a delegate can configure simultaneous ringing that enables incoming calls to his or her manager to ring all of the delegate’s simultaneous ringing targets.</span></span> <span data-ttu-id="0a44e-128">Así pues, el delegado dispone de una mayor flexibilidad para responder a las llamadas dirigidas a su superior.</span><span class="sxs-lookup"><span data-stu-id="0a44e-128">This provides the delegate with greater flexibility in responding to calls directed to the manager.</span></span> <span data-ttu-id="0a44e-129">Habilitada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="0a44e-129">Enabled by default.</span></span>
    
      - <span data-ttu-id="0a44e-p108">**Transferencia de llamadas** permite a los usuarios transferir llamadas a otros usuarios. Habilitada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="0a44e-p108">**Call transfer** enables users to transfer calls to other users. Enabled by default.</span></span>
    
      - <span data-ttu-id="0a44e-p109">**Estacionamiento de llamadas** permite que los usuarios pongan las llamadas en espera para que se puedan atender desde otro teléfono u otro cliente. Deshabilitada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="0a44e-p109">**Call park** enables users to park calls on hold, and then pick up the call from a different phone or client. Disabled by default.</span></span>
    
      - <span data-ttu-id="0a44e-134">**Llamadas simultáneas** permite que las llamadas entrantes suenen en otros teléfonos (por ejemplo, un teléfono móvil) o en otros dispositivos de extremo.</span><span class="sxs-lookup"><span data-stu-id="0a44e-134">**Simultaneous ringing** enables incoming calls to ring on additional phones (for example, a mobile phone) or other endpoint devices.</span></span> <span data-ttu-id="0a44e-135">Lync Server 2013 proporciona una gama de opciones de configuración mucho más amplia para las llamadas simultáneas.</span><span class="sxs-lookup"><span data-stu-id="0a44e-135">Lync Server 2013 provides a significantly wider range of configuration options for simultaneous ringing.</span></span> <span data-ttu-id="0a44e-136">Habilitada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="0a44e-136">Enabled by default.</span></span>
    
      - <span data-ttu-id="0a44e-p111">**Llamada de equipo** permite a los usuarios de un equipo definido responder a las llamadas en lugar de otros miembros del equipo. Habilitada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="0a44e-p111">**Team call** enables users on a defined team to answer calls for other members of the team. Enabled by default.</span></span>
    
      - <span data-ttu-id="0a44e-p112">**Volver a enrutar en RTC** permite que las llamadas realizadas por usuarios que tienen asignada esta directiva a otros usuarios de la empresa se puedan volver a enrutar en la Red telefónica conmutada (RTC) si la red WAN está saturada o no disponible. Habilitada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="0a44e-p112">**PSTN re-route** enables calls made by users who are assigned this policy to other enterprise users to be rerouted on the public switched telephone network (PSTN) if the WAN is congested or unavailable. Enabled by default.</span></span>
    
      - <span data-ttu-id="0a44e-p113">**Invalidar directiva de ancho de banda** permite a los administradores invalidar las decisiones de la directiva de control de admisión de llamadas para un usuario determinado. Deshabilitada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="0a44e-p113">**Bandwidth policy override** enables administrators to override call admission control (CAC) policy decisions for a particular user. Disabled by default.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="0a44e-p114">La directiva se invalidará solo para llamadas entrantes dirigidas a dicho usuario, pero no para las llamadas salientes que realice el usuario. Una vez establecida la sesión, el consumo de ancho de banda se registrará de forma detallada. Este parámetro debe usarse con moderación.</span><span class="sxs-lookup"><span data-stu-id="0a44e-p114">The policy will be overridden only for incoming calls to the user and not for outgoing calls that are placed by the user. After the session is established, the bandwidth consumption will be accurately recorded. This setting should be used sparingly.</span></span>

        
        </div>
    
      - <span data-ttu-id="0a44e-p115">**Seguimiento de llamadas malintencionadas** permite a los usuarios informar sobre llamadas malintencionadas (como amenazas de bomba) usando la interfaz de usuario del cliente, con lo cual la llamada queda señalada en los registros de detalles de llamadas. Deshabilitada de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="0a44e-p115">**Malicious call tracing** enables users to report malicious calls (such as bomb threats) using the client UI, which in turn flags the calls in the call detail records (CDRs). Disabled by default.</span></span>

7.  <span data-ttu-id="0a44e-148">Para asociar y configurar registros de uso de RTC para esta directiva de voz, siga uno de los procedimientos siguientes:</span><span class="sxs-lookup"><span data-stu-id="0a44e-148">To associate and configure PSTN usage records for this voice policy, do any of the following:</span></span>
    
      - <span data-ttu-id="0a44e-p116">Para elegir uno o más registros en una lista de todos los registros de uso de RTC disponibles en la implementación de Telefonía IP empresarial, haga clic en **Seleccionar**. Resalte los registros que desee asociar a esta directiva de voz y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0a44e-p116">To choose one or more records from a list of all PSTN usage records available in your Enterprise Voice deployment, click **Select**. Highlight the records that you want to associate with this voice policy, and then click **OK**.</span></span>
    
      - <span data-ttu-id="0a44e-151">Para quitar el registro de uso de RTC de esta directiva de voz, seleccione el registro y haga clic en **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="0a44e-151">To remove a PSTN usage record from this voice policy, highlight the record and click **Remove**.</span></span>
    
      - <span data-ttu-id="0a44e-152">Para definir un nuevo registro de uso de RTC y asociarlo con esta directiva de voz, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0a44e-152">To define a new PSTN usage record and associate it with this voice policy, do the following:</span></span>
        
        1.  <span data-ttu-id="0a44e-153">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="0a44e-153">Click **New**.</span></span>
        
        2.  <span data-ttu-id="0a44e-p117">En el campo **Nombre**, escriba un nombre descriptivo único para el registro. Por ejemplo, puede que desee crear un registro de uso de RTC llamado **Redmond** para los empleados de Redmond a tiempo completo, y otro registro llamado **RedmondTemps** para los empleados temporales.</span><span class="sxs-lookup"><span data-stu-id="0a44e-p117">In the **Name** field, enter a unique descriptive name for the record. For example, you may want to create a PSTN usage record named **Redmond** for full-time employees located in Redmond, and another record named **RedmondTemps** for temporary employees.</span></span>
            
            <div>
            

            > [!NOTE]  
            > <span data-ttu-id="0a44e-p118">El registro de uso de RTC debe ser único en la implementación de Enterprise Voice. Una vez guardado el registro, el campo <STRONG>Nombre</STRONG> no puede editarse.</span><span class="sxs-lookup"><span data-stu-id="0a44e-p118">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

            
            </div>
        
        3.  <span data-ttu-id="0a44e-158">Utilice alguno de los métodos siguientes para asociar y configurar rutas para este registro de uso de RTC:</span><span class="sxs-lookup"><span data-stu-id="0a44e-158">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="0a44e-159">Para elegir una o más rutas de la lista de todas las rutas disponibles en la implementación de Telefonía IP empresarial, haga clic en **Seleccionar**, resalte las rutas que desee asociar con este registro de uso de RTC y, después, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0a44e-159">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
            
              - <span data-ttu-id="0a44e-160">Para quitar una ruta del registro de uso de RTC, resalte la ruta y haga clic en **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="0a44e-160">To remove a route from the PSTN usage record, highlight the route and click **Remove**.</span></span>
            
              - <span data-ttu-id="0a44e-161">Para definir una ruta nueva y asociarla con este registro de uso de RTC, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="0a44e-161">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="0a44e-162">Para obtener más información, consulte [crear una ruta de voz en Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="0a44e-162">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="0a44e-163">Para editar una ruta que ya esté asociada con este registro de uso de RTC, resalte la ruta y haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="0a44e-163">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="0a44e-164">Para obtener más información, consulte [modificar una ruta de voz en Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="0a44e-164">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        4.  <span data-ttu-id="0a44e-165">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0a44e-165">Click **OK**.</span></span>
    
      - <span data-ttu-id="0a44e-166">Para editar un registro de uso de RTC ya asociado a esta directiva de voz:</span><span class="sxs-lookup"><span data-stu-id="0a44e-166">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>
        
        1.  <span data-ttu-id="0a44e-167">Resalte el registro de uso de RTC que desee editar y haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="0a44e-167">Highlight the PSTN usage record that you want to edit and click **Show details**.</span></span>
        
        2.  <span data-ttu-id="0a44e-168">Utilice alguno de los métodos siguientes para asociar y configurar rutas para este registro de uso de RTC:</span><span class="sxs-lookup"><span data-stu-id="0a44e-168">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
            
              - <span data-ttu-id="0a44e-169">Para elegir una o más rutas de la lista de todas las rutas disponibles en la implementación de Telefonía IP empresarial, haga clic en **Seleccionar**, resalte las rutas que desee asociar con este registro de uso de RTC y, después, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0a44e-169">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
            
              - <span data-ttu-id="0a44e-170">Para quitar una ruta de este registro de uso de RTC, resalte la ruta y haga clic en **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="0a44e-170">To remove a route from this PSTN usage record, highlight the route and click **Remove**.</span></span>
            
              - <span data-ttu-id="0a44e-171">Para definir una ruta nueva y asociarla con este registro de uso de RTC, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="0a44e-171">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="0a44e-172">Para obtener más información, consulte [crear una ruta de voz en Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="0a44e-172">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
            
              - <span data-ttu-id="0a44e-173">Para editar una ruta que ya esté asociada con este registro de uso de RTC, resalte la ruta y haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="0a44e-173">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="0a44e-174">Para obtener más información, consulte [modificar una ruta de voz en Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="0a44e-174">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
        
        3.  <span data-ttu-id="0a44e-175">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0a44e-175">Click **OK**.</span></span>

8.  <span data-ttu-id="0a44e-p123">Organice los registros de uso de RTC para lograr un rendimiento óptimo. Para cambiar la posición de un registro de la lista, resalte el nombre del registro y haga clic en la flecha arriba o abajo.</span><span class="sxs-lookup"><span data-stu-id="0a44e-p123">Arrange the PSTN usage records for optimum performance. To change a record’s position in the list, highlight the record name and click the up or down arrow.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0a44e-178">Es importante el orden en el que aparecen en la lista de la directiva de voz los registros de uso de RTC.</span><span class="sxs-lookup"><span data-stu-id="0a44e-178">The order in which PSTN usage records are listed in the voice policy is significant.</span></span> <span data-ttu-id="0a44e-179">Lync Server recorre la lista desde arriba hacia abajo.</span><span class="sxs-lookup"><span data-stu-id="0a44e-179">Lync Server traverses the list from the top down.</span></span> <span data-ttu-id="0a44e-180">Se recomienda ordenar la lista por frecuencia de uso, por ejemplo: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span><span class="sxs-lookup"><span data-stu-id="0a44e-180">We recommend that you organize the list by frequency of use, for example: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span></span>

    
    </div>

9.  <span data-ttu-id="0a44e-181">Para asociar y configurar los registros de uso de RTC correspondientes al desvío de llamadas y a las llamadas simultáneas de esta directiva de voz, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="0a44e-181">To associate and configure PSTN usage records for call forwarding and simultaneous ringing in this voice policy, do any of the following:</span></span>
    
      - <span data-ttu-id="0a44e-182">Para usar los mismos registros de uso de RTC en el desvío de llamadas y las llamadas simultáneas que esta directiva de voz, seleccione la opción **Enrutar con los usos de RTC de llamada** en el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="0a44e-182">To use the same PSTN usage records for call forwarding and simultaneous ringing as this voice policy, select the option **Route using the call PSTN usages** from the drop-down menu.</span></span>
    
      - <span data-ttu-id="0a44e-183">Para permitir el desvío de llamadas y las llamadas simultáneas solo a los usuarios internos de Lync, seleccione **enrutar solo a los usuarios internos de Lync** desde el menú desplegable.</span><span class="sxs-lookup"><span data-stu-id="0a44e-183">To allow call forwarding and simultaneous ringing to internal Lync users only, select **Route to internal Lync users only** from the drop-down menu.</span></span> <span data-ttu-id="0a44e-184">Las llamadas no se desviarán a números de RTC externos.</span><span class="sxs-lookup"><span data-stu-id="0a44e-184">Calls will not be forwarded to external PSTN numbers.</span></span>
    
      - <span data-ttu-id="0a44e-p126">Para especificar unos registros de uso de RTC para el desvío de llamadas y en las llamadas simultáneas distintos de los de esta directiva de voz, seleccione la opción **Enrutar con los usos de RTC personalizados** en el menú desplegable. Esta opción muestra un control para seleccionar unos registros de uso de RTC existentes o bien para crear otros registros de uso de RTC específicos para el desvío de llamadas y las llamadas simultáneas.</span><span class="sxs-lookup"><span data-stu-id="0a44e-p126">To specify different PSTN usage records for call forwarding and simultaneous ringing than those used for this voice policy, select the option **Route using custom PSTN usages** from the drop-down menu. This option displays a control to select existing PSTN usage records or to create new PSTN usage records, specifically for call forwarding and simultaneous ringing.</span></span>
        
          - <span data-ttu-id="0a44e-p127">Para elegir uno o más registros de una lista con los registros de uso de RTC para el desvío de llamadas y las llamadas simultáneas, haga clic en **Seleccionar**. Resalte los registros que desea asociar con esta directiva de desvío de voz y llamadas simultáneas y, después, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0a44e-p127">To choose one or more records from a list of PSTN usage records for call forwarding and simultaneous ringing, click **Select**. Highlight the records that you want to associate with this call forwarding and simultaneous ringing policy, and then click **OK**.</span></span>
        
          - <span data-ttu-id="0a44e-189">Para quitar un registro de uso de RTC de esta directiva de desvío de llamadas y llamadas simultáneas, resalte el registro y haga clic en **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="0a44e-189">To remove a PSTN usage record from this call forwarding and simultaneous ringing policy, highlight the record and click **Remove**.</span></span>
        
          - <span data-ttu-id="0a44e-190">Para definir un nuevo registro de uso de RTC y asociarlo a esta directiva de desvío de llamadas y llamadas simultáneas:</span><span class="sxs-lookup"><span data-stu-id="0a44e-190">To define a new PSTN usage record and associate it with this call forwarding and simultaneous ringing policy, do the following:</span></span>
            
            1.  <span data-ttu-id="0a44e-191">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="0a44e-191">Click **New**.</span></span>
            
            2.  <span data-ttu-id="0a44e-192">En el campo **Nombre**, escriba un nombre descriptivo único para el registro.</span><span class="sxs-lookup"><span data-stu-id="0a44e-192">In the **Name** field, enter a unique descriptive name for the record.</span></span>
                
                <div>
                

                > [!NOTE]  
                > <span data-ttu-id="0a44e-p128">El nombre del registro de uso de RTC debe ser único dentro de la implementación de Telefonía IP empresarial. Una vez guardado el registro, no se puede editar el campo <STRONG>Nombre</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="0a44e-p128">The PSTN usage record name must be unique within the Enterprise Voice deployment. After the record is saved, the <STRONG>Name</STRONG> field cannot be edited.</span></span>

                
                </div>
            
            3.  <span data-ttu-id="0a44e-195">Utilice alguno de los métodos siguientes para asociar y configurar rutas para este registro de uso de RTC:</span><span class="sxs-lookup"><span data-stu-id="0a44e-195">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
                
                  - <span data-ttu-id="0a44e-196">Para elegir una o más rutas de la lista de todas las rutas disponibles en la implementación de Telefonía IP empresarial, haga clic en **Seleccionar**, resalte las rutas que desee asociar con este registro de uso de RTC y, después, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0a44e-196">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes that you want to associate with this PSTN usage record, and then click **OK**.</span></span>
                
                  - <span data-ttu-id="0a44e-197">Para quitar una ruta del registro de uso de RTC, resalte la ruta y haga clic en **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="0a44e-197">To remove a route from the PSTN usage record, highlight the route and click **Remove**.</span></span>
                
                  - <span data-ttu-id="0a44e-198">Para definir una ruta nueva y asociarla con este registro de uso de RTC, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="0a44e-198">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="0a44e-199">Para obtener más información, consulte [crear una ruta de voz en Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="0a44e-199">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
                
                  - <span data-ttu-id="0a44e-200">Para editar una ruta que ya esté asociada con este registro de uso de RTC, resalte la ruta y haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="0a44e-200">To edit a route that is already associated with this PSTN usage record, highlight the route, and then click **Show details**.</span></span> <span data-ttu-id="0a44e-201">Para obtener más información, consulte [modificar una ruta de voz en Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="0a44e-201">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
            
            4.  <span data-ttu-id="0a44e-202">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0a44e-202">Click **OK**.</span></span>
        
          - <span data-ttu-id="0a44e-203">Para editar un registro de uso de RTC ya asociado a esta directiva de voz:</span><span class="sxs-lookup"><span data-stu-id="0a44e-203">To edit a PSTN usage record that is already associated with this voice policy, do the following:</span></span>
            
            1.  <span data-ttu-id="0a44e-204">Resalte el registro de uso de RTC que desee editar y haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="0a44e-204">Highlight the PSTN usage record that you want to edit and click **Show details**.</span></span>
            
            2.  <span data-ttu-id="0a44e-205">Utilice alguno de los métodos siguientes para asociar y configurar rutas para este registro de uso de RTC:</span><span class="sxs-lookup"><span data-stu-id="0a44e-205">Use any of the following methods to associate and configure routes for this PSTN usage record:</span></span>
                
                  - <span data-ttu-id="0a44e-206">Para elegir una o más rutas de la lista de todas las rutas disponibles en la implementación de Enterprise Voice, haga clic en **Seleccionar**, seleccione las rutas que desea asociar a este registro de uso de RTC y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0a44e-206">To choose one or more routes from the list of all available routes in your Enterprise Voice deployment, click **Select**, highlight the routes you want to associate with this PSTN usage record, and then click **OK**.</span></span>
                
                  - <span data-ttu-id="0a44e-207">Para quitar una ruta de este registro de uso de RTC, seleccione la ruta y haga clic en **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="0a44e-207">To remove a route from this PSTN usage record, highlight the route and click **Remove**.</span></span>
                
                  - <span data-ttu-id="0a44e-208">Para definir una ruta nueva y asociarla con este registro de uso de RTC, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="0a44e-208">To define a new route and associate it with this PSTN usage record, click **New**.</span></span> <span data-ttu-id="0a44e-209">Para obtener más información, consulte [crear una ruta de voz en Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="0a44e-209">For details, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>
                
                  - <span data-ttu-id="0a44e-210">Para editar una ruta que ya esté asociada con este registro de uso de RTC, resalte la ruta y haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="0a44e-210">To edit a route that is already associated with this PSTN usage record, highlight the route and click **Show details**.</span></span> <span data-ttu-id="0a44e-211">Para obtener más información, consulte [modificar una ruta de voz en Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="0a44e-211">For details, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md).</span></span>
            
            3.  <span data-ttu-id="0a44e-212">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0a44e-212">Click **OK**.</span></span>

10. <span data-ttu-id="0a44e-p133">(Opcional) Especifique un número para probar la directiva de voz y haga clic en **Ir**. Los resultados de la prueba se muestran en **Número convertido para probar**.</span><span class="sxs-lookup"><span data-stu-id="0a44e-p133">(Optional) Enter a number to test the voice policy and click **Go**. The test results are displayed under **Translated number to test**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0a44e-215">Puede guardar una directiva de voz que no haya pasado la prueba aún y volver a configurarla más adelante.</span><span class="sxs-lookup"><span data-stu-id="0a44e-215">You can save a voice policy that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="0a44e-216">Para obtener más información, consulte <A href="lync-server-2013-test-voice-routing.md">probar el enrutamiento de voz en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="0a44e-216">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

11. <span data-ttu-id="0a44e-217">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0a44e-217">Click **OK**.</span></span>

12. <span data-ttu-id="0a44e-218">En la página **Directiva de voz**, haga clic en **Confirmar** y, a continuación, en **Confirmar todo**.</span><span class="sxs-lookup"><span data-stu-id="0a44e-218">On the **Voice Policy** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0a44e-219">Siempre que cree o modifique una directiva de voz, debe ejecutar el comando <STRONG>Confirmar todo</STRONG> para publicar el cambio en la configuración.</span><span class="sxs-lookup"><span data-stu-id="0a44e-219">Whenever you create or modify a voice policy, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="0a44e-220">Para obtener más información, consulte <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish Pending changes to the Voice Routing Configuration en Lync Server 2013</A> en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="0a44e-220">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

13. <span data-ttu-id="0a44e-221">(Opcional) El desvío de correo de voz desconecta las llamadas al correo de voz de un teléfono móvil cuando detecta que el correo de voz del teléfono del usuario responde automáticamente a la llamada.</span><span class="sxs-lookup"><span data-stu-id="0a44e-221">(Optional) Voicemail Escape detects that a call was immediately answered by the user’s mobile phone voice mail, and disconnects the call to the mobile phone voice mail.</span></span> <span data-ttu-id="0a44e-222">Con esto se permite que la llamada siga sonando en los otros extremos del usuario y que el usuario pueda responder a la llamada.</span><span class="sxs-lookup"><span data-stu-id="0a44e-222">This allows the call to continue to ring on the user’s other endpoints giving the user the opportunity to answer the call.</span></span> <span data-ttu-id="0a44e-223">Para más información sobre cómo configurar una directiva de correo de voz, vea [Configuring Voice Mail escape in Lync Server 2013](lync-server-2013-configuring-voice-mail-escape.md).</span><span class="sxs-lookup"><span data-stu-id="0a44e-223">For details about how to configure a voice mail policy, see [Configuring voice mail escape in Lync Server 2013](lync-server-2013-configuring-voice-mail-escape.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0a44e-224">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0a44e-224">See Also</span></span>


[<span data-ttu-id="0a44e-225">Crear una directiva de voz y configurar los registros de uso de RTC en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0a44e-225">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="0a44e-226">Ver los registros de uso de RTC en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0a44e-226">View PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-view-pstn-usage-records.md)  
[<span data-ttu-id="0a44e-227">Crear una ruta de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0a44e-227">Create a voice route in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-route.md)  
[<span data-ttu-id="0a44e-228">Modificar una ruta de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0a44e-228">Modify a voice route in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-route.md)  
[<span data-ttu-id="0a44e-229">Publicar los cambios pendientes en la configuración del enrutamiento de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0a44e-229">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  
[<span data-ttu-id="0a44e-230">Configurar el escape de correo de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0a44e-230">Configuring voice mail escape in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-mail-escape.md)  


[<span data-ttu-id="0a44e-231">Probar el enrutamiento de voz en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0a44e-231">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

