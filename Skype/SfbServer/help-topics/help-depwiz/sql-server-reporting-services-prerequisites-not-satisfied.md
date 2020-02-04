---
title: SQL Server Reporting Services (requisitos previos no satisfechos)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeploySSRSPrereqNotSatisfied
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6be29df-b882-4ba8-ba40-8062eb3bb14d
description: Esta página aparecerá si en la infraestructura no se ha implementado ningún servidor de supervisión. Eso indica que no se han cumplido los requisitos mínimos para implementar informes de servidores de supervisión.
ms.openlocfilehash: 94a20ce6f1a48e5eeed098777494e2d1f16597c1
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "41687313"
---
# <a name="sql-server-reporting-services-prerequisites-not-satisfied"></a>SQL Server Reporting Services (requisitos previos no satisfechos)

Esta página aparecerá si en la infraestructura no se ha implementado ningún servidor de supervisión. Eso indica que no se han cumplido los requisitos mínimos para implementar informes de servidores de supervisión.

Para resolver este problema, asegúrese de que tiene un servidor de supervisión unido al dominio, que está definido en el generador de topologías y que se ha publicado la topología. SQL Server Reporting Services también debe estar disponible en SQL Server y se puede instalar como una característica en la base de datos del servidor de supervisión en SQL Server.

Para obtener más información, consulte [instalar informes de supervisión en Skype empresarial Server 2015](../../deploy/deploy-monitoring/install-monitoring-reports.md) e [implementar la supervisión](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).


