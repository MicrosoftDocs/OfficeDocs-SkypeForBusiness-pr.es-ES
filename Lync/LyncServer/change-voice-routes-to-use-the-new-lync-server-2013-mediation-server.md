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
ms.openlocfilehash: c8edaf6c8d912e9784a0a3df6dfe27a45aa873e7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "42003215"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server"></a><span data-ttu-id="f7fc3-102">Cambiar las rutas de voz para usar el nuevo servidor de mediación de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f7fc3-102">Change voice routes to use the new Lync Server 2013 Mediation Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f7fc3-103">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="f7fc3-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="f7fc3-104">Con este procedimiento se cambian las rutas de voz para usar el servidor de mediación de Lync Server 2013, en lugar del servidor de mediación de Office Communications Server 2007 R2 heredado.</span><span class="sxs-lookup"><span data-stu-id="f7fc3-104">This procedure changes the voice routes to use the Lync Server 2013 Mediation Server, instead of the legacy Office Communications Server 2007 R2 Mediation Server.</span></span>

<div>

## <a name="to-change-the-voice-routes-to-use-the-new-mediation-server"></a><span data-ttu-id="f7fc3-105">Para cambiar las rutas de voz para usar el nuevo servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="f7fc3-105">To change the voice routes to use the new Mediation Server</span></span>

1.  <span data-ttu-id="f7fc3-106">Panel de control de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f7fc3-106">Lync Server 2013 Control Panel</span></span>

2.  <span data-ttu-id="f7fc3-107">En el panel izquierdo, seleccione **Enrutamiento de voz** y luego **Ruta**.</span><span class="sxs-lookup"><span data-stu-id="f7fc3-107">In the left pane, select **Voice Routing** and then **Route**.</span></span>

3.  <span data-ttu-id="f7fc3-108">Haga clic en **Nueva** para crear una nueva ruta de voz.</span><span class="sxs-lookup"><span data-stu-id="f7fc3-108">Click **New** to create a New Voice Route.</span></span>

4.  <span data-ttu-id="f7fc3-109">Rellene los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="f7fc3-109">Fill in the following fields:</span></span>
    
      - <span data-ttu-id="f7fc3-p101">**Nombre**: escriba un nombre descriptivo de la ruta de voz. En este documento usaremos **W14PSTNRoute**.</span><span class="sxs-lookup"><span data-stu-id="f7fc3-p101">**Name**: Type a descriptive name of the voice route. For this document we will use **W15PSTNRoute**.</span></span>
    
      - <span data-ttu-id="f7fc3-112">**Descripción**: escriba una breve descripción de la ruta de voz.</span><span class="sxs-lookup"><span data-stu-id="f7fc3-112">**Description**: Type a short description of the voice route.</span></span>

5.  <span data-ttu-id="f7fc3-p102">Omita todas las secciones restantes hasta llegar a **Puertas de enlace asociadas**. Haga clic en \*\*Agregar \*\*. Seleccione la nueva puerta de enlace predeterminada y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f7fc3-p102">Skip all remaining sections until you reach **Associated gateways**. Click **Add**. Select the new default gateway and click **OK**.</span></span>

6.  <span data-ttu-id="f7fc3-116">En **Usos de la RTC asociados**, haga clic en **Seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="f7fc3-116">Under **Associated PSTN Usages**, click **Select**.</span></span>

7.  <span data-ttu-id="f7fc3-117">En la página **Seleccionar registro de uso de RTC**, seleccione un nombre de registro y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f7fc3-117">From the **Select PSTN Usage Record** page, select a record name and then click **OK**.</span></span>

8.  <span data-ttu-id="f7fc3-118">En la página **Nueva ruta de voz**, haga clic en **Aceptar** para crear la ruta\*\*\*\* de voz.</span><span class="sxs-lookup"><span data-stu-id="f7fc3-118">From the **New Voice Route** page, click **OK** to create the **Voice Route**.</span></span>

9.  <span data-ttu-id="f7fc3-119">En la página **Enrutamiento de voz**, seleccione **Ruta**.</span><span class="sxs-lookup"><span data-stu-id="f7fc3-119">From the **Voice Routing** page, select **Route**.</span></span>

10. <span data-ttu-id="f7fc3-120">Mueva la ruta que acaba de crear al principio de la lista y seleccione **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="f7fc3-120">Move the newly created route to the top of the list and then select **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

