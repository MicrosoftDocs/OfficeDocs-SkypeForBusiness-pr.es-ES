---
title: 'Lync Server 2013: planes de marcado y reglas de normalización'
description: 'Lync Server 2013: planes de marcado y reglas de normalización.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dial plans and normalization rules
ms:assetid: fde45195-6eb4-403c-9094-57df7fc0bd2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413082(v=OCS.15)
ms:contentKeyID: 48185960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0341d0c5267a2272ff45bd93408b2bd14f0ceeaa
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559746"
---
# <a name="dial-plans-and-normalization-rules-in-lync-server-2013"></a><span data-ttu-id="8be5e-103">Planes de marcado y reglas de normalización en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8be5e-103">Dial plans and normalization rules in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8be5e-104">_**Última modificación del tema:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="8be5e-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="8be5e-105">Un plan de marcado es un conjunto de reglas de normalización especificado por el usuario que convierte números de teléfono para una ubicación especificada por el usuario, un usuario individual o un objeto de contacto a un formato estándar único (E.164) con fines de autorización telefónica y enrutamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="8be5e-105">A dial plan is a named set of normalization rules that translates phone numbers for a named location, individual user, or contact object into a single standard (E.164) format for purposes of phone authorization and call routing.</span></span>

<span data-ttu-id="8be5e-106">Las reglas de normalización definen la forma en que los números de teléfono expresados en diversos formatos se van a enrutar en cada ubicación, usuario u objeto de contacto que se haya especificado.</span><span class="sxs-lookup"><span data-stu-id="8be5e-106">Normalization rules define how phone numbers expressed in various formats are to be routed for each specified location, user, or contact object.</span></span> <span data-ttu-id="8be5e-107">La misma cadena de marcado se puede interpretar y convertir de manera diferente, en función de la ubicación desde la que se marque y de la persona o el objeto de contacto que realice la llamada.</span><span class="sxs-lookup"><span data-stu-id="8be5e-107">The same dial string may be interpreted and translated differently, depending on the location from which it is dialed and the person or contact object making the call.</span></span>

<div>

## <a name="dial-plan-scope"></a><span data-ttu-id="8be5e-108">Ámbito del plan de marcado</span><span class="sxs-lookup"><span data-stu-id="8be5e-108">Dial Plan Scope</span></span>

<span data-ttu-id="8be5e-109">El *ámbito* de un plan de marcado determina el nivel jerárquico en el que se puede aplicar el plan de marcado.</span><span class="sxs-lookup"><span data-stu-id="8be5e-109">A dial plan’s *scope* determines the hierarchical level at which the dial plan can be applied.</span></span> <span data-ttu-id="8be5e-110">En Lync Server, a un usuario se le puede asignar un plan de marcado por usuario específico.</span><span class="sxs-lookup"><span data-stu-id="8be5e-110">In Lync Server, a user can be assigned a specific per-user dial plan.</span></span> <span data-ttu-id="8be5e-111">Si no se asigna un plan de marcado de usuario, se aplica el plan de marcado de grupo de registrador.</span><span class="sxs-lookup"><span data-stu-id="8be5e-111">If a user dial plan is not assigned, the Registrar pool dial plan is applied.</span></span> <span data-ttu-id="8be5e-112">Si no hay un plan de marcado de grupo de registrador, se aplica el plan de marcado de sitio.</span><span class="sxs-lookup"><span data-stu-id="8be5e-112">If there is no Registrar pool dial plan, the site dial plan is applied.</span></span> <span data-ttu-id="8be5e-113">Por último, si no hay otro plan de marcado aplicable al usuario, se aplica el plan de marcado global.</span><span class="sxs-lookup"><span data-stu-id="8be5e-113">Finally, if there is no other dial plan applicable to the user, the global dial plan is applied.</span></span>

<span data-ttu-id="8be5e-114">Los clientes obtienen niveles de ámbito del plan de marcado mediante la configuración de aprovisionamiento en banda que se proporciona cuando los usuarios inician sesión en Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8be5e-114">Clients obtain dial plan scope levels through in-band provisioning settings that are provided when users log on to Lync Server.</span></span> <span data-ttu-id="8be5e-115">Como administrador, puede administrar y asignar niveles de ámbito del plan de marcado mediante el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8be5e-115">As the administrator, you can manage and assign dial plan scope levels by using Lync Server Control Panel.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8be5e-116">El plan de marcado de puerta de enlace de red telefónica conmutada (RTC) de nivel de servicio se aplica a las llamadas entrantes de una puerta de enlace concreta.</span><span class="sxs-lookup"><span data-stu-id="8be5e-116">The service level public switched telephone network (PSTN) gateway dial plan is applied to the incoming calls from a particular gateway.</span></span>



</div>

