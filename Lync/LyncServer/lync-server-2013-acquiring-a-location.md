---
title: 'Lync Server 2013: adquisición de una ubicación'
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
ms.openlocfilehash: 5e5b3a6f9e781efbc3c8b7672ad28f1753490e17
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529747"
---
# <a name="acquiring-a-location-in-lync-server-2013"></a><span data-ttu-id="5792c-102">Adquirir una ubicación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5792c-102">Acquiring a location in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5792c-103">_**Última modificación del tema:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="5792c-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="5792c-104">En una implementación de Lync Server 2013 E9-1-1, cada cliente conectado internamente a Lync o Lync Phone Edition adquiere su propia ubicación de forma activa.</span><span class="sxs-lookup"><span data-stu-id="5792c-104">In a Lync Server 2013 E9-1-1 deployment, each internally-connected Lync or Lync Phone Edition client actively acquires its own location.</span></span> <span data-ttu-id="5792c-105">Después del registro SIP, el cliente facilita toda la información de conectividad de red que se conoce a sí misma en una solicitud de ubicación en el servicio de información de ubicaciones, que es un servicio Web respaldado por una base de datos replicada de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5792c-105">After SIP registration, the client furnishes all the network connectivity information that it knows about itself it in a location request to the Location Information service, which is a web service backed by a replicated SQL Server database.</span></span> <span data-ttu-id="5792c-106">Cada grupo de sitio central tiene un servicio de información de ubicación, que usa la información de red para consultar sus registros en busca de una ubicación coincidentes.</span><span class="sxs-lookup"><span data-stu-id="5792c-106">Each central site pool has a Location Information service, which uses the network information to query its records for a matching location.</span></span> <span data-ttu-id="5792c-107">Si hay una coincidencia, el servicio de información de ubicación devuelve una ubicación al cliente.</span><span class="sxs-lookup"><span data-stu-id="5792c-107">If there is a match, the Location Information service returns a location to the client.</span></span> <span data-ttu-id="5792c-108">Si no hay ninguna coincidencia, puede que se pida al usuario que escriba una ubicación manualmente (según la configuración de la directiva de ubicación).</span><span class="sxs-lookup"><span data-stu-id="5792c-108">If there is not a match, the user may be prompted to enter a location manually (depending on location policy settings).</span></span> <span data-ttu-id="5792c-109">Los datos de ubicación se devuelven al cliente en un formato XML estándar de grupo de trabajo de ingeniería de Internet (IETF) denominado PIDF-LO (Presence Information Data Format Location Object).</span><span class="sxs-lookup"><span data-stu-id="5792c-109">The location data are transmitted back to the client in an Internet Engineering Task Force (IETF) standardized XML format called Presence Information Data Format Location Object (PIDF-LO).</span></span>

<span data-ttu-id="5792c-110">El cliente de Lync Server incluye los datos PIDF-lo como parte de una llamada de emergencia y el proveedor de servicios E9-1-1 utiliza estos datos para determinar el PSAP adecuado y enrutar la llamada a dicho PSAP junto con el ESQK correcto, lo que permite que el distribuidor de PSAP obtenga la ubicación del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="5792c-110">The Lync Server client includes the PIDF-LO data as part of an emergency call, and this data is used by the E9-1-1 service provider to determine the appropriate PSAP and route the call to that PSAP along with the correct ESQK, which allows the PSAP dispatcher to obtain the caller’s location.</span></span>

<span data-ttu-id="5792c-111">El siguiente diagrama muestra cómo un cliente de Lync Server adquiere una ubicación (excepto para el método de ubicación basado en direcciones MAC de cliente de terceros):</span><span class="sxs-lookup"><span data-stu-id="5792c-111">The following diagram shows how a Lync Server client acquires a location (except for the third-party client MAC address–based location method):</span></span>

<span data-ttu-id="5792c-112">![Modo en que el cliente adquiere un diagrama de ubicación](images/JJ205110.4438f5fc-f1b2-444b-8565-09035363ed43(OCS.15).jpg "Modo en que el cliente adquiere un diagrama de ubicación")</span><span class="sxs-lookup"><span data-stu-id="5792c-112">![How Client Acquires a Location diagram](images/JJ205110.4438f5fc-f1b2-444b-8565-09035363ed43(OCS.15).jpg "How Client Acquires a Location diagram")</span></span>

<span data-ttu-id="5792c-113">Para que el cliente pueda adquirir la ubicación, deben llevarse a cabo los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="5792c-113">For a client to acquire a location, the following steps must take place:</span></span>

1.  <span data-ttu-id="5792c-114">El administrador rellena la base de datos del servicio de información de ubicaciones con el cableado de red (tablas que asignan varios tipos de direcciones de red a las correspondientes ubicaciones de respuesta de emergencia (ERL)).</span><span class="sxs-lookup"><span data-stu-id="5792c-114">The administrator populates the Location Information service database with the network wiremap (tables that map various types of network addresses to corresponding Emergency Response Locations (ERLs)).</span></span>

2.  <span data-ttu-id="5792c-p102">Si usa un proveedor de servicios E9-1-1 mediante troncos SIP, el administrador valida la parte de la dirección postal de la ERL con una base de datos de guía de direcciones principal (MSAG) del proveedor de servicios E9-1-1. Si usa una puerta de enlace ELIN, el administrador se asegura de que el operador de RTC cargue los ELIN en la base de datos de identificación de ubicación automática (ALI).</span><span class="sxs-lookup"><span data-stu-id="5792c-p102">If you use a SIP trunk E9-1-1 service provider, the administrator validates the civic address portions of the ERLs against a Master Street Address Guide (MSAG) database maintained by the E9-1-1 service provider. If you use an ELIN gateway, the administrator ensures that the PSTN carrier uploads the ELINs to the Automatic Location Identification (ALI) database.</span></span>

3.  <span data-ttu-id="5792c-117">Durante el registro o cuando se produce un cambio en la red, un cliente conectado internamente envía una solicitud de ubicación que contiene las direcciones de red detectadas del cliente al servicio de información de ubicación.</span><span class="sxs-lookup"><span data-stu-id="5792c-117">During registration or whenever a network change occurs, an internally-connected client sends a location request that contains the client's discovered network addresses to the Location Information service.</span></span>

4.  <span data-ttu-id="5792c-118">El servicio de información de ubicación consulta sus registros publicados para buscar una ubicación y, si se encuentra una coincidencia, devuelve el ERL al cliente en formato PIDF-lo.</span><span class="sxs-lookup"><span data-stu-id="5792c-118">The Location Information service queries its published records for a location, and, if a match is found, returns the ERL to the client in PIDF-LO format.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

