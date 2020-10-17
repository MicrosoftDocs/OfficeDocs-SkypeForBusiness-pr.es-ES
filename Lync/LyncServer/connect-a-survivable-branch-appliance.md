---
title: Conectar una aplicación de sucursal con funciones de supervivencia
description: Conecte una aplicación de sucursal con funciones de supervivencia.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Connect a Survivable Branch Appliance
ms:assetid: fe3167e2-d1b1-4cd4-bf30-262e0e7d14e8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721948(v=OCS.15)
ms:contentKeyID: 49733886
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f5bbf9e1a4189d3c80d6dec449adf68b82cd3691
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550286"
---
# <a name="connect-a-survivable-branch-appliance"></a><span data-ttu-id="db8b3-103">Conectar una aplicación de sucursal con funciones de supervivencia</span><span class="sxs-lookup"><span data-stu-id="db8b3-103">Connect a Survivable Branch Appliance</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="db8b3-104">_**Última modificación del tema:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="db8b3-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="db8b3-105">Cada aplicación de sucursal con funciones de supervivencia (SBA) está asociada a un grupo de servidores front-end que sirve como registrador de copias de seguridad para SBA.</span><span class="sxs-lookup"><span data-stu-id="db8b3-105">Every Survivable Branch Appliance (SBA) is associated with a Front End pool which serves as a backup registrar for the SBA.</span></span> <span data-ttu-id="db8b3-106">Cuando el grupo de servidores front-end se migra a Lync Server 2013, SBA debe estar desasociado del grupo de servidores front-end de Lync Server 2010 mientras se actualiza el grupo, una vez que el grupo se ha migrado a Lync Server 2013, la SBA se puede volver a asociar con el grupo de servidores front-end actualizado.</span><span class="sxs-lookup"><span data-stu-id="db8b3-106">When the Front End pool is migrated to Lync Server 2013, the SBA must be disassociated from the Lync Server 2010 Front End pool while the pool is upgraded, Once the pool has been migrated to Lync Server 2013, the SBA can be re-associated with the upgraded Front End pool.</span></span> <span data-ttu-id="db8b3-107">Esto implica eliminar la SBA de la topología de Lync Server 2010 heredada en el generador de topologías y, a continuación, agregar la SBA a la topología de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="db8b3-107">This involves deleting the SBA from the legacy Lync Server 2010 topology in Topology Builder and then adding the SBA to the Lync Server 2013 topology.</span></span> <span data-ttu-id="db8b3-108">Los usuarios hospedados en el servidor de Lync Server 2010 SBA deben moverse primero a otro grupo de servidores front-end antes de quitar SBA de la topología.</span><span class="sxs-lookup"><span data-stu-id="db8b3-108">Users homed on the legacy Lync Server 2010 SBA must first be moved to another Front End pool before removing the SBA from the topology.</span></span> <span data-ttu-id="db8b3-109">Una vez agregada SBA a la topología de Lync Server 2013, estos usuarios pueden volver a moverse a SBA.</span><span class="sxs-lookup"><span data-stu-id="db8b3-109">Once the SBA is added to the Lync Server 2013 topology, those users can then be moved back to the SBA.</span></span> <span data-ttu-id="db8b3-110">Estos pasos se sintetizan a continuación:</span><span class="sxs-lookup"><span data-stu-id="db8b3-110">These steps are summarized below:</span></span>

1.  <span data-ttu-id="db8b3-111">Mueva los usuarios de sucursal alojados en el servidor de Lync Server 2010 heredado a otro grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="db8b3-111">Move branch users homed on the legacy SBA Lync Server 2010 to another Front End pool.</span></span>

2.  <span data-ttu-id="db8b3-112">Quite SBA de la topología heredada de Lync Server 2010 para desconectar el grupo de servidores front-end existente como registrador de reserva.</span><span class="sxs-lookup"><span data-stu-id="db8b3-112">Remove SBA from the legacy Lync Server 2010 topology to disconnect the existing Front End pool as a backup registrar.</span></span>

3.  <span data-ttu-id="db8b3-113">Agregue SBA a la topología de Lync Server 2013 y configure este nuevo grupo de servidores front-end como registrador de reserva.</span><span class="sxs-lookup"><span data-stu-id="db8b3-113">Add SBA to the Lync Server 2013 topology and configure this new Front End pool as the backup registrar.</span></span>

4.  <span data-ttu-id="db8b3-114">Mueva los usuarios de sucursal al nuevo SBA de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="db8b3-114">Move the branch users to the new Lync Server 2013 SBA.</span></span>

<span data-ttu-id="db8b3-115">**Agregar un sitio de sucursal SBA de Lync Server 2010 a la topología**</span><span class="sxs-lookup"><span data-stu-id="db8b3-115">**Add Lync Server 2010 SBA Branch Site to Your Topology**</span></span>

1.  <span data-ttu-id="db8b3-116">Abrir **Generador de topologías**.</span><span class="sxs-lookup"><span data-stu-id="db8b3-116">Open **Topology Builder**.</span></span>

