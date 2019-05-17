---
title: Configurar una organización híbrida de Exchange para usarla con Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: dstrome
description: Aprenda a configurar una organización híbrida de Exchange para usarla con Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b3b41f0ae30fb0c21baab1f7e01b86e79300008e
ms.sourcegitcommit: d4b007b88469a820595ecdcf2a90854ecefe2809
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/17/2019
ms.locfileid: "34108639"
---
<a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a><span data-ttu-id="215a4-103">Configurar una organización híbrida de Exchange para usarla con Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="215a4-103">Configure an Exchange hybrid organization for use with Microsoft Teams</span></span>
======================================================================

<span data-ttu-id="215a4-p101">Por lo general, no debe tener que configurar las funciones de Exchange Online para su uso con Microsoft Teams. Sin embargo, para escenarios de implementación híbrida de Exchange, existen pasos necesarios para asegurarse de que las pertenencias a grupos se sincronizan entre el servidor de Exchange (local) y Exchange Online. Esto implica la habilitación de la funcionalidad de reescritura de grupo en Azure conectar AD junto con diversos scripts de inicialización: [Configurar grupos de Office 365 con implementación híbrida de Exchange local](https://go.microsoft.com/fwlink/?linkid=854389).</span><span class="sxs-lookup"><span data-stu-id="215a4-p101">Generally, you should not have to configure any Exchange Online functionality for use with Microsoft Teams. However, for Exchange Hybrid scenarios, there are steps necessary to ensure Group memberships are synchronized between Exchange Server (on-premises) and Exchange Online. This involves enablement of Group Writeback functionality in Azure AD Connect along with various initialization scripts: [Configure Office 365 Groups with on-premises Exchange hybrid](https://go.microsoft.com/fwlink/?linkid=854389).</span></span>
