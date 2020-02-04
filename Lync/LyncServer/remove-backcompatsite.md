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
ms.openlocfilehash: ccfcd48c575e300b12fe08611d6f898749041478
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727200"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-backcompatsite"></a><span data-ttu-id="e964c-102">Quitar BackCompatSite</span><span class="sxs-lookup"><span data-stu-id="e964c-102">Remove BackCompatSite</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e964c-103">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="e964c-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="e964c-104">Una vez desactivados todos los grupos y todos los servidores perimetrales se han desinstalado, ejecute el Asistente para combinar el generador de topología para quitar el **BackCompatSite**.</span><span class="sxs-lookup"><span data-stu-id="e964c-104">After all pools are deactivated and all Edge Servers have been uninstalled, run the Topology Builder Merge wizard to remove the **BackCompatSite**.</span></span>

<div>

## <a name="to-remove-backcompat-site-from-topology-builder"></a><span data-ttu-id="e964c-105">Para quitar el sitio de BackCompat del generador de topología</span><span class="sxs-lookup"><span data-stu-id="e964c-105">To remove BackCompat site from Topology Builder</span></span>

1.  <span data-ttu-id="e964c-106">Abra una implementación existente desde el generador de topología.</span><span class="sxs-lookup"><span data-stu-id="e964c-106">Open an existing deployment from Topology Builder.</span></span>

2.  <span data-ttu-id="e964c-107">En el menú **acción** , haga clic en **fusionar topología R2 de 2007**.</span><span class="sxs-lookup"><span data-stu-id="e964c-107">In the **Action** menu, click **Merge 2007 R2 Topology**.</span></span>

3.  <span data-ttu-id="e964c-108">Haga clic en **Siguiente** para continuar.</span><span class="sxs-lookup"><span data-stu-id="e964c-108">Click **Next** to continue.</span></span>

4.  <span data-ttu-id="e964c-109">En la página **especificar borde heredado** , asegúrese de que la lista de servidores perimetrales esté vacía.</span><span class="sxs-lookup"><span data-stu-id="e964c-109">On the **Specify Legacy Edge** page, ensure that list of Edge Servers is empty.</span></span> <span data-ttu-id="e964c-110">Si la lista no está vacía, use el botón **quitar** para quitar todos los servidores perimetrales heredados y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e964c-110">If the list is not empty, use the **Remove** button to remove all the legacy Edge Servers, and then click **Next**.</span></span>
    
    <span data-ttu-id="e964c-111">![Asistente para combinar topología, especificar página de configuración de Edge](images/JJ204637.fb35a59a-711e-4259-b177-7311df1fed3c(OCS.15).jpg "Asistente para combinar topología, especificar página de configuración de Edge")</span><span class="sxs-lookup"><span data-stu-id="e964c-111">![Merge Topology Wizard, Specify Edge Setup page](images/JJ204637.fb35a59a-711e-4259-b177-7311df1fed3c(OCS.15).jpg "Merge Topology Wizard, Specify Edge Setup page")</span></span>  

5.  <span data-ttu-id="e964c-112">En la página **especificar la configuración interna del puerto SIP** , haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e964c-112">On the **Specify Internal SIP port setting** page, click **Next**.</span></span>

6.  <span data-ttu-id="e964c-113">En la página **Resumen** , haga clic en **siguiente** para empezar a combinar las topologías para quitar el sitio heredado.</span><span class="sxs-lookup"><span data-stu-id="e964c-113">On the **Summary** page, click **Next** to begin merging the topologies to remove the legacy site.</span></span>

7.  <span data-ttu-id="e964c-114">En la columna **Estado** , compruebe que el valor es **correcto** y, a continuación, haga clic en **Finalizar** para cerrar el asistente.</span><span class="sxs-lookup"><span data-stu-id="e964c-114">In the **Status** column, verify that the value is **Success** and then click **Finish** to close the wizard.</span></span>

8.  <span data-ttu-id="e964c-115">En el panel izquierdo del generador de topologías, expanda el BackCompatSite y asegúrese de que no hay servidores en la lista.</span><span class="sxs-lookup"><span data-stu-id="e964c-115">In the left pane of Topology Builder, expand the BackCompatSite and ensure no servers are listed.</span></span>

9.  <span data-ttu-id="e964c-116">Haga clic con el botón secundario en el **BackCompatSite**y luego haga clic en **eliminar**.</span><span class="sxs-lookup"><span data-stu-id="e964c-116">Right-click the **BackCompatSite**, and then click **Delete**.</span></span>

10. <span data-ttu-id="e964c-117">En el **generador de topologías**, seleccione el nodo de nivel superior de **Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="e964c-117">In **Topology Builder**, select the top-most node **Lync Server**.</span></span>

11. <span data-ttu-id="e964c-118">En el menú **acción** , seleccione **publicar topología** y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e964c-118">From the **Action** menu, select **Publish Topology** and then click **Next**.</span></span>

12. <span data-ttu-id="e964c-119">Cuando finalice el Asistente para la **publicación** , haga clic en **Finalizar** para cerrar el asistente.</span><span class="sxs-lookup"><span data-stu-id="e964c-119">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

