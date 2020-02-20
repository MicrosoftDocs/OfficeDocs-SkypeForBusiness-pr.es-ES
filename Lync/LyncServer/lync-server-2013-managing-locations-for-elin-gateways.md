---
title: 'Lync Server 2013: administrar ubicaciones para puertas de enlace de ELIN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing locations for ELIN gateways
ms:assetid: ced79c13-4e7e-4034-95cd-6fc913f4f222
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205288(v=OCS.15)
ms:contentKeyID: 48185496
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 17fa27b82260a05ded5ca025d56005c864247844
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150321"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-locations-for-elin-gateways-in-lync-server-2013"></a><span data-ttu-id="1f9ff-102">Administración de ubicaciones para puertas de enlace de ELIN en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1f9ff-102">Managing locations for ELIN gateways in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1f9ff-103">_**Última modificación del tema:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="1f9ff-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="1f9ff-104">Para que Lync Server proporcione automáticamente ubicaciones a los clientes de una red, debe realizar las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="1f9ff-104">To have Lync Server automatically provide locations for clients within a network, you need to perform the following tasks:</span></span>

  - <span data-ttu-id="1f9ff-105">Rellene la base de datos del servicio de información de ubicación con un cableado de red e incluya los números de identificación de ubicación de emergencia (Elin) en el campo NombreCompañía.</span><span class="sxs-lookup"><span data-stu-id="1f9ff-105">Populate the Location Information service database with a network wiremap, and include the Emergency Location Identification Numbers (ELINs) in the CompanyName field.</span></span>

  - <span data-ttu-id="1f9ff-106">Publique las ubicaciones para que estén disponibles para los clientes de la red.</span><span class="sxs-lookup"><span data-stu-id="1f9ff-106">Publish the locations so that they are available for clients in your network.</span></span>

  - <span data-ttu-id="1f9ff-107">Cargue los ELIN en la base de datos de identificación de ubicación automática (ALI) del proveedor de la red telefónica conmutada (RTCP).</span><span class="sxs-lookup"><span data-stu-id="1f9ff-107">Upload the ELINs to your public switched telephone network (PSTN) carrier's Automatic Location Identification (ALI) database.</span></span>

