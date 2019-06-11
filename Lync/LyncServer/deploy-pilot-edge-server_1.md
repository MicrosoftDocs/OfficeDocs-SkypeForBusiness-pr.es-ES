---
title: Implementar el servidor perimetral piloto
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Deploy pilot Edge Server
ms:assetid: 11a59c48-0a53-4de1-83ed-875f850febd5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204682(v=OCS.15)
ms:contentKeyID: 48183446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c9cfe98069d3c90f4e021b34f6a7d31c583e7565
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842834"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-pilot-edge-server"></a><span data-ttu-id="ea534-102">Implementar el servidor perimetral piloto</span><span class="sxs-lookup"><span data-stu-id="ea534-102">Deploy pilot Edge Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ea534-103">_**Última modificación del tema:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="ea534-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="ea534-104">En este tema se destacan las opciones de configuración que debe tener en cuenta antes de implementar el servidor perimetral de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ea534-104">This topic highlights configuration settings you should be aware of prior to deploying your Lync Server 2013 Edge Server.</span></span> <span data-ttu-id="ea534-105">Esta sección solo resalta los puntos clave que debe considerar como parte de la implementación del grupo de bordes de la prueba piloto.</span><span class="sxs-lookup"><span data-stu-id="ea534-105">This section only highlights key points you should consider as part of your pilot Edge pool deployment.</span></span> <span data-ttu-id="ea534-106">Para conocer los pasos detallados, vea [implementar el acceso de usuarios externos en Lync Server 2013](lync-server-2013-deploying-external-user-access.md) en la documentación de implementación, que describe el proceso de implementación y también proporciona información de configuración para el acceso de usuarios externos.</span><span class="sxs-lookup"><span data-stu-id="ea534-106">For detailed steps, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.</span></span>

<span data-ttu-id="ea534-107">Mientras navega por el asistente **definir nuevo grupo de bordes** , revise la configuración de clave que se muestra en los siguientes pasos.</span><span class="sxs-lookup"><span data-stu-id="ea534-107">As you navigate through the **Define New Edge Pool** wizard, review the key configuration settings shown in the following steps.</span></span> <span data-ttu-id="ea534-108">Observe que solo se muestran algunas páginas del asistente **definir nuevo grupo de bordes** .</span><span class="sxs-lookup"><span data-stu-id="ea534-108">Note that only a few pages of the **Define New Edge Pool** wizard are shown.</span></span>

<span data-ttu-id="ea534-109">**Definir un grupo perimetral**</span><span class="sxs-lookup"><span data-stu-id="ea534-109">**Define an Edge Pool**</span></span>

1.  <span data-ttu-id="ea534-110">Abra la topología de la agrupación piloto con el generador de topología.</span><span class="sxs-lookup"><span data-stu-id="ea534-110">Open the pilot pool topology using Topology Builder.</span></span>

2.  <span data-ttu-id="ea534-111">Vaya al nodo de 2013 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ea534-111">Navigate to the Lync Server 2013 node.</span></span> <span data-ttu-id="ea534-112">Haga clic con \*\*\*\* el botón secundario en agrupaciones perimetrales y haga clic en **nuevo borde**.</span><span class="sxs-lookup"><span data-stu-id="ea534-112">Right-click **Edge pools**, and click **New Edge pool**.</span></span>
    
    <span data-ttu-id="ea534-113">![Definir el cuadro de diálogo nuevo grupo perimetral] (images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Definir el cuadro de diálogo nuevo grupo perimetral")</span><span class="sxs-lookup"><span data-stu-id="ea534-113">![Define the New Edge Pool dialog box](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Define the New Edge Pool dialog box")</span></span>

3.  <span data-ttu-id="ea534-114">Un grupo de servidores perimetrales puede ser un **grupo de varios equipos** o un **único grupo de equipos**.</span><span class="sxs-lookup"><span data-stu-id="ea534-114">An Edge pool can be a **Multiple computer pool** or **Single computer pool**.</span></span>
    
    <span data-ttu-id="ea534-115">![Definir el cuadro de diálogo FQDN del grupo de bordes] (images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Definir el cuadro de diálogo FQDN del grupo de bordes")</span><span class="sxs-lookup"><span data-stu-id="ea534-115">![Define the Edge Pool FQDN dialog box](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Define the Edge Pool FQDN dialog box")</span></span>

4.  <span data-ttu-id="ea534-116">En la página **seleccionar características** , no habilite la Federación ni la Federación XMPP.</span><span class="sxs-lookup"><span data-stu-id="ea534-116">On the **Select features** page, do not enable federation or XMPP federation.</span></span> <span data-ttu-id="ea534-117">La Federación y la Federación de XMPP actualmente se enrutan a través del servidor perimetral heredado de Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="ea534-117">Federation and XMPP federation are currently routed through the legacy Office Communications Server 2007 R2 Edge Server.</span></span> <span data-ttu-id="ea534-118">Estas características se configurarán en una fase posterior de la migración.</span><span class="sxs-lookup"><span data-stu-id="ea534-118">These features will be configured in a later phase of migration.</span></span>
    
    <span data-ttu-id="ea534-119">![Cuadro de diálogo Seleccionar características] (images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Cuadro de diálogo Seleccionar características")</span><span class="sxs-lookup"><span data-stu-id="ea534-119">![Select Features dialog box](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Select Features dialog box")</span></span>

