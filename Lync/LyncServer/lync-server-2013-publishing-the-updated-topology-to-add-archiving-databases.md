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
ms.openlocfilehash: d0d12b1b4195e57fc289d11eb54f24903d05ea26
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747050"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publishing-the-updated-topology-to-add-archiving-databases-in-lync-server-2013"></a><span data-ttu-id="1132f-102">Publicar la topología actualizada para agregar bases de datos de archivado en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1132f-102">Publishing the updated topology to add Archiving databases in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1132f-103">_**Última modificación del tema:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="1132f-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="1132f-104">Después de actualizar su topología en el generador de topología, debe publicarla en el almacén de administración central antes de poder configurar y usar el archivado.</span><span class="sxs-lookup"><span data-stu-id="1132f-104">After updating your topology in Topology Builder, you must publish the topology to the Central Management store before you can configure and use Archiving.</span></span> <span data-ttu-id="1132f-105">Las copias de solo lectura de los datos se replican en todos los servidores de la topología para mantener todos los servidores sincronizados con los cambios en la topología y en otras opciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="1132f-105">Read-only copies of the data are replicated to all servers in the topology to keep all servers in sync with topology and other configuration changes.</span></span>

<div>

## <a name="to-publish-your-updated-topology"></a><span data-ttu-id="1132f-106">Para publicar su topología actualizada</span><span class="sxs-lookup"><span data-stu-id="1132f-106">To publish your updated topology</span></span>

1.  <span data-ttu-id="1132f-107">En un equipo que ejecute Lync Server 2013 o en el que estén instaladas las herramientas administrativas de Lync Server, inicie sesión con una cuenta que sea miembro del grupo usuarios locales (o una cuenta con derechos de usuario equivalentes).</span><span class="sxs-lookup"><span data-stu-id="1132f-107">On a computer that is running Lync Server 2013, or on which the Lync Server administrative tools are installed, log on using an account that is a member of the local Users group (or an account with equivalent user rights).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1132f-108">Puede definir una topología con una cuenta que sea miembro del grupo usuarios locales, pero para publicar una topología, que es necesaria para agregar un servidor a la topología. debe usar una cuenta que sea miembro del grupo <STRONG>administradores de dominio</STRONG> y el grupo <STRONG>RTCUniversalServerAdmins</STRONG> , y que tenga permisos de control total (es decir, leer, escribir y modificar) en el recurso compartido de archivos de Lync Server 2013 (es decir, para que el generador de topología pueda configurar la lista de control de acceso discrecional (DACL) requerida. o una cuenta con derechos equivalentes.</span><span class="sxs-lookup"><span data-stu-id="1132f-108">You can define a topology by using an account that is a member of the local Users group, but to publish a topology, which is required to add a server to the topology, you must use an account that is a member of the <STRONG>Domain Admins</STRONG> group and the <STRONG>RTCUniversalServerAdmins</STRONG> group, and that has full control permissions (that is, read, write, and modify) on the file share that you are using for the Lync Server 2013 file store (that is, so that Topology Builder can configure the required discretionary access control list (DACLs), or an account with equivalent rights.</span></span>

    
    </div>

2.  <span data-ttu-id="1132f-109">Abra la topología que creó en la sección anterior con el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="1132f-109">Open the topology you created in the previous section using Topology Builder.</span></span>

3.  <span data-ttu-id="1132f-110">En el árbol de consola, haga clic con el botón secundario en **Lync Server 2013**y, a continuación, haga clic en **publicar topología**.</span><span class="sxs-lookup"><span data-stu-id="1132f-110">In the console tree, right-click **Lync Server 2013**, and then click **Publish Topology**.</span></span>

4.  <span data-ttu-id="1132f-111">En la página **Publicar la topología**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="1132f-111">On the **Publish the topology** page, click **Next**.</span></span>

5.  <span data-ttu-id="1132f-112">En la página **Crear bases de datos**, compruebe que la base de datos está seleccionada y, luego, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="1132f-112">On the **Create databases** page, verify that the database is selected, and then click **Next**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1132f-113">Si no tiene los permisos adecuados para crear bases de datos, puede cancelar la selección de la base de datos y alguien con permisos adecuados podrá crear la base de datos.</span><span class="sxs-lookup"><span data-stu-id="1132f-113">If you do not have the appropriate permissions to create databases, you can cancel the selection of the database and someone with appropriate permissions can create the database.</span></span> <span data-ttu-id="1132f-114">Para obtener detalles sobre los permisos y derechos de administrador necesarios, consulte <A href="lync-server-2013-deployment-permissions-for-sql-server.md">permisos de implementación para SQL Server en Lync server 2013</A> en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="1132f-114">For details about the required administrator rights and permissions, see <A href="lync-server-2013-deployment-permissions-for-sql-server.md">Deployment permissions for SQL Server in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="1132f-115">Con el generador de topologías solo se pueden instalar bases de datos en servidores SQL Server dedicados.</span><span class="sxs-lookup"><span data-stu-id="1132f-115">Only databases on dedicated SQL Server servers can be installed by using Topology Builder.</span></span> <span data-ttu-id="1132f-116">Las bases de datos de los servidores SQL Server que se colocan con otros componentes del servidor se deben instalar ejecutando la configuración local en ese equipo.</span><span class="sxs-lookup"><span data-stu-id="1132f-116">Databases on SQL Server servers that are collocated with other server components must be installed by running local setup on that computer.</span></span>

    
    </div>

6.  <span data-ttu-id="1132f-117">En la página **Asistente para publicación completado**, compruebe que se ha publicado correctamente la topología y, luego, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="1132f-117">On the **Publishing wizard complete** page, verify that the topology was successfully published, and then click **Finish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="1132f-118">Una vez publicada la topología, necesita configurar las opciones y las directivas para el archivado antes de que se pueda archivar cualquier contenido.</span><span class="sxs-lookup"><span data-stu-id="1132f-118">After publishing the topology, you must configure options and policies for Archiving before any content can be archived.</span></span> <span data-ttu-id="1132f-119">Para obtener más información, vea configuración de la <A href="lync-server-2013-configuring-support-for-archiving.md">compatibilidad de archivado en Lync Server 2013</A> en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="1132f-119">For details, see <A href="lync-server-2013-configuring-support-for-archiving.md">Configuring support for Archiving in Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

