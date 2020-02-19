---
title: Configuración de un nodo de monitor para participar en la detección de System Center
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a watcher node to participate in System Center discovery
ms:assetid: 15c5dcfd-603b-47ea-af1b-8714c2ec08af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204704(v=OCS.15)
ms:contentKeyID: 48183500
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9b0d1fe5f2865f5c8797b2018ab8493bfb4d830c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42133763"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-in-lync-server-2013-to-participate-in-system-center-discovery"></a><span data-ttu-id="8c457-102">Configuración de un nodo de monitor en Lync Server 2013 para participar en la detección de System Center</span><span class="sxs-lookup"><span data-stu-id="8c457-102">Configuring a watcher node in Lync Server 2013 to participate in System Center discovery</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8c457-103">_**Última modificación del tema:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="8c457-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="8c457-104">Para asegurarse de que el nodo de monitor participa en el proceso de detección para System Center Operations Manager, debe completar el siguiente procedimiento en un equipo en el que se haya instalado la consola de System Center Operations Manager:</span><span class="sxs-lookup"><span data-stu-id="8c457-104">To make sure that your watcher node participates in the discovery process for System Center Operations Manager, you must complete the following procedure on a computer where the System Center Operations Manager console has been installed:</span></span>

1.  <span data-ttu-id="8c457-105">En la pestaña **Administración**, haga clic en **Agente administrado**.</span><span class="sxs-lookup"><span data-stu-id="8c457-105">On the **Administration** tab, click **Agent Managed**.</span></span>

2.  <span data-ttu-id="8c457-106">Haga clic con el botón secundario en el nombre del equipo del nodo de monitor y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="8c457-106">Right-click the name of the watcher node computer, and then click **Properties**.</span></span> <span data-ttu-id="8c457-107">En el cuadro de diálogo **Propiedades**, en la pestaña **Seguridad**, seleccione **Permitir a este agente que actúe como proxy ay detecte objetos administrados en otros equipos** y luego haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8c457-107">In the **Properties** dialog box, on the **Security** tab, select **Allow this agent to act as a proxy and discover managed objects on other computers**, and then click **OK**.</span></span>

<span data-ttu-id="8c457-108">Después de configurar el nodo de monitor para que actúe como proxy, reinicie el equipo del nodo de monitor.</span><span class="sxs-lookup"><span data-stu-id="8c457-108">After configuring the watcher node to act as a proxy, reboot the watcher node computer.</span></span> <span data-ttu-id="8c457-109">Una vez reiniciado el equipo, compruebe que no se está grabando ningún evento de error en el registro de eventos de Operations Manager de ese equipo.</span><span class="sxs-lookup"><span data-stu-id="8c457-109">After the computer has rebooted, verify that no error events are being recorded in the Operations Manager event log on that computer.</span></span> <span data-ttu-id="8c457-110">Una vez que el equipo haya estado ejecutándose durante 15 minutos o más, use la consola de Operations Manager para comprobar que los equipos de Lync Server aparecen en la categoría **Lync** .</span><span class="sxs-lookup"><span data-stu-id="8c457-110">After the computer has been running for 15 minutes or so, use the Operations Manager console to verify that your Lync Server computers are listed under the **Lync** category.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

