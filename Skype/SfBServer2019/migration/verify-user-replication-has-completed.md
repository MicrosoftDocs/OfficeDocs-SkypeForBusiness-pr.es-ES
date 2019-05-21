---
title: La comprobación de la replicación de usuarios ha finalizado
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Al ejecutar el cmdlet Move-CsUser, puede experimentar un error porque la información de usuario entre los servicios de dominio de Active Directory (AD DS) y las bases de datos de Skype empresarial Server 2019 no está sincronizada porque la replicación inicial está incompleta. El tiempo que tarda la finalización satisfactoria de la sincronización inicial del servicio duplicador de usuarios de Skype empresarial Server 2019 depende de la cantidad de controladores de dominio que se hospeden en el bosque de Active Directory que aloje Skype empresarial. Grupo de servidores 2019. El proceso de sincronización inicial del servicio replicador de usuarios de Skype empresarial Server 2019 se produce cuando se inicia el servidor front-end de Skype empresarial Server 2019 por primera vez. Después, la sincronización se basa en el intervalo del replicador de usuarios. Complete los pasos siguientes para comprobar que la replicación de usuario se ha completado antes de ejecutar el cmdlet Move-CsUser.
ms.openlocfilehash: d5d0462ec2886c73fb7286860eea2c89e0fea9fb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280649"
---
# <a name="verify-user-replication-has-completed"></a><span data-ttu-id="5bc77-107">La comprobación de la replicación de usuarios ha finalizado</span><span class="sxs-lookup"><span data-stu-id="5bc77-107">Verify user replication has completed</span></span>

<span data-ttu-id="5bc77-108">Al ejecutar el cmdlet **Move-CsUser** , puede experimentar un error si la información de usuario entre los servicios de dominio de Active Directory (AD DS) y las bases de datos de Skype empresarial Server 2019 no está sincronizada porque la replicación inicial está incompleta.</span><span class="sxs-lookup"><span data-stu-id="5bc77-108">When running the **Move-CsUser** cmdlet, you may experience a failure if user information between Active Directory Domain Services (AD DS) and the Skype for Business Server 2019 databases are out of sync because the initial replication is incomplete.</span></span> <span data-ttu-id="5bc77-109">El tiempo que tarda la finalización satisfactoria de la sincronización inicial del servicio duplicador de usuarios de Skype empresarial Server 2019 depende de la cantidad de controladores de dominio que se hospeden en el bosque de Active Directory que aloje Skype empresarial. Grupo de servidores 2019.</span><span class="sxs-lookup"><span data-stu-id="5bc77-109">The time it takes for the successful completion of the Skype for Business Server 2019 User Replicator service's initial synchronization depends on the number of domain controllers that are hosted in the Active Directory forest that hosts the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="5bc77-110">El proceso de sincronización inicial del servicio replicador de usuarios de Skype empresarial Server 2019 se produce cuando se inicia el servidor front-end de Skype empresarial Server 2019 por primera vez.</span><span class="sxs-lookup"><span data-stu-id="5bc77-110">The Skype for Business Server 2019 User Replicator service initial synchronization process occurs when the Skype for Business Server 2019 Front End Server is started for the first time.</span></span> <span data-ttu-id="5bc77-111">Después, la sincronización se basa en el intervalo del replicador de usuarios.</span><span class="sxs-lookup"><span data-stu-id="5bc77-111">After that, the synchronization is based on the User Replicator interval.</span></span> <span data-ttu-id="5bc77-112">Complete los pasos siguientes para comprobar que la replicación de usuario se ha completado antes de ejecutar el cmdlet **Move-CsUser** .</span><span class="sxs-lookup"><span data-stu-id="5bc77-112">Complete the following steps to verify that user replication has completed before running the **Move-CsUser** cmdlet.</span></span> 
  
### <a name="to-verify-that-user-replication-has-completed"></a><span data-ttu-id="5bc77-113">Para comprobar que la replicación de usuarios se ha completado</span><span class="sxs-lookup"><span data-stu-id="5bc77-113">To verify that user replication has completed</span></span>

1. <span data-ttu-id="5bc77-114">Inicie sesión en el equipo donde se encuentre instalado el Generador de topologías como miembro del grupo Administradores del dominio y el grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="5bc77-114">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="5bc77-115">Haga clic en el menú **Inicio** y, a continuación, en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="5bc77-115">Click the **Start** menu, and then click **Run**.</span></span> 
    
3. <span data-ttu-id="5bc77-116">Escriba **eventvwr. exe**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5bc77-116">Enter **eventvwr.exe**, and then click **OK**.</span></span>
    
4. <span data-ttu-id="5bc77-117">En el visor de eventos, haga clic en **registros de aplicaciones y servicios** para expandirlo y, a continuación, seleccione Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="5bc77-117">In Event Viewer, click **Applications and Services logs** to expand it, and then select Skype for Business Server.</span></span> 
    
5. <span data-ttu-id="5bc77-118">En el panel **acciones** , haga clic en **filtrar registro actual**.</span><span class="sxs-lookup"><span data-stu-id="5bc77-118">In the **Actions** pane, click **Filter Current Log**.</span></span>
    
6. <span data-ttu-id="5bc77-119">En la lista **orígenes de eventos** , haga clic en replicador de usuarios de **LS**.</span><span class="sxs-lookup"><span data-stu-id="5bc77-119">From the **Event sources** list, click **LS User Replicator**.</span></span>
    
7. <span data-ttu-id="5bc77-120">En \*\* \<todos los\>identificadores de evento\*\*, escriba **30024**y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5bc77-120">In **\<All Event IDs\>**, enter **30024**, and then click **OK**.</span></span> 
    
8. <span data-ttu-id="5bc77-121">En la lista eventos filtrados, en la pestaña **General** , busque una entrada que indique que la replicación de usuarios se ha completado correctamente.</span><span class="sxs-lookup"><span data-stu-id="5bc77-121">In the filtered events list, on the **General** tab, look for an entry that states that user replication has completed successfully.</span></span> 
    

