---
title: Alta disponibilidad (herramienta de planeación)
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.plan.HighAvailability
- ms.lync.plan.HighAvailability
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14a897b3-2406-46c7-b08f-490085b3d048
description: El esquema principal de alta disponibilidad para la mayoría de roles de servidor de Skype para Business Server se basa en la redundancia de servidores a través de la agrupación. Si falla un servidor que está ejecutando un determinado rol de servidor, los demás servidores del grupo que estén ejecutando el mismo rol asumirán su carga.
ms.openlocfilehash: 9948fbc4f1daff73afa020b83357a26c185d7785
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/20/2018
ms.locfileid: "19977267"
---
# <a name="high-availability-planning-tool"></a><span data-ttu-id="e200e-104">Alta disponibilidad (herramienta de planeación)</span><span class="sxs-lookup"><span data-stu-id="e200e-104">High Availability (Planning Tool)</span></span>
 
<span data-ttu-id="e200e-105">El esquema principal de alta disponibilidad para la mayoría de roles de servidor de Skype para Business Server se basa en la redundancia de servidores a través de la agrupación.</span><span class="sxs-lookup"><span data-stu-id="e200e-105">The main high availability scheme for most server roles in Skype for Business Server is based on server redundancy via pooling.</span></span> <span data-ttu-id="e200e-106">Si falla un servidor que está ejecutando un determinado rol de servidor, los demás servidores del grupo que estén ejecutando el mismo rol asumirán su carga.</span><span class="sxs-lookup"><span data-stu-id="e200e-106">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span>
  
<span data-ttu-id="e200e-107">Skype para Business Server requiere al menos dos servidores Front-End con el fin de habilitar la alta disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="e200e-107">Skype for Business Server requires at least two Front End Servers in order to enable high availability.</span></span> <span data-ttu-id="e200e-108">La herramienta de planeación utiliza los siguientes criterios para determinar si agregará servidores adicionales con el fin de ofrecer una alta disponibilidad:</span><span class="sxs-lookup"><span data-stu-id="e200e-108">The Planning Tool uses the following criteria to determine if it will add extra servers in order to support high availability:</span></span>
  
- <span data-ttu-id="e200e-109">Si la implementación contiene dos o más servidores Front-End, la herramienta de planeación no se agrega un servidor adicional.</span><span class="sxs-lookup"><span data-stu-id="e200e-109">If the deployment contains two or more Front End Servers, the Planning Tool does not add an extra server.</span></span>
    
- <span data-ttu-id="e200e-110">Si la implementación contiene el servidor perimetral, se agrega un servidor adicional.</span><span class="sxs-lookup"><span data-stu-id="e200e-110">If the deployment contains Edge Server, an additional server is added.</span></span> 
    
- <span data-ttu-id="e200e-111">Si la implementación contiene Chat persistente, la herramienta de planeación de agregar un servidor adicional, pero no aumentar el número de grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="e200e-111">If the deployment contains Persistent Chat, the planning tool will add an extra server, but not increase the pool number.</span></span> <span data-ttu-id="e200e-112">Por ejemplo, si la implementación ya contiene cuatro servidores, la herramienta de planeación sugiere agregar un servidor adicional (para un total de cinco servidores) pero mantendrá un único grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="e200e-112">For example, if the deployment already contains four servers, the Planning Tool will suggest adding an additional server (for a total of five servers) but will maintain a single pool.</span></span> 
    
<span data-ttu-id="e200e-113">La herramienta de planeación también agrega una base de datos de reflejo SQL para todas las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="e200e-113">The Planning Tool also adds a mirror SQL database for all databases.</span></span> <span data-ttu-id="e200e-114">Por ejemplo, si hay una base de datos de SQL Server de Front-End, la herramienta de planeación agregará la otra base de datos como la base de datos reflejada para este uno y asígnele el nombre como el "Front-End SQL base de datos reflejada.</span><span class="sxs-lookup"><span data-stu-id="e200e-114">For example, if there is a Front End SQL Server database, the Planning Tool will add the other database as the mirror database for this one and name it as the "Front End mirror SQL database.</span></span>
  
<span data-ttu-id="e200e-115">Para obtener más información acerca de cómo preparar el entorno para alta disponibilidad, consulte [Plan de alta disponibilidad y recuperación ante desastres en Skype para Business Server](../../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="e200e-115">For more details about preparing your environment for high availability, see [Plan for high availability and disaster recovery in Skype for Business Server](../../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  

