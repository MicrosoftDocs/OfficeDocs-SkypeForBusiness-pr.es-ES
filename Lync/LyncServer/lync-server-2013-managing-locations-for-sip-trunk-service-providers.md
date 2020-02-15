---
title: 'Lync Server 2013: administración de ubicaciones para proveedores de servicio de tronco SIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing locations for SIP trunk service providers
ms:assetid: d9b33b56-66c2-4dee-b056-faaf98925bf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398959(v=OCS.15)
ms:contentKeyID: 48185548
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d2ffa9b16a2c582af2de990eab52b55c175121bc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042557"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-locations-for-sip-trunk-service-providers-in-lync-server-2013"></a><span data-ttu-id="2ad26-102">Administración de ubicaciones para proveedores de servicio de tronco de SIP en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2ad26-102">Managing locations for SIP trunk service providers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2ad26-103">_**Última modificación del tema:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="2ad26-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="2ad26-104">Para configurar Lync Server para ubicar automáticamente los clientes dentro de una red, debe rellenar la base de datos del servicio de información de ubicación con un cableado de red y publicar las ubicaciones o un vínculo a una base de datos externa que ya contenga la configuración correcta. asignaciones.</span><span class="sxs-lookup"><span data-stu-id="2ad26-104">To configure Lync Server to automatically locate clients within a network, you need to either populate the Location Information service database with a network wiremap and publish the locations, or link to an external database that already contains the correct mappings.</span></span> <span data-ttu-id="2ad26-105">Como parte de este proceso, valide las direcciones con el proveedor de servicios de E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="2ad26-105">As part of this process, you need to validate the civic addresses of the locations with your E9-1-1 service provider.</span></span> <span data-ttu-id="2ad26-106">Para obtener más información, consulte [configurar la base de datos de ubicaciones en Lync Server 2013](lync-server-2013-configure-the-location-database.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="2ad26-106">For details, see [Configure the location database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) in the Deployment documentation.</span></span>

<span data-ttu-id="2ad26-107">Rellene la base de datos del servicio de información de ubicaciones con una ubicación de respuesta de emergencia (ERL), formada por una dirección postal y la dirección específica en un edificio.</span><span class="sxs-lookup"><span data-stu-id="2ad26-107">You populate the Location Information service database with an Emergency Response Location (ERL), which consists of a civic address and the specific address within a building.</span></span> <span data-ttu-id="2ad26-108">El campo **Ubicación** del servicio de información de ubicación, que es la ubicación específica dentro de un edificio, tiene una longitud máxima de 20 caracteres (espacios incluidos).</span><span class="sxs-lookup"><span data-stu-id="2ad26-108">The Location Information service **Location** field, which is the specific location within a building, has a maximum length of 20 characters (including spaces).</span></span> <span data-ttu-id="2ad26-109">Dentro de esa longitud limitada, intente incluir lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2ad26-109">Within that limited length, try to include the following:</span></span>

  - <span data-ttu-id="2ad26-p103">Un nombre fácil de entender que identifique la ubicación del autor de la llamada al 911 para garantizar que los servicios de emergencias encuentren la ubicación específica rápidamente una vez que estos lleguen a la dirección postal. Este nombre de ubicación puede incluir un número de edificio, un número de piso, un indicador de ala, un número de habitación, entre otros elementos. Evite nombres conocidos solo por los empleados, ya que podrían causar que los servicios de emergencia se dirijan a una ubicación equivocada.</span><span class="sxs-lookup"><span data-stu-id="2ad26-p103">An easy-to-understand name that identifies the location of the 911 caller to help ensure that emergency responders find the specific location promptly when they arrive at the civic address. This location name may include a building number, floor number, wing designator, room number, and so on. Avoid nicknames known only to employees, which might cause emergency responders to go to the wrong location.</span></span>

  - <span data-ttu-id="2ad26-113">Un identificador de ubicación para que a los usuarios les resulte más fácil ver que su cliente de Lync eligió la ubicación correcta.</span><span class="sxs-lookup"><span data-stu-id="2ad26-113">A location identifier that helps users to easily see that their Lync client picked up the correct location.</span></span> <span data-ttu-id="2ad26-114">El cliente de Lync concatena y muestra automáticamente los campos **Location** y **City** en el encabezado.</span><span class="sxs-lookup"><span data-stu-id="2ad26-114">The Lync client automatically concatenates and displays the discovered **Location** and **City** fields in its header.</span></span> <span data-ttu-id="2ad26-115">Un procedimiento recomendado es agregar la dirección de la calle del edificio a cada identificador de ubicación (por ejemplo, "número \<\>de calle del 1 piso").</span><span class="sxs-lookup"><span data-stu-id="2ad26-115">A good practice is to add the street address of the building to each location identifier (for example, "1st Floor \<street number\>").</span></span> <span data-ttu-id="2ad26-116">Si no se indica la calle, un identificador de ubicación genérico como "1ª planta" se podría aplicar a cualquier edificio de la ciudad.</span><span class="sxs-lookup"><span data-stu-id="2ad26-116">Without the street address, a generic location identifier such as "1st Floor" could apply to any building in the city.</span></span>

  - <span data-ttu-id="2ad26-117">Si la ubicación es aproximada porque está determinada por un punto de acceso inalámbrico, añada la palabra Near, por ejemplo, Cerca del 1r piso 1234.</span><span class="sxs-lookup"><span data-stu-id="2ad26-117">If the location is approximate because it’s determined by a wireless access point, you can add the word Near (for example, "Near 1st Floor 1234").</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2ad26-118">Las ubicaciones que se agregan a la base de datos de ubicaciones centrales no están disponibles para el cliente hasta que se publican mediante un comando del shell de administración de Lync Server y se replican en los almacenes locales del grupo.</span><span class="sxs-lookup"><span data-stu-id="2ad26-118">Locations added to the central location database are not available to the client until they are published by using a Lync Server Management Shell command and are replicated to the pool's local stores.</span></span> <span data-ttu-id="2ad26-119">Para obtener más información, consulte <A href="lync-server-2013-publish-the-location-database.md">publicar la base de datos de ubicaciones en Lync Server 2013</A> en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="2ad26-119">For details, see <A href="lync-server-2013-publish-the-location-database.md">Publish the location database from Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="2ad26-120">En las secciones siguientes se describen consideraciones que debe tener en cuenta a la hora de rellenar y mantener la base de datos de ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="2ad26-120">The following sections discuss considerations that you need to take into account when populating and maintaining the location database.</span></span>

