---
title: 'Lync Server 2013: lista de comprobación para la implementación de E9-1-1'
description: 'Lync Server 2013: lista de comprobación para la implementación de E9-1-1.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for E9-1-1
ms:assetid: cc6a656a-6043-4b9b-85c2-5708b9bb1c06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398864(v=OCS.15)
ms:contentKeyID: 48185655
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c93762e2acef5e065249ced17bfa0eab2f159e4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568362"
---
# <a name="deployment-checklist-for-e9-1-1-in-lync-server-2013"></a><span data-ttu-id="d3f78-103">Lista de comprobación para la implementación de E9-1-1 en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d3f78-103">Deployment checklist for E9-1-1 in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d3f78-104">_**Última modificación del tema:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="d3f78-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="d3f78-105">Para planear eficazmente 9-1-1 mejorado (E9-1-1), no olvide incluir los siguientes requisitos en la implementación:</span><span class="sxs-lookup"><span data-stu-id="d3f78-105">To plan effectively for Enhanced 9-1-1 (E9-1-1), be sure to include the following deployment requirements:</span></span>

  - <span data-ttu-id="d3f78-106">Requisitos previos para implementar E9-1-1</span><span class="sxs-lookup"><span data-stu-id="d3f78-106">Prerequisites for deploying E9-1-1.</span></span>

  - <span data-ttu-id="d3f78-107">Pasos necesarios para implementar E9-1-1</span><span class="sxs-lookup"><span data-stu-id="d3f78-107">Steps that are required to deploy E9-1-1.</span></span>

<div>

## <a name="deployment-prerequisites-for-e9-1-1"></a><span data-ttu-id="d3f78-108">Requisitos previos para implementar E9-1-1</span><span class="sxs-lookup"><span data-stu-id="d3f78-108">Deployment Prerequisites for E9-1-1</span></span>

<span data-ttu-id="d3f78-109">Antes de implementar E9-1-1, debe haber implementado ya los servidores internos de Lync Server, incluido un almacén de administración central, un grupo de servidores front-end o un servidor Standard Edition, uno o varios servidores de mediación o grupos de servidores de mediación, y clientes de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d3f78-109">Before you deploy E9-1-1, you must already have deployed your Lync Server internal servers, including a Central Management store, a Front End pool or a Standard Edition server, one or more Mediation Servers or Mediation Server pools, and Lync Server clients.</span></span> <span data-ttu-id="d3f78-110">Además, una implementación de E9-1-1 requiere un tronco SIP con un proveedor de servicios de E9-1-1 certificado una puerta de enlace de número de identificación de ubicación de emergencia (ELIN) para la Red telefónica conmutada (RTC).</span><span class="sxs-lookup"><span data-stu-id="d3f78-110">In addition, an E9-1-1 deployment requires a SIP trunk to a qualified E9-1-1 service provider or an Emergency Location Identification Number (ELIN) gateway to your public switched telephone network (PSTN).</span></span> <span data-ttu-id="d3f78-111">Lync Server admite el uso de proveedores de servicios de E9-1-1 solo dentro de los Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="d3f78-111">Lync Server supports using E9-1-1 service providers only inside the United States.</span></span>

</div>

<div>

## <a name="deployment-process"></a><span data-ttu-id="d3f78-112">Proceso de implementación</span><span class="sxs-lookup"><span data-stu-id="d3f78-112">Deployment Process</span></span>

