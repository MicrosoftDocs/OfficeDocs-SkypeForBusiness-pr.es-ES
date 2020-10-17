---
title: 'Lync Server 2013: definir y configurar una topología en el generador de topologías'
description: 'Lync Server 2013: definir y configurar una topología en el generador de topologías.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define and configure a topology in Topology Builder
ms:assetid: 99231ff5-1c21-432b-ad65-8675fcd484f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398788(v=OCS.15)
ms:contentKeyID: 48184953
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 83a1f29ec78cf7cfd3856d3f1aa87a22dc0bbe00
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569946"
---
# <a name="define-and-configure-a-topology-in-topology-builder-for-lync-server-2013"></a><span data-ttu-id="af68e-103">Definir y configurar una topología en el generador de topologías para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="af68e-103">Define and configure a topology in Topology Builder for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="af68e-104">_**Última modificación del tema:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="af68e-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="af68e-105">Ejecutar el generador de topologías para definir una nueva topología o modificar una topología existente no requiere la pertenencia a un grupo de dominio con privilegios o de administrador local.</span><span class="sxs-lookup"><span data-stu-id="af68e-105">Running Topology Builder to define a new topology or to modify an existing topology does not require membership in a local administrator or privileged domain group.</span></span> <span data-ttu-id="af68e-106">El generador de topología le guía por los pasos necesarios para definir la topología de un grupo de servidores front-end Enterprise Edition o Standard Edition, según los requisitos de configuración.</span><span class="sxs-lookup"><span data-stu-id="af68e-106">Topology Builder guides you through the steps necessary to define your topology for an Enterprise Edition Front End pool or a Standard Edition, based on your configuration requirements.</span></span>

<span data-ttu-id="af68e-107">Debe usar el generador de topologías para completar y publicar la topología antes de poder instalar Lync Server 2013 en los servidores.</span><span class="sxs-lookup"><span data-stu-id="af68e-107">You must use Topology Builder to complete and publish the topology before you can install Lync Server 2013 on servers.</span></span> <span data-ttu-id="af68e-108">En el siguiente procedimiento se indican los pasos necesarios para definir una nueva topología.</span><span class="sxs-lookup"><span data-stu-id="af68e-108">The following procedure includes the steps required to define a new topology.</span></span>

<div>

## <a name="to-define-a-topology"></a><span data-ttu-id="af68e-109">Para definir una topología</span><span class="sxs-lookup"><span data-stu-id="af68e-109">To define a topology</span></span>

1.  <span data-ttu-id="af68e-110">Inicie el generador de topologías: haga clic en **Inicio**, haga clic en **todos los programas**, haga clic en **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topologías de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="af68e-110">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="af68e-111">En generador de topologías, seleccione **nueva topología**.</span><span class="sxs-lookup"><span data-stu-id="af68e-111">In Topology Builder, select **New Topology**.</span></span> <span data-ttu-id="af68e-112">Se le pedirá que elija una ubicación y un nombre de archivo para guardar la topología.</span><span class="sxs-lookup"><span data-stu-id="af68e-112">You are prompted for a location and file name for saving the topology.</span></span> <span data-ttu-id="af68e-113">Asigne un nombre descriptivo al archivo de topología y acepte la extensión predeterminada de .tbxml.</span><span class="sxs-lookup"><span data-stu-id="af68e-113">Give the topology file a meaningful name and accept the default extension of .tbxml.</span></span> <span data-ttu-id="af68e-114">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="af68e-114">Click **OK**.</span></span>

3.  <span data-ttu-id="af68e-115">Vaya a la ubicación donde desea guardar el nuevo archivo XML de topología, especifique un nombre para el archivo y haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="af68e-115">Navigate to the location where you want to save the new topology XML file, enter a name for the file, and then click **Save**.</span></span>

4.  <span data-ttu-id="af68e-116">En la página **Definir el dominio principal**, escriba el nombre del dominio SIP principal de la organización y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="af68e-116">On the **Define the primary domain** page, enter the name of the primary SIP domain for your organization, and then click **Next**.</span></span>

5.  <span data-ttu-id="af68e-117">En la página **Especificar dominios admitidos adicionales**, especifique el nombre de los dominios adicionales, si los hay, y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="af68e-117">On the **Specify additional supported domains** page, enter the names of additional domains, if any, and then click **Next**.</span></span>

6.  <span data-ttu-id="af68e-118">En la página **Definir el primer sitio**, escriba un nombre y una descripción para el primer sitio y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="af68e-118">On the **Define the first site** page, enter a name and a description for the first site, and then click **Next**.</span></span>

7.  <span data-ttu-id="af68e-119">En la página **Especificar detalles del sitio**, escriba la información de ubicación del sitio y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="af68e-119">On the **Specify site details** page, enter the location information for the site, and then click **Next**.</span></span>

8.  <span data-ttu-id="af68e-120">En la página **nueva topología definida correctamente** , asegúrese de que esté activada la casilla **abrir el Asistente para nuevo front-end cuando se cierre este asistente** y, a continuación, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="af68e-120">On the **New topology was successfully defined** page, make sure the **Open the New Front End Wizard when this wizard closes** check box is selected, and then click **Finish**.</span></span>

<span data-ttu-id="af68e-121">Una vez que haya definido y guardado la topología, use el Asistente para nuevo servidor front-end con el fin de definir un grupo de servidores front-end o un servidor Standard Edition para el sitio.</span><span class="sxs-lookup"><span data-stu-id="af68e-121">After you’ve defined and saved the topology, use the New Front End Wizard to define a Front End pool or Standard Edition server for your site.</span></span> <span data-ttu-id="af68e-122">Para obtener más información, consulte [definir y configurar un grupo de servidores front-end o un servidor Standard Edition en Lync server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md).</span><span class="sxs-lookup"><span data-stu-id="af68e-122">For details, see [Define and configure a Front End pool or Standard Edition server in Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

