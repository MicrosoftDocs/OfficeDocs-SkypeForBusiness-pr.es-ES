---
title: 'Lync Server 2013: Mover usuarios a telefonía IP empresarial'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Moving users to Enterprise Voice
ms:assetid: a2df6d51-5cf2-4d3e-8f97-496af5fd5e5e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412758(v=OCS.15)
ms:contentKeyID: 48184958
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1127bd0c767da7f02df8aefb30fda41a64bd353a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826741"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="moving-users-to-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="c5370-102">Mover usuarios a telefonía IP empresarial en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5370-102">Moving users to Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c5370-103">_**Última modificación del tema:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="c5370-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="c5370-104">Si va a mover usuarios de una infraestructura de telefonía PBX existente a Enterprise Voice, el proceso de implementación incluye algunos pasos que no forman parte del proceso de planeación ya descrito en [planificación de telefonía IP empresarial en Lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md).</span><span class="sxs-lookup"><span data-stu-id="c5370-104">If you are moving users from an existing PBX telephony infrastructure to Enterprise Voice, the deployment process includes some steps that are not part of the planning process already described in [Planning for Enterprise Voice in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md).</span></span> <span data-ttu-id="c5370-105">Para obtener información sobre cómo migrar usuarios de una implementación de voz de empresa anterior, consulte los documentos de migración que se incluyeron con los medios de instalación.</span><span class="sxs-lookup"><span data-stu-id="c5370-105">For information about migrating users from an earlier Enterprise Voice deployment, see the migration documents that were included with your installation media.</span></span>

<span data-ttu-id="c5370-106">El proceso de mover usuarios de una infraestructura de telefonía existente a Enterprise Voice consta de los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="c5370-106">The process of moving users from an existing telephony infrastructure to Enterprise Voice consists of the following steps:</span></span>

1.  <span data-ttu-id="c5370-107">Designar números de teléfono principales.</span><span class="sxs-lookup"><span data-stu-id="c5370-107">Designate primary phone numbers.</span></span>

2.  <span data-ttu-id="c5370-108">Habilitar a los usuarios para Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="c5370-108">Enable users for Enterprise Voice.</span></span>

3.  <span data-ttu-id="c5370-109">Preparar planes de marcado para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="c5370-109">Prepare dial plans for users.</span></span>

4.  <span data-ttu-id="c5370-110">Planear las directivas de voz de usuario.</span><span class="sxs-lookup"><span data-stu-id="c5370-110">Plan user voice policies.</span></span>

5.  <span data-ttu-id="c5370-111">Planificar rutas de llamadas.</span><span class="sxs-lookup"><span data-stu-id="c5370-111">Plan call routes.</span></span>

6.  <span data-ttu-id="c5370-112">Configure el tronco de PBX o SIP para redirigir las llamadas para los usuarios habilitados para telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="c5370-112">Configure PBX or SIP Trunk to reroute calls for users enabled for Enterprise Voice.</span></span>

7.  <span data-ttu-id="c5370-113">Mover usuarios a mensajería unificada (UM) de Exchange (recomendado).</span><span class="sxs-lookup"><span data-stu-id="c5370-113">Move users to Exchange Unified Messaging (UM) (recommended).</span></span>

<span data-ttu-id="c5370-114">En este tema se describe la planificación necesaria para cada uno de estos pasos.</span><span class="sxs-lookup"><span data-stu-id="c5370-114">This topic describes the planning that is necessary for each of these steps.</span></span>

<div>

## <a name="step-1-designate-primary-phone-numbers"></a><span data-ttu-id="c5370-115">Paso 1.</span><span class="sxs-lookup"><span data-stu-id="c5370-115">Step 1.</span></span> <span data-ttu-id="c5370-116">Designar números de teléfono principales</span><span class="sxs-lookup"><span data-stu-id="c5370-116">Designate primary phone numbers</span></span>

<span data-ttu-id="c5370-117">Enterprise Voice integra voz con otros medios de mensajería, como cuando una llamada llega al servidor, el servidor asigna el número al URI SIP del usuario y, después, bifurca la llamada a todos los puntos de conexión de cliente asociados con ese SIP-URI.</span><span class="sxs-lookup"><span data-stu-id="c5370-117">Enterprise Voice integrates voice with other messaging media, such that when an incoming call arrives at the server, the server maps the number to the user’s SIP-URI and then forks the call to all the client endpoints associated with that SIP-URI.</span></span> <span data-ttu-id="c5370-118">Este proceso requiere que cada usuario esté asociado a un número de teléfono principal.</span><span class="sxs-lookup"><span data-stu-id="c5370-118">This process requires that each user be associated with a primary phone number.</span></span>

