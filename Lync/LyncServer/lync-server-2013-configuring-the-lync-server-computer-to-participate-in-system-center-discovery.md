---
title: Configuración del equipo de Lync Server para participar en la detección de System Center
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the Lync Server computer to participate in System Center discovery
ms:assetid: 2f9c9cb0-3120-4571-9cd2-657c2123fe21
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204776(v=OCS.15)
ms:contentKeyID: 48183731
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2b59622306fbde12eb570b72c95b37cec7885c7f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42040929"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-lync-server-2013-computer-to-participate-in-system-center-discovery"></a><span data-ttu-id="054e9-102">Configuración del equipo de Lync Server 2013 para participar en la detección de System Center</span><span class="sxs-lookup"><span data-stu-id="054e9-102">Configuring the Lync Server 2013 computer to participate in System Center discovery</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="054e9-103">_**Última modificación del tema:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="054e9-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="054e9-104">Para asegurarse de que el nuevo agente de Lync Server participa en el proceso de detección para System Center Operations Manager, debe completar el siguiente procedimiento en cada equipo en el que se haya instalado la consola de System Center Operations Manager:</span><span class="sxs-lookup"><span data-stu-id="054e9-104">To make sure that your new Lync Server agent participates in discovery process for System Center Operations Manager, you must complete the following procedure on each computer where the System Center Operations Manager console has been installed:</span></span>

1.  <span data-ttu-id="054e9-105">En la pestaña **Administración**, haga clic en **Agente administrado**.</span><span class="sxs-lookup"><span data-stu-id="054e9-105">On the **Administration** tab, click **Agent Managed**.</span></span>

2.  <span data-ttu-id="054e9-p101">Haga clic con el botón secundario en el nombre del equipo y, a continuación, haga clic en  **Propiedades**. En el cuadro de diálogo **Propiedades**, en la pestaña **Seguridad**, seleccione **Permitir a este agente que actúe como proxy ay detecte objetos administrados en otros equipos** y luego haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="054e9-p101">Right-click the name of the computer, and then click **Properties**. In the **Properties** dialog box, on the **Security** tab, select **Allow this agent to act as a proxy and discover managed objects on other computers**, and then click **OK**.</span></span>

<span data-ttu-id="054e9-p102">Luego de completar el paso 2, reinicie el servicio Agente de estado. (Reiniciar el servicio “obligará” a que se detecte la nueva máquina. Si no reinicia el servicio, podría demorar hasta 4 horas la detección de la nueva máquina por parte de System Center Operations Manager). Una vez que se haya reiniciado el servicio, verifique que no se registra ningún evento de error en el registro de eventos de Operations Manager en ese equipo.</span><span class="sxs-lookup"><span data-stu-id="054e9-p102">After completing step 2, reboot the Health Agent service. (Rebooting the service will “force” discovery of the new machine. If you do not reboot the service, it could take as long as 4 hours before the new machine is discovered by System Center Operations Manager.). After the service has rebooted, verify that no error events are being recorded in the Operations Manager event log on that computer.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

