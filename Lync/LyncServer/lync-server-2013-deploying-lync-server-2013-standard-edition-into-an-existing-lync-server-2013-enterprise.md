---
title: 'Lync Server 2013: implementación de Lync Server 2013 Standard Edition en un Lync Server 2013 Enterprise existente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Lync Server 2013 Standard Edition into an existing Lync Server 2013 Enterprise
ms:assetid: 05ea128d-6c94-49b3-b28b-477367196425
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398112(v=OCS.15)
ms:contentKeyID: 48183297
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 733dcadc52550c665cc74407a81cddbfbd5ea640
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195373"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-lync-server-2013-standard-edition-into-an-existing-lync-server-2013-enterprise"></a><span data-ttu-id="a3fdb-102">Implementación de Lync Server 2013 Standard Edition en una empresa existente de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a3fdb-102">Deploying Lync Server 2013 Standard Edition into an existing Lync Server 2013 Enterprise</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a3fdb-103">_**Última modificación del tema:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="a3fdb-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="a3fdb-104">La implementación de un servidor Standard Edition en una implementación de Enterprise Edition existente es similar a la implementación de roles de servidor adicionales.</span><span class="sxs-lookup"><span data-stu-id="a3fdb-104">Deploying a Standard Edition server into an existing Enterprise Edition deployment is similar to deploying additional server roles.</span></span> <span data-ttu-id="a3fdb-105">Es posible que se implemente un servidor Standard Edition en otro sitio, lo que permite a los usuarios de ese sitio hospedarse en el servidor Standard Edition en lugar del grupo de servidores front-end en una red de área extensa (WAN).</span><span class="sxs-lookup"><span data-stu-id="a3fdb-105">A Standard Edition server might be deployed to another site, allowing for users in that site to be homed on the Standard Edition server rather than the Front End pool across a wide area network (WAN).</span></span> <span data-ttu-id="a3fdb-106">Los procedimientos para instalar el nuevo sitio y los servidores de ese sitio ya están definidos en otras secciones de la documentación sobre la [implementación de Lync Server 2013](lync-server-2013-deploying-lync-server.md) .</span><span class="sxs-lookup"><span data-stu-id="a3fdb-106">The procedures for installing the new site and servers in that site are already defined in other sections of the [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) documentation.</span></span>

<div id="sectionSection0" class="section">

<span data-ttu-id="a3fdb-107">**Para definir un sitio nuevo**</span><span class="sxs-lookup"><span data-stu-id="a3fdb-107">**To define a new site**</span></span>

1.  <span data-ttu-id="a3fdb-108">Inicie el generador de topologías: haga clic en **Inicio**, haga clic en **todos los programas**, haga clic en **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topologías de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="a3fdb-108">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="a3fdb-109">En el árbol de la consola, haga clic con el botón secundario en **Lync Server 2013**y, a continuación, haga clic en **nuevo sitio central**.</span><span class="sxs-lookup"><span data-stu-id="a3fdb-109">In the console tree, right-click **Lync Server 2013**, and then click **New Central Site**.</span></span>

3.  <span data-ttu-id="a3fdb-110">En la página **Identificar el sitio**, escriba un nombre para el sitio y, opcionalmente, una descripción.</span><span class="sxs-lookup"><span data-stu-id="a3fdb-110">On the **Identify the site** page, give a name to the site and optionally enter a description.</span></span>

4.  <span data-ttu-id="a3fdb-111">Siga los procedimientos de definición del resto de la topología del sitio.</span><span class="sxs-lookup"><span data-stu-id="a3fdb-111">Follow the procedures for defining the rest of the site topology.</span></span> <span data-ttu-id="a3fdb-112">Para obtener más información, consulte [definir y configurar la topología en Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span><span class="sxs-lookup"><span data-stu-id="a3fdb-112">For details, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span></span>

5.  <span data-ttu-id="a3fdb-113">Publicar la topología actualizada.</span><span class="sxs-lookup"><span data-stu-id="a3fdb-113">Publish the updated topology.</span></span> <span data-ttu-id="a3fdb-114">Para obtener más información, consulte [publicar la topología en Lync Server 2013](lync-server-2013-publish-the-topology.md).</span><span class="sxs-lookup"><span data-stu-id="a3fdb-114">For details, see [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md).</span></span>

6.  <span data-ttu-id="a3fdb-115">Configurar e instalar un servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="a3fdb-115">Set up and install a Standard Edition server.</span></span>
    
    <div>
    

    > [!Caution]  
    > <span data-ttu-id="a3fdb-116">Si ha implementado un entorno con un servidor Standard Edition, habría iniciado el proceso de instalación desde el Asistente para la implementación de Lync Server mediante el vínculo <STRONG>preparar el primer servidor Standard Edition</STRONG> para instalar los archivos de base de datos iniciales en el nuevo servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="a3fdb-116">If you have deployed an environment with only a Standard Edition server, you would have begun the setup process from the Lync Server Deployment Wizard by using the <STRONG>Prepare first Standard Edition server</STRONG> link to install the initial database files to the new Standard Edition server.</span></span> <span data-ttu-id="a3fdb-117"><STRONG>No</STRONG> siga ese proceso cuando instale un servidor Standard Edition en una implementación existente de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a3fdb-117"><STRONG>Do not</STRONG> follow that process when installing a Standard Edition server into an existing Lync Server 2013 deployment.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

