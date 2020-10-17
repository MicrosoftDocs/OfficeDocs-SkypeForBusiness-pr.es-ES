---
title: 'Lync Server 2013: lista de comprobación para la implementación del archivado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for Archiving
ms:assetid: 7479734d-be01-40d9-ad82-320a09d19d04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205009(v=OCS.15)
ms:contentKeyID: 48184516
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ccec3917e892d1ba6c3e1841773c77e8c2d015d0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514533"
---
# <a name="deployment-checklist-for-archiving-in-lync-server-2013"></a><span data-ttu-id="b0b86-102">Lista de comprobación para la implementación del archivado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b0b86-102">Deployment checklist for Archiving in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b0b86-103">_**Última modificación del tema:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="b0b86-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="b0b86-104">El archivado se instala automáticamente en cada uno de los servidores front-end de la implementación de Lync Server 2013, pero es necesario configurarlo antes de poder usarlo.</span><span class="sxs-lookup"><span data-stu-id="b0b86-104">Archiving is automatically installed on each Front End Server in your Lync Server 2013 deployment, but you still need to set it up before you can use it.</span></span> <span data-ttu-id="b0b86-105">Los pasos necesarios para configurarlo, como se resume en esta sección, constituyen la implementación del archivado.</span><span class="sxs-lookup"><span data-stu-id="b0b86-105">The steps required to set it up, as summarized in this section, constitute the deployment of Archiving.</span></span>

<div>

## <a name="deployment-sequence"></a><span data-ttu-id="b0b86-106">Secuencia de implementación</span><span class="sxs-lookup"><span data-stu-id="b0b86-106">Deployment Sequence</span></span>

<span data-ttu-id="b0b86-107">La configuración del archivado depende de la opción de almacenamiento que elija:</span><span class="sxs-lookup"><span data-stu-id="b0b86-107">How you set up Archiving depends on which storage option you choose:</span></span>

  - <span data-ttu-id="b0b86-108">Si usa la integración de Microsoft Exchange para todos los usuarios de la implementación, no es necesario que configure las directivas de archivado de Lync Server 2013 para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="b0b86-108">If you use Microsoft Exchange integration for all users in your deployment, you don’t need to configure Lync Server 2013 Archiving policies for your users.</span></span> <span data-ttu-id="b0b86-109">En su lugar, configure las directivas de suspensión de In-Place de Exchange para admitir el archivado para los usuarios hospedados en Exchange 2013, con sus buzones colocados en In-Place retenido.</span><span class="sxs-lookup"><span data-stu-id="b0b86-109">Instead, configure your Exchange In-Place Hold policies to support archiving for users homed on Exchange 2013, with their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="b0b86-110">Para obtener más información acerca de la configuración de estas directivas, consulte la documentación del producto de Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="b0b86-110">For details about configuring these policies, see the Exchange 2013 product documentation.</span></span>

  - <span data-ttu-id="b0b86-111">Si no usa la integración de Microsoft Exchange para todos los usuarios de la implementación, debe agregar bases de datos de archivado de Lync Server (bases de datos de SQL Server) a la topología y, a continuación, publicarla, así como configurar directivas y opciones de configuración para los usuarios, antes de poder archivar datos para esos usuarios.</span><span class="sxs-lookup"><span data-stu-id="b0b86-111">If you do not use Microsoft Exchange integration for all users in your deployment, you need to add Lync Server Archiving databases (SQL Server databases) to your topology and then publish it, as well as configure policies and settings for your users, before you can archive data for those users.</span></span> <span data-ttu-id="b0b86-112">Puede implementar las bases de datos de archivado al mismo tiempo que implementa la topología inicial o después de haber implementado al menos un grupo de servidores front-end o un servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="b0b86-112">You can deploy Archiving databases at the same time that you deploy your initial topology or after you have deployed at least one Front End pool or Standard Edition server.</span></span> <span data-ttu-id="b0b86-113">En este documento se describe cómo implementar las bases de datos de archivado agregándolas a una implementación existente.</span><span class="sxs-lookup"><span data-stu-id="b0b86-113">This document describes how to deploy Archiving databases by adding them to an existing deployment.</span></span>

