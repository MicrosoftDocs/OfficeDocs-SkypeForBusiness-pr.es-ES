---
title: 'Lync Server 2013: Implementación de Lync Server 2013 Standard Edition en un Lync Server 2013 Enterprise existente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying Lync Server 2013 Standard Edition into an existing Lync Server 2013 Enterprise
ms:assetid: 05ea128d-6c94-49b3-b28b-477367196425
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398112(v=OCS.15)
ms:contentKeyID: 48183297
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c505a692590662adf03e48d695b3c1ff089d8d7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835542"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-lync-server-2013-standard-edition-into-an-existing-lync-server-2013-enterprise"></a><span data-ttu-id="31156-102">Implementación de Lync Server 2013 Standard Edition en un Lync Server 2013 Enterprise existente</span><span class="sxs-lookup"><span data-stu-id="31156-102">Deploying Lync Server 2013 Standard Edition into an existing Lync Server 2013 Enterprise</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="31156-103">_**Última modificación del tema:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="31156-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="31156-104">Implementar un servidor Standard Edition en una implementación existente de Enterprise Edition es similar a implementar roles de servidor adicionales.</span><span class="sxs-lookup"><span data-stu-id="31156-104">Deploying a Standard Edition server into an existing Enterprise Edition deployment is similar to deploying additional server roles.</span></span> <span data-ttu-id="31156-105">Es posible que se implemente un servidor Standard Edition en otro sitio, lo que permite a los usuarios de ese sitio estar alojados en el servidor Standard Edition en lugar del grupo de aplicaciones front-end en una red de área extensa (WAN).</span><span class="sxs-lookup"><span data-stu-id="31156-105">A Standard Edition server might be deployed to another site, allowing for users in that site to be homed on the Standard Edition server rather than the Front End pool across a wide area network (WAN).</span></span> <span data-ttu-id="31156-106">Los procedimientos para instalar el nuevo sitio y los servidores de ese sitio ya están definidos en otras secciones de la documentación de [implementación de Lync Server 2013](lync-server-2013-deploying-lync-server.md) .</span><span class="sxs-lookup"><span data-stu-id="31156-106">The procedures for installing the new site and servers in that site are already defined in other sections of the [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) documentation.</span></span>

<div id="sectionSection0" class="section">

<span data-ttu-id="31156-107">**Para definir un sitio nuevo**</span><span class="sxs-lookup"><span data-stu-id="31156-107">**To define a new site**</span></span>

1.  <span data-ttu-id="31156-108">Iniciar generador de topología: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topología de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="31156-108">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="31156-109">En el árbol de consola, haga clic con el botón secundario en **Lync Server 2013**y, a continuación, haga clic en **nuevo sitio central**.</span><span class="sxs-lookup"><span data-stu-id="31156-109">In the console tree, right-click **Lync Server 2013**, and then click **New Central Site**.</span></span>

3.  <span data-ttu-id="31156-110">En la página **identificar el sitio** , asigne un nombre al sitio y, opcionalmente, escriba una descripción.</span><span class="sxs-lookup"><span data-stu-id="31156-110">On the **Identify the site** page, give a name to the site and optionally enter a description.</span></span>

4.  <span data-ttu-id="31156-111">Siga los procedimientos para definir el resto de la topología del sitio.</span><span class="sxs-lookup"><span data-stu-id="31156-111">Follow the procedures for defining the rest of the site topology.</span></span> <span data-ttu-id="31156-112">Para obtener más información, consulte [definir y configurar la topología en Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span><span class="sxs-lookup"><span data-stu-id="31156-112">For details, see [Defining and configuring the topology in Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).</span></span>

5.  <span data-ttu-id="31156-113">Publique la topología actualizada.</span><span class="sxs-lookup"><span data-stu-id="31156-113">Publish the updated topology.</span></span> <span data-ttu-id="31156-114">Para obtener más información, vea [publicar la topología en Lync Server 2013](lync-server-2013-publish-the-topology.md).</span><span class="sxs-lookup"><span data-stu-id="31156-114">For details, see [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md).</span></span>

6.  <span data-ttu-id="31156-115">Configure e instale un servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="31156-115">Set up and install a Standard Edition server.</span></span>
    
    <div>
    

    > [!Caution]  
    > <span data-ttu-id="31156-116">Si ha implementado un entorno con un servidor Standard Edition, debería haber iniciado el proceso de instalación desde el Asistente para la implementación de Lync Server mediante el vínculo <STRONG>preparar el primer servidor Standard Edition</STRONG> para instalar los archivos de base de datos iniciales en el nuevo Servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="31156-116">If you have deployed an environment with only a Standard Edition server, you would have begun the setup process from the Lync Server Deployment Wizard by using the <STRONG>Prepare first Standard Edition server</STRONG> link to install the initial database files to the new Standard Edition server.</span></span> <span data-ttu-id="31156-117"><STRONG>No</STRONG> siga ese proceso cuando instale un servidor Standard Edition en una implementación existente de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="31156-117"><STRONG>Do not</STRONG> follow that process when installing a Standard Edition server into an existing Lync Server 2013 deployment.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

