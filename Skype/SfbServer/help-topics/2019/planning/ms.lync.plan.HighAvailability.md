---
title: Alta disponibilidad (herramienta de planeación)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: El esquema de alta disponibilidad principal para la mayoría de los roles de servidor en Skype Empresarial Server se basa en la redundancia de servidores mediante agrupación. Si se produce un error en un servidor que ejecuta un rol de servidor determinado, los demás servidores del grupo que ejecutan el mismo rol asumen la carga de dicho servidor.
ms.openlocfilehash: 36b2d9fad34e16daf11fb7539f73c815264a55a6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093318"
---
# <a name="high-availability-planning-tool"></a><span data-ttu-id="f6c33-104">Alta disponibilidad (herramienta de planeación)</span><span class="sxs-lookup"><span data-stu-id="f6c33-104">High Availability (Planning Tool)</span></span>
 
<span data-ttu-id="f6c33-105">El esquema de alta disponibilidad principal para la mayoría de los roles de servidor en Skype Empresarial Server se basa en la redundancia de servidores mediante agrupación.</span><span class="sxs-lookup"><span data-stu-id="f6c33-105">The main high availability scheme for most server roles in Skype for Business Server is based on server redundancy via pooling.</span></span> <span data-ttu-id="f6c33-106">Si se produce un error en un servidor que ejecuta un rol de servidor determinado, los demás servidores del grupo que ejecutan el mismo rol asumen la carga de dicho servidor.</span><span class="sxs-lookup"><span data-stu-id="f6c33-106">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span>
  
<span data-ttu-id="f6c33-107">Skype Empresarial Server requiere al menos dos servidores front-end para habilitar la alta disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="f6c33-107">Skype for Business Server requires at least two Front End Servers in order to enable high availability.</span></span> <span data-ttu-id="f6c33-108">La Herramienta de planeación usa los siguientes criterios para determinar si agregará servidores adicionales para admitir la alta disponibilidad:</span><span class="sxs-lookup"><span data-stu-id="f6c33-108">The Planning Tool uses the following criteria to determine if it will add extra servers in order to support high availability:</span></span>
  
- <span data-ttu-id="f6c33-109">Si la implementación contiene dos o más servidores front-end, la herramienta de planeación no agrega un servidor adicional.</span><span class="sxs-lookup"><span data-stu-id="f6c33-109">If the deployment contains two or more Front End Servers, the Planning Tool does not add an extra server.</span></span>
    
- <span data-ttu-id="f6c33-110">Si la implementación contiene servidor perimetral, se agrega un servidor adicional.</span><span class="sxs-lookup"><span data-stu-id="f6c33-110">If the deployment contains Edge Server, an additional server is added.</span></span> 
    
- <span data-ttu-id="f6c33-111">Si la implementación contiene chat persistente, la herramienta de planeación agregará un servidor adicional, pero no aumentará el número de grupo.</span><span class="sxs-lookup"><span data-stu-id="f6c33-111">If the deployment contains Persistent Chat, the planning tool will add an extra server, but not increase the pool number.</span></span> <span data-ttu-id="f6c33-112">Por ejemplo, si la implementación ya contiene cuatro servidores, la Herramienta de planeación sugerirá agregar un servidor adicional (para un total de cinco servidores), pero mantendrá un único grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="f6c33-112">For example, if the deployment already contains four servers, the Planning Tool will suggest adding an additional server (for a total of five servers) but will maintain a single pool.</span></span> 

    > [!NOTE] 
    > <span data-ttu-id="f6c33-113">El chat persistente está disponible en Skype Empresarial Server 2015, pero ya no se admite en Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="f6c33-113">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="f6c33-114">La misma funcionalidad está disponible en Teams.</span><span class="sxs-lookup"><span data-stu-id="f6c33-114">The same functionality is available in Teams.</span></span> <span data-ttu-id="f6c33-115">Para obtener más información, [vea Skype Empresarial to Microsoft Teams upgrade](/MicrosoftTeams/upgrade-start-here).</span><span class="sxs-lookup"><span data-stu-id="f6c33-115">For more information, see [Skype for Business to Microsoft Teams upgrade](/MicrosoftTeams/upgrade-start-here).</span></span> <span data-ttu-id="f6c33-116">Si necesita usar el chat persistente, las opciones son migrar usuarios que requieren esta funcionalidad a Teams o seguir usando Skype Empresarial Server 2015.</span><span class="sxs-lookup"><span data-stu-id="f6c33-116">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams or continue using Skype for Business Server 2015.</span></span> 

    
<span data-ttu-id="f6c33-117">La Herramienta de planeación también agrega una base de datos SQL reflejo para todas las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="f6c33-117">The Planning Tool also adds a mirror SQL database for all databases.</span></span> <span data-ttu-id="f6c33-118">Por ejemplo, si hay una base de datos de SQL Server front-end, la Herramienta de planeación agregará la otra base de datos como la base de datos reflejada para esta y la nombrará como la base de datos reflejada SQL front-end.</span><span class="sxs-lookup"><span data-stu-id="f6c33-118">For example, if there is a Front End SQL Server database, the Planning Tool will add the other database as the mirror database for this one and name it as the "Front End mirror SQL database.</span></span>
  
<span data-ttu-id="f6c33-119">Para obtener más información sobre cómo preparar el entorno para la alta disponibilidad, vea [Plan for high availability and disaster recovery in Skype for Business Server](../../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="f6c33-119">For more details about preparing your environment for high availability, see [Plan for high availability and disaster recovery in Skype for Business Server](../../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
