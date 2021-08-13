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
ms.openlocfilehash: 6c87bc180923442bfd1f32b6836a6d41256261d3fe3233b0f347071f6bf9e884
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54304082"
---
# <a name="sql-server-reporting-services-prerequisites-not-satisfied"></a>SQL Server Reporting Services (requisitos previos no satisfechos)

Esta página aparecerá si en la infraestructura no se ha implementado ningún servidor de supervisión. Eso indica que no se han cumplido los requisitos mínimos para implementar informes de servidores de supervisión.

Para resolver este problema, asegúrese de que tiene un servidor de supervisión unido al dominio, que está definido en el Generador de topologías y que la topología se ha publicado. SQL Server Reporting Services también debe estar disponible en el SQL Server e instalarse como una característica en la base de datos del servidor de supervisión en el SQL Server.

Para obtener más información, vea [Install Monitoring Reports in Skype Empresarial Server 2015](../../deploy/deploy-monitoring/install-monitoring-reports.md) e [Deploying Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring).