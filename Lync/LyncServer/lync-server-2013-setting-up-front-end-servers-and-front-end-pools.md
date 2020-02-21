---
title: 'Lync Server 2013: configuración de servidores front-end y grupos de servidores front-end'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up Front End Servers and Front End pools
ms:assetid: c88526f9-69e2-47dd-b3d7-056139d74fb2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398827(v=OCS.15)
ms:contentKeyID: 48185381
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e6f02d3af49cd6bf37764528d7c6f71c587d7d1b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200576"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-front-end-servers-and-front-end-pools-for-lync-server-2013"></a><span data-ttu-id="e9954-102">Configuración de servidores front-end y grupos de servidores front-end para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9954-102">Setting up Front End Servers and Front End pools for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e9954-103">_**Última modificación del tema:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="e9954-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="e9954-104">Esta sección le guiará a través de la instalación de Lync Server 2013 y la configuración de las funciones de servidor para el servidor Standard Edition y el grupo de servidores front-end, incluidos los servidores front-end y los roles de servidor combinados con los servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="e9954-104">This section guides you through installing Lync Server 2013 and setting up the server roles for the Standard Edition server and the Front End pool, including the Front End Servers and any server roles that are collocated with the Front End Servers.</span></span> <span data-ttu-id="e9954-105">Para instalar y configurar roles de servidor, ejecute el Asistente para la implementación de Lync Server en cada equipo en el que vaya a instalar una función de servidor.</span><span class="sxs-lookup"><span data-stu-id="e9954-105">To install and set up server roles, you run the Lync Server Deployment Wizard on each computer on which you are installing a server role.</span></span> <span data-ttu-id="e9954-106">Use el Asistente para la implementación para completar los cuatro pasos de implementación, incluida la instalación del almacén de configuración local, la instalación de los servidores front-end, la configuración de certificados y el inicio de los servicios.</span><span class="sxs-lookup"><span data-stu-id="e9954-106">You use the Deployment Wizard to complete all four deployment steps, including installing the Local Configuration store, installing the Front End Servers, configuring certificates, and starting services.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e9954-107">Antes de poder instalar los roles de servidor, debe haber publicado correctamente una topología.</span><span class="sxs-lookup"><span data-stu-id="e9954-107">Before you can set up server roles, you must have successfully published a topology.</span></span> <span data-ttu-id="e9954-108">Para obtener más información sobre la publicación de una topología, consulte <A href="lync-server-2013-finalizing-and-implementing-the-topology-design.md">Finalizar e implementar el diseño de la topología en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="e9954-108">For details about publishing a topology, see <A href="lync-server-2013-finalizing-and-implementing-the-topology-design.md">Finalizing and implementing the topology design in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e9954-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="e9954-109">In This Section</span></span>

  - [<span data-ttu-id="e9954-110">Instalar el almacén de configuración local en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9954-110">Install the Local Configuration store in Lync Server 2013</span></span>](lync-server-2013-install-the-local-configuration-store.md)

  - [<span data-ttu-id="e9954-111">Instalación de componentes de servidor para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9954-111">Install server components for Lync Server 2013</span></span>](lync-server-2013-install-lync-server-server-components.md)

  - [<span data-ttu-id="e9954-112">Configurar certificados para servidores en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9954-112">Configure certificates for servers in Lync Server 2013</span></span>](lync-server-2013-configure-certificates-for-servers.md)

  - [<span data-ttu-id="e9954-113">Inicie los servicios en los servidores para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9954-113">Start services on servers for Lync Server 2013</span></span>](lync-server-2013-start-services-on-servers.md)

  - [<span data-ttu-id="e9954-114">Probar la implementación del grupo de servidores en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9954-114">Test the pool deployment in Lync Server 2013</span></span>](lync-server-2013-test-the-pool-deployment.md)

  - [<span data-ttu-id="e9954-115">Probar el servidor Standard Edition en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e9954-115">Test the Standard Edition server in Lync Server 2013</span></span>](lync-server-2013-test-the-standard-edition-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

