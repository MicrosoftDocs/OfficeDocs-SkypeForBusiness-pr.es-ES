---
title: 'Lync Server 2013: Publicar la topología actualizada'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Publish the updated topology
ms:assetid: 59455dd1-6a9e-433f-a714-d3636c068100
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204910(v=OCS.15)
ms:contentKeyID: 48184203
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a9f3be1443f98444712a66942417e1812181efe7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823892"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-the-updated-topology-in-lync-server-2013"></a><span data-ttu-id="06935-102">Publicar la topología actualizada en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="06935-102">Publish the updated topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="06935-103">_**Última modificación del tema:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="06935-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="06935-104">Después de actualizar su topología en el generador de topología, debe publicarla en el almacén de administración central para poder configurar y usar el servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="06935-104">After updating your topology in Topology Builder, you must publish the topology to the Central Management store before you can configure and use Persistent Chat Server.</span></span> <span data-ttu-id="06935-105">Las copias de solo lectura de los datos se replican en todos los servidores de la topología para mantener todos los servidores sincronizados con los cambios en la topología y en otras opciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="06935-105">Read-only copies of the data are replicated to all servers in the topology to keep all servers in sync with topology and other configuration changes.</span></span>

<div>

## <a name="to-publish-an-updated-topology"></a><span data-ttu-id="06935-106">Para publicar una topología actualizada</span><span class="sxs-lookup"><span data-stu-id="06935-106">To publish an updated topology</span></span>

<span data-ttu-id="06935-107">Antes de publicar su topología, instale las bases de datos para el servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="06935-107">Before you publish your topology, install the databases for Persistent Chat Server.</span></span> <span data-ttu-id="06935-108">Use el generador de topología para instalar bases de datos seleccionando **acción** e **instalar base de datos**.</span><span class="sxs-lookup"><span data-stu-id="06935-108">Use Topology Builder to install databases by selecting **Action** and **Install Database**.</span></span>

1.  <span data-ttu-id="06935-109">En un equipo que ejecute Lync Server 2013 o en el que estén instaladas las herramientas administrativas de Lync Server, inicie sesión con una cuenta que sea miembro del grupo **administradores de dominio** y del grupo **RTCUniversalServerAdmins** , y que tenga control total permisos (es decir, leer, escribir y modificar) en el almacén de archivos para usarlos en el almacén de archivos del servidor de chat persistente (para que el generador de topología pueda configurar las listas de control de acceso discrecional (DACL) obligatorias) o una cuenta con derechos de usuario equivalentes.</span><span class="sxs-lookup"><span data-stu-id="06935-109">On a computer that is running Lync Server 2013 or on which the Lync Server administrative tools are installed, log on using an account that is a member of both the **Domain Admins** group and the **RTCUniversalServerAdmins** group, and that has full control permissions (that is, read, write, and modify) on the file store to be used for the Persistent Chat Server file store (so that Topology Builder can configure the required discretionary access control lists (DACLs)), or an account with equivalent user rights.</span></span>

2.  <span data-ttu-id="06935-110">Iniciar el generador de topología.</span><span class="sxs-lookup"><span data-stu-id="06935-110">Start Topology Builder.</span></span> <span data-ttu-id="06935-111">Seleccione **Descargar topología de una implementación existente**o **abra topología desde un archivo local** si la ha guardado de forma local.</span><span class="sxs-lookup"><span data-stu-id="06935-111">Select **Download Topology from existing deployment**, or **Open Topology from a local file** if you saved it locally.</span></span>

3.  <span data-ttu-id="06935-112">En el árbol de consola, haga clic con el botón secundario en **Lync Server 2013**y, a continuación, haga clic en **publicar topología**.</span><span class="sxs-lookup"><span data-stu-id="06935-112">In the console tree, right-click **Lync Server 2013**, and then click **Publish Topology**.</span></span>

4.  <span data-ttu-id="06935-113">En la página **Publicar la topología**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="06935-113">On the **Publish the topology** page, click **Next**.</span></span>

5.  <span data-ttu-id="06935-114">En la página **Asistente para publicación completado**, compruebe que se ha publicado correctamente la topología y, luego, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="06935-114">On the **Publishing wizard complete** page, verify that the topology was successfully published, and then click **Finish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="06935-115">Después de publicar la topología, debe configurar la compatibilidad con el servidor de chat persistente antes de que se pueda archivar contenido.</span><span class="sxs-lookup"><span data-stu-id="06935-115">After publishing the topology, you must configure support for Persistent Chat Server before any content can be archived.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

