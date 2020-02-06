---
title: La comprobación de la replicación de usuarios ha finalizado
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Al ejecutar el cmdlet Move-CsUser, puede experimentar un error porque la información de usuario entre los servicios de dominio de Active Directory (AD DS) y las bases de datos de Skype empresarial Server 2019 no está sincronizada porque la replicación inicial está incompleta. El tiempo que tarda la finalización satisfactoria de la sincronización inicial del servicio duplicador de usuarios de Skype empresarial Server 2019 depende de la cantidad de controladores de dominio que se hospeden en el bosque de Active Directory que aloje Skype empresarial. Grupo de servidores 2019. El proceso de sincronización inicial del servicio replicador de usuarios de Skype empresarial Server 2019 se produce cuando se inicia el servidor front-end de Skype empresarial Server 2019 por primera vez. Después, la sincronización se basa en el intervalo del replicador de usuarios. Complete los pasos siguientes para comprobar que la replicación de usuario se ha completado antes de ejecutar el cmdlet Move-CsUser.
ms.openlocfilehash: 31f4f9f1045367e376d4536df54c32be14580312
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812658"
---
# <a name="verify-user-replication-has-completed"></a><span data-ttu-id="b573c-107">La comprobación de la replicación de usuarios ha finalizado</span><span class="sxs-lookup"><span data-stu-id="b573c-107">Verify user replication has completed</span></span>

<span data-ttu-id="b573c-108">Al ejecutar el cmdlet **Move-CsUser** , puede experimentar un error si la información de usuario entre los servicios de dominio de Active Directory (AD DS) y las bases de datos de Skype empresarial Server 2019 no está sincronizada porque la replicación inicial está incompleta.</span><span class="sxs-lookup"><span data-stu-id="b573c-108">When running the **Move-CsUser** cmdlet, you may experience a failure if user information between Active Directory Domain Services (AD DS) and the Skype for Business Server 2019 databases are out of sync because the initial replication is incomplete.</span></span> <span data-ttu-id="b573c-109">El tiempo que tarda la finalización satisfactoria de la sincronización inicial del servicio duplicador de usuarios de Skype empresarial Server 2019 depende de la cantidad de controladores de dominio que se hospeden en el bosque de Active Directory que aloje Skype empresarial. Grupo de servidores 2019.</span><span class="sxs-lookup"><span data-stu-id="b573c-109">The time it takes for the successful completion of the Skype for Business Server 2019 User Replicator service's initial synchronization depends on the number of domain controllers that are hosted in the Active Directory forest that hosts the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="b573c-110">El proceso de sincronización inicial del servicio replicador de usuarios de Skype empresarial Server 2019 se produce cuando se inicia el servidor front-end de Skype empresarial Server 2019 por primera vez.</span><span class="sxs-lookup"><span data-stu-id="b573c-110">The Skype for Business Server 2019 User Replicator service initial synchronization process occurs when the Skype for Business Server 2019 Front End Server is started for the first time.</span></span> <span data-ttu-id="b573c-111">Después, la sincronización se basa en el intervalo del replicador de usuarios.</span><span class="sxs-lookup"><span data-stu-id="b573c-111">After that, the synchronization is based on the User Replicator interval.</span></span> <span data-ttu-id="b573c-112">Complete los pasos siguientes para comprobar que la replicación de usuario se ha completado antes de ejecutar el cmdlet **Move-CsUser** .</span><span class="sxs-lookup"><span data-stu-id="b573c-112">Complete the following steps to verify that user replication has completed before running the **Move-CsUser** cmdlet.</span></span> 
  
### <a name="to-verify-that-user-replication-has-completed"></a><span data-ttu-id="b573c-113">Para comprobar que la replicación de usuarios se ha completado</span><span class="sxs-lookup"><span data-stu-id="b573c-113">To verify that user replication has completed</span></span>

1. <span data-ttu-id="b573c-114">Inicie sesión en el equipo donde se encuentre instalado el Generador de topologías como miembro del grupo Administradores del dominio y el grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="b573c-114">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="b573c-115">Haga clic en el menú **Inicio** y, a continuación, en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="b573c-115">Click the **Start** menu, and then click **Run**.</span></span> 
    
3. <span data-ttu-id="b573c-116">Escriba **eventvwr. exe**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b573c-116">Enter **eventvwr.exe**, and then click **OK**.</span></span>
    
4. <span data-ttu-id="b573c-117">En el visor de eventos, haga clic en **registros de aplicaciones y servicios** para expandirlo y, a continuación, seleccione Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="b573c-117">In Event Viewer, click **Applications and Services logs** to expand it, and then select Skype for Business Server.</span></span> 
    
5. <span data-ttu-id="b573c-118">En el panel **acciones** , haga clic en **filtrar registro actual**.</span><span class="sxs-lookup"><span data-stu-id="b573c-118">In the **Actions** pane, click **Filter Current Log**.</span></span>
    
6. <span data-ttu-id="b573c-119">En la lista **orígenes de eventos** , haga clic en **replicador de usuarios de LS**.</span><span class="sxs-lookup"><span data-stu-id="b573c-119">From the **Event sources** list, click **LS User Replicator**.</span></span>
    
7. <span data-ttu-id="b573c-120">En \*\* \<todos los identificadores\>de evento\*\*, escriba **30024**y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b573c-120">In **\<All Event IDs\>**, enter **30024**, and then click **OK**.</span></span> 
    
8. <span data-ttu-id="b573c-121">En la lista eventos filtrados, en la pestaña **General** , busque una entrada que indique que la replicación de usuarios se ha completado correctamente.</span><span class="sxs-lookup"><span data-stu-id="b573c-121">In the filtered events list, on the **General** tab, look for an entry that states that user replication has completed successfully.</span></span> 
    

