---
title: 'Lync Server 2013: administración de ubicaciones de puertas de enlace de ELIN'
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
ms.openlocfilehash: ba5a7e9067e4cd59ca42e60c620dbb4e8ee5b901
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762108"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-locations-for-elin-gateways-in-lync-server-2013"></a><span data-ttu-id="25f69-102">Administrar ubicaciones de puertas de enlace de ELIN en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="25f69-102">Managing locations for ELIN gateways in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="25f69-103">_**Última modificación del tema:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="25f69-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="25f69-104">Para que Lync Server proporcione automáticamente ubicaciones para los clientes dentro de una red, debe realizar las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="25f69-104">To have Lync Server automatically provide locations for clients within a network, you need to perform the following tasks:</span></span>

  - <span data-ttu-id="25f69-105">Rellene la información de ubicación de la base de datos del servicio con un Wiremap de red e incluya los números de identificación de ubicación de emergencia (ELINs) en el campo NombreCompañía.</span><span class="sxs-lookup"><span data-stu-id="25f69-105">Populate the Location Information service database with a network wiremap, and include the Emergency Location Identification Numbers (ELINs) in the CompanyName field.</span></span>

  - <span data-ttu-id="25f69-106">Publica las ubicaciones para que estén disponibles para los clientes en tu red.</span><span class="sxs-lookup"><span data-stu-id="25f69-106">Publish the locations so that they are available for clients in your network.</span></span>

  - <span data-ttu-id="25f69-107">Carga los ELIN en la base de datos de identificación de ubicación automática (ALI) del proveedor de la red telefónica conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="25f69-107">Upload the ELINs to your public switched telephone network (PSTN) carrier's Automatic Location Identification (ALI) database.</span></span>

