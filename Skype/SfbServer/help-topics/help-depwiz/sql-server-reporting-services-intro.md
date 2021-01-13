---
title: SQL Server Reporting Services (introducción)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeploySSRSIntro
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f3cda686-6301-419c-af68-b49cc785e5fc
description: Cada grupo de servidores front-end y cada aplicación de sucursal con funciones de supervivencia solo pueden tener asociado un servidor de supervisión. Si se ha habilitado la supervisión en el sitio, el servidor de supervisión proporciona datos e informes del registro de detalles de las llamadas (CDR) y de calidad de la experiencia (QoE).
ms.openlocfilehash: 6a45508c3f95da02df966e4d9905020af1b9f9b4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49829580"
---
# <a name="sql-server-reporting-services-intro"></a><span data-ttu-id="d1b26-104">SQL Server Reporting Services (introducción)</span><span class="sxs-lookup"><span data-stu-id="d1b26-104">SQL Server Reporting Services (Intro)</span></span>
 
<span data-ttu-id="d1b26-p102">Cada grupo de servidores front-end y cada aplicación de sucursal con funciones de supervivencia solo pueden tener asociado un servidor de supervisión. Si se ha habilitado la supervisión en el sitio, el servidor de supervisión proporciona datos e informes del registro de detalles de las llamadas (CDR) y de calidad de la experiencia (QoE).</span><span class="sxs-lookup"><span data-stu-id="d1b26-p102">Each Front End pool and Survivable Branch Appliance can have only one Monitoring Server associated with it. When monitoring is enabled for the site, Monitoring Server provides call detail recording (CDR) and Quality of Experience (QoE) data collection and reporting.</span></span>
  
<span data-ttu-id="d1b26-107">Todos los grupos de servidores de un sitio y los grupos de servidores de varios sitios centrales pueden usar el mismo servidor de supervisión, siempre que el uso no sobrepase la capacidad del servidor de supervisión.</span><span class="sxs-lookup"><span data-stu-id="d1b26-107">All pools at a site and the pools of multiple central sites can use the same Monitoring Server, if usage does not exceed the capacity of the Monitoring Server.</span></span> <span data-ttu-id="d1b26-108">Para obtener más información sobre cómo diseñar una topología que admita la supervisión, consulte Asociar un almacén de supervisión con un grupo de servidores [front-end en Skype Empresarial Server 2015](../../deploy/deploy-monitoring/associate-a-monitoring-store.md) en la documentación sobre implementación.</span><span class="sxs-lookup"><span data-stu-id="d1b26-108">For details about designing a topology to support monitoring, see [Associate a monitoring store with a Front End pool in Skype for Business Server 2015](../../deploy/deploy-monitoring/associate-a-monitoring-store.md) in the Deployment documentation.</span></span>
  

