---
title: 'Lync Server 2013: Reforzar y proteger las bases de datos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Hardening and protecting the databases of Lync Server 2013
ms:assetid: 6953e721-3511-4235-b848-51bab093dc89
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518330(v=OCS.15)
ms:contentKeyID: 62625490
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 265ca1058b4f3b41c5f0dbc4c5b2cdcd631fa911
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835093"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hardening-and-protecting-the-databases-of-lync-server-2013"></a><span data-ttu-id="cee0b-102">Reforzar y proteger las bases de datos de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cee0b-102">Hardening and protecting the databases of Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cee0b-103">_**Última modificación del tema:** 2013-12-05_</span><span class="sxs-lookup"><span data-stu-id="cee0b-103">_**Topic Last Modified:** 2013-12-05_</span></span>

<span data-ttu-id="cee0b-104">Microsoft Lync Server 2013 también depende de las bases de datos de SQL Server para almacenar información de usuario, estado de la Conferencia, datos de archivado y registros de detalles de llamadas (CDRs).</span><span class="sxs-lookup"><span data-stu-id="cee0b-104">Microsoft Lync Server 2013 also depends on SQL Server databases for storing user information, conference state, archiving data, and Call Detail Records (CDRs).</span></span> <span data-ttu-id="cee0b-105">Puede maximizar la disponibilidad de datos de Lync Server 2013 en bases de datos back-end de Lync Server, al particionar los datos de la aplicación de forma que mejore la tolerancia a errores y simplifique la solución de problemas.</span><span class="sxs-lookup"><span data-stu-id="cee0b-105">You can maximize the availability of Lync Server 2013 data on Lync Server back-end databases, by partitioning the application data in a way that improves fault tolerance and simplifies troubleshooting.</span></span> <span data-ttu-id="cee0b-106">Para lograr estos objetivos, divida los datos de la aplicación por:</span><span class="sxs-lookup"><span data-stu-id="cee0b-106">To achieve these goals, partition the application data by:</span></span>

  - <span data-ttu-id="cee0b-107">**Uso**   de las prácticas recomendadas para la partición de servidores separe los archivos de sistema operativo, aplicaciones y programas de los archivos de datos.</span><span class="sxs-lookup"><span data-stu-id="cee0b-107">**Using server partitioning best practices**   Separate your operating system, application, and program files from your data files.</span></span>

  - <span data-ttu-id="cee0b-108">**Almacenar archivos de registro de transacciones y archivos**   de base de datos almacene estos archivos por separado para aumentar la tolerancia a errores y optimizar la recuperación, y almacenarlos en un disco o volumen cifrado.</span><span class="sxs-lookup"><span data-stu-id="cee0b-108">**Storing transaction log files and database files**   Store these files separately to increase fault tolerance and optimize recovery, and store them on an encrypted disk or volume.</span></span>

  - <span data-ttu-id="cee0b-109">**Usar clústeres de servidor**   agrupar los servidores back-end para optimizar la disponibilidad del sistema de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cee0b-109">**Using server clustering**   Cluster the back-end servers to optimize Lync Server 2013 system availability.</span></span>

  - <span data-ttu-id="cee0b-110">**Asegurarse de que todas las copias de seguridad de los datos se cifren y se administren**   correctamente los medios de copia de seguridad perdidos, descartados o extraviados pueden suponer una amenaza importante para la seguridad de los datos para implementaciones de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cee0b-110">**Ensure that all data backups are encrypted and properly handled**   Lost, discarded, or misplaced backup media can pose a significant threat to data security for Lync Server 2013 deployments</span></span>

