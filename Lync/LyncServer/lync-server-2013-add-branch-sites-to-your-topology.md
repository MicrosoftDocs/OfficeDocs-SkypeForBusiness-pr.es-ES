---
title: 'Lync Server 2013: agregar sitios de sucursal a la topología'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add branch sites to your topology
ms:assetid: b9c35fb0-0081-4aeb-8f95-ac2fcc6c3335
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412905(v=OCS.15)
ms:contentKeyID: 48185216
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3d4e024ed5cdb29bb8a8a4170b89399f955254bf
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181393"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="add-branch-sites-to-your-topology-in-lync-server-2013"></a><span data-ttu-id="05b7a-102">Agregar sitios de sucursal a la topología en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="05b7a-102">Add branch sites to your topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="05b7a-103">_**Última modificación del tema:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="05b7a-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="05b7a-104">Los sitios de sucursal representan las sucursales físicas que están conectadas a las oficinas principales a través de un vínculo WAN.</span><span class="sxs-lookup"><span data-stu-id="05b7a-104">Branch sites represent physical branch offices that are connected to your main offices over a WAN link.</span></span> <span data-ttu-id="05b7a-105">Para agregar un sitio de sucursal a la topología de Lync, realice este procedimiento en el sitio central.</span><span class="sxs-lookup"><span data-stu-id="05b7a-105">To add a branch site to your Lync topology, perform this procedure at the central site.</span></span>

<div>

## <a name="to-add-branch-sites-to-your-topology"></a><span data-ttu-id="05b7a-106">Para agregar sitios de sucursal a la topología</span><span class="sxs-lookup"><span data-stu-id="05b7a-106">To add branch sites to your topology</span></span>

1.  <span data-ttu-id="05b7a-107">Haga clic sucesivamente en **Inicio**, **Todos los programas**, **Microsoft Lync Server** y **Lync Server Topology Builder**.</span><span class="sxs-lookup"><span data-stu-id="05b7a-107">Click **Start**, click **All Programs**, click **Microsoft Lync Server**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="05b7a-108">En el árbol de la consola, expanda el sitio central, haga clic con el botón secundario en **sitios de sucursal**y, a continuación, haga clic en **nuevo sitio de sucursal**.</span><span class="sxs-lookup"><span data-stu-id="05b7a-108">In the console tree, expand the central site, right-click **Branch Sites**, and then click **New Branch Site**.</span></span>

3.  <span data-ttu-id="05b7a-109">En el cuadro de diálogo **Definir nuevo sitio de sucursal**, haga clic en \*\*Nombre \*\* y escriba el nombre del sitio de sucursal.</span><span class="sxs-lookup"><span data-stu-id="05b7a-109">In the **Define New Branch Site** dialog box, click **Name**, and then type the name of the branch site.</span></span>

4.  <span data-ttu-id="05b7a-110">(Opcional) Haga clic en \*\*Descripción \*\* y escriba una descripción significativa para el sitio de sucursal.</span><span class="sxs-lookup"><span data-stu-id="05b7a-110">(Optional) Click **Description**, and then type a meaningful description for the branch site.</span></span>

5.  <span data-ttu-id="05b7a-111">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="05b7a-111">Click **Next**.</span></span>

6.  <span data-ttu-id="05b7a-112">(Opcional) En el siguiente cuadro de diálogo **Definir nuevo sitio de sucursal**, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="05b7a-112">(Optional) In the next **Define New Branch Site** dialog box, do any of the following:</span></span>
    
      - <span data-ttu-id="05b7a-113">Haga clic en **Ciudad** y escriba el nombre de la ciudad en la se ubica el sitio de sucursal.</span><span class="sxs-lookup"><span data-stu-id="05b7a-113">Click **City**, and then type the name of the city in which the branch site is located.</span></span>
    
      - <span data-ttu-id="05b7a-114">Haga clic en **Provincia o región** y escriba el nombre de la provincia o la región en la que se ubica el sitio de sucursal.</span><span class="sxs-lookup"><span data-stu-id="05b7a-114">Click **State/Region**, and then type the name of the state or region in which the branch site is located.</span></span>
    
      - <span data-ttu-id="05b7a-115">Haga clic en **código de país** y escriba el código telefónico de dos dígitos del país o la región en el que se ubica el sitio de sucursal.</span><span class="sxs-lookup"><span data-stu-id="05b7a-115">Click **Country Code**, and then type the two-digit calling code for the country/region in which the branch site is located.</span></span>

7.  <span data-ttu-id="05b7a-116">Haga clic en **Siguiente** y, a continuación, siga uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="05b7a-116">Click **Next**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="05b7a-117">Si está usando una aplicación o un servidor de sucursal con funciones de supervivencia en este sitio, asegúrese de que la casilla **abrir el nuevo asistente superviviente cuando se cierre este asistente** esté activada, haga clic en **Finalizar**y, a continuación, siga las instrucciones del asistente que se abre.</span><span class="sxs-lookup"><span data-stu-id="05b7a-117">If you are using a Survivable Branch Appliance or Server at this site, be sure that the **Open the New Survivable Wizard when this wizard closes** check box is selected, click **Finish**, and then follow the directions in the wizard that opens.</span></span> <span data-ttu-id="05b7a-118">Para obtener información sobre los elementos del asistente, consulte [definir una aplicación o un servidor de sucursal con funciones de supervivencia en Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span><span class="sxs-lookup"><span data-stu-id="05b7a-118">For information about wizard items, see [Define a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).</span></span>
    
      - <span data-ttu-id="05b7a-119">Si no usa una aplicación o un servidor de sucursal con funciones de supervivencia en este sitio, desactive la casilla **Abrir el Asistente con nuevas funciones de supervivencia cuando se cierre este asistente** y haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="05b7a-119">If you are not using a Survivable Branch Appliance or Server at this site, clear the **Open the New Survivable Wizard when this wizard closes** check box, and then click **Finish**.</span></span>

8.  <span data-ttu-id="05b7a-120">Repita los pasos anteriores para cada sitio de sucursal que desee agregar a la topología.</span><span class="sxs-lookup"><span data-stu-id="05b7a-120">Repeat the previous steps for each branch site that you want to add to the topology.</span></span>

<span data-ttu-id="05b7a-121">**Siguiente paso:**</span><span class="sxs-lookup"><span data-stu-id="05b7a-121">**Next step:**</span></span>

<span data-ttu-id="05b7a-122">Para las aplicaciones o servidores de sucursal con funciones de supervivencia: [definir una aplicación o un servidor de sucursal con funciones de supervivencia en Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)</span><span class="sxs-lookup"><span data-stu-id="05b7a-122">For Survivable Branch Appliances or Servers: [Define a Survivable Branch Appliance or Server in Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)</span></span>

<span data-ttu-id="05b7a-123">Para la conectividad con RTC no resistente: [defina una puerta de enlace RTC para un sitio de sucursal en Lync server 2013](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md), [Configure un tronco con omisión de medios en Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)o [Configure un tronco sin omisión de medios en Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)</span><span class="sxs-lookup"><span data-stu-id="05b7a-123">For non-resilient PSTN connectivity: [Define a PSTN gateway for a branch site in Lync Server 2013](lync-server-2013-define-a-pstn-gateway-for-a-branch-site.md), [Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md), or [Configure a trunk without media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

