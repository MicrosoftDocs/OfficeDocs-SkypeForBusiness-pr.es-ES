---
title: Cambiar las rutas de voz para usar el nuevo servidor de mediación de Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Change voice routes to use the new Lync Server 2013 Mediation Server
ms:assetid: acd487b3-377c-46bf-9f71-fe6152002664
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205162(v=OCS.15)
ms:contentKeyID: 48185069
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 40f9bed4262adcabdb23e5b5b85e7de43292d18b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727560"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server"></a><span data-ttu-id="227a8-102">Cambiar las rutas de voz para usar el nuevo servidor de mediación de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="227a8-102">Change voice routes to use the new Lync Server 2013 Mediation Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="227a8-103">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="227a8-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="227a8-104">En este procedimiento se cambian las rutas de voz para usar el servidor de mediación de Lync Server 2013, en lugar del servidor de mediación de Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="227a8-104">This procedure changes the voice routes to use the Lync Server 2013 Mediation Server, instead of the legacy Office Communications Server 2007 R2 Mediation Server.</span></span>

<div>

## <a name="to-change-the-voice-routes-to-use-the-new-mediation-server"></a><span data-ttu-id="227a8-105">Para cambiar las rutas de voz para usar el nuevo servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="227a8-105">To change the voice routes to use the new Mediation Server</span></span>

1.  <span data-ttu-id="227a8-106">Panel de control de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="227a8-106">Lync Server 2013 Control Panel</span></span>

2.  <span data-ttu-id="227a8-107">En el panel izquierdo, seleccione **enrutamiento de voz** y, a continuación, **enrutar**.</span><span class="sxs-lookup"><span data-stu-id="227a8-107">In the left pane, select **Voice Routing** and then **Route**.</span></span>

3.  <span data-ttu-id="227a8-108">Haga clic en **nuevo** para crear una nueva ruta de voz.</span><span class="sxs-lookup"><span data-stu-id="227a8-108">Click **New** to create a New Voice Route.</span></span>

4.  <span data-ttu-id="227a8-109">Rellene los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="227a8-109">Fill in the following fields:</span></span>
    
      - <span data-ttu-id="227a8-110">**Nombre**: escriba un nombre descriptivo para la ruta de voz.</span><span class="sxs-lookup"><span data-stu-id="227a8-110">**Name**: Type a descriptive name of the voice route.</span></span> <span data-ttu-id="227a8-111">Para este documento, usaremos **W15PSTNRoute**.</span><span class="sxs-lookup"><span data-stu-id="227a8-111">For this document we will use **W15PSTNRoute**.</span></span>
    
      - <span data-ttu-id="227a8-112">**Descripción**: escriba una breve descripción de la ruta de voz.</span><span class="sxs-lookup"><span data-stu-id="227a8-112">**Description**: Type a short description of the voice route.</span></span>

5.  <span data-ttu-id="227a8-113">Omita todas las secciones restantes hasta que llegue **a las puertas de enlace asociadas**.</span><span class="sxs-lookup"><span data-stu-id="227a8-113">Skip all remaining sections until you reach **Associated gateways**.</span></span> <span data-ttu-id="227a8-114">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="227a8-114">Click **Add**.</span></span> <span data-ttu-id="227a8-115">Seleccione la nueva puerta de enlace predeterminada y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="227a8-115">Select the new default gateway and click **OK**.</span></span>

6.  <span data-ttu-id="227a8-116">En **usos de RTC asociados**, haga clic en **seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="227a8-116">Under **Associated PSTN Usages**, click **Select**.</span></span>

7.  <span data-ttu-id="227a8-117">En la página **seleccionar registro de uso de RTC** , seleccione un nombre de registro y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="227a8-117">From the **Select PSTN Usage Record** page, select a record name and then click **OK**.</span></span>

8.  <span data-ttu-id="227a8-118">En la **nueva** página de la ruta de voz, haga clic en **Aceptar** para crear la **ruta de voz**.</span><span class="sxs-lookup"><span data-stu-id="227a8-118">From the **New Voice Route** page, click **OK** to create the **Voice Route**.</span></span>

9.  <span data-ttu-id="227a8-119">En la página de **enrutamiento de voz** , seleccione **enrutar**.</span><span class="sxs-lookup"><span data-stu-id="227a8-119">From the **Voice Routing** page, select **Route**.</span></span>

10. <span data-ttu-id="227a8-120">Mueva la ruta recién creada a la parte superior de la lista y, a continuación, seleccione **confirmar**.</span><span class="sxs-lookup"><span data-stu-id="227a8-120">Move the newly created route to the top of the list and then select **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

