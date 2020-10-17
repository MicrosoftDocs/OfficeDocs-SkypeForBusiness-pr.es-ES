---
title: 'Lync Server 2013: cambios realizados por la preparación del bosque'
description: 'Lync Server 2013: cambios realizados por la preparación del bosque.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes made by forest preparation
ms:assetid: 2e12613e-59f2-4810-a32d-24a9789a4a6e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425791(v=OCS.15)
ms:contentKeyID: 48183734
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c9bc40539c285e03610b2fc97166842473997fb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543656"
---
# <a name="changes-made-by-forest-preparation-in-lync-server-2013"></a><span data-ttu-id="5f489-103">Cambios realizados por la preparación del bosque en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f489-103">Changes made by forest preparation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5f489-104">_**Última modificación del tema:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="5f489-104">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="5f489-105">En esta sección se describe la configuración global y los objetos, así como el servicio universal y los grupos de administración, que se crean mediante el paso de preparación del bosque.</span><span class="sxs-lookup"><span data-stu-id="5f489-105">This section describes the global settings and objects, and the universal service and administration groups that are created by the forest preparation step.</span></span>

<div>

## <a name="active-directory-global-settings-and-objects"></a><span data-ttu-id="5f489-106">Configuración global y objetos de Active Directory</span><span class="sxs-lookup"><span data-stu-id="5f489-106">Active Directory Global Settings and Objects</span></span>

<span data-ttu-id="5f489-107">Si almacena la configuración global en el contenedor de configuración (como ocurre con todas las implementaciones nuevas de Lync Server 2013), la preparación del bosque utiliza el contenedor de servicios existente y agrega un objeto de **servicio RTC** en el objeto de servicios de configuración \\ .</span><span class="sxs-lookup"><span data-stu-id="5f489-107">If you store global settings in the Configuration container (as is the case for all new Lync Server 2013 deployments), forest preparation uses the existing Services container and adds an **RTC Service** object under the Configuration\\Services object.</span></span> <span data-ttu-id="5f489-108">Al preparar el bosque, se agrega un objeto de **Global Settings** de tipo msRTCSIP-GlobalContainer dentro del objeto RTC Service.</span><span class="sxs-lookup"><span data-stu-id="5f489-108">Under the RTC Service object, forest preparation adds a **Global Settings** object of type msRTCSIP-GlobalContainer.</span></span> <span data-ttu-id="5f489-109">El objeto global Settings contiene toda la configuración que se aplica a la implementación de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5f489-109">The global settings object holds all the settings that apply to the Lync Server deployment.</span></span> <span data-ttu-id="5f489-110">Si almacena la configuración global en el contenedor del sistema, la preparación del bosque utiliza un contenedor de Microsoft en el contenedor del sistema del dominio raíz y un objeto de servicio RTC en el objeto del sistema de \\ Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5f489-110">If you store global settings in the System container, forest preparation uses a Microsoft container under the root domain System container and an RTC Service object under the System\\Microsoft object.</span></span>

<span data-ttu-id="5f489-111">Al preparar el bosque, se agrega también un nuevo objeto **msRTCSIP-Domain** para el dominio raíz en el que se ejecuta el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="5f489-111">Forest preparation also adds a new **msRTCSIP-Domain** object for the root domain in which the procedure is run.</span></span>

</div>

<div>

## <a name="active-directory-universal-service-and-administration-groups"></a><span data-ttu-id="5f489-112">Servicio universal y grupos de administración de Active Directory</span><span class="sxs-lookup"><span data-stu-id="5f489-112">Active Directory Universal Service and Administration Groups</span></span>

<span data-ttu-id="5f489-p102">La preparación del bosque crea grupos universales basados en el dominio especificado y agrega entradas de control de acceso (ACE) para estos grupos. Este paso crea los grupos universales en los contenedores User del dominio especificado.</span><span class="sxs-lookup"><span data-stu-id="5f489-p102">Forest preparation creates universal groups based on the domain that you specify and adds access control entries (ACEs) for these groups. This step creates the universal groups in the User containers of the domain that you specify.</span></span>

