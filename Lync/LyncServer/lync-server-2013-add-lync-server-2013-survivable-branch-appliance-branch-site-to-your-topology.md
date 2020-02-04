---
title: Agregar un sitio de sucursal de aplicación de sucursal con función de supervivencia de Lync Server 2013 a la topología
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
ms.openlocfilehash: b4fc2dd7426006d0c8f19b38b85ba778744fff2e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735020"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-lync-server-2013-survivable-branch-appliance-branch-site-to-your-topology"></a><span data-ttu-id="ce0ac-102">Agregar un sitio de sucursal de aplicación de sucursal con función de supervivencia de Lync Server 2013 a la topología</span><span class="sxs-lookup"><span data-stu-id="ce0ac-102">Add Lync Server 2013 Survivable Branch Appliance branch site to your topology</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ce0ac-103">_**Última modificación del tema:** 2012-10-07_</span><span class="sxs-lookup"><span data-stu-id="ce0ac-103">_**Topic Last Modified:** 2012-10-07_</span></span>

<span data-ttu-id="ce0ac-104">Los equipos de la sucursal de Microsoft Lync Server 2013 (SBA) no se pueden asociar a un grupo front-end de Microsoft Lync Server 2010 como registrador de copias de seguridad.</span><span class="sxs-lookup"><span data-stu-id="ce0ac-104">Microsoft Lync Server 2013 Survivable Branch Appliances (SBA) cannot be associated to a Microsoft Lync Server 2010 Front End pool as a backup Registrar.</span></span> <span data-ttu-id="ce0ac-105">SBA debe estar asociado a un grupo front end de Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ce0ac-105">The SBA must be associated with a Microsoft Lync Server 2013 Front End pool.</span></span> <span data-ttu-id="ce0ac-106">En estos pasos se supone que se 2013 SBA de Microsoft Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ce0ac-106">These steps assume a Microsoft Lync Server 2013 SBA.</span></span> <span data-ttu-id="ce0ac-107">Realice este procedimiento en el sitio central.</span><span class="sxs-lookup"><span data-stu-id="ce0ac-107">Perform this procedure at the central site.</span></span>

<div>

## <a name="to-add-branch-sites-with-microsoft-lync-server-2013-sba-to-your-topology"></a><span data-ttu-id="ce0ac-108">Para agregar sitios de sucursales con Microsoft Lync Server 2013 SBA a su topología</span><span class="sxs-lookup"><span data-stu-id="ce0ac-108">To add branch sites with Microsoft Lync Server 2013 SBA to your topology</span></span>

1.  <span data-ttu-id="ce0ac-109">Iniciar generador de topología: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topología de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="ce0ac-109">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="ce0ac-110">En el árbol de consola, expanda el sitio central, expanda **sitios de sucursal**y, a continuación, haga clic en **nuevo sitio de sucursal**.</span><span class="sxs-lookup"><span data-stu-id="ce0ac-110">In the console tree, expand the central site, expand **Branch Sites**, and then click **New Branch Site**.</span></span>

3.  <span data-ttu-id="ce0ac-111">En el cuadro de diálogo **definir nuevo sitio de sucursal** , haga clic en **nombre**y, a continuación, escriba un nombre para el nuevo sitio de la sucursal.</span><span class="sxs-lookup"><span data-stu-id="ce0ac-111">In the **Define New Branch Site** dialog box, click **Name**, and then type a name for the new branch site.</span></span>

4.  <span data-ttu-id="ce0ac-112">Faculta Haga clic en **Descripción**y, a continuación, escriba una descripción para el sitio de la sucursal.</span><span class="sxs-lookup"><span data-stu-id="ce0ac-112">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>

5.  <span data-ttu-id="ce0ac-113">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="ce0ac-113">Click **Next**.</span></span>

6.  <span data-ttu-id="ce0ac-114">Faculta En el cuadro de diálogo **definir siguiente sitio de sucursal** , realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="ce0ac-114">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span>
    
      - <span data-ttu-id="ce0ac-115">Haga clic en **ciudad**y, a continuación, escriba el nombre de la ciudad en la que se encuentra el sitio de la sucursal.</span><span class="sxs-lookup"><span data-stu-id="ce0ac-115">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
      - <span data-ttu-id="ce0ac-116">Haga clic en **Estado o región**y, a continuación, escriba el nombre del estado o la región en la que se encuentra el sitio de la sucursal.</span><span class="sxs-lookup"><span data-stu-id="ce0ac-116">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
      - <span data-ttu-id="ce0ac-117">Haga clic en **prefijo internacional**y escriba el código de la llamada de dos dígitos para el país o la región en la que se encuentra el sitio de la sucursal.</span><span class="sxs-lookup"><span data-stu-id="ce0ac-117">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>

7.  <span data-ttu-id="ce0ac-118">Haga clic en **siguiente**y, a continuación, siga uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="ce0ac-118">Click **Next**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="ce0ac-119">Si está usando una aplicación de sucursal o un servidor de sucursal con la supervivencia, asegúrese de que esté activada la casilla **abrir el nuevo asistente superviviente cuando se cierre este asistente** .</span><span class="sxs-lookup"><span data-stu-id="ce0ac-119">If you are using a Survivable Branch Appliance or Survivable Branch Server at this site, be sure that the **Open the New Survivable Wizard when this wizard closes** check box is selected.</span></span>
    
      - <span data-ttu-id="ce0ac-120">Si no usa una aplicación de sucursal o un servidor de sucursal que sea revivientes en este sitio, desactive la casilla **abrir el nuevo asistente superviviente cuando se cierre este asistente** .</span><span class="sxs-lookup"><span data-stu-id="ce0ac-120">If you are not using a Survivable Branch Appliance or Survivable Branch Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box.</span></span>
    
      - <span data-ttu-id="ce0ac-121">Haga clic en **Finalizar**y, a continuación, siga las instrucciones del asistente que se abre.</span><span class="sxs-lookup"><span data-stu-id="ce0ac-121">Click **Finish**, and then follow the directions in the wizard that opens.</span></span> <span data-ttu-id="ce0ac-122">Para obtener información sobre los elementos del asistente, consulte [definir un dispositivo o servidor de sucursal con la que sea reviviente en Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span><span class="sxs-lookup"><span data-stu-id="ce0ac-122">For information about wizard items, see [Define a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span></span>

8.  <span data-ttu-id="ce0ac-123">Repita los pasos anteriores para cada sitio de sucursal que desee agregar a la topología.</span><span class="sxs-lookup"><span data-stu-id="ce0ac-123">Repeat the previous steps for each branch site that you want to add to the topology.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ce0ac-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="ce0ac-124">See Also</span></span>


[<span data-ttu-id="ce0ac-125">Definir un servidor o aplicación de sucursal con funciones de supervivencia en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ce0ac-125">Define a Survivable Branch Appliance or Server in Lync Server 2013</span></span>](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)  
[<span data-ttu-id="ce0ac-126">Definir una puerta de enlace RTC para un sitio de sucursal en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ce0ac-126">Define a PSTN gateway for a branch site in Lync Server 2013</span></span>](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md)  
[<span data-ttu-id="ce0ac-127">Configure a trunk with media bypass in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ce0ac-127">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[<span data-ttu-id="ce0ac-128">Configurar un tronco sin omisión de medios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ce0ac-128">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

