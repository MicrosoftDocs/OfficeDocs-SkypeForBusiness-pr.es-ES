---
title: 'Lync Server 2013: marcar una aplicación de lenguaje de procesamiento SIP de Microsoft (MSPL) como crítica o no crítica'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mark a Microsoft SIP Processing Language (MSPL) application as critical or not critical
ms:assetid: df68fdc6-b7e6-4f07-acdc-0cd4c2c888a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182598(v=OCS.15)
ms:contentKeyID: 48185622
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 54d8b0858145930e0a2144ade55934b39394dcaf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757954"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical-in-lync-server-2013"></a><span data-ttu-id="74f81-102">Marcar una aplicación de Microsoft SIP Processing language (MSPL) como crítica o incrítica en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="74f81-102">Mark a Microsoft SIP Processing Language (MSPL) application as critical or not critical in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="74f81-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="74f81-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="74f81-104">Las aplicaciones de servidor de Microsoft SIP Processing language (MSPL) son aplicaciones de solo script que usan el lenguaje de scripts MSPL en lugar de la API 2010 de Microsoft Lync.</span><span class="sxs-lookup"><span data-stu-id="74f81-104">Microsoft SIP Processing Language (MSPL) server applications are script-only applications that use the MSPL scripting language instead of the Microsoft Lync 2010 API.</span></span> <span data-ttu-id="74f81-105">Algunas aplicaciones de servidor MSPL se especifican como críticas.</span><span class="sxs-lookup"><span data-stu-id="74f81-105">Some MSPL server applications are specified as critical.</span></span> <span data-ttu-id="74f81-106">Si una secuencia de comandos es crítica, la secuencia de comandos debe iniciarse durante el inicio del sistema para que Lync Server 2013 se inicie.</span><span class="sxs-lookup"><span data-stu-id="74f81-106">If a script is critical, the script must start during system startup in order for Lync Server 2013 to start.</span></span> <span data-ttu-id="74f81-107">Si se produce un error en la secuencia de comandos mientras Lync Server se está ejecutando, el servidor no se cierra, pero deja de enviar tráfico al script y escribe los errores en el registro de eventos.</span><span class="sxs-lookup"><span data-stu-id="74f81-107">If the script fails while Lync Server is running, the server does not shut down, but it stops sending traffic to the script, and it writes errors in the event log.</span></span>

<span data-ttu-id="74f81-108">Puede usar el panel de control de Lync Server para marcar las aplicaciones de servidor de Microsoft SIP Processing language (MSPL) como críticas o desmarcarlas.</span><span class="sxs-lookup"><span data-stu-id="74f81-108">You can use Lync Server Control Panel to mark Microsoft SIP Processing Language (MSPL) server applications as critical or unmark them.</span></span>

<span data-ttu-id="74f81-109">No todos los scripts admiten esta opción.</span><span class="sxs-lookup"><span data-stu-id="74f81-109">Not all scripts support this option.</span></span> <span data-ttu-id="74f81-110">Por ejemplo, el script DefaultRouting se marca como crítico, y esta opción no se puede cambiar para DefaultRouting.</span><span class="sxs-lookup"><span data-stu-id="74f81-110">For example, the DefaultRouting script is marked as critical, and this option cannot be changed for DefaultRouting.</span></span>

<div>

## <a name="to-mark-or-unmark-an-mspl-server-application-as-critical"></a><span data-ttu-id="74f81-111">Para marcar o desmarcar una aplicación de servidor de MSPL como crítica</span><span class="sxs-lookup"><span data-stu-id="74f81-111">To mark or unmark an MSPL server application as critical</span></span>

1.  <span data-ttu-id="74f81-112">Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins (o que tenga derechos de usuario equivalentes), o asignada al rol CsServerAdministrator o CsAdministrator, inicie sesión en cualquier equipo de la red en el que haya implementado Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="74f81-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="74f81-113">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="74f81-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="74f81-114">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="74f81-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="74f81-115">En la barra de navegación izquierda, haga clic en **topología** y después haga clic en **aplicación de servidor**.</span><span class="sxs-lookup"><span data-stu-id="74f81-115">In the left navigation bar, click **Topology** and then click **Server Application**.</span></span>

4.  <span data-ttu-id="74f81-116">En la página de la **aplicación servidor** , haga clic en un encabezado de columna para ordenar las aplicaciones, si es necesario, y, a continuación, haga clic en la aplicación de servidor que desea modificar.</span><span class="sxs-lookup"><span data-stu-id="74f81-116">On the **Server Application** page, click a column heading to sort the applications, if needed, and then click the server application that you want to modify.</span></span>

5.  <span data-ttu-id="74f81-117">Haga clic en **acción**.</span><span class="sxs-lookup"><span data-stu-id="74f81-117">Click **Action**.</span></span>

6.  <span data-ttu-id="74f81-118">Haga clic en **marcar como crítico** o **deseleccionar como crítico** (es decir, si el script admite esta opción).</span><span class="sxs-lookup"><span data-stu-id="74f81-118">Click **Mark as critical** or **Unselect as critical** (that is, if the script supports this option).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="74f81-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="74f81-119">See Also</span></span>


[<span data-ttu-id="74f81-120">Habilitar o deshabilitar una aplicación de servidor de Microsoft SIP Processing language (MSPL) en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="74f81-120">Enable or disable a Microsoft SIP Processing Language (MSPL) server application in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application.md)  


[<span data-ttu-id="74f81-121">Ver las aplicaciones de servidor del lenguaje de procesamiento de SIP de Microsoft (MSPL) de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="74f81-121">View Microsoft SIP Processing Language (MSPL) server applications in Lync Server 2013</span></span>](lync-server-2013-view-microsoft-sip-processing-language-mspl-server-applications.md)  


[<span data-ttu-id="74f81-122">Administración de la topología de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="74f81-122">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