<span data-ttu-id="5f489-p103">Los grupos universales permiten a los administradores obtener acceso a la configuración global y los servicios y administrarlos. La preparación del bosque agrega los siguientes tipos de grupos universales:</span><span class="sxs-lookup"><span data-stu-id="5f489-p103">Universal groups allow administrators to access and manage global settings and services. Forest preparation adds the following types of universal groups:</span></span>

  - <span data-ttu-id="5f489-117">**Grupos administrativos**     Estos grupos definen los roles de administrador para una red de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5f489-117">**Administrative groups**   These groups define administrator roles for a Lync Server network.</span></span>

  - <span data-ttu-id="5f489-118">**Grupos**     de infraestructura Estos grupos proporcionan permiso para acceder a áreas específicas de la infraestructura de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5f489-118">**Infrastructure groups**   These groups provide permission to access specific areas of the Lync Server infrastructure.</span></span> <span data-ttu-id="5f489-119">Funcionan como componentes de grupos administrativos.</span><span class="sxs-lookup"><span data-stu-id="5f489-119">They function as components of administrative groups.</span></span> <span data-ttu-id="5f489-120">No debe modificar estos grupos ni agregar usuarios directamente.</span><span class="sxs-lookup"><span data-stu-id="5f489-120">You should not modify these groups or add users directly to them.</span></span>

  - <span data-ttu-id="5f489-121">**Grupos**     de servicio Estos grupos son cuentas de servicio necesarias para tener acceso a varios servicios de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5f489-121">**Service groups**   These groups are service accounts that are required to access various Lync Server services.</span></span>

<span data-ttu-id="5f489-122">En la tabla siguiente se describen los grupos administrativos.</span><span class="sxs-lookup"><span data-stu-id="5f489-122">The following table describes the administrative groups.</span></span>

### <a name="administrative-groups-created-during-forest-preparation"></a><span data-ttu-id="5f489-123">Grupos administrativos creados durante la preparación de un bosque</span><span class="sxs-lookup"><span data-stu-id="5f489-123">Administrative Groups Created During Forest Preparation</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5f489-124">Grupo administrativo</span><span class="sxs-lookup"><span data-stu-id="5f489-124">Administrative group</span></span></th>
<th><span data-ttu-id="5f489-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="5f489-125">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5f489-126">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="5f489-126">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="5f489-127">Permite a los miembros administrar la configuración de los servidores y grupos de servidores, incluidos todos los roles de servidor, la configuración global y los usuarios.</span><span class="sxs-lookup"><span data-stu-id="5f489-127">Allows members to manage server and pool settings, including all server roles, global settings, and users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f489-128">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="5f489-128">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="5f489-129">Permite a los miembros administrar la configuración de los usuarios y mover los usuarios de un servidor o grupo de servidores a otro.</span><span class="sxs-lookup"><span data-stu-id="5f489-129">Allows members to manage user settings and move users from one server or pool to another.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f489-130">RTCUniversalReadOnlyAdmins</span><span class="sxs-lookup"><span data-stu-id="5f489-130">RTCUniversalReadOnlyAdmins</span></span></p></td>
<td><p><span data-ttu-id="5f489-131">Permite a los miembros leer la configuración de los servidores, grupos de servidores y usuarios.</span><span class="sxs-lookup"><span data-stu-id="5f489-131">Allows members to read server, pool, and user settings.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5f489-132">En la tabla siguiente se describen los grupos de infraestructura.</span><span class="sxs-lookup"><span data-stu-id="5f489-132">The following table describes the infrastructure groups.</span></span>

### <a name="infrastructure-groups-created-during-forest-preparation"></a><span data-ttu-id="5f489-133">Grupos de infraestructura creados durante la preparación de un bosque</span><span class="sxs-lookup"><span data-stu-id="5f489-133">Infrastructure Groups Created During Forest Preparation</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5f489-134">Grupo de infraestructura</span><span class="sxs-lookup"><span data-stu-id="5f489-134">Infrastructure group</span></span></th>
<th><span data-ttu-id="5f489-135">Descripción</span><span class="sxs-lookup"><span data-stu-id="5f489-135">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5f489-136">RTCUniversalGlobalWriteGroup</span><span class="sxs-lookup"><span data-stu-id="5f489-136">RTCUniversalGlobalWriteGroup</span></span></p></td>
<td><p><span data-ttu-id="5f489-137">Concede acceso de escritura a los objetos de configuración global de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5f489-137">Grants write access to global setting objects for Lync Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f489-138">RTCUniversalGlobalReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="5f489-138">RTCUniversalGlobalReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="5f489-139">Concede acceso de solo lectura a los objetos de configuración global de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5f489-139">Grants read-only access to global setting objects for Lync Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f489-140">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="5f489-140">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="5f489-141">Concede acceso de solo lectura a la configuración de usuario de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5f489-141">Grants read-only access to Lync Server user settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f489-142">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="5f489-142">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="5f489-143">Concede acceso de solo lectura a la configuración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5f489-143">Grants read-only access to Lync Server settings.</span></span> <span data-ttu-id="5f489-144">Este grupo no tiene acceso a la configuración de nivel de grupo de servidores, sino únicamente a la configuración específica de un servidor individual.</span><span class="sxs-lookup"><span data-stu-id="5f489-144">This group does not have access to pool level settings, only to settings specific to an individual server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f489-145">RTCUniversalSBATechnicians</span><span class="sxs-lookup"><span data-stu-id="5f489-145">RTCUniversalSBATechnicians</span></span></p></td>
<td><p><span data-ttu-id="5f489-146">Concede acceso de solo lectura a la configuración de Lync Server y se coloca en el grupo de administradores locales de las aplicaciones de sucursal con funciones de supervivencia durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="5f489-146">Grants read-only access to Lync Server configuration and are placed in the Local Administrators group of the survivable branch appliances during installation.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5f489-147">En la tabla siguiente se describen los grupos de servicio.</span><span class="sxs-lookup"><span data-stu-id="5f489-147">The following table describes the service groups.</span></span>