<span data-ttu-id="cee0b-111">En cualquier servidor de Lync Server 2013 excepto el servidor Standard Edition, no se puede acceder a la instancia de SQL Server Express (instancia RTCLOCAL) de forma remota y no se crean excepciones de Firewall local, excepto SQL Server Express en un servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="cee0b-111">On any Lync Server 2013 server except Standard Edition server, the SQL Server Express instance (RTCLOCAL instance) is not remotely accessible, and no local firewall exceptions are created, except for SQL Server Express on a Standard Edition server.</span></span> <span data-ttu-id="cee0b-112">En un servidor Standard Edition, tanto la base de datos back-end como el almacén de administración central (CMS) están configurados para que sean accesibles de forma remota.</span><span class="sxs-lookup"><span data-stu-id="cee0b-112">On a Standard Edition server, both the back-end database and the Central Management store (CMS) are set up to be remotely accessible.</span></span> <span data-ttu-id="cee0b-113">Para reforzar las bases de datos de SQL Server, puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="cee0b-113">To harden SQL Server databases, you can do the following:</span></span>

  - <span data-ttu-id="cee0b-114">Personalizar el Firewall de SQL Server Express en servidores Standard Edition, lo que limita el ámbito de los servidores que pueden tener acceso a la base de datos de forma remota.</span><span class="sxs-lookup"><span data-stu-id="cee0b-114">Customize the SQL Server Express firewall on Standard Edition servers, limiting the scope of servers that can remotely access the database.</span></span> <span data-ttu-id="cee0b-115">De forma predeterminada, cualquier dirección IP puede tener acceso remoto a la base de datos.</span><span class="sxs-lookup"><span data-stu-id="cee0b-115">By default, any IP address can remotely access the database.</span></span>

  - <span data-ttu-id="cee0b-116">Use el administrador de configuración de SQL Server para especificar los protocolos, las direcciones IP y los puertos para el acceso remoto de SQL Server:</span><span class="sxs-lookup"><span data-stu-id="cee0b-116">Use SQL Server Configuration Manager to specify the protocols, IP addresses, and ports for SQL Server remote access:</span></span>
    
      - <span data-ttu-id="cee0b-117">Lync Server 2013 usa el protocolo TCP/IP.</span><span class="sxs-lookup"><span data-stu-id="cee0b-117">Lync Server 2013 uses the TCP/IP protocol.</span></span> <span data-ttu-id="cee0b-118">Es compatible con IP versión 4 (IPv4), pero no con IP versión 6 (IPv6).</span><span class="sxs-lookup"><span data-stu-id="cee0b-118">It supports IP version 4 (IPv4), but not IP version 6 (IPv6).</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="cee0b-119">Lync Server 2013 puede funcionar en una red con dos pilas IP habilitadas.</span><span class="sxs-lookup"><span data-stu-id="cee0b-119">Lync Server 2013 can function in a network with dual IP stack enabled.</span></span>

        
        </div>
    
      - <span data-ttu-id="cee0b-120">Lync Server 2013 admite varias direcciones IP (tarjetas de dirección de red multitarjeta).</span><span class="sxs-lookup"><span data-stu-id="cee0b-120">Lync Server 2013 supports multiple IP address (multi-homed network address cards).</span></span> <span data-ttu-id="cee0b-121">Puede especificar que SQL Server solo escuche direcciones IP específicas (dirección individual o por subred) y use únicamente protocolos específicos.</span><span class="sxs-lookup"><span data-stu-id="cee0b-121">You can specify that SQL Server listen only to specific IP addresses (individual address or by subnet) and only use specific protocols.</span></span>
    
      - <span data-ttu-id="cee0b-122">Lync Server 2013 admite puertos de SQL Server estáticos y dinámicos.</span><span class="sxs-lookup"><span data-stu-id="cee0b-122">Lync Server 2013 supports static and dynamic SQL Server ports.</span></span>

  - <span data-ttu-id="cee0b-123">Ejecute SQL Server en un puerto estático (no predeterminado) y no ejecute SQL Server Browser (por lo tanto, no puede informar del puerto de escucha al cliente).</span><span class="sxs-lookup"><span data-stu-id="cee0b-123">Run SQL Server on a static (non-default) port, and do not run SQL Server Browser (so it cannot report the listening port to the client).</span></span> <span data-ttu-id="cee0b-124">Esto requiere una configuración personalizada en cada cliente de SQL Server, incluidos los servidores front-end, el servidor de supervisión, el servidor de archivado y las consolas administrativas (ejecutando el shell de administración de Lync Server, el panel de control de Lync Server o el generador de topología) y todos los demás servidores que ejecutan bases de datos de Lync Server).</span><span class="sxs-lookup"><span data-stu-id="cee0b-124">This requires a custom configuration on each SQL Server client, including Front End Servers, Monitoring Server, Archiving Server, and administrative consoles (running Lync Server Management Shell, Lync Server Control Panel, or Topology Builder), and all other servers running Lync Server databases).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cee0b-125">El acceso a bases de datos debe limitarse a los administradores de bases de datos de confianza.</span><span class="sxs-lookup"><span data-stu-id="cee0b-125">Access to databases must be limited to trusted database administrators.</span></span> <span data-ttu-id="cee0b-126">Un administrador de bases de datos malintencionado puede insertar o modificar datos en las bases de datos para adquirir privilegios sobre los servidores de Lync Server 2013 o para obtener información confidencial de los servicios, incluso si el administrador de la base de datos no se le ha concedido acceso directo o control de los servidores de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cee0b-126">A malicious database administrator could insert or modify data into the databases to acquire privileges over the Lync Server 2013 servers or obtain sensitive information from the services, even if the database administrator has not been granted direct access or control of the Lync Server 2013 servers.</span></span>



</div>

<span data-ttu-id="cee0b-127">Para obtener información detallada sobre las configuraciones personalizadas y la consolidación de las bases de datos de SQL Server, consulte el artículo del blog de NextHop, "usar Lync Server 2010 con una [http://go.microsoft.com/fwlink/p/?LinkId=214008](http://go.microsoft.com/fwlink/p/?linkid=214008)configuración de red de SQL Server personalizada", en.</span><span class="sxs-lookup"><span data-stu-id="cee0b-127">For details about custom configurations and hardening SQL Server databases, see the NextHop blog article, "Using Lync Server 2010 with a Custom SQL Server Network Configuration," at [http://go.microsoft.com/fwlink/p/?LinkId=214008](http://go.microsoft.com/fwlink/p/?linkid=214008).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cee0b-128">También puede reforzar los sistemas operativos y los servidores de aplicaciones, y puede usar la Directiva de grupo para implementar los bloqueos de seguridad en su implementación de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cee0b-128">You can also harden operating systems and applications servers, and you can use Group Policy to implement security lockdowns in your Lync Server deployment.</span></span> <span data-ttu-id="cee0b-129">Para obtener más información, consulte reforzar <A href="lync-server-2013-hardening-and-protecting-servers-and-applications.md">y proteger servidores y aplicaciones para Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="cee0b-129">For details, see <A href="lync-server-2013-hardening-and-protecting-servers-and-applications.md">Hardening and protecting servers and applications for Lync Server 2013</A>.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

