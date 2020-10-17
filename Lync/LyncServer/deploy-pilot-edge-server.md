---
title: Implementar el servidor perimetral piloto
description: Implementar el servidor perimetral piloto.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Deploy pilot Edge Server
ms:assetid: dab345c0-8577-4c11-ac73-fe8b2a75f4cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205306(v=OCS.15)
ms:contentKeyID: 48185559
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d63e9255ad448995fcafa05fed12e97ea151736b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550736"
---
# <a name="deploy-pilot-edge-server"></a><span data-ttu-id="4500c-103">Implementar el servidor perimetral piloto</span><span class="sxs-lookup"><span data-stu-id="4500c-103">Deploy pilot Edge Server</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4500c-104">_**Última modificación del tema:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="4500c-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="4500c-105">En este tema se destacan las opciones de configuración que debe tener en cuenta antes de implementar el servidor perimetral de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4500c-105">This topic highlights configuration settings you should be aware of prior to deploying your Lync Server 2013 Edge Server.</span></span> <span data-ttu-id="4500c-106">Los procesos de implementación y configuración de Lync Server 2013 son muy similares a los de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="4500c-106">The deployment and configuration processes for Lync Server 2013 are very similar to Lync Server 2010.</span></span> <span data-ttu-id="4500c-107">En esta sección solo se detallan los aspectos clave que hay que considerar al implementar el grupo piloto.</span><span class="sxs-lookup"><span data-stu-id="4500c-107">This section only highlights key points you should consider as part of your pilot pool deployment.</span></span> <span data-ttu-id="4500c-108">Para conocer los pasos detallados, consulte [Deploying external User Access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) en la documentación sobre implementación, que describe el proceso de implementación y también proporciona información de configuración para el acceso de usuarios externos.</span><span class="sxs-lookup"><span data-stu-id="4500c-108">For detailed steps, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.</span></span>

<span data-ttu-id="4500c-p102">Al navegar por el asistente **Definir nuevo grupo de servidores perimetrales**, repase las principales opciones de configuración recogidas en cada paso. Observe que solo se muestran unas cuantas páginas de\*\*\*\* este asistente.</span><span class="sxs-lookup"><span data-stu-id="4500c-p102">As you navigate through the **Define New Edge Pool** wizard, review the key configuration settings shown in the following steps. Note that only a few pages of the **Define New Edge Pool** wizard are shown.</span></span>

<span data-ttu-id="4500c-111">**Definir un grupo de servidores perimetrales**</span><span class="sxs-lookup"><span data-stu-id="4500c-111">**Define an Edge Pool**</span></span>

1.  <span data-ttu-id="4500c-112">Inicie sesión en el equipo en el que Topology Builder esté instalado como miembro del grupo Admins. del dominio y el grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="4500c-112">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="4500c-113">Navegue hasta el nodo 2013 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4500c-113">Navigate to the Lync Server 2013 node.</span></span> <span data-ttu-id="4500c-114">haga clic con el botón secundario en **Grupos de servidores perimetrales** y en **Nuevo grupo de servidores perimetrales**.</span><span class="sxs-lookup"><span data-stu-id="4500c-114">Right-click **Edge pools**, and click **New Edge pool**.</span></span>
    
    <span data-ttu-id="4500c-115">![Definir el cuadro de diálogo nuevo grupo de servidores perimetrales](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Definir el cuadro de diálogo nuevo grupo de servidores perimetrales")</span><span class="sxs-lookup"><span data-stu-id="4500c-115">![Define the New Edge Pool dialog box](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Define the New Edge Pool dialog box")</span></span>

3.  <span data-ttu-id="4500c-116">Un grupo de servidores perimetrales puede ser un **Grupo de varios equipos** o un **Grupo de un solo equipo**.</span><span class="sxs-lookup"><span data-stu-id="4500c-116">An Edge pool can be a **Multiple computer pool** or **Single computer pool**.</span></span>
    
    <span data-ttu-id="4500c-117">![Cuadro de diálogo definir el FQDN del grupo de servidores perimetrales](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Cuadro de diálogo definir el FQDN del grupo de servidores perimetrales")</span><span class="sxs-lookup"><span data-stu-id="4500c-117">![Define the Edge Pool FQDN dialog box](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Define the Edge Pool FQDN dialog box")</span></span>

4.  <span data-ttu-id="4500c-118">En la página **Seleccionar características**, no habilite la federación ni la federación XMPP.</span><span class="sxs-lookup"><span data-stu-id="4500c-118">On the **Select features** page, do not enable federation or XMPP federation.</span></span> <span data-ttu-id="4500c-119">La Federación y la Federación de XMPP se enrutan actualmente a través del servidor perimetral de Lync Server 2010 antiguo.</span><span class="sxs-lookup"><span data-stu-id="4500c-119">Federation and XMPP federation are both currently routed through the legacy Lync Server 2010 Edge Server.</span></span> <span data-ttu-id="4500c-120">Estas características se configurarán en una fase posterior de la migración.</span><span class="sxs-lookup"><span data-stu-id="4500c-120">These features will be configured in a later phase of migration.</span></span>
    
    <span data-ttu-id="4500c-121">![Cuadro de diálogo Seleccionar características](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Cuadro de diálogo Seleccionar características")</span><span class="sxs-lookup"><span data-stu-id="4500c-121">![Select Features dialog box](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Select Features dialog box")</span></span>