### <a name="service-groups-created-during-forest-preparation"></a><span data-ttu-id="5f489-148">Grupos de servicio creados durante la preparación de un bosque</span><span class="sxs-lookup"><span data-stu-id="5f489-148">Service Groups Created During Forest Preparation</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5f489-149">Grupo de servicio</span><span class="sxs-lookup"><span data-stu-id="5f489-149">Service group</span></span></th>
<th><span data-ttu-id="5f489-150">Descripción</span><span class="sxs-lookup"><span data-stu-id="5f489-150">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5f489-151">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="5f489-151">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="5f489-152">Incluye las cuentas de servicio usadas para ejecutar los servidores front-end y los servidores Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="5f489-152">Includes service accounts used to run Front End Server and Standard Edition servers.</span></span> <span data-ttu-id="5f489-153">Este grupo permite que los servidores tengan acceso de lectura y escritura a la configuración global de Lync Server y a los objetos de usuario de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5f489-153">This group allows servers read/write access to Lync Server global settings and Active Directory user objects.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f489-154">RTCComponentUniversalServices</span><span class="sxs-lookup"><span data-stu-id="5f489-154">RTCComponentUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="5f489-155">Incluye las cuentas de servicio usadas para ejecutar los servidores de conferencia a/V, los servicios Web, el servidor de mediación, el servidor de archivado y el servidor de supervisión.</span><span class="sxs-lookup"><span data-stu-id="5f489-155">Includes service accounts used to run A/V Conferencing Servers, Web Services, Mediation Server, Archiving Server, and Monitoring Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f489-156">RTCProxyUniversalServices</span><span class="sxs-lookup"><span data-stu-id="5f489-156">RTCProxyUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="5f489-157">Incluye las cuentas de servicio usadas para ejecutar los servidores perimetrales de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5f489-157">Includes service accounts used to run Lync Server Edge Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f489-158">RTCUniversalConfigReplicator</span><span class="sxs-lookup"><span data-stu-id="5f489-158">RTCUniversalConfigReplicator</span></span></p></td>
<td><p><span data-ttu-id="5f489-159">Incluye servidores que pueden participar en la replicación del almacén de administración central de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5f489-159">Includes servers that can participate in Lync Server Central Management store replication.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f489-160">RTCSBAUniversalServices</span><span class="sxs-lookup"><span data-stu-id="5f489-160">RTCSBAUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="5f489-161">Concede acceso de solo lectura a la configuración de Lync Server, pero permite la configuración para la instalación de un servidor de sucursal con funciones de supervivencia y una implementación de aplicación de sucursal con funciones de supervivencia.</span><span class="sxs-lookup"><span data-stu-id="5f489-161">Grants read-only access to Lync Server settings, but allows for configuration for the installation of a survivable branch server and survivable branch appliance deployment.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5f489-162">A continuación, la preparación del bosque agrega los grupos de servicio y administración a los grupos de infraestructura correspondientes del siguiente modo:</span><span class="sxs-lookup"><span data-stu-id="5f489-162">Forest preparation then adds service and administration groups to the appropriate infrastructure groups, as follows:</span></span>

  - <span data-ttu-id="5f489-163">RTCUniversalServerAdmins se agrega a RTCUniversalGlobalReadOnlyGroup, RTCUniversalGlobalWriteGroup, RTCUniversalServerReadOnlyGroup y RTCUniversalUserReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="5f489-163">RTCUniversalServerAdmins is added to RTCUniversalGlobalReadOnlyGroup, RTCUniversalGlobalWriteGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>

  - <span data-ttu-id="5f489-164">RTCUniversalUserAdmins se agrega como miembro de RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup y RTCUniversalUserReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="5f489-164">RTCUniversalUserAdmins is added as a member of RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>

  - <span data-ttu-id="5f489-165">RTCHSUniversalServices, RTCComponentUniversalServices y RTCUniversalReadOnlyAdmins se agregan como miembros de RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup y RTCUniversalUserReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="5f489-165">RTCHSUniversalServices, RTCComponentUniversalServices and RTCUniversalReadOnlyAdmins are added as members of RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>

