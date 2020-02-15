---
title: 'Lync Server 2013: publicación de la topología actualizada para agregar bases de datos de archivado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publishing the updated topology to add Archiving databases
ms:assetid: 454c68df-2ef5-4b5f-a44c-4eee02635d45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204860(v=OCS.15)
ms:contentKeyID: 48184034
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 543ee664aeb8f2d8688fd35f7591726c9c0c7392
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045963"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publishing-the-updated-topology-to-add-archiving-databases-in-lync-server-2013"></a><span data-ttu-id="afae7-102">Publicación de la topología actualizada para agregar bases de datos de archivado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="afae7-102">Publishing the updated topology to add Archiving databases in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="afae7-103">_**Última modificación del tema:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="afae7-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="afae7-104">Después de actualizar la topología en el generador de topologías, debe publicar la topología en el almacén de administración central para poder configurar y usar el archivado.</span><span class="sxs-lookup"><span data-stu-id="afae7-104">After updating your topology in Topology Builder, you must publish the topology to the Central Management store before you can configure and use Archiving.</span></span> <span data-ttu-id="afae7-105">Las copias de solo lectura de los datos se replican en todos los servidores de la topología para mantener todos los servidores sincronizados con los cambios de topología y de otro tipo.</span><span class="sxs-lookup"><span data-stu-id="afae7-105">Read-only copies of the data are replicated to all servers in the topology to keep all servers in sync with topology and other configuration changes.</span></span>

<div>

## <a name="to-publish-your-updated-topology"></a><span data-ttu-id="afae7-106">Para publicar su topología actualizada</span><span class="sxs-lookup"><span data-stu-id="afae7-106">To publish your updated topology</span></span>

1.  <span data-ttu-id="afae7-107">En un equipo que ejecuta Lync Server 2013 o en el que están instaladas las herramientas administrativas de Lync Server, inicie sesión con una cuenta que sea miembro del grupo de usuarios locales (o una cuenta con derechos de usuario equivalentes).</span><span class="sxs-lookup"><span data-stu-id="afae7-107">On a computer that is running Lync Server 2013, or on which the Lync Server administrative tools are installed, log on using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="afae7-108">Puede definir una topología con una cuenta que sea miembro del grupo de usuarios locales, pero para publicar una topología, que es necesaria para agregar un servidor a la topología. debe usar una cuenta que sea miembro del grupo <STRONG>administradores de dominio</STRONG> y del grupo <STRONG>RTCUniversalServerAdmins</STRONG> , y que tenga permisos de control total (es decir, lectura, escritura y modificación) en el recurso compartido de archivos que está usando para el almacén de archivos de Lync Server 2013 (es decir, el generador de topología puede configurar la lista de control de acceso discrecional (DACL) requerida. o una cuenta con derechos equivalentes.</span><span class="sxs-lookup"><span data-stu-id="afae7-108">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to add a server to the topology, you must use an account that is a member of the <STRONG>Domain Admins</STRONG> group and the <STRONG>RTCUniversalServerAdmins</STRONG> group, and that has full control permissions (that is, read, write, and modify) on the file share that you are using for the Lync Server 2013 file store (that is, so that Topology Builder can configure the required discretionary access control list (DACLs), or an account with equivalent rights.</span></span>

    
    </div>

2.  <span data-ttu-id="afae7-109">Abra la topología que creó en la sección anterior mediante el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="afae7-109">Open the topology you created in the previous section using Topology Builder.</span></span>

3.  <span data-ttu-id="afae7-110">En el árbol de la consola, haga clic con el botón secundario en **Lync Server 2013**y, a continuación, haga clic en **publicar topología**.</span><span class="sxs-lookup"><span data-stu-id="afae7-110">In the console tree, right-click **Lync Server 2013**, and then click **Publish Topology**.</span></span>

4.  <span data-ttu-id="afae7-111">En la página **Publicar la topología**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="afae7-111">On the **Publish the topology** page, click **Next**.</span></span>

5.  <span data-ttu-id="afae7-112">En la página **Crear bases de datos**, compruebe que la base de datos está seleccionada y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="afae7-112">On the **Create databases** page, verify that the database is selected, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="afae7-113">Si no tiene los permisos adecuados para crear bases de datos, puede cancelar la selección de la base de datos y alguien con permisos adecuados podrá crear la base de datos.</span><span class="sxs-lookup"><span data-stu-id="afae7-113">If you do not have the appropriate permissions to create databases, you can cancel the selection of the database and someone with appropriate permissions can create the database.</span></span> <span data-ttu-id="afae7-114">Para obtener más información sobre los permisos y derechos de administrador necesarios, consulte <A href="lync-server-2013-deployment-permissions-for-sql-server.md">permisos de implementación para SQL Server en Lync Server 2013</A> en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="afae7-114">For details about the required administrator rights and permissions, see <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment permissions for SQL Server in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="afae7-115">Solo se pueden instalar bases de datos en servidores SQL Server dedicados mediante el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="afae7-115">Only databases on dedicated SQL Server servers can be installed by using Topology Builder.</span></span> <span data-ttu-id="afae7-116">Las bases de datos de los servidores de SQL Server que se colocan con otros componentes del servidor deben instalarse mediante la ejecución de la configuración local en ese equipo.</span><span class="sxs-lookup"><span data-stu-id="afae7-116">Databases on SQL Server servers that are collocated with other server components must be installed by running local setup on that computer.</span></span>

    
    </div>

6.  <span data-ttu-id="afae7-117">En la página **Asistente para publicación completado**, verifique que se ha publicado correctamente la topología y haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="afae7-117">On the **Publishing wizard complete** page, verify that the topology was successfully published, and then click **Finish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="afae7-118">Una vez publicada la topología, debe configurar opciones y directivas para el archivado antes de que se pueda archivar cualquier contenido.</span><span class="sxs-lookup"><span data-stu-id="afae7-118">After publishing the topology, you must configure options and policies for Archiving before any content can be archived.</span></span> <span data-ttu-id="afae7-119">Para obtener más información, consulte <A href="lync-server-2013-configuring-support-for-archiving.md">Configuring Support for archiving in Lync Server 2013</A> en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="afae7-119">For details, see <A href="lync-server-2013-configuring-support-for-archiving.md">Configuring support for Archiving in Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

