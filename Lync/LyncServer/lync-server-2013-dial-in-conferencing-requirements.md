---
title: Requisitos de conferencia de acceso telefónico local de Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Dial-in conferencing requirements
ms:assetid: 9aff949e-3dac-481a-be46-a180c72e8066
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398802(v=OCS.15)
ms:contentKeyID: 48184969
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a2f4878e81a28b5d51726cb1f3e2dc5c7c5aa0fc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835405"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dial-in-conferencing-requirements-in-lync-server-2013"></a><span data-ttu-id="2283a-102">Requisitos de las conferencias de acceso telefónico local en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2283a-102">Dial-in conferencing requirements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2283a-103">_**Última modificación del tema:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="2283a-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="2283a-104">Antes de iniciar el proceso de implementación de Lync Server 2013, necesitará planear lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2283a-104">Before you start the Lync Server 2013 deployment process you need to plan for the following:</span></span>

  - <span data-ttu-id="2283a-105">La configuración que se usa para conectarse a la red de telefonía pública conmutada (RTC)</span><span class="sxs-lookup"><span data-stu-id="2283a-105">The configuration to use for connecting to the public switched telephone network (PSTN)</span></span>

  - <span data-ttu-id="2283a-106">Su estrategia para asignar regiones de conferencia de acceso telefónico local a los números de acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="2283a-106">Your strategy for assigning dial-in conferencing regions to dial-in access numbers</span></span>

  - <span data-ttu-id="2283a-107">Su estrategia para crear directorios de conferencia</span><span class="sxs-lookup"><span data-stu-id="2283a-107">Your strategy for creating conference directories</span></span>

<div>

## <a name="planning-for-dial-in-pstn-connectivity"></a><span data-ttu-id="2283a-108">Planificación de la conectividad RTC de acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="2283a-108">Planning for Dial-in PSTN Connectivity</span></span>

<span data-ttu-id="2283a-109">Las conferencias de acceso telefónico local requieren al menos un servidor de mediación y una puerta de enlace PSTN como mínimo.</span><span class="sxs-lookup"><span data-stu-id="2283a-109">Dial-in conferencing requires at least one Mediation Server and at least one PSTN gateway.</span></span>

<span data-ttu-id="2283a-110">Puede implementar un servidor de mediación en un sitio central o en un sitio de sucursal.</span><span class="sxs-lookup"><span data-stu-id="2283a-110">You can deploy a Mediation Server in a central site or in a branch site.</span></span> <span data-ttu-id="2283a-111">En un sitio central, puede instalar un servidor de mediación en un grupo de servidores front-end o en un servidor Standard Edition, o bien puede implementarlo en un servidor o en un grupo de servidores independiente.</span><span class="sxs-lookup"><span data-stu-id="2283a-111">In a central site, you can collocate a Mediation Server on a Front End pool or Standard Edition server, or you can deploy it on a stand-alone server or pool.</span></span> <span data-ttu-id="2283a-112">En un sitio de sucursal, puede implementar un servidor de mediación en un servidor independiente o como componente de la aplicación de sucursal con funciones de supervivencia.</span><span class="sxs-lookup"><span data-stu-id="2283a-112">In a branch site, you can deploy a Mediation Server on a stand-alone server or as a component of the Survivable Branch Appliance.</span></span>

<span data-ttu-id="2283a-p102">Puede implementar una puerta de enlace RTC en un sitio central o en un sitio de sucursal. En un sitio de sucursal, la puerta de enlace RTC puede ser independiente o un componente de la aplicación de sucursal con funciones de supervivencia.</span><span class="sxs-lookup"><span data-stu-id="2283a-p102">You can deploy a PSTN gateway in a central site or in a branch site. In a branch site, the PSTN gateway can be stand-alone or a component of the Survivable Branch Appliance.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2283a-115">Las conferencias de acceso telefónico local no usan la omisión de medios porque el servidor de conferencia A/V no admite la omisión de medios.</span><span class="sxs-lookup"><span data-stu-id="2283a-115">Dial-in conferencing does not use media bypass because A/V Conferencing Server do not support media bypass.</span></span>



