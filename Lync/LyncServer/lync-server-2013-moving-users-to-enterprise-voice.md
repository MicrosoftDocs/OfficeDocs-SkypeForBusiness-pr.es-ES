---
title: 'Lync Server 2013: mover usuarios a telefonía IP empresarial'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Moving users to Enterprise Voice
ms:assetid: a2df6d51-5cf2-4d3e-8f97-496af5fd5e5e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412758(v=OCS.15)
ms:contentKeyID: 48184958
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5554a9c7fde74b5bcf9c81c451023d0f48bbf918
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42217146"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="moving-users-to-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="fe106-102">Mover usuarios a telefonía IP empresarial en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fe106-102">Moving users to Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fe106-103">_**Última modificación del tema:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="fe106-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="fe106-104">Si va a mover usuarios de una infraestructura de telefonía PBX existente a Enterprise Voice, el proceso de implementación incluye algunos pasos que no forman parte del proceso de planeación ya descrito en [Planning for Enterprise Voice in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md).</span><span class="sxs-lookup"><span data-stu-id="fe106-104">If you are moving users from an existing PBX telephony infrastructure to Enterprise Voice, the deployment process includes some steps that are not part of the planning process already described in [Planning for Enterprise Voice in Lync Server 2013](lync-server-2013-planning-for-enterprise-voice.md).</span></span> <span data-ttu-id="fe106-105">Para obtener información sobre la migración de usuarios de una implementación de telefonía IP empresarial anterior, vea los documentos de migración que se incluyeron en los medios de instalación.</span><span class="sxs-lookup"><span data-stu-id="fe106-105">For information about migrating users from an earlier Enterprise Voice deployment, see the migration documents that were included with your installation media.</span></span>

<span data-ttu-id="fe106-106">El proceso de traslado de usuarios de una infraestructura de telefonía existente a Enterprise Voice consta de los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="fe106-106">The process of moving users from an existing telephony infrastructure to Enterprise Voice consists of the following steps:</span></span>

1.  <span data-ttu-id="fe106-107">Designar los números de teléfono principales.</span><span class="sxs-lookup"><span data-stu-id="fe106-107">Designate primary phone numbers.</span></span>

2.  <span data-ttu-id="fe106-108">Habilitar a los usuarios para Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="fe106-108">Enable users for Enterprise Voice.</span></span>

3.  <span data-ttu-id="fe106-109">Preparar planes de marcado para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="fe106-109">Prepare dial plans for users.</span></span>

4.  <span data-ttu-id="fe106-110">Planeación de directivas de voz de usuario.</span><span class="sxs-lookup"><span data-stu-id="fe106-110">Plan user voice policies.</span></span>

5.  <span data-ttu-id="fe106-111">Planeación de rutas de llamadas.</span><span class="sxs-lookup"><span data-stu-id="fe106-111">Plan call routes.</span></span>

6.  <span data-ttu-id="fe106-112">Configure PBX o el tronco SIP para redirigir las llamadas de los usuarios habilitados para telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="fe106-112">Configure PBX or SIP Trunk to reroute calls for users enabled for Enterprise Voice.</span></span>

7.  <span data-ttu-id="fe106-113">Mover usuarios a mensajería unificada (UM) de Exchange (recomendado).</span><span class="sxs-lookup"><span data-stu-id="fe106-113">Move users to Exchange Unified Messaging (UM) (recommended).</span></span>

<span data-ttu-id="fe106-114">En este tema se describe la planeación necesaria para cada uno de estos pasos.</span><span class="sxs-lookup"><span data-stu-id="fe106-114">This topic describes the planning that is necessary for each of these steps.</span></span>

<div>

## <a name="step-1-designate-primary-phone-numbers"></a><span data-ttu-id="fe106-115">Paso 1.</span><span class="sxs-lookup"><span data-stu-id="fe106-115">Step 1.</span></span> <span data-ttu-id="fe106-116">Designar los números de teléfono principales</span><span class="sxs-lookup"><span data-stu-id="fe106-116">Designate primary phone numbers</span></span>

