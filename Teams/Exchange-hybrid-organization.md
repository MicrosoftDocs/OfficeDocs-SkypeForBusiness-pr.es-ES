---
title: Configurar una Exchange híbrida
author: dstrome
ms.author: dstrome
manager: serdars
ms.date: 09/25/2017
ms.topic: article
audience: admin
ms.service: msteams
ms.reviewer: dstrome
description: Obtenga información sobre cómo configurar una Exchange híbrida para su uso con Microsoft Teams asegurarse de que las pertenencias a grupos se sincronizan.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 90250b3d3f3593990d356843bebea324060d6f8b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094612"
---
<a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a><span data-ttu-id="d955c-103">Configurar una organización híbrida de Exchange para usarla con Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d955c-103">Configure an Exchange hybrid organization for use with Microsoft Teams</span></span>
======================================================================

<span data-ttu-id="d955c-104">Por lo general, no debe tener que configurar ninguna funcionalidad Exchange Online para su uso con Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d955c-104">Generally, you should not have to configure any Exchange Online functionality for use with Microsoft Teams.</span></span> <span data-ttu-id="d955c-105">Sin embargo, Exchange escenarios híbridos, hay pasos necesarios para asegurarse de que las pertenencias a grupos se sincronizan entre Exchange Server (local) y Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="d955c-105">However, for Exchange Hybrid scenarios, there are steps necessary to ensure Group memberships are synchronized between Exchange Server (on-premises) and Exchange Online.</span></span> <span data-ttu-id="d955c-106">Esto implica la habilitación de la funcionalidad de reescribición de grupo en Azure AD Conectar junto con varios scripts de inicialización: Configurar Microsoft 365 grupos con aplicaciones locales [Exchange híbrida.](/exchange/hybrid-deployment/set-up-microsoft-365-groups)</span><span class="sxs-lookup"><span data-stu-id="d955c-106">This involves enablement of Group Writeback functionality in Azure AD Connect along with various initialization scripts: [Configure Microsoft 365 Groups with on-premises Exchange hybrid](/exchange/hybrid-deployment/set-up-microsoft-365-groups).</span></span>