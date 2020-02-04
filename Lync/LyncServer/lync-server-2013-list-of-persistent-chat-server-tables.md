---
title: 'Lync Server 2013: Lista de tablas de servidores de chat persistente'
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
ms.openlocfilehash: 4902f0710752dd38c146b01bddcc44e135735201
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765408"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-persistent-chat-server-tables-in-lync-server-2013"></a><span data-ttu-id="155cc-102">Lista de tablas de servidores de chat persistente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="155cc-102">List of Persistent Chat Server tables in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="155cc-103">_**Última modificación del tema:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="155cc-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="155cc-104">El esquema de base de datos de chat persistente consta de las siguientes tablas.</span><span class="sxs-lookup"><span data-stu-id="155cc-104">The Persistent Chat database schema consists of the following tables.</span></span>

<div>

## <a name="active-directory-sync"></a><span data-ttu-id="155cc-105">Sincronización de Active Directory</span><span class="sxs-lookup"><span data-stu-id="155cc-105">Active Directory Sync</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="155cc-106">Tabla</span><span class="sxs-lookup"><span data-stu-id="155cc-106">Table</span></span></th>
<th><span data-ttu-id="155cc-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="155cc-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="155cc-108"><a href="lync-server-2013-tbladcookie.md">tblADCookie en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="155cc-108"><a href="lync-server-2013-tbladcookie.md">tblADCookie in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="155cc-109">Contiene las cookies de sincronización del Protocolo ligero de acceso a directorios (LDAP).</span><span class="sxs-lookup"><span data-stu-id="155cc-109">Contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span> <span data-ttu-id="155cc-110">Cada fila corresponde a un dominio de servicios de dominio de Active Directory en el que el servidor de chat persistente está supervisando activamente los cambios.</span><span class="sxs-lookup"><span data-stu-id="155cc-110">Each row corresponds to an Active Directory Domain Services domain that Persistent Chat Server is actively monitoring for changes.</span></span> <span data-ttu-id="155cc-111">(En esta tabla solo se representan los dominios de Active Directory pertinentes para el servidor de chat persistente).</span><span class="sxs-lookup"><span data-stu-id="155cc-111">(Only the Active Directory domains that are relevant for Persistent Chat Server are represented in this table.)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="155cc-112"><a href="lync-server-2013-tblprincipalmemberdifference.md">tblPrincipalMemberDifference en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="155cc-112"><a href="lync-server-2013-tblprincipalmemberdifference.md">tblPrincipalMemberDifference in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="155cc-113">Contiene cambios en la pertenencia a grupos (miembros agregados y eliminados) que aún no han sido procesados por los pasos de sincronización de Active Directory más recientes y es una de las tablas temporales (junto con la tabla tblADUpdates) que se usa en el primer paso de la sincronización de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="155cc-113">Contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Sync steps and is one of the temporary tables (along with tblADUpdates table) that is used in the first step of Active Directory Sync.</span></span></p>
<p><span data-ttu-id="155cc-114">Los cambios de pertenencia se almacenan, se procesan o ambos, solo para los grupos que se muestran en la tabla tblPrincipal o que ya tienen miembros.</span><span class="sxs-lookup"><span data-stu-id="155cc-114">Membership changes are stored, processed, or both, only for groups that are listed in the tblPrincipal table or that already have members listed there.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="155cc-115"><a href="lync-server-2013-tbladupdates.md">tblADUpdates en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="155cc-115"><a href="lync-server-2013-tbladupdates.md">tblADUpdates in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="155cc-116">Contiene cambios en los servicios de dominio de Active Directory que aún no han sido procesados por los pasos de sincronización de Active Directory más recientes y es una de las tablas temporales (junto con la tabla tblPrincipalMemberDifference) que se usa en el primer paso de Active Directory. Sync.</span><span class="sxs-lookup"><span data-stu-id="155cc-116">Contains changes to Active Directory Domain Services that have not yet been processed by the later Active Directory Sync steps and is one of the temporary tables (along with the tblPrincipalMemberDifference table) that is used in the first step of Active Directory Sync.</span></span></p>
<p><span data-ttu-id="155cc-117">Los cambios en Active Directory se almacenan, se procesan o ambos solo para los principales que ya aparecen en la tabla tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="155cc-117">Changes to Active Directory are stored, processed, or both only for principals that are already listed in the tblPrincipal table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="155cc-118"><a href="lync-server-2013-tblprincipalmembers.md">tblPrincipalMembers en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="155cc-118"><a href="lync-server-2013-tblprincipalmembers.md">tblPrincipalMembers in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="155cc-119">Contiene pertenencias principales.</span><span class="sxs-lookup"><span data-stu-id="155cc-119">Contains principal memberships.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="155cc-120"><a href="lync-server-2013-tblprincipalmeta.md">tblPrincipalMeta en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="155cc-120"><a href="lync-server-2013-tblprincipalmeta.md">tblPrincipalMeta in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="155cc-121">Contiene las entidades de identidad que deben actualizarse desde Active Directory.</span><span class="sxs-lookup"><span data-stu-id="155cc-121">Contains the principals that have to be refreshed from Active Directory.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="155cc-122"><a href="lync-server-2013-tblskippedaffiliations.md">tblSkippedAffiliations en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="155cc-122"><a href="lync-server-2013-tblskippedaffiliations.md">tblSkippedAffiliations in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="155cc-123">Contiene afiliaciones que no se pudieron actualizar por alguna razón, generalmente debido a errores de acceso a Active Directory.</span><span class="sxs-lookup"><span data-stu-id="155cc-123">Contains affiliations that could not be refreshed for some reason, usually due to Active Directory access errors.</span></span></p>
<p><span data-ttu-id="155cc-124">Esta tabla es solo para fines informativos.</span><span class="sxs-lookup"><span data-stu-id="155cc-124">This table is for informational purposes only.</span></span> <span data-ttu-id="155cc-125">No se utiliza su contenido.</span><span class="sxs-lookup"><span data-stu-id="155cc-125">Its content is not used.</span></span></p>
<p><span data-ttu-id="155cc-126">Las principales de las afiliaciones que no se hayan actualizado correctamente se guardan en la tabla tblPrincipalMeta y se les da otra oportunidad para que se actualicen.</span><span class="sxs-lookup"><span data-stu-id="155cc-126">The principals with affiliations that could not be refreshed properly are kept in the tblPrincipalMeta table and are given another chance to be refreshed.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="principals-affiliations-nodes-scopes-and-roles"></a><span data-ttu-id="155cc-127">Principales, afiliaciones, nodos, ámbitos y roles</span><span class="sxs-lookup"><span data-stu-id="155cc-127">Principals, Affiliations, Nodes, Scopes, and Roles</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="155cc-128">Tabla</span><span class="sxs-lookup"><span data-stu-id="155cc-128">Table</span></span></th>
<th><span data-ttu-id="155cc-129">Descripción</span><span class="sxs-lookup"><span data-stu-id="155cc-129">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="155cc-130"><a href="lync-server-2013-tblprincipaltype.md">tblPrincipalType en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="155cc-130"><a href="lync-server-2013-tblprincipaltype.md">tblPrincipalType in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="155cc-131">Contiene tipos de principal para categorizar lo que hay en la tabla tblPrincipal.</span><span class="sxs-lookup"><span data-stu-id="155cc-131">Contains principal types to categorize what is in the tblPrincipal table.</span></span> <span data-ttu-id="155cc-132">Esta tabla es estática.</span><span class="sxs-lookup"><span data-stu-id="155cc-132">This table is static.</span></span> <span data-ttu-id="155cc-133">Se configura durante la creación de la base de datos y no cambia.</span><span class="sxs-lookup"><span data-stu-id="155cc-133">It is set up during database creation and does not change.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="155cc-134"><a href="lync-server-2013-tblprincipal.md">tblPrincipal enn Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="155cc-134"><a href="lync-server-2013-tblprincipal.md">tblPrincipal in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="155cc-135">Contiene todos los principales (usuarios, carpetas, grupos, etc.).</span><span class="sxs-lookup"><span data-stu-id="155cc-135">Contains all principals (users, folders, groups, and so on).</span></span> <span data-ttu-id="155cc-136">El servidor de chat persistente gestiona esto como una lista heterogénea plana.</span><span class="sxs-lookup"><span data-stu-id="155cc-136">Persistent Chat Server handles this as a flat heterogeneous list.</span></span> <span data-ttu-id="155cc-137">Varias columnas se basan en el tipo de cada principal.</span><span class="sxs-lookup"><span data-stu-id="155cc-137">Various columns are based on the type of each principal.</span></span></p>
<p><span data-ttu-id="155cc-138">La mayoría de estos principios son copias almacenadas en caché de los objetos almacenados en Active Directory.</span><span class="sxs-lookup"><span data-stu-id="155cc-138">Most of these principals are cached copies of objects stored in Active Directory.</span></span> <span data-ttu-id="155cc-139">La creación de la copia en caché en la tabla principal de estos objetos de Active Directory se denomina <em>suministro</em>.</span><span class="sxs-lookup"><span data-stu-id="155cc-139">Creating the cached copy in the Principal table of these Active Directory objects is referred as <em>provisioning</em>.</span></span></p>
<p><span data-ttu-id="155cc-140">Algunas entidades de identidad se crean de forma más agresiva que otras, y algunos objetos de Active Directory se pasan por alto.</span><span class="sxs-lookup"><span data-stu-id="155cc-140">Some principals are created more aggressively than others, and some Active Directory objects are ignored altogether.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="155cc-141"><a href="lync-server-2013-tblprincipalaffiliations.md">tblPrincipalAffiliations en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="155cc-141"><a href="lync-server-2013-tblprincipalaffiliations.md">tblPrincipalAffiliations in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="155cc-142">Contiene las afiliaciones principales que describen las pertenencias a grupos de seguridad de Active Directory, contenedores de Active Directory, etc.</span><span class="sxs-lookup"><span data-stu-id="155cc-142">Contains principal affiliations that describe memberships in Active Directory security groups, Active Directory containers, and so on.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="155cc-143"><a href="lync-server-2013-tblnode.md">tblNode en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="155cc-143"><a href="lync-server-2013-tblnode.md">tblNode in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="155cc-144">Contiene el nodo de categoría, administrado en el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="155cc-144">Contains the category node, as managed in Lync Server Control Panel.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="155cc-145"><a href="lync-server-2013-tblroletype.md">tblRoleType en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="155cc-145"><a href="lync-server-2013-tblroletype.md">tblRoleType in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="155cc-146">Contiene tipos de roles y sus conjuntos de permisos asociados.</span><span class="sxs-lookup"><span data-stu-id="155cc-146">Contains role types and their associated permission sets.</span></span> <span data-ttu-id="155cc-147">Esta tabla de búsqueda es estática.</span><span class="sxs-lookup"><span data-stu-id="155cc-147">This lookup table is static.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="155cc-148"><a href="lync-server-2013-tblscopeprincipal.md">tblScopePrincipal en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="155cc-148"><a href="lync-server-2013-tblscopeprincipal.md">tblScopePrincipal in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="155cc-149">Contiene ámbitos asignados a los nodos.</span><span class="sxs-lookup"><span data-stu-id="155cc-149">Contains scopes assigned to nodes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="155cc-150"><a href="lync-server-2013-tblprincipalrole.md">tblPrincipalRole en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="155cc-150"><a href="lync-server-2013-tblprincipalrole.md">tblPrincipalRole in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="155cc-151">Contiene roles asignados a nodos.</span><span class="sxs-lookup"><span data-stu-id="155cc-151">Contains roles assigned to nodes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="155cc-152"><a href="lync-server-2013-tblsiopwhitelist.md">tblSiopWhiteList en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="155cc-152"><a href="lync-server-2013-tblsiopwhitelist.md">tblSiopWhiteList in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="155cc-153">Contiene los complementos registrados que se pueden asociar con nodos.</span><span class="sxs-lookup"><span data-stu-id="155cc-153">Contains the registered Add-ins that can be associated with nodes.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="155cc-154"><a href="lync-server-2013-tblenumattribute.md">tblEnumAttribute en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="155cc-154"><a href="lync-server-2013-tblenumattribute.md">tblEnumAttribute in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="155cc-155">Contiene solo los atributos &quot;de&quot; visibilidad &quot;y&quot; comportamiento codificados que se usan en la tabla tblNode.</span><span class="sxs-lookup"><span data-stu-id="155cc-155">Contains only the hardcoded &quot;Visibility&quot; and &quot;Behavior&quot; attributes that are used in the tblNode table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="155cc-156"><a href="lync-server-2013-tblenumvalue.md">tblEnumValue en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="155cc-156"><a href="lync-server-2013-tblenumvalue.md">tblEnumValue in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="155cc-157">Contiene los valores de los atributos &quot;de comportamiento&quot; de visibilidad "y" que se usan en la tabla tblNode.</span><span class="sxs-lookup"><span data-stu-id="155cc-157">Contains the values of the hardcoded &quot;Visibility” and “Behavior&quot; attributes that are used in the tblNode table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="invites-chats-and-other-client-support"></a><span data-ttu-id="155cc-158">Invitaciones, chats y otros tipos de asistencia al cliente</span><span class="sxs-lookup"><span data-stu-id="155cc-158">Invites, Chats, and Other Client Support</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="155cc-159">Tabla</span><span class="sxs-lookup"><span data-stu-id="155cc-159">Table</span></span></th>
<th><span data-ttu-id="155cc-160">Descripción</span><span class="sxs-lookup"><span data-stu-id="155cc-160">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="155cc-161"><a href="lync-server-2013-tblprincipalinvites.md">tblPrincipalInvites en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="155cc-161"><a href="lync-server-2013-tblprincipalinvites.md">tblPrincipalInvites in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="155cc-162">Contiene invitaciones para todos los usuarios aprovisionados del sistema en todos los nodos con la opción de invitación automática habilitada.</span><span class="sxs-lookup"><span data-stu-id="155cc-162">Contains invites for all provisioned users in the system for all nodes with Auto Invite enabled.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="155cc-163"><a href="lync-server-2013-tblchat.md">tblChat en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="155cc-163"><a href="lync-server-2013-tblchat.md">tblChat in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="155cc-164">Contiene todos los mensajes instantáneos.</span><span class="sxs-lookup"><span data-stu-id="155cc-164">Contains all chat messages.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="155cc-165"><a href="lync-server-2013-tbllastinviteid.md">tblLastInviteId en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="155cc-165"><a href="lync-server-2013-tbllastinviteid.md">tblLastInviteId in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="155cc-166">Contiene el identificador de la última invitación que se generó (y se usó en la tabla tblPrincipalInvites) para cada usuario.</span><span class="sxs-lookup"><span data-stu-id="155cc-166">Contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="155cc-167"><a href="lync-server-2013-tbllastchatid.md">tblLastChatId en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="155cc-167"><a href="lync-server-2013-tbllastchatid.md">tblLastChatId in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="155cc-168">Contiene el último identificador de chat generado (y usado en la tabla tblChat) para cada usuario.</span><span class="sxs-lookup"><span data-stu-id="155cc-168">Contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="155cc-169"><a href="lync-server-2013-tblpreference.md">tblPreference en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="155cc-169"><a href="lync-server-2013-tblpreference.md">tblPreference in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="155cc-170">Contiene preferencias de clientes de usuario (solo utilizadas por clientes heredados).</span><span class="sxs-lookup"><span data-stu-id="155cc-170">Contains user client preferences (used by legacy clients only).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="155cc-171"><a href="lync-server-2013-tblfiletoken.md">tblFileToken en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="155cc-171"><a href="lync-server-2013-tblfiletoken.md">tblFileToken in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="155cc-172">Contiene tokens temporales para la transferencia de archivos.</span><span class="sxs-lookup"><span data-stu-id="155cc-172">Contains temporary tokens for file transfer purposes.</span></span> <span data-ttu-id="155cc-173">Cada vez que se carga o descarga un archivo, el servicio de chat persistente genera un token que el cliente usa para acceder al almacén de archivos del servicio Web.</span><span class="sxs-lookup"><span data-stu-id="155cc-173">Each time a file is uploaded or downloaded, the Persistent Chat service generates a token that the client uses to access the Web service file store.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="server-support"></a><span data-ttu-id="155cc-174">Compatibilidad con servidores</span><span class="sxs-lookup"><span data-stu-id="155cc-174">Server Support</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="155cc-175">Tabla</span><span class="sxs-lookup"><span data-stu-id="155cc-175">Table</span></span></th>
<th><span data-ttu-id="155cc-176">Descripción</span><span class="sxs-lookup"><span data-stu-id="155cc-176">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="155cc-177"><a href="lync-server-2013-tblserveridentity.md">tblServerIdentity en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="155cc-177"><a href="lync-server-2013-tblserveridentity.md">tblServerIdentity in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="155cc-178">Contiene los servidores activos del grupo de servidores de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="155cc-178">Contains the active servers in the Persistent Chat Server pool.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="155cc-179"><a href="lync-server-2013-tbladminlock.md">tblAdminLock en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="155cc-179"><a href="lync-server-2013-tbladminlock.md">tblAdminLock in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="155cc-180">Contiene el bloqueo de administrador para ejecutar algunos comandos de administrador.</span><span class="sxs-lookup"><span data-stu-id="155cc-180">Contains the administrator lock to run some administrator commands.</span></span> <span data-ttu-id="155cc-181">La entrada de revisión del sistema de la tabla tblSystemRevision se incrementa después de cada lanzamiento de bloqueo.</span><span class="sxs-lookup"><span data-stu-id="155cc-181">The system revision entry in the tblSystemRevision table is incremented after each release of the lock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="155cc-182"><a href="lync-server-2013-tblsystemrevision.md">tblSystemRevision en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="155cc-182"><a href="lync-server-2013-tblsystemrevision.md">tblSystemRevision in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="155cc-183">Contiene la entrada del número de revisión usado (junto con la tabla tblAdminLock) para lograr la coherencia entre varios servidores.</span><span class="sxs-lookup"><span data-stu-id="155cc-183">Contains the revision number entry used (along with the tblAdminLock table) for achieving consistency across multiple servers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="155cc-184"><a href="lync-server-2013-tblactivepeers.md">tblActivePeers en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="155cc-184"><a href="lync-server-2013-tblactivepeers.md">tblActivePeers in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="155cc-185">Contiene conexiones de punto a punto actuales entre servicios de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="155cc-185">Contains current peer-to-peer connections between Persistent Chat services.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="155cc-186"><a href="lync-server-2013-tblconfig.md">tblConfig en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="155cc-186"><a href="lync-server-2013-tblconfig.md">tblConfig in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="155cc-187">Contiene la configuración no compatible del servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="155cc-187">Contains the Persistent Chat Server unsupported configuration.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