<span data-ttu-id="5f489-166">Durante la preparación del bosque también se crean los siguientes grupos de control de acceso basado en roles (RBAC):</span><span class="sxs-lookup"><span data-stu-id="5f489-166">Forest preparation also creates the following role-based access control (RBAC) groups:</span></span>

  - <span data-ttu-id="5f489-167">CSAdministrator</span><span class="sxs-lookup"><span data-stu-id="5f489-167">CSAdministrator</span></span>

  - <span data-ttu-id="5f489-168">Rol csarchivingadministrator</span><span class="sxs-lookup"><span data-stu-id="5f489-168">CSArchivingAdministrator</span></span>

  - <span data-ttu-id="5f489-169">CSHelpDesk</span><span class="sxs-lookup"><span data-stu-id="5f489-169">CSHelpDesk</span></span>

  - <span data-ttu-id="5f489-170">CSLocationAdministrator</span><span class="sxs-lookup"><span data-stu-id="5f489-170">CSLocationAdministrator</span></span>

  - <span data-ttu-id="5f489-171">CSResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="5f489-171">CSResponseGroupAdministrator</span></span>

  - <span data-ttu-id="5f489-172">CSServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="5f489-172">CSServerAdministrator</span></span>

  - <span data-ttu-id="5f489-173">CSUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="5f489-173">CSUserAdministrator</span></span>

  - <span data-ttu-id="5f489-174">CSViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="5f489-174">CSViewOnlyAdministrator</span></span>

  - <span data-ttu-id="5f489-175">CSVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="5f489-175">CSVoiceAdministrator</span></span>

  - <span data-ttu-id="5f489-176">CsPersistentChatAdministator</span><span class="sxs-lookup"><span data-stu-id="5f489-176">CsPersistentChatAdministator</span></span>

  - <span data-ttu-id="5f489-177">CsResponseGroupManager</span><span class="sxs-lookup"><span data-stu-id="5f489-177">CsResponseGroupManager</span></span>

<span data-ttu-id="5f489-178">Para obtener más información sobre los roles RBAC y las tareas permitidas para cada uno, consulte [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="5f489-178">For details about RBAC roles and the tasks allowed for each, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) in the Planning documentation.</span></span>

<span data-ttu-id="5f489-179">La preparación del bosque crea entradas ACE privadas y públicas.</span><span class="sxs-lookup"><span data-stu-id="5f489-179">Forest preparation creates both private and public ACEs.</span></span> <span data-ttu-id="5f489-180">Crea ACE privadas en el contenedor de configuración global usado por Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5f489-180">It creates private ACEs on the global settings container used by Lync Server.</span></span> <span data-ttu-id="5f489-181">Este contenedor solo se usa en Lync Server y se encuentra en el contenedor de configuración o en el contenedor del sistema en el dominio raíz, en función de dónde almacene la configuración global.</span><span class="sxs-lookup"><span data-stu-id="5f489-181">This container is used only by Lync Server and is located either in the Configuration container or the System container in the root domain, depending on where you store global settings.</span></span> <span data-ttu-id="5f489-182">Las entradas ACE públicas que se crean al preparar el bosque se indican en la siguiente tabla:</span><span class="sxs-lookup"><span data-stu-id="5f489-182">The public ACEs created by forest preparation are listed in the following table.</span></span>