<span data-ttu-id="25f69-108">Para obtener más información sobre cómo realizar estas tareas, vea [configurar la base de datos de ubicaciones en Lync Server 2013](lync-server-2013-configure-the-location-database.md) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="25f69-108">For details about how to perform these tasks, see [Configure the location database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="25f69-109">Las ubicaciones que se agreguen a la base de datos de ubicación central no estarán disponibles para el cliente hasta que se hayan publicado mediante un comando de Shell de administración de Lync Server y se repliquen en las tiendas locales del grupo.</span><span class="sxs-lookup"><span data-stu-id="25f69-109">Locations added to the central location database are not available to the client until they have been published by using a Lync Server Management Shell command and are replicated to the pool's local stores.</span></span> <span data-ttu-id="25f69-110">Para obtener más información, vea <A href="lync-server-2013-publish-the-location-database.md">publicar la base de datos de ubicaciones de Lync Server 2013</A> en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="25f69-110">For details, see <A href="lync-server-2013-publish-the-location-database.md">Publish the location database from Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="25f69-111">Esta sección describe qué necesitas tener en cuenta cuando planificas la actualización y el mantenimiento de la base de datos de ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="25f69-111">This section describes things to consider as you plan to update and maintain the location database.</span></span>

<div>

## <a name="planning-emergency-locations"></a><span data-ttu-id="25f69-112">Planificar las ubicaciones de emergencia</span><span class="sxs-lookup"><span data-stu-id="25f69-112">Planning Emergency Locations</span></span>

<span data-ttu-id="25f69-113">Cuando use puertas de enlace ELIN, deberá rellenar la base de datos de servicios de información de ubicación con la dirección cívica, una ubicación específica dentro de un edificio y, al menos, una ELIN para cada ubicación.</span><span class="sxs-lookup"><span data-stu-id="25f69-113">When you use ELIN gateways, you populate the Location Information service database with the civic address, a specific location within a building, and at least one ELIN for each location .</span></span> <span data-ttu-id="25f69-114">Durante la fase de planificación, recomendamos que decidas el nombre que quieras dar a las ubicaciones y cómo deseas asignar los ELIN.</span><span class="sxs-lookup"><span data-stu-id="25f69-114">During the planning phase, it is a good idea to decide how you want to name the locations and how you want to assign ELINs.</span></span>

<div>

## <a name="planning-location-names"></a><span data-ttu-id="25f69-115">Planificar nombres de ubicación</span><span class="sxs-lookup"><span data-stu-id="25f69-115">Planning Location Names</span></span>

<span data-ttu-id="25f69-116">El campo **Ubicación** del servicio de información de ubicación, que contiene la ubicación específica dentro de un edificio, tiene una longitud máxima de 20 caracteres (incluidos los espacios).</span><span class="sxs-lookup"><span data-stu-id="25f69-116">The Location Information service **Location** field, which holds the specific location within a building, has a maximum length of 20 characters (including spaces).</span></span> <span data-ttu-id="25f69-117">Dentro de esa longitud limitada, intenta incluir lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="25f69-117">Within that limited length, try to include the following:</span></span>

  - <span data-ttu-id="25f69-p104">Un nombre fácil de comprender que identifique la ubicación del autor de la llamada al 911 para que a los encargados de emergencias les resulte más fácil encontrar rápidamente la ubicación específica cuando lleguen a la dirección postal. Este nombre de ubicación puede incluir un número de edificio, la planta, la escalera, la puerta, etc. Evita los apodos que solo conozcan los empleados, ya que los encargados de emergencias podrían equivocarse de ubicación.</span><span class="sxs-lookup"><span data-stu-id="25f69-p104">An easy-to-understand name that identifies the location of the 911 caller to help ensure that emergency responders find the specific location promptly when they arrive at the civic address. This location name may include a building number, floor number, wing designator, room number, and so on. Avoid nicknames that are known only to employees, which might cause emergency responders to go to the wrong location.</span></span>

  - <span data-ttu-id="25f69-121">Un identificador de ubicación que permite a los usuarios ver fácilmente que el cliente de Lync ha recogido la ubicación correcta.</span><span class="sxs-lookup"><span data-stu-id="25f69-121">A location identifier that helps users to easily see that their Lync client picked up the correct location.</span></span> <span data-ttu-id="25f69-122">El cliente de Lync concatena y muestra automáticamente los campos **Ubicación** detectada y **ciudad** en el encabezado.</span><span class="sxs-lookup"><span data-stu-id="25f69-122">The Lync client automatically concatenates and displays the discovered **Location** and **City** fields in its header.</span></span> <span data-ttu-id="25f69-123">Una buena práctica es agregar la dirección del edificio a cada identificador de ubicación (por ejemplo, "número \<\>de calle del primer piso").</span><span class="sxs-lookup"><span data-stu-id="25f69-123">A good practice is to add the street address of the building to each location identifier (for example, "1st Floor \<street number\>").</span></span> <span data-ttu-id="25f69-124">Sin la calle, un identificador genérico como "1.ª planta" podría referirse a cualquier edificio de la ciudad.</span><span class="sxs-lookup"><span data-stu-id="25f69-124">Without the street address, a generic location identifier such as "1st Floor" could apply to any building in the city.</span></span>

  - <span data-ttu-id="25f69-125">Si la ubicación es aproximada, porque se determina con un punto de acceso inalámbrico, agrega la palabra Near (por ejemplo, "Cerca 1.ª planta 1234").</span><span class="sxs-lookup"><span data-stu-id="25f69-125">If the location is approximate because it’s determined by a wireless access point, you may want to add the word Near (for example, "Near 1st Floor 1234").</span></span>

</div>

<div>

## <a name="planning-elins"></a><span data-ttu-id="25f69-126">Planificar ELIN</span><span class="sxs-lookup"><span data-stu-id="25f69-126">Planning ELINs</span></span>

<span data-ttu-id="25f69-p106">Después de decidir cómo vas a dividir el espacio del edificio en ubicaciones, necesitas decidir cuántos ELIN asignarás a cada ubicación. Por ejemplo, en un edificio de varias plantas o varios inquilinos, puede haber diferentes zonas de emergencia para las diversas áreas del edificio. Por lo general, se considera que cada planta de un edificio es una ubicación. Después, asigna a cada ubicación uno o más ELIN, que se usan como número(s) de llamada durante una llamada de emergencia. Ponte en contacto con tu proveedor de RTC para que te brinde los números de teléfono que puedes usar para los ELIN. La tabla siguiente proporciona un ejemplo de ubicaciones para una dirección postal concreta.</span><span class="sxs-lookup"><span data-stu-id="25f69-p106">After you decide how you want to divide your building space into locations, you need to decide how many ELINs to assign to each location. For example, in a multifloor or multitenant building, different areas in the building can be assigned different emergency zones. Typically, each floor in a building is designated as a location. Each location is then assigned one or more ELINs, which are used as the calling number(s) during an emergency call. Contact your PSTN carrier for phone numbers that you can use for ELINs. The following table provides an example of locations for a specific street address.</span></span>

### <a name="sample-location-and-elin-assignments"></a><span data-ttu-id="25f69-133">Ubicación y asignaciones de ELIN de ejemplo</span><span class="sxs-lookup"><span data-stu-id="25f69-133">Sample Location and ELIN Assignments</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="25f69-134">Área del edificio</span><span class="sxs-lookup"><span data-stu-id="25f69-134">Building Area</span></span></th>
<th><span data-ttu-id="25f69-135">Ubicación</span><span class="sxs-lookup"><span data-stu-id="25f69-135">Location</span></span></th>
<th><span data-ttu-id="25f69-136">ELIN</span><span class="sxs-lookup"><span data-stu-id="25f69-136">ELIN</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="25f69-137">Primera planta</span><span class="sxs-lookup"><span data-stu-id="25f69-137">First floor</span></span></p></td>
<td><p><span data-ttu-id="25f69-138">1</span><span class="sxs-lookup"><span data-stu-id="25f69-138">1</span></span></p></td>
<td><p><span data-ttu-id="25f69-139">425-555-0100</span><span class="sxs-lookup"><span data-stu-id="25f69-139">425-555-0100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25f69-140">Segunda planta</span><span class="sxs-lookup"><span data-stu-id="25f69-140">Second floor</span></span></p></td>
<td><p><span data-ttu-id="25f69-141">1</span><span class="sxs-lookup"><span data-stu-id="25f69-141">2</span></span></p></td>
<td><p><span data-ttu-id="25f69-142">425-555-0111</span><span class="sxs-lookup"><span data-stu-id="25f69-142">425-555-0111</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25f69-143">Tercera planta</span><span class="sxs-lookup"><span data-stu-id="25f69-143">Third floor</span></span></p></td>
<td><p><span data-ttu-id="25f69-144">3</span><span class="sxs-lookup"><span data-stu-id="25f69-144">3</span></span></p></td>
<td><p><span data-ttu-id="25f69-145">425-555-0123</span><span class="sxs-lookup"><span data-stu-id="25f69-145">425-555-0123</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="25f69-146">Las ubicaciones que definas necesitan:</span><span class="sxs-lookup"><span data-stu-id="25f69-146">The locations you define should meet the following requirements:</span></span>

  - <span data-ttu-id="25f69-147">Cumplir las normativas nacionales o regionales en cuanto al área máxima por ubicación y a la cantidad de ubicaciones por dirección postal.</span><span class="sxs-lookup"><span data-stu-id="25f69-147">Comply with local and national/regional regulations in terms of maximum area per location and number of locations per street address.</span></span>

  - <span data-ttu-id="25f69-148">Tener la precisión suficiente como para que sea fácil ubicar a la persona que realiza la llamada de emergencia.</span><span class="sxs-lookup"><span data-stu-id="25f69-148">Are specific enough to make it easy to locate the emergency caller.</span></span>

</div>

</div>

<div>

## <a name="populating-the-location-database"></a><span data-ttu-id="25f69-149">Rellenar la base de datos de ubicaciones</span><span class="sxs-lookup"><span data-stu-id="25f69-149">Populating the Location Database</span></span>

<span data-ttu-id="25f69-150">Con las siguientes preguntas te será más fácil determinar cómo rellenar la base de datos de ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="25f69-150">The following questions will help you determine how to will populate the location database.</span></span>

  - <span data-ttu-id="25f69-151">**¿Qué proceso usará para rellenar la base de datos de ubicaciones?**</span><span class="sxs-lookup"><span data-stu-id="25f69-151">**What process will you use to populate the location database?**</span></span>  
    <span data-ttu-id="25f69-p107">¿Dónde se encuentran los datos y qué pasos necesitas realizar para convertirlos al formato que necesita la base de datos de ubicaciones? ¿Agregarás las ubicaciones una por una o en bloque con un archivo CSV?</span><span class="sxs-lookup"><span data-stu-id="25f69-p107">Where does the data exist, and what steps do you need to take to convert the data into the format required by the location database? Will you add locations individually, or in bulk, by using a CSV file?</span></span>

<!-- end list -->

  - <span data-ttu-id="25f69-154">**¿Dispone de una base de datos de otros fabricantes que ya contenga una asignación de ubicaciones?**</span><span class="sxs-lookup"><span data-stu-id="25f69-154">**Do you have a third party database that already contains a mapping of locations?**</span></span>  
    <span data-ttu-id="25f69-155">Al usar la opción de servicio de información de ubicación secundaria de Lync Server para conectarse a una base de datos de terceros, puede agrupar y administrar ubicaciones mediante una plataforma sin conexión.</span><span class="sxs-lookup"><span data-stu-id="25f69-155">By using Lync Server's Secondary Location Information service option to connect to a third-party database, you can group and manage locations by using an offline platform.</span></span> <span data-ttu-id="25f69-156">La ventaja es que además de asociar las ubicaciones a identificadores de red, puedes asociar las ubicaciones a un usuario.</span><span class="sxs-lookup"><span data-stu-id="25f69-156">A benefit to this approach is that in addition to associating locations to network identifiers, you can associate locations to a user.</span></span> <span data-ttu-id="25f69-157">Esto significa que el servicio de información de ubicación puede devolver varias direcciones, que se originan en el servicio de información de ubicación secundaria, en un cliente de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="25f69-157">This means that the Location Information service can return multiple addresses, originating from the Secondary Location Information service, to a Lync Server client.</span></span> <span data-ttu-id="25f69-158">Luego, el usuario podrá elegir la ubicación más adecuada.</span><span class="sxs-lookup"><span data-stu-id="25f69-158">The user can then choose the most appropriate location.</span></span>
    
    <span data-ttu-id="25f69-159">Para integrar con el servicio de información de ubicación, la base de datos de terceros debe seguir el esquema de solicitud/respuesta de la ubicación de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="25f69-159">To integrate with the Location Information service, the third-party database must follow the Lync Server Location Request/Response schema.</span></span> <span data-ttu-id="25f69-160">Para obtener más información <http://go.microsoft.com/fwlink/p/?linkid=213819>, consulte.</span><span class="sxs-lookup"><span data-stu-id="25f69-160">For details, see <http://go.microsoft.com/fwlink/p/?linkid=213819>.</span></span> <span data-ttu-id="25f69-161">Para obtener detalles sobre cómo implementar un servicio de información de ubicación secundaria, vea [configurar un servicio de información de ubicación secundaria en Lync Server 2013](lync-server-2013-configure-a-secondary-location-information-service.md) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="25f69-161">For details about deploying a Secondary Location Information service, see [Configure a secondary Location Information service in Lync Server 2013](lync-server-2013-configure-a-secondary-location-information-service.md) in the Deployment documentation.</span></span>

<span data-ttu-id="25f69-162">Para obtener detalles sobre cómo rellenar la base de datos de ubicación, vea [configurar la base de datos de ubicaciones en Lync Server 2013](lync-server-2013-configure-the-location-database.md) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="25f69-162">For details about populating the location database, see [Configure the location database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="maintaining-the-location-database"></a><span data-ttu-id="25f69-163">Mantener la base de datos de ubicaciones</span><span class="sxs-lookup"><span data-stu-id="25f69-163">Maintaining the Location Database</span></span>

<span data-ttu-id="25f69-p110">Una vez rellenada la base de datos de ubicaciones, desarrolla una estrategia para actualizar la base de datos a medida que se produzcan cambios en la configuración de red. Con las siguientes preguntas te será fácil determinar cómo mantener la base de datos de ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="25f69-p110">After you populate the location database, you need to develop a strategy for updating the database as the network configuration changes. The following questions will help you determine how to maintain the location database.</span></span>

  - <span data-ttu-id="25f69-166">**¿Cómo actualizará la base de datos de ubicaciones?**</span><span class="sxs-lookup"><span data-stu-id="25f69-166">**How will you update the location database?**</span></span>  
    <span data-ttu-id="25f69-p111">Existen diversos escenarios que requieren una actualización de la base de datos de ubicaciones, como agregar puntos de acceso inalámbricos (WAP), cambiar el cableado de una oficina (lo que da lugar a asignaciones de conmutador diferentes) o la expansión de subredes. ¿Actualizarás directamente cada ubicación individual o llevarás a cabo una actualización en bloque de todas las ubicaciones con un archivo CSV?</span><span class="sxs-lookup"><span data-stu-id="25f69-p111">There are several scenarios that require an update to the location database, including adding wireless access points (WAPs), office recabling (resulting in different switch assignments), and subnet expansion. Will you directly update each individual location, or will you perform a bulk update of all the locations by using a CSV file?</span></span>

<!-- end list -->

  - <span data-ttu-id="25f69-169">**¿Usará una aplicación SNMP para hacer coincidir las direcciones MAC del cliente Lync con los identificadores de conmutadores y puertos?**</span><span class="sxs-lookup"><span data-stu-id="25f69-169">**Will you use an SNMP application to match Lync client MAC addresses to port and switch identifiers?**</span></span>  
    <span data-ttu-id="25f69-170">Si usas una aplicación SNMP, necesitas desarrollar un proceso manual para mantener sincronizada la información de conmutadores y puertos entre la aplicación SNMP y la base de datos de ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="25f69-170">If you use an SNMP application, you need to develop a manual process for keeping the switch chassis and port information consistent between the SNMP application and the location database.</span></span> <span data-ttu-id="25f69-171">Si la aplicación SNMP devuelve una dirección IP del chasis o un identificador de puerto que no está incluido en la base de datos, el servicio de información de ubicación no podrá devolver una ubicación al cliente.</span><span class="sxs-lookup"><span data-stu-id="25f69-171">If the SNMP application returns a chassis IP address or port ID that is not included in the database, the Location Information service will not be able to return a location to the client.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

