---
title: 'Lync Server 2013: cambios realizados por la preparación del bosque'
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
ms.openlocfilehash: 4df16ffb24c4eb4e010e2b57f6af62d3518c05b6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730100"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-forest-preparation-in-lync-server-2013"></a><span data-ttu-id="74579-102">Cambios realizados por la preparación del bosque en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="74579-102">Changes made by forest preparation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="74579-103">_**Última modificación del tema:** 2012-10-30_</span><span class="sxs-lookup"><span data-stu-id="74579-103">_**Topic Last Modified:** 2012-10-30_</span></span>

<span data-ttu-id="74579-104">En esta sección se describen la configuración global y los objetos, así como el servicio universal y los grupos de administración creados por el paso de preparación del bosque.</span><span class="sxs-lookup"><span data-stu-id="74579-104">This section describes the global settings and objects, and the universal service and administration groups that are created by the forest preparation step.</span></span>

<div>

## <a name="active-directory-global-settings-and-objects"></a><span data-ttu-id="74579-105">Objetos y configuración global de Active Directory</span><span class="sxs-lookup"><span data-stu-id="74579-105">Active Directory Global Settings and Objects</span></span>

<span data-ttu-id="74579-106">Si almacena la configuración global en el contenedor de configuración (como es el caso de todas las implementaciones de Lync Server 2013 nuevas), la preparación del bosque usa el contenedor servicios existentes y agrega un objeto\\de **servicio RTC** en el objeto de servicios de configuración.</span><span class="sxs-lookup"><span data-stu-id="74579-106">If you store global settings in the Configuration container (as is the case for all new Lync Server 2013 deployments), forest preparation uses the existing Services container and adds an **RTC Service** object under the Configuration\\Services object.</span></span> <span data-ttu-id="74579-107">En el objeto de servicio RTC, la preparación del bosque agrega un objeto de **configuración global** de tipo MsRTCSIP-GlobalContainer.</span><span class="sxs-lookup"><span data-stu-id="74579-107">Under the RTC Service object, forest preparation adds a **Global Settings** object of type msRTCSIP-GlobalContainer.</span></span> <span data-ttu-id="74579-108">El objeto configuración global contiene toda la configuración que se aplica a la implementación de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="74579-108">The global settings object holds all the settings that apply to the Lync Server deployment.</span></span> <span data-ttu-id="74579-109">Si almacena la configuración global en el contenedor del sistema, la preparación del bosque usa un contenedor de Microsoft en el contenedor del sistema del dominio raíz y un\\objeto de servicio RTC bajo el objeto Microsoft del sistema.</span><span class="sxs-lookup"><span data-stu-id="74579-109">If you store global settings in the System container, forest preparation uses a Microsoft container under the root domain System container and an RTC Service object under the System\\Microsoft object.</span></span>

<span data-ttu-id="74579-110">La preparación del bosque también agrega un nuevo objeto **msRTCSIP-Domain** para el dominio raíz en el que se ejecuta el procedimiento.</span><span class="sxs-lookup"><span data-stu-id="74579-110">Forest preparation also adds a new **msRTCSIP-Domain** object for the root domain in which the procedure is run.</span></span>

</div>

<div>

## <a name="active-directory-universal-service-and-administration-groups"></a><span data-ttu-id="74579-111">Servicio universal de Active Directory y grupos de administración</span><span class="sxs-lookup"><span data-stu-id="74579-111">Active Directory Universal Service and Administration Groups</span></span>

<span data-ttu-id="74579-112">La preparación del bosque crea grupos universales basados en el dominio que especifique y agrega entradas de control de acceso (ACE) para estos grupos.</span><span class="sxs-lookup"><span data-stu-id="74579-112">Forest preparation creates universal groups based on the domain that you specify and adds access control entries (ACEs) for these groups.</span></span> <span data-ttu-id="74579-113">Este paso crea los grupos universales en los contenedores de usuario del dominio que especifique.</span><span class="sxs-lookup"><span data-stu-id="74579-113">This step creates the universal groups in the User containers of the domain that you specify.</span></span>

