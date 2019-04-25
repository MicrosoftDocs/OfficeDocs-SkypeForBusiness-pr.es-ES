---
title: La comprobación de la replicación de usuarios ha finalizado
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Cuando se ejecuta el cmdlet Move-CsUser, puede experimentar un error debido a que la información de usuario entre los servicios de dominio de Active Directory (AD DS) y el Skype para bases de datos de negocio Server 2019 están sincronizados debido a que la replicación inicial está incompleta. El tiempo necesario para la finalización correcta de la Skype para la sincronización inicial del servicio de Replicador de usuarios de Business Server 2019 depende del número de controladores de dominio que se hospedan en el bosque de Active Directory que hospeda el Skype para la empresa Grupo de servidores de servidor 2019. El Skype para el proceso de sincronización inicial del servicio de Replicador de usuarios de Business Server 2019 se produce cuando se inicia el Skype para profesionales de 2019 Front-End Server por primera vez. Después de, la sincronización, a continuación, se basa en el intervalo del replicador de usuarios. Complete los pasos siguientes para comprobar la replicación de usuarios ha completado antes de ejecutar el cmdlet Move-CsUser.
ms.openlocfilehash: bab54e91ebda7a10804980e368e05bb58ff911ff
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231339"
---
# <a name="verify-user-replication-has-completed"></a><span data-ttu-id="f5bca-107">La comprobación de la replicación de usuarios ha finalizado</span><span class="sxs-lookup"><span data-stu-id="f5bca-107">Verify user replication has completed</span></span>

<span data-ttu-id="f5bca-108">Cuando se ejecuta el cmdlet **Move-CsUser** , puede experimentar un error si la información de usuario entre los servicios de dominio de Active Directory (AD DS) y el Skype para bases de datos de negocio Server 2019 está sincronizado debido a que la replicación inicial está incompleta.</span><span class="sxs-lookup"><span data-stu-id="f5bca-108">When running the **Move-CsUser** cmdlet, you may experience a failure if user information between Active Directory Domain Services (AD DS) and the Skype for Business Server 2019 databases are out of sync because the initial replication is incomplete.</span></span> <span data-ttu-id="f5bca-109">El tiempo necesario para la finalización correcta de la Skype para la sincronización inicial del servicio de Replicador de usuarios de Business Server 2019 depende del número de controladores de dominio que se hospedan en el bosque de Active Directory que hospeda el Skype para la empresa Grupo de servidores de servidor 2019.</span><span class="sxs-lookup"><span data-stu-id="f5bca-109">The time it takes for the successful completion of the Skype for Business Server 2019 User Replicator service's initial synchronization depends on the number of domain controllers that are hosted in the Active Directory forest that hosts the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="f5bca-110">El Skype para el proceso de sincronización inicial del servicio de Replicador de usuarios de Business Server 2019 se produce cuando se inicia el Skype para profesionales de 2019 Front-End Server por primera vez.</span><span class="sxs-lookup"><span data-stu-id="f5bca-110">The Skype for Business Server 2019 User Replicator service initial synchronization process occurs when the Skype for Business Server 2019 Front End Server is started for the first time.</span></span> <span data-ttu-id="f5bca-111">Después de, la sincronización se basa en el intervalo del replicador de usuarios.</span><span class="sxs-lookup"><span data-stu-id="f5bca-111">After that, the synchronization is based on the User Replicator interval.</span></span> <span data-ttu-id="f5bca-112">Complete los pasos siguientes para comprobar que la replicación de usuarios ha completado antes de ejecutar el cmdlet **Move-CsUser** .</span><span class="sxs-lookup"><span data-stu-id="f5bca-112">Complete the following steps to verify that user replication has completed before running the **Move-CsUser** cmdlet.</span></span> 
  
### <a name="to-verify-that-user-replication-has-completed"></a><span data-ttu-id="f5bca-113">Para comprobar que la replicación de usuarios ha completado</span><span class="sxs-lookup"><span data-stu-id="f5bca-113">To verify that user replication has completed</span></span>

1. <span data-ttu-id="f5bca-114">Inicie sesión en el equipo donde se encuentre instalado el Generador de topologías como miembro del grupo Administradores del dominio y el grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="f5bca-114">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="f5bca-115">Haga clic en el menú **Inicio** y, a continuación, haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="f5bca-115">Click the **Start** menu, and then click **Run**.</span></span> 
    
3. <span data-ttu-id="f5bca-116">Escriba **eventvwr.exe**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f5bca-116">Enter **eventvwr.exe**, and then click **OK**.</span></span>
    
4. <span data-ttu-id="f5bca-117">En el Visor de eventos, haga clic en **registros de aplicaciones y servicios** para expandirlo y, a continuación, seleccione Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="f5bca-117">In Event Viewer, click **Applications and Services logs** to expand it, and then select Skype for Business Server.</span></span> 
    
5. <span data-ttu-id="f5bca-118">En el panel **acciones** , haga clic en **Filtrar registro actual**.</span><span class="sxs-lookup"><span data-stu-id="f5bca-118">In the **Actions** pane, click **Filter Current Log**.</span></span>
    
6. <span data-ttu-id="f5bca-119">En la lista de **orígenes de eventos** , haga clic en **LS User Replicator**.</span><span class="sxs-lookup"><span data-stu-id="f5bca-119">From the **Event sources** list, click **LS User Replicator**.</span></span>
    
7. <span data-ttu-id="f5bca-120">En \*\* \<todos los identificadores de evento\>\*\*, escriba **30024**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f5bca-120">In **\<All Event IDs\>**, enter **30024**, and then click **OK**.</span></span> 
    
8. <span data-ttu-id="f5bca-121">En la lista de eventos filtrados, en la ficha **General** , busque una entrada que indica que la replicación de usuario se ha completado correctamente.</span><span class="sxs-lookup"><span data-stu-id="f5bca-121">In the filtered events list, on the **General** tab, look for an entry that states that user replication has completed successfully.</span></span> 
    

