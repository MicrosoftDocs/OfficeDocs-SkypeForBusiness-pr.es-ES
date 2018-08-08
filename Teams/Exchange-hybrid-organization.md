---
title: Configurar una organización híbrida de Exchange para usarla con Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: crowe
description: Aprenda a configurar una organización híbrida de Exchange para usarla con Microsoft Teams.
localization_priority: Priority
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: b2550ade04f7a7411234c3b9836a2e1becbaa6b4
ms.sourcegitcommit: 0c2d1766b96b99d9985f5a0f4f90b8d8bd9aa3ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/08/2018
ms.locfileid: "18998999"
---
<a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a><span data-ttu-id="42d8a-103">Configurar una organización híbrida de Exchange para usarla con Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="42d8a-103">Configure an Exchange hybrid organization for use with Microsoft Teams</span></span>
======================================================================

<span data-ttu-id="42d8a-p101">Por lo general, no necesita configurar ninguna funcionalidad de Exchange Online para usarla con Microsoft Teams. Pero en los escenarios híbridos de Exchange, es necesario seguir unos pasos para asegurarse de que las pertenencias a grupos estén sincronizadas entre Exchange Server (local) y Exchange Online. Esto implica la habilitación de la funcionalidad Reescritura de grupos en Azure AD Connect junto con varios scripts de inicialización: [Configuración de grupos de Office 365 con Exchange híbrido local](https://go.microsoft.com/fwlink/?linkid=854389)</span><span class="sxs-lookup"><span data-stu-id="42d8a-p101">Generally, you should not have to configure any Exchange Online functionality for use with Microsoft Teams. However, for Exchange Hybrid scenarios, there are steps necessary to ensure Group memberships are synchronized between Exchange Server (on-premises) and Exchange Online. This involves enablement of Group Writeback functionality in Azure AD Connect along with various initialization scripts: [Configure Office 365 Groups with on-premises Exchange hybrid](https://go.microsoft.com/fwlink/?linkid=854389)</span></span>
