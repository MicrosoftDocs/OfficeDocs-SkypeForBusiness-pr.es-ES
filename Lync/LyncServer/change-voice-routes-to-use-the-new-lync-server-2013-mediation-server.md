---
title: Cambiar las rutas de voz para usar el nuevo servidor de mediación de Lync Server 2013
description: Cambie las rutas de voz para usar el nuevo servidor de mediación de Lync Server 2013.
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
ms.openlocfilehash: ef58ba61512b5de31a74b79e554dbb3f94b67d99
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545746"
---
# <a name="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server"></a><span data-ttu-id="3573d-103">Cambiar las rutas de voz para usar el nuevo servidor de mediación de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3573d-103">Change voice routes to use the new Lync Server 2013 Mediation Server</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3573d-104">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="3573d-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="3573d-105">Con este procedimiento se cambian las rutas de voz para usar el servidor de mediación de Lync Server 2013, en lugar del servidor de mediación de Office Communications Server 2007 R2 heredado.</span><span class="sxs-lookup"><span data-stu-id="3573d-105">This procedure changes the voice routes to use the Lync Server 2013 Mediation Server, instead of the legacy Office Communications Server 2007 R2 Mediation Server.</span></span>

<div>

## <a name="to-change-the-voice-routes-to-use-the-new-mediation-server"></a><span data-ttu-id="3573d-106">Para cambiar las rutas de voz para usar el nuevo servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="3573d-106">To change the voice routes to use the new Mediation Server</span></span>

1.  <span data-ttu-id="3573d-107">Panel de control de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3573d-107">Lync Server 2013 Control Panel</span></span>

2.  <span data-ttu-id="3573d-108">En el panel izquierdo, seleccione **Enrutamiento de voz** y luego **Ruta**.</span><span class="sxs-lookup"><span data-stu-id="3573d-108">In the left pane, select **Voice Routing** and then **Route**.</span></span>

3.  <span data-ttu-id="3573d-109">Haga clic en **Nueva** para crear una nueva ruta de voz.</span><span class="sxs-lookup"><span data-stu-id="3573d-109">Click **New** to create a New Voice Route.</span></span>

4.  <span data-ttu-id="3573d-110">Rellene los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="3573d-110">Fill in the following fields:</span></span>
    
      - <span data-ttu-id="3573d-p101">**Nombre**: escriba un nombre descriptivo de la ruta de voz. En este documento usaremos **W14PSTNRoute**.</span><span class="sxs-lookup"><span data-stu-id="3573d-p101">**Name**: Type a descriptive name of the voice route. For this document we will use **W15PSTNRoute**.</span></span>
    
      - <span data-ttu-id="3573d-113">**Descripción**: escriba una breve descripción de la ruta de voz.</span><span class="sxs-lookup"><span data-stu-id="3573d-113">**Description**: Type a short description of the voice route.</span></span>

5.  <span data-ttu-id="3573d-p102">Omita todas las secciones restantes hasta llegar a **Puertas de enlace asociadas**. Haga clic en \*\*Agregar \*\*. Seleccione la nueva puerta de enlace predeterminada y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3573d-p102">Skip all remaining sections until you reach **Associated gateways**. Click **Add**. Select the new default gateway and click **OK**.</span></span>

6.  <span data-ttu-id="3573d-117">En **Usos de la RTC asociados**, haga clic en **Seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="3573d-117">Under **Associated PSTN Usages**, click **Select**.</span></span>

7.  <span data-ttu-id="3573d-118">En la página **Seleccionar registro de uso de RTC**, seleccione un nombre de registro y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3573d-118">From the **Select PSTN Usage Record** page, select a record name and then click **OK**.</span></span>

8.  <span data-ttu-id="3573d-119">En la página **Nueva ruta de voz**, haga clic en **Aceptar** para crear la ruta\*\*\*\* de voz.</span><span class="sxs-lookup"><span data-stu-id="3573d-119">From the **New Voice Route** page, click **OK** to create the **Voice Route**.</span></span>

9.  <span data-ttu-id="3573d-120">En la página **Enrutamiento de voz**, seleccione **Ruta**.</span><span class="sxs-lookup"><span data-stu-id="3573d-120">From the **Voice Routing** page, select **Route**.</span></span>

10. <span data-ttu-id="3573d-121">Mueva la ruta que acaba de crear al principio de la lista y seleccione **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="3573d-121">Move the newly created route to the top of the list and then select **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

