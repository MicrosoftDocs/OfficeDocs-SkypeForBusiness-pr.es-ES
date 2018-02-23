---
title: "Configurar una organización híbrida de Exchange para usarla con Microsoft Teams"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: crowe
description: "Aprenda a configurar una organización híbrida de Exchange para usarla con Microsoft Teams."
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9caba4c88985bac543bf33c37acdbbe50c6c3753
ms.sourcegitcommit: 4b69ae91de3f82912eda3513cec65ae12e1ce2b2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2018
---
<a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a><span data-ttu-id="889d6-103">Configurar una organización híbrida de Exchange para usarla con Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="889d6-103">Configure an Exchange hybrid organization for use with Microsoft Teams</span></span>
======================================================================

<span data-ttu-id="889d6-p101">Por lo general, no necesita configurar ninguna funcionalidad de Exchange Online para usarla con Microsoft Teams. Pero en los escenarios híbridos de Exchange, es necesario seguir unos pasos para asegurarse de que las pertenencias a grupos estén sincronizadas entre Exchange Server (local) y Exchange Online. Esto implica la habilitación de la funcionalidad Reescritura de grupos en Azure AD Connect junto con varios scripts de inicialización: [Configuración de grupos de Office 365 con Exchange híbrido local](https://go.microsoft.com/fwlink/?linkid=854389)</span><span class="sxs-lookup"><span data-stu-id="889d6-p101">Generally, you should not have to configure any Exchange Online functionality for use with Microsoft Teams. However, for Exchange Hybrid scenarios, there are steps necessary to ensure Group memberships are synchronized between Exchange Server (on-premises) and Exchange Online. This involves enablement of Group Writeback functionality in Azure AD Connect along with various initialization scripts: [Configure Office 365 Groups with on-premises Exchange hybrid](https://go.microsoft.com/fwlink/?linkid=854389)</span></span>
