---
title: Implementar el servidor perimetral piloto
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Deploy pilot Edge Server
ms:assetid: 11a59c48-0a53-4de1-83ed-875f850febd5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204682(v=OCS.15)
ms:contentKeyID: 48183446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6cbf3be6dd47f794768ba0f3c8140e7124a1cabb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180413"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploy-pilot-edge-server"></a><span data-ttu-id="7ed06-102">Implementar el servidor perimetral piloto</span><span class="sxs-lookup"><span data-stu-id="7ed06-102">Deploy pilot Edge Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7ed06-103">_**Última modificación del tema:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="7ed06-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="7ed06-104">En este tema se destacan las opciones de configuración que debe tener en cuenta antes de implementar el servidor perimetral de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7ed06-104">This topic highlights configuration settings you should be aware of prior to deploying your Lync Server 2013 Edge Server.</span></span> <span data-ttu-id="7ed06-105">En esta sección solo se destacan los puntos clave que se deben tener en cuenta como parte de la implementación del grupo de servidores perimetrales piloto.</span><span class="sxs-lookup"><span data-stu-id="7ed06-105">This section only highlights key points you should consider as part of your pilot Edge pool deployment.</span></span> <span data-ttu-id="7ed06-106">Para conocer los pasos detallados, consulte [Deploying external User Access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) en la documentación sobre implementación, que describe el proceso de implementación y también proporciona información de configuración para el acceso de usuarios externos.</span><span class="sxs-lookup"><span data-stu-id="7ed06-106">For detailed steps, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.</span></span>

<span data-ttu-id="7ed06-p102">Al navegar por el asistente **Definir nuevo grupo de servidores perimetrales**, repase las principales opciones de configuración recogidas en cada paso. Observe que solo se muestran unas cuantas páginas de\*\*\*\* este asistente.</span><span class="sxs-lookup"><span data-stu-id="7ed06-p102">As you navigate through the **Define New Edge Pool** wizard, review the key configuration settings shown in the following steps. Note that only a few pages of the **Define New Edge Pool** wizard are shown.</span></span>

<span data-ttu-id="7ed06-109">**Definir un grupo de servidores perimetrales**</span><span class="sxs-lookup"><span data-stu-id="7ed06-109">**Define an Edge Pool**</span></span>

1.  <span data-ttu-id="7ed06-110">Abra la topología del grupo piloto en Generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="7ed06-110">Open the pilot pool topology using Topology Builder.</span></span>

2.  <span data-ttu-id="7ed06-111">Navegue hasta el nodo 2013 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7ed06-111">Navigate to the Lync Server 2013 node.</span></span> <span data-ttu-id="7ed06-112">haga clic con el botón secundario en **Grupos de servidores perimetrales** y en **Nuevo grupo de servidores perimetrales**.</span><span class="sxs-lookup"><span data-stu-id="7ed06-112">Right-click **Edge pools**, and click **New Edge pool**.</span></span>
    
    <span data-ttu-id="7ed06-113">![Definir el cuadro de diálogo nuevo grupo de servidores perimetrales](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Definir el cuadro de diálogo nuevo grupo de servidores perimetrales")</span><span class="sxs-lookup"><span data-stu-id="7ed06-113">![Define the New Edge Pool dialog box](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Define the New Edge Pool dialog box")</span></span>

3.  <span data-ttu-id="7ed06-114">Un grupo de servidores perimetrales puede ser un **Grupo de varios equipos** o un **Grupo de un solo equipo**.</span><span class="sxs-lookup"><span data-stu-id="7ed06-114">An Edge pool can be a **Multiple computer pool** or **Single computer pool**.</span></span>
    
    <span data-ttu-id="7ed06-115">![Cuadro de diálogo definir el FQDN del grupo de servidores perimetrales](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Cuadro de diálogo definir el FQDN del grupo de servidores perimetrales")</span><span class="sxs-lookup"><span data-stu-id="7ed06-115">![Define the Edge Pool FQDN dialog box](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Define the Edge Pool FQDN dialog box")</span></span>

4.  <span data-ttu-id="7ed06-116">En la página **Seleccionar características**, no habilite la federación ni la federación XMPP.</span><span class="sxs-lookup"><span data-stu-id="7ed06-116">On the **Select features** page, do not enable federation or XMPP federation.</span></span> <span data-ttu-id="7ed06-117">La Federación y la Federación XMPP actualmente se enrutan a través del servidor perimetral de Office Communications Server 2007 R2 heredado.</span><span class="sxs-lookup"><span data-stu-id="7ed06-117">Federation and XMPP federation are currently routed through the legacy Office Communications Server 2007 R2 Edge Server.</span></span> <span data-ttu-id="7ed06-118">Estas características se configurarán en una fase posterior de la migración.</span><span class="sxs-lookup"><span data-stu-id="7ed06-118">These features will be configured in a later phase of migration.</span></span>
    
    <span data-ttu-id="7ed06-119">![Cuadro de diálogo Seleccionar características](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Cuadro de diálogo Seleccionar características")</span><span class="sxs-lookup"><span data-stu-id="7ed06-119">![Select Features dialog box](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Select Features dialog box")</span></span>

5.  <span data-ttu-id="7ed06-120">A continuación, siga completando las siguientes páginas del asistente: **Seleccione opciones IP**, **FQDN externos**, **defina la dirección IP interna**y **defina la dirección IP externa**.</span><span class="sxs-lookup"><span data-stu-id="7ed06-120">Next, continue completing the following wizard pages: **Select IP options**, **External FQDNs**, **Define the internal IP address**, and **Define the external IP address**.</span></span>