<span data-ttu-id="d3f78-113">En la tabla siguiente se proporciona información general del proceso de implementación de E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="d3f78-113">The following table provides an overview of the E9-1-1 deployment process.</span></span> <span data-ttu-id="d3f78-114">Para obtener más información sobre los pasos de implementación, vea [Configure enhanced 9-1-1 in Lync Server 2013](lync-server-2013-configure-enhanced-9-1-1.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="d3f78-114">For details about deployment steps, see [Configure Enhanced 9-1-1 in Lync Server 2013](lync-server-2013-configure-enhanced-9-1-1.md) in the Deployment documentation.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d3f78-115">Fase</span><span class="sxs-lookup"><span data-stu-id="d3f78-115">Phase</span></span></th>
<th><span data-ttu-id="d3f78-116">Pasos</span><span class="sxs-lookup"><span data-stu-id="d3f78-116">Steps</span></span></th>
<th><span data-ttu-id="d3f78-117">Roles</span><span class="sxs-lookup"><span data-stu-id="d3f78-117">Roles</span></span></th>
<th><span data-ttu-id="d3f78-118">Documentación de implementación</span><span class="sxs-lookup"><span data-stu-id="d3f78-118">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d3f78-119">Realizar configuraciones de tronco, rutas y usos de voz</span><span class="sxs-lookup"><span data-stu-id="d3f78-119">Configure voice usages, routes, and trunk configurations</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="d3f78-p103">Cree un registro de uso de RTC. Se trata del mismo nombre que se ha usado para el parámetro <strong>Uso de RTC</strong> en la directiva de ubicación.</span><span class="sxs-lookup"><span data-stu-id="d3f78-p103">Create a new PSTN usage record. This is the same name that is used for the <strong>PSTN Usage</strong> setting in the location policy.</span></span></p></li>
<li><p><span data-ttu-id="d3f78-122">Cree o asigne una ruta de voz con el registro de uso de RTC creado en el paso anterior y apunte el atributo de puerta de enlace al tronco SIP E9-1-1 o la puerta de enlace ELIN.</span><span class="sxs-lookup"><span data-stu-id="d3f78-122">Create or assign a voice route to the PSTN usage record created in the previous step and then point the gateway attribute to the E9-1-1 SIP trunk or ELIN gateway.</span></span></p></li>
<li><p><span data-ttu-id="d3f78-123">Para un proveedor de servicios E9-1-1 de tronco SIP, defina el tronco que va a gestionar las llamadas E9-1-1 sobre el SIP para transferir datos PIDF-LO con el cmdlet <strong>Set-CsTrunkConfiguration –EnablePIDFLOSupport</strong>.</span><span class="sxs-lookup"><span data-stu-id="d3f78-123">For a SIP trunk E9-1-1 service provider, set the trunk that will be handling E9-1-1 calls over the SIP to pass PIDF-LO data by using the <strong>Set-CsTrunkConfiguration –EnablePIDFLOSupport</strong> cmdlet.</span></span></p></li>
<li><p><span data-ttu-id="d3f78-p104">Opcionalmente, para un proveedor de servicios E9-1-1 de tronco SIP, cree o asigne una ruta RTC local para llamadas no gestionadas por el tronco SIP del proveedor de servicios E9-1-1. Esta ruta se usará si la conexión al proveedor de servicios E9-1-1 no está disponible. Si lo admite el proveedor de servicios E9-1-1, asigne una regla de configuración de tronco a la puerta de enlace que convierte la cadena de marcado 911 en el número de llamada directa a la extensión (DID) del Centro de respuesta a llamadas de emergencia nacional y/o regional.</span><span class="sxs-lookup"><span data-stu-id="d3f78-p104">Optionally, for a SIP trunk E9-1-1 service provider, create or assign a local PSTN route for calls that are not handled by the E9-1-1 service provider’s SIP trunk. This route will be used if the connection to the E9-1-1 service provider is not available. If supported by your E9-1-1 service provider, assign a trunk configuration rule to the gateway that translates the 911 dial string into the direct inward dialing (DID) number of the national/regional Emergency Call Response Center (ECRC).</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="d3f78-127">CSVoiceAdmin</span><span class="sxs-lookup"><span data-stu-id="d3f78-127">CSVoiceAdmin</span></span></p></td>
<td><p><span data-ttu-id="d3f78-128"><a href="lync-server-2013-configure-an-e9-1-1-voice-route.md">Configurar una ruta de voz E9-1-1 en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d3f78-128"><a href="lync-server-2013-configure-an-e9-1-1-voice-route.md">Configure an E9-1-1 voice route in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3f78-129">Crear directivas de ubicación y asignarlas a usuarios y subredes</span><span class="sxs-lookup"><span data-stu-id="d3f78-129">Create location policies and assign them to users and subnets</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="d3f78-130">Revise la directiva de ubicación global.</span><span class="sxs-lookup"><span data-stu-id="d3f78-130">Review the global location policy.</span></span></p></li>
<li><p><span data-ttu-id="d3f78-131">Cree una directiva de ubicación con un ámbito en el nivel de usuario o si la organización tiene más de un sitio con diferentes usos de emergencia, cree una directiva de ubicación con un ámbito de nivel de red.</span><span class="sxs-lookup"><span data-stu-id="d3f78-131">Create a location policy with a user-level scope; or, if the organization has more than one site with different emergency usages, create a location policy with a network-level scope.</span></span></p></li>
<li><p><span data-ttu-id="d3f78-132">Asigne la directiva de ubicación a sitios de red.</span><span class="sxs-lookup"><span data-stu-id="d3f78-132">Assign the location policy to network sites.</span></span></p></li>
<li><p><span data-ttu-id="d3f78-133">Agregue las subredes apropiadas al sitio de red.</span><span class="sxs-lookup"><span data-stu-id="d3f78-133">Add the appropriate subnets to the network site.</span></span></p></li>
<li><p><span data-ttu-id="d3f78-134">Asigne la directiva de ubicación a directivas de usuario (opcional).</span><span class="sxs-lookup"><span data-stu-id="d3f78-134">(Optional) Assign the location policy to user policies.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="d3f78-135">CSVoiceAdmin</span><span class="sxs-lookup"><span data-stu-id="d3f78-135">CSVoiceAdmin</span></span></p>
<p><span data-ttu-id="d3f78-136">CSLocationAdmin (excepto para crear directivas de ubicación)</span><span class="sxs-lookup"><span data-stu-id="d3f78-136">CSLocationAdmin (except for creating Location Policies)</span></span></p></td>
<td><p><span data-ttu-id="d3f78-137"><a href="lync-server-2013-create-location-policies.md">Crear directivas de ubicación en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d3f78-137"><a href="lync-server-2013-create-location-policies.md">Create location policies in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="d3f78-138"><a href="lync-server-2013-add-a-location-policy-to-a-network-site.md">Agregar una directiva de ubicación a un sitio de red en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d3f78-138"><a href="lync-server-2013-add-a-location-policy-to-a-network-site.md">Add a location policy to a network site in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="d3f78-139"><a href="lync-server-2013-associate-subnets-with-network-sites-for-e9-1-1.md">Asociar subredes a sitios de red para E9-1-1 en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d3f78-139"><a href="lync-server-2013-associate-subnets-with-network-sites-for-e9-1-1.md">Associate subnets with network sites for E9-1-1 in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d3f78-140">Configurar la base de datos de ubicaciones</span><span class="sxs-lookup"><span data-stu-id="d3f78-140">Configure the location database</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="d3f78-141">Rellene la base de datos con asignaciones de elementos de red a ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="d3f78-141">Populate the database with a mapping of network elements to locations.</span></span></p></li>
<li><p><span data-ttu-id="d3f78-142">Para las puertas de enlace ELIN, agregue Elin a &lt; la &gt; columna CompanyName.</span><span class="sxs-lookup"><span data-stu-id="d3f78-142">For ELIN gateways, add the ELINs to the &lt;CompanyName&gt; column.</span></span></p></li>
<li><p><span data-ttu-id="d3f78-143">Configure la conexión con el proveedor de servicios de E9-1-1 para validar las direcciones.</span><span class="sxs-lookup"><span data-stu-id="d3f78-143">Configure the connection to the E9-1-1 service provider for validating addresses.</span></span></p></li>
<li><p><span data-ttu-id="d3f78-144">Valide las direcciones con el proveedor de servicios E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="d3f78-144">Validate the addresses with the E9-1-1 service provider.</span></span></p></li>
<li><p><span data-ttu-id="d3f78-145">Publique la base de datos actualizada.</span><span class="sxs-lookup"><span data-stu-id="d3f78-145">Publish the updated database.</span></span></p></li>
<li><p><span data-ttu-id="d3f78-146">Para las puertas de enlace ELIN, cargue los ELIN en la base de datos de identificación automática de ubicaciones (ALI) del proveedor de RTC.</span><span class="sxs-lookup"><span data-stu-id="d3f78-146">For ELIN gateways, upload the ELINs to your PSTN carrier's Automatic Location Identification (ALI) database.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="d3f78-147">CSVoiceAdmin</span><span class="sxs-lookup"><span data-stu-id="d3f78-147">CSVoiceAdmin</span></span></p>
<p><span data-ttu-id="d3f78-148">CSLocationAdmin</span><span class="sxs-lookup"><span data-stu-id="d3f78-148">CSLocationAdmin</span></span></p></td>
<td><p><span data-ttu-id="d3f78-149"><a href="lync-server-2013-configure-the-location-database.md">Configurar la base de datos de ubicaciones en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d3f78-149"><a href="lync-server-2013-configure-the-location-database.md">Configure the location database in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d3f78-150">Configurar características avanzadas (opcional)</span><span class="sxs-lookup"><span data-stu-id="d3f78-150">Configure Advanced Features (optional)</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="d3f78-151">Configure la dirección URL de la aplicación SNMP.</span><span class="sxs-lookup"><span data-stu-id="d3f78-151">Configure the URL for the SNMP application.</span></span></p></li>
<li><p><span data-ttu-id="d3f78-152">Configure la dirección URL para la ubicación del servicio de información de ubicación secundaria.</span><span class="sxs-lookup"><span data-stu-id="d3f78-152">Configure the URL for the location of the Secondary Location Information service.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="d3f78-153">CSVoiceAdmin</span><span class="sxs-lookup"><span data-stu-id="d3f78-153">CSVoiceAdmin</span></span></p></td>
<td><p><span data-ttu-id="d3f78-154"><a href="lync-server-2013-configure-an-snmp-application.md">Configurar una aplicación SNMP en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d3f78-154"><a href="lync-server-2013-configure-an-snmp-application.md">Configure an SNMP application in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="d3f78-155"><a href="lync-server-2013-configure-a-secondary-location-information-service.md">Configurar un servicio de información de ubicación secundaria en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="d3f78-155"><a href="lync-server-2013-configure-a-secondary-location-information-service.md">Configure a secondary Location Information service in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

