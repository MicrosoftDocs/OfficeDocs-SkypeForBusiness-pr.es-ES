---
title: La comprobación de la replicación de usuarios ha finalizado
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify user replication has completed
ms:assetid: 199dc9de-b555-468f-a42a-9e92ea6c9053
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204712(v=OCS.15)
ms:contentKeyID: 48183524
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e51ff7889b97a58298256cc1a1de3a5d4f901608
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518007"
---
# <a name="verify-user-replication-has-completed"></a><span data-ttu-id="9d597-102">La comprobación de la replicación de usuarios ha finalizado</span><span class="sxs-lookup"><span data-stu-id="9d597-102">Verify user replication has completed</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9d597-103">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="9d597-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="9d597-104">Cuando se ejecuta el cmdlet **Move-CsLegacyUser** , puede experimentar un error debido a la información de usuario entre los servicios de dominio de Active Directory (AD DS) y las bases de datos de Lync Server 2013 que no están sincronizadas porque la replicación inicial está incompleta.</span><span class="sxs-lookup"><span data-stu-id="9d597-104">When running the **Move-CsLegacyUser** cmdlet, you may experience a failure due to user information between Active Directory Domain Services (AD DS) and the Lync Server 2013 databases being out of sync because the initial replication is incomplete.</span></span> <span data-ttu-id="9d597-105">El tiempo que tarda la finalización correcta de la sincronización inicial del servicio replicador de usuarios de Lync Server 2013 depende del número de controladores de dominio que se hospedan en el bosque de Active Directory que hospeda el grupo de servidores de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9d597-105">The time it takes for the successful completion of the Lync Server 2013 User Replicator service's initial synchronization depends on the number of domain controllers that are hosted in the Active Directory forest that hosts the Lync Server 2013 pool.</span></span> <span data-ttu-id="9d597-106">El proceso de sincronización inicial del servicio replicador de usuarios de Lync Server 2013 se produce cuando el servidor front-end de Lync Server 2013 se inicia por primera vez.</span><span class="sxs-lookup"><span data-stu-id="9d597-106">The Lync Server 2013 User Replicator service initial synchronization process occurs when the Lync Server 2013 Front End Server is started for the first time.</span></span> <span data-ttu-id="9d597-107">Tras ello, la sincronización se basa en el intervalo del replicador de usuarios.</span><span class="sxs-lookup"><span data-stu-id="9d597-107">After that, the synchronization is then based on the User Replicator interval.</span></span> <span data-ttu-id="9d597-108">Complete los siguientes pasos para comprobar que la replicación de usuarios se ha completado antes de ejecutar el cmdlet **Move-CsLegacyUser**.</span><span class="sxs-lookup"><span data-stu-id="9d597-108">Complete the following steps to verify user replication has completed before running the **Move-CsLegacyUser** cmdlet.</span></span>

<div>

## <a name="to-verify-that-user-replication-has-completed"></a><span data-ttu-id="9d597-109">Para comprobar que la replicación de usuarios se ha completado</span><span class="sxs-lookup"><span data-stu-id="9d597-109">To verify that user replication has completed</span></span>

1.  <span data-ttu-id="9d597-110">En el servidor front-end de Lync Server 2013, haga clic en el menú **Inicio** y, a continuación, haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="9d597-110">From the Lync Server 2013 Front End server, click the **Start** menu, and then click **Run**.</span></span>

2.  <span data-ttu-id="9d597-111">Escriba **eventvwr.exe** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9d597-111">Enter **eventvwr.exe** and then click **OK**.</span></span>

3.  <span data-ttu-id="9d597-112">En el Visor de eventos, haga clic en **Registros de aplicaciones y servicios** para expandirlo y, a continuación, seleccione Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9d597-112">In Event Viewer, click **Applications and Services logs** to expand it, and then select Lync Server.</span></span>

4.  <span data-ttu-id="9d597-113">En el panel **Acciones**, haga clic en **Filtrar registro actual**.</span><span class="sxs-lookup"><span data-stu-id="9d597-113">In the **Actions** pane click **Filter Current Log**.</span></span>

5.  <span data-ttu-id="9d597-114">En la lista **Orígenes del evento**, haga clic en **LS User Replicator**.</span><span class="sxs-lookup"><span data-stu-id="9d597-114">From the **Event sources** list, click **LS User Replicator**.</span></span>

6.  <span data-ttu-id="9d597-115">En **\<All Event IDs\>** escriba **30024** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9d597-115">In **\<All Event IDs\>** enter **30024** and then click **OK**.</span></span>

7.  <span data-ttu-id="9d597-116">En la lista de eventos filtrados, en la pestaña **General**, busque una entrada que indique que la replicación de usuarios finalizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="9d597-116">In the filtered events list, on the **General** tab, look for an entry that states user replication has completed successfully.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