<span data-ttu-id="74579-114">Los grupos universales permiten a los administradores acceder y administrar la configuración y los servicios globales.</span><span class="sxs-lookup"><span data-stu-id="74579-114">Universal groups allow administrators to access and manage global settings and services.</span></span> <span data-ttu-id="74579-115">La preparación del bosque agrega los siguientes tipos de grupos universales:</span><span class="sxs-lookup"><span data-stu-id="74579-115">Forest preparation adds the following types of universal groups:</span></span>

  - <span data-ttu-id="74579-116">**Grupos administrativos estos**   grupos definen roles de administrador para una red de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="74579-116">**Administrative groups**   These groups define administrator roles for a Lync Server network.</span></span>

  - <span data-ttu-id="74579-117">**Grupos de infraestructura**   estos grupos proporcionan permiso para acceder a áreas específicas de la infraestructura de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="74579-117">**Infrastructure groups**   These groups provide permission to access specific areas of the Lync Server infrastructure.</span></span> <span data-ttu-id="74579-118">Funcionan como componentes de grupos administrativos.</span><span class="sxs-lookup"><span data-stu-id="74579-118">They function as components of administrative groups.</span></span> <span data-ttu-id="74579-119">No debe modificar estos grupos ni agregar usuarios directamente.</span><span class="sxs-lookup"><span data-stu-id="74579-119">You should not modify these groups or add users directly to them.</span></span>

  - <span data-ttu-id="74579-120">**Grupos de servicio**   estos grupos son cuentas de servicio necesarias para acceder a varios servicios de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="74579-120">**Service groups**   These groups are service accounts that are required to access various Lync Server services.</span></span>

<span data-ttu-id="74579-121">En la tabla siguiente se describen los grupos administrativos.</span><span class="sxs-lookup"><span data-stu-id="74579-121">The following table describes the administrative groups.</span></span>

### <a name="administrative-groups-created-during-forest-preparation"></a><span data-ttu-id="74579-122">Grupos administrativos creados durante la preparación del bosque</span><span class="sxs-lookup"><span data-stu-id="74579-122">Administrative Groups Created During Forest Preparation</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="74579-123">Grupo administrativo</span><span class="sxs-lookup"><span data-stu-id="74579-123">Administrative group</span></span></th>
<th><span data-ttu-id="74579-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="74579-124">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="74579-125">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="74579-125">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="74579-126">Permite a los miembros administrar la configuración del servidor y del grupo, incluidos los roles de servidor, la configuración global y los usuarios.</span><span class="sxs-lookup"><span data-stu-id="74579-126">Allows members to manage server and pool settings, including all server roles, global settings, and users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74579-127">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="74579-127">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="74579-128">Permite a los miembros administrar la configuración de usuario y mover los usuarios de un servidor o grupo a otro.</span><span class="sxs-lookup"><span data-stu-id="74579-128">Allows members to manage user settings and move users from one server or pool to another.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74579-129">RTCUniversalReadOnlyAdmins</span><span class="sxs-lookup"><span data-stu-id="74579-129">RTCUniversalReadOnlyAdmins</span></span></p></td>
<td><p><span data-ttu-id="74579-130">Permite que los miembros lean la configuración del servidor, del grupo y del usuario.</span><span class="sxs-lookup"><span data-stu-id="74579-130">Allows members to read server, pool, and user settings.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="74579-131">En la tabla siguiente se describen los grupos de infraestructura.</span><span class="sxs-lookup"><span data-stu-id="74579-131">The following table describes the infrastructure groups.</span></span>

### <a name="infrastructure-groups-created-during-forest-preparation"></a><span data-ttu-id="74579-132">Grupos de infraestructura creados durante la preparación del bosque</span><span class="sxs-lookup"><span data-stu-id="74579-132">Infrastructure Groups Created During Forest Preparation</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="74579-133">Grupo de infraestructura</span><span class="sxs-lookup"><span data-stu-id="74579-133">Infrastructure group</span></span></th>
<th><span data-ttu-id="74579-134">Descripción</span><span class="sxs-lookup"><span data-stu-id="74579-134">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="74579-135">RTCUniversalGlobalWriteGroup</span><span class="sxs-lookup"><span data-stu-id="74579-135">RTCUniversalGlobalWriteGroup</span></span></p></td>
<td><p><span data-ttu-id="74579-136">Concede acceso de escritura a los objetos de configuración global de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="74579-136">Grants write access to global setting objects for Lync Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74579-137">RTCUniversalGlobalReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="74579-137">RTCUniversalGlobalReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="74579-138">Concede acceso de solo lectura a objetos de configuración global para Lync Server.</span><span class="sxs-lookup"><span data-stu-id="74579-138">Grants read-only access to global setting objects for Lync Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74579-139">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="74579-139">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="74579-140">Concede acceso de solo lectura a la configuración de usuario de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="74579-140">Grants read-only access to Lync Server user settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74579-141">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="74579-141">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="74579-142">Concede acceso de solo lectura a la configuración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="74579-142">Grants read-only access to Lync Server settings.</span></span> <span data-ttu-id="74579-143">Este grupo no tiene acceso a la configuración del nivel de grupo, solo a la configuración específica de un servidor individual.</span><span class="sxs-lookup"><span data-stu-id="74579-143">This group does not have access to pool level settings, only to settings specific to an individual server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74579-144">RTCUniversalSBATechnicians</span><span class="sxs-lookup"><span data-stu-id="74579-144">RTCUniversalSBATechnicians</span></span></p></td>
<td><p><span data-ttu-id="74579-145">Concede acceso de solo lectura a la configuración de Lync Server y se coloca en el grupo de administradores locales de las aplicaciones de las sucursales que son supervivientes durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="74579-145">Grants read-only access to Lync Server configuration and are placed in the Local Administrators group of the survivable branch appliances during installation.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="74579-146">En la siguiente tabla se describen los grupos de servicios.</span><span class="sxs-lookup"><span data-stu-id="74579-146">The following table describes the service groups.</span></span>

