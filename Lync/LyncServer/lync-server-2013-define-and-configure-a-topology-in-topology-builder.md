---
title: 'Lync Server 2013: Definir y configurar una topología en Topology Builder'
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
ms.openlocfilehash: 876651b0d0c5ed33d4e82429822585de4a2b8579
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728430"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-and-configure-a-topology-in-topology-builder-for-lync-server-2013"></a><span data-ttu-id="fadd8-102">Definir y configurar una topología en Topology Builder para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fadd8-102">Define and configure a topology in Topology Builder for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fadd8-103">_**Última modificación del tema:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="fadd8-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="fadd8-104">Al ejecutar el generador de topologías para definir una topología nueva o modificar una topología existente, no es necesario ser miembro de un grupo de dominio de administrador local o privilegiado.</span><span class="sxs-lookup"><span data-stu-id="fadd8-104">Running Topology Builder to define a new topology or to modify an existing topology does not require membership in a local administrator or privileged domain group.</span></span> <span data-ttu-id="fadd8-105">El generador de topología le guía a través de los pasos necesarios para definir su topología para un grupo de servidores front-end Enterprise Edition o Standard Edition, en función de los requisitos de configuración.</span><span class="sxs-lookup"><span data-stu-id="fadd8-105">Topology Builder guides you through the steps necessary to define your topology for an Enterprise Edition Front End pool or a Standard Edition, based on your configuration requirements.</span></span>

<span data-ttu-id="fadd8-106">Debe usar topología Builder para completar y publicar la topología antes de poder instalar Lync Server 2013 en servidores.</span><span class="sxs-lookup"><span data-stu-id="fadd8-106">You must use Topology Builder to complete and publish the topology before you can install Lync Server 2013 on servers.</span></span> <span data-ttu-id="fadd8-107">El procedimiento siguiente incluye los pasos necesarios para definir una nueva topología.</span><span class="sxs-lookup"><span data-stu-id="fadd8-107">The following procedure includes the steps required to define a new topology.</span></span>

<div>

## <a name="to-define-a-topology"></a><span data-ttu-id="fadd8-108">Para definir una topología</span><span class="sxs-lookup"><span data-stu-id="fadd8-108">To define a topology</span></span>

1.  <span data-ttu-id="fadd8-109">Iniciar generador de topología: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topología de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="fadd8-109">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="fadd8-110">En el generador de topologías, seleccione **nueva topología**.</span><span class="sxs-lookup"><span data-stu-id="fadd8-110">In Topology Builder, select **New Topology**.</span></span> <span data-ttu-id="fadd8-111">Se le pedirá una ubicación y un nombre de archivo para guardar la topología.</span><span class="sxs-lookup"><span data-stu-id="fadd8-111">You are prompted for a location and file name for saving the topology.</span></span> <span data-ttu-id="fadd8-112">Asigne al archivo de topología un nombre significativo y acepte la extensión predeterminada de. tbxml.</span><span class="sxs-lookup"><span data-stu-id="fadd8-112">Give the topology file a meaningful name and accept the default extension of .tbxml.</span></span> <span data-ttu-id="fadd8-113">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="fadd8-113">Click **OK**.</span></span>

3.  <span data-ttu-id="fadd8-114">Vaya a la ubicación donde desea guardar el nuevo archivo XML de topología, escriba un nombre para el archivo y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="fadd8-114">Navigate to the location where you want to save the new topology XML file, enter a name for the file, and then click **Save**.</span></span>

4.  <span data-ttu-id="fadd8-115">En la página **definir el dominio principal** , escriba el nombre del dominio SIP principal de la organización y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="fadd8-115">On the **Define the primary domain** page, enter the name of the primary SIP domain for your organization, and then click **Next**.</span></span>

5.  <span data-ttu-id="fadd8-116">En la página **especificar dominios admitidos adicionales** , escriba los nombres de los dominios adicionales, si los hay, y haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="fadd8-116">On the **Specify additional supported domains** page, enter the names of additional domains, if any, and then click **Next**.</span></span>

6.  <span data-ttu-id="fadd8-117">En la página **definir el primer sitio** , escriba un nombre y una descripción para el primer sitio y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="fadd8-117">On the **Define the first site** page, enter a name and a description for the first site, and then click **Next**.</span></span>

7.  <span data-ttu-id="fadd8-118">En la página **especificar detalles del sitio** , escriba la información de ubicación del sitio y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="fadd8-118">On the **Specify site details** page, enter the location information for the site, and then click **Next**.</span></span>

8.  <span data-ttu-id="fadd8-119">En la **nueva topología se definió correctamente** como página, asegúrese de que la casilla **abrir el Asistente para el usuario nuevo al cerrar el asistente** está activada y, a continuación, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="fadd8-119">On the **New topology was successfully defined** page, make sure the **Open the New Front End Wizard when this wizard closes** check box is selected, and then click **Finish**.</span></span>

<span data-ttu-id="fadd8-120">Una vez que haya definido y guardado la topología, use el Asistente para nuevo front-end para definir un grupo de servidores front-end o un servidor Standard Edition para el sitio.</span><span class="sxs-lookup"><span data-stu-id="fadd8-120">After you’ve defined and saved the topology, use the New Front End Wizard to define a Front End pool or Standard Edition server for your site.</span></span> <span data-ttu-id="fadd8-121">Para obtener más información, vea [definir y configurar un grupo de servidores front-end o un servidor Standard Edition en Lync server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md).</span><span class="sxs-lookup"><span data-stu-id="fadd8-121">For details, see [Define and configure a Front End pool or Standard Edition server in Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

