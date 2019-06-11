---
title: 'Lync Server 2013: Iniciar servicios en servidores'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Start services on servers
ms:assetid: fa26eaed-0529-4f32-9f3f-f32c4bd4b1c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413059(v=OCS.15)
ms:contentKeyID: 48185912
ms.date: 09/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c0c0c14aea9966e61703e85dd2aff8a2e448d5eb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850566"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="start-services-on-servers-for-lync-server-2013"></a><span data-ttu-id="16074-102">Iniciar servicios en servidores para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="16074-102">Start services on servers for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="16074-103">_**Última modificación del tema:** 2014-09-03_</span><span class="sxs-lookup"><span data-stu-id="16074-103">_**Topic Last Modified:** 2014-09-03_</span></span>

<span data-ttu-id="16074-104">Para completar correctamente este procedimiento, debe haber iniciado sesión como un usuario que sea miembro del grupo RTCUniversalServerAdmins o tener los permisos configurados correctamente.</span><span class="sxs-lookup"><span data-stu-id="16074-104">To successfully complete this procedure you should be logged in as a user who is a member of the RTCUniversalServerAdmins group or have the correct permissions delegated.</span></span> <span data-ttu-id="16074-105">Para obtener más información sobre la delegación de permisos, vea el tema [permisos de configuración de delegación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="16074-105">For details about delegating permissions, see the topic [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

<span data-ttu-id="16074-106">Después de instalar el almacén de configuración local en los servidores, instalar los componentes de Lync Server 2013 y configurar certificados en un servidor front-end o un servidor front-end, debe iniciar los servicios de Lync Server 2013 en el servidor.</span><span class="sxs-lookup"><span data-stu-id="16074-106">After you install the Local Configuration store on your servers, install the Lync Server 2013 components, and configure certificates on a Front End Server or Front End Server, you must start the Lync Server 2013 services on the server.</span></span> <span data-ttu-id="16074-107">Use el siguiente procedimiento para iniciar servicios en cada servidor front-end de su implementación.</span><span class="sxs-lookup"><span data-stu-id="16074-107">Use the following procedure to start services on each Front End Server in your deployment.</span></span>

<div>

## <a name="to-start-services-on-a-standard-edition-or-front-end-server"></a><span data-ttu-id="16074-108">Para iniciar servicios en un servidor Standard Edition o front-end</span><span class="sxs-lookup"><span data-stu-id="16074-108">To start services on a Standard Edition or Front End Server</span></span>

1.  <span data-ttu-id="16074-109">En el Asistente para la implementación de Lync Server, en la página de **Lync server 2013** , haga clic en **Ejecutar** junto al **paso 4: iniciar servicios**.</span><span class="sxs-lookup"><span data-stu-id="16074-109">In the Lync Server Deployment Wizard, on the **Lync Server 2013** page, click **Run** next to **Step 4: Start Services**.</span></span>

2.  <span data-ttu-id="16074-110">En la página **iniciar servicios** , haga clic en **siguiente** para iniciar los servicios de Lync Server en el servidor.</span><span class="sxs-lookup"><span data-stu-id="16074-110">On the **Start Services** page, click **Next** to start the Lync Server services on the server.</span></span>

3.  <span data-ttu-id="16074-111">En la página **Ejecución de comandos**, una vez que todos los servicios se hayan iniciado correctamente, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="16074-111">On the **Executing Commands** page, after all services have started successfully, click **Finish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="16074-112">El comando para iniciar los servicios en el servidor es el mejor método para notificar que los servicios se han iniciado.</span><span class="sxs-lookup"><span data-stu-id="16074-112">The command to start the services on the server is a best effort method to report that the services have in fact started.</span></span> <span data-ttu-id="16074-113">Es posible que no refleje el estado actual del servicio.</span><span class="sxs-lookup"><span data-stu-id="16074-113">It might not reflect the actual state of the service.</span></span> <span data-ttu-id="16074-114">Le recomendamos que use el estado de servicio de Step <STRONG>(opcional)</STRONG> inmediatamente después de <STRONG>iniciar los servicios</STRONG> para abrir Microsoft Management Console (MMC) y confirmar que los servicios se han iniciado correctamente.</span><span class="sxs-lookup"><span data-stu-id="16074-114">We recommend that you use the step <STRONG>Service Status (Optional)</STRONG> immediately following <STRONG>Start Services</STRONG> to open the Microsoft Management Console (MMC) and confirm that the services have started successfully.</span></span> <span data-ttu-id="16074-115">Si algún servicio de Lync Server no se ha iniciado, puede hacer clic con el botón secundario en el servicio en la MMC y, a continuación, hacer clic en <STRONG>iniciar</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="16074-115">If any Lync Server service has not started, you can right-click that service in the MMC, and then click <STRONG>Start</STRONG>.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

