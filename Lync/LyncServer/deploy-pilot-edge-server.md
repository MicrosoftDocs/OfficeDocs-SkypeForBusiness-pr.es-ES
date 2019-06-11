---
title: Implementar el servidor perimetral piloto
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Deploy pilot Edge Server
ms:assetid: dab345c0-8577-4c11-ac73-fe8b2a75f4cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205306(v=OCS.15)
ms:contentKeyID: 48185559
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bd8fddd611422562c9384a52748623623d4e6f68
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842836"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-pilot-edge-server"></a><span data-ttu-id="2beff-102">Implementar el servidor perimetral piloto</span><span class="sxs-lookup"><span data-stu-id="2beff-102">Deploy pilot Edge Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2beff-103">_**Última modificación del tema:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="2beff-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="2beff-104">En este tema se destacan las opciones de configuración que debe tener en cuenta antes de implementar el servidor perimetral de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2beff-104">This topic highlights configuration settings you should be aware of prior to deploying your Lync Server 2013 Edge Server.</span></span> <span data-ttu-id="2beff-105">Los procesos de implementación y configuración de Lync Server 2013 son muy similares a los de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2beff-105">The deployment and configuration processes for Lync Server 2013 are very similar to Lync Server 2010.</span></span> <span data-ttu-id="2beff-106">Esta sección solo resalta los puntos clave que debe considerar como parte de la implementación de un grupo piloto.</span><span class="sxs-lookup"><span data-stu-id="2beff-106">This section only highlights key points you should consider as part of your pilot pool deployment.</span></span> <span data-ttu-id="2beff-107">Para conocer los pasos detallados, vea [implementar el acceso de usuarios externos en Lync Server 2013](lync-server-2013-deploying-external-user-access.md) en la documentación de implementación, que describe el proceso de implementación y también proporciona información de configuración para el acceso de usuarios externos.</span><span class="sxs-lookup"><span data-stu-id="2beff-107">For detailed steps, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation, which describes the deployment process and also gives configuration information for external user access.</span></span>

<span data-ttu-id="2beff-108">Mientras navega por el asistente **definir nuevo grupo de bordes** , revise la configuración de clave que se muestra en los siguientes pasos.</span><span class="sxs-lookup"><span data-stu-id="2beff-108">As you navigate through the **Define New Edge Pool** wizard, review the key configuration settings shown in the following steps.</span></span> <span data-ttu-id="2beff-109">Observe que solo se muestran algunas páginas del asistente **definir nuevo grupo de bordes** .</span><span class="sxs-lookup"><span data-stu-id="2beff-109">Note that only a few pages of the **Define New Edge Pool** wizard are shown.</span></span>

<span data-ttu-id="2beff-110">**Definir un grupo perimetral**</span><span class="sxs-lookup"><span data-stu-id="2beff-110">**Define an Edge Pool**</span></span>

1.  <span data-ttu-id="2beff-111">Inicie sesión en el equipo donde se encuentre instalado el Generador de topologías como miembro del grupo Administradores del dominio y el grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="2beff-111">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="2beff-112">Vaya al nodo de 2013 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2beff-112">Navigate to the Lync Server 2013 node.</span></span> <span data-ttu-id="2beff-113">Haga clic con \*\*\*\* el botón secundario en agrupaciones perimetrales y haga clic en **nuevo borde**.</span><span class="sxs-lookup"><span data-stu-id="2beff-113">Right-click **Edge pools**, and click **New Edge pool**.</span></span>
    
    <span data-ttu-id="2beff-114">![Definir el cuadro de diálogo nuevo grupo perimetral] (images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Definir el cuadro de diálogo nuevo grupo perimetral")</span><span class="sxs-lookup"><span data-stu-id="2beff-114">![Define the New Edge Pool dialog box](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Define the New Edge Pool dialog box")</span></span>

3.  <span data-ttu-id="2beff-115">Un grupo de servidores perimetrales puede ser un **grupo de varios equipos** o un **único grupo de equipos**.</span><span class="sxs-lookup"><span data-stu-id="2beff-115">An Edge pool can be a **Multiple computer pool** or **Single computer pool**.</span></span>
    
    <span data-ttu-id="2beff-116">![Definir el cuadro de diálogo FQDN del grupo de bordes] (images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Definir el cuadro de diálogo FQDN del grupo de bordes")</span><span class="sxs-lookup"><span data-stu-id="2beff-116">![Define the Edge Pool FQDN dialog box](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Define the Edge Pool FQDN dialog box")</span></span>

4.  <span data-ttu-id="2beff-117">En la página **seleccionar características** , no habilite la Federación ni la Federación XMPP.</span><span class="sxs-lookup"><span data-stu-id="2beff-117">On the **Select features** page, do not enable federation or XMPP federation.</span></span> <span data-ttu-id="2beff-118">La Federación y la Federación XMPP actualmente se enrutan a través del servidor perimetral antiguo de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2beff-118">Federation and XMPP federation are both currently routed through the legacy Lync Server 2010 Edge Server.</span></span> <span data-ttu-id="2beff-119">Estas características se configurarán en una fase posterior de la migración.</span><span class="sxs-lookup"><span data-stu-id="2beff-119">These features will be configured in a later phase of migration.</span></span>
    
    <span data-ttu-id="2beff-120">![Cuadro de diálogo Seleccionar características] (images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Cuadro de diálogo Seleccionar características")</span><span class="sxs-lookup"><span data-stu-id="2beff-120">![Select Features dialog box](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Select Features dialog box")</span></span>

