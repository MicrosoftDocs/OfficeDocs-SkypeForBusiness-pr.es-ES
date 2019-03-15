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
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d4dfc6b476498fef4484718a90f9c242a565cd64
ms.sourcegitcommit: bc2b227b4ac0a9521993f808a1361b4f9bc7faad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2019
ms.locfileid: "30568563"
---
<a name="configure-an-exchange-hybrid-organization-for-use-with-microsoft-teams"></a>Configurar una organización híbrida de Exchange para usarla con Microsoft Teams
======================================================================

Por lo general, no debe tener que configurar las funciones de Exchange Online para su uso con Microsoft Teams. Sin embargo, para escenarios de implementación híbrida de Exchange, existen pasos necesarios para asegurarse de que las pertenencias a grupos se sincronizan entre el servidor de Exchange (local) y Exchange Online. Esto implica la habilitación de la funcionalidad de reescritura de grupo en Azure conectar AD junto con diversos scripts de inicialización: [Configurar grupos de Office 365 con implementación híbrida de Exchange local](https://go.microsoft.com/fwlink/?linkid=854389).
