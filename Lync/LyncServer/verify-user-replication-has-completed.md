---
title: La comprobación de la replicación de usuarios ha finalizado
description: Compruebe que la replicación de usuarios se ha completado.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify user replication has completed
ms:assetid: 119e9896-45e5-4f8b-af43-7b09360ada0b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204680(v=OCS.15)
ms:contentKeyID: 48183441
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60bca44fcce811c29b1633bd4d3a39f832851885
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555486"
---
# <a name="verify-user-replication-has-completed"></a><span data-ttu-id="8498a-103">La comprobación de la replicación de usuarios ha finalizado</span><span class="sxs-lookup"><span data-stu-id="8498a-103">Verify user replication has completed</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8498a-104">_**Última modificación del tema:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="8498a-104">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="8498a-105">Cuando se ejecuta el cmdlet **Move-CsUser** , puede experimentar un error porque la información de usuario entre los servicios de dominio de Active Directory (AD DS) y las bases de datos de Lync Server 2013 no está sincronizada porque la replicación inicial está incompleta.</span><span class="sxs-lookup"><span data-stu-id="8498a-105">When running the **Move-CsUser** cmdlet, you may experience a failure because user information between Active Directory Domain Services (AD DS) and the Lync Server 2013 databases are out of sync because the initial replication is incomplete.</span></span> <span data-ttu-id="8498a-106">El tiempo que tarda la finalización correcta de la sincronización inicial del servicio replicador de usuarios de Lync Server 2013 depende del número de controladores de dominio que se hospedan en el bosque de Active Directory que hospeda el grupo de servidores de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8498a-106">The time it takes for the successful completion of the Lync Server 2013 User Replicator service's initial synchronization depends on the number of domain controllers that are hosted in the Active Directory forest that hosts the Lync Server 2013 pool.</span></span> <span data-ttu-id="8498a-107">El proceso de sincronización inicial del servicio replicador de usuarios de Lync Server 2013 se produce cuando el servidor front-end de Lync Server 2013 se inicia por primera vez.</span><span class="sxs-lookup"><span data-stu-id="8498a-107">The Lync Server 2013 User Replicator service initial synchronization process occurs when the Lync Server 2013 Front End Server is started for the first time.</span></span> <span data-ttu-id="8498a-108">Posteriormente, la sincronización se basa en el intervalo del User Replicator.</span><span class="sxs-lookup"><span data-stu-id="8498a-108">After that, the synchronization is then based on the User Replicator interval.</span></span> <span data-ttu-id="8498a-109">Realice los siguientes pasos para verificar que se haya completado la replicación de usuario antes de ejecutar el cmdlet **Move-CsUser**.</span><span class="sxs-lookup"><span data-stu-id="8498a-109">Complete the following steps to verify user replication has completed before running the **Move-CsUser** cmdlet.</span></span>

<div>

## <a name="to-verify-user-replication-has-completed"></a><span data-ttu-id="8498a-110">Para comprobar que la replicación de usuarios ha finalizado</span><span class="sxs-lookup"><span data-stu-id="8498a-110">To verify user replication has completed</span></span>

1.  <span data-ttu-id="8498a-111">Inicie sesión en el equipo en el que Topology Builder esté instalado como miembro del grupo Admins. del dominio y el grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="8498a-111">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="8498a-112">Haga clic en el menú **Inicio** y, a continuación, haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="8498a-112">Click the **Start** menu, and then click **Run**.</span></span>

3.  <span data-ttu-id="8498a-113">Escriba **eventvwr.exe** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8498a-113">Enter **eventvwr.exe** and then click **OK**.</span></span>

4.  <span data-ttu-id="8498a-114">En el Visor de eventos, haga clic en **Registros de aplicaciones y servicios** para expandirlo y, a continuación, seleccione Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8498a-114">In Event Viewer, click **Applications and Services logs** to expand it, and then select Lync Server.</span></span>

5.  <span data-ttu-id="8498a-115">En el panel **Acciones**, haga clic en **Filtrar registro actual**.</span><span class="sxs-lookup"><span data-stu-id="8498a-115">In the **Actions** pane click **Filter Current Log**.</span></span>

6.  <span data-ttu-id="8498a-116">En la lista **Orígenes del evento**, haga clic en **LS User Replicator**.</span><span class="sxs-lookup"><span data-stu-id="8498a-116">From the **Event sources** list, click **LS User Replicator**.</span></span>

7.  <span data-ttu-id="8498a-117">En **\<All Event IDs\>** escriba **30024** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8498a-117">In **\<All Event IDs\>** enter **30024** and then click **OK**.</span></span>

8.  <span data-ttu-id="8498a-118">En la lista de eventos filtrados, en la pestaña **General**, busque una entrada que indique que la replicación de usuarios finalizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="8498a-118">In the filtered events list, on the **General** tab, look for an entry that states user replication has completed successfully.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

