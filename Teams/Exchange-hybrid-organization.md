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
ms.openlocfilehash: 4a0480ff8a795addb9ae322478fddb69e9aeceeed14ebca83f27cac34b01bfbb
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54284480"
---
<a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a>Configurar una organización híbrida de Exchange para usarla con Microsoft Teams
======================================================================

Por lo general, no debe tener que configurar ninguna funcionalidad Exchange Online para su uso con Microsoft Teams. Sin embargo, Exchange escenarios híbridos, hay pasos necesarios para asegurarse de que las pertenencias a grupos se sincronizan entre Exchange Server (local) y Exchange Online. Esto implica la habilitación de la funcionalidad de reescribición de grupo en Azure AD Conectar junto con varios scripts de inicialización: Configurar Microsoft 365 grupos con aplicaciones locales [Exchange híbrida.](/exchange/hybrid-deployment/set-up-microsoft-365-groups)