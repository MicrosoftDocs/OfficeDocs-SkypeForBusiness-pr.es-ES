---
title: Conexión de una aplicación de sucursal con funciones de supervivencia
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Connect a Survivable Branch Appliance
ms:assetid: fe3167e2-d1b1-4cd4-bf30-262e0e7d14e8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721948(v=OCS.15)
ms:contentKeyID: 49733886
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77382343fa7736c90ac208f8d13f81bc74969efa
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006526"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="connect-a-survivable-branch-appliance"></a><span data-ttu-id="95c96-102">Conexión de una aplicación de sucursal con funciones de supervivencia</span><span class="sxs-lookup"><span data-stu-id="95c96-102">Connect a Survivable Branch Appliance</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="95c96-103">_**Última modificación del tema:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="95c96-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="95c96-104">Cada aplicación de sucursal con funciones de supervivencia (SBA) está asociada a un grupo de servidores front-end que sirve como registrador de copias de seguridad para SBA.</span><span class="sxs-lookup"><span data-stu-id="95c96-104">Every Survivable Branch Appliance (SBA) is associated with a Front End pool which serves as a backup registrar for the SBA.</span></span> <span data-ttu-id="95c96-105">Cuando el grupo de servidores front-end se migra a Lync Server 2013, SBA debe estar desasociado del grupo de servidores front-end de Lync Server 2010 mientras se actualiza el grupo, una vez que el grupo se ha migrado a Lync Server 2013, la SBA se puede volver a asociar con el grupo de servidores front-end actualizado.</span><span class="sxs-lookup"><span data-stu-id="95c96-105">When the Front End pool is migrated to Lync Server 2013, the SBA must be disassociated from the Lync Server 2010 Front End pool while the pool is upgraded, Once the pool has been migrated to Lync Server 2013, the SBA can be re-associated with the upgraded Front End pool.</span></span> <span data-ttu-id="95c96-106">Esto implica eliminar la SBA de la topología de Lync Server 2010 heredada en el generador de topologías y, a continuación, agregar la SBA a la topología de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="95c96-106">This involves deleting the SBA from the legacy Lync Server 2010 topology in Topology Builder and then adding the SBA to the Lync Server 2013 topology.</span></span> <span data-ttu-id="95c96-107">Los usuarios hospedados en el servidor de Lync Server 2010 SBA deben moverse primero a otro grupo de servidores front-end antes de quitar SBA de la topología.</span><span class="sxs-lookup"><span data-stu-id="95c96-107">Users homed on the legacy Lync Server 2010 SBA must first be moved to another Front End pool before removing the SBA from the topology.</span></span> <span data-ttu-id="95c96-108">Una vez agregada SBA a la topología de Lync Server 2013, estos usuarios pueden volver a moverse a SBA.</span><span class="sxs-lookup"><span data-stu-id="95c96-108">Once the SBA is added to the Lync Server 2013 topology, those users can then be moved back to the SBA.</span></span> <span data-ttu-id="95c96-109">Estos pasos se sintetizan a continuación:</span><span class="sxs-lookup"><span data-stu-id="95c96-109">These steps are summarized below:</span></span>

1.  <span data-ttu-id="95c96-110">Mueva los usuarios de sucursal alojados en el servidor de Lync Server 2010 heredado a otro grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="95c96-110">Move branch users homed on the legacy SBA Lync Server 2010 to another Front End pool.</span></span>

2.  <span data-ttu-id="95c96-111">Quite SBA de la topología heredada de Lync Server 2010 para desconectar el grupo de servidores front-end existente como registrador de reserva.</span><span class="sxs-lookup"><span data-stu-id="95c96-111">Remove SBA from the legacy Lync Server 2010 topology to disconnect the existing Front End pool as a backup registrar.</span></span>

3.  <span data-ttu-id="95c96-112">Agregue SBA a la topología de Lync Server 2013 y configure este nuevo grupo de servidores front-end como registrador de reserva.</span><span class="sxs-lookup"><span data-stu-id="95c96-112">Add SBA to the Lync Server 2013 topology and configure this new Front End pool as the backup registrar.</span></span>

4.  <span data-ttu-id="95c96-113">Mueva los usuarios de sucursal al nuevo SBA de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="95c96-113">Move the branch users to the new Lync Server 2013 SBA.</span></span>

<span data-ttu-id="95c96-114">**Agregar un sitio de sucursal SBA de Lync Server 2010 a la topología**</span><span class="sxs-lookup"><span data-stu-id="95c96-114">**Add Lync Server 2010 SBA Branch Site to Your Topology**</span></span>

1.  <span data-ttu-id="95c96-115">Abrir **Generador de topologías**.</span><span class="sxs-lookup"><span data-stu-id="95c96-115">Open **Topology Builder**.</span></span>

