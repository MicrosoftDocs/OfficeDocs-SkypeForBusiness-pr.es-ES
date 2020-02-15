---
title: Requisitos para conferencias de acceso telefónico local de Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dial-in conferencing requirements
ms:assetid: 9aff949e-3dac-481a-be46-a180c72e8066
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398802(v=OCS.15)
ms:contentKeyID: 48184969
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b80ab9db6b565530db211db8aa47e2e00cbd9cf2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044722"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dial-in-conferencing-requirements-in-lync-server-2013"></a><span data-ttu-id="c1415-102">Requisitos de conferencia de acceso telefónico local en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c1415-102">Dial-in conferencing requirements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c1415-103">_**Última modificación del tema:** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="c1415-103">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="c1415-104">Antes de iniciar el proceso de implementación de Lync Server 2013, tiene que planear lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c1415-104">Before you start the Lync Server 2013 deployment process you need to plan for the following:</span></span>

  - <span data-ttu-id="c1415-105">La configuración que usará para conectarse a la red telefónica conmutada (RTC)</span><span class="sxs-lookup"><span data-stu-id="c1415-105">The configuration to use for connecting to the public switched telephone network (PSTN)</span></span>

  - <span data-ttu-id="c1415-106">La estrategia que empleará para asignar regiones de conferencia de acceso telefónico local a números de acceso telefónico</span><span class="sxs-lookup"><span data-stu-id="c1415-106">Your strategy for assigning dial-in conferencing regions to dial-in access numbers</span></span>

  - <span data-ttu-id="c1415-107">La estrategia que empleará para crear directorios de conferencia</span><span class="sxs-lookup"><span data-stu-id="c1415-107">Your strategy for creating conference directories</span></span>

<div>

## <a name="planning-for-dial-in-pstn-connectivity"></a><span data-ttu-id="c1415-108">Planeación de la conectividad con RTC de acceso telefónico</span><span class="sxs-lookup"><span data-stu-id="c1415-108">Planning for Dial-in PSTN Connectivity</span></span>

<span data-ttu-id="c1415-109">La Conferencia de acceso telefónico local requiere al menos un servidor de mediación y una puerta de enlace RTC.</span><span class="sxs-lookup"><span data-stu-id="c1415-109">Dial-in conferencing requires at least one Mediation Server and at least one PSTN gateway.</span></span>

<span data-ttu-id="c1415-110">Puede implementar un servidor de mediación en un sitio central o en un sitio de sucursal.</span><span class="sxs-lookup"><span data-stu-id="c1415-110">You can deploy a Mediation Server in a central site or in a branch site.</span></span> <span data-ttu-id="c1415-111">En un sitio central, puede combinar un servidor de mediación en un grupo de servidores front-end o un servidor Standard Edition, o puede implementarlo en un servidor o grupo de servidores independiente.</span><span class="sxs-lookup"><span data-stu-id="c1415-111">In a central site, you can collocate a Mediation Server on a Front End pool or Standard Edition server, or you can deploy it on a stand-alone server or pool.</span></span> <span data-ttu-id="c1415-112">En un sitio de sucursal, puede implementar un servidor de mediación en un servidor independiente o como componente de la aplicación de sucursal con funciones de supervivencia.</span><span class="sxs-lookup"><span data-stu-id="c1415-112">In a branch site, you can deploy a Mediation Server on a stand-alone server or as a component of the Survivable Branch Appliance.</span></span>

<span data-ttu-id="c1415-113">Puede implementar una puerta de enlace RTC en un sitio central o en un sitio de sucursal.</span><span class="sxs-lookup"><span data-stu-id="c1415-113">You can deploy a PSTN gateway in a central site or in a branch site.</span></span> <span data-ttu-id="c1415-114">En un sitio de sucursal, la puerta de enlace RTC puede ser independiente o un componente de la aplicación de sucursal con funciones de supervivencia.</span><span class="sxs-lookup"><span data-stu-id="c1415-114">In a branch site, the PSTN gateway can be stand-alone or a component of the Survivable Branch Appliance.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c1415-115">La Conferencia de acceso telefónico local no usa la omisión de medios porque el servidor de conferencia A/V no admite el desvío de medios.</span><span class="sxs-lookup"><span data-stu-id="c1415-115">Dial-in conferencing does not use media bypass because A/V Conferencing Server do not support media bypass.</span></span>



</div>