<span data-ttu-id="fe106-117">La telefonía IP empresarial se integra con otros medios de mensajería, de modo que cuando una llamada entrante llega al servidor, el servidor asigna el número al URI SIP del usuario y, a continuación, se ramifica la llamada a todos los extremos de cliente asociados con ese SIP-URI.</span><span class="sxs-lookup"><span data-stu-id="fe106-117">Enterprise Voice integrates voice with other messaging media, such that when an incoming call arrives at the server, the server maps the number to the user’s SIP-URI and then forks the call to all the client endpoints associated with that SIP-URI.</span></span> <span data-ttu-id="fe106-118">Este proceso requiere que cada usuario esté asociado a un número de teléfono principal.</span><span class="sxs-lookup"><span data-stu-id="fe106-118">This process requires that each user be associated with a primary phone number.</span></span>

<span data-ttu-id="fe106-119">Un número de teléfono principal debe ser:</span><span class="sxs-lookup"><span data-stu-id="fe106-119">A primary phone number must be:</span></span>

  - <span data-ttu-id="fe106-120">Globalmente único o, en el caso de las extensiones internas, única en la empresa.</span><span class="sxs-lookup"><span data-stu-id="fe106-120">Globally unique or, in the case of internal extensions, unique in the enterprise.</span></span>

  - <span data-ttu-id="fe106-121">Propiedad de y enrutable de la empresa.</span><span class="sxs-lookup"><span data-stu-id="fe106-121">Owned by and routable in the enterprise.</span></span> <span data-ttu-id="fe106-122">No se deben usar números personales.</span><span class="sxs-lookup"><span data-stu-id="fe106-122">Personal numbers should not be used.</span></span>

<span data-ttu-id="fe106-123">Los usuarios de la empresa pueden tener dos o más números de teléfono enumerados para ellos en los servicios de dominio de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="fe106-123">Enterprise users can have two or more telephone numbers listed for them in Active Directory Domain Services.</span></span> <span data-ttu-id="fe106-124">Todos los números de teléfono asociados con un usuario en particular se pueden ver o cambiar en la hoja de propiedades de ese usuario en el complemento usuarios y equipos de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="fe106-124">All the telephone numbers associated with a particular user can be viewed or changed on the property sheet for that user in the Active Directory Users and Computers snap-in.</span></span>

<span data-ttu-id="fe106-125">El cuadro **número de teléfono** de la ficha **General** del cuadro de diálogo Propiedades de **usuario** debe contener el número de trabajo principal del usuario.</span><span class="sxs-lookup"><span data-stu-id="fe106-125">The **Telephone number** box on the **General** tab of the **User Properties** dialog box should contain the user’s main work number.</span></span> <span data-ttu-id="fe106-126">Este número se suele designar como el número de teléfono principal del usuario.</span><span class="sxs-lookup"><span data-stu-id="fe106-126">This number will usually be designated as the user's Primary Phone Number.</span></span>

<span data-ttu-id="fe106-127">Es posible que algunos usuarios tengan requisitos especiales (por ejemplo, un ejecutivo que quiera que todas las llamadas entrantes se enruten a través de un asistente administrativo), pero esas excepciones deben limitarse a aquellas en las que la necesidad sea clara y crítica.</span><span class="sxs-lookup"><span data-stu-id="fe106-127">Some users may have special requirements (for example, an executive who wants all incoming calls routed through an administrative assistant), but such exceptions should be limited only to those where the need is clear and critical.</span></span>

