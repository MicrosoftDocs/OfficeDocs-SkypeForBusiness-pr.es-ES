---
title: 'Lync Server 2013: Implementar tipos de dirección IP en un servidor perimetral'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploy IP address types on an Edge Server
ms:assetid: 6e2fe7e8-6e90-4d1a-8fc5-e3be92c46571
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204984(v=OCS.15)
ms:contentKeyID: 48184435
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a094a39fd74ab30ee1dd3a5a3da4e777bcf7e338
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835573"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-ip-address-types-on-an-edge-server-for-lync-server-2013"></a><span data-ttu-id="790e3-102">Implementar tipos de dirección IP en un servidor perimetral para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="790e3-102">Deploy IP address types on an Edge Server for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="790e3-103">_**Última modificación del tema:** 2012-06-14_</span><span class="sxs-lookup"><span data-stu-id="790e3-103">_**Topic Last Modified:** 2012-06-14_</span></span>

<span data-ttu-id="790e3-104">Con el generador de topologías, siga los pasos que se indican en el siguiente procedimiento para implementar tipos de direcciones IP en un servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="790e3-104">Using Topology Builder, perform the steps in the following procedure to deploy IP address types on an Edge Server.</span></span>

<div>

## <a name="to-deploy-ip-address-types-on-an-edge-server"></a><span data-ttu-id="790e3-105">Para implementar tipos de direcciones IP en un servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="790e3-105">To deploy IP address types on an Edge Server</span></span>

1.  <span data-ttu-id="790e3-106">En el generador de topologías, en **grupos de límites**, haga clic con el botón secundario en el servidor dentro de un grupo y seleccione **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="790e3-106">In Topology Builder, under **Edge pools**, right-click the server within a pool, and then select **Edit Properties**.</span></span> <span data-ttu-id="790e3-107">(También puede seleccionar el servidor y, a continuación, hacer clic en **Editar propiedades** en el menú **acción** ).</span><span class="sxs-lookup"><span data-stu-id="790e3-107">(Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>

2.  <span data-ttu-id="790e3-p102">En la ventana **Editar propiedades**, seleccione la configuración de dirección IP que quiera admitir. En las siguientes figuras se muestra una configuración de pila dual para la interfaz interna y la interfaz externa.</span><span class="sxs-lookup"><span data-stu-id="790e3-p102">In the **Edit Properties** window, select the IP address configuration that you want to support. The following figures show a dual stack configuration for the internal interface and the external interface.</span></span>
    
    <span data-ttu-id="790e3-110">**Interfaz interna del servidor perimetral de pila dual**</span><span class="sxs-lookup"><span data-stu-id="790e3-110">**Dual stacked Edge Server internal interface**</span></span>
    
    <span data-ttu-id="790e3-111">![Página de propiedades generales de Lync Server] (images/JJ204984.5b0883ee-b9f2-4a21-91a9-3286d0beb63b(OCS.15).png "Página de propiedades generales de Lync Server")</span><span class="sxs-lookup"><span data-stu-id="790e3-111">![Lync Server general properties page](images/JJ204984.5b0883ee-b9f2-4a21-91a9-3286d0beb63b(OCS.15).png "Lync Server general properties page")</span></span>
    
    <span data-ttu-id="790e3-112">**Interfaz externa del servidor perimetral de pila dual**</span><span class="sxs-lookup"><span data-stu-id="790e3-112">**Dual stacked Edge Server external interface**</span></span>
    
    <span data-ttu-id="790e3-113">![Página de siguiente salto/configuración externa de Lync Server] (images/JJ204984.2aa00ce2-ba50-40aa-bbf1-78636016daf9(OCS.15).png "Página de siguiente salto/configuración externa de Lync Server")</span><span class="sxs-lookup"><span data-stu-id="790e3-113">![Lync Server next hop/external configuration page](images/JJ204984.2aa00ce2-ba50-40aa-bbf1-78636016daf9(OCS.15).png "Lync Server next hop/external configuration page")</span></span>

3.  <span data-ttu-id="790e3-114">Es preciso proporcionar las direcciones internas y externas apropiadas para cada tipo de dirección que seleccione.</span><span class="sxs-lookup"><span data-stu-id="790e3-114">For each address type that you select, you must supply appropriate internal and external addresses.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

