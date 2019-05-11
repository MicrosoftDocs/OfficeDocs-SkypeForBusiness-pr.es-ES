---
title: SQL Server Reporting Services (requisitos previos no satisfechos)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: 78bc27491c69f0532411567eded61ad3a9f17fa2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33925176"
---
# <a name="sql-server-reporting-services-prerequisites-not-satisfied"></a><span data-ttu-id="46e08-104">SQL Server Reporting Services (requisitos previos no satisfechos)</span><span class="sxs-lookup"><span data-stu-id="46e08-104">SQL Server Reporting Services (Prerequisites Not Satisfied)</span></span>

<span data-ttu-id="46e08-p102">Esta página aparecerá si en la infraestructura no se ha implementado ningún servidor de supervisión. Eso indica que no se han cumplido los requisitos mínimos para implementar informes de servidores de supervisión.</span><span class="sxs-lookup"><span data-stu-id="46e08-p102">You will see this page if there is no Monitoring Server deployed in your infrastructure. This indicates that the minimum requirements for deploying Monitoring Server reports have not been met.</span></span>

<span data-ttu-id="46e08-107">Para resolver este problema, asegúrese de tener un servidor de supervisión unido al dominio, que se define en el generador, y que se ha publicado la topología.</span><span class="sxs-lookup"><span data-stu-id="46e08-107">To resolve this issue, make sure that you have a Monitoring Server joined to the domain, that it is defined in Topology Builder, and that the topology has been published.</span></span> <span data-ttu-id="46e08-108">SQL Server Reporting Services también debe estar disponible en el servidor SQL Server e instalado como una característica en la base de datos del servidor de supervisión en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="46e08-108">SQL Server Reporting Services must also be available on the SQL Server, and installed as a feature into the Monitoring Server database on the SQL Server.</span></span>

<span data-ttu-id="46e08-109">Para obtener información detallada, vea [Instalar informes de supervisión en Skype para Business Server 2015](../../deploy/deploy-monitoring/install-monitoring-reports.md) y [Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).</span><span class="sxs-lookup"><span data-stu-id="46e08-109">For details, see [Install Monitoring Reports in Skype for Business Server 2015](../../deploy/deploy-monitoring/install-monitoring-reports.md) and [Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).</span></span>