<span data-ttu-id="b0b86-114">Si habilita el archivado en un grupo de servidores front-end o un servidor Standard Edition, debe habilitarlo para todos los demás grupos de servidores front-end y servidores Standard Edition de la implementación.</span><span class="sxs-lookup"><span data-stu-id="b0b86-114">If you enable archiving in one Front End pool or Standard Edition server, you should enable it for all other Front End pools and Standard Edition servers in your deployment.</span></span> <span data-ttu-id="b0b86-115">Esto se debe a que los usuarios cuyas comunicaciones deben archivarse pueden ser invitados a una conversación de mensajería instantánea en grupo o a reuniones hospedadas en un grupo de servidores diferente.</span><span class="sxs-lookup"><span data-stu-id="b0b86-115">This is because users whose communications are required to be archived can be invited to a group IM conversation or meetings hosted on a different pool.</span></span> <span data-ttu-id="b0b86-116">Si el archivado no está habilitado en el grupo en el que está hospedada la conversación o la reunión, es posible que no se Archive la sesión completa.</span><span class="sxs-lookup"><span data-stu-id="b0b86-116">If archiving is not enabled on the pool where the conversation or meeting is hosted, the complete session may not be archived.</span></span> <span data-ttu-id="b0b86-117">En estos casos, los mensajes instantáneos con usuarios habilitados para archivado todavía pueden archivarse, pero no para los archivos de contenido de conferencias, ni eventos de unión o abandono de conferencias.</span><span class="sxs-lookup"><span data-stu-id="b0b86-117">In these cases, IMs with archiving-enabled users still can be archived, but not for conferencing content files, and conference join or leave events.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b0b86-118">Si el archivado es crítico en su organización por motivos de cumplimiento, asegúrese de implementar el archivado, configurar directivas y otras opciones en el nivel adecuado y habilitarlo para todos los usuarios apropiados, antes de habilitar a esos usuarios para Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b0b86-118">If archiving is critical in your organization for compliance reasons, be sure to deploy Archiving, configure policies and other options at the appropriate level, and enable it for all appropriate users, before you enable those users for Lync Server 2013.</span></span>



</div>

</div>

<div>

## <a name="archiving-deployment-process"></a><span data-ttu-id="b0b86-119">Proceso de implementación de archivado</span><span class="sxs-lookup"><span data-stu-id="b0b86-119">Archiving Deployment Process</span></span>

<span data-ttu-id="b0b86-120">En la tabla siguiente se proporciona información general sobre los pasos necesarios para implementar el archivado en una topología existente.</span><span class="sxs-lookup"><span data-stu-id="b0b86-120">The following table provides an overview of the steps required to deploy archiving in an existing topology.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b0b86-121">Fase</span><span class="sxs-lookup"><span data-stu-id="b0b86-121">Phase</span></span></th>
<th><span data-ttu-id="b0b86-122">Pasos</span><span class="sxs-lookup"><span data-stu-id="b0b86-122">Steps</span></span></th>
<th><span data-ttu-id="b0b86-123">Roles y pertenencia a grupos</span><span class="sxs-lookup"><span data-stu-id="b0b86-123">Roles and group memberships</span></span></th>
<th><span data-ttu-id="b0b86-124">Documentación</span><span class="sxs-lookup"><span data-stu-id="b0b86-124">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b0b86-125"><strong>Instale el hardware y el software necesario como requisito previo</strong></span><span class="sxs-lookup"><span data-stu-id="b0b86-125"><strong>Install prerequisite hardware and software</strong></span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="b0b86-126">Para usar la integración de Microsoft Exchange (con Exchange 2013 para el almacenamiento de archivado para algunos o todos los usuarios), necesitará una implementación de Exchange 2013 existente.</span><span class="sxs-lookup"><span data-stu-id="b0b86-126">To use Microsoft Exchange integration (using Exchange 2013 for archiving storage for some or all users), you need an existing Exchange 2013 deployment.</span></span></p></li>
<li><p><span data-ttu-id="b0b86-127">Para usar bases de datos de archivado independientes (con bases de datos de SQL Server) para el almacenamiento de archivado para algunos o todos los usuarios, SQL Server en el servidor en el que se almacenarán los datos de archivado.</span><span class="sxs-lookup"><span data-stu-id="b0b86-127">To use separate Archiving databases (using SQL Server databases) for archiving storage for some or all users, SQL Server on the server that will store archiving data.</span></span></p></li>
</ul>
<div>