<div>

## <a name="populating-the-location-database"></a><span data-ttu-id="2ad26-121">Rellenar la base de datos de ubicaciones</span><span class="sxs-lookup"><span data-stu-id="2ad26-121">Populating the Location Database</span></span>

<span data-ttu-id="2ad26-122">Con las siguientes preguntas le será fácil determinar cómo rellenar la base de datos de ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="2ad26-122">The following questions can help you determine how to populate the location database.</span></span>

  - <span data-ttu-id="2ad26-123">**¿Qué proceso usará para rellenar la base de datos de ubicaciones?**</span><span class="sxs-lookup"><span data-stu-id="2ad26-123">**What process will you use to populate the location database?**</span></span>  
    <span data-ttu-id="2ad26-p106">¿Dónde se encuentran los datos y qué pasos debe realizar para convertirlos al formato que necesita la base de datos de ubicaciones? ¿Agregará las ubicaciones una por una o en bloque con un archivo CSV?</span><span class="sxs-lookup"><span data-stu-id="2ad26-p106">Where does the data exist, and what steps do you need to take to convert the data into the format required by the location database? Will you add locations individually, or in bulk, by using a CSV file?</span></span>

<!-- end list -->

  - <span data-ttu-id="2ad26-126">**¿Dispone de una base de datos de otros fabricantes que ya contenga una asignación de ubicaciones?**</span><span class="sxs-lookup"><span data-stu-id="2ad26-126">**Do you have a third party database that already contains a mapping of locations?**</span></span>  
    <span data-ttu-id="2ad26-127">Mediante el uso de la opción servicio de información de ubicación secundaria de Lync Server para conectarse a una base de datos de terceros, puede agrupar y administrar las ubicaciones mediante una plataforma sin conexión.</span><span class="sxs-lookup"><span data-stu-id="2ad26-127">By using Lync Server's Secondary Location Information service option to connect to a third-party database, you can group and manage locations by using an offline platform.</span></span> <span data-ttu-id="2ad26-128">La ventana es que además de asociar las ubicaciones a identificadores de red, puede asociar las ubicaciones a un usuario.</span><span class="sxs-lookup"><span data-stu-id="2ad26-128">A benefit to this approach is that in addition to associating locations to network identifiers, you can associate locations to a user.</span></span> <span data-ttu-id="2ad26-129">Esto significa que el servicio de información de ubicación puede devolver varias direcciones, que se originan del servicio de información de ubicación secundario, a un cliente de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2ad26-129">This means that the Location Information service can return multiple addresses, originating from the Secondary Location Information service, to a Lync Server client.</span></span> <span data-ttu-id="2ad26-130">Y el usuario puede elegir la ubicación más adecuada.</span><span class="sxs-lookup"><span data-stu-id="2ad26-130">The user can then choose the most appropriate location.</span></span>
    
    <span data-ttu-id="2ad26-131">Para integrarse con el servicio de información de ubicaciones, la base de datos de terceros debe seguir el esquema de solicitud y respuesta de la ubicación de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2ad26-131">To integrate with the Location Information service, the third-party database must follow the Lync Server Location Request/Response schema.</span></span> <span data-ttu-id="2ad26-132">Para obtener más información,\[consulte "MS\]-E911WS: servicio web para la especificación del protocolo <http://go.microsoft.com/fwlink/p/?linkid=213819>de soporte de E911" en.</span><span class="sxs-lookup"><span data-stu-id="2ad26-132">For details, see "\[MS-E911WS\]: Web Service for E911 Support Protocol Specification" at <http://go.microsoft.com/fwlink/p/?linkid=213819>.</span></span> <span data-ttu-id="2ad26-133">Para obtener más información sobre cómo implementar un servicio de información de ubicaciones secundarias, vea [configurar un servicio de información de ubicaciones secundarias en Lync Server 2013](lync-server-2013-configure-a-secondary-location-information-service.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="2ad26-133">For details about deploying a Secondary Location Information service, see [Configure a secondary Location Information service in Lync Server 2013](lync-server-2013-configure-a-secondary-location-information-service.md) in the Deployment documentation.</span></span>

