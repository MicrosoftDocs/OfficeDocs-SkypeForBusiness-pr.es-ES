---
title: Volver a activar el servidor después de que el Asistente para configuración de seguridad cierre los puertos en IIS
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Re-activate server after Security Configuration Wizard closes ports in IIS
ms:assetid: cb8e17cf-f8c1-4099-b63b-c242d656c26a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398851(v=OCS.15)
ms:contentKeyID: 48185644
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b74e1f773f449c139beeb1819d69ba77e92c500e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183383"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="re-activate-server-after-security-configuration-wizard-closes-ports-in-iis"></a><span data-ttu-id="897f6-102">Volver a activar el servidor después de que el Asistente para configuración de seguridad cierre los puertos en IIS</span><span class="sxs-lookup"><span data-stu-id="897f6-102">Re-activate server after Security Configuration Wizard closes ports in IIS</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="897f6-103">_**Última modificación del tema:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="897f6-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="897f6-104">Algunas funciones de Lync Server 2013 ejecutan servicios web en el puerto 4443 de Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="897f6-104">Some Lync Server 2013 roles run Web Services on Internet Information Services (IIS) port 4443.</span></span> <span data-ttu-id="897f6-105">Al ejecutar el Asistente para la implementación de Lync Server, Bootstrapper. exe, o mediante el cmdlet **enable-CsComputer** , se crea una excepción en el firewall y se abre el puerto.</span><span class="sxs-lookup"><span data-stu-id="897f6-105">Running the Lync Server Deployment Wizard, Bootstrapper.exe, or using the **Enable-CsComputer** cmdlet creates an exception in the firewall and opens the port.</span></span> <span data-ttu-id="897f6-106">Si, a continuación, ejecuta el Asistente para configuración de seguridad de Windows Server 2008 R2 (u otros scripts de protección), se bloqueará el puerto 4443 y los clientes externos no podrán contactar con los servicios Web.</span><span class="sxs-lookup"><span data-stu-id="897f6-106">If you then run the Windows Server 2008 R2 Security Configuration Wizard (or other hardening scripts), port 4443 will be blocked, and external clients will not be able to contact Web Services.</span></span> <span data-ttu-id="897f6-107">Para volver a abrir el puerto, puede modificar la excepción del firewall directamente o reactivar el servidor.</span><span class="sxs-lookup"><span data-stu-id="897f6-107">To reopen the port you can either modify the firewall exception directly or re-activate the server.</span></span>

<div>

## <a name="to-re-activate-the-server-by-using-the-deployment-wizard"></a><span data-ttu-id="897f6-108">Para reactivar el servidor mediante el Asistente para la implementación</span><span class="sxs-lookup"><span data-stu-id="897f6-108">To re-activate the server by using the Deployment Wizard</span></span>

1.  <span data-ttu-id="897f6-109">En la página Asistente para la implementación de Lync Server, haga clic en **Ejecutar** junto al **paso 2: configurar o quitar componentes de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="897f6-109">On the Lync Server Deployment Wizard page, click **Run** next to **Step 2: Setup or Remove Lync Server Components**.</span></span>

2.  <span data-ttu-id="897f6-110">En la página **Instalar componentes de Lync Server**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="897f6-110">On **Setup Lync Server components** page, click **Next**.</span></span>

3.  <span data-ttu-id="897f6-111">Cuando el estado de la tarea aparezca como completado en la página **Ejecución de comandos**, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="897f6-111">On the **Executing Commands** page, when the task status is shown as completed, click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="897f6-112">Para reactivar el servidor, también puede usar bootstrapper.exe o <STRONG>Enable-CsComputer</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="897f6-112">You can also use bootstrapper.exe or <STRONG>Enable-CsComputer</STRONG> to re-activate the server.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