2.  <span data-ttu-id="95c96-116">En el panel de la izquierda, hacer clic con el botón secundario en **Sitios de sucursal** y, a continuación, en **Nuevo sitio de sucursal**.</span><span class="sxs-lookup"><span data-stu-id="95c96-116">In the left pane right-click **Branch sites**, and then click **New Branch Site**.</span></span>

3.  <span data-ttu-id="95c96-117">En el cuadro de diálogo **Definir nuevo sitio de sucursal**, haga clic en \*\*Nombre \*\* y escriba el nombre del sitio de sucursal.</span><span class="sxs-lookup"><span data-stu-id="95c96-117">In the **Define New Branch Site** dialog box, click **Name**, and then type the name of the branch site.</span></span>

4.  <span data-ttu-id="95c96-118">(Opcional) Haga clic en \*\*Descripción \*\* y escriba una descripción significativa para el sitio de sucursal.</span><span class="sxs-lookup"><span data-stu-id="95c96-118">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>

5.  <span data-ttu-id="95c96-119">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="95c96-119">Click **Next**.</span></span>

6.  <span data-ttu-id="95c96-120">(Opcional) En el siguiente cuadro de diálogo **Definir nuevo sitio de sucursal**, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="95c96-120">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span>
    
    1.  <span data-ttu-id="95c96-121">Haga clic en **Ciudad** y escriba el nombre de la ciudad en la se ubica el sitio de sucursal.</span><span class="sxs-lookup"><span data-stu-id="95c96-121">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
    2.  <span data-ttu-id="95c96-122">Haga clic en **Provincia o región** y escriba el nombre de la provincia o la región en la que se ubica el sitio de sucursal.</span><span class="sxs-lookup"><span data-stu-id="95c96-122">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
    3.  <span data-ttu-id="95c96-123">Haga clic en **código de país** y escriba el código telefónico de dos dígitos del país o la región en el que se ubica el sitio de sucursal.</span><span class="sxs-lookup"><span data-stu-id="95c96-123">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>

7.  <span data-ttu-id="95c96-124">Haga clic en **Siguiente** y, a continuación, siga uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="95c96-124">Click **Next**, and then do one of the following:</span></span>
    
    1.  <span data-ttu-id="95c96-p102">Si utiliza una aplicación o un servidor de sucursal con funciones de supervivencia de Lync 2010 en este sitio, no olvide desactivar la opción **Abrir el Asistente con nuevas funciones de supervivencia cuando se cierre el asistente**. Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="95c96-p102">If you are using a Lync 2010 Survivable Branch Appliance or Server at this site, be sure to uncheck the **Open the New Survivable Wizard when this wizard closes** option. Click **Finish**.</span></span>

8.  <span data-ttu-id="95c96-127">Para asociar el SBA heredado de Lync Server 2010 al grupo de servidores front-end de Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="95c96-127">To associate the legacy Lync Server 2010 SBA to the Lync Server 2013 Front End pool:</span></span>
    
    1.  <span data-ttu-id="95c96-128">Expanda el sitio de sucursal que ha creado.</span><span class="sxs-lookup"><span data-stu-id="95c96-128">Expand the branch site that has been created.</span></span>
    
    2.  <span data-ttu-id="95c96-129">Haga clic con el botón secundario en **Lync Server 2010** y, a continuación, en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="95c96-129">Right click on **Lync Server 2010** and then click **New**.</span></span>
    
    3.  <span data-ttu-id="95c96-130">Haga clic en **Aplicación de sucursal con funciones de supervivencia…**</span><span class="sxs-lookup"><span data-stu-id="95c96-130">Click **Survivable Branch Appliance…**</span></span>

9.  <span data-ttu-id="95c96-131">Siga las indicaciones del asistente que se abrirá.</span><span class="sxs-lookup"><span data-stu-id="95c96-131">Follow the directions in the wizard that opens.</span></span> <span data-ttu-id="95c96-132">Para obtener información sobre los elementos del asistente, consulte [definir una aplicación o un servidor de sucursal con funciones de supervivencia en Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span><span class="sxs-lookup"><span data-stu-id="95c96-132">For information about wizard items, see [Define a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="95c96-133">Una aplicación de sucursal con funciones de supervivencia de Lync Server 2010 solo se puede asociar a un almacén de supervisión de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="95c96-133">A Lync Server 2010 Survivable Branch Appliance can only be associated with a Lync Server 2010 Monitoring Store.</span></span>

    
    </div>

10. <span data-ttu-id="95c96-134">Si no usa una aplicación o un servidor de sucursal con funciones de supervivencia en este sitio, desactive la casilla **Abrir el Asistente con nuevas funciones de supervivencia cuando se cierre este asistente** y haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="95c96-134">If you are not using a Survivable Branch Appliance or Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box, and then click **Finish**.</span></span>

11. <span data-ttu-id="95c96-135">Repita los pasos anteriores para cada sitio de sucursal que desee agregar a la topología.</span><span class="sxs-lookup"><span data-stu-id="95c96-135">Repeat the previous steps for each branch site you want to add to the topology.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