<span data-ttu-id="1f9ff-108">Para obtener más información sobre cómo realizar estas tareas, vea [configurar la base de datos de ubicaciones en Lync Server 2013](lync-server-2013-configure-the-location-database.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="1f9ff-108">For details about how to perform these tasks, see [Configure the location database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1f9ff-109">Las ubicaciones que se agregan a la base de datos de ubicaciones centrales no están disponibles para el cliente hasta que se han publicado mediante un comando del shell de administración de Lync Server y se replican en los almacenes locales del grupo.</span><span class="sxs-lookup"><span data-stu-id="1f9ff-109">Locations added to the central location database are not available to the client until they have been published by using a Lync Server Management Shell command and are replicated to the pool's local stores.</span></span> <span data-ttu-id="1f9ff-110">Para obtener más información, consulte <A href="lync-server-2013-publish-the-location-database.md">publicar la base de datos de ubicaciones en Lync Server 2013</A> en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="1f9ff-110">For details, see <A href="lync-server-2013-publish-the-location-database.md">Publish the location database from Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="1f9ff-111">Esta sección describe qué debe tener en cuenta cuando planea la actualización y el mantenimiento de la base de datos de ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="1f9ff-111">This section describes things to consider as you plan to update and maintain the location database.</span></span>

<div>

## <a name="planning-emergency-locations"></a><span data-ttu-id="1f9ff-112">Planear las ubicaciones de emergencia</span><span class="sxs-lookup"><span data-stu-id="1f9ff-112">Planning Emergency Locations</span></span>

<span data-ttu-id="1f9ff-113">Cuando use puertas de enlace ELIN, rellene la base de datos del servicio de información de ubicaciones con la dirección cívica, una ubicación específica dentro de un edificio y al menos una ELIN para cada ubicación.</span><span class="sxs-lookup"><span data-stu-id="1f9ff-113">When you use ELIN gateways, you populate the Location Information service database with the civic address, a specific location within a building, and at least one ELIN for each location .</span></span> <span data-ttu-id="1f9ff-114">Durante la fase de planeación, le recomendamos que decida el nombre que quiere dar a las ubicaciones y cómo desea asignar los ELIN.</span><span class="sxs-lookup"><span data-stu-id="1f9ff-114">During the planning phase, it is a good idea to decide how you want to name the locations and how you want to assign ELINs.</span></span>

<div>

## <a name="planning-location-names"></a><span data-ttu-id="1f9ff-115">Planear nombres de ubicación</span><span class="sxs-lookup"><span data-stu-id="1f9ff-115">Planning Location Names</span></span>

<span data-ttu-id="1f9ff-116">El campo **Ubicación** del servicio de información de ubicación, que contiene la ubicación específica dentro de un edificio, tiene una longitud máxima de 20 caracteres (espacios incluidos).</span><span class="sxs-lookup"><span data-stu-id="1f9ff-116">The Location Information service **Location** field, which holds the specific location within a building, has a maximum length of 20 characters (including spaces).</span></span> <span data-ttu-id="1f9ff-117">Dentro de esa longitud limitada, intente incluir lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="1f9ff-117">Within that limited length, try to include the following:</span></span>

  - <span data-ttu-id="1f9ff-p104">Un nombre fácil de comprender que identifique la ubicación del autor de la llamada al 911 para que a los encargados de emergencias les resulte más fácil encontrar rápidamente la ubicación específica cuando lleguen a la dirección postal. Este nombre de ubicación puede incluir un número de edificio, la planta, la escalera, la puerta, etc. Evite los apodos que solo conozcan los empleados, ya que los encargados de emergencias podrían equivocarse de ubicación.</span><span class="sxs-lookup"><span data-stu-id="1f9ff-p104">An easy-to-understand name that identifies the location of the 911 caller to help ensure that emergency responders find the specific location promptly when they arrive at the civic address. This location name may include a building number, floor number, wing designator, room number, and so on. Avoid nicknames that are known only to employees, which might cause emergency responders to go to the wrong location.</span></span>

  - <span data-ttu-id="1f9ff-121">Un identificador de ubicación para que a los usuarios les resulte más fácil ver que su cliente de Lync eligió la ubicación correcta.</span><span class="sxs-lookup"><span data-stu-id="1f9ff-121">A location identifier that helps users to easily see that their Lync client picked up the correct location.</span></span> <span data-ttu-id="1f9ff-122">El cliente de Lync concatena y muestra automáticamente los campos **Location** y **City** en el encabezado.</span><span class="sxs-lookup"><span data-stu-id="1f9ff-122">The Lync client automatically concatenates and displays the discovered **Location** and **City** fields in its header.</span></span> <span data-ttu-id="1f9ff-123">Un procedimiento recomendado es agregar la dirección de la calle del edificio a cada identificador de ubicación (por ejemplo, "número \<\>de calle del 1 piso").</span><span class="sxs-lookup"><span data-stu-id="1f9ff-123">A good practice is to add the street address of the building to each location identifier (for example, "1st Floor \<street number\>").</span></span> <span data-ttu-id="1f9ff-124">Si no se indica la calle, un identificador de ubicación genérico como "1ª planta" se podría aplicar a cualquier edificio de la ciudad.</span><span class="sxs-lookup"><span data-stu-id="1f9ff-124">Without the street address, a generic location identifier such as "1st Floor" could apply to any building in the city.</span></span>

  - <span data-ttu-id="1f9ff-125">Si la ubicación es aproximativa, porque se determina con un punto de acceso inalámbrico, agregue la palabra Near (por ejemplo, "Cerca 1ª planta 1234").</span><span class="sxs-lookup"><span data-stu-id="1f9ff-125">If the location is approximate because it’s determined by a wireless access point, you may want to add the word Near (for example, "Near 1st Floor 1234").</span></span>

</div>

<div>

## <a name="planning-elins"></a><span data-ttu-id="1f9ff-126">Planear ELIN</span><span class="sxs-lookup"><span data-stu-id="1f9ff-126">Planning ELINs</span></span>

<span data-ttu-id="1f9ff-p106">Después de decidir cómo va a dividir el espacio del edificio en ubicaciones, decida cuántos ELIN asignará a cada ubicación. Por ejemplo, en un edificio de varias plantas o inquilinos, puede haber diferentes zonas de emergencia para las diversas áreas del edificio. Por lo general, se considera que cada planta de un edificio es una ubicación. Después, asigne a cada ubicación uno o más ELIN, que se usan como número de llamada durante una llamada de emergencia. Póngase en contacto con el proveedor de RTC para que le dé los números de teléfono para los ELIN. La tabla siguiente proporciona un ejemplo de ubicaciones para una dirección postal concreta.</span><span class="sxs-lookup"><span data-stu-id="1f9ff-p106">After you decide how you want to divide your building space into locations, you need to decide how many ELINs to assign to each location. For example, in a multifloor or multitenant building, different areas in the building can be assigned different emergency zones. Typically, each floor in a building is designated as a location. Each location is then assigned one or more ELINs, which are used as the calling number(s) during an emergency call. Contact your PSTN carrier for phone numbers that you can use for ELINs. The following table provides an example of locations for a specific street address.</span></span>

### <a name="sample-location-and-elin-assignments"></a><span data-ttu-id="1f9ff-133">Ubicación y asignaciones ELIN de ejemplo</span><span class="sxs-lookup"><span data-stu-id="1f9ff-133">Sample Location and ELIN Assignments</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1f9ff-134">Área del edificio</span><span class="sxs-lookup"><span data-stu-id="1f9ff-134">Building Area</span></span></th>
<th><span data-ttu-id="1f9ff-135">Ubicación</span><span class="sxs-lookup"><span data-stu-id="1f9ff-135">Location</span></span></th>
<th><span data-ttu-id="1f9ff-136">ELIN</span><span class="sxs-lookup"><span data-stu-id="1f9ff-136">ELIN</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1f9ff-137">Primera planta</span><span class="sxs-lookup"><span data-stu-id="1f9ff-137">First floor</span></span></p></td>
<td><p><span data-ttu-id="1f9ff-138">1</span><span class="sxs-lookup"><span data-stu-id="1f9ff-138">1</span></span></p></td>
<td><p><span data-ttu-id="1f9ff-139">425-555-0100</span><span class="sxs-lookup"><span data-stu-id="1f9ff-139">425-555-0100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f9ff-140">Segunda planta</span><span class="sxs-lookup"><span data-stu-id="1f9ff-140">Second floor</span></span></p></td>
<td><p><span data-ttu-id="1f9ff-141">segundo</span><span class="sxs-lookup"><span data-stu-id="1f9ff-141">2</span></span></p></td>
<td><p><span data-ttu-id="1f9ff-142">425-555-0111</span><span class="sxs-lookup"><span data-stu-id="1f9ff-142">425-555-0111</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f9ff-143">Tercera planta</span><span class="sxs-lookup"><span data-stu-id="1f9ff-143">Third floor</span></span></p></td>
<td><p><span data-ttu-id="1f9ff-144">3</span><span class="sxs-lookup"><span data-stu-id="1f9ff-144">3</span></span></p></td>
<td><p><span data-ttu-id="1f9ff-145">425-555-0123</span><span class="sxs-lookup"><span data-stu-id="1f9ff-145">425-555-0123</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="1f9ff-146">Las ubicaciones que defina deben:</span><span class="sxs-lookup"><span data-stu-id="1f9ff-146">The locations you define should meet the following requirements:</span></span>

  - <span data-ttu-id="1f9ff-147">Cumplir las normativas nacionales o regionales en cuanto al área máxima por ubicación y número de ubicaciones por dirección postal.</span><span class="sxs-lookup"><span data-stu-id="1f9ff-147">Comply with local and national/regional regulations in terms of maximum area per location and number of locations per street address.</span></span>

  - <span data-ttu-id="1f9ff-148">Tener la concreción suficiente como para que sea fácil ubicar a la persona que realiza la llamada de emergencia.</span><span class="sxs-lookup"><span data-stu-id="1f9ff-148">Are specific enough to make it easy to locate the emergency caller.</span></span>

</div>

</div>

<div>

## <a name="populating-the-location-database"></a><span data-ttu-id="1f9ff-149">Rellenar la base de datos de ubicaciones</span><span class="sxs-lookup"><span data-stu-id="1f9ff-149">Populating the Location Database</span></span>

<span data-ttu-id="1f9ff-150">Con las siguientes preguntas le será más fácil determinar cómo rellenar la base de datos de ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="1f9ff-150">The following questions will help you determine how to will populate the location database.</span></span>

  - <span data-ttu-id="1f9ff-151">**¿Qué proceso usará para rellenar la base de datos de ubicaciones?**</span><span class="sxs-lookup"><span data-stu-id="1f9ff-151">**What process will you use to populate the location database?**</span></span>  
    <span data-ttu-id="1f9ff-p107">¿Dónde se encuentran los datos y qué pasos debe realizar para convertirlos al formato que necesita la base de datos de ubicaciones? ¿Agregará las ubicaciones una por una o en bloque con un archivo CSV?</span><span class="sxs-lookup"><span data-stu-id="1f9ff-p107">Where does the data exist, and what steps do you need to take to convert the data into the format required by the location database? Will you add locations individually, or in bulk, by using a CSV file?</span></span>

<!-- end list -->

  - <span data-ttu-id="1f9ff-154">**¿Dispone de una base de datos de otros fabricantes que ya contenga una asignación de ubicaciones?**</span><span class="sxs-lookup"><span data-stu-id="1f9ff-154">**Do you have a third party database that already contains a mapping of locations?**</span></span>  
    <span data-ttu-id="1f9ff-155">Mediante el uso de la opción servicio de información de ubicación secundaria de Lync Server para conectarse a una base de datos de terceros, puede agrupar y administrar las ubicaciones mediante una plataforma sin conexión.</span><span class="sxs-lookup"><span data-stu-id="1f9ff-155">By using Lync Server's Secondary Location Information service option to connect to a third-party database, you can group and manage locations by using an offline platform.</span></span> <span data-ttu-id="1f9ff-156">La ventana es que además de asociar las ubicaciones a identificadores de red, puede asociar las ubicaciones a un usuario.</span><span class="sxs-lookup"><span data-stu-id="1f9ff-156">A benefit to this approach is that in addition to associating locations to network identifiers, you can associate locations to a user.</span></span> <span data-ttu-id="1f9ff-157">Esto significa que el servicio de información de ubicación puede devolver varias direcciones, que se originan del servicio de información de ubicación secundario, a un cliente de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1f9ff-157">This means that the Location Information service can return multiple addresses, originating from the Secondary Location Information service, to a Lync Server client.</span></span> <span data-ttu-id="1f9ff-158">Y el usuario puede elegir la ubicación más adecuada.</span><span class="sxs-lookup"><span data-stu-id="1f9ff-158">The user can then choose the most appropriate location.</span></span>
    
    <span data-ttu-id="1f9ff-159">Para integrarse con el servicio de información de ubicaciones, la base de datos de terceros debe seguir el esquema de solicitud y respuesta de la ubicación de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1f9ff-159">To integrate with the Location Information service, the third-party database must follow the Lync Server Location Request/Response schema.</span></span> <span data-ttu-id="1f9ff-160">Para obtener más información <https://go.microsoft.com/fwlink/p/?linkid=213819>, consulte.</span><span class="sxs-lookup"><span data-stu-id="1f9ff-160">For details, see <https://go.microsoft.com/fwlink/p/?linkid=213819>.</span></span> <span data-ttu-id="1f9ff-161">Para obtener más información sobre cómo implementar un servicio de información de ubicaciones secundarias, vea [configurar un servicio de información de ubicaciones secundarias en Lync Server 2013](lync-server-2013-configure-a-secondary-location-information-service.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="1f9ff-161">For details about deploying a Secondary Location Information service, see [Configure a secondary Location Information service in Lync Server 2013](lync-server-2013-configure-a-secondary-location-information-service.md) in the Deployment documentation.</span></span>

<span data-ttu-id="1f9ff-162">Para obtener información detallada sobre cómo rellenar la base de datos de ubicaciones, consulte [Configure The location Database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="1f9ff-162">For details about populating the location database, see [Configure the location database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="maintaining-the-location-database"></a><span data-ttu-id="1f9ff-163">Mantener la base de datos de ubicaciones</span><span class="sxs-lookup"><span data-stu-id="1f9ff-163">Maintaining the Location Database</span></span>

<span data-ttu-id="1f9ff-p110">Una vez rellenada la base de datos de ubicaciones, desarrolle una estrategia para actualizar la base de datos a medida que se produzcan cambios en la configuración de red. Con las siguientes preguntas le será fácil determinar cómo mantener la base de datos de ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="1f9ff-p110">After you populate the location database, you need to develop a strategy for updating the database as the network configuration changes. The following questions will help you determine how to maintain the location database.</span></span>

  - <span data-ttu-id="1f9ff-166">**¿Cómo actualizará la base de datos de ubicaciones?**</span><span class="sxs-lookup"><span data-stu-id="1f9ff-166">**How will you update the location database?**</span></span>  
    <span data-ttu-id="1f9ff-p111">Existen diversos escenarios que requieren una actualización de la base de datos de ubicaciones, como agregar puntos de acceso inalámbricos (WAP), cambiar el cableado de una oficina (lo que da lugar a asignaciones de conmutador diferentes) o la expansión de subredes. ¿Actualizará directamente cada ubicación individual o llevará a cabo una actualización en bloque de todas las ubicaciones con un archivo CSV?</span><span class="sxs-lookup"><span data-stu-id="1f9ff-p111">There are several scenarios that require an update to the location database, including adding wireless access points (WAPs), office recabling (resulting in different switch assignments), and subnet expansion. Will you directly update each individual location, or will you perform a bulk update of all the locations by using a CSV file?</span></span>

<!-- end list -->

  - <span data-ttu-id="1f9ff-169">**¿Usará una aplicación SNMP para hacer coincidir las direcciones MAC clientes de Lync con los identificadores de conmutadores y puertos?**</span><span class="sxs-lookup"><span data-stu-id="1f9ff-169">**Will you use an SNMP application to match Lync client MAC addresses to port and switch identifiers?**</span></span>  
    <span data-ttu-id="1f9ff-170">Si usa una aplicación SNMP, desarrolle un proceso manual para que la información de chasis de conmutador y de puerto sea coherente entre la aplicación SNMP y la base de datos de ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="1f9ff-170">If you use an SNMP application, you need to develop a manual process for keeping the switch chassis and port information consistent between the SNMP application and the location database.</span></span> <span data-ttu-id="1f9ff-171">Si la aplicación SNMP devuelve una dirección IP o identificador de puerto del chasis que no está incluido en la base de datos, el servicio de información de ubicación no podrá devolver una ubicación al cliente.</span><span class="sxs-lookup"><span data-stu-id="1f9ff-171">If the SNMP application returns a chassis IP address or port ID that is not included in the database, the Location Information service will not be able to return a location to the client.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

