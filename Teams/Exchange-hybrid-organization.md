---
title: Configurar una organización híbrida de Exchange para usarla con Microsoft Teams
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
ms.openlocfilehash: eb81460a5a3d388bc9634cb53ce15655933534c5
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41834450"
---
<a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a><span data-ttu-id="dcb2e-103">Configurar una organización híbrida de Exchange para usarla con Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="dcb2e-103">Configure an Exchange hybrid organization for use with Microsoft Teams</span></span>
======================================================================

<span data-ttu-id="dcb2e-p101">Por lo general, no es necesario configurar ninguna funcionalidad de Exchange Online para su uso con Microsoft Teams. Sin embargo, para los escenarios híbridos de Exchange, hay pasos necesarios para garantizar que las pertenencias a grupos se sincronizan entre Exchange Server (local) y Exchange Online. Esto implica la habilitación de la funcionalidad de reescritura de grupo en Azure AD Connect junto con varios scripts de inicialización: [configurar grupos de Office 365 con un híbrido local de Exchange](https://go.microsoft.com/fwlink/?linkid=854389).</span><span class="sxs-lookup"><span data-stu-id="dcb2e-p101">Generally, you should not have to configure any Exchange Online functionality for use with Microsoft Teams. However, for Exchange Hybrid scenarios, there are steps necessary to ensure Group memberships are synchronized between Exchange Server (on-premises) and Exchange Online. This involves enablement of Group Writeback functionality in Azure AD Connect along with various initialization scripts: [Configure Office 365 Groups with on-premises Exchange hybrid](https://go.microsoft.com/fwlink/?linkid=854389).</span></span>
