---
title: 'Lync Server 2013: planes de marcado y reglas de normalización'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Dial plans and normalization rules
ms:assetid: fde45195-6eb4-403c-9094-57df7fc0bd2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413082(v=OCS.15)
ms:contentKeyID: 48185960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5d399c49db109a7bac1a1cd3ac430280cb70f665
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835420"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dial-plans-and-normalization-rules-in-lync-server-2013"></a><span data-ttu-id="65f96-102">Planes de marcado y reglas de normalización en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="65f96-102">Dial plans and normalization rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="65f96-103">_**Última modificación del tema:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="65f96-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="65f96-104">Un plan de marcado es un conjunto de reglas de normalización especificado por el usuario que convierte números de teléfono para una ubicación especificada por el usuario, un usuario individual o un objeto de contacto a un formato estándar único (E.164) con fines de autorización telefónica y enrutamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="65f96-104">A dial plan is a named set of normalization rules that translates phone numbers for a named location, individual user, or contact object into a single standard (E.164) format for purposes of phone authorization and call routing.</span></span>

<span data-ttu-id="65f96-p101">Las reglas de normalización definen la forma en que los números de teléfono expresados en diversos formatos se van a redirigir en cada ubicación, usuario u objeto de contacto que se haya especificado. La misma cadena de marcado se puede interpretar y convertir de manera distinta en función de la ubicación desde la que se marque y la persona o el objeto de contacto que realice la llamada.</span><span class="sxs-lookup"><span data-stu-id="65f96-p101">Normalization rules define how phone numbers expressed in various formats are to be routed for each specified location, user, or contact object. The same dial string may be interpreted and translated differently, depending on the location from which it is dialed and the person or contact object making the call.</span></span>

<div>

## <a name="dial-plan-scope"></a><span data-ttu-id="65f96-107">Ámbito del plan de marcado</span><span class="sxs-lookup"><span data-stu-id="65f96-107">Dial Plan Scope</span></span>

<span data-ttu-id="65f96-108">El *ámbito* de un plan de marcado determina el nivel jerárquico en el que se puede aplicar.</span><span class="sxs-lookup"><span data-stu-id="65f96-108">A dial plan’s *scope* determines the hierarchical level at which the dial plan can be applied.</span></span> <span data-ttu-id="65f96-109">En Lync Server, un usuario puede tener asignado un plan de marcado por usuario específico.</span><span class="sxs-lookup"><span data-stu-id="65f96-109">In Lync Server, a user can be assigned a specific per-user dial plan.</span></span> <span data-ttu-id="65f96-110">Si no se asigna un plan de marcado de usuario, se aplica el plan de marcado de la agrupación de registradores.</span><span class="sxs-lookup"><span data-stu-id="65f96-110">If a user dial plan is not assigned, the Registrar pool dial plan is applied.</span></span> <span data-ttu-id="65f96-111">Si no hay ningún plan de marcado del grupo de registradores, se aplica el plan de marcado del sitio.</span><span class="sxs-lookup"><span data-stu-id="65f96-111">If there is no Registrar pool dial plan, the site dial plan is applied.</span></span> <span data-ttu-id="65f96-112">Por último, si no hay otro plan de marcado aplicable al usuario, se aplica el plan de marcado global.</span><span class="sxs-lookup"><span data-stu-id="65f96-112">Finally, if there is no other dial plan applicable to the user, the global dial plan is applied.</span></span>

<span data-ttu-id="65f96-113">Los clientes obtienen niveles de ámbito del plan de marcado mediante la configuración de aprovisionamiento en banda que se proporciona cuando los usuarios inician sesión en Lync Server.</span><span class="sxs-lookup"><span data-stu-id="65f96-113">Clients obtain dial plan scope levels through in-band provisioning settings that are provided when users log on to Lync Server.</span></span> <span data-ttu-id="65f96-114">Como administrador, puede administrar y asignar niveles de ámbito de plan de marcado mediante el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="65f96-114">As the administrator, you can manage and assign dial plan scope levels by using Lync Server Control Panel.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="65f96-115">El plan de marcado de la puerta de enlace de la red telefónica conmutada (RTC) de nivel de servicio se aplica a las llamadas entrantes de una determinada puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="65f96-115">The service level public switched telephone network (PSTN) gateway dial plan is applied to the incoming calls from a particular gateway.</span></span>



</div>

