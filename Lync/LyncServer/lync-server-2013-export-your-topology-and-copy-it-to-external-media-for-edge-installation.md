---
title: Exportar la topología y copiarla en un medio externo para la instalación perimetral
description: Exportar la topología y copiarla en un medio externo para la instalación perimetral.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Export your topology and copy it to external media for edge installation
ms:assetid: def9f416-c519-4a72-b242-7d3057d9c1fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398983(v=OCS.15)
ms:contentKeyID: 48185615
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47fcee032b4c0e667455ae7f35afe8b99c2d12cc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564766"
---
# <a name="export-your-lync-server-2013-topology-and-copy-it-to-external-media-for-edge-installation"></a><span data-ttu-id="046b4-103">Exportar la topología de Lync Server 2013 y copiarla en un medio externo para la instalación perimetral</span><span class="sxs-lookup"><span data-stu-id="046b4-103">Export your Lync Server 2013 topology and copy it to external media for edge installation</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="046b4-104">_**Última modificación del tema:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="046b4-104">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="046b4-105">Después de publicar la topología, el Asistente para la implementación de Lync Server necesita tener acceso a los datos del almacén de administración central para poder iniciar el proceso de implementación en el servidor.</span><span class="sxs-lookup"><span data-stu-id="046b4-105">After you publish your topology, the Lync Server Deployment Wizard needs access to the Central Management store data in order to start the deployment process on the server.</span></span> <span data-ttu-id="046b4-106">En la red interna, se puede obtener acceso a los datos desde los servidores, pero los servidores perimetrales que no se encuentran en el dominio interno no pueden obtener acceso a los datos.</span><span class="sxs-lookup"><span data-stu-id="046b4-106">In the internal network, the data is available directly from the servers, but Edge Servers that are not in the internal domain cannot access the data.</span></span> <span data-ttu-id="046b4-107">Para que los datos de configuración de la topología estén disponibles para una implementación de servidor perimetral, debe exportar los datos de la topología a un archivo y copiarlos en medios externos (por ejemplo, una unidad USB o un recurso compartido de red disponible desde el servidor perimetral) antes de ejecutar el Asistente para la implementación de Lync Server en el servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="046b4-107">To make the topology configuration data available for an Edge Server deployment, you must export the topology data to a file and copy it to external media (for example, a USB drive or a network share that is available from the Edge Server) before you run the Lync Server Deployment Wizard on the Edge Server.</span></span> <span data-ttu-id="046b4-108">Siga el procedimiento indicado a continuación para hacer que sus datos de configuración de topología estén disponibles en el servidor perimetral que está implementando.</span><span class="sxs-lookup"><span data-stu-id="046b4-108">Use the following procedure to make your topology configuration data available on the Edge Server that you are deploying.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="046b4-109">Después de instalar Lync Server 2013 en un servidor perimetral, se administra el servidor perimetral mediante las herramientas administrativas de la red interna, que replican automáticamente la configuración en los servidores perimetrales de la implementación.</span><span class="sxs-lookup"><span data-stu-id="046b4-109">After you install Lync Server 2013 on an Edge Server, you manage the Edge Server using the administrative tools in the internal network, which automatically replicate configuration to any Edge Servers in your deployment.</span></span> <span data-ttu-id="046b4-110">La única excepción es la asignación e instalación de certificados, así como la detención y el inicio de servicios que deben realizarse en el servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="046b4-110">The only exception is assigning and installing certificates and stopping and starting services, both of which must be done on the Edge Server.</span></span>



</div>

<div>

## <a name="to-make-your-topology-data-available-on-an-edge-server-by-using-lync-server-management-shell"></a><span data-ttu-id="046b4-111">Para hacer que los datos de la topología estén disponibles en un servidor perimetral mediante el Shell de administración de Communications Server</span><span class="sxs-lookup"><span data-stu-id="046b4-111">To make your topology data available on an Edge Server by using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="046b4-112">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="046b4-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="046b4-113">En el shell de administración de Lync Server, ejecute el siguiente cmdlet:</span><span class="sxs-lookup"><span data-stu-id="046b4-113">In the Lync Server Management Shell, run the following cmdlet:</span></span>
    
        Export-CsConfiguration -FileName <ConfigurationFilePath.zip>

3.  <span data-ttu-id="046b4-114">Copie el archivo externo a medios externos (por ejemplo, una unidad USB o un recurso compartido de red disponible desde el servidor perimetral durante la implementación).</span><span class="sxs-lookup"><span data-stu-id="046b4-114">Copy the exported file to external media (for example, a USB drive or a network share that is available from the Edge Server during deployment).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