<span data-ttu-id="c5370-119">Un número de teléfono principal debe ser:</span><span class="sxs-lookup"><span data-stu-id="c5370-119">A primary phone number must be:</span></span>

  - <span data-ttu-id="c5370-120">Único globalmente o, en el caso de las extensiones internas, exclusiva de la empresa.</span><span class="sxs-lookup"><span data-stu-id="c5370-120">Globally unique or, in the case of internal extensions, unique in the enterprise.</span></span>

  - <span data-ttu-id="c5370-121">Pertenece a la empresa y se pueda enrutar.</span><span class="sxs-lookup"><span data-stu-id="c5370-121">Owned by and routable in the enterprise.</span></span> <span data-ttu-id="c5370-122">No se deben usar números personales.</span><span class="sxs-lookup"><span data-stu-id="c5370-122">Personal numbers should not be used.</span></span>

<span data-ttu-id="c5370-123">Los usuarios de la empresa pueden tener dos o más números de teléfono que se indican en servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c5370-123">Enterprise users can have two or more telephone numbers listed for them in Active Directory Domain Services.</span></span> <span data-ttu-id="c5370-124">Todos los números de teléfono asociados con un usuario en particular se pueden ver o cambiar en la hoja de propiedades de ese usuario en el complemento usuarios y equipos de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c5370-124">All the telephone numbers associated with a particular user can be viewed or changed on the property sheet for that user in the Active Directory Users and Computers snap-in.</span></span>

<span data-ttu-id="c5370-125">El cuadro **número de teléfono** en la pestaña **General** del cuadro de diálogo Propiedades del **usuario** debe contener el número de trabajo principal del usuario.</span><span class="sxs-lookup"><span data-stu-id="c5370-125">The **Telephone number** box on the **General** tab of the **User Properties** dialog box should contain the user’s main work number.</span></span> <span data-ttu-id="c5370-126">Este número normalmente se designará como número de teléfono principal del usuario.</span><span class="sxs-lookup"><span data-stu-id="c5370-126">This number will usually be designated as the user's Primary Phone Number.</span></span>

<span data-ttu-id="c5370-127">Es posible que algunos usuarios tengan requisitos especiales (por ejemplo, un ejecutivo que quiera que todas las llamadas entrantes se dirijan a través de un auxiliar administrativo), pero dichas excepciones deben limitarse a aquellos casos en los que la necesidad sea clara y crítica.</span><span class="sxs-lookup"><span data-stu-id="c5370-127">Some users may have special requirements (for example, an executive who wants all incoming calls routed through an administrative assistant), but such exceptions should be limited only to those where the need is clear and critical.</span></span>

