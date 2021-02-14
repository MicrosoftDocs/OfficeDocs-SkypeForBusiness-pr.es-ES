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
description: Aprenda a configurar una organización híbrida de Exchange para usarla con Microsoft Teams para asegurarse de que se sincronizan las pertenencias a grupos.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1061ce633dcd1db8f956a37143850deed9855e56
ms.sourcegitcommit: ab094058e3ffa974527fce8a331dad609ac19609
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "46551966"
---
<a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a>Configurar una organización híbrida de Exchange para usarla con Microsoft Teams
======================================================================

Por lo general, no debe tener que configurar ninguna funcionalidad de Exchange Online para su uso con Microsoft Teams. Sin embargo, para escenarios híbridos de Exchange, hay pasos necesarios para asegurarse de que la pertenencia a grupos se sincroniza entre Exchange Server (local) y Exchange Online. Esto implica la habilitación de la funcionalidad de reescribición de grupo en Azure AD Connect junto con varios scripts de inicialización: Configurar grupos de [Microsoft 365](https://docs.microsoft.com/exchange/hybrid-deployment/set-up-microsoft-365-groups)con la implementación híbrida de Exchange local.
