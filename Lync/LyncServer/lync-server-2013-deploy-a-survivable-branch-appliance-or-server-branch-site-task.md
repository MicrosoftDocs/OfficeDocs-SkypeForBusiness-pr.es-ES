---
title: Implementar una aplicación de sucursal con funciones de supervivencia o una tarea de sitio de sucursal de servidor
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy a Survivable Branch Appliance or Server - branch site task
ms:assetid: 7989ba29-0419-46dd-892c-4ad3238afd56
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398599(v=OCS.15)
ms:contentKeyID: 48184586
ms.date: 10/29/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 835de118f46dba61fe86ee3f412c55d945dfb2a9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521657"
---
# <a name="deploy-a-survivable-branch-appliance-or-server-with-lync-server-2013---branch-site-task"></a><span data-ttu-id="b75fc-102">Implementar una aplicación o un servidor de sucursal con funciones de supervivencia con Lync Server 2013: tarea de sitio de sucursal</span><span class="sxs-lookup"><span data-stu-id="b75fc-102">Deploy a Survivable Branch Appliance or Server with Lync Server 2013 - branch site task</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b75fc-103">_**Última modificación del tema:** 2014-10-28_</span><span class="sxs-lookup"><span data-stu-id="b75fc-103">_**Topic Last Modified:** 2014-10-28_</span></span>

<span data-ttu-id="b75fc-104">Realice uno de los dos procedimientos descritos en este tema en el sitio de sucursal, después de completar correctamente las tareas de [implementación de una aplicación o servidor de sucursal con funciones de supervivencia con las tareas de sitio central de Lync Server 2013-central](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md).</span><span class="sxs-lookup"><span data-stu-id="b75fc-104">Perform one of the two procedures described in this topic at the branch site, after successfully completing the tasks in [Deploying a Survivable Branch Appliance or Server with Lync Server 2013 - central site tasks](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md).</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="b75fc-105">Para llevar a cabo este procedimiento, debe ser miembro del grupo RTCUniversalSBATechnicians.</span><span class="sxs-lookup"><span data-stu-id="b75fc-105">To perform this procedure, you must be a member of the RTCUniversalSBATechnicians group.</span></span>



</div>

<div>

## <a name="to-deploy-the-survivable-branch-appliance"></a><span data-ttu-id="b75fc-106">Para implementar la aplicación de sucursal con funciones de supervivencia</span><span class="sxs-lookup"><span data-stu-id="b75fc-106">To deploy the Survivable Branch Appliance</span></span>

  - <span data-ttu-id="b75fc-107">El proveedor de aplicación de sucursal con funciones de supervivencia habilita la implementación de aplicaciones de sucursal con funciones de supervivencia mediante una interfaz de usuario (UI) Web.</span><span class="sxs-lookup"><span data-stu-id="b75fc-107">Survivable Branch Appliance deployment is enabled by the Survivable Branch Appliance vendor through a web user interface (UI).</span></span> <span data-ttu-id="b75fc-108">Para obtener información acerca de la implementación de la aplicación de sucursal con funciones de supervivencia, consulte la documentación del proveedor de la aplicación de sucursal con funciones de supervivencia.</span><span class="sxs-lookup"><span data-stu-id="b75fc-108">For information about deploying the Survivable Branch Appliance, see your Survivable Branch Appliance vendor documentation.</span></span>

</div>

<div>

## <a name="to-deploy-the-survivable-branch-server"></a><span data-ttu-id="b75fc-109">Para implementar el servidor de sucursal con funciones de supervivencia</span><span class="sxs-lookup"><span data-stu-id="b75fc-109">To deploy the Survivable Branch Server</span></span>

  - <span data-ttu-id="b75fc-110">Instale Lync Server 2013 en un equipo que ejecute Windows Server 2008 R2, Windows Server 2012 o Windows Server 2012 R2, del mismo modo que se instala cualquier otro rol de servidor de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b75fc-110">Install Lync Server 2013 on a computer running Windows Server 2008 R2, Windows Server 2012, or Windows Server 2012 R2, just as you would install any other Lync Server 2013 server role.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="b75fc-111">Para obtener información acerca de la instalación de Lync Server, consulte <A href="lync-server-2013-deploying-lync-server.md">Deploying Lync server 2013</A> en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="b75fc-111">For information about installing Lync Server, see <A href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

<span data-ttu-id="b75fc-112">**Siguiente paso**: [configuración de usuarios para la resistencia de sitios de sucursal en Lync Server 2013](lync-server-2013-configuring-users-for-branch-site-resiliency.md)</span><span class="sxs-lookup"><span data-stu-id="b75fc-112">**Next step**: [Configuring users for branch site resiliency in Lync Server 2013](lync-server-2013-configuring-users-for-branch-site-resiliency.md)</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b75fc-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b75fc-113">See Also</span></span>


[<span data-ttu-id="b75fc-114">Apéndice A: uso de cmdlets para implementar una aplicación de sucursal con funciones de supervivencia en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b75fc-114">Appendix A: Using cmdlets to deploy a Survivable Branch Appliance in Lync Server 2013</span></span>](lync-server-2013-appendix-a-using-cmdlets-to-deploy-a-survivable-branch-appliance.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