### <a name="service-groups-created-during-forest-preparation"></a><span data-ttu-id="74579-147">Grupos de servicio creados durante la preparación del bosque</span><span class="sxs-lookup"><span data-stu-id="74579-147">Service Groups Created During Forest Preparation</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="74579-148">Grupo de servicio</span><span class="sxs-lookup"><span data-stu-id="74579-148">Service group</span></span></th>
<th><span data-ttu-id="74579-149">Descripción</span><span class="sxs-lookup"><span data-stu-id="74579-149">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="74579-150">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="74579-150">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="74579-151">Incluye cuentas de servicio que se usan para ejecutar servidores front-end y servidores Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="74579-151">Includes service accounts used to run Front End Server and Standard Edition servers.</span></span> <span data-ttu-id="74579-152">Este grupo permite que los servidores tengan acceso de lectura y escritura a la configuración global de Lync Server y a los objetos de usuario de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="74579-152">This group allows servers read/write access to Lync Server global settings and Active Directory user objects.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74579-153">RTCComponentUniversalServices</span><span class="sxs-lookup"><span data-stu-id="74579-153">RTCComponentUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="74579-154">Incluye cuentas de servicio que se usan para ejecutar servidores de conferencia A/V, servicios Web, servidor de mediación, servidor de archivado y servidor de supervisión.</span><span class="sxs-lookup"><span data-stu-id="74579-154">Includes service accounts used to run A/V Conferencing Servers, Web Services, Mediation Server, Archiving Server, and Monitoring Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74579-155">RTCProxyUniversalServices</span><span class="sxs-lookup"><span data-stu-id="74579-155">RTCProxyUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="74579-156">Incluye cuentas de servicio que se usan para ejecutar servidores perimetrales de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="74579-156">Includes service accounts used to run Lync Server Edge Servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74579-157">RTCUniversalConfigReplicator</span><span class="sxs-lookup"><span data-stu-id="74579-157">RTCUniversalConfigReplicator</span></span></p></td>
<td><p><span data-ttu-id="74579-158">Incluye servidores que pueden participar en la replicación del almacén central de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="74579-158">Includes servers that can participate in Lync Server Central Management store replication.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74579-159">RTCSBAUniversalServices</span><span class="sxs-lookup"><span data-stu-id="74579-159">RTCSBAUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="74579-160">Concede acceso de solo lectura a la configuración del servidor de Lync, pero permite la configuración de la instalación de un servidor de sucursal y una implementación de dispositivos de rama supervivientes.</span><span class="sxs-lookup"><span data-stu-id="74579-160">Grants read-only access to Lync Server settings, but allows for configuration for the installation of a survivable branch server and survivable branch appliance deployment.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="74579-161">La preparación del bosque, a continuación, agrega grupos de servicio y administración a los grupos de infraestructura adecuados, de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="74579-161">Forest preparation then adds service and administration groups to the appropriate infrastructure groups, as follows:</span></span>

  - <span data-ttu-id="74579-162">RTCUniversalServerAdmins se agrega a RTCUniversalGlobalReadOnlyGroup, RTCUniversalGlobalWriteGroup, RTCUniversalServerReadOnlyGroup y RTCUniversalUserReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="74579-162">RTCUniversalServerAdmins is added to RTCUniversalGlobalReadOnlyGroup, RTCUniversalGlobalWriteGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>

  - <span data-ttu-id="74579-163">RTCUniversalUserAdmins se agrega como miembro de RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup y RTCUniversalUserReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="74579-163">RTCUniversalUserAdmins is added as a member of RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>

  - <span data-ttu-id="74579-164">RTCHSUniversalServices, RTCComponentUniversalServices y RTCUniversalReadOnlyAdmins se agregan como miembros de RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup y RTCUniversalUserReadOnlyGroup.</span><span class="sxs-lookup"><span data-stu-id="74579-164">RTCHSUniversalServices, RTCComponentUniversalServices and RTCUniversalReadOnlyAdmins are added as members of RTCUniversalGlobalReadOnlyGroup, RTCUniversalServerReadOnlyGroup, and RTCUniversalUserReadOnlyGroup.</span></span>