<span data-ttu-id="65f96-116">Los niveles de ámbito del plan de marcado se definen de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="65f96-116">Dial plan scope levels are defined as follows:</span></span>

  - <span data-ttu-id="65f96-117">**Plan de marcado del usuario:** Puede asignarse a usuarios individuales, grupos o a objetos de contactos.</span><span class="sxs-lookup"><span data-stu-id="65f96-117">**User dial plan:** Can be assigned to individual users, groups, or contact objects.</span></span> <span data-ttu-id="65f96-118">Las aplicaciones de voz pueden buscar un plan de marcado por usuario cuando una llamada se recibe con el contexto telefónico establecido en el predeterminado para el usuario.</span><span class="sxs-lookup"><span data-stu-id="65f96-118">Voice applications can look up a per-user dial plan when a call is received with the phone-context set to user-default.</span></span> <span data-ttu-id="65f96-119">Con el fin de asignar un plan de marcado, un objeto de contacto se considera un usuario individual.</span><span class="sxs-lookup"><span data-stu-id="65f96-119">For the purpose of assigning a dial plan, a contact object is treated as an individual user.</span></span>

  - <span data-ttu-id="65f96-120">**Plan de marcado de Grupo:** Se puede crear en el nivel de servicio para cualquier puerta de enlace o registrador RTC de su topología.</span><span class="sxs-lookup"><span data-stu-id="65f96-120">**Pool dial plan:** Can be created at the service level for any PSTN gateway or Registrar in your topology.</span></span> <span data-ttu-id="65f96-121">Para definir un plan de marcado de grupo, necesitas especificar el servicio (puerta de enlace RTC o grupo de registrador) específico en el que se aplica el plan de marcado.</span><span class="sxs-lookup"><span data-stu-id="65f96-121">To define a pool dial plan, you must specify the particular service (PSTN gateway or Registrar pool) to which the dial plan applies.</span></span>

  - <span data-ttu-id="65f96-122">**Plan de marcado del sitio:** Puede crearse para un sitio completo, excepto para los usuarios, grupos o objetos de contacto a los que se haya asignado un plan de marcado de grupo o un plan de marcado de usuario.</span><span class="sxs-lookup"><span data-stu-id="65f96-122">**Site dial plan:** Can be created for an entire site, except for any users, groups, or contact objects that are assigned a pool dial plan or user dial plan.</span></span> <span data-ttu-id="65f96-123">Para definir un plan de marcado de sitio, necesitas especificar el sitio en el que se aplica el plan de marcado.</span><span class="sxs-lookup"><span data-stu-id="65f96-123">To define a site dial plan, you must specify the site to which the dial plan applies.</span></span>

  - <span data-ttu-id="65f96-124">**Plan de marcado global:** El plan de marcado predeterminado instalado con el producto.</span><span class="sxs-lookup"><span data-stu-id="65f96-124">**Global dial plan:** The default dial plan installed with the product.</span></span> <span data-ttu-id="65f96-125">Puedes editar el plan de marcado global, pero no eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="65f96-125">You can edit the global dial plan, but you cannot delete it.</span></span> <span data-ttu-id="65f96-126">Este plan de marcado se aplica a todos los usuarios, grupos y objetos de contacto de Enterprise Voice de su implementación, a menos que configure y asigne un plan de marcado con un ámbito más específico.</span><span class="sxs-lookup"><span data-stu-id="65f96-126">This dial plan applies to all Enterprise Voice users, groups, and contact objects in your deployment, unless you configure and assign a dial plan with a more specific scope.</span></span>

</div>

<div>

## <a name="planning-for-dial-plans"></a><span data-ttu-id="65f96-127">Planificar planes de marcado</span><span class="sxs-lookup"><span data-stu-id="65f96-127">Planning for Dial Plans</span></span>

