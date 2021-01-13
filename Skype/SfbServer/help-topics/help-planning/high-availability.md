---
title: Alta disponibilidad (Herramienta de planeación)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/8/2016
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
description: El esquema de alta disponibilidad principal para la mayoría de los roles de servidor en Skype Empresarial Server 2015 se basa en la redundancia de servidores a través de la agrupación. Si se produce un error en un servidor que ejecuta un rol de servidor determinado, los demás servidores del grupo que ejecutan el mismo rol asumen la carga de dicho servidor.
ms.openlocfilehash: a866784f94dd2e2c861aa93c482b40946da7ac7d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49829010"
---
# <a name="high-availability-planning-tool"></a><span data-ttu-id="85640-104">Alta disponibilidad (Herramienta de planeación)</span><span class="sxs-lookup"><span data-stu-id="85640-104">High Availability (Planning Tool)</span></span>
 
<span data-ttu-id="85640-105">El esquema de alta disponibilidad principal para la mayoría de los roles de servidor en Skype Empresarial Server 2015 se basa en la redundancia de servidores a través de la agrupación.</span><span class="sxs-lookup"><span data-stu-id="85640-105">The main high availability scheme for most server roles in Skype for Business Server 2015 is based on server redundancy via pooling.</span></span> <span data-ttu-id="85640-106">Si se produce un error en un servidor que ejecuta un rol de servidor determinado, los demás servidores del grupo que ejecutan el mismo rol asumen la carga de dicho servidor.</span><span class="sxs-lookup"><span data-stu-id="85640-106">If a server running a certain server role fails, the other servers in the pool running the same role take the load of that server.</span></span>
  
<span data-ttu-id="85640-107">Skype Empresarial Server 2015 requiere al menos dos servidores front-end para habilitar la alta disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="85640-107">Skype for Business Server 2015 requires at least two Front End Servers in order to enable high availability.</span></span> <span data-ttu-id="85640-108">La Herramienta de planeación usa los siguientes criterios para determinar si agregará servidores adicionales para admitir la alta disponibilidad:</span><span class="sxs-lookup"><span data-stu-id="85640-108">The Planning Tool uses the following criteria to determine if it will add extra servers in order to support high availability:</span></span>
  
- <span data-ttu-id="85640-109">Si la implementación contiene dos o más servidores front-end, la Herramienta de planeación no agrega un servidor adicional.</span><span class="sxs-lookup"><span data-stu-id="85640-109">If the deployment contains two or more Front End Servers, the Planning Tool does not add an extra server.</span></span>
    
- <span data-ttu-id="85640-110">Si la implementación contiene un servidor perimetral, se agrega un servidor adicional.</span><span class="sxs-lookup"><span data-stu-id="85640-110">If the deployment contains Edge Server, an additional server is added.</span></span> 
    
- <span data-ttu-id="85640-111">Si la implementación contiene chat persistente, la herramienta de planeación agregará un servidor adicional, pero no aumentará el número de grupo.</span><span class="sxs-lookup"><span data-stu-id="85640-111">If the deployment contains Persistent Chat, the planning tool will add an extra server, but not increase the pool number.</span></span> <span data-ttu-id="85640-112">Por ejemplo, si la implementación ya contiene cuatro servidores, la Herramienta de planeación sugerirá agregar un servidor adicional (para un total de cinco servidores), pero mantendrá un único grupo.</span><span class="sxs-lookup"><span data-stu-id="85640-112">For example, if the deployment already contains four servers, the Planning Tool will suggest adding an additional server (for a total of five servers) but will maintain a single pool.</span></span> 
    
<span data-ttu-id="85640-113">La Herramienta de planeación también agrega una base de datos SQL reflejo para todas las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="85640-113">The Planning Tool also adds a mirror SQL database for all databases.</span></span> <span data-ttu-id="85640-114">Por ejemplo, si hay una base de datos de SQL Server front-end, la Herramienta de planeación agregará la otra base de datos como la base de datos reflejada para esta y la nombrará como la base de datos reflejada SQL front-end.</span><span class="sxs-lookup"><span data-stu-id="85640-114">For example, if there is a Front End SQL Server database, the Planning Tool will add the other database as the mirror database for this one and name it as the "Front End mirror SQL database.</span></span>
  
<span data-ttu-id="85640-115">Para obtener más información sobre cómo preparar su entorno para la alta disponibilidad, consulte [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="85640-115">For more details about preparing your environment for high availability, see [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  

