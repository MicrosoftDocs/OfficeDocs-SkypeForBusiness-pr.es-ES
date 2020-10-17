---
title: 'Lync Server 2013: lista de tablas del servidor de chat persistente'
description: 'Lync Server 2013: lista de tablas del servidor de chat persistente.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: List of Persistent Chat Server tables
ms:assetid: 26c9e271-3516-4d90-b930-70fec4e359ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558628(v=OCS.15)
ms:contentKeyID: 48183659
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 838e6d8f83b137923075851b29df4c602a487391
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550056"
---
# <a name="list-of-persistent-chat-server-tables-in-lync-server-2013"></a><span data-ttu-id="2a768-103">Lista de tablas del servidor de chat persistente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2a768-103">List of Persistent Chat Server tables in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2a768-104">_**Última modificación del tema:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="2a768-104">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="2a768-105">El esquema de base de datos de chat persistente consta de las siguientes tablas.</span><span class="sxs-lookup"><span data-stu-id="2a768-105">The Persistent Chat database schema consists of the following tables.</span></span>

<div>

## <a name="active-directory-sync"></a><span data-ttu-id="2a768-106">Sincronización de Active Directory</span><span class="sxs-lookup"><span data-stu-id="2a768-106">Active Directory Sync</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2a768-107">Table</span><span class="sxs-lookup"><span data-stu-id="2a768-107">Table</span></span></th>
<th><span data-ttu-id="2a768-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="2a768-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2a768-109"><a href="lync-server-2013-tbladcookie.md">tblADCookie en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2a768-109"><a href="lync-server-2013-tbladcookie.md">tblADCookie in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2a768-110">Contiene las cookies de sincronización del Protocolo ligero de acceso a directorios (LDAP) actual.</span><span class="sxs-lookup"><span data-stu-id="2a768-110">Contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span> <span data-ttu-id="2a768-111">Cada fila corresponde a un dominio de servicios de dominio de Active Directory que el servidor de chat persistente supervisa activamente los cambios.</span><span class="sxs-lookup"><span data-stu-id="2a768-111">Each row corresponds to an Active Directory Domain Services domain that Persistent Chat Server is actively monitoring for changes.</span></span> <span data-ttu-id="2a768-112">(En esta tabla solo se representan los dominios de Active Directory relevantes para el servidor de chat persistente).</span><span class="sxs-lookup"><span data-stu-id="2a768-112">(Only the Active Directory domains that are relevant for Persistent Chat Server are represented in this table.)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a768-113"><a href="lync-server-2013-tblprincipalmemberdifference.md">tblPrincipalMemberDifference en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2a768-113"><a href="lync-server-2013-tblprincipalmemberdifference.md">tblPrincipalMemberDifference in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2a768-114">Contiene los cambios en la pertenencia a grupos (miembros agregados y eliminados) que aún no han sido procesados por los pasos de sincronización de Active Directory posteriores y es una de las tablas temporales (junto con la tabla tblADUpdates) que se usa en el primer paso de la sincronización de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2a768-114">Contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Sync steps and is one of the temporary tables (along with tblADUpdates table) that is used in the first step of Active Directory Sync.</span></span></p>
<p><span data-ttu-id="2a768-115">Los cambios de pertenencia se almacenan, se procesan o ambos solo para los grupos que se enumeran en la tabla tblPrincipal o que ya tienen miembros en la lista.</span><span class="sxs-lookup"><span data-stu-id="2a768-115">Membership changes are stored, processed, or both, only for groups that are listed in the tblPrincipal table or that already have members listed there.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a768-116"><a href="lync-server-2013-tbladupdates.md">tblADUpdates en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2a768-116"><a href="lync-server-2013-tbladupdates.md">tblADUpdates in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2a768-117">Contiene cambios en los servicios de dominio de Active Directory que todavía no han sido procesados por los pasos de sincronización de Active Directory posteriores y es una de las tablas temporales (junto con la tabla tblPrincipalMemberDifference) que se usa en el primer paso de la sincronización de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2a768-117">Contains changes to Active Directory Domain Services that have not yet been processed by the later Active Directory Sync steps and is one of the temporary tables (along with the tblPrincipalMemberDifference table) that is used in the first step of Active Directory Sync.</span></span></p>
<p><span data-ttu-id="2a768-118">Los cambios en Active Directory se almacenan, se procesan o ambos solo para las entidades de identidad que ya aparecen en la tabla tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="2a768-118">Changes to Active Directory are stored, processed, or both only for principals that are already listed in the tblPrincipal table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a768-119"><a href="lync-server-2013-tblprincipalmembers.md">tblPrincipalMembers en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2a768-119"><a href="lync-server-2013-tblprincipalmembers.md">tblPrincipalMembers in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2a768-120">Contiene pertenencias principales.</span><span class="sxs-lookup"><span data-stu-id="2a768-120">Contains principal memberships.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a768-121"><a href="lync-server-2013-tblprincipalmeta.md">tblPrincipalMeta en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2a768-121"><a href="lync-server-2013-tblprincipalmeta.md">tblPrincipalMeta in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2a768-122">Contiene las entidades de identidad que se deben actualizar desde Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2a768-122">Contains the principals that have to be refreshed from Active Directory.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a768-123"><a href="lync-server-2013-tblskippedaffiliations.md">tblSkippedAffiliations en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2a768-123"><a href="lync-server-2013-tblskippedaffiliations.md">tblSkippedAffiliations in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2a768-124">Contiene las afiliaciones que no se pudieron actualizar por algún motivo, normalmente debido a errores de acceso de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2a768-124">Contains affiliations that could not be refreshed for some reason, usually due to Active Directory access errors.</span></span></p>
<p><span data-ttu-id="2a768-125">Esta tabla es solo para fines informativos.</span><span class="sxs-lookup"><span data-stu-id="2a768-125">This table is for informational purposes only.</span></span> <span data-ttu-id="2a768-126">Su contenido no se usa.</span><span class="sxs-lookup"><span data-stu-id="2a768-126">Its content is not used.</span></span></p>
<p><span data-ttu-id="2a768-127">Las identidades con las afiliaciones que no se pudieron actualizar correctamente se conservan en la tabla tblPrincipalMeta y tienen otra posibilidad de actualizarse.</span><span class="sxs-lookup"><span data-stu-id="2a768-127">The principals with affiliations that could not be refreshed properly are kept in the tblPrincipalMeta table and are given another chance to be refreshed.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="principals-affiliations-nodes-scopes-and-roles"></a><span data-ttu-id="2a768-128">Entidades de identidad, afiliaciones, nodos, ámbitos y roles</span><span class="sxs-lookup"><span data-stu-id="2a768-128">Principals, Affiliations, Nodes, Scopes, and Roles</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2a768-129">Table</span><span class="sxs-lookup"><span data-stu-id="2a768-129">Table</span></span></th>
<th><span data-ttu-id="2a768-130">Descripción</span><span class="sxs-lookup"><span data-stu-id="2a768-130">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2a768-131"><a href="lync-server-2013-tblprincipaltype.md">tblPrincipalType en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2a768-131"><a href="lync-server-2013-tblprincipaltype.md">tblPrincipalType in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2a768-132">Contiene los tipos de entidad de tipo para categorizar lo que se encuentra en la tabla tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="2a768-132">Contains principal types to categorize what is in the tblPrincipal table.</span></span> <span data-ttu-id="2a768-133">Esta tabla es estática.</span><span class="sxs-lookup"><span data-stu-id="2a768-133">This table is static.</span></span> <span data-ttu-id="2a768-134">Se configura durante la creación de la base de datos y no cambia.</span><span class="sxs-lookup"><span data-stu-id="2a768-134">It is set up during database creation and does not change.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a768-135"><a href="lync-server-2013-tblprincipal.md">tblPrincipal en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2a768-135"><a href="lync-server-2013-tblprincipal.md">tblPrincipal in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2a768-136">Contiene todas las entidades de identidad (usuarios, carpetas, grupos, etc.).</span><span class="sxs-lookup"><span data-stu-id="2a768-136">Contains all principals (users, folders, groups, and so on).</span></span> <span data-ttu-id="2a768-137">El servidor de chat persistente administra esto como una lista heterogénea plana.</span><span class="sxs-lookup"><span data-stu-id="2a768-137">Persistent Chat Server handles this as a flat heterogeneous list.</span></span> <span data-ttu-id="2a768-138">Varias columnas se basan en el tipo de cada entidad de tipo.</span><span class="sxs-lookup"><span data-stu-id="2a768-138">Various columns are based on the type of each principal.</span></span></p>
<p><span data-ttu-id="2a768-139">La mayoría de estas entidades son copias en caché de los objetos almacenados en Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2a768-139">Most of these principals are cached copies of objects stored in Active Directory.</span></span> <span data-ttu-id="2a768-140">La creación de la copia en caché en la tabla principal de estos objetos de Active Directory se denomina <em>aprovisionamiento</em>.</span><span class="sxs-lookup"><span data-stu-id="2a768-140">Creating the cached copy in the Principal table of these Active Directory objects is referred as <em>provisioning</em>.</span></span></p>
<p><span data-ttu-id="2a768-141">Algunas entidades de identidad se crean de forma más agresiva que otras, y algunos objetos de Active Directory se omiten por completo.</span><span class="sxs-lookup"><span data-stu-id="2a768-141">Some principals are created more aggressively than others, and some Active Directory objects are ignored altogether.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a768-142"><a href="lync-server-2013-tblprincipalaffiliations.md">tblPrincipalAffiliations en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2a768-142"><a href="lync-server-2013-tblprincipalaffiliations.md">tblPrincipalAffiliations in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2a768-143">Contiene las afiliaciones principales que describen las pertenencias a grupos de seguridad de Active Directory, contenedores de Active Directory, etc.</span><span class="sxs-lookup"><span data-stu-id="2a768-143">Contains principal affiliations that describe memberships in Active Directory security groups, Active Directory containers, and so on.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a768-144"><a href="lync-server-2013-tblnode.md">tblNode en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2a768-144"><a href="lync-server-2013-tblnode.md">tblNode in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2a768-145">Contiene el nodo Category, tal como se administra en el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2a768-145">Contains the category node, as managed in Lync Server Control Panel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a768-146"><a href="lync-server-2013-tblroletype.md">tblRoleType en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2a768-146"><a href="lync-server-2013-tblroletype.md">tblRoleType in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2a768-147">Contiene los tipos de funciones y sus conjuntos de permisos asociados.</span><span class="sxs-lookup"><span data-stu-id="2a768-147">Contains role types and their associated permission sets.</span></span> <span data-ttu-id="2a768-148">Esta tabla de búsqueda es estática.</span><span class="sxs-lookup"><span data-stu-id="2a768-148">This lookup table is static.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a768-149"><a href="lync-server-2013-tblscopeprincipal.md">tblScopePrincipal en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2a768-149"><a href="lync-server-2013-tblscopeprincipal.md">tblScopePrincipal in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2a768-150">Contiene ámbitos asignados a nodos.</span><span class="sxs-lookup"><span data-stu-id="2a768-150">Contains scopes assigned to nodes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a768-151"><a href="lync-server-2013-tblprincipalrole.md">tblPrincipalRole en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2a768-151"><a href="lync-server-2013-tblprincipalrole.md">tblPrincipalRole in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2a768-152">Contiene los roles asignados a los nodos.</span><span class="sxs-lookup"><span data-stu-id="2a768-152">Contains roles assigned to nodes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a768-153"><a href="lync-server-2013-tblsiopwhitelist.md">tblSiopWhiteList en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2a768-153"><a href="lync-server-2013-tblsiopwhitelist.md">tblSiopWhiteList in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2a768-154">Contiene los complementos registrados que se pueden asociar con nodos.</span><span class="sxs-lookup"><span data-stu-id="2a768-154">Contains the registered Add-ins that can be associated with nodes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a768-155"><a href="lync-server-2013-tblenumattribute.md">tblEnumAttribute en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2a768-155"><a href="lync-server-2013-tblenumattribute.md">tblEnumAttribute in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2a768-156">Contiene solo los &quot; &quot; atributos de visibilidad y comportamiento codificados &quot; &quot; que se usan en la tabla tblNode.</span><span class="sxs-lookup"><span data-stu-id="2a768-156">Contains only the hardcoded &quot;Visibility&quot; and &quot;Behavior&quot; attributes that are used in the tblNode table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a768-157"><a href="lync-server-2013-tblenumvalue.md">tblEnumValue en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2a768-157"><a href="lync-server-2013-tblenumvalue.md">tblEnumValue in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2a768-158">Contiene los valores de los atributos de comportamiento de visibilidad de contenido codificado &quot; "y" &quot; que se usan en la tabla tblNode.</span><span class="sxs-lookup"><span data-stu-id="2a768-158">Contains the values of the hardcoded &quot;Visibility” and “Behavior&quot; attributes that are used in the tblNode table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="invites-chats-and-other-client-support"></a><span data-ttu-id="2a768-159">Invitaciones, chats y otros tipos de compatibilidad con clientes</span><span class="sxs-lookup"><span data-stu-id="2a768-159">Invites, Chats, and Other Client Support</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2a768-160">Table</span><span class="sxs-lookup"><span data-stu-id="2a768-160">Table</span></span></th>
<th><span data-ttu-id="2a768-161">Descripción</span><span class="sxs-lookup"><span data-stu-id="2a768-161">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2a768-162"><a href="lync-server-2013-tblprincipalinvites.md">tblPrincipalInvites en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2a768-162"><a href="lync-server-2013-tblprincipalinvites.md">tblPrincipalInvites in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2a768-163">Contiene invitaciones para todos los usuarios aprovisionados del sistema para todos los nodos con la invitación automática habilitada.</span><span class="sxs-lookup"><span data-stu-id="2a768-163">Contains invites for all provisioned users in the system for all nodes with Auto Invite enabled.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a768-164"><a href="lync-server-2013-tblchat.md">tblChat en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2a768-164"><a href="lync-server-2013-tblchat.md">tblChat in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2a768-165">Contiene todos los mensajes de chat.</span><span class="sxs-lookup"><span data-stu-id="2a768-165">Contains all chat messages.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a768-166"><a href="lync-server-2013-tbllastinviteid.md">tblLastInviteId en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2a768-166"><a href="lync-server-2013-tbllastinviteid.md">tblLastInviteId in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2a768-167">Contiene el último identificador de invitación generado (y utilizado en la tabla tblPrincipalInvites) para cada usuario.</span><span class="sxs-lookup"><span data-stu-id="2a768-167">Contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a768-168"><a href="lync-server-2013-tbllastchatid.md">tblLastChatId en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2a768-168"><a href="lync-server-2013-tbllastchatid.md">tblLastChatId in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2a768-169">Contiene el último identificador de chat generado (y utilizado en la tabla tblChat) para cada usuario.</span><span class="sxs-lookup"><span data-stu-id="2a768-169">Contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a768-170"><a href="lync-server-2013-tblpreference.md">tblPreference en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2a768-170"><a href="lync-server-2013-tblpreference.md">tblPreference in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2a768-171">Contiene las preferencias del cliente de usuario (solo las usan los clientes heredados).</span><span class="sxs-lookup"><span data-stu-id="2a768-171">Contains user client preferences (used by legacy clients only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a768-172"><a href="lync-server-2013-tblfiletoken.md">tblFileToken en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2a768-172"><a href="lync-server-2013-tblfiletoken.md">tblFileToken in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2a768-173">Contiene tokens temporales para propósitos de transferencia de archivos.</span><span class="sxs-lookup"><span data-stu-id="2a768-173">Contains temporary tokens for file transfer purposes.</span></span> <span data-ttu-id="2a768-174">Cada vez que se carga o descarga un archivo, el servicio de chat persistente genera un token que el cliente usa para obtener acceso al almacén de archivos del servicio Web.</span><span class="sxs-lookup"><span data-stu-id="2a768-174">Each time a file is uploaded or downloaded, the Persistent Chat service generates a token that the client uses to access the Web service file store.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="server-support"></a><span data-ttu-id="2a768-175">Compatibilidad con servidores</span><span class="sxs-lookup"><span data-stu-id="2a768-175">Server Support</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2a768-176">Table</span><span class="sxs-lookup"><span data-stu-id="2a768-176">Table</span></span></th>
<th><span data-ttu-id="2a768-177">Descripción</span><span class="sxs-lookup"><span data-stu-id="2a768-177">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2a768-178"><a href="lync-server-2013-tblserveridentity.md">Tabla tblserveridentity en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2a768-178"><a href="lync-server-2013-tblserveridentity.md">tblServerIdentity in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2a768-179">Contiene los servidores activos en el grupo de servidores de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="2a768-179">Contains the active servers in the Persistent Chat Server pool.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a768-180"><a href="lync-server-2013-tbladminlock.md">tblAdminLock en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2a768-180"><a href="lync-server-2013-tbladminlock.md">tblAdminLock in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2a768-181">Contiene el bloqueo de administrador para ejecutar algunos comandos de administrador.</span><span class="sxs-lookup"><span data-stu-id="2a768-181">Contains the administrator lock to run some administrator commands.</span></span> <span data-ttu-id="2a768-182">La entrada de revisión del sistema en la tabla tblSystemRevision se incrementa después de cada versión del bloqueo.</span><span class="sxs-lookup"><span data-stu-id="2a768-182">The system revision entry in the tblSystemRevision table is incremented after each release of the lock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a768-183"><a href="lync-server-2013-tblsystemrevision.md">tblSystemRevision en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2a768-183"><a href="lync-server-2013-tblsystemrevision.md">tblSystemRevision in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2a768-184">Contiene la entrada del número de revisión usado (junto con la tabla tblAdminLock) para lograr la coherencia entre varios servidores.</span><span class="sxs-lookup"><span data-stu-id="2a768-184">Contains the revision number entry used (along with the tblAdminLock table) for achieving consistency across multiple servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a768-185"><a href="lync-server-2013-tblactivepeers.md">tblActivePeers en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2a768-185"><a href="lync-server-2013-tblactivepeers.md">tblActivePeers in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2a768-186">Contiene las conexiones punto a punto actuales entre los servicios de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="2a768-186">Contains current peer-to-peer connections between Persistent Chat services.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a768-187"><a href="lync-server-2013-tblconfig.md">tblConfig en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2a768-187"><a href="lync-server-2013-tblconfig.md">tblConfig in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="2a768-188">Contiene la configuración no admitida del servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="2a768-188">Contains the Persistent Chat Server unsupported configuration.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

