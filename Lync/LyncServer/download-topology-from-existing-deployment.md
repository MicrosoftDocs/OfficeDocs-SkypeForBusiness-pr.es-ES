---
title: Descargar una topología desde una implementación existente
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Download topology from existing deployment
ms:assetid: e39065a2-d4b0-4f27-8c49-f56be78fa55b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721913(v=OCS.15)
ms:contentKeyID: 49733847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7ebf73ad647003a1835a235bda240229433ac6d6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137951"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="download-topology-from-existing-deployment"></a><span data-ttu-id="e3d26-102">Descargar una topología desde una implementación existente</span><span class="sxs-lookup"><span data-stu-id="e3d26-102">Download topology from existing deployment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e3d26-103">_**Última modificación del tema:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="e3d26-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="e3d26-104">Al crear un grupo de servidores de Lync Server 2013, usará el almacén de administración central que está asociado con Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="e3d26-104">When creating a Lync Server 2013 pool, you will use the Central Management Store that is associated with Lync Server 2010.</span></span> <span data-ttu-id="e3d26-105">Cuando inicie el Generador de topologías, en el primer uso y en los usos posteriores se le solicitará la ubicación en la que desea que el Generador de topologías cargue el documento de configuración actual.</span><span class="sxs-lookup"><span data-stu-id="e3d26-105">When you start Topology Builder on first use and subsequent edit sessions, you are prompted for the location where you want Topology Builder to load the current configuration document.</span></span> <span data-ttu-id="e3d26-106">Como ya tiene una topología de Lync Server 2010 definida y ha establecido el almacén de administración central, debe elegir descargar una topología de una implementación existente.</span><span class="sxs-lookup"><span data-stu-id="e3d26-106">Because you already have a Lync Server 2010 topology defined and have established the Central Management store, you should choose to download a topology from an existing deployment.</span></span> <span data-ttu-id="e3d26-107">El Generador de topologías leerá la base de datos y recuperará la definición actual.</span><span class="sxs-lookup"><span data-stu-id="e3d26-107">Topology Builder will read the database and retrieve the current definition.</span></span>

<span data-ttu-id="e3d26-108">**Para descargar una topología de una implementación existente**</span><span class="sxs-lookup"><span data-stu-id="e3d26-108">**To download a topology from an existing deployment**</span></span>

1.  <span data-ttu-id="e3d26-109">Abra el **Asistente para la implementación de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="e3d26-109">Open the **Lync Server Deployment Wizard**.</span></span>

2.  <span data-ttu-id="e3d26-110">En la página **Lync Server 2013 – Asistente para la implementación**, haga clic en **Instalar las Herramientas administrativas**.</span><span class="sxs-lookup"><span data-stu-id="e3d26-110">From the **Lync Server 2013 – Deployment Wizard** page, click **Install Administrative Tools**.</span></span>

3.  <span data-ttu-id="e3d26-111">Inicie el generador de topologías: haga clic en **Inicio**, haga clic en **todos los programas**, haga clic en **Microsoft Lync Server 2013** y, a continuación, haga clic en **generador de topologías de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="e3d26-111">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013** , and then click **Lync Server Topology Builder**.</span></span>

4.  <span data-ttu-id="e3d26-112">Seleccione **Descargar una topología desde una implementación existente**.</span><span class="sxs-lookup"><span data-stu-id="e3d26-112">Select **Download Topology from existing deployment**.</span></span>
    
    <span data-ttu-id="e3d26-113">![Configuración del generador de topologías del Asistente para la implementación](images/JJ721913.d5b39fd9-3c13-422e-a06c-25d2568fe781(OCS.15).jpg "Configuración del generador de topologías del Asistente para la implementación")</span><span class="sxs-lookup"><span data-stu-id="e3d26-113">![Deployment Wizard Topology Builder settings](images/JJ721913.d5b39fd9-3c13-422e-a06c-25d2568fe781(OCS.15).jpg "Deployment Wizard Topology Builder settings")</span></span>

5.  <span data-ttu-id="e3d26-114">Elija un nombre de archivo y guarde la topología con el tipo de archivo .tbxml como valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="e3d26-114">Choose a file name and save the topology with the default .tbxml file type.</span></span>

6.  <span data-ttu-id="e3d26-115">Expanda el nodo de Lync Server, tal como mostramos, para revelar los diversos roles de servidor de la implementación.</span><span class="sxs-lookup"><span data-stu-id="e3d26-115">Expand the Lync Server node, as shown, to reveal the various server roles in the deployment.</span></span>
    
    <span data-ttu-id="e3d26-116">![Propiedades generales del rol de servidor del generador de topologías](images/JJ721913.af99ead3-676b-47fd-8369-5a5f9717383f(OCS.15).jpg "Propiedades generales del rol de servidor del generador de topologías")</span><span class="sxs-lookup"><span data-stu-id="e3d26-116">![Topology Builder server role general properties](images/JJ721913.af99ead3-676b-47fd-8369-5a5f9717383f(OCS.15).jpg "Topology Builder server role general properties")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

