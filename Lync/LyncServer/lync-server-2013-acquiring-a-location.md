---
title: 'Lync Server 2013: Adquirir una ubicación'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Acquiring a location
ms:assetid: 9bf069aa-d240-4d95-be3a-e795537f8e70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205110(v=OCS.15)
ms:contentKeyID: 48184903
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e54c7032973f75922f6c6893a0c758409ec945be
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723370"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="acquiring-a-location-in-lync-server-2013"></a><span data-ttu-id="bf415-102">Adquirir una ubicación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bf415-102">Acquiring a location in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bf415-103">_**Última modificación del tema:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="bf415-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="bf415-104">En una implementación de Lync Server 2013 E9-1-1, cada cliente de Lync o Lync Phone Edition conectado internamente adquiere su propia ubicación.</span><span class="sxs-lookup"><span data-stu-id="bf415-104">In a Lync Server 2013 E9-1-1 deployment, each internally-connected Lync or Lync Phone Edition client actively acquires its own location.</span></span> <span data-ttu-id="bf415-105">Después del registro SIP, el cliente brinda toda la información de conectividad de red que él conoce sobre él en una solicitud de ubicación en el servicio de información de ubicación, que es un servicio Web respaldado por una base de datos de SQL Server replicada.</span><span class="sxs-lookup"><span data-stu-id="bf415-105">After SIP registration, the client furnishes all the network connectivity information that it knows about itself it in a location request to the Location Information service, which is a web service backed by a replicated SQL Server database.</span></span> <span data-ttu-id="bf415-106">Cada grupo de sitios central tiene un servicio de información de ubicación, que usa la información de la red para consultar sus registros en busca de una ubicación coincidente.</span><span class="sxs-lookup"><span data-stu-id="bf415-106">Each central site pool has a Location Information service, which uses the network information to query its records for a matching location.</span></span> <span data-ttu-id="bf415-107">Si hay una coincidencia, el servicio de información de ubicación devuelve una ubicación al cliente.</span><span class="sxs-lookup"><span data-stu-id="bf415-107">If there is a match, the Location Information service returns a location to the client.</span></span> <span data-ttu-id="bf415-108">Si no hay una coincidencia, puede que se pida al usuario que escriba una ubicación manualmente (según la configuración de la directiva de ubicación).</span><span class="sxs-lookup"><span data-stu-id="bf415-108">If there is not a match, the user may be prompted to enter a location manually (depending on location policy settings).</span></span> <span data-ttu-id="bf415-109">Los datos de ubicación se transmiten de vuelta al cliente en un formato XML estandarizado del Grupo de trabajo de ingeniería de Internet (IETF) conocido como Objeto de ubicación para formato de datos de información sobre presencia (PIDF-LO).</span><span class="sxs-lookup"><span data-stu-id="bf415-109">The location data are transmitted back to the client in an Internet Engineering Task Force (IETF) standardized XML format called Presence Information Data Format Location Object (PIDF-LO).</span></span>

<span data-ttu-id="bf415-110">El cliente de Lync Server incluye los datos de PIDF como parte de una llamada de emergencia y el proveedor de servicios E9-1-1 usa estos datos para determinar el PSAP adecuado y enrutar la llamada a ese PSAP junto con el ESQK correcto, lo que permite al PSAP distribuidor obtener el Ubicación del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="bf415-110">The Lync Server client includes the PIDF-LO data as part of an emergency call, and this data is used by the E9-1-1 service provider to determine the appropriate PSAP and route the call to that PSAP along with the correct ESQK, which allows the PSAP dispatcher to obtain the caller’s location.</span></span>

<span data-ttu-id="bf415-111">En el siguiente diagrama se muestra cómo un cliente de Lync Server adquiere una ubicación (excepto para el método de ubicación basado en direcciones MAC del cliente de terceros):</span><span class="sxs-lookup"><span data-stu-id="bf415-111">The following diagram shows how a Lync Server client acquires a location (except for the third-party client MAC address–based location method):</span></span>

<span data-ttu-id="bf415-112">![Diagrama sobre cómo adquiere una ubicación el cliente](images/JJ205110.4438f5fc-f1b2-444b-8565-09035363ed43(OCS.15).jpg "Diagrama sobre cómo adquiere una ubicación el cliente")</span><span class="sxs-lookup"><span data-stu-id="bf415-112">![How Client Acquires a Location diagram](images/JJ205110.4438f5fc-f1b2-444b-8565-09035363ed43(OCS.15).jpg "How Client Acquires a Location diagram")</span></span>

<span data-ttu-id="bf415-113">Para que un cliente adquiera una ubicación, es preciso seguir estos pasos:</span><span class="sxs-lookup"><span data-stu-id="bf415-113">For a client to acquire a location, the following steps must take place:</span></span>

1.  <span data-ttu-id="bf415-114">El administrador rellena la base de datos del servicio de información de ubicación con el Wiremap de red (tablas que asignan varios tipos de direcciones de red a las ubicaciones de respuesta de emergencia correspondientes (ERLs)).</span><span class="sxs-lookup"><span data-stu-id="bf415-114">The administrator populates the Location Information service database with the network wiremap (tables that map various types of network addresses to corresponding Emergency Response Locations (ERLs)).</span></span>

2.  <span data-ttu-id="bf415-p102">Si utiliza un proveedor de servicio E9-1-1 para troncos SIP, el administrador validará las partes de dirección postal de las ERL con una base de datos de guía de direcciones principal (MSAG) mantenida por el proveedor del servicio E9-1-1. Si utiliza una puerta de enlace ELIN, el administrador se asegurará de que la portadora RTC cargue las ELIN a la base de datos de identificación automática de ubicaciones (ALI).</span><span class="sxs-lookup"><span data-stu-id="bf415-p102">If you use a SIP trunk E9-1-1 service provider, the administrator validates the civic address portions of the ERLs against a Master Street Address Guide (MSAG) database maintained by the E9-1-1 service provider. If you use an ELIN gateway, the administrator ensures that the PSTN carrier uploads the ELINs to the Automatic Location Identification (ALI) database.</span></span>

3.  <span data-ttu-id="bf415-117">Durante el registro o cuando se produce un cambio en la red, un cliente conectado internamente envía una solicitud de ubicación que contiene las direcciones de red detectadas del cliente al servicio de información de ubicación.</span><span class="sxs-lookup"><span data-stu-id="bf415-117">During registration or whenever a network change occurs, an internally-connected client sends a location request that contains the client's discovered network addresses to the Location Information service.</span></span>

4.  <span data-ttu-id="bf415-118">El servicio de información de ubicación consulta sus registros publicados en busca de una ubicación y, si se encuentra una coincidencia, devuelve el ERL al cliente con el formato PIDF-es.</span><span class="sxs-lookup"><span data-stu-id="bf415-118">The Location Information service queries its published records for a location, and, if a match is found, returns the ERL to the client in PIDF-LO format.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

