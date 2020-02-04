---
title: Conectar una aplicación de sucursal con funciones de supervivencia
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
ms.openlocfilehash: 5ef6294deba25998c5ad16254e464b6f682fa660
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723180"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="connect-a-survivable-branch-appliance"></a><span data-ttu-id="4a31a-102">Conectar una aplicación de sucursal con funciones de supervivencia</span><span class="sxs-lookup"><span data-stu-id="4a31a-102">Connect a Survivable Branch Appliance</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4a31a-103">_**Última modificación del tema:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="4a31a-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="4a31a-104">Cada dispositivo de sucursal con supervivencia (SBA) está asociado con un grupo de servidores front-end que sirve como registrador de copias de seguridad de la SBA.</span><span class="sxs-lookup"><span data-stu-id="4a31a-104">Every Survivable Branch Appliance (SBA) is associated with a Front End pool which serves as a backup registrar for the SBA.</span></span> <span data-ttu-id="4a31a-105">Cuando el grupo de servidores front-end se migra a Lync Server 2013, SBA debe desasociarse del grupo de servidores front-end de Lync Server 2010 mientras se actualiza el grupo, una vez que el grupo se ha migrado a Lync Server 2013, la SBA se puede volver a asociar con el grupo de servidores front-end actualizado.</span><span class="sxs-lookup"><span data-stu-id="4a31a-105">When the Front End pool is migrated to Lync Server 2013, the SBA must be disassociated from the Lync Server 2010 Front End pool while the pool is upgraded, Once the pool has been migrated to Lync Server 2013, the SBA can be re-associated with the upgraded Front End pool.</span></span> <span data-ttu-id="4a31a-106">Esto implica eliminar SBA de la topología heredada de Lync Server 2010 en el generador de topología y, a continuación, agregar SBA a la topología de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4a31a-106">This involves deleting the SBA from the legacy Lync Server 2010 topology in Topology Builder and then adding the SBA to the Lync Server 2013 topology.</span></span> <span data-ttu-id="4a31a-107">Los usuarios alojados en el antiguo Lync Server 2010 SBA deben moverse primero a otro grupo de servidores front end antes de quitar SBA de la topología.</span><span class="sxs-lookup"><span data-stu-id="4a31a-107">Users homed on the legacy Lync Server 2010 SBA must first be moved to another Front End pool before removing the SBA from the topology.</span></span> <span data-ttu-id="4a31a-108">Una vez agregada SBA a la topología de Lync Server 2013, esos usuarios podrán volver a la SBA.</span><span class="sxs-lookup"><span data-stu-id="4a31a-108">Once the SBA is added to the Lync Server 2013 topology, those users can then be moved back to the SBA.</span></span> <span data-ttu-id="4a31a-109">Estos pasos se resumen a continuación:</span><span class="sxs-lookup"><span data-stu-id="4a31a-109">These steps are summarized below:</span></span>

1.  <span data-ttu-id="4a31a-110">Mueva los usuarios alojados en el servidor de Lync existente de SBA de 2010 a otro grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="4a31a-110">Move branch users homed on the legacy SBA Lync Server 2010 to another Front End pool.</span></span>

2.  <span data-ttu-id="4a31a-111">Quite SBA de la topología heredada de Lync Server 2010 para desconectar el grupo de servidores front-end existente como registrador de copias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="4a31a-111">Remove SBA from the legacy Lync Server 2010 topology to disconnect the existing Front End pool as a backup registrar.</span></span>

3.  <span data-ttu-id="4a31a-112">Agregue SBA a la topología de Lync Server 2013 y configúrela como registrador de la copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="4a31a-112">Add SBA to the Lync Server 2013 topology and configure this new Front End pool as the backup registrar.</span></span>

4.  <span data-ttu-id="4a31a-113">Mueva los usuarios de la sucursal al nuevo Lync Server 2013 SBA.</span><span class="sxs-lookup"><span data-stu-id="4a31a-113">Move the branch users to the new Lync Server 2013 SBA.</span></span>

<span data-ttu-id="4a31a-114">**Agregar el sitio de la sucursal de SBA de Lync Server 2010 a su topología**</span><span class="sxs-lookup"><span data-stu-id="4a31a-114">**Add Lync Server 2010 SBA Branch Site to Your Topology**</span></span>

1.  <span data-ttu-id="4a31a-115">Abra el **generador de topologías**.</span><span class="sxs-lookup"><span data-stu-id="4a31a-115">Open **Topology Builder**.</span></span>

2.  <span data-ttu-id="4a31a-116">En el panel izquierdo, haga clic con el botón secundario en **sitios de sucursales**y luego haga clic en **nuevo sitio de rama**.</span><span class="sxs-lookup"><span data-stu-id="4a31a-116">In the left pane right-click **Branch sites**, and then click **New Branch Site**.</span></span>

