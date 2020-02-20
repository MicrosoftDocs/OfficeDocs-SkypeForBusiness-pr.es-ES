---
title: 'Lync Server 2013: configurar SQL Server para Lync Server'
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
ms.openlocfilehash: 77f6357d38731438555b2c9e3af7ec6a22e9df7c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145729"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-sql-server-for-lync-server-2013"></a><span data-ttu-id="1f0a2-102">Configuración de SQL Server para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1f0a2-102">Configure SQL Server for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1f0a2-103">_**Última modificación del tema:** 2013-08-12_</span><span class="sxs-lookup"><span data-stu-id="1f0a2-103">_**Topic Last Modified:** 2013-08-12_</span></span>

<span data-ttu-id="1f0a2-104">En los temas de esta sección se explica cómo implementar y configurar SQL Server para usarlo en una implementación empresarial de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1f0a2-104">The topics in this section discuss how to deploy and configure SQL Server to use in an Enterprise deployment of Lync Server.</span></span> <span data-ttu-id="1f0a2-105">Los servidores Standard Edition usan una versión de SQL Server Express de SQL Server combinada que tiene el tamaño adecuado para las cargas de trabajo de un servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="1f0a2-105">Standard Edition servers use a collocated SQL Server Express version of SQL Server that is right sized for the workloads of a Standard Edition server.</span></span>

<span data-ttu-id="1f0a2-106">El almacén de administración central de Lync Server 2013 retiene datos de usuario para todos los servidores Enterprise Edition de un grupo y está diseñado para ubicarse en un servidor back-end basado en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1f0a2-106">The Lync Server 2013 Central Management store holds user data for all Enterprise Edition servers within a pool, and is designed to be located on a SQL Server -based Back End Server.</span></span> <span data-ttu-id="1f0a2-107">Como repositorio centralizado, el almacén de administración central no se puede instalar en el mismo equipo que cualquier otro rol de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1f0a2-107">As a centralized repository, the Central Management store cannot be installed on the same computer as any other Lync Server 2013 role.</span></span> <span data-ttu-id="1f0a2-108">El almacén de administración central no puede residir en un servidor Enterprise Edition del grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="1f0a2-108">The Central Management store cannot reside on an Enterprise Edition server in the pool.</span></span> <span data-ttu-id="1f0a2-109">El almacén de administración central se crea automáticamente cuando se publica la topología por primera vez y se selecciona la creación de las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="1f0a2-109">The Central Management store is created automatically when you publish the topology for the first time and select to create the databases.</span></span> <span data-ttu-id="1f0a2-110">El equipo que designe como servidor back-end debe estar ejecutando el software de base de datos de SQL Server para que la instalación se realice correctamente.</span><span class="sxs-lookup"><span data-stu-id="1f0a2-110">The computer that you designate as the Back End Server must already be running SQL Server database software in order for the installation to succeed.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="1f0a2-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="1f0a2-111">In This Section</span></span>

  - [<span data-ttu-id="1f0a2-112">Ubicación de los archivos de registro y datos de SQL Server para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1f0a2-112">SQL Server data and log file placement for Lync Server 2013</span></span>](lync-server-2013-sql-server-data-and-log-file-placement.md)

  - [<span data-ttu-id="1f0a2-113">Configurar SQL Server en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1f0a2-113">Configure SQL Server in Lync Server 2013</span></span>](lync-server-2013-configure-sql-server.md)

  - [<span data-ttu-id="1f0a2-114">Permisos de implementación para SQL Server en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1f0a2-114">Deployment permissions for SQL Server in Lync Server 2013</span></span>](lync-server-2013-deployment-permissions-for-sql-server.md)

  - [<span data-ttu-id="1f0a2-115">Instalación de bases de datos mediante el shell de administración de Lync Server en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1f0a2-115">Database installation using Lync Server Management Shell in Lync Server 2013</span></span>](lync-server-2013-database-installation-using-lync-server-management-shell.md)

  - [<span data-ttu-id="1f0a2-116">Descripción de los requisitos de Firewall para SQL Server con Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1f0a2-116">Understanding firewall requirements for SQL Server with Lync Server 2013</span></span>](lync-server-2013-understanding-firewall-requirements-for-sql-server.md)

  - [<span data-ttu-id="1f0a2-117">Configurar la organización en clústeres de SQL Server para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1f0a2-117">Configure SQL Server clustering for Lync Server 2013</span></span>](lync-server-2013-configure-sql-server-clustering.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

