---
title: 'Lync Server 2013: lista de comprobación para la implementación del servidor de chat persistente'
description: 'Lync Server 2013: lista de comprobación para la implementación del servidor de chat persistente.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for Persistent Chat Server
ms:assetid: b1108f8f-88a2-4660-8086-d25ba76f7239
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412851(v=OCS.15)
ms:contentKeyID: 48185155
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 28d96da5e2961634e6a81450796e5d1ae3426819
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568296"
---
# <a name="deployment-checklist-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="4a711-103">Lista de comprobación para la implementación del servidor de chat persistente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4a711-103">Deployment checklist for Persistent Chat Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4a711-104">_**Última modificación del tema:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="4a711-104">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="4a711-105">La implementación de Lync Server 2013, el servidor de chat persistente requiere que lo implemente en la secuencia correcta y que complete todos los pasos de implementación necesarios.</span><span class="sxs-lookup"><span data-stu-id="4a711-105">Deployment of Lync Server 2013, Persistent Chat Server requires that you deploy it in the correct sequence and that you complete all required deployment steps.</span></span>

<div>

## <a name="deployment-sequence"></a><span data-ttu-id="4a711-106">Secuencia de implementación</span><span class="sxs-lookup"><span data-stu-id="4a711-106">Deployment Sequence</span></span>

<span data-ttu-id="4a711-107">Puede implementar el servidor de chat persistente después de implementar la topología inicial, incluido al menos un servidor de Lync Server 2013, un grupo de servidores front-end o un servidor de Lync Server 2013, Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="4a711-107">You can deploy Persistent Chat Server after you deploy your initial topology, including at least one Lync Server 2013, Front End pool or one Lync Server 2013, Standard Edition server.</span></span> <span data-ttu-id="4a711-108">En este tema se describe cómo implementar el servidor de chat persistente agregándolo a una implementación existente.</span><span class="sxs-lookup"><span data-stu-id="4a711-108">This topic describes how to deploy Persistent Chat Server by adding it to an existing deployment.</span></span>

</div>

<div>

## <a name="deployment-process"></a><span data-ttu-id="4a711-109">Proceso de implementación</span><span class="sxs-lookup"><span data-stu-id="4a711-109">Deployment Process</span></span>

<span data-ttu-id="4a711-110">En la siguiente tabla se enumeran los pasos básicos para implementar el servidor de chat persistente y se proporcionan vínculos para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="4a711-110">The following table lists the basic steps to deploy Persistent Chat Server and provides links for more details.</span></span>

