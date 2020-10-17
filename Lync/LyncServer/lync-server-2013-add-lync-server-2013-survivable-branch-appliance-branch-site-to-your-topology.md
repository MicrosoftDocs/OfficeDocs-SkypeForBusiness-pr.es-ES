---
title: Agregar un sitio de sucursal de aplicación de sucursal con funciones de supervivencia de Lync Server 2013 a la topología
description: Agregue el sitio de sucursal de aplicación de sucursal con funciones de supervivencia de Lync Server 2013 a su topología.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add Lync Server 2013 Survivable Branch Appliance branch site to your topology
ms:assetid: d3142a37-4606-456d-8ea9-6cc0e51e55f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721896(v=OCS.15)
ms:contentKeyID: 49733830
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1b50c03dd53c7637fcf0914db290b3e452b64b83
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572036"
---
# <a name="add-lync-server-2013-survivable-branch-appliance-branch-site-to-your-topology"></a><span data-ttu-id="b31a6-103">Agregar un sitio de sucursal de aplicación de sucursal con funciones de supervivencia de Lync Server 2013 a la topología</span><span class="sxs-lookup"><span data-stu-id="b31a6-103">Add Lync Server 2013 Survivable Branch Appliance branch site to your topology</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b31a6-104">_**Última modificación del tema:** 2012-10-07_</span><span class="sxs-lookup"><span data-stu-id="b31a6-104">_**Topic Last Modified:** 2012-10-07_</span></span>

<span data-ttu-id="b31a6-105">Microsoft Lync Server 2013 las aplicaciones de sucursal con funciones de supervivencia (SBA) no se pueden asociar a un grupo de servidores front-end de Microsoft Lync Server 2010 como registrador de reserva.</span><span class="sxs-lookup"><span data-stu-id="b31a6-105">Microsoft Lync Server 2013 Survivable Branch Appliances (SBA) cannot be associated to a Microsoft Lync Server 2010 Front End pool as a backup Registrar.</span></span> <span data-ttu-id="b31a6-106">SBA debe estar asociado a un grupo de servidores front-end 2013 de Microsoft Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b31a6-106">The SBA must be associated with a Microsoft Lync Server 2013 Front End pool.</span></span> <span data-ttu-id="b31a6-107">En estos pasos se presupone que es un servidor de Microsoft Lync Server 2013 SBA.</span><span class="sxs-lookup"><span data-stu-id="b31a6-107">These steps assume a Microsoft Lync Server 2013 SBA.</span></span> <span data-ttu-id="b31a6-108">Realice este procedimiento en el sitio central.</span><span class="sxs-lookup"><span data-stu-id="b31a6-108">Perform this procedure at the central site.</span></span>

<div>

## <a name="to-add-branch-sites-with-microsoft-lync-server-2013-sba-to-your-topology"></a><span data-ttu-id="b31a6-109">Para agregar sitios de sucursal con SBA de Microsoft Lync Server 2013 a su topología</span><span class="sxs-lookup"><span data-stu-id="b31a6-109">To add branch sites with Microsoft Lync Server 2013 SBA to your topology</span></span>

1.  <span data-ttu-id="b31a6-110">Inicie el generador de topologías: haga clic en **Inicio**, haga clic en **todos los programas**, haga clic en **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topologías de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="b31a6-110">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="b31a6-111">En el árbol de consola, expanda sucesivamente el sitio central y los **Sitios de sucursal** y luego haga clic en **Nuevo sitio de sucursal**.</span><span class="sxs-lookup"><span data-stu-id="b31a6-111">In the console tree, expand the central site, expand **Branch Sites**, and then click **New Branch Site**.</span></span>

3.  <span data-ttu-id="b31a6-112">En el cuadro de diálogo **Definir nuevo sitio de sucursal**, haga clic en **Nombre** y escriba un nombre para el sitio de sucursal nuevo.</span><span class="sxs-lookup"><span data-stu-id="b31a6-112">In the **Define New Branch Site** dialog box, click **Name**, and then type a name for the new branch site.</span></span>