</div>

<span data-ttu-id="2283a-116">Para obtener detalles sobre el planeamiento de la configuración del servidor de mediación y de las puertas de enlace RTC para conferencias de acceso telefónico local, vea [componentes y topologías de servidor de mediación en Lync server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="2283a-116">For details about planning your configuration for Mediation Server and PSTN gateways for dial-in conferencing, see [Components and topologies for Mediation Server in Lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) in the Planning documentation.</span></span>

</div>

<span id="bkmk_PlanningforDialinConferencingRegions"></span>

<div>

## <a name="planning-for-dial-in-conferencing-regions"></a><span data-ttu-id="2283a-117">Planificación de regiones de conferencia de acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="2283a-117">Planning for Dial-in Conferencing Regions</span></span>

<span data-ttu-id="2283a-118">Durante la configuración de acceso telefónico, puede crear planes de marcado y números de acceso a la Conferencia de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="2283a-118">During dial-in configuration, you create dial plans and dial-in conferencing access numbers.</span></span> <span data-ttu-id="2283a-119">Los planes de marcado son conjuntos de reglas de normalización que especifican el número y el patrón de dígitos en un número de teléfono y traducen el número de teléfono en el formato estándar E. 164 para el enrutamiento de llamadas.</span><span class="sxs-lookup"><span data-stu-id="2283a-119">Dial plans are sets of normalization rules that specify the number and pattern of digits in a phone number and translate the phone number into the standard E.164 format for call routing.</span></span> <span data-ttu-id="2283a-120">Los números de acceso a conferencias de acceso telefónico local son números a los que pueden llamar los usuarios para participar en una conferencia.</span><span class="sxs-lookup"><span data-stu-id="2283a-120">Dial-in conferencing access numbers are the numbers participants call to join a conference.</span></span>

<span data-ttu-id="2283a-121">Cada número de acceso a conferencias de acceso telefónico local necesita estar asociado por lo menos con un plan de marcado.</span><span class="sxs-lookup"><span data-stu-id="2283a-121">Every dial-in conferencing access number must be associated with at least one dial plan.</span></span> <span data-ttu-id="2283a-122">Las regiones de conferencias de acceso telefónico local asocian un número de acceso de conferencia de acceso telefónico local a sus planes de marcado.</span><span class="sxs-lookup"><span data-stu-id="2283a-122">Dial-in conferencing regions associate a dial-in conferencing access number with its dial plans.</span></span> <span data-ttu-id="2283a-123">Al configurar un plan de marcado, se especifica la región de conferencia de acceso telefónico local que se aplica al plan de marcado.</span><span class="sxs-lookup"><span data-stu-id="2283a-123">When you set up a dial plan, you specify the dial-in conferencing region that applies to the dial plan.</span></span> <span data-ttu-id="2283a-124">Cuando crea el número de acceso telefónico local, selecciona las regiones que asocian el número de acceso con los planes de marcado pertinentes.</span><span class="sxs-lookup"><span data-stu-id="2283a-124">When you create the dial-in access number, you select the regions that associate the access number with the appropriate dial plans.</span></span>

<span data-ttu-id="2283a-125">Al crear un plan de marcado, debe especificar el ámbito del plan de marcado: ámbito de usuario, ámbito del grupo o ámbito del sitio.</span><span class="sxs-lookup"><span data-stu-id="2283a-125">When you create a dial plan, you specify the scope of the dial plan: user scope, pool scope, or site scope.</span></span> <span data-ttu-id="2283a-126">A cada usuario se le asigna el plan de marcado correspondiente al ámbito más limitado que se aplica al usuario.</span><span class="sxs-lookup"><span data-stu-id="2283a-126">Every user is assigned the dial plan from the narrowest scope that applies to the user.</span></span> <span data-ttu-id="2283a-127">Por ejemplo, se asigna a un usuario un plan de marcado de nivel de usuario, si procede.</span><span class="sxs-lookup"><span data-stu-id="2283a-127">For example, a user is assigned a user-level dial plan, if one applies.</span></span> <span data-ttu-id="2283a-128">Si no tiene aplicado ningún plan de marcado de nivel de usuario, se le asignará un plan de marcado de nivel de grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="2283a-128">If a user-level dial plan does not apply, the user is assigned a pool-level dial plan.</span></span> <span data-ttu-id="2283a-129">Si no tiene aplicado ningún plan de marcado de nivel de grupo de servidores, se le asignará un plan de marcado de nivel de sitio.</span><span class="sxs-lookup"><span data-stu-id="2283a-129">If a pool-level dial plan does not apply, the user is assigned a site-level dial plan.</span></span> <span data-ttu-id="2283a-130">Si no tiene aplicado ningún plan de marcado de nivel de sitio, se le asignará el plan de marcado global.</span><span class="sxs-lookup"><span data-stu-id="2283a-130">If a site-level dial plan does not apply, the user is assigned the global dial plan.</span></span>

<span data-ttu-id="2283a-p106">Antes de configurar los planes de marcado, es importante planear qué nombres desea aplicar a las regiones y cómo desea usarlas. Las consideraciones siguientes necesitan aplicarse a las regiones de conferencia de acceso telefónico local:</span><span class="sxs-lookup"><span data-stu-id="2283a-p106">Before you configure the dial plans, is it important to plan how you want to name and use regions. The following considerations apply to dial-in conferencing regions:</span></span>

  - <span data-ttu-id="2283a-133">Una región es, por lo general, un área geográfica asociada con una oficina o con un grupo de oficinas.</span><span class="sxs-lookup"><span data-stu-id="2283a-133">A region is typically a geographical area that is associated with an office or group of offices.</span></span>

  - <span data-ttu-id="2283a-p107">Los números de acceso telefónico local están asociados a idiomas. Si admite áreas geográficas con varios idiomas, tendrá que decidir cómo desea definir las regiones para que admitan los diferentes idiomas. Por ejemplo, puede definir varias regiones según una combinación de zona geográfica e idioma, o bien puede definir una única región según la zona geográfica y tener números de acceso telefónico local distintos para cada idioma.</span><span class="sxs-lookup"><span data-stu-id="2283a-p107">Languages are associated with dial-in access numbers. If you support geographical areas that have multiple languages, you should decide how you want to define regions to support the multiple languages. For example, you might define multiple regions based on a combination of geography and language, or you might define a single region based on geography and have a different dial-in access numbers for each language.</span></span>

  - <span data-ttu-id="2283a-137">Cuando un usuario programa una reunión, de forma predeterminada la reunión usa la región especificada por el plan de marcado del usuario.</span><span class="sxs-lookup"><span data-stu-id="2283a-137">When a user schedules a meeting, by default the meeting uses the region specified by that user's dial plan.</span></span>

  - <span data-ttu-id="2283a-138">De forma predeterminada, todos los números de acceso telefónico local de la región están incluidos en la invitación a la reunión.</span><span class="sxs-lookup"><span data-stu-id="2283a-138">By default, the all of the dial-in access numbers for the region are included in the meeting invitation.</span></span>

  - <span data-ttu-id="2283a-139">Es importante asignar un nombre a las regiones de modo que puedan reconocerse claramente.</span><span class="sxs-lookup"><span data-stu-id="2283a-139">It is important to name regions so that they are clearly recognizable.</span></span> <span data-ttu-id="2283a-140">El usuario puede usar los nombres de las regiones para cambiar una región de una reunión de modo que los distintos números de acceso se incluyan en la invitación.</span><span class="sxs-lookup"><span data-stu-id="2283a-140">The user can use the names of the regions to change a meeting's region so that different access numbers are included in the invitation.</span></span> <span data-ttu-id="2283a-141">(Cuando los usuarios usan Outlook para programar una reunión, el usuario usa el complemento de reunión en línea para Lync 2013 para cambiar la región).</span><span class="sxs-lookup"><span data-stu-id="2283a-141">(When users use Outlook to schedule a meeting, the user uses the Online Meeting Add-in for Lync 2013 to change the region).</span></span>

  - <span data-ttu-id="2283a-142">Las regiones necesitan asignarse de tal modo que cualquier invitado que quiera obtener acceso a una conferencia pueda ver un número de acceso local en la invitación a la misma.</span><span class="sxs-lookup"><span data-stu-id="2283a-142">Regions should be designed so that any invitee who wants to dial into a conference can see a local access number in the conference invitation.</span></span>

  - <span data-ttu-id="2283a-143">Puede configurar el orden en el que aparecen los números de acceso dentro de una región en la página Configuración de conferencia de acceso telefónico local (y, por tanto, el orden en el que aparecen en la invitación a la Conferencia) mediante los cmdlets del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2283a-143">You can configure the order in which access numbers within a region appear on the Dial-in Conferencing Settings page (and, therefore, the order in which they appear in the conference invitation) by using Lync Server Management Shell cmdlets.</span></span>

  - <span data-ttu-id="2283a-144">Cualquier usuario puede llamar al número de acceso telefónico local que desee para unirse a una conferencia desde cualquier ubicación.</span><span class="sxs-lookup"><span data-stu-id="2283a-144">Any user from any location can call any dial-in access number to join a conference.</span></span>

</div>

<div>

## <a name="planning-for-conference-directories"></a><span data-ttu-id="2283a-145">Planificación de directorios de conferencia</span><span class="sxs-lookup"><span data-stu-id="2283a-145">Planning for Conference Directories</span></span>

<span data-ttu-id="2283a-146">Los directorios de conferencia mantienen una asignación entre el identificador de reunión alfanumérico que un participante usa para unirse a una conferencia al usar Lync 2013 y el identificador de conferencia de acceso telefónico local que usa un participante de conferencia de acceso telefónico local para unirse a la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="2283a-146">Conference directories maintain a mapping between the alphanumeric meeting ID that a participant uses to join a conference when using Lync 2013, and the numeric-only conference ID that a dial-in conferencing participant uses to join the conference.</span></span> <span data-ttu-id="2283a-147">El formato del identificador de conferencia es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="2283a-147">The format of the conference ID is as follows:</span></span>

    <housekeeping digit (1 digit)><conference directory (usually 1-2 digits)><conference number (variable number of digits><check digit (1 digit)>

<span data-ttu-id="2283a-148">Si crea varios directorios de conferencia, se asegurará de que los Id. de conferencia se mantienen cortos hasta que se haya creado un número significativo de conferencias.</span><span class="sxs-lookup"><span data-stu-id="2283a-148">Creating multiple conference directories will ensure that conference IDs will stay short until a significant amount of conferences have been created.</span></span> <span data-ttu-id="2283a-149">En una organización con un número establecido de conferencias por usuario, se recomienda crear un directorio de conferencia por cada 999 usuarios en el grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="2283a-149">In an organization with a typical number of conferences per user, we recommend that you create one conference directory for every 999 users in the pool.</span></span> <span data-ttu-id="2283a-150">Con esta pauta, los identificadores de conferencia generalmente se mantienen reducidos.</span><span class="sxs-lookup"><span data-stu-id="2283a-150">Using this guideline the conference IDs can generally be kept small.</span></span> <span data-ttu-id="2283a-151">Ahora bien, una vez que entre los diferentes grupos de servidores haya más de 9 directorios de conferencia, el número de Id. de conferencia crecerá para facilitar la creación de nuevas conferencias.</span><span class="sxs-lookup"><span data-stu-id="2283a-151">However, once the number of conference directories (across the pools) exceed 9, the Conference ID number will grow to support additional conferences.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2283a-152">Vea también</span><span class="sxs-lookup"><span data-stu-id="2283a-152">See Also</span></span>


[<span data-ttu-id="2283a-153">Componente de servidor de mediación de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2283a-153">Mediation Server component in Lync Server 2013</span></span>](lync-server-2013-mediation-server-component.md)  
[<span data-ttu-id="2283a-154">Planes de marcado y reglas de normalización en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2283a-154">Dial plans and normalization rules in Lync Server 2013</span></span>](lync-server-2013-dial-plans-and-normalization-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