### <a name="persistent-chat-server-deployment-process"></a><span data-ttu-id="4a711-111">Proceso de implementación del servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="4a711-111">Persistent Chat Server Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4a711-112">Task</span><span class="sxs-lookup"><span data-stu-id="4a711-112">Task</span></span></th>
<th><span data-ttu-id="4a711-113">Pasos</span><span class="sxs-lookup"><span data-stu-id="4a711-113">Steps</span></span></th>
<th><span data-ttu-id="4a711-114">Roles y pertenencias a grupos necesarios</span><span class="sxs-lookup"><span data-stu-id="4a711-114">Required roles and group memberships</span></span></th>
<th><span data-ttu-id="4a711-115">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="4a711-115">Related topics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4a711-116"><strong>Instalar los requisitos previos de hardware y software</strong></span><span class="sxs-lookup"><span data-stu-id="4a711-116"><strong>Install prerequisite hardware and software</strong></span></span></p></td>
<td><p><span data-ttu-id="4a711-117">En un hardware que cumpla los requisitos del sistema, instale los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="4a711-117">On hardware that meets system requirements, install the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="4a711-118">En los servidores front-end del servidor de chat persistente:</span><span class="sxs-lookup"><span data-stu-id="4a711-118">On the Persistent Chat Server Front End Servers:</span></span></p></li>
</ul>
<ul>
<li><p><span data-ttu-id="4a711-119">Un sistema operativo que cumpla los requisitos del sistema</span><span class="sxs-lookup"><span data-stu-id="4a711-119">An operating system that meets system requirements</span></span></p></li>
<li><p><span data-ttu-id="4a711-120">Requisitos previos de software para equipos que ejecutan Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4a711-120">Software prerequisites for computers running Lync Server 2013</span></span></p></li>
<li><p><span data-ttu-id="4a711-121">SQL Server en el servidor donde se hospedará la base de datos del servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="4a711-121">SQL Server on the server that will host Persistent Chat Server database</span></span></p></li>
</ul>
<p><span data-ttu-id="4a711-122">Si se requiere el cumplimiento del servidor de chat persistente:</span><span class="sxs-lookup"><span data-stu-id="4a711-122">If Persistent Chat Server compliance is required:</span></span></p>
<ul>
<li><p><span data-ttu-id="4a711-123">SQL Server en el servidor donde se hospedará la base de datos de cumplimiento del servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="4a711-123">SQL Server on the server that will host Persistent Chat Server compliance database</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="4a711-124">Cualquier usuario que pertenezca al grupo de administradores locales.</span><span class="sxs-lookup"><span data-stu-id="4a711-124">Any user who is a member of the local Administrators group.</span></span></p></td>
<td><p><span data-ttu-id="4a711-125"><a href="lync-server-2013-supported-hardware.md">Hardware compatible para Lync Server 2013</a> en la documentación sobre compatibilidad</span><span class="sxs-lookup"><span data-stu-id="4a711-125"><a href="lync-server-2013-supported-hardware.md">Supported hardware for Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="4a711-126"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Software de servidor y compatibilidad con la infraestructura en Lync Server 2013</a> en la documentación sobre compatibilidad</span><span class="sxs-lookup"><span data-stu-id="4a711-126"><a href="lync-server-2013-server-software-and-infrastructure-support.md">Server software and infrastructure support in Lync Server 2013</a> in the Supportability documentation</span></span></p>
<p><span data-ttu-id="4a711-127"><a href="lync-server-2013-determining-your-system-requirements.md">Determinación de los requisitos del sistema para Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="4a711-127"><a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="4a711-128"><a href="lync-server-2013-technical-requirements-for-persistent-chat-server.md">Requisitos técnicos para el servidor de chat persistente en Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="4a711-128"><a href="lync-server-2013-technical-requirements-for-persistent-chat-server.md">Technical requirements for Persistent Chat Server in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a711-129"><strong>Crear la topología interna adecuada para admitir el servidor de chat persistente (y, opcionalmente, el cumplimiento de chat persistente)</strong></span><span class="sxs-lookup"><span data-stu-id="4a711-129"><strong>Create the appropriate internal topology to support Persistent Chat Server (and optionally, Persistent Chat compliance)</strong></span></span></p></td>
<td><p><span data-ttu-id="4a711-130">Ejecute el generador de topologías para agregar un grupo de servidores de chat persistente a la topología:</span><span class="sxs-lookup"><span data-stu-id="4a711-130">Run Topology Builder to add a Persistent Chat Server pool to your topology:</span></span></p>
<ul>
<li><p><span data-ttu-id="4a711-131">Agregar componentes del servidor de chat persistente a la topología</span><span class="sxs-lookup"><span data-stu-id="4a711-131">Add Persistent Chat Server components to the topology</span></span></p></li>
<li><p><span data-ttu-id="4a711-132">Crear una base de datos de SQL Server para el almacén del servidor de chat persistente (y una copia de seguridad de SQL Server para la recuperación ante desastres)</span><span class="sxs-lookup"><span data-stu-id="4a711-132">Create a SQL Server database for the Persistent Chat Server store (and a backup SQL Server for disaster recovery)</span></span></p></li>
<li><p><span data-ttu-id="4a711-133">Definir un nuevo almacén de archivos de Lync o usar un almacén de archivos de Lync existente para los archivos del servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="4a711-133">Define a new Lync File Store or use an existing Lync File Store for Persistent Chat Server files</span></span></p></li>
<li><p><span data-ttu-id="4a711-134">Asociar el grupo de servidores de Lync Server 2013 que puede enrutar solicitudes a este grupo de servidores de chat persistente</span><span class="sxs-lookup"><span data-stu-id="4a711-134">Associate the Lync Server 2013 pool that can route requests to this Persistent Chat Server pool</span></span></p></li>
</ul>
<p><span data-ttu-id="4a711-135">Si se requiere el cumplimiento del chat persistente:</span><span class="sxs-lookup"><span data-stu-id="4a711-135">If Persistent Chat compliance is required:</span></span></p>
<ul>
<li><p><span data-ttu-id="4a711-136">Agregar almacén de cumplimiento de chat persistente</span><span class="sxs-lookup"><span data-stu-id="4a711-136">Add Persistent Chat Compliance Store</span></span></p></li>
<li><p><span data-ttu-id="4a711-137">Haga clic en la casilla definición del grupo de servidores de chat persistente para habilitar el cumplimiento</span><span class="sxs-lookup"><span data-stu-id="4a711-137">Click the Persistent Chat Server pool definition check box for enabling compliance</span></span></p></li>
<li><p><span data-ttu-id="4a711-138">Publicar la topología</span><span class="sxs-lookup"><span data-stu-id="4a711-138">Publish the topology</span></span></p></li>
</ul>
<p><span data-ttu-id="4a711-139">Si instala el servidor de chat persistente en Standard Edition, el nombre de dominio completo (FQDN) del grupo de servidores de chat persistente debe coincidir con el servidor Standard Edition y las bases de datos de SQL Server se combinan en la instancia de SQL Server Express en el servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="4a711-139">If you install Persistent Chat Server on Standard Edition, the fully qualified domain name (FQDN) of the Persistent Chat Server pool must match the Standard Edition server, and the SQL Server databases are collocated on the SQL Server Express instance on the Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="4a711-140">Para definir una topología, una cuenta que pertenezca al grupo de usuarios locales.</span><span class="sxs-lookup"><span data-stu-id="4a711-140">To define a topology, an account that is a member of the local Users group.</span></span></p>
<p><span data-ttu-id="4a711-141">Para publicar la topología, una cuenta que sea miembro del grupo administradores de dominio y del grupo RTCUniversalServerAdmins, y el usuario también debe tener permisos de control total (lectura/escritura/modificación) en el almacén de archivos de Lync para los archivos del servidor de chat persistente (para que el generador de topologías pueda configurar las DACL necesarias).</span><span class="sxs-lookup"><span data-stu-id="4a711-141">To publish the topology, an account that is a member of the Domain Admins group and RTCUniversalServerAdmins group, and the user should also have full control permissions (read/write/modify) on the Lync File Store for Persistent Chat Server files (so that Topology Builder can configure the required DACLs).</span></span></p></td>
<td><p><span data-ttu-id="4a711-142"><a href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adición de un servidor de chat persistente a la implementación en Lync Server 2013</a> en la documentación de implementación</span><span class="sxs-lookup"><span data-stu-id="4a711-142"><a href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a711-143"><strong>Implementar el servidor de chat persistente</strong></span><span class="sxs-lookup"><span data-stu-id="4a711-143"><strong>Deploy Persistent Chat Server</strong></span></span></p></td>
<td><p><span data-ttu-id="4a711-144">Ejecute el programa de instalación de Lync Server en todos los equipos que ejecuten el servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="4a711-144">Run the Lync Server setup on all the computers running Persistent Chat Server.</span></span> <span data-ttu-id="4a711-145">La instalación del servidor de chat persistente está integrada en el Asistente para la implementación de Lync Server 2013 que proporciona las instrucciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="4a711-145">The Persistent Chat Server setup is integrated into the Lync Server 2013 Deployment wizard that provides the following instructions:</span></span></p>
<ul>
<li><p><span data-ttu-id="4a711-146">Implemente el almacén de administración local</span><span class="sxs-lookup"><span data-stu-id="4a711-146">Deploy local management store</span></span></p></li>
<li><p><span data-ttu-id="4a711-147">Instalar los servicios del servidor de chat persistente</span><span class="sxs-lookup"><span data-stu-id="4a711-147">Install Persistent Chat Server services</span></span></p></li>
<li><p><span data-ttu-id="4a711-148">Solicite y asigne certificados</span><span class="sxs-lookup"><span data-stu-id="4a711-148">Request and assign certificates</span></span></p></li>
<li><p><span data-ttu-id="4a711-149">Ejecute e inicie los servicios</span><span class="sxs-lookup"><span data-stu-id="4a711-149">Run and start the services</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="4a711-150">Cualquier usuario que pertenezca al grupo de administradores locales.</span><span class="sxs-lookup"><span data-stu-id="4a711-150">Any user who is a member of the local Administrators group.</span></span></p></td>
<td><p><span data-ttu-id="4a711-151"><a href="lync-server-2013-deploying-persistent-chat-server.md">Deploying persistent chat Server in Lync Server 2013</a> en la documentación de implementación</span><span class="sxs-lookup"><span data-stu-id="4a711-151"><a href="lync-server-2013-deploying-persistent-chat-server.md">Deploying Persistent Chat Server in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a711-152"><strong>Crear un administrador de chat persistente</strong></span><span class="sxs-lookup"><span data-stu-id="4a711-152"><strong>Create a Persistent Chat administrator</strong></span></span></p></td>
<td><p><span data-ttu-id="4a711-153">Agregue usuarios al grupo de seguridad CsPersistentChatAdministrator.</span><span class="sxs-lookup"><span data-stu-id="4a711-153">Add users to the CsPersistentChatAdministrator security group.</span></span></p></td>
<td><p><span data-ttu-id="4a711-154">Cualquier usuario que pertenezca al grupo de administradores de dominio.</span><span class="sxs-lookup"><span data-stu-id="4a711-154">Any user who is a member of domain administrators.</span></span></p></td>
<td><p><span data-ttu-id="4a711-155"><a href="lync-server-2013-adding-a-persistent-chat-administrator.md">Adición de un administrador de chat persistente en Lync Server 2013</a> en la documentación de implementación</span><span class="sxs-lookup"><span data-stu-id="4a711-155"><a href="lync-server-2013-adding-a-persistent-chat-administrator.md">Adding a Persistent Chat administrator in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a711-156"><strong>Configuración del servidor de chat persistente</strong></span><span class="sxs-lookup"><span data-stu-id="4a711-156"><strong>Configure Persistent Chat Server</strong></span></span></p></td>
<td><p><span data-ttu-id="4a711-157">Configure usuarios:</span><span class="sxs-lookup"><span data-stu-id="4a711-157">Configure users:</span></span></p>
<ul>
<li><p><span data-ttu-id="4a711-158">El usuario tiene que estar habilitado por la Directiva para tener acceso al servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="4a711-158">User has to be enabled by policy to access Persistent Chat Server.</span></span> <span data-ttu-id="4a711-159">De manera predeterminada, la directiva está desactivada para todos los usuarios, y se puede definir en el ámbito global, de sitio, de grupo o de usuario.</span><span class="sxs-lookup"><span data-stu-id="4a711-159">By default, the policy is turned off for all users and can be defined at global/site/pool/user scopes.</span></span></p></li>
<li><p><span data-ttu-id="4a711-160">Defina la configuración</span><span class="sxs-lookup"><span data-stu-id="4a711-160">Configure settings</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="4a711-p104">El usuario debe pertenecer al grupo CsPersistentChatAdministrator. Para cambiar la directiva, el usuario ser miembro de CsUserAdministrator, como mínimo.</span><span class="sxs-lookup"><span data-stu-id="4a711-p104">User must be a member of CsPersistentChatAdministrator. To change policy, user must be in CsUserAdministrator, at a minimum.</span></span></p></td>
<td><p><span data-ttu-id="4a711-163"><a href="lync-server-2013-configuring-persistent-chat-server.md">Configuración del servidor de chat persistente en Lync Server 2013</a> en la documentación de implementación</span><span class="sxs-lookup"><span data-stu-id="4a711-163"><a href="lync-server-2013-configuring-persistent-chat-server.md">Configuring Persistent Chat Server in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <span data-ttu-id="4a711-164">Puede implementar uno o más grupos de servidores de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="4a711-164">You can deploy one or more Persistent Chat Server pools.</span></span> <span data-ttu-id="4a711-165">Admitimos varios grupos de servidores de chat persistente por motivos legales por los que se requiere que los datos generados en una región determinada permanezcan en dicha región.</span><span class="sxs-lookup"><span data-stu-id="4a711-165">We support multiple Persistent Chat Server pools for regulatory reasons whereby data generated in a given region is required to stay in that region.</span></span> <span data-ttu-id="4a711-166">Por ejemplo, si implementa un grupo de servidores de chat persistente en Chicago y otro en Zurich para cumplir con las normativas de datos en Suiza, los usuarios pueden conectarse a salas en los grupos de servidores de chat persistente, siempre que tengan acceso.</span><span class="sxs-lookup"><span data-stu-id="4a711-166">For example, if you deploy a Persistent Chat Server pool in Chicago, and another in Zurich to comply with regulations for data in Switzerland, users can connect to rooms in both the Persistent Chat Server pools, provided they have access.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

