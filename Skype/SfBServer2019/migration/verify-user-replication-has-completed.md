---
title: La comprobación de la replicación del usuario ha finalizado
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Al ejecutar el cmdlet Move-CsUser, puede experimentar un error porque la información de usuario entre los Servicios de dominio de Active Directory (AD DS) y las bases de datos de Skype Empresarial Server 2019 no están sincronizadas porque la replicación inicial está incompleta. El tiempo que se tarda en completar correctamente la sincronización inicial del servicio replicador de usuarios de Skype Empresarial Server 2019 depende del número de controladores de dominio hospedados en el bosque de Active Directory que hospeda el grupo de servidores de Skype Empresarial Server 2019. El proceso de sincronización inicial del servicio replicador de usuarios de Skype Empresarial Server 2019 se produce cuando el servidor front-end de Skype Empresarial Server 2019 se inicia por primera vez. Tras ello, la sincronización se basa en el intervalo del replicador de usuarios. Realice los siguientes pasos para verificar que se haya completado la replicación de usuario antes de ejecutar el cmdlet Move-CsUser.
ms.openlocfilehash: 5aa832216cc5eddce1d80cc9401ec9992c9edbf1
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751652"
---
# <a name="verify-user-replication-has-completed"></a><span data-ttu-id="7d075-107">La comprobación de la replicación del usuario ha finalizado</span><span class="sxs-lookup"><span data-stu-id="7d075-107">Verify user replication has completed</span></span>

<span data-ttu-id="7d075-108">Al ejecutar el cmdlet **Move-CsUser,** puede producirse un error si la información de usuario entre los Servicios de dominio de Active Directory (AD DS) y las bases de datos de Skype Empresarial Server 2019 no están sincronizadas porque la replicación inicial está incompleta.</span><span class="sxs-lookup"><span data-stu-id="7d075-108">When running the **Move-CsUser** cmdlet, you may experience a failure if user information between Active Directory Domain Services (AD DS) and the Skype for Business Server 2019 databases are out of sync because the initial replication is incomplete.</span></span> <span data-ttu-id="7d075-109">El tiempo que se tarda en completar correctamente la sincronización inicial del servicio replicador de usuarios de Skype Empresarial Server 2019 depende del número de controladores de dominio hospedados en el bosque de Active Directory que hospeda el grupo de servidores de Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="7d075-109">The time it takes for the successful completion of the Skype for Business Server 2019 User Replicator service's initial synchronization depends on the number of domain controllers that are hosted in the Active Directory forest that hosts the Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="7d075-110">El proceso de sincronización inicial del servicio replicador de usuarios de Skype Empresarial Server 2019 se produce cuando se inicia por primera vez el servidor front-end de Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="7d075-110">The Skype for Business Server 2019 User Replicator service initial synchronization process occurs when the Skype for Business Server 2019 Front End Server is started for the first time.</span></span> <span data-ttu-id="7d075-111">Después, la sincronización se basa en el intervalo de replicador de usuarios.</span><span class="sxs-lookup"><span data-stu-id="7d075-111">After that, the synchronization is based on the User Replicator interval.</span></span> <span data-ttu-id="7d075-112">Complete los pasos siguientes para comprobar que la replicación de usuarios se ha completado antes de ejecutar el cmdlet **Move-CsUser.**</span><span class="sxs-lookup"><span data-stu-id="7d075-112">Complete the following steps to verify that user replication has completed before running the **Move-CsUser** cmdlet.</span></span> 
  
### <a name="to-verify-that-user-replication-has-completed"></a><span data-ttu-id="7d075-113">Para comprobar que la replicación de usuarios se ha completado</span><span class="sxs-lookup"><span data-stu-id="7d075-113">To verify that user replication has completed</span></span>

1. <span data-ttu-id="7d075-114">Inicie sesión en el equipo en el que Topology Builder esté instalado como miembro del grupo Admins. del dominio y el grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="7d075-114">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>
    
2. <span data-ttu-id="7d075-115">Haga clic en el menú **Inicio** y, a continuación, haga clic en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="7d075-115">Click the **Start** menu, and then click **Run**.</span></span> 
    
3. <span data-ttu-id="7d075-116">Escriba **eventvwr.exe** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7d075-116">Enter **eventvwr.exe**, and then click **OK**.</span></span>
    
4. <span data-ttu-id="7d075-117">En el Visor de eventos, haga clic **en** Registros de aplicaciones y servicios para expandirlo y, a continuación, seleccione Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="7d075-117">In Event Viewer, click **Applications and Services logs** to expand it, and then select Skype for Business Server.</span></span> 
    
5. <span data-ttu-id="7d075-118">En el panel **Acciones**, haga clic en **Filtrar registro actual**.</span><span class="sxs-lookup"><span data-stu-id="7d075-118">In the **Actions** pane, click **Filter Current Log**.</span></span>
    
6. <span data-ttu-id="7d075-119">En la lista **Orígenes del evento**, haga clic en **LS User Replicator**.</span><span class="sxs-lookup"><span data-stu-id="7d075-119">From the **Event sources** list, click **LS User Replicator**.</span></span>
    
7. <span data-ttu-id="7d075-120">En **\<All Event IDs\>** , escriba **30024** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7d075-120">In **\<All Event IDs\>**, enter **30024**, and then click **OK**.</span></span> 
    
8. <span data-ttu-id="7d075-121">En la lista de eventos filtrados, en la pestaña **General,** busque una entrada que indica que la replicación de usuarios se ha completado correctamente.</span><span class="sxs-lookup"><span data-stu-id="7d075-121">In the filtered events list, on the **General** tab, look for an entry that states that user replication has completed successfully.</span></span> 
    