<span data-ttu-id="c5370-128">Una vez que se elige un número principal, debe ser:</span><span class="sxs-lookup"><span data-stu-id="c5370-128">After a primary number is chosen, it must be:</span></span>

  - <span data-ttu-id="c5370-129">Normalizado al formato E. 164, siempre que sea posible.</span><span class="sxs-lookup"><span data-stu-id="c5370-129">Normalized to E.164 format, wherever possible.</span></span>

  - <span data-ttu-id="c5370-130">Se ha copiado en el atributo de **msRTCSIP-line de** Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c5370-130">Copied to the Active Directory **msRTCSIP-line** attribute.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c5370-131"><STRONG>Coexistencia con control remoto de llamadas (RCC)</STRONG></span><span class="sxs-lookup"><span data-stu-id="c5370-131"><STRONG>Coexisting with remote call control (RCC)</STRONG></span></span><BR><span data-ttu-id="c5370-132">RCC es la capacidad de usar Lync Server para supervisar y controlar un teléfono PBX de escritorio.</span><span class="sxs-lookup"><span data-stu-id="c5370-132">RCC is the ability to use Lync Server to monitor and control a desktop PBX phone.</span></span> <span data-ttu-id="c5370-133">El control se enruta a través del servidor, que actúa como una puerta de enlace a la PBX.</span><span class="sxs-lookup"><span data-stu-id="c5370-133">Control is routed through the server, which acts as a gateway to the PBX.</span></span> <span data-ttu-id="c5370-134">Aunque no puede configurar un usuario tanto para RCC como para telefonía IP empresarial, la configuración de URI de línea designa el número de teléfono principal de un usuario en cualquier caso.</span><span class="sxs-lookup"><span data-stu-id="c5370-134">Although you cannot configure a user for both RCC and Enterprise Voice, the Line URI setting designates a user’s primary phone number in either case.</span></span><BR><span data-ttu-id="c5370-135">Si ya tiene una infraestructura PBX existente que quiere que los usuarios seleccionados puedan seguir usando, puede introducir una voz empresarial incremental en la organización.</span><span class="sxs-lookup"><span data-stu-id="c5370-135">If you have an existing PBX infrastructure that you want selected users to continue using, you can introduce Enterprise Voice incrementally into your organization.</span></span> <span data-ttu-id="c5370-136">Para obtener más información sobre este escenario de implementación, consulte <A href="lync-server-2013-direct-sip-deployment-options.md">Opciones de implementación de SIP directo en Lync Server 2013</A> en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="c5370-136">For details about this deployment scenario, see <A href="lync-server-2013-direct-sip-deployment-options.md">Direct SIP deployment options in Lync Server 2013</A> in the Planning documentation.</span></span><BR><span data-ttu-id="c5370-137">En versiones anteriores, se podía habilitar tanto RCC como empresarial Voice para un usuario, pero solo si también has configurado el usuario para la bifurcación dual, una característica en la que una llamada entrante sonará al teléfono PBX de un usuario y a Communicator al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="c5370-137">In previous releases, you could enable both RCC and Enterprise Voice for a user, but only if you also configured the user for dual forking, a feature in which an incoming call will ring a user’s PBX phone and Communicator simultaneously.</span></span> <span data-ttu-id="c5370-138">En Lync Server 2010, no se admite la bifurcación dual.</span><span class="sxs-lookup"><span data-stu-id="c5370-138">In Lync Server 2010, dual-forking is not supported.</span></span>

    
    </div>

<span data-ttu-id="c5370-139">Hay tres métodos para rellenar el atributo **msRTCSIP-line** :</span><span class="sxs-lookup"><span data-stu-id="c5370-139">There are three methods for populating the **msRTCSIP-line** attribute:</span></span>

  - <span data-ttu-id="c5370-140">Microsoft Identity Integration Server (recomendado)</span><span class="sxs-lookup"><span data-stu-id="c5370-140">Microsoft Identity Integration Server (recommended)</span></span>

  - <span data-ttu-id="c5370-141">Página **usuarios** del panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="c5370-141">The **Users** page in the Lync Server Control Panel</span></span>

<span data-ttu-id="c5370-142">Desde dónde se deben procesar muchos números de teléfono, la mejor opción es una secuencia de comandos personalizada desarrollada por su organización.</span><span class="sxs-lookup"><span data-stu-id="c5370-142">Where many phone numbers must be processed, a script custom developed by your organization is the better choice.</span></span> <span data-ttu-id="c5370-143">Según el modo en que la organización represente los números de teléfono en los servicios de dominio de Active Directory, es posible que la secuencia de comandos tenga que normalizar los números de teléfono principales al formato E. 164 antes de copiarlos en el atributo de **msRTCSIP-line** .</span><span class="sxs-lookup"><span data-stu-id="c5370-143">Depending on how your organization represents telephone numbers in Active Directory Domain Services, the script may have to normalize primary phone numbers to E.164 format before copying them to the **msRTCSIP-line** attribute.</span></span>

  - <span data-ttu-id="c5370-144">Si su organización mantiene todos los números de teléfono en los servicios de dominio de Active Directory en un solo formato y este formato es E. 164, su script solo necesita escribir cada número de teléfono principal en el atributo **msRTCSIP-line** .</span><span class="sxs-lookup"><span data-stu-id="c5370-144">If your organization maintains all telephone numbers in Active Directory Domain Services in a single format, and if that format is E.164, your script only needs to write each Primary Telephone Number to the **msRTCSIP-line** attribute.</span></span>

  - <span data-ttu-id="c5370-145">Si su organización mantiene todos los números de teléfono en los servicios de dominio de Active Directory en un solo formato, pero ese formato no es E. 164, su script debe definir una regla de normalización adecuada para convertir los números de teléfono principales de su formato existente. a E. 164 antes de escribirlos en el atributo **msRTCSIP-line** .</span><span class="sxs-lookup"><span data-stu-id="c5370-145">If your organization maintains all telephone numbers in Active Directory Domain Services in a single format, but that format is not E.164, your script should define an appropriate normalization rule to convert Primary Telephone Numbers from their existing format to E.164 before writing them to the **msRTCSIP-line** attribute.</span></span>

  - <span data-ttu-id="c5370-146">Si su organización no impone un formato estándar para los números de teléfono de los servicios de dominio de Active Directory, su script debe definir las reglas de normalización apropiadas para convertir los números de teléfono principales de los distintos formatos a E. 164 conformidad antes de escribir los números de teléfono primarios en el atributo de **msRTCSIP-line** .</span><span class="sxs-lookup"><span data-stu-id="c5370-146">If your organization does not enforce a standard format for telephone numbers in Active Directory Domain Services, your script should define appropriate normalization rules to convert Primary Phone Numbers from their various formats to E.164 compliance before writing the Primary Telephone Numbers to the **msRTCSIP-line** attribute.</span></span>