<span data-ttu-id="2ad26-134">Para obtener información detallada sobre cómo rellenar la base de datos de ubicaciones, consulte [Configure The location Database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="2ad26-134">For details about populating the location database, see [Configure the location database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="maintaining-the-location-database"></a><span data-ttu-id="2ad26-135">Mantener la base de datos de ubicaciones</span><span class="sxs-lookup"><span data-stu-id="2ad26-135">Maintaining the Location Database</span></span>

<span data-ttu-id="2ad26-p109">Una vez rellenada la base de datos de ubicaciones, desarrolle una estrategia para actualizar la base de datos a medida que se produzcan cambios en la configuración de red. Con las siguientes preguntas le será fácil determinar cómo mantener la base de datos de ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="2ad26-p109">After you populate the location database, you need to develop a strategy for updating the database as the network configuration changes. The following questions will help you determine how to maintain the location database.</span></span>

  - <span data-ttu-id="2ad26-138">**¿Cómo actualizará la base de datos de ubicaciones?**</span><span class="sxs-lookup"><span data-stu-id="2ad26-138">**How will you update the location database?**</span></span>  
    <span data-ttu-id="2ad26-p110">Existen diversos escenarios que requieren una actualización de la base de datos de ubicaciones, como agregar WAP, cambiar el cableado de una oficina (lo que da lugar a asignaciones de conmutador nuevas) y la expansión de subredes. ¿Actualizará directamente cada ubicación o llevará a cabo una actualización en bloque de todas las ubicaciones con un archivo CSV?</span><span class="sxs-lookup"><span data-stu-id="2ad26-p110">There are several scenarios that require an update to the location database, including adding WAPs, office recabling (resulting in different switch assignments), and subnet expansion. Will you directly update each individual location, or will you perform a bulk update of all the locations by using a CSV file?</span></span>

<!-- end list -->

  - <span data-ttu-id="2ad26-141">**¿Usará una aplicación SNMP para hacer coincidir las direcciones MAC con la información de conmutadores y puertos?**</span><span class="sxs-lookup"><span data-stu-id="2ad26-141">**Will you use an SNMP application to match Lync client MAC addresses to port and switch identifiers?**</span></span>  
    <span data-ttu-id="2ad26-142">Si usa una aplicación SNMP, desarrolle un proceso manual para que la información de chasis de conmutador y de puerto sea coherente entre la aplicación SNMP y la base de datos de ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="2ad26-142">If you use an SNMP application, you need to develop a manual process for keeping the switch chassis and port information consistent between the SNMP application and the location database.</span></span> <span data-ttu-id="2ad26-143">Si la aplicación SNMP devuelve una dirección IP o identificador de puerto del chasis que no está incluido en la base de datos, el servicio de información de ubicación no podrá devolver una ubicación al cliente.</span><span class="sxs-lookup"><span data-stu-id="2ad26-143">If the SNMP application returns a chassis IP address or port ID that is not included in the database, the Location Information service will not be able to return a location to the client.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