2.  <span data-ttu-id="db8b3-117">En el panel de la izquierda, hacer clic con el botón secundario en **Sitios de sucursal** y, a continuación, en **Nuevo sitio de sucursal**.</span><span class="sxs-lookup"><span data-stu-id="db8b3-117">In the left pane right-click **Branch sites**, and then click **New Branch Site**.</span></span>

3.  <span data-ttu-id="db8b3-118">En el cuadro de diálogo **Definir nuevo sitio de sucursal**, haga clic en \*\*Nombre \*\* y escriba el nombre del sitio de sucursal.</span><span class="sxs-lookup"><span data-stu-id="db8b3-118">In the **Define New Branch Site** dialog box, click **Name**, and then type the name of the branch site.</span></span>

4.  <span data-ttu-id="db8b3-119">(Opcional) Haga clic en \*\*Descripción \*\* y escriba una descripción significativa para el sitio de sucursal.</span><span class="sxs-lookup"><span data-stu-id="db8b3-119">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>

5.  <span data-ttu-id="db8b3-120">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="db8b3-120">Click **Next**.</span></span>

6.  <span data-ttu-id="db8b3-121">(Opcional) En el siguiente cuadro de diálogo **Definir nuevo sitio de sucursal**, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="db8b3-121">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span>
    
    1.  <span data-ttu-id="db8b3-122">Haga clic en **Ciudad** y escriba el nombre de la ciudad en la se ubica el sitio de sucursal.</span><span class="sxs-lookup"><span data-stu-id="db8b3-122">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
    2.  <span data-ttu-id="db8b3-123">Haga clic en **Provincia o región** y escriba el nombre de la provincia o la región en la que se ubica el sitio de sucursal.</span><span class="sxs-lookup"><span data-stu-id="db8b3-123">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
    3.  <span data-ttu-id="db8b3-124">Haga clic en **código de país** y escriba el código telefónico de dos dígitos del país o la región en el que se ubica el sitio de sucursal.</span><span class="sxs-lookup"><span data-stu-id="db8b3-124">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>

7.  <span data-ttu-id="db8b3-125">Haga clic en **Siguiente** y, a continuación, siga uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="db8b3-125">Click **Next**, and then do one of the following:</span></span>
    
    1.  <span data-ttu-id="db8b3-p102">Si utiliza una aplicación o un servidor de sucursal con funciones de supervivencia de Lync 2010 en este sitio, no olvide desactivar la opción **Abrir el Asistente con nuevas funciones de supervivencia cuando se cierre el asistente**. Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="db8b3-p102">If you are using a Lync 2010 Survivable Branch Appliance or Server at this site, be sure to uncheck the **Open the New Survivable Wizard when this wizard closes** option. Click **Finish**.</span></span>

8.  <span data-ttu-id="db8b3-128">Para asociar el SBA heredado de Lync Server 2010 al grupo de servidores front-end de Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="db8b3-128">To associate the legacy Lync Server 2010 SBA to the Lync Server 2013 Front End pool:</span></span>
    
    1.  <span data-ttu-id="db8b3-129">Expanda el sitio de sucursal que ha creado.</span><span class="sxs-lookup"><span data-stu-id="db8b3-129">Expand the branch site that has been created.</span></span>
    
    2.  <span data-ttu-id="db8b3-130">Haga clic con el botón secundario en **Lync Server 2010** y, a continuación, en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="db8b3-130">Right click on **Lync Server 2010** and then click **New**.</span></span>
    
    3.  <span data-ttu-id="db8b3-131">Haga clic en **Aplicación de sucursal con funciones de supervivencia…**</span><span class="sxs-lookup"><span data-stu-id="db8b3-131">Click **Survivable Branch Appliance…**</span></span>

9.  <span data-ttu-id="db8b3-132">Siga las indicaciones del asistente que se abrirá.</span><span class="sxs-lookup"><span data-stu-id="db8b3-132">Follow the directions in the wizard that opens.</span></span> <span data-ttu-id="db8b3-133">Para obtener información sobre los elementos del asistente, consulte [definir una aplicación o un servidor de sucursal con funciones de supervivencia en Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span><span class="sxs-lookup"><span data-stu-id="db8b3-133">For information about wizard items, see [Define a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="db8b3-134">Una aplicación de sucursal con funciones de supervivencia de Lync Server 2010 solo se puede asociar a un almacén de supervisión de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="db8b3-134">A Lync Server 2010 Survivable Branch Appliance can only be associated with a Lync Server 2010 Monitoring Store.</span></span>

    
    </div>

10. <span data-ttu-id="db8b3-135">Si no usa una aplicación o un servidor de sucursal con funciones de supervivencia en este sitio, desactive la casilla **Abrir el Asistente con nuevas funciones de supervivencia cuando se cierre este asistente** y haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="db8b3-135">If you are not using a Survivable Branch Appliance or Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box, and then click **Finish**.</span></span>

11. <span data-ttu-id="db8b3-136">Repita los pasos anteriores para cada sitio de sucursal que desee agregar a la topología.</span><span class="sxs-lookup"><span data-stu-id="db8b3-136">Repeat the previous steps for each branch site you want to add to the topology.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

