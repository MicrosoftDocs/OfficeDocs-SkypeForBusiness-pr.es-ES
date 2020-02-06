---
title: High Availability (Planning Tool)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.plan.HighAvailability
- ms.lync.plan.HighAvailability
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14a897b3-2406-46c7-b08f-490085b3d048
ROBOTS: NOINDEX, NOFOLLOW
description: El esquema de alta disponibilidad principal para la mayoría de los roles de servidor de Skype empresarial Server se basa en la redundancia de los servidores a través de la agrupación. Si falla un servidor que está ejecutando un determinado rol de servidor, los demás servidores del grupo que estén ejecutando el mismo rol asumirán su carga.
ms.openlocfilehash: 328d269e6d6694dc26be66bd3894094770562726
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41797181"
---
# <a name="high-availability-planning-tool"></a><span data-ttu-id="ed6e3-104">High Availability (Planning Tool)</span><span class="sxs-lookup"><span data-stu-id="ed6e3-104">High Availability (Planning Tool)</span></span>
 
<span data-ttu-id="ed6e3-105">El esquema de alta disponibilidad principal para la mayoría de los roles de servidor de Skype empresarial Server se basa en la redundancia de los servidores a través de la agrupación.</span><span class="sxs-lookup"><span data-stu-id="ed6e3-105">The main high availability scheme for most server roles in Skype for Business Server is based on server redundancy via pooling.</span></span> <span data-ttu-id="ed6e3-106">Si falla un servidor que está ejecutando un determinado rol de servidor, los demás servidores del grupo que estén ejecutando el mismo rol asumirán su carga.</span><span class="sxs-lookup"><span data-stu-id="ed6e3-106">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span>
  
<span data-ttu-id="ed6e3-107">Para permitir una alta disponibilidad, Skype empresarial Server requiere al menos dos servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="ed6e3-107">Skype for Business Server requires at least two Front End Servers in order to enable high availability.</span></span> <span data-ttu-id="ed6e3-108">La herramienta de planeación usa los siguientes criterios para determinar si agregará servidores adicionales para admitir una alta disponibilidad:</span><span class="sxs-lookup"><span data-stu-id="ed6e3-108">The Planning Tool uses the following criteria to determine if it will add extra servers in order to support high availability:</span></span>
  
- <span data-ttu-id="ed6e3-109">Si la implementación contiene dos o más servidores front-end, la herramienta de planeación no agrega un servidor adicional.</span><span class="sxs-lookup"><span data-stu-id="ed6e3-109">If the deployment contains two or more Front End Servers, the Planning Tool does not add an extra server.</span></span>
    
- <span data-ttu-id="ed6e3-110">Si la implementación contiene un servidor perimetral, se agrega un servidor adicional.</span><span class="sxs-lookup"><span data-stu-id="ed6e3-110">If the deployment contains Edge Server, an additional server is added.</span></span> 
    
- <span data-ttu-id="ed6e3-111">Si la implementación contiene una conversación persistente, la herramienta de planificación agregará un servidor adicional, pero no aumentará el número de la agrupación.</span><span class="sxs-lookup"><span data-stu-id="ed6e3-111">If the deployment contains Persistent Chat, the planning tool will add an extra server, but not increase the pool number.</span></span> <span data-ttu-id="ed6e3-112">Por ejemplo, si la implementación ya contiene cuatro servidores, la herramienta de planeación sugerirá que se agregue un servidor adicional (para un total de cinco servidores), pero que mantendrá un único grupo.</span><span class="sxs-lookup"><span data-stu-id="ed6e3-112">For example, if the deployment already contains four servers, the Planning Tool will suggest adding an additional server (for a total of five servers) but will maintain a single pool.</span></span> 

    > [!NOTE] 
    > <span data-ttu-id="ed6e3-113">Chat persistente está disponible en Skype empresarial Server 2015, pero ya no es compatible con Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="ed6e3-113">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="ed6e3-114">La misma funcionalidad está disponible en Teams.</span><span class="sxs-lookup"><span data-stu-id="ed6e3-114">The same functionality is available in Teams.</span></span> <span data-ttu-id="ed6e3-115">Para obtener más información, consulte [actualización de Skype empresarial a Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/upgrade-start-here).</span><span class="sxs-lookup"><span data-stu-id="ed6e3-115">For more information, see [Skype for Business to Microsoft Teams upgrade](https://docs.microsoft.com/MicrosoftTeams/upgrade-start-here).</span></span> <span data-ttu-id="ed6e3-116">Si necesita usar una conversación persistente, su elección es migrar los usuarios que necesitan esta funcionalidad a teams o seguir usando Skype empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="ed6e3-116">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams or continue using Skype for Business Server 2015.</span></span> 

    
<span data-ttu-id="ed6e3-117">La herramienta de planeación también agrega una base de datos SQL de reflejo para todas las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="ed6e3-117">The Planning Tool also adds a mirror SQL database for all databases.</span></span> <span data-ttu-id="ed6e3-118">Por ejemplo, si hay una base de datos de SQL Server front end, la herramienta de planeación agregará la otra base de datos como la base de datos reflejada para esta y la asignaremos el nombre "base de datos SQL de reflejo front-end.</span><span class="sxs-lookup"><span data-stu-id="ed6e3-118">For example, if there is a Front End SQL Server database, the Planning Tool will add the other database as the mirror database for this one and name it as the "Front End mirror SQL database.</span></span>
  
<span data-ttu-id="ed6e3-119">Para obtener más información sobre cómo preparar el entorno para una alta disponibilidad, consulte [planear la alta disponibilidad y la recuperación ante desastres en Skype empresarial Server](../../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="ed6e3-119">For more details about preparing your environment for high availability, see [Plan for high availability and disaster recovery in Skype for Business Server](../../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  