<span data-ttu-id="c1415-116">Para obtener información detallada sobre cómo planear la configuración del servidor de mediación y de las puertas de enlace RTC para las conferencias de acceso telefónico local, consulte [componentes y topologías para servidor de mediación en Lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="c1415-116">For details about planning your configuration for Mediation Server and PSTN gateways for dial-in conferencing, see [Components and topologies for Mediation Server in Lync Server 2013](lync-server-2013-components-and-topologies-for-mediation-server.md) in the Planning documentation.</span></span>

</div>

<span id="bkmk_PlanningforDialinConferencingRegions"></span>

<div>

## <a name="planning-for-dial-in-conferencing-regions"></a><span data-ttu-id="c1415-117">Planeación de las regiones de conferencia de acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="c1415-117">Planning for Dial-in Conferencing Regions</span></span>

<span data-ttu-id="c1415-p103">Durante la configuración de acceso telefónico, se crean planes de marcado y números de acceso a conferencias de acceso telefónico local. Los planes de marcado son conjuntos de reglas de normalización que especifican el número y el patrón de dígitos de un número de teléfono y convierten el número de teléfono al formato E.164 estándar para el enrutamiento de llamadas. Los números de acceso a conferencias de acceso telefónico local son números a los que pueden llamar los usuarios para participar en una conferencia.</span><span class="sxs-lookup"><span data-stu-id="c1415-p103">During dial-in configuration, you create dial plans and dial-in conferencing access numbers. Dial plans are sets of normalization rules that specify the number and pattern of digits in a phone number and translate the phone number into the standard E.164 format for call routing. Dial-in conferencing access numbers are the numbers participants call to join a conference.</span></span>

<span data-ttu-id="c1415-p104">Cada número de acceso a conferencias de acceso telefónico local debe estar asociado por lo menos con un plan de marcado. Las regiones de conferencia de acceso telefónico local asocian un número de acceso a conferencias de acceso telefónico local con sus planes de marcado. Al definir un plan de marcado, se especifica la región de conferencia de acceso telefónico local que se aplica al plan de marcado. Cuando se crea el número de acceso telefónico local, se seleccionan las regiones que asocian el número de acceso con los planes de marcado pertinentes.</span><span class="sxs-lookup"><span data-stu-id="c1415-p104">Every dial-in conferencing access number must be associated with at least one dial plan. Dial-in conferencing regions associate a dial-in conferencing access number with its dial plans. When you set up a dial plan, you specify the dial-in conferencing region that applies to the dial plan. When you create the dial-in access number, you select the regions that associate the access number with the appropriate dial plans.</span></span>

<span data-ttu-id="c1415-p105">Al crear un plan de marcado, se especifica el ámbito del mismo: ámbito de usuario, ámbito de grupo de servidores o ámbito de sitio. A cada usuario se asigna el plan de marcado correspondiente al ámbito más limitado que se aplica al usuario. Por ejemplo, se asigna a un usuario un plan de marcado de nivel de usuario, si procede. Si no tiene aplicado ningún plan de marcado de nivel de usuario, se le asignará un plan de marcado de nivel de grupo de servidores. Si no tiene aplicado ningún plan de marcado de nivel de grupo de servidores, se le asignará un plan de marcado de nivel de sitio. Si no tiene aplicado ningún plan de marcado de nivel de sitio, se le asignará el plan de marcado global.</span><span class="sxs-lookup"><span data-stu-id="c1415-p105">When you create a dial plan, you specify the scope of the dial plan: user scope, pool scope, or site scope. Every user is assigned the dial plan from the narrowest scope that applies to the user. For example, a user is assigned a user-level dial plan, if one applies. If a user-level dial plan does not apply, the user is assigned a pool-level dial plan. If a pool-level dial plan does not apply, the user is assigned a site-level dial plan. If a site-level dial plan does not apply, the user is assigned the global dial plan.</span></span>

<span data-ttu-id="c1415-p106">Antes de configurar los planes de marcado, es importante planear qué nombres desea aplicar a las regiones y cómo desea usarlas. Las consideraciones siguientes deben aplicarse a las regiones de conferencia de acceso telefónico local:</span><span class="sxs-lookup"><span data-stu-id="c1415-p106">Before you configure the dial plans, is it important to plan how you want to name and use regions. The following considerations apply to dial-in conferencing regions:</span></span>

  - <span data-ttu-id="c1415-133">Una región es, por lo general, un área geográfica asociada con una oficina o con un grupo de oficinas.</span><span class="sxs-lookup"><span data-stu-id="c1415-133">A region is typically a geographical area that is associated with an office or group of offices.</span></span>

  - <span data-ttu-id="c1415-p107">Los números de acceso telefónico local están asociados a idiomas. Si admite áreas geográficas con varios idiomas, tendrá que decidir cómo desea definir las regiones para que admitan los diferentes idiomas. Por ejemplo, puede definir varias regiones según una combinación de zona geográfica e idioma, o bien puede definir una única región según la zona geográfica y tener números de acceso telefónico local distintos para cada idioma.</span><span class="sxs-lookup"><span data-stu-id="c1415-p107">Languages are associated with dial-in access numbers. If you support geographical areas that have multiple languages, you should decide how you want to define regions to support the multiple languages. For example, you might define multiple regions based on a combination of geography and language, or you might define a single region based on geography and have a different dial-in access numbers for each language.</span></span>

  - <span data-ttu-id="c1415-137">Cuando un usuario programa una reunión, de forma predeterminada la reunión usa la región especificada por el plan de marcado del usuario.</span><span class="sxs-lookup"><span data-stu-id="c1415-137">When a user schedules a meeting, by default the meeting uses the region specified by that user's dial plan.</span></span>

  - <span data-ttu-id="c1415-138">De forma predeterminada, todos los números de acceso telefónico local de la región se incluyen en la invitación a la reunión.</span><span class="sxs-lookup"><span data-stu-id="c1415-138">By default, the all of the dial-in access numbers for the region are included in the meeting invitation.</span></span>

  - <span data-ttu-id="c1415-139">Es importante asignar un nombre a las regiones de modo que puedan reconocerse claramente.</span><span class="sxs-lookup"><span data-stu-id="c1415-139">It is important to name regions so that they are clearly recognizable.</span></span> <span data-ttu-id="c1415-140">El usuario puede usar los nombres de las regiones para cambiar una región de una reunión de modo que los distintos números de acceso se incluyan en la invitación.</span><span class="sxs-lookup"><span data-stu-id="c1415-140">The user can use the names of the regions to change a meeting's region so that different access numbers are included in the invitation.</span></span> <span data-ttu-id="c1415-141">(Cuando los usuarios usan Outlook para programar una reunión, el usuario usa el complemento de reunión en línea para Lync 2013 para cambiar la región).</span><span class="sxs-lookup"><span data-stu-id="c1415-141">(When users use Outlook to schedule a meeting, the user uses the Online Meeting Add-in for Lync 2013 to change the region).</span></span>

  - <span data-ttu-id="c1415-142">Las regiones deben asignarse de tal modo que cualquier invitado que quiera obtener acceso a una conferencia pueda ver un número de acceso local en la invitación a la misma.</span><span class="sxs-lookup"><span data-stu-id="c1415-142">Regions should be designed so that any invitee who wants to dial into a conference can see a local access number in the conference invitation.</span></span>

  - <span data-ttu-id="c1415-143">Puede configurar el orden en el que aparecen los números de acceso dentro de una región en la página Configuración de conferencia de acceso telefónico local (y, por tanto, el orden en que aparecen en la invitación a la Conferencia) mediante los cmdlets del shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c1415-143">You can configure the order in which access numbers within a region appear on the Dial-in Conferencing Settings page (and, therefore, the order in which they appear in the conference invitation) by using Lync Server Management Shell cmdlets.</span></span>

  - <span data-ttu-id="c1415-144">Cualquier usuario puede llamar al número de acceso telefónico local que desee para unirse a una conferencia desde cualquier ubicación.</span><span class="sxs-lookup"><span data-stu-id="c1415-144">Any user from any location can call any dial-in access number to join a conference.</span></span>

</div>

<div>

## <a name="planning-for-conference-directories"></a><span data-ttu-id="c1415-145">Planeación de los directorios de conferencia</span><span class="sxs-lookup"><span data-stu-id="c1415-145">Planning for Conference Directories</span></span>

<span data-ttu-id="c1415-146">Los directorios de conferencia mantienen una asignación entre el identificador de reunión alfanumérico que un participante usa para unirse a una conferencia cuando usa Lync 2013 y el identificador de conferencia de acceso telefónico local que usa un participante de la Conferencia de acceso telefónico local para unirse a la Conferencia.</span><span class="sxs-lookup"><span data-stu-id="c1415-146">Conference directories maintain a mapping between the alphanumeric meeting ID that a participant uses to join a conference when using Lync 2013, and the numeric-only conference ID that a dial-in conferencing participant uses to join the conference.</span></span> <span data-ttu-id="c1415-147">El formato del identificador de conferencia es el siguiente:</span><span class="sxs-lookup"><span data-stu-id="c1415-147">The format of the conference ID is as follows:</span></span>

    <housekeeping digit (1 digit)><conference directory (usually 1-2 digits)><conference number (variable number of digits><check digit (1 digit)>

<span data-ttu-id="c1415-p110">Si crea varios directorios de conferencia, se asegurará de que los Id. de conferencia se mantienen cortos hasta que se haya creado un número significativo de conferencias. En una organización con un número establecido de conferencias por usuario, se recomienda crear un directorio de conferencia por cada 999 usuarios en el grupo de servidores. Si aplica esta sugerencia, los Id. de conferencia, por lo general, se mantendrán cortos. Ahora bien, una vez que entre los diferentes grupos de servidores haya más de 9 directorios de conferencia, el número de Id. de conferencia crecerá para facilitar la creación de nuevas conferencias.</span><span class="sxs-lookup"><span data-stu-id="c1415-p110">Creating multiple conference directories will ensure that conference IDs will stay short until a significant amount of conferences have been created. In an organization with a typical number of conferences per user, we recommend that you create one conference directory for every 999 users in the pool. Using this guideline the conference IDs can generally be kept small. However, once the number of conference directories (across the pools) exceed 9, the Conference ID number will grow to support additional conferences.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c1415-152">Vea también</span><span class="sxs-lookup"><span data-stu-id="c1415-152">See Also</span></span>


[<span data-ttu-id="c1415-153">Componente de servidor de mediación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c1415-153">Mediation Server component in Lync Server 2013</span></span>](lync-server-2013-mediation-server-component.md)  
[<span data-ttu-id="c1415-154">Planes de marcado y reglas de normalización en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c1415-154">Dial plans and normalization rules in Lync Server 2013</span></span>](lync-server-2013-dial-plans-and-normalization-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

