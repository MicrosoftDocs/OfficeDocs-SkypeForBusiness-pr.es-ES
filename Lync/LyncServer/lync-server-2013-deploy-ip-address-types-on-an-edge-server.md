---
title: 'Lync Server 2013: implementar tipos de direcciones IP en un servidor perimetral'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy IP address types on an Edge Server
ms:assetid: 6e2fe7e8-6e90-4d1a-8fc5-e3be92c46571
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204984(v=OCS.15)
ms:contentKeyID: 48184435
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ea42103886a317c02e36c68c8b067fef157ebc9f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150899"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploy-ip-address-types-on-an-edge-server-for-lync-server-2013"></a><span data-ttu-id="398b2-102">Implementar tipos de direcciones IP en un servidor perimetral para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="398b2-102">Deploy IP address types on an Edge Server for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="398b2-103">_**Última modificación del tema:** 2012-06-14_</span><span class="sxs-lookup"><span data-stu-id="398b2-103">_**Topic Last Modified:** 2012-06-14_</span></span>

<span data-ttu-id="398b2-104">Mediante el generador de topologías, lleve a cabo los pasos del siguiente procedimiento para implementar tipos de direcciones IP en un servidor perimetral.</span><span class="sxs-lookup"><span data-stu-id="398b2-104">Using Topology Builder, perform the steps in the following procedure to deploy IP address types on an Edge Server.</span></span>

<div>

## <a name="to-deploy-ip-address-types-on-an-edge-server"></a><span data-ttu-id="398b2-105">Para implementar tipos de direcciones IP en un servidor perimetral</span><span class="sxs-lookup"><span data-stu-id="398b2-105">To deploy IP address types on an Edge Server</span></span>

1.  <span data-ttu-id="398b2-106">En el generador de topologías, en grupos de servidores **perimetrales**, haga clic con el botón secundario en el servidor dentro de un grupo y, después, seleccione **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="398b2-106">In Topology Builder, under **Edge pools**, right-click the server within a pool, and then select **Edit Properties**.</span></span> <span data-ttu-id="398b2-107">(También puede seleccionar el servidor y hacer clic en **Editar propiedades** en el menú **Acción**).</span><span class="sxs-lookup"><span data-stu-id="398b2-107">(Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>

2.  <span data-ttu-id="398b2-p102">En la ventana **Editar propiedades**, seleccione la configuración de dirección IP que quiera admitir. En las siguientes figuras se muestra una configuración de pila dual para la interfaz interna y la interfaz externa.</span><span class="sxs-lookup"><span data-stu-id="398b2-p102">In the **Edit Properties** window, select the IP address configuration that you want to support. The following figures show a dual stack configuration for the internal interface and the external interface.</span></span>
    
    <span data-ttu-id="398b2-110">**Interfaz interna del servidor perimetral**</span><span class="sxs-lookup"><span data-stu-id="398b2-110">**Dual stacked Edge Server internal interface**</span></span>
    
    <span data-ttu-id="398b2-111">![Página de propiedades generales de Lync Server](images/JJ204984.5b0883ee-b9f2-4a21-91a9-3286d0beb63b(OCS.15).png "Página de propiedades generales de Lync Server")</span><span class="sxs-lookup"><span data-stu-id="398b2-111">![Lync Server general properties page](images/JJ204984.5b0883ee-b9f2-4a21-91a9-3286d0beb63b(OCS.15).png "Lync Server general properties page")</span></span>
    
    <span data-ttu-id="398b2-112">**Interfaz de servidor perimetral externo interfaz de pila dual**</span><span class="sxs-lookup"><span data-stu-id="398b2-112">**Dual stacked Edge Server external interface**</span></span>
    
    <span data-ttu-id="398b2-113">![Página de configuración externa y próximo salto de Lync Server](images/JJ204984.2aa00ce2-ba50-40aa-bbf1-78636016daf9(OCS.15).png "Página de configuración externa y próximo salto de Lync Server")</span><span class="sxs-lookup"><span data-stu-id="398b2-113">![Lync Server next hop/external configuration page](images/JJ204984.2aa00ce2-ba50-40aa-bbf1-78636016daf9(OCS.15).png "Lync Server next hop/external configuration page")</span></span>

3.  <span data-ttu-id="398b2-114">Debe proporcionar las direcciones internas y externas apropiadas para cada tipo de dirección que seleccione.</span><span class="sxs-lookup"><span data-stu-id="398b2-114">For each address type that you select, you must supply appropriate internal and external addresses.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