5.  <span data-ttu-id="2beff-121">A continuación, siga completando las siguientes páginas del asistente: **FQDN externos**, **defina la dirección IP interna**y **defina la dirección IP externa**.</span><span class="sxs-lookup"><span data-stu-id="2beff-121">Next, continue completing the following wizard pages: **External FQDNs**, **Define the internal IP address**, and **Define the external IP address**.</span></span>

6.  <span data-ttu-id="2beff-122">En la página **definir el siguiente salto** , seleccione el director para el próximo salto del grupo de servidores perimetrales de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2beff-122">On the **Define the next hop** page, select the Director for the next hop of the Lync Server 2010 Edge pool.</span></span>
    
    <span data-ttu-id="2beff-123">![Definir el cuadro de diálogo siguiente del salto] (images/JJ205306.11baf3ea-74f5-4eb7-8650-b03b3b190416(OCS.15).jpg "Definir el cuadro de diálogo siguiente del salto")</span><span class="sxs-lookup"><span data-stu-id="2beff-123">![Define the Next Hop dialog box](images/JJ205306.11baf3ea-74f5-4eb7-8650-b03b3b190416(OCS.15).jpg "Define the Next Hop dialog box")</span></span>

7.  <span data-ttu-id="2beff-124">En la página **asociar grupos de servicios de media o front-end** , no asocie un grupo con este grupo de límites en este momento.</span><span class="sxs-lookup"><span data-stu-id="2beff-124">On the **Associate Front End or Mediation pools** page, do not associate a pool with this Edge pool at this time.</span></span> <span data-ttu-id="2beff-125">El tráfico multimedia externo está enrutado a través del servidor perimetral heredado de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="2beff-125">External media traffic is currently routed through the legacy Lync Server 2010 Edge Server.</span></span> <span data-ttu-id="2beff-126">Esta configuración se configurará en una fase posterior de la migración.</span><span class="sxs-lookup"><span data-stu-id="2beff-126">This setting will be configured in a later phase of migration.</span></span>
    
    <span data-ttu-id="2beff-127">![Cuadro de diálogo asociar grupos front-end] (images/JJ205306.fe0da887-7b51-4564-afc5-d57da95a2eb6(OCS.15).jpg "Cuadro de diálogo asociar grupos front-end")</span><span class="sxs-lookup"><span data-stu-id="2beff-127">![Associate Front End Pools dialog box](images/JJ205306.fe0da887-7b51-4564-afc5-d57da95a2eb6(OCS.15).jpg "Associate Front End Pools dialog box")</span></span>

8.  <span data-ttu-id="2beff-128">Haga clic en **Finalizar** y, a continuación, **publique** la topología.</span><span class="sxs-lookup"><span data-stu-id="2beff-128">Click **Finish** and then **Publish** the topology.</span></span>

9.  <span data-ttu-id="2beff-129">Siga los pasos que se indican en [instalar servidores perimetrales para Lync Server 2013](lync-server-2013-install-edge-servers.md) en la documentación de implementación para instalar los archivos en el nuevo servidor perimetral, configurar certificados e iniciar los servicios.</span><span class="sxs-lookup"><span data-stu-id="2beff-129">Follow the steps in [Install Edge Servers for Lync Server 2013](lync-server-2013-install-edge-servers.md) in the Deployment documentation to install the files on the new Edge Server, configure certificates, and start the services.</span></span>

<span data-ttu-id="2beff-130">Es muy importante seguir las directrices de los temas [implementar el acceso de usuarios externos en Lync Server 2013](lync-server-2013-deploying-external-user-access.md) en la documentación de implementación.</span><span class="sxs-lookup"><span data-stu-id="2beff-130">It’s very important that you follow the guidelines in the topics [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) in the Deployment documentation.</span></span> <span data-ttu-id="2beff-131">En esta sección se proporciona una mera información sobre las opciones de configuración al instalar estos roles de servidor.</span><span class="sxs-lookup"><span data-stu-id="2beff-131">This section merely provided some guidance on configuration settings when installing these server roles.</span></span>

<span data-ttu-id="2beff-132">Ahora debe implementar un servidor perimetral antiguo de Lync Server 2010 en paralelo con una implementación de servidor perimetral de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2beff-132">You should now have a legacy Lync Server 2010 Edge Server deployed in parallel with a Lync Server 2013 Edge server deployment.</span></span> <span data-ttu-id="2beff-133">Compruebe que las implementaciones se ejecutan correctamente y que se inician los servicios, y puede administrar cada implementación antes de pasar a la siguiente fase.</span><span class="sxs-lookup"><span data-stu-id="2beff-133">Verify that both deployments are running properly, services are started, and you can administer each deployment prior to moving to the next phase.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

