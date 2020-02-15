---
title: 'Lync Server 2013: refuerzo y protección de bases de datos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardening and protecting the databases of Lync Server 2013
ms:assetid: 6953e721-3511-4235-b848-51bab093dc89
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518330(v=OCS.15)
ms:contentKeyID: 62625490
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6e1ef045253f6733ea3356baa6254a6c90926762
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006216"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hardening-and-protecting-the-databases-of-lync-server-2013"></a><span data-ttu-id="cf371-102">Refuerzo y protección de las bases de datos de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cf371-102">Hardening and protecting the databases of Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cf371-103">_**Última modificación del tema:** 2013-12-05_</span><span class="sxs-lookup"><span data-stu-id="cf371-103">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="cf371-104">Microsoft Lync Server 2013 también depende de las bases de datos de SQL Server para almacenar información de usuario, estado de conferencia, datos de archivado y registros de detalles de llamadas (CDR).</span><span class="sxs-lookup"><span data-stu-id="cf371-104">Microsoft Lync Server 2013 also depends on SQL Server databases for storing user information, conference state, archiving data, and Call Detail Records (CDRs).</span></span> <span data-ttu-id="cf371-105">Puede maximizar la disponibilidad de los datos de Lync Server 2013 en las bases de datos back-end de Lync Server, mediante la partición de los datos de la aplicación de forma que se mejore la tolerancia a errores y se simplifique la solución de problemas.</span><span class="sxs-lookup"><span data-stu-id="cf371-105">You can maximize the availability of Lync Server 2013 data on Lync Server back-end databases, by partitioning the application data in a way that improves fault tolerance and simplifies troubleshooting.</span></span> <span data-ttu-id="cf371-106">Para lograr estos objetivos, divida en particiones los datos de la aplicación mediante las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="cf371-106">To achieve these goals, partition the application data by:</span></span>

  - <span data-ttu-id="cf371-107">**Mediante los procedimientos recomendados**   para la partición del servidor, separe los archivos del sistema operativo, la aplicación y el programa de los archivos de datos.</span><span class="sxs-lookup"><span data-stu-id="cf371-107">**Using server partitioning best practices**   Separate your operating system, application, and program files from your data files.</span></span>

  - <span data-ttu-id="cf371-108">**Almacenar archivos de registro de transacciones y archivos**   de base de datos almacene estos archivos por separado para aumentar la tolerancia a errores y optimizar la recuperación, y almacénelos en un disco o volumen cifrado.</span><span class="sxs-lookup"><span data-stu-id="cf371-108">**Storing transaction log files and database files**   Store these files separately to increase fault tolerance and optimize recovery, and store them on an encrypted disk or volume.</span></span>

  - <span data-ttu-id="cf371-109">**Uso**   del clúster de servidores agrupa los servidores back-end para optimizar la disponibilidad del sistema de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cf371-109">**Using server clustering**   Cluster the back-end servers to optimize Lync Server 2013 system availability.</span></span>

  - <span data-ttu-id="cf371-110">**Asegurarse de que todas las copias de seguridad de los datos se cifran y que se controlan**   correctamente los medios de copia de seguridad perdidos, descartados o extraviados pueden suponer una amenaza importante para la seguridad de datos para las implementaciones de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cf371-110">**Ensure that all data backups are encrypted and properly handled**   Lost, discarded, or misplaced backup media can pose a significant threat to data security for Lync Server 2013 deployments</span></span>

