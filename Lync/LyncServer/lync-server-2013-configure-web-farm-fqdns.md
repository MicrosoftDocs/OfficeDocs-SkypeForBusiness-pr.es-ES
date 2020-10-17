---
title: 'Lync Server 2013: configurar FQDN de granja de servidores Web'
description: 'Lync Server 2013: configurar FQDN de granja de servidores Web.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure web farm FQDNs
ms:assetid: cb25dbbd-dcea-4997-8e14-e5007dd7d3ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429722(v=OCS.15)
ms:contentKeyID: 48185481
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8a07faac4d4809ffe10e7ca3699e7441e6dbcb7b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566666"
---
# <a name="configure-web-farm-fqdns-for-lync-server-2013"></a><span data-ttu-id="76bbb-103">Configurar FQDN de granja de servidores web para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="76bbb-103">Configure web farm FQDNs for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="76bbb-104">_**Última modificación del tema:** 2013-03-29_</span><span class="sxs-lookup"><span data-stu-id="76bbb-104">_**Topic Last Modified:** 2013-03-29_</span></span>

<span data-ttu-id="76bbb-105">Al definir la configuración del servidor Standard Edition, el grupo de servidores front-end, el director o el grupo de directores en el generador de topologías, se configura un nombre de dominio completo (FQDN) de servicios web externos.</span><span class="sxs-lookup"><span data-stu-id="76bbb-105">When you defined the configuration of the Standard Edition server, Front End pool, Director or Director pool in Topology Builder, you configure an external web services fully qualified domain name (FQDN).</span></span> <span data-ttu-id="76bbb-106">Durante el proceso de inicio de sesión de un cliente hospedado en el servidor Standard Edition o el grupo de servidores front-end, los FQDN de servicios web configurados se envían por medio del aprovisionamiento en banda.</span><span class="sxs-lookup"><span data-stu-id="76bbb-106">During the log on process of a client homed in the Standard Edition server or Front End pool, the configured web services FQDNs are sent by way of in-band provisioning.</span></span> <span data-ttu-id="76bbb-107">Si necesita agregar o cambiar la dirección URL de los servicios web externos, use el generador de topologías para configurar o volver a configurar la configuración de los servicios Web mediante el procedimiento descrito en este tema.</span><span class="sxs-lookup"><span data-stu-id="76bbb-107">If you need to add or change the external web services URL, you use Topology Builder to configure or reconfigure the web services configuration using the procedure in this topic.</span></span>

<div>

## <a name="to-configure-an-external-pool-fqdn-for-web-services"></a><span data-ttu-id="76bbb-108">Para configurar el FQDN de un grupo de servidores externo para servicios web</span><span class="sxs-lookup"><span data-stu-id="76bbb-108">To configure an external pool FQDN for web services</span></span>

1.  <span data-ttu-id="76bbb-109">Inicie el generador de topologías: haga clic en **Inicio**, haga clic en **todos los programas**, haga clic en **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topologías de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="76bbb-109">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="76bbb-110">En el generador de topologías, en el árbol de la consola, en **servidores front-end Standard Edition**, **servidores front-end Enterprise Edition**y **directores**, haga clic con el botón secundario en el nombre del grupo que tiene que editar y, a continuación, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="76bbb-110">In Topology Builder, in the console tree under **Standard Edition Front Ends**, **Enterprise Edition Front Ends**, and **Directors**, right-click the pool name that you need to edit, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="76bbb-111">En la sección **Servicios web**, agregue o edite el **FQDN de servicios web externos**.</span><span class="sxs-lookup"><span data-stu-id="76bbb-111">In the **Web services** section, add or edit the **External web services FQDN**.</span></span>

4.  <span data-ttu-id="76bbb-p102">Revise y ajuste los  **Puertos de escucha** para HTTP y HTTPS. Los valores predeterminados serán:</span><span class="sxs-lookup"><span data-stu-id="76bbb-p102">Review and adjust the **Listening ports** for both HTTP and HTTPS. The defaults will be:</span></span>
    
      - <span data-ttu-id="76bbb-114">**Puertos de escucha:** HTTP 8080, HTTPS 4443</span><span class="sxs-lookup"><span data-stu-id="76bbb-114">**Listening ports:** HTTP 8080, HTTPS 4443</span></span>
    
      - <span data-ttu-id="76bbb-115">**Puertos de escucha:** HTTP 80, HTTPS 443</span><span class="sxs-lookup"><span data-stu-id="76bbb-115">**Published ports:** HTTP 80, HTTPS 443</span></span>
    
    <span data-ttu-id="76bbb-116">Donde los **Puertos de escucha** son los puertos que los servicios web externos configurarán para recibir solicitudes desde el proxy inverso y los **Puertos publicados** son los puertos que publica externamente el proxy inverso y se comunican a los clientes durante el aprovisionamiento en banda.</span><span class="sxs-lookup"><span data-stu-id="76bbb-116">Where the **Listening ports** is the port that the external web services will be configured to receive requests from the reverse proxy, and the **Published ports** is the ports that are published externally by the reverse proxy and is communicated to clients during in-band provisioning.</span></span>

5.  <span data-ttu-id="76bbb-117">Cuando haya completado las adiciones y actualizaciones, haga clic en **Aceptar** para continuar.</span><span class="sxs-lookup"><span data-stu-id="76bbb-117">When you have completed your additions and updates, click **OK** to continue.</span></span>

6.  <span data-ttu-id="76bbb-118">Haga clic con el botón secundario en **Lync Server 2013**y, a continuación, haga clic en **publicar**.</span><span class="sxs-lookup"><span data-stu-id="76bbb-118">Right-click **Lync Server 2013**, and then click **Publish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="76bbb-119">Una vez finalizada la publicación correctamente, puede aparecer un vínculo que le informa de que hay pasos adicionales que deban llevarse a cabo.</span><span class="sxs-lookup"><span data-stu-id="76bbb-119">After publishing successfully completes, a link may be presented that informs you that there are additional steps that need to be taken.</span></span> <span data-ttu-id="76bbb-120">Si se hace clic en el vínculo, se abre una lista de servidores afectados por los cambios realizados en Topology Builder que requerirán volver a ejecutar el Asistente para la implementación de Lync Server en cada servidor de la lista para actualizar la configuración de los componentes agregados, quitados o modificados.</span><span class="sxs-lookup"><span data-stu-id="76bbb-120">The link, if clicked, opens a list of servers affected by the changes made in Topology Builder that will require you to re-run the Lync Server Deployment Wizard on each listed server to update the configuration for added, removed, or changed components.</span></span>

    
    </div>

7.  <span data-ttu-id="76bbb-121">Repita estos pasos para cada servidor Standard Edition, grupo de servidores front-end, director o grupo de directores de la organización.</span><span class="sxs-lookup"><span data-stu-id="76bbb-121">Repeat these steps for each Standard Edition server, Front End pool, Director or Director pool in the organization.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

