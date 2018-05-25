---
title: SQL Server Reporting Services (requisitos previos no satisfechos)
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/26/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeploySSRSPrereqNotSatisfied
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6be29df-b882-4ba8-ba40-8062eb3bb14d
description: Esta página aparecerá si en la infraestructura no se ha implementado ningún servidor de supervisión. Eso indica que no se han cumplido los requisitos mínimos para implementar informes de servidores de supervisión.
ms.openlocfilehash: e55310f8767daa7fc2be42e97ee4b3e368d158a9
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2018
---
# <a name="sql-server-reporting-services-prerequisites-not-satisfied"></a><span data-ttu-id="64f14-104">SQL Server Reporting Services (requisitos previos no satisfechos)</span><span class="sxs-lookup"><span data-stu-id="64f14-104">SQL Server Reporting Services (Prerequisites Not Satisfied)</span></span>
 
<span data-ttu-id="64f14-p102">Esta página aparecerá si en la infraestructura no se ha implementado ningún servidor de supervisión. Eso indica que no se han cumplido los requisitos mínimos para implementar informes de servidores de supervisión.</span><span class="sxs-lookup"><span data-stu-id="64f14-p102">You will see this page if there is no Monitoring Server deployed in your infrastructure. This indicates that the minimum requirements for deploying Monitoring Server reports have not been met.</span></span> 
  
<span data-ttu-id="64f14-107">Para resolver este problema, asegúrese de tener un servidor de supervisión unido al dominio, que se define en el generador, y que se ha publicado la topología.</span><span class="sxs-lookup"><span data-stu-id="64f14-107">To resolve this issue, make sure that you have a Monitoring Server joined to the domain, that it is defined in Topology Builder, and that the topology has been published.</span></span> <span data-ttu-id="64f14-108">SQL Server Reporting Services también debe estar disponible en el servidor SQL Server e instalado como una característica en la base de datos del servidor de supervisión en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="64f14-108">SQL Server Reporting Services must also be available on the SQL Server, and installed as a feature into the Monitoring Server database on the SQL Server.</span></span> 
  
<span data-ttu-id="64f14-109">Para obtener información detallada, vea [Instalar informes de supervisión en Skype para Business Server 2015](../../deploy/deploy-monitoring/install-monitoring-reports.md) y [Deploying Monitoring](http://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).</span><span class="sxs-lookup"><span data-stu-id="64f14-109">For details, see [Install Monitoring Reports in Skype for Business Server 2015](../../deploy/deploy-monitoring/install-monitoring-reports.md) and [Deploying Monitoring](http://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).</span></span>
  

