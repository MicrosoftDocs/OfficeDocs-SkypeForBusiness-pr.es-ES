---
title: SQL Server Reporting Services (requisitos previos no satisfechos)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeploySSRSPrereqNotSatisfied
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6be29df-b882-4ba8-ba40-8062eb3bb14d
description: Esta página aparecerá si en la infraestructura no se ha implementado ningún servidor de supervisión. Eso indica que no se han cumplido los requisitos mínimos para implementar informes de servidores de supervisión.
ms.openlocfilehash: 792c9d3b6e7c398d517549eb55aaf85086badb64
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100016"
---
# <a name="sql-server-reporting-services-prerequisites-not-satisfied"></a><span data-ttu-id="f6e79-104">SQL Server Reporting Services (requisitos previos no satisfechos)</span><span class="sxs-lookup"><span data-stu-id="f6e79-104">SQL Server Reporting Services (Prerequisites Not Satisfied)</span></span>

<span data-ttu-id="f6e79-p102">Esta página aparecerá si en la infraestructura no se ha implementado ningún servidor de supervisión. Eso indica que no se han cumplido los requisitos mínimos para implementar informes de servidores de supervisión.</span><span class="sxs-lookup"><span data-stu-id="f6e79-p102">You will see this page if there is no Monitoring Server deployed in your infrastructure. This indicates that the minimum requirements for deploying Monitoring Server reports have not been met.</span></span>

<span data-ttu-id="f6e79-107">Para resolver este problema, asegúrese de que tiene un servidor de supervisión unido al dominio, que está definido en el Generador de topologías y que la topología se ha publicado.</span><span class="sxs-lookup"><span data-stu-id="f6e79-107">To resolve this issue, make sure that you have a Monitoring Server joined to the domain, that it is defined in Topology Builder, and that the topology has been published.</span></span> <span data-ttu-id="f6e79-108">SQL Server Reporting Services también debe estar disponible en el SQL Server e instalarse como una característica en la base de datos del servidor de supervisión en el SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f6e79-108">SQL Server Reporting Services must also be available on the SQL Server, and installed as a feature into the Monitoring Server database on the SQL Server.</span></span>

<span data-ttu-id="f6e79-109">Para obtener más información, vea [Instalar informes de supervisión en Skype Empresarial Server 2015](../../deploy/deploy-monitoring/install-monitoring-reports.md) e Implementar [supervisión.](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring)</span><span class="sxs-lookup"><span data-stu-id="f6e79-109">For details, see [Install Monitoring Reports in Skype for Business Server 2015](../../deploy/deploy-monitoring/install-monitoring-reports.md) and [Deploying Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring).</span></span>