5.  <span data-ttu-id="4500c-122">Tras ello, siga cumplimentando las siguientes páginas del asistente: **FQDN externos**, **Definir la dirección IP interna** y **Definir la dirección IP externa**.</span><span class="sxs-lookup"><span data-stu-id="4500c-122">Next, continue completing the following wizard pages: **External FQDNs**, **Define the internal IP address**, and **Define the external IP address**.</span></span>

6.  <span data-ttu-id="4500c-123">En la página **definir el próximo salto** , seleccione el director para el próximo salto del grupo de servidores perimetrales de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="4500c-123">On the **Define the next hop** page, select the Director for the next hop of the Lync Server 2010 Edge pool.</span></span>
    
    <span data-ttu-id="4500c-124">![Cuadro de diálogo definir el próximo salto](images/JJ205306.11baf3ea-74f5-4eb7-8650-b03b3b190416(OCS.15).jpg "Cuadro de diálogo definir el próximo salto")</span><span class="sxs-lookup"><span data-stu-id="4500c-124">![Define the Next Hop dialog box](images/JJ205306.11baf3ea-74f5-4eb7-8650-b03b3b190416(OCS.15).jpg "Define the Next Hop dialog box")</span></span>

7.  <span data-ttu-id="4500c-125">En la página **asociar grupos de servidores front-end o de mediación** , no asocie un grupo de servidores con este grupo de servidores perimetrales en este momento.</span><span class="sxs-lookup"><span data-stu-id="4500c-125">On the **Associate Front End or Mediation pools** page, do not associate a pool with this Edge pool at this time.</span></span> <span data-ttu-id="4500c-126">El tráfico multimedia externo se enruta actualmente a través del servidor perimetral heredado de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="4500c-126">External media traffic is currently routed through the legacy Lync Server 2010 Edge Server.</span></span> <span data-ttu-id="4500c-127">Definiremos esta configuración en una fase posterior de la migración.</span><span class="sxs-lookup"><span data-stu-id="4500c-127">This setting will be configured in a later phase of migration.</span></span>
    
    <span data-ttu-id="4500c-128">![Cuadro de diálogo asociar grupos de servidores front-end](images/JJ205306.fe0da887-7b51-4564-afc5-d57da95a2eb6(OCS.15).jpg "Cuadro de diálogo asociar grupos de servidores front-end")</span><span class="sxs-lookup"><span data-stu-id="4500c-128">![Associate Front End Pools dialog box](images/JJ205306.fe0da887-7b51-4564-afc5-d57da95a2eb6(OCS.15).jpg "Associate Front End Pools dialog box")</span></span>

8.  <span data-ttu-id="4500c-129">Haga clic en **Finalizar** y, a continuación, publique\*\*\*\* la topología.</span><span class="sxs-lookup"><span data-stu-id="4500c-129">Click **Finish** and then **Publish** the topology.</span></span>

9.  <span data-ttu-id="4500c-130">Siga los pasos descritos en [instalar servidores perimetrales para Lync Server 2013](lync-server-2013-install-edge-servers.md) en la documentación de implementación para instalar los archivos en el nuevo servidor perimetral, configurar los certificados e iniciar los servicios.</span><span class="sxs-lookup"><span data-stu-id="4500c-130">Follow the steps in [Install Edge Servers for Lync Server 2013](lync-server-2013-install-edge-servers.md) in the Deployment documentation to install the files on the new Edge Server, configure certificates, and start the services.</span></span>

<span data-ttu-id="4500c-131">Es muy importante que siga las instrucciones de los temas [Deploying external User Access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="4500c-131">It’s very important that you follow the guidelines in the topics [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation.</span></span> <span data-ttu-id="4500c-132">En esta sección solo se ha proporcionado cierta orientación sobre las opciones de configuración al instalar estos roles de servidor.</span><span class="sxs-lookup"><span data-stu-id="4500c-132">This section merely provided some guidance on configuration settings when installing these server roles.</span></span>

<span data-ttu-id="4500c-133">Ahora debe tener un servidor perimetral de Lync Server 2010 que esté implementado en paralelo con una implementación de servidor perimetral de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4500c-133">You should now have a legacy Lync Server 2010 Edge Server deployed in parallel with a Lync Server 2013 Edge server deployment.</span></span> <span data-ttu-id="4500c-134">Antes de pasar a la siguiente fase, confirme que ambas implementaciones funcionan correctamente, que los servicios se han iniciado y que puede administrar cada una de las implementaciones.</span><span class="sxs-lookup"><span data-stu-id="4500c-134">Verify that both deployments are running properly, services are started, and you can administer each deployment prior to moving to the next phase.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