<span data-ttu-id="74579-165">La preparación del bosque también crea los siguientes grupos de control de acceso basado en roles (RBAC):</span><span class="sxs-lookup"><span data-stu-id="74579-165">Forest preparation also creates the following role-based access control (RBAC) groups:</span></span>

  - <span data-ttu-id="74579-166">CSAdministrator</span><span class="sxs-lookup"><span data-stu-id="74579-166">CSAdministrator</span></span>

  - <span data-ttu-id="74579-167">CSArchivingAdministrator</span><span class="sxs-lookup"><span data-stu-id="74579-167">CSArchivingAdministrator</span></span>

  - <span data-ttu-id="74579-168">CSHelpDesk</span><span class="sxs-lookup"><span data-stu-id="74579-168">CSHelpDesk</span></span>

  - <span data-ttu-id="74579-169">CSLocationAdministrator</span><span class="sxs-lookup"><span data-stu-id="74579-169">CSLocationAdministrator</span></span>

  - <span data-ttu-id="74579-170">CSResponseGroupAdministrator</span><span class="sxs-lookup"><span data-stu-id="74579-170">CSResponseGroupAdministrator</span></span>

  - <span data-ttu-id="74579-171">CSServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="74579-171">CSServerAdministrator</span></span>

  - <span data-ttu-id="74579-172">CSUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="74579-172">CSUserAdministrator</span></span>

  - <span data-ttu-id="74579-173">CSViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="74579-173">CSViewOnlyAdministrator</span></span>

  - <span data-ttu-id="74579-174">CSVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="74579-174">CSVoiceAdministrator</span></span>

  - <span data-ttu-id="74579-175">CsPersistentChatAdministator</span><span class="sxs-lookup"><span data-stu-id="74579-175">CsPersistentChatAdministator</span></span>

  - <span data-ttu-id="74579-176">AdministradorGrupoRespuestaCs</span><span class="sxs-lookup"><span data-stu-id="74579-176">CsResponseGroupManager</span></span>

<span data-ttu-id="74579-177">Para obtener más información sobre los roles RBAC y las tareas permitidas para cada uno, vea [planear el control de acceso basado en roles en Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="74579-177">For details about RBAC roles and the tasks allowed for each, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) in the Planning documentation.</span></span>

<span data-ttu-id="74579-178">La preparación del bosque crea entradas de acceso privadas y públicas.</span><span class="sxs-lookup"><span data-stu-id="74579-178">Forest preparation creates both private and public ACEs.</span></span> <span data-ttu-id="74579-179">Crea ACE privadas en el contenedor de configuración global usado por Lync Server.</span><span class="sxs-lookup"><span data-stu-id="74579-179">It creates private ACEs on the global settings container used by Lync Server.</span></span> <span data-ttu-id="74579-180">Este contenedor solo es utilizado por Lync Server y se encuentra en el contenedor configuración o en el contenedor del sistema en el dominio raíz, según dónde se almacene la configuración global.</span><span class="sxs-lookup"><span data-stu-id="74579-180">This container is used only by Lync Server and is located either in the Configuration container or the System container in the root domain, depending on where you store global settings.</span></span> <span data-ttu-id="74579-181">Las ACE públicas creadas por la preparación del bosque se enumeran en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="74579-181">The public ACEs created by forest preparation are listed in the following table.</span></span>