> [!NOTE]  
> <span data-ttu-id="b0b86-128">El archivado se ejecuta en los servidores front-end de un grupo de servidores Enterprise y servidores Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="b0b86-128">Archiving runs on Front End Servers of an Enterprise pool and Standard Edition servers.</span></span> <span data-ttu-id="b0b86-129">No hay ningún requisito adicional de hardware o de software aparte de los necesarios para instalar dichos servidores.</span><span class="sxs-lookup"><span data-stu-id="b0b86-129">It has no additional hardware or software requirements beyond what is required to install those servers.</span></span>


</div></td>
<td><p><span data-ttu-id="b0b86-130">Usuario de dominio que es miembro del grupo de administradores locales.</span><span class="sxs-lookup"><span data-stu-id="b0b86-130">Domain user who is a member of the local administrators group.</span></span></p></td>
<td><p><span data-ttu-id="b0b86-131"><a href="lync-server-2013-supported-hardware.md">Hardware compatible para Lync Server 2013</a> en la documentación sobre compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="b0b86-131"><a href="lync-server-2013-supported-hardware.md">Supported hardware for Lync Server 2013</a> in the Supportability documentation.</span></span></p>
<p><span data-ttu-id="b0b86-132"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Software de servidor y compatibilidad con la infraestructura en Lync Server 2013</a> en la documentación sobre compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="b0b86-132"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Server software and infrastructure support in Lync Server 2013</a> in the Supportability documentation.</span></span></p>
<p><span data-ttu-id="b0b86-133"><a href="lync-server-2013-technical-requirements-for-archiving.md">Requisitos técnicos para el archivado en Lync Server 2013</a> en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="b0b86-133"><a href="lync-server-2013-technical-requirements-for-archiving.md">Technical requirements for Archiving in Lync Server 2013</a> in the Planning documentation.</span></span></p>
<p><span data-ttu-id="b0b86-134"><a href="lync-server-2013-setting-up-systems-and-infrastructure-for-archiving.md">Configurar los sistemas y la infraestructura para el archivado en Lync Server 2013</a> en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="b0b86-134"><a href="lync-server-2013-setting-up-systems-and-infrastructure-for-archiving.md">Setting up systems and infrastructure for Archiving in Lync Server 2013</a> in the Deployment documentation.</span></span></p>
<p><span data-ttu-id="b0b86-135"><a href="lync-server-2013-exchange-and-sharepoint-integration-support.md">Compatibilidad con la integración de Exchange Server y SharePoint en Lync server 2013</a> en la documentación sobre compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="b0b86-135"><a href="lync-server-2013-exchange-and-sharepoint-integration-support.md">Exchange Server and SharePoint integration support in Lync Server 2013</a> in the Supportability documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0b86-136"><strong>Crear la topología interna adecuada para admitir el archivado (solo si no se usa la integración de Microsoft Exchange para todos los usuarios de la implementación)</strong></span><span class="sxs-lookup"><span data-stu-id="b0b86-136"><strong>Create the appropriate internal topology to support archiving (only if not using Microsoft Exchange integration for all users in your deployment)</strong></span></span></p></td>
<td><p><span data-ttu-id="b0b86-137">Ejecute el generador de topologías para agregar bases de datos de archivado de Lync Server 2013 (bases de datos de SQL Server) a la topología y, a continuación, publique la topología.</span><span class="sxs-lookup"><span data-stu-id="b0b86-137">Run Topology Builder to add Lync Server 2013 Archiving databases (SQL Server databases) to the topology, and then publish the topology.</span></span></p></td>
<td><p><span data-ttu-id="b0b86-138">Para definir una topología para incorporar bases de datos de archivado, una cuenta que sea miembro del grupo de usuarios locales.</span><span class="sxs-lookup"><span data-stu-id="b0b86-138">To define a topology to incorporate Archiving databases, an account that is a member of the local users group.</span></span></p>
<p><span data-ttu-id="b0b86-139">Para publicar la topología, una cuenta que sea miembro del grupo administradores de dominio y del grupo RTCUniversalServerAdmins, y que tenga permisos de control total (lectura/escritura/modificación) en el recurso compartido de archivos para su uso en el almacén de archivos de Lync Server 2013 (para que el generador de topologías pueda configurar las DACL necesarias).</span><span class="sxs-lookup"><span data-stu-id="b0b86-139">To publish the topology, an account that is a member of the domain admins group and RTCUniversalServerAdmins group, and that has full control permissions (read/write/modify) on the file share to be used for the Lync Server 2013 file store (so that Topology Builder can configure the required DACLs).</span></span></p></td>
<td><p><span data-ttu-id="b0b86-140"><a href="lync-server-2013-adding-archiving-databases-to-an-existing-lync-server-2013-deployment.md">Adición de bases de datos de archivado a una implementación existente de Lync Server 2013</a> en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="b0b86-140"><a href="lync-server-2013-adding-archiving-databases-to-an-existing-lync-server-2013-deployment.md">Adding Archiving databases to an existing Lync Server 2013 Deployment</a> in the Deployment documentation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b0b86-141"><strong>Configurar la autenticación de servidor a servidor (solo si se usa la integración de Microsoft Exchange)</strong></span><span class="sxs-lookup"><span data-stu-id="b0b86-141"><strong>Configure server-to-server authentication (only if using Microsoft Exchange integration)</strong></span></span></p></td>
<td><p><span data-ttu-id="b0b86-142">Configure los servidores para habilitar la autenticación entre Lync Server 2013 y Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="b0b86-142">Configure servers to enable authentication between Lync Server 2013 and Exchange 2013.</span></span> <span data-ttu-id="b0b86-143">Se recomienda ejecutar <strong>Test-CsExchangeStorageConnectivity testuser_sipUri: contenedor de carpetas</strong> para validar la Conectividad del almacenamiento de archivado de Exchange antes de habilitar el archivado.</span><span class="sxs-lookup"><span data-stu-id="b0b86-143">We recommend running <strong>Test-CsExchangeStorageConnectivity testuser_sipUri –Folder Dumpster</strong> to validate Exchange Archiving storage connectivity before enabling archiving.</span></span></p></td>
<td><p><span data-ttu-id="b0b86-144">Una cuenta con los permisos adecuados para administrar certificados en los servidores.</span><span class="sxs-lookup"><span data-stu-id="b0b86-144">An account with the appropriate permissions for managing certificates on the servers.</span></span></p></td>
<td><p><span data-ttu-id="b0b86-145"><a href="lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md">Administrar la autenticación de servidor a servidor (OAuth) y las aplicaciones de socio en Lync server 2013</a> en la documentación de implementación o en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="b0b86-145"><a href="lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md">Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013</a> in the Deployment documentation or the Operations documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b0b86-146"><strong>Configuración de directivas y configuraciones de archivado</strong></span><span class="sxs-lookup"><span data-stu-id="b0b86-146"><strong>Configure archiving policies and configurations</strong></span></span></p></td>
<td><p><span data-ttu-id="b0b86-147">Configurar el archivado, incluido si se va a usar la integración de Microsoft Exchange, la directiva global y las directivas de sitio y de usuario (cuando no se usa la integración de Microsoft Exchange para todo el almacenamiento de datos) y opciones de archivado específicas, como el modo crítico y la exportación y depuración de datos.</span><span class="sxs-lookup"><span data-stu-id="b0b86-147">Configure archiving, including whether to use Microsoft Exchange integration, the global policy and any site and user policies (when not using Microsoft Exchange integration for all data storage), and specific archiving options, such as critical mode and data export and purging.</span></span></p>
<p><span data-ttu-id="b0b86-148">Si usa la integración de Microsoft Exchange, configure las directivas de retención de Exchange In-Place según corresponda.</span><span class="sxs-lookup"><span data-stu-id="b0b86-148">If using Microsoft Exchange integration, configure Exchange In-Place Hold policies as appropriate.</span></span></p></td>
<td><p><span data-ttu-id="b0b86-149">Grupo RTCUniversalServerAdmins (solo Windows PowerShell) o asignar usuarios al rol rol csarchivingadministrator o CSAdministrator.</span><span class="sxs-lookup"><span data-stu-id="b0b86-149">RTCUniversalServerAdmins group (Windows PowerShell only) or assign users to the CSArchivingAdministrator or CSAdministrator role.</span></span></p></td>
<td><p><span data-ttu-id="b0b86-150"><a href="lync-server-2013-configuring-support-for-archiving.md">Configuring Support for archiving in Lync Server 2013</a> en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="b0b86-150"><a href="lync-server-2013-configuring-support-for-archiving.md">Configuring support for Archiving in Lync Server 2013</a> in the Deployment documentation.</span></span></p>
<p><span data-ttu-id="b0b86-151">Documentación del producto de Exchange (si se usa la integración de Microsoft Exchange).</span><span class="sxs-lookup"><span data-stu-id="b0b86-151">Exchange product documentation (if using Microsoft Exchange integration).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="deploying-lync-server-and-microsoft-exchange-in-different-forests"></a><span data-ttu-id="b0b86-152">Implementación de Lync Server y Microsoft Exchange en bosques diferentes</span><span class="sxs-lookup"><span data-stu-id="b0b86-152">Deploying Lync Server and Microsoft Exchange in Different Forests</span></span>

