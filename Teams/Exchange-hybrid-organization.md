---
title: Configurar una organización híbrida de Exchange
author: JoanneHendrickson
ms.author: jhendr
manager: serdars
ms.date: 09/25/2017
ms.topic: article
audience: admin
ms.service: msteams
description: Obtenga información sobre cómo configurar una organización híbrida de Exchange para su uso con Microsoft Teams con el fin de asegurarse de que se sincronizan las pertenencias a grupos.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: cb2471a2680218a69daa74d20b27c4b7642fa1d7
ms.sourcegitcommit: fc87f4300f53abf7a049936944abb21d0cade0d9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2022
ms.locfileid: "68480680"
---
# <a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a>Configurar una organización híbrida de Exchange para usarla con Microsoft Teams

Por lo general, no debe tener que configurar ninguna funcionalidad de Exchange Online para su uso con Microsoft Teams. Sin embargo, para escenarios híbridos de Exchange, hay pasos necesarios para asegurarse de que la pertenencia a grupos se sincroniza entre Exchange Server (local) y Exchange Online. Esto implica habilitar la funcionalidad de reescritura de grupo en Azure AD Connect junto con varios scripts de inicialización: [Configurar Grupos de Microsoft 365 con la implementación híbrida de Exchange](/exchange/hybrid-deployment/set-up-microsoft-365-groups) local.