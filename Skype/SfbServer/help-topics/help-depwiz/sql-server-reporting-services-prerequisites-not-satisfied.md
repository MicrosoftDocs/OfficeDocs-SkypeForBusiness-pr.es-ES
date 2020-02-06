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
- CSH
ms.custom:
- ms.lync.dep.DeploySSRSPrereqNotSatisfied
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6be29df-b882-4ba8-ba40-8062eb3bb14d
description: Esta página aparecerá si en la infraestructura no se ha implementado ningún servidor de supervisión. Eso indica que no se han cumplido los requisitos mínimos para implementar informes de servidores de supervisión.
ms.openlocfilehash: 2c5f58751d03d5c482bd3b9113b764ffe626cec6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41823454"
---
# <a name="sql-server-reporting-services-prerequisites-not-satisfied"></a>SQL Server Reporting Services (requisitos previos no satisfechos)

Esta página aparecerá si en la infraestructura no se ha implementado ningún servidor de supervisión. Eso indica que no se han cumplido los requisitos mínimos para implementar informes de servidores de supervisión.

Para resolver este problema, asegúrese de que tiene un servidor de supervisión unido al dominio, que está definido en el generador de topologías y que se ha publicado la topología. SQL Server Reporting Services también debe estar disponible en SQL Server y se puede instalar como una característica en la base de datos del servidor de supervisión en SQL Server.

Para obtener más información, consulte [instalar informes de supervisión en Skype empresarial Server 2015](../../deploy/deploy-monitoring/install-monitoring-reports.md) e [implementar la supervisión](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).