<span data-ttu-id="fe106-128">Una vez seleccionado un número principal, debe ser:</span><span class="sxs-lookup"><span data-stu-id="fe106-128">After a primary number is chosen, it must be:</span></span>

  - <span data-ttu-id="fe106-129">Normalizado al formato E. 164, siempre que sea posible.</span><span class="sxs-lookup"><span data-stu-id="fe106-129">Normalized to E.164 format, wherever possible.</span></span>

  - <span data-ttu-id="fe106-130">Se copia en el atributo **msRTCSIP-line de** Active Directory.</span><span class="sxs-lookup"><span data-stu-id="fe106-130">Copied to the Active Directory **msRTCSIP-line** attribute.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="fe106-131"><STRONG>Coexistencia con control remoto de llamadas (RCC)</STRONG></span><span class="sxs-lookup"><span data-stu-id="fe106-131"><STRONG>Coexisting with remote call control (RCC)</STRONG></span></span><BR><span data-ttu-id="fe106-132">RCC es la capacidad de usar Lync Server para supervisar y controlar un teléfono PBX de escritorio.</span><span class="sxs-lookup"><span data-stu-id="fe106-132">RCC is the ability to use Lync Server to monitor and control a desktop PBX phone.</span></span> <span data-ttu-id="fe106-133">El control se enruta a través del servidor, que actúa como una puerta de enlace a la PBX.</span><span class="sxs-lookup"><span data-stu-id="fe106-133">Control is routed through the server, which acts as a gateway to the PBX.</span></span> <span data-ttu-id="fe106-134">Aunque no se puede configurar un usuario tanto para RCC como para telefonía IP empresarial, la configuración de URI de línea designa el número de teléfono principal de un usuario en cualquier caso.</span><span class="sxs-lookup"><span data-stu-id="fe106-134">Although you cannot configure a user for both RCC and Enterprise Voice, the Line URI setting designates a user’s primary phone number in either case.</span></span><BR><span data-ttu-id="fe106-135">Si tiene una infraestructura PBX existente que desea que los usuarios seleccionados sigan usando, puede presentar la telefonía IP empresarial de forma incremental en su organización.</span><span class="sxs-lookup"><span data-stu-id="fe106-135">If you have an existing PBX infrastructure that you want selected users to continue using, you can introduce Enterprise Voice incrementally into your organization.</span></span> <span data-ttu-id="fe106-136">Para obtener más información sobre este escenario de implementación, consulte <A href="lync-server-2013-direct-sip-deployment-options.md">Opciones de implementación SIP directa en Lync Server 2013</A> en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="fe106-136">For details about this deployment scenario, see <A href="lync-server-2013-direct-sip-deployment-options.md">Direct SIP deployment options in Lync Server 2013</A> in the Planning documentation.</span></span><BR><span data-ttu-id="fe106-137">En versiones anteriores, podía habilitar tanto RCC como Enterprise Voice para un usuario, pero solo si también configuraste el usuario para dos ramificaciones, una característica en la que una llamada entrante sonará simultáneamente por teléfono PBX de usuario y Communicator.</span><span class="sxs-lookup"><span data-stu-id="fe106-137">In previous releases, you could enable both RCC and Enterprise Voice for a user, but only if you also configured the user for dual forking, a feature in which an incoming call will ring a user’s PBX phone and Communicator simultaneously.</span></span> <span data-ttu-id="fe106-138">En Lync Server 2010, no se admite la bifurcación dual.</span><span class="sxs-lookup"><span data-stu-id="fe106-138">In Lync Server 2010, dual-forking is not supported.</span></span>

    
    </div>

<span data-ttu-id="fe106-139">Hay tres métodos para rellenar el atributo **msRTCSIP-line** :</span><span class="sxs-lookup"><span data-stu-id="fe106-139">There are three methods for populating the **msRTCSIP-line** attribute:</span></span>

  - <span data-ttu-id="fe106-140">Microsoft Identity Integration Server (recomendado)</span><span class="sxs-lookup"><span data-stu-id="fe106-140">Microsoft Identity Integration Server (recommended)</span></span>

  - <span data-ttu-id="fe106-141">Página **usuarios** del panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="fe106-141">The **Users** page in the Lync Server Control Panel</span></span>

<span data-ttu-id="fe106-142">Cuando se deben procesar muchos números de teléfono, la mejor opción es una secuencia de comandos personalizada desarrollada por la organización.</span><span class="sxs-lookup"><span data-stu-id="fe106-142">Where many phone numbers must be processed, a script custom developed by your organization is the better choice.</span></span> <span data-ttu-id="fe106-143">En función de cómo represente su organización los números de teléfono en los servicios de dominio de Active Directory, es posible que el script deba normalizar los números de teléfono principales al formato E. 164 antes de copiarlos al atributo **msRTCSIP-line** .</span><span class="sxs-lookup"><span data-stu-id="fe106-143">Depending on how your organization represents telephone numbers in Active Directory Domain Services, the script may have to normalize primary phone numbers to E.164 format before copying them to the **msRTCSIP-line** attribute.</span></span>

  - <span data-ttu-id="fe106-144">Si su organización mantiene todos los números de teléfono de los servicios de dominio de Active Directory en un único formato y, si ese formato es E. 164, el script solo tiene que escribir cada número de teléfono principal en el atributo **msRTCSIP-line** .</span><span class="sxs-lookup"><span data-stu-id="fe106-144">If your organization maintains all telephone numbers in Active Directory Domain Services in a single format, and if that format is E.164, your script only needs to write each Primary Telephone Number to the **msRTCSIP-line** attribute.</span></span>

  - <span data-ttu-id="fe106-145">Si la organización mantiene todos los números de teléfono de los servicios de dominio de Active Directory en un único formato, pero ese formato no es E. 164, el script debe definir una regla de normalización adecuada para convertir los números de teléfono principales de su formato existente a E. 164 antes de escribirlos en el atributo **msRTCSIP-line** .</span><span class="sxs-lookup"><span data-stu-id="fe106-145">If your organization maintains all telephone numbers in Active Directory Domain Services in a single format, but that format is not E.164, your script should define an appropriate normalization rule to convert Primary Telephone Numbers from their existing format to E.164 before writing them to the **msRTCSIP-line** attribute.</span></span>

  - <span data-ttu-id="fe106-146">Si su organización no exige un formato estándar para los números de teléfono de los servicios de dominio de Active Directory, el script debe definir las reglas de normalización adecuadas para convertir los números de teléfono principales de los distintos formatos a E. 164 cumplimiento antes de escribir los números de teléfono principales en el atributo **msRTCSIP-line** .</span><span class="sxs-lookup"><span data-stu-id="fe106-146">If your organization does not enforce a standard format for telephone numbers in Active Directory Domain Services, your script should define appropriate normalization rules to convert Primary Phone Numbers from their various formats to E.164 compliance before writing the Primary Telephone Numbers to the **msRTCSIP-line** attribute.</span></span>

<span data-ttu-id="fe106-147">El script también tendrá que insertar el prefijo **Tel:** antes de cada número principal antes de escribirlo en el atributo **msRTCSIP-line** .</span><span class="sxs-lookup"><span data-stu-id="fe106-147">Your script will also have to insert the prefix **Tel:** before each primary number before writing it to the **msRTCSIP-line** attribute.</span></span>

<span data-ttu-id="fe106-148">El formato esperado del número especificado en este atributo es:</span><span class="sxs-lookup"><span data-stu-id="fe106-148">The expected format of the number specified in this attribute is:</span></span>

  - <span data-ttu-id="fe106-149">Tel: + 14255550100; ext = 50100.</span><span class="sxs-lookup"><span data-stu-id="fe106-149">Tel:+14255550100;ext=50100.</span></span>

  - <span data-ttu-id="fe106-150">Tel: 5550100 (para extensiones únicas de toda la empresa)</span><span class="sxs-lookup"><span data-stu-id="fe106-150">Tel:5550100 (for unique enterprise wide extensions)</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="fe106-151">La normalización que realiza el servicio de libreta de direcciones (ABS) no reemplaza o elimina la necesidad de normalizar el número de teléfono principal de cada usuario en servicios de dominio de Active Directory porque el ABS no tiene acceso a los servicios de dominio de Active Directory y, por lo tanto, no puede copiar los números principales en el atributo <STRONG>msRTCSIP-line</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="fe106-151">The normalization performed by the Address Book Service (ABS) does not replace or otherwise eliminate the need to normalize each user's primary phone number in Active Directory Domain Services because ABS does not have access to Active Directory Domain Services and therefore cannot copy primary numbers to the <STRONG>msRTCSIP-line</STRONG> attribute.</span></span>

    
    </div>

</div>

<div>

## <a name="step-2-enable-users-for-enterprise-voice"></a><span data-ttu-id="fe106-152">Paso 2.</span><span class="sxs-lookup"><span data-stu-id="fe106-152">Step 2.</span></span> <span data-ttu-id="fe106-153">Habilitar a los usuarios para la telefonía IP empresarial</span><span class="sxs-lookup"><span data-stu-id="fe106-153">Enable users for Enterprise Voice</span></span>

<span data-ttu-id="fe106-154">Aparte de identificar los usuarios que se van a habilitar, no se requiere una planificación especial para completar este paso.</span><span class="sxs-lookup"><span data-stu-id="fe106-154">Other than identifying which users are to be enabled, no special planning is required to complete this step.</span></span>

</div>

<div>

## <a name="step-3-prepare-dial-plans-for-users"></a><span data-ttu-id="fe106-155">Paso 3.</span><span class="sxs-lookup"><span data-stu-id="fe106-155">Step 3.</span></span> <span data-ttu-id="fe106-156">Preparar planes de marcado para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="fe106-156">Prepare dial plans for users.</span></span>

<span data-ttu-id="fe106-157">Los usuarios habilitados para la telefonía IP empresarial no podrán realizar llamadas a la RTC sin planes de marcado en su lugar.</span><span class="sxs-lookup"><span data-stu-id="fe106-157">Users who are enabled for Enterprise Voice will not be able to make calls to the PSTN without dial plans in place.</span></span> <span data-ttu-id="fe106-158">Un plan de marcado es un conjunto de reglas de normalización especificado por el usuario que convierte números de teléfono para una ubicación especificada por el usuario, un usuario individual o un objeto de contacto a un formato estándar único (E.164) con fines de autorización telefónica y enrutamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="fe106-158">A dial plan is a named set of normalization rules that translates phone numbers for a named location, individual user, or contact object into a single standard (E.164) format for purposes of phone authorization and call routing.</span></span> <span data-ttu-id="fe106-159">Las reglas de normalización definen la forma en que los números de teléfono expresados en diversos formatos se van a enrutar en cada ubicación, usuario u objeto de contacto que se haya especificado.</span><span class="sxs-lookup"><span data-stu-id="fe106-159">Normalization rules define how phone numbers expressed in various formats are to be routed for each specified location, user, or contact object.</span></span>

<span data-ttu-id="fe106-160">Para obtener información sobre la preparación de planes de marcado, consulte [planes de marcado y reglas de normalización en Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md).</span><span class="sxs-lookup"><span data-stu-id="fe106-160">For information about preparing dial plans, see [Dial plans and normalization rules in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md).</span></span>

</div>

<div>

## <a name="step-4-plan-user-voice-policies"></a><span data-ttu-id="fe106-161">Paso 4.</span><span class="sxs-lookup"><span data-stu-id="fe106-161">Step 4.</span></span> <span data-ttu-id="fe106-162">Planeación de directivas de voz de usuario</span><span class="sxs-lookup"><span data-stu-id="fe106-162">Plan user voice policies</span></span>

<span data-ttu-id="fe106-163">La configuración de la clase de servicio de usuario en una PBX heredada, como el derecho de realizar llamadas de larga distancia o internacionales desde los teléfonos de la empresa, debe volver a configurarse como directivas VoIP para los usuarios que se movieron a la telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="fe106-163">User class-of-service settings on a legacy PBX, such as the right to make long-distance or international calls from company phones, must be reconfigured as VoIP policies for users moved to Enterprise Voice.</span></span> <span data-ttu-id="fe106-164">Para obtener más información sobre la planeación y la creación de directivas para la telefonía IP empresarial, consulte [directivas de voz en Lync Server 2013](lync-server-2013-voice-policies.md).</span><span class="sxs-lookup"><span data-stu-id="fe106-164">For details about planning and creating policies for Enterprise Voice, see [Voice policies in Lync Server 2013](lync-server-2013-voice-policies.md).</span></span>

</div>

<div>

## <a name="step-5-plan-outbound-call-routes"></a><span data-ttu-id="fe106-165">Paso 5.</span><span class="sxs-lookup"><span data-stu-id="fe106-165">Step 5.</span></span> <span data-ttu-id="fe106-166">Planeación de rutas de llamadas salientes</span><span class="sxs-lookup"><span data-stu-id="fe106-166">Plan outbound call routes</span></span>

<span data-ttu-id="fe106-167">Las rutas de llamadas especifican cómo Lync Server administra las llamadas salientes realizadas por los usuarios de telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="fe106-167">Call routes specify how Lync Server handles outbound calls placed by Enterprise Voice users.</span></span> <span data-ttu-id="fe106-168">Cuando un usuario marca un número, el servidor, si es necesario, normaliza la cadena de marcado al formato E. 164 e intenta establecer una coincidencia con un URI de SIP.</span><span class="sxs-lookup"><span data-stu-id="fe106-168">When a user dials a number, the server, if necessary, normalizes the dial string to E.164 format and attempts to match it to a SIP URI.</span></span> <span data-ttu-id="fe106-169">Si el servidor no puede realizar la coincidencia, aplica la lógica de enrutamiento de llamadas salientes en función del número.</span><span class="sxs-lookup"><span data-stu-id="fe106-169">If the server is unable to make the match, it applies outgoing call routing logic based on the number.</span></span> <span data-ttu-id="fe106-170">El último paso para definir la lógica es crear una ruta de llamada con nombre independiente para cada conjunto de números de teléfono de destino que se enumeran en cada plan de marcado.</span><span class="sxs-lookup"><span data-stu-id="fe106-170">The final step in defining that logic is creating a separate named call route for each set of destination phone numbers that are listed in each dial plan.</span></span>

