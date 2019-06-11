---
title: La comprobación de la replicación de usuarios ha finalizado
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Verify user replication has completed
ms:assetid: 119e9896-45e5-4f8b-af43-7b09360ada0b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204680(v=OCS.15)
ms:contentKeyID: 48183441
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6e96d3231fbbfe9ce9062e948e6b60de6521720e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849827"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-user-replication-has-completed"></a><span data-ttu-id="aebd8-102">La comprobación de la replicación de usuarios ha finalizado</span><span class="sxs-lookup"><span data-stu-id="aebd8-102">Verify user replication has completed</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aebd8-103">_**Última modificación del tema:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="aebd8-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="aebd8-104">Al ejecutar el cmdlet **Move-CsUser** , puede experimentar un error porque la información del usuario entre los servicios de dominio de Active Directory (AD DS) y las bases de datos de Lync Server 2013 no está sincronizada porque la replicación inicial está incompleta.</span><span class="sxs-lookup"><span data-stu-id="aebd8-104">When running the **Move-CsUser** cmdlet, you may experience a failure because user information between Active Directory Domain Services (AD DS) and the Lync Server 2013 databases are out of sync because the initial replication is incomplete.</span></span> <span data-ttu-id="aebd8-105">El tiempo que tarda la finalización satisfactoria de la sincronización inicial del servicio duplicador de usuarios de Lync Server 2013 depende del número de controladores de dominio que se hospeden en el bosque de Active Directory que hospeda el grupo de servidores de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="aebd8-105">The time it takes for the successful completion of the Lync Server 2013 User Replicator service's initial synchronization depends on the number of domain controllers that are hosted in the Active Directory forest that hosts the Lync Server 2013 pool.</span></span> <span data-ttu-id="aebd8-106">El proceso de sincronización inicial del servicio replicador de usuarios de Lync Server 2013 se produce cuando el servidor front-end de Lync Server 2013 se inicia por primera vez.</span><span class="sxs-lookup"><span data-stu-id="aebd8-106">The Lync Server 2013 User Replicator service initial synchronization process occurs when the Lync Server 2013 Front End Server is started for the first time.</span></span> <span data-ttu-id="aebd8-107">Después, la sincronización se basa en el intervalo del replicador de usuarios.</span><span class="sxs-lookup"><span data-stu-id="aebd8-107">After that, the synchronization is then based on the User Replicator interval.</span></span> <span data-ttu-id="aebd8-108">Complete los pasos siguientes para comprobar que la replicación de usuario se ha completado antes de ejecutar el cmdlet **Move-CsUser** .</span><span class="sxs-lookup"><span data-stu-id="aebd8-108">Complete the following steps to verify user replication has completed before running the **Move-CsUser** cmdlet.</span></span>

<div>

## <a name="to-verify-user-replication-has-completed"></a><span data-ttu-id="aebd8-109">Para comprobar que la replicación de usuario se ha completado</span><span class="sxs-lookup"><span data-stu-id="aebd8-109">To verify user replication has completed</span></span>

1.  <span data-ttu-id="aebd8-110">Inicie sesión en el equipo donde se encuentre instalado el Generador de topologías como miembro del grupo Administradores del dominio y el grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="aebd8-110">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="aebd8-111">Haga clic en el menú **Inicio** y, a continuación, en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="aebd8-111">Click the **Start** menu, and then click **Run**.</span></span>

3.  <span data-ttu-id="aebd8-112">Escribe **eventvwr. exe** y haz clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="aebd8-112">Enter **eventvwr.exe** and then click **OK**.</span></span>

4.  <span data-ttu-id="aebd8-113">En el visor de eventos, haga clic en **registros de aplicaciones y servicios** para expandirlo y, a continuación, seleccione Lync Server.</span><span class="sxs-lookup"><span data-stu-id="aebd8-113">In Event Viewer, click **Applications and Services logs** to expand it, and then select Lync Server.</span></span>

5.  <span data-ttu-id="aebd8-114">En el panel **acciones** , haga clic en **filtrar registro actual**.</span><span class="sxs-lookup"><span data-stu-id="aebd8-114">In the **Actions** pane click **Filter Current Log**.</span></span>

6.  <span data-ttu-id="aebd8-115">En la lista **orígenes de eventos** , haga clic en replicador de usuarios de **LS**.</span><span class="sxs-lookup"><span data-stu-id="aebd8-115">From the **Event sources** list, click **LS User Replicator**.</span></span>

7.  <span data-ttu-id="aebd8-116">En \*\* \<todos los\> identificadores de evento\*\* , escriba **30024** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="aebd8-116">In **\<All Event IDs\>** enter **30024** and then click **OK**.</span></span>

8.  <span data-ttu-id="aebd8-117">En la lista eventos filtrados, en la pestaña **General** , busque una entrada que indique que la replicación de usuarios se ha completado correctamente.</span><span class="sxs-lookup"><span data-stu-id="aebd8-117">In the filtered events list, on the **General** tab, look for an entry that states user replication has completed successfully.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