<span data-ttu-id="8be5e-117">Los niveles de ámbito de plan de marcado se definen de la manera siguiente:</span><span class="sxs-lookup"><span data-stu-id="8be5e-117">Dial plan scope levels are defined as follows:</span></span>

  - <span data-ttu-id="8be5e-118">**Plan de marcado de usuario:** Se puede asignar a usuarios individuales, grupos o a objetos de contacto.</span><span class="sxs-lookup"><span data-stu-id="8be5e-118">**User dial plan:** Can be assigned to individual users, groups, or contact objects.</span></span> <span data-ttu-id="8be5e-119">Las aplicaciones de voz pueden buscar un plan de marcado por usuario cuando se recibe una llamada con el contexto de teléfono establecido en el predeterminado del usuario.</span><span class="sxs-lookup"><span data-stu-id="8be5e-119">Voice applications can look up a per-user dial plan when a call is received with the phone-context set to user-default.</span></span> <span data-ttu-id="8be5e-120">Con el fin de asignar un plan de marcado, un objeto de contacto se considera un usuario individual.</span><span class="sxs-lookup"><span data-stu-id="8be5e-120">For the purpose of assigning a dial plan, a contact object is treated as an individual user.</span></span>

  - <span data-ttu-id="8be5e-121">**Plan de marcado del Grupo:** Se pueden crear en el nivel de servicio de cualquier puerta de enlace RTC o registrador de la topología.</span><span class="sxs-lookup"><span data-stu-id="8be5e-121">**Pool dial plan:** Can be created at the service level for any PSTN gateway or Registrar in your topology.</span></span> <span data-ttu-id="8be5e-122">Para definir un plan de marcado de grupo, debe especificarse el servicio (puerta de enlace de RTC o grupo de registrador) en el que se aplica el plan de marcado.</span><span class="sxs-lookup"><span data-stu-id="8be5e-122">To define a pool dial plan, you must specify the particular service (PSTN gateway or Registrar pool) to which the dial plan applies.</span></span>

  - <span data-ttu-id="8be5e-123">**Plan de marcado de sitio:** Se puede crear para un sitio completo, excepto para los usuarios, grupos o objetos de contacto a los que se haya asignado un plan de marcado de grupo o de usuario.</span><span class="sxs-lookup"><span data-stu-id="8be5e-123">**Site dial plan:** Can be created for an entire site, except for any users, groups, or contact objects that are assigned a pool dial plan or user dial plan.</span></span> <span data-ttu-id="8be5e-124">Para definir un plan de marcado de sitio, debe especificar el sitio en el que se aplica el plan de marcado.</span><span class="sxs-lookup"><span data-stu-id="8be5e-124">To define a site dial plan, you must specify the site to which the dial plan applies.</span></span>

  - <span data-ttu-id="8be5e-125">**Plan de marcado global:** El plan de marcado predeterminado instalado con el producto.</span><span class="sxs-lookup"><span data-stu-id="8be5e-125">**Global dial plan:** The default dial plan installed with the product.</span></span> <span data-ttu-id="8be5e-126">El plan de marcado global puede editarse, pero no eliminarse.</span><span class="sxs-lookup"><span data-stu-id="8be5e-126">You can edit the global dial plan, but you cannot delete it.</span></span> <span data-ttu-id="8be5e-127">Este plan de marcado se aplica a todos los usuarios, grupos y objetos de contacto de Enterprise Voice en su implementación, a menos que configure y asigne un plan de marcado con un ámbito más específico.</span><span class="sxs-lookup"><span data-stu-id="8be5e-127">This dial plan applies to all Enterprise Voice users, groups, and contact objects in your deployment, unless you configure and assign a dial plan with a more specific scope.</span></span>

</div>

<div>

## <a name="planning-for-dial-plans"></a><span data-ttu-id="8be5e-128">Planeación de planes de marcado</span><span class="sxs-lookup"><span data-stu-id="8be5e-128">Planning for Dial Plans</span></span>

