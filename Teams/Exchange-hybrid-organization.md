---
title: Configurar una organización híbrida de Exchange
author: dstrome
ms.author: dstrome
manager: serdars
ms.date: 09/25/2017
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: dstrome
description: Aprenda a configurar una organización híbrida de Exchange para usarla con Microsoft Teams.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: f1a59c01fa112294d771dc6f8d08f32a3c7a4f19
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/03/2020
ms.locfileid: "43136520"
---
<a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a><span data-ttu-id="599b2-103">Configurar una organización híbrida de Exchange para usarla con Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="599b2-103">Configure an Exchange hybrid organization for use with Microsoft Teams</span></span>
======================================================================

<span data-ttu-id="599b2-p101">Por lo general, no es necesario configurar ninguna funcionalidad de Exchange Online para su uso con Microsoft Teams. Sin embargo, para los escenarios híbridos de Exchange, hay pasos necesarios para garantizar que las pertenencias a grupos se sincronizan entre Exchange Server (local) y Exchange Online. Esto implica la habilitación de la funcionalidad de reescritura de grupo en Azure AD Connect junto con varios scripts de inicialización: [configurar grupos de Office 365 con un híbrido local de Exchange](https://go.microsoft.com/fwlink/?linkid=854389).</span><span class="sxs-lookup"><span data-stu-id="599b2-p101">Generally, you should not have to configure any Exchange Online functionality for use with Microsoft Teams. However, for Exchange Hybrid scenarios, there are steps necessary to ensure Group memberships are synchronized between Exchange Server (on-premises) and Exchange Online. This involves enablement of Group Writeback functionality in Azure AD Connect along with various initialization scripts: [Configure Office 365 Groups with on-premises Exchange hybrid](https://go.microsoft.com/fwlink/?linkid=854389).</span></span>
