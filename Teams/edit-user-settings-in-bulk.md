---
title: Editar la configuración de los usuarios de Microsoft Teams de forma masiva
author: LanaChin
ms.author: v-lanac
ms.reviewer: jastark
manager: serdars
ms.date: 04/19/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Obtenga información sobre cómo administrar la configuración de usuario de Microsoft Teams de forma masiva en el centro de administración de Microsoft Teams.
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.bulkoperations.edit
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4c1dfba0bdaec642b0ea078d7f10ba022c8514da
ms.sourcegitcommit: 3000a661ac420eecd825a8285bdac7b744bd25da
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2019
ms.locfileid: "31988976"
---
# <a name="edit-microsoft-teams-user-settings-in-bulk"></a>Editar la configuración de usuario de Microsoft Teams de forma masiva

Como administrador, puede administrar la configuración de usuario de los equipos en el centro de administración de Microsoft Teams. En la página **usuarios** , puede ver información como la cuenta y detalles de la licencia y editar Directiva y otras opciones de configuración. Puede editar la configuración de los usuarios individualmente o para varios usuarios al mismo tiempo.

## <a name="edit-user-settings-in-bulk"></a>Editar la configuración de usuario de forma masiva

Use el centro de administración de Microsoft Teams para editar la configuración de varios usuarios a la vez. Se recomienda la edición de la configuración para 20 usuarios a la vez. Para editar la configuración de un gran número de usuarios, use PowerShell. Para obtener más información, vea [Información general de los equipos de PowerShell](teams-powershell-overview.md).

1. En la izquierda el centro de administración de Microsoft Teams, seleccione **los usuarios**.
2. Búsqueda de los usuarios que desee editar o filtrar la vista para mostrar a los usuarios que desea editar.
3. En la **& #x 2713;** columna (marca de verificación), seleccione los usuarios, realice una de las siguientes opciones:
    - Seleccione uno de los usuarios a la vez. Un **& #x 2713;** se muestra junto a cada usuario que seleccione. Si selecciona más de 20 usuarios, no se bloqueará pero tenga en cuenta que los usuarios más seleccione, se llevará más tiempo para completar la operación.

        ![Captura de pantalla de la página de los usuarios que muestra la selección del usuario](media/bulk-edit-user-settings-select-users.png)

    - Haga clic en el & #x 2713; (marca de verificación) en la parte superior de la tabla para seleccionar todos los usuarios (hasta un máximo de 20 usuarios) y, a continuación, en el cuadro de diálogo **Limitar selección** , haga clic en **continuar seleccione todo** para completar la selección.

        ![Captura de pantalla de la página usuarios, que muestra el límite de selección](media/bulk-edit-user-settings-select-all-limit.png) <br> Un **& #x 2713;** se muestra junto a los usuarios seleccionados.

        ![Captura de pantalla de la página usuarios, que muestra 20 usuarios seleccionados](media/bulk-edit-user-settings-select-all.png)
4. Haga clic en **Editar configuración**, realice los cambios que desee y, a continuación, haga clic en **Guardar**.

    ![Captura de pantalla del panel Editar configuración](media/bulk-edit-user-settings-edit-settings.png)