### <a name="public-aces-created-by-forest-preparation"></a><span data-ttu-id="74579-182">ACE públicas creadas por la preparación del bosque</span><span class="sxs-lookup"><span data-stu-id="74579-182">Public ACEs created by Forest Preparation</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="74579-183">ENTRADA</span><span class="sxs-lookup"><span data-stu-id="74579-183">ACE</span></span></th>
<th><span data-ttu-id="74579-184">RTCUniversalGlobalReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="74579-184">RTCUniversalGlobalReadOnlyGroup</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="74579-185">Leer el contenedor del sistema del dominio raíz (no heredado)<strong>\*</strong></span><span class="sxs-lookup"><span data-stu-id="74579-185">Read root domain System Container (not inherited)<strong>\*</strong></span></span></p></td>
<td><p><span data-ttu-id="74579-186">X</span><span class="sxs-lookup"><span data-stu-id="74579-186">X</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74579-187">Contenedor DisplaySpecifiers de lectura de la configuración (no heredado)</span><span class="sxs-lookup"><span data-stu-id="74579-187">Read Configuration’s DisplaySpecifiers container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="74579-188">X</span><span class="sxs-lookup"><span data-stu-id="74579-188">X</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="74579-189"><STRONG>\*</STRONG>Las ACE que no se heredan no conceden acceso a objetos secundarios en estos contenedores.</span><span class="sxs-lookup"><span data-stu-id="74579-189"><STRONG>\*</STRONG>ACEs that are not inherited do not grant access to child objects under these containers.</span></span> <span data-ttu-id="74579-190">Las ACE que se heredan otorgan acceso a objetos secundarios en estos contenedores.</span><span class="sxs-lookup"><span data-stu-id="74579-190">ACEs that are inherited grant access to child objects under these containers.</span></span>



</div>

<span data-ttu-id="74579-191">En el contenedor configuración, en el contexto de nomenclatura de configuración, la preparación del bosque realiza las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="74579-191">On the Configuration container, under the Configuration naming context, forest preparation performs the following tasks:</span></span>

  - <span data-ttu-id="74579-192">Agrega una entrada **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** para la página de **propiedades RTC** en los atributos adminContextMenu y adminPropertyPages del especificador de presentación de idioma para usuarios, contactos y InetOrgPersons (por ejemplo, CN = user-Display, CN = 409, CN = DisplaySpecifiers).</span><span class="sxs-lookup"><span data-stu-id="74579-192">Adds an entry **{AB255F23-2DBD-4bb6-891D-38754AC280EF}** for the **RTC property** page under the adminContextMenu and adminPropertyPages attributes of the language display specifier for users, contacts, and InetOrgPersons (for example, CN=user-Display,CN=409,CN=DisplaySpecifiers).</span></span>

  - <span data-ttu-id="74579-193">Agrega un objeto **RTCPropertySet** de tipo **controlAccessRight** bajo **Extended-Rights** que se aplica a las clases User y contact.</span><span class="sxs-lookup"><span data-stu-id="74579-193">Adds an **RTCPropertySet** object of type **controlAccessRight** under **Extended-Rights** that applies to the User and Contact classes.</span></span>

  - <span data-ttu-id="74579-194">Agrega un objeto **RTCUserSearchPropertySet** de tipo **controlAccessRight** bajo **Extended-Rights** que se aplica a las clases User, Contact, ou y DomainDNS.</span><span class="sxs-lookup"><span data-stu-id="74579-194">Adds an **RTCUserSearchPropertySet** object of type **controlAccessRight** under **Extended-Rights** that applies to User, Contact, OU, and DomainDNS classes.</span></span>

  - <span data-ttu-id="74579-195">Agrega **msRTCSIP-PrimaryUserAddress** en el atributo **extracolumns** del especificador de pantalla de cada idioma de unidad organizativa (OU) (por ejemplo, CN = ORGANIZATIONALUNIT-display, CN = 409, CN = DisplaySpecifiers) y copia los valores del atributo **extracolumns** de la presentación predeterminada (por ejemplo, CN = default-display, CN = 409, CN = DisplaySpecifiers).</span><span class="sxs-lookup"><span data-stu-id="74579-195">Adds **msRTCSIP-PrimaryUserAddress** under the **extraColumns** attribute of each language organizational unit (OU) display specifier (for example, CN=organizationalUnit-Display,CN=409,CN=DisplaySpecifiers) and copies the values of the **extraColumns** attribute of the default display (for example, CN=default-Display, CN=409,CN=DisplaySpecifiers).</span></span>

  - <span data-ttu-id="74579-196">Agrega **atributos msRTCSIP-PrimaryUserAddress**, **msRTCSIP-PrimaryHomeServer**y **msRTCSIP-UserEnabled** al atributo **attributeDisplayNames** de cada especificador de visualización de idioma para los objetos users, Contacts e INETORGPERSON (por ejemplo, en Inglés: CN = user-Display, CN = 409, CN = DisplaySpecifiers).</span><span class="sxs-lookup"><span data-stu-id="74579-196">Adds **msRTCSIP-PrimaryUserAddress**, **msRTCSIP-PrimaryHomeServer**, and **msRTCSIP-UserEnabled** filtering attributes under the **attributeDisplayNames** attribute of each language display specifier for Users, Contacts, and InetOrgPerson objects (for example, in English: CN=user-Display,CN=409,CN=DisplaySpecifiers).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

