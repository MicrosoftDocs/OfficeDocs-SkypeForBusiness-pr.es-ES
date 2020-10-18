---
title: 'Lync Server 2013: configurar SQL Server para Lync Server'
description: 'Lync Server 2013: configurar SQL Server para Lync Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure SQL Server for Lync Server 2013
ms:assetid: 375e5cc4-e436-46dc-9b02-5063f35cdcc1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425848(v=OCS.15)
ms:contentKeyID: 48183869
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d9ac7d8f14c64f3b7935df3f48602a6df1791c7a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576726"
---
# <a name="configure-sql-server-for-lync-server-2013"></a><span data-ttu-id="bb8a7-103">Configuración de SQL Server para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bb8a7-103">Configure SQL Server for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bb8a7-104">_**Última modificación del tema:** 2013-08-12_</span><span class="sxs-lookup"><span data-stu-id="bb8a7-104">_**Topic Last Modified:** 2013-08-12_</span></span>

<span data-ttu-id="bb8a7-105">En los temas de esta sección se explica cómo implementar y configurar SQL Server para usarlo en una implementación empresarial de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bb8a7-105">The topics in this section discuss how to deploy and configure SQL Server to use in an Enterprise deployment of Lync Server.</span></span> <span data-ttu-id="bb8a7-106">Los servidores Standard Edition usan una versión de SQL Server Express de SQL Server combinada que tiene el tamaño adecuado para las cargas de trabajo de un servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="bb8a7-106">Standard Edition servers use a collocated SQL Server Express version of SQL Server that is right sized for the workloads of a Standard Edition server.</span></span>

<span data-ttu-id="bb8a7-107">El almacén de administración central de Lync Server 2013 retiene datos de usuario para todos los servidores Enterprise Edition de un grupo y está diseñado para ubicarse en un servidor back-end basado en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="bb8a7-107">The Lync Server 2013 Central Management store holds user data for all Enterprise Edition servers within a pool, and is designed to be located on a SQL Server -based Back End Server.</span></span> <span data-ttu-id="bb8a7-108">Como repositorio centralizado, el almacén de administración central no se puede instalar en el mismo equipo que cualquier otro rol de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bb8a7-108">As a centralized repository, the Central Management store cannot be installed on the same computer as any other Lync Server 2013 role.</span></span> <span data-ttu-id="bb8a7-109">El almacén de administración central no puede residir en un servidor Enterprise Edition del grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="bb8a7-109">The Central Management store cannot reside on an Enterprise Edition server in the pool.</span></span> <span data-ttu-id="bb8a7-110">El almacén de administración central se crea automáticamente cuando se publica la topología por primera vez y se selecciona la creación de las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="bb8a7-110">The Central Management store is created automatically when you publish the topology for the first time and select to create the databases.</span></span> <span data-ttu-id="bb8a7-111">El equipo que designe como servidor back-end debe estar ejecutando el software de base de datos de SQL Server para que la instalación se realice correctamente.</span><span class="sxs-lookup"><span data-stu-id="bb8a7-111">The computer that you designate as the Back End Server must already be running SQL Server database software in order for the installation to succeed.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="bb8a7-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="bb8a7-112">In This Section</span></span>

  - [<span data-ttu-id="bb8a7-113">Ubicación de los archivos de registro y datos de SQL Server para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bb8a7-113">SQL Server data and log file placement for Lync Server 2013</span></span>](lync-server-2013-sql-server-data-and-log-file-placement.md)

  - [<span data-ttu-id="bb8a7-114">Configurar SQL Server en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bb8a7-114">Configure SQL Server in Lync Server 2013</span></span>](lync-server-2013-configure-sql-server.md)

  - [<span data-ttu-id="bb8a7-115">Permisos de implementación para SQL Server en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bb8a7-115">Deployment permissions for SQL Server in Lync Server 2013</span></span>](lync-server-2013-deployment-permissions-for-sql-server.md)

  - [<span data-ttu-id="bb8a7-116">Instalación de bases de datos mediante el shell de administración de Lync Server en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bb8a7-116">Database installation using Lync Server Management Shell in Lync Server 2013</span></span>](lync-server-2013-database-installation-using-lync-server-management-shell.md)

  - [<span data-ttu-id="bb8a7-117">Descripción de los requisitos de Firewall para SQL Server con Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bb8a7-117">Understanding firewall requirements for SQL Server with Lync Server 2013</span></span>](lync-server-2013-understanding-firewall-requirements-for-sql-server.md)

  - [<span data-ttu-id="bb8a7-118">Configurar la organización en clústeres de SQL Server para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bb8a7-118">Configure SQL Server clustering for Lync Server 2013</span></span>](lync-server-2013-configure-sql-server-clustering.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