<span data-ttu-id="c5370-147">El script también tendrá que insertar el prefijo **Tel:** antes de cada número principal antes de escribirlo en el atributo de **msRTCSIP-line** .</span><span class="sxs-lookup"><span data-stu-id="c5370-147">Your script will also have to insert the prefix **Tel:** before each primary number before writing it to the **msRTCSIP-line** attribute.</span></span>

<span data-ttu-id="c5370-148">El formato esperado del número especificado en este atributo es:</span><span class="sxs-lookup"><span data-stu-id="c5370-148">The expected format of the number specified in this attribute is:</span></span>

  - <span data-ttu-id="c5370-149">Tel: + 14255550100; ext = 50100.</span><span class="sxs-lookup"><span data-stu-id="c5370-149">Tel:+14255550100;ext=50100.</span></span>

  - <span data-ttu-id="c5370-150">Tel: 5550100 (para extensiones exclusivas de toda la empresa)</span><span class="sxs-lookup"><span data-stu-id="c5370-150">Tel:5550100 (for unique enterprise wide extensions)</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c5370-151">La normalización realizada por el servicio de libreta de direcciones (ABS) no reemplaza o elimina la necesidad de normalizar el número de teléfono principal de cada usuario en servicios de dominio de Active Directory porque ABS no tiene acceso a los servicios de dominio de Active Directory y por lo tanto, no puede copiar números primarios en el atributo <STRONG>msRTCSIP-line</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="c5370-151">The normalization performed by the Address Book Service (ABS) does not replace or otherwise eliminate the need to normalize each user's primary phone number in Active Directory Domain Services because ABS does not have access to Active Directory Domain Services and therefore cannot copy primary numbers to the <STRONG>msRTCSIP-line</STRONG> attribute.</span></span>

    
    </div>

</div>

<div>

## <a name="step-2-enable-users-for-enterprise-voice"></a><span data-ttu-id="c5370-152">Paso 2.</span><span class="sxs-lookup"><span data-stu-id="c5370-152">Step 2.</span></span> <span data-ttu-id="c5370-153">Habilitar a los usuarios para la telefonía IP empresarial</span><span class="sxs-lookup"><span data-stu-id="c5370-153">Enable users for Enterprise Voice</span></span>

<span data-ttu-id="c5370-154">Aparte de identificar qué usuarios se deben habilitar, no es necesario realizar ninguna planificación especial para completar este paso.</span><span class="sxs-lookup"><span data-stu-id="c5370-154">Other than identifying which users are to be enabled, no special planning is required to complete this step.</span></span>

</div>

<div>

## <a name="step-3-prepare-dial-plans-for-users"></a><span data-ttu-id="c5370-155">Paso 3.</span><span class="sxs-lookup"><span data-stu-id="c5370-155">Step 3.</span></span> <span data-ttu-id="c5370-156">Preparar planes de marcado para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="c5370-156">Prepare dial plans for users.</span></span>