<span data-ttu-id="fe106-171">Para obtener más información sobre la planeación de rutas de llamadas, consulte [rutas de voz en Lync Server 2013](lync-server-2013-voice-routes.md).</span><span class="sxs-lookup"><span data-stu-id="fe106-171">For details about planning call routes, see [Voice routes in Lync Server 2013](lync-server-2013-voice-routes.md).</span></span>

</div>

<div>

## <a name="step-6-configure-pbx-or-sip-trunk-to-reroute-calls-for-enterprise-voice-users"></a><span data-ttu-id="fe106-172">Paso 6.</span><span class="sxs-lookup"><span data-stu-id="fe106-172">Step 6.</span></span> <span data-ttu-id="fe106-173">Configurar la PBX o el tronco SIP para redirigir las llamadas de los usuarios de Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="fe106-173">Configure PBX or SIP Trunk to reroute calls for Enterprise Voice users</span></span>

<span data-ttu-id="fe106-174">Los usuarios que anteriormente se hospedaban en una PBX tradicional o en una conexión de enlace troncal SIP a un proveedor de servicios de telefonía por Internet (ITSP) conservan sus números de teléfono después del traslado.</span><span class="sxs-lookup"><span data-stu-id="fe106-174">Users who formerly were hosted on a traditional PBX or on a SIP Trunk connection to an Internet Telephony Service Provider (ITSP) retain their phone numbers after the move.</span></span> <span data-ttu-id="fe106-175">El único requisito es que, después del traslado, el tronco de PBX o de SIP se debe volver a configurar para enrutar las llamadas entrantes de los usuarios de Enterprise Voice al servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="fe106-175">The only requirement is that after the move, the PBX or SIP Trunk must be reconfigured to route incoming calls for Enterprise Voice users to the Mediation Server.</span></span>

</div>

<div>

## <a name="step-7-move-users-to-exchange-unified-messaging-recommended"></a><span data-ttu-id="fe106-176">Paso 7.</span><span class="sxs-lookup"><span data-stu-id="fe106-176">Step 7.</span></span> <span data-ttu-id="fe106-177">Mover usuarios a la mensajería unificada de Exchange (recomendado)</span><span class="sxs-lookup"><span data-stu-id="fe106-177">Move users to Exchange Unified Messaging (recommended)</span></span>

<span data-ttu-id="fe106-178">El traslado de usuarios a la mensajería unificada de Exchange consta de las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="fe106-178">Moving users to Exchange Unified Messaging consists of the following tasks:</span></span>

  - <span data-ttu-id="fe106-179">Configurar la mensajería unificada de Exchange y Lync Server para que funcionen conjuntamente.</span><span class="sxs-lookup"><span data-stu-id="fe106-179">Configure Exchange Unified Messaging and Lync Server to work together.</span></span>

  - <span data-ttu-id="fe106-180">Habilite a los usuarios para el contestador automático de mensajería unificada de Exchange y Outlook Voice Access.</span><span class="sxs-lookup"><span data-stu-id="fe106-180">Enable users for Exchange Unified Messaging call answering and Outlook Voice Access.</span></span> <span data-ttu-id="fe106-181">Esta tarea se realiza en el servidor de mensajería unificada de Exchange.</span><span class="sxs-lookup"><span data-stu-id="fe106-181">This task is performed on the Exchange Unified Messaging server.</span></span> <span data-ttu-id="fe106-182">Para obtener más información, consulte la biblioteca de TechNet de [https://go.microsoft.com/fwlink/p/?linkID=139372](https://go.microsoft.com/fwlink/p/?linkid=139372)Exchange Server 2010 en.</span><span class="sxs-lookup"><span data-stu-id="fe106-182">For details, see the Exchange Server 2010 TechNet Library at [https://go.microsoft.com/fwlink/p/?linkID=139372](https://go.microsoft.com/fwlink/p/?linkid=139372).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