<span data-ttu-id="b0b86-153">Si Microsoft Exchange Server no se implementa en el mismo bosque que Lync Server, debe asegurarse de que los siguientes atributos de Active Directory de Exchange están sincronizados con el bosque en el que se ha implementado Lync Server:</span><span class="sxs-lookup"><span data-stu-id="b0b86-153">If Microsoft Exchange Server is not deployed in the same forest as Lync Server, you must make sure that the following Exchange Active Directory attributes are synchronized to the forest where Lync Server is deployed:</span></span>

1.  <span data-ttu-id="b0b86-154">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="b0b86-154">msExchUserHoldPolicies</span></span>

2.  <span data-ttu-id="b0b86-155">proxyAddresses</span><span class="sxs-lookup"><span data-stu-id="b0b86-155">proxyAddresses</span></span>

<span data-ttu-id="b0b86-156">Se trata de un atributo de varios valores.</span><span class="sxs-lookup"><span data-stu-id="b0b86-156">This is a multi-value attribute.</span></span> <span data-ttu-id="b0b86-157">Al sincronizar este atributo, debe combinar los valores, no reemplazarlos para asegurarse de que no se pierdan los valores existentes.</span><span class="sxs-lookup"><span data-stu-id="b0b86-157">When synchronizing this attribute, you need to merge the values, not replace them to ensure the existing values are not lost.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