5.  <span data-ttu-id="ea534-120">Después, siga completando las siguientes páginas del asistente: **Seleccione opciones de IP**, **FQDN externos**, **defina la dirección IP interna**y **defina la dirección IP externa**.</span><span class="sxs-lookup"><span data-stu-id="ea534-120">Next, continue completing the following wizard pages: **Select IP options**, **External FQDNs**, **Define the internal IP address**, and **Define the external IP address**.</span></span>

6.  <span data-ttu-id="ea534-121">En la página **definir el siguiente salto** , seleccione el director para el próximo salto del grupo de servidores perimetrales de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ea534-121">On the **Define the next hop** page, select the Director for the next hop of the Lync Server 2013 Edge pool.</span></span>
    
    <span data-ttu-id="ea534-122">![Cuadro de diálogo definir nuevo grupo perimetral, lista Grupo de próximos saltos] (images/JJ204682.61d963d5-e0bd-4b1f-b437-e37c267347ba(OCS.15).jpg "Cuadro de diálogo definir nuevo grupo perimetral, lista Grupo de próximos saltos")</span><span class="sxs-lookup"><span data-stu-id="ea534-122">![Define New Edge Pool dialog, Next hop pool list](images/JJ204682.61d963d5-e0bd-4b1f-b437-e37c267347ba(OCS.15).jpg "Define New Edge Pool dialog, Next hop pool list")</span></span>

7.  <span data-ttu-id="ea534-123">En la página **asociar pools front-end** , no asocie un grupo con este grupo perimetral en este momento.</span><span class="sxs-lookup"><span data-stu-id="ea534-123">On the **Associate Front End pools** page, do not associate a pool with this Edge pool at this time.</span></span> <span data-ttu-id="ea534-124">El tráfico multimedia externo se enruta actualmente a través del servidor perimetral heredado de Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="ea534-124">External media traffic is currently routed through the legacy Office Communications Server 2007 R2 Edge Server.</span></span> <span data-ttu-id="ea534-125">Esta configuración se configurará en una fase posterior de la migración.</span><span class="sxs-lookup"><span data-stu-id="ea534-125">This setting will be configured in a later phase of migration.</span></span>
    
    <span data-ttu-id="ea534-126">![Cuadro de diálogo definir nuevo grupo perimetral] (images/JJ204682.bb538039-bd2a-40ed-a120-8b80bd2cefc2(OCS.15).jpg "Cuadro de diálogo definir nuevo grupo perimetral")</span><span class="sxs-lookup"><span data-stu-id="ea534-126">![Define New Edge Pool dialog](images/JJ204682.bb538039-bd2a-40ed-a120-8b80bd2cefc2(OCS.15).jpg "Define New Edge Pool dialog")</span></span>

8.  <span data-ttu-id="ea534-127">Haga clic en **Finalizar** y, a continuación, **publique** la topología.</span><span class="sxs-lookup"><span data-stu-id="ea534-127">Click **Finish** and then **Publish** the topology.</span></span>

9.  <span data-ttu-id="ea534-128">Siga los pasos que se indican en [instalar servidores perimetrales para Lync Server 2013](lync-server-2013-install-edge-servers.md) en la documentación de implementación para instalar los archivos en el nuevo servidor perimetral, configurar certificados e iniciar los servicios.</span><span class="sxs-lookup"><span data-stu-id="ea534-128">Follow the steps in [Install Edge Servers for Lync Server 2013](lync-server-2013-install-edge-servers.md) in the Deployment documentation to install the files on the new Edge Server, configure certificates, and start the services.</span></span>

<span data-ttu-id="ea534-129">Es muy importante seguir las directrices de los temas [implementar el acceso de usuarios externos en Lync Server 2013](lync-server-2013-deploying-external-user-access.md) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="ea534-129">It’s very important that you follow the guidelines in the topics [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation.</span></span> <span data-ttu-id="ea534-130">En esta sección se proporciona una mera información sobre las opciones de configuración al instalar estos roles de servidor.</span><span class="sxs-lookup"><span data-stu-id="ea534-130">This section merely provided some guidance on configuration settings when installing these server roles.</span></span>

<span data-ttu-id="ea534-131">Ahora debe tener una implementación heredada de servidor perimetral de Office Communications Server 2007 R2, indicada por la presencia de la BackCompatSite, en paralelo con una implementación de servidor perimetral de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ea534-131">You should now have a legacy Office Communications Server 2007 R2 Edge server deployment, indicated by the presence of the BackCompatSite, in parallel with a Lync Server 2013 Edge server deployment.</span></span> <span data-ttu-id="ea534-132">La Federación está configurada para usar el director de Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="ea534-132">Federation is configured to use the Office Communications Server 2007 R2 Director.</span></span> <span data-ttu-id="ea534-133">Compruebe que las implementaciones se ejecutan correctamente y que se inician los servicios, y puede administrar cada implementación antes de pasar a la siguiente fase.</span><span class="sxs-lookup"><span data-stu-id="ea534-133">Verify that both deployments are running properly, services are started, and you can administer each deployment prior to moving to the next phase.</span></span>

<span data-ttu-id="ea534-134">![Generador de topología que muestra el servidor perimetral de OCS] (images/JJ204682.171363a3-eaf0-4c94-bd41-02b1ab6fa7dc(OCS.15).jpg "Generador de topología que muestra el servidor perimetral de OCS")</span><span class="sxs-lookup"><span data-stu-id="ea534-134">![Topology Builder showing OCS Edge Server](images/JJ204682.171363a3-eaf0-4c94-bd41-02b1ab6fa7dc(OCS.15).jpg "Topology Builder showing OCS Edge Server")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