<span data-ttu-id="c5370-157">Los usuarios que están habilitados para telefonía IP empresarial no podrán llamar a la llamada a la RTC sin realizar planes de marcado.</span><span class="sxs-lookup"><span data-stu-id="c5370-157">Users who are enabled for Enterprise Voice will not be able to make calls to the PSTN without dial plans in place.</span></span> <span data-ttu-id="c5370-158">Un plan de marcado es un conjunto de reglas de normalización especificado por el usuario que convierte números de teléfono para una ubicación especificada por el usuario, un usuario individual o un objeto de contacto a un formato estándar único (E.164) con fines de autorización telefónica y enrutamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="c5370-158">A dial plan is a named set of normalization rules that translates phone numbers for a named location, individual user, or contact object into a single standard (E.164) format for purposes of phone authorization and call routing.</span></span> <span data-ttu-id="c5370-159">Las reglas de normalización definen la forma en que los números de teléfono expresados en diversos formatos se van a redirigir en cada ubicación, usuario u objeto de contacto que se haya especificado.</span><span class="sxs-lookup"><span data-stu-id="c5370-159">Normalization rules define how phone numbers expressed in various formats are to be routed for each specified location, user, or contact object.</span></span>

<span data-ttu-id="c5370-160">Para obtener información sobre la preparación de los planes de marcado, consulte [planes de marcado y reglas de normalización en Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md).</span><span class="sxs-lookup"><span data-stu-id="c5370-160">For information about preparing dial plans, see [Dial plans and normalization rules in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md).</span></span>

</div>

<div>

## <a name="step-4-plan-user-voice-policies"></a><span data-ttu-id="c5370-161">Paso 4.</span><span class="sxs-lookup"><span data-stu-id="c5370-161">Step 4.</span></span> <span data-ttu-id="c5370-162">Planear las directivas de voz de usuario</span><span class="sxs-lookup"><span data-stu-id="c5370-162">Plan user voice policies</span></span>

<span data-ttu-id="c5370-163">La configuración de clase de usuario de servicio en un sistema PBX heredado, como el derecho de hacer llamadas de larga distancia o internacionales desde teléfonos de la empresa, debe ser reconfigurada como directivas de VoIP para los usuarios que han migrado a la telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="c5370-163">User class-of-service settings on a legacy PBX, such as the right to make long-distance or international calls from company phones, must be reconfigured as VoIP policies for users moved to Enterprise Voice.</span></span> <span data-ttu-id="c5370-164">Para obtener más información sobre la planeación y la creación de directivas para telefonía IP empresarial, consulte [directivas de voz en Lync Server 2013](lync-server-2013-voice-policies.md).</span><span class="sxs-lookup"><span data-stu-id="c5370-164">For details about planning and creating policies for Enterprise Voice, see [Voice policies in Lync Server 2013](lync-server-2013-voice-policies.md).</span></span>

</div>

<div>

## <a name="step-5-plan-outbound-call-routes"></a><span data-ttu-id="c5370-165">Paso 5.</span><span class="sxs-lookup"><span data-stu-id="c5370-165">Step 5.</span></span> <span data-ttu-id="c5370-166">Planificar rutas de llamadas salientes</span><span class="sxs-lookup"><span data-stu-id="c5370-166">Plan outbound call routes</span></span>

<span data-ttu-id="c5370-167">Las rutas de llamadas especifican cómo Lync Server administra las llamadas salientes que hacen los usuarios de telefonía IP.</span><span class="sxs-lookup"><span data-stu-id="c5370-167">Call routes specify how Lync Server handles outbound calls placed by Enterprise Voice users.</span></span> <span data-ttu-id="c5370-168">Cuando un usuario marca un número, el servidor, si es necesario, normaliza la cadena de marcado al formato E. 164 e intenta hacerlo coincidir con el URI del SIP.</span><span class="sxs-lookup"><span data-stu-id="c5370-168">When a user dials a number, the server, if necessary, normalizes the dial string to E.164 format and attempts to match it to a SIP URI.</span></span> <span data-ttu-id="c5370-169">Si el servidor no puede establecer la coincidencia, aplica la lógica de enrutamiento de llamadas salientes en función del número.</span><span class="sxs-lookup"><span data-stu-id="c5370-169">If the server is unable to make the match, it applies outgoing call routing logic based on the number.</span></span> <span data-ttu-id="c5370-170">El último paso para definir esa lógica es crear una ruta de llamada con nombre diferente para cada conjunto de números de teléfono de destino que aparecen en cada plan de marcado.</span><span class="sxs-lookup"><span data-stu-id="c5370-170">The final step in defining that logic is creating a separate named call route for each set of destination phone numbers that are listed in each dial plan.</span></span>