<span data-ttu-id="8be5e-129">Para planear un plan de marcado, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="8be5e-129">To plan a dial plan, follow these steps:</span></span>

  - <span data-ttu-id="8be5e-130">Enumera todas las configuraciones regionales en las que la organización tiene una oficina.</span><span class="sxs-lookup"><span data-stu-id="8be5e-130">List all the locales in which your organization has an office.</span></span>
    
    <span data-ttu-id="8be5e-131">La lista debe estar actualizada y completa.</span><span class="sxs-lookup"><span data-stu-id="8be5e-131">The list must be up-to-date and complete.</span></span> <span data-ttu-id="8be5e-132">Deberá revisarse a medida que evolucione la compañía.</span><span class="sxs-lookup"><span data-stu-id="8be5e-132">It will need to be revised as company organization evolves.</span></span> <span data-ttu-id="8be5e-133">En una gran empresa multinacional con numerosas pequeñas sucursales, esta tarea puede llevar mucho tiempo.</span><span class="sxs-lookup"><span data-stu-id="8be5e-133">In a large, multinational company with numerous small branch offices, this can be a time-consuming task.</span></span>

  - <span data-ttu-id="8be5e-134">Identificar patrones de números válidos para cada sitio.</span><span class="sxs-lookup"><span data-stu-id="8be5e-134">Identify valid number patterns for each site.</span></span>
    
    <span data-ttu-id="8be5e-p109">La tarea que más tiempo requiere en el marco de la planeación de los planes de marcado es la identificación de los modelos de número válidos para cada sitio. En algunos casos, se podrán copiar en otros planes de marcado las reglas de normalización escritas para un plan de marcado, sobre todo si los sitios correspondientes están dentro del mismo país o región o incluso en el mismo continente. En otros casos, pequeñas modificaciones en los números de un plan de marcado pueden bastar para usarse en otros planes de marcado.</span><span class="sxs-lookup"><span data-stu-id="8be5e-p109">The most time-consuming part of planning your dial plans is identifying the valid number patterns for each site. In some cases, you may be able to copy normalization rules that you have written for one dial plan to other dial plans, especially if the corresponding sites are within the same country/region or even continent. In other cases, small changes to numbers in one dial plan may be enough to use them in other dial plans.</span></span>

  - <span data-ttu-id="8be5e-138">Desarrollar un esquema de organización para la asignación de nombres a los planes de marcado.</span><span class="sxs-lookup"><span data-stu-id="8be5e-138">Develop an organization-wide scheme for naming dial plans.</span></span>
    
    <span data-ttu-id="8be5e-139">Adoptar un esquema estándar de asignación de nombres asegura la coherencia en toda la organización y facilita los procesos de mantenimiento y actualización.</span><span class="sxs-lookup"><span data-stu-id="8be5e-139">Adopting a standard naming scheme assures consistency across an organization and makes maintenance and updates easier.</span></span>

  - <span data-ttu-id="8be5e-140">Decida si se requieren varios planes de marcado para una sola ubicación.</span><span class="sxs-lookup"><span data-stu-id="8be5e-140">Decide whether multiple dial plans are required for a single location.</span></span>
    
    <span data-ttu-id="8be5e-141">Si su organización mantiene un solo plan de marcado en varias ubicaciones, es posible que tenga que crear un plan de marcado independiente para los usuarios de Enterprise Voice que migren desde una central de conmutación (PBX) y que necesiten mantener sus extensiones existentes.</span><span class="sxs-lookup"><span data-stu-id="8be5e-141">If your organization maintains a single dial plan across multiple locations, you may still need to create a separate dial plan for Enterprise Voice users who are migrating from a private branch exchange (PBX) and who need to have their existing extensions retained.</span></span>

  - <span data-ttu-id="8be5e-142">Decida si los planes de marcado por usuario son necesarios.</span><span class="sxs-lookup"><span data-stu-id="8be5e-142">Decide whether per-user dial plans are required.</span></span> <span data-ttu-id="8be5e-143">Por ejemplo, si tiene usuarios en un sitio de sucursal que están registrados en el sitio central o si tiene usuarios registrados en una aplicación de sucursal con funciones de supervivencia, puede considerar escenarios especiales de marcado para los usuarios con planes de marcado y reglas de normalización por usuario.</span><span class="sxs-lookup"><span data-stu-id="8be5e-143">For example, if you have users at a branch site who are registered with the central site or if you have users who are registered on a Survivable Branch Appliance, you can consider special dialing scenarios for such users using per-user dial plans and normalization rules.</span></span> <span data-ttu-id="8be5e-144">Para obtener información detallada, consulte [Branch-site Resiliency Requirements for Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8be5e-144">For details, see [Branch-site resiliency requirements for Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md).</span></span>

  - <span data-ttu-id="8be5e-145">Determine el ámbito del plan de marcado (como se describió anteriormente en este tema).</span><span class="sxs-lookup"><span data-stu-id="8be5e-145">Determine dial plan scope (as previously described in this topic).</span></span>

<span data-ttu-id="8be5e-146">Para crear un plan de marcado, especifique valores en los campos siguientes, según sea necesario, mediante el panel de control de Lync Server o el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8be5e-146">To create a dial plan, you specify values in the following fields, as required, by using Lync Server Control Panel or Lync Server Management Shell.</span></span>

<div>

## <a name="name-and-simple-name"></a><span data-ttu-id="8be5e-147">Nombre y Nombre simple</span><span class="sxs-lookup"><span data-stu-id="8be5e-147">Name and Simple Name</span></span>

<span data-ttu-id="8be5e-148">Para los planes de marcado de los usuarios, debe especificar un nombre descriptivo que identifique los usuarios, los grupos o los objetos de contacto a los que se asignará el plan de marcado.</span><span class="sxs-lookup"><span data-stu-id="8be5e-148">For user dial plans, you should specify a descriptive name that identifies the users, groups, or contact objects to which the dial plan will be assigned.</span></span> <span data-ttu-id="8be5e-149">En el caso de planes de marcado de sitio, el campo Nombre se rellena previamente con el nombre del sitio y no se puede modificar.</span><span class="sxs-lookup"><span data-stu-id="8be5e-149">For site dial plans, the Name field is prepopulated with the site name and cannot be changed.</span></span> <span data-ttu-id="8be5e-150">Para los planes de marcado de grupo, el campo nombre se rellena previamente con el nombre de dominio completo (FQDN) del grupo de servidores front-end o la puerta de enlace RTC, y no se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="8be5e-150">For pool dial plans, the Name field is prepopulated with the PSTN gateway or Front End pool fully qualified domain name (FQDN) and cannot be changed.</span></span>

<span data-ttu-id="8be5e-151">El *nombre simple* del plan de marcado se rellena previamente con una cadena que se deriva del nombre del plan de marcado.</span><span class="sxs-lookup"><span data-stu-id="8be5e-151">The dial plan *Simple Name* is prepopulated with a string that is derived from the dial plan name.</span></span> <span data-ttu-id="8be5e-152">El campo nombre simple es editable, lo que le permite crear una Convención de nomenclatura más descriptiva para los planes de marcado.</span><span class="sxs-lookup"><span data-stu-id="8be5e-152">The Simple Name field is editable, which enables you to create a more descriptive naming convention for your dial plans.</span></span> <span data-ttu-id="8be5e-153">El valor del *nombre simple* no puede estar vacío y debe ser único.</span><span class="sxs-lookup"><span data-stu-id="8be5e-153">The *Simple Name* value cannot be empty and must be unique.</span></span> <span data-ttu-id="8be5e-154">Un procedimiento recomendado es desarrollar una Convención de nomenclatura para toda la organización y, a continuación, usar esta Convención de forma coherente en todos los sitios y usuarios.</span><span class="sxs-lookup"><span data-stu-id="8be5e-154">A best practice is to develop a naming convention for your entire organization and then use this convention consistently across all sites and users.</span></span>

</div>

<div>

## <a name="description"></a><span data-ttu-id="8be5e-155">Descripción</span><span class="sxs-lookup"><span data-stu-id="8be5e-155">Description</span></span>

<span data-ttu-id="8be5e-p113">Se recomienda escribir el nombre común y reconocible de la ubicación geográfica en la que se aplica el plan de marcado correspondiente. Por ejemplo, si el nombre del plan de marcado es Londres.Contoso.com, la descripción recomendada es Londres.</span><span class="sxs-lookup"><span data-stu-id="8be5e-p113">We recommend that you type the common, recognizable name of the geographic location to which the corresponding dial plan applies. For example, if the dial plan name is London.Contoso.com, the recommended description would be London.</span></span>

</div>

<div>

## <a name="dial-in-conferencing-region"></a><span data-ttu-id="8be5e-158">Región de conferencia de acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="8be5e-158">Dial-in Conferencing Region</span></span>

<span data-ttu-id="8be5e-159">Si se implementan conferencias de acceso telefónico local, debe especificarse una región de conferencias de acceso telefónico local para asociar números de acceso de conferencias de acceso telefónico local con un plan de marcado.</span><span class="sxs-lookup"><span data-stu-id="8be5e-159">If you are deploying dial-in conferencing, you will need to specify a dial-in conferencing region to associate dial-in conferencing access numbers with a dial plan.</span></span>

</div>

<div>

## <a name="external-access-prefix"></a><span data-ttu-id="8be5e-160">Prefijo de acceso externo</span><span class="sxs-lookup"><span data-stu-id="8be5e-160">External Access Prefix</span></span>

<span data-ttu-id="8be5e-161">Puede especificar un prefijo de acceso externo de hasta cuatro caracteres ( \# , \* y 0-9) si los usuarios necesitan marcar uno o más dígitos iniciales adicionales (por ejemplo, 9) para obtener una línea externa.</span><span class="sxs-lookup"><span data-stu-id="8be5e-161">You can specify an external access prefix of up to four characters (\#, \*, and 0-9) if users need to dial one or more additional leading digits (for example, 9) to get an external line.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8be5e-162">Si especifica un prefijo de acceso externo, no necesita crear otra regla de normalización para incluir el prefijo.</span><span class="sxs-lookup"><span data-stu-id="8be5e-162">If you specify an external access prefix, you do not need to create an additional normalization rule to accommodate the prefix.</span></span>



</div>

</div>

</div>

<div>

## <a name="normalization-rules"></a><span data-ttu-id="8be5e-163">Reglas de normalización</span><span class="sxs-lookup"><span data-stu-id="8be5e-163">Normalization Rules</span></span>

<span data-ttu-id="8be5e-164">Las reglas de normalización definen cómo deben enrutarse los números de teléfono expresados en diversos formatos para la ubicación con nombre.</span><span class="sxs-lookup"><span data-stu-id="8be5e-164">Normalization rules define how phone numbers expressed in various formats are to be routed for the named location.</span></span> <span data-ttu-id="8be5e-165">La misma cadena de números puede interpretarse y traducirse de forma diferente, dependiendo de la configuración regional desde la que se marque.</span><span class="sxs-lookup"><span data-stu-id="8be5e-165">The same number string may be interpreted and translated differently, depending on the locale from which it is dialed.</span></span> <span data-ttu-id="8be5e-166">Las reglas de normalización son necesarias para el enrutamiento y la autorización de las llamadas, ya que los usuarios pueden usar (y usan) diversos formatos al escribir los números de teléfono en sus listas de contactos.</span><span class="sxs-lookup"><span data-stu-id="8be5e-166">Normalization rules are necessary for call routing because users can, and do, use various formats when entering phone numbers in their Contacts lists.</span></span>

<span data-ttu-id="8be5e-167">La normalización de los números de teléfono proporcionados por el usuario proporciona un formato coherente que facilita las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="8be5e-167">Normalizing user-supplied phone numbers provides a consistent format that facilitates the following tasks:</span></span>

  - <span data-ttu-id="8be5e-168">Hacer coincidir un número marcado con el SIP-URI del destinatario correspondiente.</span><span class="sxs-lookup"><span data-stu-id="8be5e-168">Match a dialed number to the intended recipient’s SIP-URI.</span></span>

  - <span data-ttu-id="8be5e-169">Aplicar reglas de autorización de marcado al usuario que realiza la llamada.</span><span class="sxs-lookup"><span data-stu-id="8be5e-169">Apply dialing authorization rules to the calling party.</span></span>

<span data-ttu-id="8be5e-170">Los siguientes campos numéricos están entre los que deben tener en cuenta las reglas de normalización:</span><span class="sxs-lookup"><span data-stu-id="8be5e-170">The following number fields are among those that your normalization rules may need to account for:</span></span>

  - <span data-ttu-id="8be5e-171">Plan de marcado</span><span class="sxs-lookup"><span data-stu-id="8be5e-171">Dial plan</span></span>

  - <span data-ttu-id="8be5e-172">Código de país</span><span class="sxs-lookup"><span data-stu-id="8be5e-172">Country code</span></span>

  - <span data-ttu-id="8be5e-173">Código de área</span><span class="sxs-lookup"><span data-stu-id="8be5e-173">Area code</span></span>

  - <span data-ttu-id="8be5e-174">Longitud de extensión</span><span class="sxs-lookup"><span data-stu-id="8be5e-174">Length of extension</span></span>

  - <span data-ttu-id="8be5e-175">Prefijo de sitio</span><span class="sxs-lookup"><span data-stu-id="8be5e-175">Site prefix</span></span>

<div>

## <a name="creating-normalization-rules"></a><span data-ttu-id="8be5e-176">Creación de reglas de normalización</span><span class="sxs-lookup"><span data-stu-id="8be5e-176">Creating Normalization Rules</span></span>

<span data-ttu-id="8be5e-177">Las reglas de normalización utilizan expresiones regulares de .NET Framework para especificar patrones de coincidencia numérica que el servidor usa para traducir cadenas de marcado al formato E. 164 con el fin de realizar la búsqueda inversa de números.</span><span class="sxs-lookup"><span data-stu-id="8be5e-177">Normalization rules use .NET Framework regular expressions to specify numeric match patterns that the server uses to translate dial strings to E.164 format for the purpose of performing reverse number lookup.</span></span> <span data-ttu-id="8be5e-178">Puede crear reglas de normalización en el panel de control de Lync Server si escribe las expresiones manualmente o si escribe los dígitos iniciales y la longitud de las cadenas de marcado para coincidir y permite que el panel de control de Lync Server genere la expresión regular correspondiente.</span><span class="sxs-lookup"><span data-stu-id="8be5e-178">You create normalization rules in the Lync Server Control Panel either by entering the expressions manually, or by entering the starting digits and the length of the dial strings to be matched and letting the Lync Server Control Panel generate the corresponding regular expression for you.</span></span> <span data-ttu-id="8be5e-179">En cualquier caso, cuando termine, puede escribir un número de prueba para comprobar que la regla de normalización funciona según lo esperado.</span><span class="sxs-lookup"><span data-stu-id="8be5e-179">Either way, when you finish, you can enter a test number to verify that the normalization rule works as expected.</span></span>

<span data-ttu-id="8be5e-180">Para obtener información detallada sobre el uso de expresiones regulares de .NET Framework, vea "expresiones regulares de .NET Framework" en [https://go.microsoft.com/fwlink/p/?linkId=140927](https://go.microsoft.com/fwlink/p/?linkid=140927) .</span><span class="sxs-lookup"><span data-stu-id="8be5e-180">For details about using .NET Framework regular expressions, see ".NET Framework Regular Expressions" at [https://go.microsoft.com/fwlink/p/?linkId=140927](https://go.microsoft.com/fwlink/p/?linkid=140927).</span></span>

</div>

<span id="BKMK_SampleNormalizationRules"></span>

<div>

## <a name="sample-normalization-rules"></a><span data-ttu-id="8be5e-181">Reglas de normalización de ejemplo</span><span class="sxs-lookup"><span data-stu-id="8be5e-181">Sample Normalization Rules</span></span>

<span data-ttu-id="8be5e-p116">En la siguiente tabla se muestran ejemplos de reglas de normalización escritas como expresiones regulares de .NET Framework. Son solo ejemplos, no una referencia normativa para crear reglas de normalización.</span><span class="sxs-lookup"><span data-stu-id="8be5e-p116">The following table shows sample normalization rules that are written as .NET Framework regular expressions. The samples are examples only and are not meant to be a prescriptive reference for creating your own normalization rules.</span></span>

### <a name="table-1normalization-rules-using-net-framework-regular-expressions"></a><span data-ttu-id="8be5e-184">Tabla 1. Reglas de normalización que usan expresiones regulares de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="8be5e-184">Table 1.Normalization Rules Using .NET Framework Regular Expressions</span></span>

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
<th><span data-ttu-id="8be5e-185">Nombre de regla</span><span class="sxs-lookup"><span data-stu-id="8be5e-185">Rule name</span></span></th>
<th><span data-ttu-id="8be5e-186">Descripción</span><span class="sxs-lookup"><span data-stu-id="8be5e-186">Description</span></span></th>
<th><span data-ttu-id="8be5e-187">Modelo de número</span><span class="sxs-lookup"><span data-stu-id="8be5e-187">Number pattern</span></span></th>
<th><span data-ttu-id="8be5e-188">Translation</span><span class="sxs-lookup"><span data-stu-id="8be5e-188">Translation</span></span></th>
<th><span data-ttu-id="8be5e-189">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8be5e-189">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8be5e-190">4digitExtension</span><span class="sxs-lookup"><span data-stu-id="8be5e-190">4digitExtension</span></span></p></td>
<td><p><span data-ttu-id="8be5e-191">Convierte extensiones de 4 dígitos</span><span class="sxs-lookup"><span data-stu-id="8be5e-191">Translates 4-digit extensions</span></span></p></td>
<td><p><span data-ttu-id="8be5e-192">^ (\d {4} ) $</span><span class="sxs-lookup"><span data-stu-id="8be5e-192">^(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="8be5e-193">+ 1425555 $1</span><span class="sxs-lookup"><span data-stu-id="8be5e-193">+1425555$1</span></span></p></td>
<td><p><span data-ttu-id="8be5e-194">0100 se convierte en +14255550100</span><span class="sxs-lookup"><span data-stu-id="8be5e-194">0100 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8be5e-195">5digitExtension</span><span class="sxs-lookup"><span data-stu-id="8be5e-195">5digitExtension</span></span></p></td>
<td><p><span data-ttu-id="8be5e-196">Convierte extensiones de 5 dígitos</span><span class="sxs-lookup"><span data-stu-id="8be5e-196">Translates 5-digit extensions</span></span></p></td>
<td><p><span data-ttu-id="8be5e-197">^ 5 (\d {4} ) $</span><span class="sxs-lookup"><span data-stu-id="8be5e-197">^5(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="8be5e-198">+ 1425555 $1</span><span class="sxs-lookup"><span data-stu-id="8be5e-198">+1425555$1</span></span></p></td>
<td><p><span data-ttu-id="8be5e-199">50100 se convierte en +14255550100</span><span class="sxs-lookup"><span data-stu-id="8be5e-199">50100 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8be5e-200">7digitcallingRedmond</span><span class="sxs-lookup"><span data-stu-id="8be5e-200">7digitcallingRedmond</span></span></p></td>
<td><p><span data-ttu-id="8be5e-201">Convierte números de 7 dígitos en números locales de Redmond</span><span class="sxs-lookup"><span data-stu-id="8be5e-201">Translates 7-digit numbers to Redmond local numbers</span></span></p></td>
<td><p><span data-ttu-id="8be5e-202">^ (\d {7} ) $</span><span class="sxs-lookup"><span data-stu-id="8be5e-202">^(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="8be5e-203">+ 1425 $1</span><span class="sxs-lookup"><span data-stu-id="8be5e-203">+1425$1</span></span></p></td>
<td><p><span data-ttu-id="8be5e-204">5550100 se convierte en +14255550100</span><span class="sxs-lookup"><span data-stu-id="8be5e-204">5550100 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8be5e-205">7digitcallingDallas</span><span class="sxs-lookup"><span data-stu-id="8be5e-205">7digitcallingDallas</span></span></p></td>
<td><p><span data-ttu-id="8be5e-206">Convierte números de 7 dígitos en números locales de Dallas</span><span class="sxs-lookup"><span data-stu-id="8be5e-206">Translates 7-digit numbers to Dallas local numbers</span></span></p></td>
<td><p><span data-ttu-id="8be5e-207">^ (\d {7} ) $</span><span class="sxs-lookup"><span data-stu-id="8be5e-207">^(\d{7})$</span></span></p></td>
<td><p><span data-ttu-id="8be5e-208">+ 1972 $1</span><span class="sxs-lookup"><span data-stu-id="8be5e-208">+1972$1</span></span></p></td>
<td><p><span data-ttu-id="8be5e-209">5550100 se convierte en +19725550100</span><span class="sxs-lookup"><span data-stu-id="8be5e-209">5550100 is translated to +19725550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8be5e-210">10digitcallingUS</span><span class="sxs-lookup"><span data-stu-id="8be5e-210">10digitcallingUS</span></span></p></td>
<td><p><span data-ttu-id="8be5e-211">Convierte números de 10 dígitos en los Estados Unidos</span><span class="sxs-lookup"><span data-stu-id="8be5e-211">Translates 10-digit numbers in the United States</span></span></p></td>
<td><p><span data-ttu-id="8be5e-212">^ (\d {10} ) $</span><span class="sxs-lookup"><span data-stu-id="8be5e-212">^(\d{10})$</span></span></p></td>
<td><p><span data-ttu-id="8be5e-213">+ 1 $1</span><span class="sxs-lookup"><span data-stu-id="8be5e-213">+1$1</span></span></p></td>
<td><p><span data-ttu-id="8be5e-214">2065550100 se convierte en +12065550100</span><span class="sxs-lookup"><span data-stu-id="8be5e-214">2065550100 is translated to +12065550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8be5e-215">LDCallingUS</span><span class="sxs-lookup"><span data-stu-id="8be5e-215">LDCallingUS</span></span></p></td>
<td><p><span data-ttu-id="8be5e-216">Convierte los números con prefijos de larga distancia de Estados Unidos</span><span class="sxs-lookup"><span data-stu-id="8be5e-216">Translates numbers with long distance prefixes in the United States</span></span></p></td>
<td><p><span data-ttu-id="8be5e-217">^ 1 (\d {10} ) $</span><span class="sxs-lookup"><span data-stu-id="8be5e-217">^1(\d{10})$</span></span></p></td>
<td><p><span data-ttu-id="8be5e-218">+ $1</span><span class="sxs-lookup"><span data-stu-id="8be5e-218">+$1</span></span></p></td>
<td><p><span data-ttu-id="8be5e-219">12145550100 se convierte en +2145550100</span><span class="sxs-lookup"><span data-stu-id="8be5e-219">12145550100 is translated to +2145550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8be5e-220">IntlCallingUS</span><span class="sxs-lookup"><span data-stu-id="8be5e-220">IntlCallingUS</span></span></p></td>
<td><p><span data-ttu-id="8be5e-221">Convierte los números con prefijos internacionales de Estados Unidos</span><span class="sxs-lookup"><span data-stu-id="8be5e-221">Translates numbers with international prefixes in the United States</span></span></p></td>
<td><p><span data-ttu-id="8be5e-222">^ 011 (\d \*) $</span><span class="sxs-lookup"><span data-stu-id="8be5e-222">^011(\d\*)$</span></span></p></td>
<td><p><span data-ttu-id="8be5e-223">+ $1</span><span class="sxs-lookup"><span data-stu-id="8be5e-223">+$1</span></span></p></td>
<td><p><span data-ttu-id="8be5e-224">01191445550100 se convierte en +91445550100</span><span class="sxs-lookup"><span data-stu-id="8be5e-224">01191445550100 is translated to +91445550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8be5e-225">RedmondOperator</span><span class="sxs-lookup"><span data-stu-id="8be5e-225">RedmondOperator</span></span></p></td>
<td><p><span data-ttu-id="8be5e-226">Convierte 0 al operador de Redmond</span><span class="sxs-lookup"><span data-stu-id="8be5e-226">Translates 0 to Redmond Operator</span></span></p></td>
<td><p><span data-ttu-id="8be5e-227">^ $0</span><span class="sxs-lookup"><span data-stu-id="8be5e-227">^0$</span></span></p></td>
<td><p><span data-ttu-id="8be5e-228">+ 14255550100</span><span class="sxs-lookup"><span data-stu-id="8be5e-228">+14255550100</span></span></p></td>
<td><p><span data-ttu-id="8be5e-229">0 se convierte en +14255550100</span><span class="sxs-lookup"><span data-stu-id="8be5e-229">0 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8be5e-230">RedmondSitePrefix</span><span class="sxs-lookup"><span data-stu-id="8be5e-230">RedmondSitePrefix</span></span></p></td>
<td><p><span data-ttu-id="8be5e-231">Convierte los números con prefijo de red (6) y prefijo de sitio de Redmond (222)</span><span class="sxs-lookup"><span data-stu-id="8be5e-231">Translates numbers with on-net prefix (6) and Redmond site code (222)</span></span></p></td>
<td><p><span data-ttu-id="8be5e-232">^ 6222 (\d {4} ) $</span><span class="sxs-lookup"><span data-stu-id="8be5e-232">^6222(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="8be5e-233">+ 1425555 $1</span><span class="sxs-lookup"><span data-stu-id="8be5e-233">+1425555$1</span></span></p></td>
<td><p><span data-ttu-id="8be5e-234">62220100 se convierte en +14255550100</span><span class="sxs-lookup"><span data-stu-id="8be5e-234">62220100 is translated to +14255550100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8be5e-235">NYSitePrefix</span><span class="sxs-lookup"><span data-stu-id="8be5e-235">NYSitePrefix</span></span></p></td>
<td><p><span data-ttu-id="8be5e-236">Convierte los números con prefijo de red (6) y prefijo de sitio de Nueva York (333)</span><span class="sxs-lookup"><span data-stu-id="8be5e-236">Translates numbers with on-net prefix (6) and NY site code (333)</span></span></p></td>
<td><p><span data-ttu-id="8be5e-237">^ 6333 (\d {4} ) $</span><span class="sxs-lookup"><span data-stu-id="8be5e-237">^6333(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="8be5e-238">+ 1202555 $1</span><span class="sxs-lookup"><span data-stu-id="8be5e-238">+1202555$1</span></span></p></td>
<td><p><span data-ttu-id="8be5e-239">63330100 se convierte en +12025550100</span><span class="sxs-lookup"><span data-stu-id="8be5e-239">63330100 is translated to +12025550100</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8be5e-240">DallasSitePrefix</span><span class="sxs-lookup"><span data-stu-id="8be5e-240">DallasSitePrefix</span></span></p></td>
<td><p><span data-ttu-id="8be5e-241">Convierte los números con prefijo de red (6) y prefijo de sitio de Dallas (444)</span><span class="sxs-lookup"><span data-stu-id="8be5e-241">Translates numbers with on-net prefix (6) and Dallas site code (444)</span></span></p></td>
<td><p><span data-ttu-id="8be5e-242">^ 6444 (\d {4} ) $</span><span class="sxs-lookup"><span data-stu-id="8be5e-242">^6444(\d{4})$</span></span></p></td>
<td><p><span data-ttu-id="8be5e-243">+ 1972555 $1</span><span class="sxs-lookup"><span data-stu-id="8be5e-243">+1972555$1</span></span></p></td>
<td><p><span data-ttu-id="8be5e-244">64440100 se convierte en +19725550100</span><span class="sxs-lookup"><span data-stu-id="8be5e-244">64440100 is translated to +19725550100</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="8be5e-245">En la tabla siguiente se muestra un plan de marcado de ejemplo para Redmond, Washington, Estados Unidos, basado en las reglas de normalización que se muestran en la tabla anterior.</span><span class="sxs-lookup"><span data-stu-id="8be5e-245">The following table illustrates a sample dial plan for Redmond, Washington, United States, based on the normalization rules shown in the previous table.</span></span>

### <a name="table-2-redmond-dial-plan-based-on-normalization-rules-shown-in-table-1"></a><span data-ttu-id="8be5e-p117">Tabla 2. Plan de marcado de Redmond basado en las reglas de normalización mostradas en la tabla 1</span><span class="sxs-lookup"><span data-stu-id="8be5e-p117">Table 2. Redmond Dial Plan Based on Normalization Rules Shown in Table 1</span></span>

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8be5e-248">Redmond. forestFQDN</span><span class="sxs-lookup"><span data-stu-id="8be5e-248">Redmond.forestFQDN</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8be5e-249">5digitExtension</span><span class="sxs-lookup"><span data-stu-id="8be5e-249">5digitExtension</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8be5e-250">7digitcallingRedmond</span><span class="sxs-lookup"><span data-stu-id="8be5e-250">7digitcallingRedmond</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8be5e-251">10digitcallingUS</span><span class="sxs-lookup"><span data-stu-id="8be5e-251">10digitcallingUS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8be5e-252">IntlCallingUS</span><span class="sxs-lookup"><span data-stu-id="8be5e-252">IntlCallingUS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8be5e-253">RedmondSitePrefix</span><span class="sxs-lookup"><span data-stu-id="8be5e-253">RedmondSitePrefix</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8be5e-254">NYSitePrefix</span><span class="sxs-lookup"><span data-stu-id="8be5e-254">NYSitePrefix</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8be5e-255">DallasSitePrefix</span><span class="sxs-lookup"><span data-stu-id="8be5e-255">DallasSitePrefix</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8be5e-256">RedmondOperator</span><span class="sxs-lookup"><span data-stu-id="8be5e-256">RedmondOperator</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="8be5e-p118">Aunque los nombres de las reglas de normalización que se muestran en la tabla anterior no incluyen espacios, es opcional usarlos. Por ejemplo, el primer nombre de la tabla se podía haber escrito como "Extensión de 5 dígitos" y sería un nombre válido.</span><span class="sxs-lookup"><span data-stu-id="8be5e-p118">The normalization rules names shown in the preceding table do not include spaces, but this is a matter of choice. The first name in the table, for example, could have been written "5 digit extension" or "5-digit Extension" and still be valid.</span></span>



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

