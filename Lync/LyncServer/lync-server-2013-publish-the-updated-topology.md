---
title: 'Lync Server 2013: publicación de la topología actualizada'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publish the updated topology
ms:assetid: 59455dd1-6a9e-433f-a714-d3636c068100
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204910(v=OCS.15)
ms:contentKeyID: 48184203
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5a0a690d38d6f7d348cdaf12503b08027bc4c0f4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "41987325"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-the-updated-topology-in-lync-server-2013"></a><span data-ttu-id="d3fe0-102">Publicar la topología actualizada en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d3fe0-102">Publish the updated topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d3fe0-103">_**Última modificación del tema:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="d3fe0-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="d3fe0-104">Después de actualizar la topología en el generador de topologías, debe publicar la topología en el almacén de administración central para poder configurar y usar el servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="d3fe0-104">After updating your topology in Topology Builder, you must publish the topology to the Central Management store before you can configure and use Persistent Chat Server.</span></span> <span data-ttu-id="d3fe0-105">Las copias de solo lectura de los datos se replican a todos los servidores de la topología para que todos los servidores permanezcan sincronizados con la topología y otros cambios de configuración.</span><span class="sxs-lookup"><span data-stu-id="d3fe0-105">Read-only copies of the data are replicated to all servers in the topology to keep all servers in sync with topology and other configuration changes.</span></span>

<div>

## <a name="to-publish-an-updated-topology"></a><span data-ttu-id="d3fe0-106">Para publicar una topología actualizada</span><span class="sxs-lookup"><span data-stu-id="d3fe0-106">To publish an updated topology</span></span>

<span data-ttu-id="d3fe0-107">Antes de publicar la topología, instale las bases de datos para el servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="d3fe0-107">Before you publish your topology, install the databases for Persistent Chat Server.</span></span> <span data-ttu-id="d3fe0-108">Use el generador de topologías para instalar las bases de datos seleccionando **acción** e **instalar base de datos**.</span><span class="sxs-lookup"><span data-stu-id="d3fe0-108">Use Topology Builder to install databases by selecting **Action** and **Install Database**.</span></span>

1.  <span data-ttu-id="d3fe0-109">En un equipo que ejecuta Lync Server 2013 o en el que están instaladas las herramientas administrativas de Lync Server, inicie sesión con una cuenta que sea miembro del grupo **administradores de dominio** y del grupo **RTCUniversalServerAdmins** y que tiene permisos de control total (es decir, de lectura, escritura y modificación) en el almacén de archivos que se va a usar para el almacén de archivos del servidor de chat persistente (de modo que el generador de topologías pueda configurar las listas de control de acceso discrecional (DACL) necesarias) o una cuenta con derechos de usuario equivalentes.</span><span class="sxs-lookup"><span data-stu-id="d3fe0-109">On a computer that is running Lync Server 2013 or on which the Lync Server administrative tools are installed, log on using an account that is a member of both the **Domain Admins** group and the **RTCUniversalServerAdmins** group, and that has full control permissions (that is, read, write, and modify) on the file store to be used for the Persistent Chat Server file store (so that Topology Builder can configure the required discretionary access control lists (DACLs)), or an account with equivalent user rights.</span></span>

2.  <span data-ttu-id="d3fe0-110">Inicie el Generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="d3fe0-110">Start Topology Builder.</span></span> <span data-ttu-id="d3fe0-111">Seleccione **Descargar topología de la implementación existente**o **abrir topología desde un archivo local** si lo guardó localmente.</span><span class="sxs-lookup"><span data-stu-id="d3fe0-111">Select **Download Topology from existing deployment**, or **Open Topology from a local file** if you saved it locally.</span></span>

3.  <span data-ttu-id="d3fe0-112">En el árbol de la consola, haga clic con el botón secundario en **Lync Server 2013**y, a continuación, haga clic en **publicar topología**.</span><span class="sxs-lookup"><span data-stu-id="d3fe0-112">In the console tree, right-click **Lync Server 2013**, and then click **Publish Topology**.</span></span>

4.  <span data-ttu-id="d3fe0-113">En la página **Publicar topología**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d3fe0-113">On the **Publish the topology** page, click **Next**.</span></span>

5.  <span data-ttu-id="d3fe0-114">En la página **Asistente de publicación completado**, compruebe que la topología se haya publicado correctamente y, a continuación, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="d3fe0-114">On the **Publishing wizard complete** page, verify that the topology was successfully published, and then click **Finish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d3fe0-115">Después de publicar la topología, debe configurar la compatibilidad con el servidor de chat persistente antes de que se pueda archivar contenido.</span><span class="sxs-lookup"><span data-stu-id="d3fe0-115">After publishing the topology, you must configure support for Persistent Chat Server before any content can be archived.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