3.  <span data-ttu-id="4a31a-117">En el cuadro de diálogo **definir nuevo sitio de sucursal** , haga clic en **nombre**y, a continuación, escriba el nombre del sitio de la sucursal.</span><span class="sxs-lookup"><span data-stu-id="4a31a-117">In the **Define New Branch Site** dialog box, click **Name**, and then type the name of the branch site.</span></span>

4.  <span data-ttu-id="4a31a-118">Faculta Haga clic en **Descripción**y, a continuación, escriba una descripción para el sitio de la sucursal.</span><span class="sxs-lookup"><span data-stu-id="4a31a-118">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>

5.  <span data-ttu-id="4a31a-119">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="4a31a-119">Click **Next**.</span></span>

6.  <span data-ttu-id="4a31a-120">Faculta En el cuadro de diálogo **definir siguiente sitio de sucursal** , realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="4a31a-120">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span>
    
    1.  <span data-ttu-id="4a31a-121">Haga clic en **ciudad**y, a continuación, escriba el nombre de la ciudad en la que se encuentra el sitio de la sucursal.</span><span class="sxs-lookup"><span data-stu-id="4a31a-121">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
    2.  <span data-ttu-id="4a31a-122">Haga clic en **Estado o región**y, a continuación, escriba el nombre del estado o la región en la que se encuentra el sitio de la sucursal.</span><span class="sxs-lookup"><span data-stu-id="4a31a-122">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
    3.  <span data-ttu-id="4a31a-123">Haga clic en **prefijo internacional**y escriba el código de la llamada de dos dígitos para el país o la región en la que se encuentra el sitio de la sucursal.</span><span class="sxs-lookup"><span data-stu-id="4a31a-123">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>

7.  <span data-ttu-id="4a31a-124">Haga clic en **siguiente**y, a continuación, siga uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="4a31a-124">Click **Next**, and then do one of the following:</span></span>
    
    1.  <span data-ttu-id="4a31a-125">Si está usando un equipo o servidor de una sucursal de Lync 2010, asegúrese de desactivar la opción **abrir el nuevo asistente superviviente cuando se cierre este asistente** .</span><span class="sxs-lookup"><span data-stu-id="4a31a-125">If you are using a Lync 2010 Survivable Branch Appliance or Server at this site, be sure to uncheck the **Open the New Survivable Wizard when this wizard closes** option.</span></span> <span data-ttu-id="4a31a-126">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="4a31a-126">Click **Finish**.</span></span>

8.  <span data-ttu-id="4a31a-127">Para asociar el servidor de Lync Server 2010 SBA al grupo front-end de Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="4a31a-127">To associate the legacy Lync Server 2010 SBA to the Lync Server 2013 Front End pool:</span></span>
    
    1.  <span data-ttu-id="4a31a-128">Expanda el sitio de la sucursal que ha creado.</span><span class="sxs-lookup"><span data-stu-id="4a31a-128">Expand the branch site that has been created.</span></span>
    
    2.  <span data-ttu-id="4a31a-129">Haga clic con el botón secundario en **Lync Server 2010** y, a continuación, haga clic en **nuevo**.</span><span class="sxs-lookup"><span data-stu-id="4a31a-129">Right click on **Lync Server 2010** and then click **New**.</span></span>
    
    3.  <span data-ttu-id="4a31a-130">Haga clic en **equipo de rama superviviente...**</span><span class="sxs-lookup"><span data-stu-id="4a31a-130">Click **Survivable Branch Appliance…**</span></span>

9.  <span data-ttu-id="4a31a-131">Siga las instrucciones del asistente que se abre.</span><span class="sxs-lookup"><span data-stu-id="4a31a-131">Follow the directions in the wizard that opens.</span></span> <span data-ttu-id="4a31a-132">Para obtener información sobre los elementos del asistente, consulte [definir un dispositivo o servidor de sucursal con la que sea reviviente en Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span><span class="sxs-lookup"><span data-stu-id="4a31a-132">For information about wizard items, see [Define a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4a31a-133">Un dispositivo de sucursal 2010 de Lync Server solo se puede asociar con un almacén de supervisión de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="4a31a-133">A Lync Server 2010 Survivable Branch Appliance can only be associated with a Lync Server 2010 Monitoring Store.</span></span>

    
    </div>

10. <span data-ttu-id="4a31a-134">Si no usa un equipo o servidor de sucursal con la supervivencia en este sitio, desactive la casilla **abrir el nuevo asistente superviviente cuando se cierre este asistente** y, a continuación, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="4a31a-134">If you are not using a Survivable Branch Appliance or Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box, and then click **Finish**.</span></span>

11. <span data-ttu-id="4a31a-135">Repita los pasos anteriores para cada sitio de sucursal que desee agregar a la topología.</span><span class="sxs-lookup"><span data-stu-id="4a31a-135">Repeat the previous steps for each branch site you want to add to the topology.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

