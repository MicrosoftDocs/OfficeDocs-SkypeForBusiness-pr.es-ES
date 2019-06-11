---
title: Configurar el equipo de Lync Server para que participe en la detección de System Center
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring the Lync Server computer to participate in System Center discovery
ms:assetid: 2f9c9cb0-3120-4571-9cd2-657c2123fe21
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204776(v=OCS.15)
ms:contentKeyID: 48183731
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e4b50fad3e0d197259847db9a94bf9e64618d7e2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842171"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-lync-server-2013-computer-to-participate-in-system-center-discovery"></a><span data-ttu-id="6815e-102">Configurar el equipo de Lync Server 2013 para que participe en la detección de System Center</span><span class="sxs-lookup"><span data-stu-id="6815e-102">Configuring the Lync Server 2013 computer to participate in System Center discovery</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6815e-103">_**Última modificación del tema:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="6815e-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="6815e-104">Para asegurarse de que el nuevo agente de Lync Server participa en el proceso de detección de System Center Operations Manager, debe completar el siguiente procedimiento en cada equipo en el que se haya instalado la consola de System Center Operations Manager:</span><span class="sxs-lookup"><span data-stu-id="6815e-104">To make sure that your new Lync Server agent participates in discovery process for System Center Operations Manager, you must complete the following procedure on each computer where the System Center Operations Manager console has been installed:</span></span>

1.  <span data-ttu-id="6815e-105">En la pestaña **Administración** , haga clic en **agente administrado**.</span><span class="sxs-lookup"><span data-stu-id="6815e-105">On the **Administration** tab, click **Agent Managed**.</span></span>

2.  <span data-ttu-id="6815e-106">Haga clic con el botón secundario en el nombre del equipo y, a continuación, haga clic en **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="6815e-106">Right-click the name of the computer, and then click **Properties**.</span></span> <span data-ttu-id="6815e-107">En el cuadro de diálogo **propiedades** , en la pestaña **seguridad** , seleccione **permitir que este agente actúe como proxy y descubrir objetos administrados en otros equipos**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6815e-107">In the **Properties** dialog box, on the **Security** tab, select **Allow this agent to act as a proxy and discover managed objects on other computers**, and then click **OK**.</span></span>

<span data-ttu-id="6815e-108">Después de completar el paso 2, reinicie el servicio del agente de estado.</span><span class="sxs-lookup"><span data-stu-id="6815e-108">After completing step 2, reboot the Health Agent service.</span></span> <span data-ttu-id="6815e-109">(Si reinicia el servicio, "forzará" el descubrimiento de la nueva máquina.</span><span class="sxs-lookup"><span data-stu-id="6815e-109">(Rebooting the service will “force” discovery of the new machine.</span></span> <span data-ttu-id="6815e-110">Si no reinicia el servicio, puede demorar hasta 4 horas antes de que System Center Operations Manager Descubra la nueva máquina.).</span><span class="sxs-lookup"><span data-stu-id="6815e-110">If you do not reboot the service, it could take as long as 4 hours before the new machine is discovered by System Center Operations Manager.).</span></span> <span data-ttu-id="6815e-111">Después de que el servicio se haya reiniciado, compruebe que no se graban eventos de error en el registro de eventos de Operations Manager de ese equipo.</span><span class="sxs-lookup"><span data-stu-id="6815e-111">After the service has rebooted, verify that no error events are being recorded in the Operations Manager event log on that computer.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