<span data-ttu-id="c5370-171">Para obtener más información sobre la planeación de rutas de llamadas, consulte [rutas de voz en Lync Server 2013](lync-server-2013-voice-routes.md).</span><span class="sxs-lookup"><span data-stu-id="c5370-171">For details about planning call routes, see [Voice routes in Lync Server 2013](lync-server-2013-voice-routes.md).</span></span>

</div>

<div>

## <a name="step-6-configure-pbx-or-sip-trunk-to-reroute-calls-for-enterprise-voice-users"></a><span data-ttu-id="c5370-172">Paso 6.</span><span class="sxs-lookup"><span data-stu-id="c5370-172">Step 6.</span></span> <span data-ttu-id="c5370-173">Configurar el tronco de PBX o SIP para redirigir llamadas para usuarios de Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="c5370-173">Configure PBX or SIP Trunk to reroute calls for Enterprise Voice users</span></span>

<span data-ttu-id="c5370-174">Los usuarios que anteriormente se hospedaban en una PBX tradicional o en una conexión SIP troncal a un proveedor de servicios de telefonía por Internet (ITSP) conservan sus números de teléfono después del movimiento.</span><span class="sxs-lookup"><span data-stu-id="c5370-174">Users who formerly were hosted on a traditional PBX or on a SIP Trunk connection to an Internet Telephony Service Provider (ITSP) retain their phone numbers after the move.</span></span> <span data-ttu-id="c5370-175">El único requisito es que, después de la mudanza, el troncal de PBX o SIP debe reconfigurarse para enrutar las llamadas entrantes para los usuarios de la empresa de telefonía al servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="c5370-175">The only requirement is that after the move, the PBX or SIP Trunk must be reconfigured to route incoming calls for Enterprise Voice users to the Mediation Server.</span></span>

</div>

<div>

## <a name="step-7-move-users-to-exchange-unified-messaging-recommended"></a><span data-ttu-id="c5370-176">Paso 7.</span><span class="sxs-lookup"><span data-stu-id="c5370-176">Step 7.</span></span> <span data-ttu-id="c5370-177">Mover usuarios a la mensajería unificada de Exchange (recomendado)</span><span class="sxs-lookup"><span data-stu-id="c5370-177">Move users to Exchange Unified Messaging (recommended)</span></span>

<span data-ttu-id="c5370-178">El traslado de usuarios a la mensajería unificada de Exchange consta de las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="c5370-178">Moving users to Exchange Unified Messaging consists of the following tasks:</span></span>

  - <span data-ttu-id="c5370-179">Configure la mensajería unificada de Exchange y Lync Server para que funcionen conjuntamente.</span><span class="sxs-lookup"><span data-stu-id="c5370-179">Configure Exchange Unified Messaging and Lync Server to work together.</span></span>

  - <span data-ttu-id="c5370-180">Habilite los usuarios para la respuesta de la mensajería unificada de Exchange y Outlook Voice Access.</span><span class="sxs-lookup"><span data-stu-id="c5370-180">Enable users for Exchange Unified Messaging call answering and Outlook Voice Access.</span></span> <span data-ttu-id="c5370-181">Esta tarea se realiza en el servidor de mensajería unificada de Exchange.</span><span class="sxs-lookup"><span data-stu-id="c5370-181">This task is performed on the Exchange Unified Messaging server.</span></span> <span data-ttu-id="c5370-182">Para obtener más información, consulte la biblioteca de TechNet de [http://go.microsoft.com/fwlink/p/?linkID=139372](http://go.microsoft.com/fwlink/p/?linkid=139372)Exchange Server 2010 en.</span><span class="sxs-lookup"><span data-stu-id="c5370-182">For details, see the Exchange Server 2010 TechNet Library at [http://go.microsoft.com/fwlink/p/?linkID=139372](http://go.microsoft.com/fwlink/p/?linkid=139372).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