<span data-ttu-id="cf371-111">En cualquier servidor de Lync Server 2013 excepto en el servidor Standard Edition, la instancia de SQL Server Express (instancia RTCLOCAL) no es accesible de forma remota y no se crean excepciones del firewall local, excepto para SQL Server Express en un servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="cf371-111">On any Lync Server 2013 server except Standard Edition server, the SQL Server Express instance (RTCLOCAL instance) is not remotely accessible, and no local firewall exceptions are created, except for SQL Server Express on a Standard Edition server.</span></span> <span data-ttu-id="cf371-112">En un servidor Standard Edition, tanto la base de datos back-end como el Almacén de administración central (CMS) están configurados para poder acceder a ellos de forma remota.</span><span class="sxs-lookup"><span data-stu-id="cf371-112">On a Standard Edition server, both the back-end database and the Central Management store (CMS) are set up to be remotely accessible.</span></span> <span data-ttu-id="cf371-113">Para proteger las bases de datos de SQL Server, puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="cf371-113">To harden SQL Server databases, you can do the following:</span></span>

  - <span data-ttu-id="cf371-p103">Personalizar el firewall de SQL Server Express en los servidores Standard Edition, limitando el ámbito de servidores que pueden acceder de forma remota a la base de datos. De manera predeterminada, cualquier dirección IP puede acceder a la base de datos de forma remota.</span><span class="sxs-lookup"><span data-stu-id="cf371-p103">Customize the SQL Server Express firewall on Standard Edition servers, limiting the scope of servers that can remotely access the database. By default, any IP address can remotely access the database.</span></span>

  - <span data-ttu-id="cf371-116">Usar el Administrador de configuración de SQL Server para especificar los protocolos, direcciones IP y puertos para el acceso remoto a SQL Server:</span><span class="sxs-lookup"><span data-stu-id="cf371-116">Use SQL Server Configuration Manager to specify the protocols, IP addresses, and ports for SQL Server remote access:</span></span>
    
      - <span data-ttu-id="cf371-117">Lync Server 2013 usa el protocolo TCP/IP.</span><span class="sxs-lookup"><span data-stu-id="cf371-117">Lync Server 2013 uses the TCP/IP protocol.</span></span> <span data-ttu-id="cf371-118">Admite la versión 4 de IP (IPv4), pero no admite la versión 6 (IPv6).</span><span class="sxs-lookup"><span data-stu-id="cf371-118">It supports IP version 4 (IPv4), but not IP version 6 (IPv6).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="cf371-119">Lync Server 2013 puede funcionar en una red con una pila IP dual habilitada.</span><span class="sxs-lookup"><span data-stu-id="cf371-119">Lync Server 2013 can function in a network with dual IP stack enabled.</span></span>

        
        </div>
    
      - <span data-ttu-id="cf371-120">Lync Server 2013 admite varias direcciones IP (tarjetas de dirección de red multitarjeta).</span><span class="sxs-lookup"><span data-stu-id="cf371-120">Lync Server 2013 supports multiple IP address (multi-homed network address cards).</span></span> <span data-ttu-id="cf371-121">Puede especificar que SQL Server escuche solo direcciones IP específicas (direcciones individuales o por subred) y use solo protocolos específicos.</span><span class="sxs-lookup"><span data-stu-id="cf371-121">You can specify that SQL Server listen only to specific IP addresses (individual address or by subnet) and only use specific protocols.</span></span>
    
      - <span data-ttu-id="cf371-122">Lync Server 2013 admite puertos de SQL Server estáticos y dinámicos.</span><span class="sxs-lookup"><span data-stu-id="cf371-122">Lync Server 2013 supports static and dynamic SQL Server ports.</span></span>

  - <span data-ttu-id="cf371-123">Ejecute SQL Server en un puerto estático (que no sea predeterminado) y no ejecute SQL Server Browser (para que no pueda informar del puerto de escucha al cliente).</span><span class="sxs-lookup"><span data-stu-id="cf371-123">Run SQL Server on a static (non-default) port, and do not run SQL Server Browser (so it cannot report the listening port to the client).</span></span> <span data-ttu-id="cf371-124">Esto requiere una configuración personalizada en cada cliente de SQL Server, incluidos los servidores front-end, el servidor de supervisión, el servidor de archivado y las consolas administrativas (ejecutando el shell de administración de Lync Server, el panel de control de Lync Server o el generador de topologías) y todos los demás servidores que ejecutan las bases de datos de Lync Server).</span><span class="sxs-lookup"><span data-stu-id="cf371-124">This requires a custom configuration on each SQL Server client, including Front End Servers, Monitoring Server, Archiving Server, and administrative consoles (running Lync Server Management Shell, Lync Server Control Panel, or Topology Builder), and all other servers running Lync Server databases).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cf371-125">El acceso a las bases de datos debe limitarse a los administradores de bases de datos de confianza.</span><span class="sxs-lookup"><span data-stu-id="cf371-125">Access to databases must be limited to trusted database administrators.</span></span> <span data-ttu-id="cf371-126">Un administrador de bases de datos malintencionado puede insertar o modificar datos en las bases de datos para adquirir privilegios en los servidores de Lync Server 2013 u obtener información confidencial de los servicios, incluso si el administrador de la base de datos no se le ha concedido acceso directo o control de los servidores de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cf371-126">A malicious database administrator could insert or modify data into the databases to acquire privileges over the Lync Server 2013 servers or obtain sensitive information from the services, even if the database administrator has not been granted direct access or control of the Lync Server 2013 servers.</span></span>



</div>

<span data-ttu-id="cf371-127">Para obtener más información sobre las configuraciones personalizadas y consolidar las bases de datos de SQL Server, vea el artículo del blog NextHop, "Using Lync Server 2010 con una configuración de red [http://go.microsoft.com/fwlink/p/?LinkId=214008](http://go.microsoft.com/fwlink/p/?linkid=214008)de SQL Server personalizada", en.</span><span class="sxs-lookup"><span data-stu-id="cf371-127">For details about custom configurations and hardening SQL Server databases, see the NextHop blog article, "Using Lync Server 2010 with a Custom SQL Server Network Configuration," at [http://go.microsoft.com/fwlink/p/?LinkId=214008](http://go.microsoft.com/fwlink/p/?linkid=214008).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cf371-128">También puede reforzar los sistemas operativos y los servidores de aplicaciones, y puede usar la Directiva de grupo para implementar bloqueos de seguridad en su implementación de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cf371-128">You can also harden operating systems and applications servers, and you can use Group Policy to implement security lockdowns in your Lync Server deployment.</span></span> <span data-ttu-id="cf371-129">Para obtener más información, consulte <A href="lync-server-2013-hardening-and-protecting-servers-and-applications.md">refuerzo y protección de servidores y aplicaciones para Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="cf371-129">For details, see <A href="lync-server-2013-hardening-and-protecting-servers-and-applications.md">Hardening and protecting servers and applications for Lync Server 2013</A>.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