<span data-ttu-id="65f96-128">Para planificar un plan de marcado, haz lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="65f96-128">To plan a dial plan, follow these steps:</span></span>

  - <span data-ttu-id="65f96-129">Haz una lista de todas las configuraciones regionales en las que la organización tiene una oficina.</span><span class="sxs-lookup"><span data-stu-id="65f96-129">List all the locales in which your organization has an office.</span></span>
    
    <span data-ttu-id="65f96-p108">La lista necesita estar completa y actualizada. Necesitarás revisarla a medida que evolucione la organización de la compañía. En una compañía multinacional con numerosas sucursales pequeñas, esta tarea puede demandar mucho tiempo.</span><span class="sxs-lookup"><span data-stu-id="65f96-p108">The list must be up-to-date and complete. It will need to be revised as company organization evolves. In a large, multinational company with numerous small branch offices, this can be a time-consuming task.</span></span>

  - <span data-ttu-id="65f96-133">Identifica patrones de números válidos para cada sitio.</span><span class="sxs-lookup"><span data-stu-id="65f96-133">Identify valid number patterns for each site.</span></span>
    
    <span data-ttu-id="65f96-p109">La tarea que más tiempo requiere en el marco de la planificación de los planes de marcado es la identificación de los patrones de números válidos para cada sitio. En algunos casos, se podrán copiar las reglas de normalización escritas para un plan de marcado en otros planes de marcado, sobre todo si los sitios correspondientes están dentro del mismo país o de la misma región, o incluso en el mismo continente. En otros casos, pequeñas modificaciones en los números de un plan de marcado pueden bastar para usarse en otros planes de marcado.</span><span class="sxs-lookup"><span data-stu-id="65f96-p109">The most time-consuming part of planning your dial plans is identifying the valid number patterns for each site. In some cases, you may be able to copy normalization rules that you have written for one dial plan to other dial plans, especially if the corresponding sites are within the same country/region or even continent. In other cases, small changes to numbers in one dial plan may be enough to use them in other dial plans.</span></span>

  - <span data-ttu-id="65f96-137">Desarrolla un esquema aplicable a toda la organización para asignar nombres a los planes de marcado.</span><span class="sxs-lookup"><span data-stu-id="65f96-137">Develop an organization-wide scheme for naming dial plans.</span></span>
    
    <span data-ttu-id="65f96-138">Adoptar un esquema estándar de asignación de nombres asegura la coherencia en toda la organización y facilita los procesos de mantenimiento y actualización.</span><span class="sxs-lookup"><span data-stu-id="65f96-138">Adopting a standard naming scheme assures consistency across an organization and makes maintenance and updates easier.</span></span>

  - <span data-ttu-id="65f96-139">Decide si son necesarios varios planes de marcado para una sola ubicación.</span><span class="sxs-lookup"><span data-stu-id="65f96-139">Decide whether multiple dial plans are required for a single location.</span></span>
    
    <span data-ttu-id="65f96-140">Si su organización mantiene un solo plan de marcado en varias ubicaciones, es posible que aún necesite crear un plan de marcado independiente para los usuarios de telefonía IP empresarial que migren desde una central de conmutación (PBX) y tengan que mantener las extensiones existentes.</span><span class="sxs-lookup"><span data-stu-id="65f96-140">If your organization maintains a single dial plan across multiple locations, you may still need to create a separate dial plan for Enterprise Voice users who are migrating from a private branch exchange (PBX) and who need to have their existing extensions retained.</span></span>

  - <span data-ttu-id="65f96-141">Decide si son necesarios los planes de marcado por usuario.</span><span class="sxs-lookup"><span data-stu-id="65f96-141">Decide whether per-user dial plans are required.</span></span> <span data-ttu-id="65f96-142">Por ejemplo, si tiene usuarios en un sitio de sucursal que están registrados con el sitio central o tiene usuarios registrados en un dispositivo de sucursal con la supervivencia, puede tener en cuenta escenarios especiales de marcado para esos usuarios usando planes de marcado por usuario y reglas de normalización .</span><span class="sxs-lookup"><span data-stu-id="65f96-142">For example, if you have users at a branch site who are registered with the central site or if you have users who are registered on a Survivable Branch Appliance, you can consider special dialing scenarios for such users using per-user dial plans and normalization rules.</span></span> <span data-ttu-id="65f96-143">Para obtener más información, consulte [requisitos de resistencia de sitio de sucursal para Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="65f96-143">For details, see [Branch-site resiliency requirements for Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md).</span></span>

  - <span data-ttu-id="65f96-144">Determina el ámbito del plan de marcado (como ya se ha explicado antes en este tema).</span><span class="sxs-lookup"><span data-stu-id="65f96-144">Determine dial plan scope (as previously described in this topic).</span></span>

<span data-ttu-id="65f96-145">Para crear un plan de marcado, especifique los valores en los siguientes campos, según sea necesario, mediante el panel de control de Lync Server o el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="65f96-145">To create a dial plan, you specify values in the following fields, as required, by using Lync Server Control Panel or Lync Server Management Shell.</span></span>

<div>

## <a name="name-and-simple-name"></a><span data-ttu-id="65f96-146">Nombre y Nombre simple</span><span class="sxs-lookup"><span data-stu-id="65f96-146">Name and Simple Name</span></span>

<span data-ttu-id="65f96-147">En los planes de marcado de usuario necesitas asignar un nombre descriptivo que identifique a los usuarios, grupos u objetos de contacto a los que se asignará el plan de marcado.</span><span class="sxs-lookup"><span data-stu-id="65f96-147">For user dial plans, you should specify a descriptive name that identifies the users, groups, or contact objects to which the dial plan will be assigned.</span></span> <span data-ttu-id="65f96-148">En el caso de los planes de marcado del sitio, el campo nombre se rellena previamente con el nombre del sitio y no se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="65f96-148">For site dial plans, the Name field is prepopulated with the site name and cannot be changed.</span></span> <span data-ttu-id="65f96-149">Para los planes de marcado de grupo, el campo nombre se rellena previamente con el nombre de dominio completo (FQDN) de la puerta de enlace RTC o el grupo de servidores front-end (FQDN) y no se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="65f96-149">For pool dial plans, the Name field is prepopulated with the PSTN gateway or Front End pool fully qualified domain name (FQDN) and cannot be changed.</span></span>

<span data-ttu-id="65f96-150">El *nombre simple* del plan de marcado se rellena previamente con una cadena que se deriva del nombre del plan de marcado.</span><span class="sxs-lookup"><span data-stu-id="65f96-150">The dial plan *Simple Name* is prepopulated with a string that is derived from the dial plan name.</span></span> <span data-ttu-id="65f96-151">El campo Nombre simple puede editarse, para que puedas crear una convención de nomenclatura más descriptiva para tus planes de marcado.</span><span class="sxs-lookup"><span data-stu-id="65f96-151">The Simple Name field is editable, which enables you to create a more descriptive naming convention for your dial plans.</span></span> <span data-ttu-id="65f96-152">El campo *Nombre simple* no puede quedar vacío y necesita ser exclusivo.</span><span class="sxs-lookup"><span data-stu-id="65f96-152">The *Simple Name* value cannot be empty and must be unique.</span></span> <span data-ttu-id="65f96-153">El procedimiento recomendado es desarrollar una convención de nomenclatura para toda la organización y aplicarla con coherencia en todos los sitios y para todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="65f96-153">A best practice is to develop a naming convention for your entire organization and then use this convention consistently across all sites and users.</span></span>

</div>

<div>

## <a name="description"></a><span data-ttu-id="65f96-154">Descripción</span><span class="sxs-lookup"><span data-stu-id="65f96-154">Description</span></span>

<span data-ttu-id="65f96-p113">Recomendamos escribir el nombre común y reconocible de la ubicación geográfica en la que se aplica el plan de marcado correspondiente. Por ejemplo, si el nombre del plan de marcado es Londres.Contoso.com, la descripción recomendada sería Londres.</span><span class="sxs-lookup"><span data-stu-id="65f96-p113">We recommend that you type the common, recognizable name of the geographic location to which the corresponding dial plan applies. For example, if the dial plan name is London.Contoso.com, the recommended description would be London.</span></span>

</div>

<div>

## <a name="dial-in-conferencing-region"></a><span data-ttu-id="65f96-157">Región de conferencia de acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="65f96-157">Dial-in Conferencing Region</span></span>

<span data-ttu-id="65f96-158">Si implementas conferencias de acceso telefónico local, necesitarás especificar una región de conferencias de acceso telefónico local para asociar números de acceso de conferencias de acceso telefónico local con un plan de marcado.</span><span class="sxs-lookup"><span data-stu-id="65f96-158">If you are deploying dial-in conferencing, you will need to specify a dial-in conferencing region to associate dial-in conferencing access numbers with a dial plan.</span></span>

</div>

<div>

## <a name="external-access-prefix"></a><span data-ttu-id="65f96-159">Prefijo de acceso externo</span><span class="sxs-lookup"><span data-stu-id="65f96-159">External Access Prefix</span></span>

<span data-ttu-id="65f96-160">Puede especificar un prefijo de acceso externo de hasta cuatro caracteres (\#, \*y 0-9) si los usuarios necesitan marcar uno o varios dígitos iniciales adicionales (por ejemplo, 9) para obtener una línea externa.</span><span class="sxs-lookup"><span data-stu-id="65f96-160">You can specify an external access prefix of up to four characters (\#, \*, and 0-9) if users need to dial one or more additional leading digits (for example, 9) to get an external line.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="65f96-161">Si especificas un prefijo de acceso externo, no necesitas crear una regla de normalización adicional para incluir el prefijo.</span><span class="sxs-lookup"><span data-stu-id="65f96-161">If you specify an external access prefix, you do not need to create an additional normalization rule to accommodate the prefix.</span></span>



</div>

</div>

</div>

<div>

## <a name="normalization-rules"></a><span data-ttu-id="65f96-162">Reglas de normalización</span><span class="sxs-lookup"><span data-stu-id="65f96-162">Normalization Rules</span></span>

<span data-ttu-id="65f96-p114">Las reglas de normalización definen cómo es el enrutamiento necesario de los números de teléfono expresados en diversos formatos para la ubicación específica. La misma cadena de número se puede interpretar y convertir de manera distinta en función de la configuración regional desde la que se marque. Las reglas de normalización son necesarias para el enrutamiento de las llamadas, ya que los usuarios pueden usar (y usan) diversos formatos al escribir los números de teléfono en sus listas de contactos.</span><span class="sxs-lookup"><span data-stu-id="65f96-p114">Normalization rules define how phone numbers expressed in various formats are to be routed for the named location. The same number string may be interpreted and translated differently, depending on the locale from which it is dialed. Normalization rules are necessary for call routing because users can, and do, use various formats when entering phone numbers in their Contacts lists.</span></span>

<span data-ttu-id="65f96-166">La normalización de los números de teléfono proporcionados por los usuarios aporta un formato uniforme que facilita las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="65f96-166">Normalizing user-supplied phone numbers provides a consistent format that facilitates the following tasks:</span></span>

  - <span data-ttu-id="65f96-167">Asociar un número marcado al URI del SIP del destinatario.</span><span class="sxs-lookup"><span data-stu-id="65f96-167">Match a dialed number to the intended recipient’s SIP-URI.</span></span>

  - <span data-ttu-id="65f96-168">Aplicar las reglas de autorización de marcado al usuario que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="65f96-168">Apply dialing authorization rules to the calling party.</span></span>

<span data-ttu-id="65f96-169">Los siguientes campos numéricos se incluyen entre los que necesitan considerar las reglas de normalización:</span><span class="sxs-lookup"><span data-stu-id="65f96-169">The following number fields are among those that your normalization rules may need to account for:</span></span>

  - <span data-ttu-id="65f96-170">Plan de marcado</span><span class="sxs-lookup"><span data-stu-id="65f96-170">Dial plan</span></span>

  - <span data-ttu-id="65f96-171">Código de país</span><span class="sxs-lookup"><span data-stu-id="65f96-171">Country code</span></span>

  - <span data-ttu-id="65f96-172">Código de área</span><span class="sxs-lookup"><span data-stu-id="65f96-172">Area code</span></span>

  - <span data-ttu-id="65f96-173">Longitud de extensión</span><span class="sxs-lookup"><span data-stu-id="65f96-173">Length of extension</span></span>

  - <span data-ttu-id="65f96-174">Prefijo de sitio</span><span class="sxs-lookup"><span data-stu-id="65f96-174">Site prefix</span></span>

<div>

## <a name="creating-normalization-rules"></a><span data-ttu-id="65f96-175">Crear reglas de normalización</span><span class="sxs-lookup"><span data-stu-id="65f96-175">Creating Normalization Rules</span></span>

<span data-ttu-id="65f96-176">Las reglas de normalización usan expresiones regulares de .NET Framework para especificar patrones numéricos coincidentes que el servidor utiliza para convertir las cadenas de marcado a formato E.164 con el fin de realizar búsquedas inversas de números.</span><span class="sxs-lookup"><span data-stu-id="65f96-176">Normalization rules use .NET Framework regular expressions to specify numeric match patterns that the server uses to translate dial strings to E.164 format for the purpose of performing reverse number lookup.</span></span> <span data-ttu-id="65f96-177">Puede crear reglas de normalización en el panel de control de Lync Server, ya sea introduciendo las expresiones manualmente, o bien especificando los dígitos iniciales y la longitud de las cadenas de marcado que deben coincidir y que el panel de control de Lync Server genere el correspondiente expresión regular para usted.</span><span class="sxs-lookup"><span data-stu-id="65f96-177">You create normalization rules in the Lync Server Control Panel either by entering the expressions manually, or by entering the starting digits and the length of the dial strings to be matched and letting the Lync Server Control Panel generate the corresponding regular expression for you.</span></span> <span data-ttu-id="65f96-178">Sea como fuere, al finalizar puedes especificar un número de prueba para comprobar que la regla de normalización funciona según lo previsto.</span><span class="sxs-lookup"><span data-stu-id="65f96-178">Either way, when you finish, you can enter a test number to verify that the normalization rule works as expected.</span></span>

<span data-ttu-id="65f96-179">Para obtener información detallada sobre el uso de expresiones regulares de .NET Framework, vea "expresiones [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927)regulares de .NET Framework" en.</span><span class="sxs-lookup"><span data-stu-id="65f96-179">For details about using .NET Framework regular expressions, see ".NET Framework Regular Expressions" at [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927).</span></span>

</div>

<span id="BKMK_SampleNormalizationRules"></span>

<div>

## <a name="sample-normalization-rules"></a><span data-ttu-id="65f96-180">Reglas de normalización de ejemplo</span><span class="sxs-lookup"><span data-stu-id="65f96-180">Sample Normalization Rules</span></span>

<span data-ttu-id="65f96-p116">En la siguiente tabla se muestran ejemplos de reglas de normalización escritas como expresiones regulares de .NET Framework. Son solo ejemplos, no una referencia normativa para crear reglas de normalización.</span><span class="sxs-lookup"><span data-stu-id="65f96-p116">The following table shows sample normalization rules that are written as .NET Framework regular expressions. The samples are examples only and are not meant to be a prescriptive reference for creating your own normalization rules.</span></span>

### <a name="table-1normalization-rules-using-net-framework-regular-expressions"></a><span data-ttu-id="65f96-183">Tabla 1. Reglas de normalización que usan expresiones regulares de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="65f96-183">Table 1.Normalization Rules Using .NET Framework Regular Expressions</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="65f96-184">Nombre de la regla</span><span class="sxs-lookup"><span data-stu-id="65f96-184">Rule name</span></span></th>
<th><span data-ttu-id="65f96-185">Descripción</span><span class="sxs-lookup"><span data-stu-id="65f96-185">Description</span></span></th>
<th><span data-ttu-id="65f96-186">Patrón de números</span><span class="sxs-lookup"><span data-stu-id="65f96-186">Number pattern</span></span></th>
<th><span data-ttu-id="65f96-187">Conversión</span><span class="sxs-lookup"><span data-stu-id="65f96-187">Translation</span></span></th>
<th><span data-ttu-id="65f96-188">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="65f96-188">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="65f96-189">4digitExtension</span><span class="sxs-lookup"><span data-stu-id="65f96-189">4digitExtension</span></span></p></td>
<td><p><span data-ttu-id="65f96-190">Convierte extensiones de 4 dígitos</span><span class="sxs-lookup"><span data-stu-id="65f96-190">Translates 4-digit extensions</span></span></p></td>
<td><p><span data-ttu-id="65f96-191">^ (\d{4}) $</span><span class="sxs-lookup"><span data-stu-id="65f96-191">^(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="65f96-192">+1425555$1</span><span class="sxs-lookup"><span data-stu-id="65f96-192">+1425555$1</span></span></p></td>
<td><p><span data-ttu-id="65f96-193">0100 se traduce a +14255550100</span><span class="sxs-lookup"><span data-stu-id="65f96-193">0100 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65f96-194">5digitExtension</span><span class="sxs-lookup"><span data-stu-id="65f96-194">5digitExtension</span></span></p></td>
<td><p><span data-ttu-id="65f96-195">Convierte extensiones de 5 dígitos</span><span class="sxs-lookup"><span data-stu-id="65f96-195">Translates 5-digit extensions</span></span></p></td>
<td><p><span data-ttu-id="65f96-196">^ 5 (\d{4}) $</span><span class="sxs-lookup"><span data-stu-id="65f96-196">^5(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="65f96-197">+1425555$1</span><span class="sxs-lookup"><span data-stu-id="65f96-197">+1425555$1</span></span></p></td>
<td><p><span data-ttu-id="65f96-198">50100 se traduce a +14255550100</span><span class="sxs-lookup"><span data-stu-id="65f96-198">50100 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="65f96-199">7digitcallingRedmond</span><span class="sxs-lookup"><span data-stu-id="65f96-199">7digitcallingRedmond</span></span></p></td>
<td><p><span data-ttu-id="65f96-200">Convierte números de 7 dígitos en números locales de Redmond</span><span class="sxs-lookup"><span data-stu-id="65f96-200">Translates 7-digit numbers to Redmond local numbers</span></span></p></td>
<td><p><span data-ttu-id="65f96-201">^ (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="65f96-201">^(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="65f96-202">+1425$1</span><span class="sxs-lookup"><span data-stu-id="65f96-202">+1425$1</span></span></p></td>
<td><p><span data-ttu-id="65f96-203">5550100 se convierte en +14255550100</span><span class="sxs-lookup"><span data-stu-id="65f96-203">5550100 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65f96-204">7digitcallingDallas</span><span class="sxs-lookup"><span data-stu-id="65f96-204">7digitcallingDallas</span></span></p></td>
<td><p><span data-ttu-id="65f96-205">Convierte números de 7 dígitos en números locales de Dallas</span><span class="sxs-lookup"><span data-stu-id="65f96-205">Translates 7-digit numbers to Dallas local numbers</span></span></p></td>
<td><p><span data-ttu-id="65f96-206">^ (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="65f96-206">^(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="65f96-207">+1972$1</span><span class="sxs-lookup"><span data-stu-id="65f96-207">+1972$1</span></span></p></td>
<td><p><span data-ttu-id="65f96-208">5550100 se convierte en +19725550100</span><span class="sxs-lookup"><span data-stu-id="65f96-208">5550100 is translated to +19725550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="65f96-209">10digitcallingUS</span><span class="sxs-lookup"><span data-stu-id="65f96-209">10digitcallingUS</span></span></p></td>
<td><p><span data-ttu-id="65f96-210">Convierte números de 10 dígitos de Estados Unidos</span><span class="sxs-lookup"><span data-stu-id="65f96-210">Translates 10-digit numbers in the United States</span></span></p></td>
<td><p><span data-ttu-id="65f96-211">^ (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="65f96-211">^(\d{10})$</span></span></p></td>
<td><p><span data-ttu-id="65f96-212">+1$1</span><span class="sxs-lookup"><span data-stu-id="65f96-212">+1$1</span></span></p></td>
<td><p><span data-ttu-id="65f96-213">2065550100 se convierte en +12065550100</span><span class="sxs-lookup"><span data-stu-id="65f96-213">2065550100 is translated to +12065550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65f96-214">LDCallingUS</span><span class="sxs-lookup"><span data-stu-id="65f96-214">LDCallingUS</span></span></p></td>
<td><p><span data-ttu-id="65f96-215">Convierte los números con prefijos de larga distancia de Estados Unidos</span><span class="sxs-lookup"><span data-stu-id="65f96-215">Translates numbers with long distance prefixes in the United States</span></span></p></td>
<td><p><span data-ttu-id="65f96-216">^ 1 (\d{10}) $</span><span class="sxs-lookup"><span data-stu-id="65f96-216">^1(\d{10})$</span></span></p></td>
<td><p><span data-ttu-id="65f96-217">+$1</span><span class="sxs-lookup"><span data-stu-id="65f96-217">+$1</span></span></p></td>
<td><p><span data-ttu-id="65f96-218">12145550100 se convierte en +2145550100</span><span class="sxs-lookup"><span data-stu-id="65f96-218">12145550100 is translated to +2145550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="65f96-219">IntlCallingUS</span><span class="sxs-lookup"><span data-stu-id="65f96-219">IntlCallingUS</span></span></p></td>
<td><p><span data-ttu-id="65f96-220">Convierte los números con prefijos internacionales de Estados Unidos</span><span class="sxs-lookup"><span data-stu-id="65f96-220">Translates numbers with international prefixes in the United States</span></span></p></td>
<td><p><span data-ttu-id="65f96-221">^011(\d\*)$</span><span class="sxs-lookup"><span data-stu-id="65f96-221">^011(\d\*)$</span></span></p></td>
<td><p><span data-ttu-id="65f96-222">+$1</span><span class="sxs-lookup"><span data-stu-id="65f96-222">+$1</span></span></p></td>
<td><p><span data-ttu-id="65f96-223">01191445550100 se convierte en +91445550100</span><span class="sxs-lookup"><span data-stu-id="65f96-223">01191445550100 is translated to +91445550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65f96-224">RedmondOperator</span><span class="sxs-lookup"><span data-stu-id="65f96-224">RedmondOperator</span></span></p></td>
<td><p><span data-ttu-id="65f96-225">Convierte 0 al operador de Redmond</span><span class="sxs-lookup"><span data-stu-id="65f96-225">Translates 0 to Redmond Operator</span></span></p></td>
<td><p><span data-ttu-id="65f96-226">^0$</span><span class="sxs-lookup"><span data-stu-id="65f96-226">^0$</span></span></p></td>
<td><p><span data-ttu-id="65f96-227">+14255550100</span><span class="sxs-lookup"><span data-stu-id="65f96-227">+14255550100</span></span></p></td>
<td><p><span data-ttu-id="65f96-228">0 se traduce a +14255550100</span><span class="sxs-lookup"><span data-stu-id="65f96-228">0 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="65f96-229">RedmondSitePrefix</span><span class="sxs-lookup"><span data-stu-id="65f96-229">RedmondSitePrefix</span></span></p></td>
<td><p><span data-ttu-id="65f96-230">Convierte los números con prefijo de red (6) y prefijo de sitio de Redmond (222)</span><span class="sxs-lookup"><span data-stu-id="65f96-230">Translates numbers with on-net prefix (6) and Redmond site code (222)</span></span></p></td>
<td><p><span data-ttu-id="65f96-231">^ 6222 (\d{4}) $</span><span class="sxs-lookup"><span data-stu-id="65f96-231">^6222(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="65f96-232">+1425555$1</span><span class="sxs-lookup"><span data-stu-id="65f96-232">+1425555$1</span></span></p></td>
<td><p><span data-ttu-id="65f96-233">62220100 se convierte en +14255550100</span><span class="sxs-lookup"><span data-stu-id="65f96-233">62220100 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65f96-234">NYSitePrefix</span><span class="sxs-lookup"><span data-stu-id="65f96-234">NYSitePrefix</span></span></p></td>
<td><p><span data-ttu-id="65f96-235">Convierte los números con prefijo de red (6) y prefijo de sitio de Nueva York (333)</span><span class="sxs-lookup"><span data-stu-id="65f96-235">Translates numbers with on-net prefix (6) and NY site code (333)</span></span></p></td>
<td><p><span data-ttu-id="65f96-236">^ 6333 (\d{4}) $</span><span class="sxs-lookup"><span data-stu-id="65f96-236">^6333(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="65f96-237">+1202555$1</span><span class="sxs-lookup"><span data-stu-id="65f96-237">+1202555$1</span></span></p></td>
<td><p><span data-ttu-id="65f96-238">63330100 se convierte en +12025550100</span><span class="sxs-lookup"><span data-stu-id="65f96-238">63330100 is translated to +12025550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="65f96-239">DallasSitePrefix</span><span class="sxs-lookup"><span data-stu-id="65f96-239">DallasSitePrefix</span></span></p></td>
<td><p><span data-ttu-id="65f96-240">Convierte los números con prefijo de red (6) y prefijo de sitio de Dallas (444)</span><span class="sxs-lookup"><span data-stu-id="65f96-240">Translates numbers with on-net prefix (6) and Dallas site code (444)</span></span></p></td>
<td><p><span data-ttu-id="65f96-241">^ 6444 (\d{4}) $</span><span class="sxs-lookup"><span data-stu-id="65f96-241">^6444(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="65f96-242">+1972555$1</span><span class="sxs-lookup"><span data-stu-id="65f96-242">+1972555$1</span></span></p></td>
<td><p><span data-ttu-id="65f96-243">64440100 se convierte en +19725550100</span><span class="sxs-lookup"><span data-stu-id="65f96-243">64440100 is translated to +19725550100</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="65f96-244">En la tabla siguiente se muestra un plan de marcado de ejemplo para Redmond, Washington, Estados Unidos, basado en las reglas de normalización que se muestran en la tabla anterior.</span><span class="sxs-lookup"><span data-stu-id="65f96-244">The following table illustrates a sample dial plan for Redmond, Washington, United States, based on the normalization rules shown in the previous table.</span></span>

### <a name="table-2-redmond-dial-plan-based-on-normalization-rules-shown-in-table-1"></a><span data-ttu-id="65f96-p117">Tabla 2. Plan de marcado de Redmond basado en las reglas de normalización mostradas en la tabla 1</span><span class="sxs-lookup"><span data-stu-id="65f96-p117">Table 2. Redmond Dial Plan Based on Normalization Rules Shown in Table 1</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="65f96-247">Redmond.forestFQDN</span><span class="sxs-lookup"><span data-stu-id="65f96-247">Redmond.forestFQDN</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="65f96-248">5digitExtension</span><span class="sxs-lookup"><span data-stu-id="65f96-248">5digitExtension</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65f96-249">7digitcallingRedmond</span><span class="sxs-lookup"><span data-stu-id="65f96-249">7digitcallingRedmond</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="65f96-250">10digitcallingUS</span><span class="sxs-lookup"><span data-stu-id="65f96-250">10digitcallingUS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65f96-251">IntlCallingUS</span><span class="sxs-lookup"><span data-stu-id="65f96-251">IntlCallingUS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="65f96-252">RedmondSitePrefix</span><span class="sxs-lookup"><span data-stu-id="65f96-252">RedmondSitePrefix</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65f96-253">NYSitePrefix</span><span class="sxs-lookup"><span data-stu-id="65f96-253">NYSitePrefix</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="65f96-254">DallasSitePrefix</span><span class="sxs-lookup"><span data-stu-id="65f96-254">DallasSitePrefix</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="65f96-255">RedmondOperator</span><span class="sxs-lookup"><span data-stu-id="65f96-255">RedmondOperator</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="65f96-p118">Los nombres de las reglas de normalización que se muestran en la tabla anterior no incluyen espacios, pero esto es opcional. Por ejemplo, el primer nombre de la tabla podría haberse escrito como "extensión de 5 dígitos" o "Extensión de 5 dígitos" y ser igualmente válido.</span><span class="sxs-lookup"><span data-stu-id="65f96-p118">The normalization rules names shown in the preceding table do not include spaces, but this is a matter of choice. The first name in the table, for example, could have been written "5 digit extension" or "5-digit Extension" and still be valid.</span></span>



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