### <a name="public-aces-created-by-forest-preparation"></a><span data-ttu-id="5f489-183">Entradas ACE públicas creadas al preparar el bosque</span><span class="sxs-lookup"><span data-stu-id="5f489-183">Public ACEs created by Forest Preparation</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5f489-184">ACE</span><span class="sxs-lookup"><span data-stu-id="5f489-184">ACE</span></span></th>
<th><span data-ttu-id="5f489-185">RTCUniversalGlobalReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="5f489-185">RTCUniversalGlobalReadOnlyGroup</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5f489-186">Contenedor System de dominio raíz Read (no se hereda)<strong>\*</strong></span><span class="sxs-lookup"><span data-stu-id="5f489-186">Read root domain System Container (not inherited)<strong>\*</strong></span></span></p></td>
<td><p><span data-ttu-id="5f489-187">X</span><span class="sxs-lookup"><span data-stu-id="5f489-187">X</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f489-188">Contenedor DisplaySpecifiers de Read Configuration (no se hereda)</span><span class="sxs-lookup"><span data-stu-id="5f489-188">Read Configuration’s DisplaySpecifiers container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="5f489-189">X</span><span class="sxs-lookup"><span data-stu-id="5f489-189">X</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="5f489-190"><STRONG>\*</STRONG>Las ACE que no se heredan no conceden acceso a objetos secundarios en estos contenedores.</span><span class="sxs-lookup"><span data-stu-id="5f489-190"><STRONG>\*</STRONG>ACEs that are not inherited do not grant access to child objects under these containers.</span></span> <span data-ttu-id="5f489-191">Las entradas de control de acceso que se heredan permiten el acceso a los objetos secundarios de estos contenedores.</span><span class="sxs-lookup"><span data-stu-id="5f489-191">ACEs that are inherited grant access to child objects under these containers.</span></span>



</div>

<span data-ttu-id="5f489-192">En el contenedor Configuration, bajo el contexto de nomenclatura de configuración, el procedimiento de preparación del bosque realiza las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="5f489-192">On the Configuration container, under the Configuration naming context, forest preparation performs the following tasks:</span></span>

  - <span data-ttu-id="5f489-193">Agrega una entrada **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** para la página **RTC property** dentro de los atributos adminContextMenu y adminPropertyPages del especificador de presentación de idioma correspondiente a los objetos User, Contact e InetOrgPerson (por ejemplo, CN=user-Display,CN=409,CN=DisplaySpecifiers).</span><span class="sxs-lookup"><span data-stu-id="5f489-193">Adds an entry **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** for the **RTC property** page under the adminContextMenu and adminPropertyPages attributes of the language display specifier for users, contacts, and InetOrgPersons (for example, CN=user-Display,CN=409,CN=DisplaySpecifiers).</span></span>

  - <span data-ttu-id="5f489-194">Agrega un objeto **RTCPropertySet** de tipo **controlAccessRight** en **Extended-Rights** que se aplica a las clases User y Contact.</span><span class="sxs-lookup"><span data-stu-id="5f489-194">Adds an **RTCPropertySet** object of type **controlAccessRight** under **Extended-Rights** that applies to the User and Contact classes.</span></span>

  - <span data-ttu-id="5f489-195">Agrega un objeto **RTCUserSearchPropertySet** de tipo **controlAccessRight** en **Extended-Rights** que se aplica a las clases User, Contact, OU y DomainDNS.</span><span class="sxs-lookup"><span data-stu-id="5f489-195">Adds an **RTCUserSearchPropertySet** object of type **controlAccessRight** under **Extended-Rights** that applies to User, Contact, OU, and DomainDNS classes.</span></span>

  - <span data-ttu-id="5f489-196">Agrega **msRTCSIP-PrimaryUserAddress** en el atributo **extraColumns** de cada especificador de presentación de unidad organizativa de idioma (por ejemplo, CN=organizationalUnit-Display,CN=409,CN=DisplaySpecifiers) y copia los valores del atributo **extraColumns** de la presentación predeterminada (por ejemplo, CN=default-Display, CN=409,CN=DisplaySpecifiers).</span><span class="sxs-lookup"><span data-stu-id="5f489-196">Adds **msRTCSIP-PrimaryUserAddress** under the **extraColumns** attribute of each language organizational unit (OU) display specifier (for example, CN=organizationalUnit-Display,CN=409,CN=DisplaySpecifiers) and copies the values of the **extraColumns** attribute of the default display (for example, CN=default-Display, CN=409,CN=DisplaySpecifiers).</span></span>

  - <span data-ttu-id="5f489-197">Agrega los atributos de filtro **msRTCSIP-PrimaryUserAddress**, **msRTCSIP-PrimaryHomeServer** y **msRTCSIP-UserEnabled** en el atributo **attributeDisplayNames** de cada especificador de presentación de idioma de los objetos Users, Contacts e InetOrgPerson (por ejemplo, en inglés: CN=user-Display,CN=409,CN=DisplaySpecifiers).</span><span class="sxs-lookup"><span data-stu-id="5f489-197">Adds **msRTCSIP-PrimaryUserAddress**, **msRTCSIP-PrimaryHomeServer**, and **msRTCSIP-UserEnabled** filtering attributes under the **attributeDisplayNames** attribute of each language display specifier for Users, Contacts, and InetOrgPerson objects (for example, in English: CN=user-Display,CN=409,CN=DisplaySpecifiers).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