6.  <span data-ttu-id="7ed06-121">En la página **definir el próximo salto** , seleccione el director para el próximo salto del grupo de servidores perimetrales de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7ed06-121">On the **Define the next hop** page, select the Director for the next hop of the Lync Server 2013 Edge pool.</span></span>
    
    <span data-ttu-id="7ed06-122">![Cuadro de diálogo definir nuevo grupo de servidores perimetrales, lista de grupo de servidores de próximo salto](images/JJ204682.61d963d5-e0bd-4b1f-b437-e37c267347ba(OCS.15).jpg "Cuadro de diálogo definir nuevo grupo de servidores perimetrales, lista de grupo de servidores de próximo salto")</span><span class="sxs-lookup"><span data-stu-id="7ed06-122">![Define New Edge Pool dialog, Next hop pool list](images/JJ204682.61d963d5-e0bd-4b1f-b437-e37c267347ba(OCS.15).jpg "Define New Edge Pool dialog, Next hop pool list")</span></span>

7.  <span data-ttu-id="7ed06-123">En la página **asociar grupos de servidores front-end** , no asocie un grupo de servidores a este grupo de servidores perimetrales en este momento.</span><span class="sxs-lookup"><span data-stu-id="7ed06-123">On the **Associate Front End pools** page, do not associate a pool with this Edge pool at this time.</span></span> <span data-ttu-id="7ed06-124">El tráfico de medios externos se enruta actualmente a través del servidor perimetral de Office Communications Server 2007 R2 heredado.</span><span class="sxs-lookup"><span data-stu-id="7ed06-124">External media traffic is currently routed through the legacy Office Communications Server 2007 R2 Edge Server.</span></span> <span data-ttu-id="7ed06-125">Definiremos esta configuración en una fase posterior de la migración.</span><span class="sxs-lookup"><span data-stu-id="7ed06-125">This setting will be configured in a later phase of migration.</span></span>
    
    <span data-ttu-id="7ed06-126">![Cuadro de diálogo definir nuevo grupo de servidores perimetrales](images/JJ204682.bb538039-bd2a-40ed-a120-8b80bd2cefc2(OCS.15).jpg "Cuadro de diálogo definir nuevo grupo de servidores perimetrales")</span><span class="sxs-lookup"><span data-stu-id="7ed06-126">![Define New Edge Pool dialog](images/JJ204682.bb538039-bd2a-40ed-a120-8b80bd2cefc2(OCS.15).jpg "Define New Edge Pool dialog")</span></span>

8.  <span data-ttu-id="7ed06-127">Haga clic en **Finalizar** y, a continuación, publique\*\*\*\* la topología.</span><span class="sxs-lookup"><span data-stu-id="7ed06-127">Click **Finish** and then **Publish** the topology.</span></span>

9.  <span data-ttu-id="7ed06-128">Siga los pasos descritos en [instalar servidores perimetrales para Lync Server 2013](lync-server-2013-install-edge-servers.md) en la documentación de implementación para instalar los archivos en el nuevo servidor perimetral, configurar los certificados e iniciar los servicios.</span><span class="sxs-lookup"><span data-stu-id="7ed06-128">Follow the steps in [Install Edge Servers for Lync Server 2013](lync-server-2013-install-edge-servers.md) in the Deployment documentation to install the files on the new Edge Server, configure certificates, and start the services.</span></span>

<span data-ttu-id="7ed06-129">Es muy importante que siga las instrucciones de los temas [Deploying external User Access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="7ed06-129">It’s very important that you follow the guidelines in the topics [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation.</span></span> <span data-ttu-id="7ed06-130">En esta sección solo se ha proporcionado cierta orientación sobre las opciones de configuración al instalar estos roles de servidor.</span><span class="sxs-lookup"><span data-stu-id="7ed06-130">This section merely provided some guidance on configuration settings when installing these server roles.</span></span>

<span data-ttu-id="7ed06-131">Ahora debe tener una implementación heredada de servidor perimetral de Office Communications Server 2007 R2, indicada por la presencia de BackCompatSite, en paralelo con una implementación de servidor perimetral de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7ed06-131">You should now have a legacy Office Communications Server 2007 R2 Edge server deployment, indicated by the presence of the BackCompatSite, in parallel with a Lync Server 2013 Edge server deployment.</span></span> <span data-ttu-id="7ed06-132">La Federación está configurada para usar el director de Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="7ed06-132">Federation is configured to use the Office Communications Server 2007 R2 Director.</span></span> <span data-ttu-id="7ed06-133">Antes de pasar a la siguiente fase, confirme que ambas implementaciones funcionan correctamente, que los servicios se han iniciado y que puede administrar cada una de las implementaciones.</span><span class="sxs-lookup"><span data-stu-id="7ed06-133">Verify that both deployments are running properly, services are started, and you can administer each deployment prior to moving to the next phase.</span></span>

<span data-ttu-id="7ed06-134">![Generador de topologías que muestra el servidor perimetral de OCS](images/JJ204682.171363a3-eaf0-4c94-bd41-02b1ab6fa7dc(OCS.15).jpg "Generador de topologías que muestra el servidor perimetral de OCS")</span><span class="sxs-lookup"><span data-stu-id="7ed06-134">![Topology Builder showing OCS Edge Server](images/JJ204682.171363a3-eaf0-4c94-bd41-02b1ab6fa7dc(OCS.15).jpg "Topology Builder showing OCS Edge Server")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