4.  <span data-ttu-id="b31a6-113">(Opcional) Haga clic en **Descripción** y escriba una descripción significativa para el sitio de sucursal.</span><span class="sxs-lookup"><span data-stu-id="b31a6-113">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>

5.  <span data-ttu-id="b31a6-114">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="b31a6-114">Click **Next**.</span></span>

6.  <span data-ttu-id="b31a6-115">(Opcional) En el siguiente cuadro de diálogo **Definir nuevo sitio de sucursal**, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="b31a6-115">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span>
    
      - <span data-ttu-id="b31a6-116">Haga clic en **Ciudad** y escriba el nombre de la ciudad en la se ubica el sitio de sucursal.</span><span class="sxs-lookup"><span data-stu-id="b31a6-116">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
      - <span data-ttu-id="b31a6-117">Haga clic en **Provincia o región** y escriba el nombre de la provincia o la región en la que se ubica el sitio de sucursal.</span><span class="sxs-lookup"><span data-stu-id="b31a6-117">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
      - <span data-ttu-id="b31a6-118">Haga clic en **código de país** y escriba el código telefónico de dos dígitos del país o la región en el que se ubica el sitio de sucursal.</span><span class="sxs-lookup"><span data-stu-id="b31a6-118">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>

7.  <span data-ttu-id="b31a6-119">Haga clic en **Siguiente** y, a continuación, siga uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="b31a6-119">Click **Next**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="b31a6-120">Si está usando una aplicación de sucursal con funciones de supervivencia o un servidor de sucursal con funciones de supervivencia en este sitio, asegúrese de que esté activada la casilla **abrir el nuevo asistente superviviente cuando se cierre este asistente** .</span><span class="sxs-lookup"><span data-stu-id="b31a6-120">If you are using a Survivable Branch Appliance or Survivable Branch Server at this site, be sure that the **Open the New Survivable Wizard when this wizard closes** check box is selected.</span></span>
    
      - <span data-ttu-id="b31a6-121">Si no está usando una aplicación de sucursal con funciones de supervivencia o un servidor de sucursal con funciones de supervivencia en este sitio, desactive la casilla **abrir el nuevo asistente superviviente cuando se cierre este asistente** .</span><span class="sxs-lookup"><span data-stu-id="b31a6-121">If you are not using a Survivable Branch Appliance or Survivable Branch Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box.</span></span>
    
      - <span data-ttu-id="b31a6-122">Haga clic en **Finalizar** y siga las instrucciones del asistente que se abre.</span><span class="sxs-lookup"><span data-stu-id="b31a6-122">Click **Finish**, and then follow the directions in the wizard that opens.</span></span> <span data-ttu-id="b31a6-123">Para obtener información sobre los elementos del asistente, consulte [definir una aplicación o un servidor de sucursal con funciones de supervivencia en Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span><span class="sxs-lookup"><span data-stu-id="b31a6-123">For information about wizard items, see [Define a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span></span>

8.  <span data-ttu-id="b31a6-124">Repita los pasos anteriores para cada sitio de sucursal que desee agregar a la topología.</span><span class="sxs-lookup"><span data-stu-id="b31a6-124">Repeat the previous steps for each branch site that you want to add to the topology.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b31a6-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b31a6-125">See Also</span></span>


[<span data-ttu-id="b31a6-126">Definir una aplicación o un servidor de sucursal con funciones de supervivencia en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b31a6-126">Define a Survivable Branch Appliance or Server in Lync Server 2013</span></span>](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)  
[<span data-ttu-id="b31a6-127">Definir una puerta de enlace RTC para un sitio de sucursal en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b31a6-127">Define a PSTN gateway for a branch site in Lync Server 2013</span></span>](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md)  
[<span data-ttu-id="b31a6-128">Configurar un tronco con la omisión de medios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b31a6-128">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[<span data-ttu-id="b31a6-129">Configurar un tronco sin omisión de medios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b31a6-129">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

