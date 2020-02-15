---
title: Quitar BackCompatSite
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove BackCompatSite
ms:assetid: 039650e3-541b-45c2-a682-c4fa08423118
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204637(v=OCS.15)
ms:contentKeyID: 48183265
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7f613f6e96261d256c4c1f15fd2161648eed4fe
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008936"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-backcompatsite"></a><span data-ttu-id="d806d-102">Quitar BackCompatSite</span><span class="sxs-lookup"><span data-stu-id="d806d-102">Remove BackCompatSite</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d806d-103">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="d806d-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="d806d-104">Una vez que se desactivaron todos los grupos de servidores y se desinstalaron todos los servidores perimetrales, ejecute el asistente para la combinación del Generador de topologías a fin de quitar **BackCompatSite**.</span><span class="sxs-lookup"><span data-stu-id="d806d-104">After all pools are deactivated and all Edge Servers have been uninstalled, run the Topology Builder Merge wizard to remove the **BackCompatSite**.</span></span>

<div>

## <a name="to-remove-backcompat-site-from-topology-builder"></a><span data-ttu-id="d806d-105">Para quitar el sitio BackCompat del Generador de topologías</span><span class="sxs-lookup"><span data-stu-id="d806d-105">To remove BackCompat site from Topology Builder</span></span>

1.  <span data-ttu-id="d806d-106">Abra una implementación existente del Generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="d806d-106">Open an existing deployment from Topology Builder.</span></span>

2.  <span data-ttu-id="d806d-107">En el menú **Acción**, haga clic en **Combinar topología de 2007**.</span><span class="sxs-lookup"><span data-stu-id="d806d-107">In the **Action** menu, click **Merge 2007 R2 Topology**.</span></span>

3.  <span data-ttu-id="d806d-108">Haga clic en \*\*Siguiente \*\* para continuar.</span><span class="sxs-lookup"><span data-stu-id="d806d-108">Click **Next** to continue.</span></span>

4.  <span data-ttu-id="d806d-p101">En la página **Especificar servidor perimetral heredado**, asegúrese de que la lista de servidores perimetrales esté vacía. Si no lo está, utilice el botón **Quitar** para quitar todos los servidores perimetrales heredados y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d806d-p101">On the **Specify Legacy Edge** page, ensure that list of Edge Servers is empty. If the list is not empty, use the **Remove** button to remove all the legacy Edge Servers, and then click **Next**.</span></span>
    
    <span data-ttu-id="d806d-111">![Asistente para combinar topología, especificar página de configuración perimetral](images/JJ204637.fb35a59a-711e-4259-b177-7311df1fed3c(OCS.15).jpg "Asistente para combinar topología, especificar página de configuración perimetral")</span><span class="sxs-lookup"><span data-stu-id="d806d-111">![Merge Topology Wizard, Specify Edge Setup page](images/JJ204637.fb35a59a-711e-4259-b177-7311df1fed3c(OCS.15).jpg "Merge Topology Wizard, Specify Edge Setup page")</span></span>  

5.  <span data-ttu-id="d806d-112">En la página **Especificar puerto SIP interno**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d806d-112">On the **Specify Internal SIP port setting** page, click **Next**.</span></span>

6.  <span data-ttu-id="d806d-113">En la página **Resumen** , haga clic en **siguiente** para comenzar a combinar las topologías para quitar el sitio heredado.</span><span class="sxs-lookup"><span data-stu-id="d806d-113">On the **Summary** page, click **Next** to begin merging the topologies to remove the legacy site.</span></span>

7.  <span data-ttu-id="d806d-114">En la columna **Estado**, compruebe que el valor sea **Correcto** y haga clic en **Finalizar** para cerrar el asistente.</span><span class="sxs-lookup"><span data-stu-id="d806d-114">In the **Status** column, verify that the value is **Success** and then click **Finish** to close the wizard.</span></span>

8.  <span data-ttu-id="d806d-115">En el panel izquierdo de Topology Builder, expanda BackCompatSite y compruebe que no se muestre ningún servidor.</span><span class="sxs-lookup"><span data-stu-id="d806d-115">In the left pane of Topology Builder, expand the BackCompatSite and ensure no servers are listed.</span></span>

9.  <span data-ttu-id="d806d-116">Haga clic con el botón secundario en **BackCompatSite** y, a continuación, haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="d806d-116">Right-click the **BackCompatSite**, and then click **Delete**.</span></span>

10. <span data-ttu-id="d806d-117">En el **Generador de topologías**, seleccione el primer nodo **Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="d806d-117">In **Topology Builder**, select the top-most node **Lync Server**.</span></span>

11. <span data-ttu-id="d806d-118">En el menú **Acción**, seleccione **Publicar topología** y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d806d-118">From the **Action** menu, select **Publish Topology** and then click **Next**.</span></span>

12. <span data-ttu-id="d806d-119">Cuando el **Asistente para publicación** haya finalizado, haga clic en **Finalizar** para cerrar el asistente.</span><span class="sxs-lookup"><span data-stu-id="d806d-119">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

