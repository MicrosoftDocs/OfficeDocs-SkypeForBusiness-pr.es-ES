---
title: Editar en bloque la configuración de los usuarios de Microsoft Teams
author: LanaChin
ms.author: v-lanac
ms.reviewer: jastark
manager: serdars
ms.date: 04/19/2019
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Obtenga información sobre cómo administrar la configuración de usuario de Microsoft Teams en masa en el centro de administración de Microsoft Teams.
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.bulkoperations.edit
ms.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9585266ff2af124a1b9985c4cf18d842bc45af5c
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36236786"
---
# <a name="edit-microsoft-teams-user-settings-in-bulk"></a>Editar la configuración de usuario de Microsoft Teams en masa

Como administrador, administra la configuración de usuario de Teams en el centro de administración de Microsoft Teams. En la página **usuarios** , puede ver información como detalles de cuentas y licencias, así como editar directivas y otras opciones de configuración. Puede editar la configuración de los usuarios de forma individual o para varios usuarios al mismo tiempo.

## <a name="edit-user-settings-in-bulk"></a>Editar la configuración de usuario en masa

Use el centro de administración de Microsoft Teams para editar la configuración de varios usuarios a la vez. Recomendamos editar la configuración de 20 usuarios a la vez. Para editar la configuración de un gran número de usuarios, use PowerShell. Para obtener más información, vea [información general de Teams PowerShell](teams-powershell-overview.md).

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, seleccione **usuarios**.
2. Busque los usuarios que desea editar o filtre la vista para mostrar los usuarios que desea editar.
3. En la columna **&#x2713;** (marca), seleccione los usuarios siguiendo uno de estos procedimientos:
    - Seleccione los usuarios de uno en uno. Aparece una **&#x2713;** junto a cada uno de los usuarios que seleccione. Si selecciona más de 20 usuarios, no se bloqueará, pero tenga en cuenta que cuanto más usuarios seleccione, más tiempo tardará la operación en completarse.

        ![Captura de pantalla de la página usuarios que muestra la selección de usuario](media/bulk-edit-user-settings-select-users.png)

    - Haga clic en la &#x2713; (marca de verificación) situada en la parte superior de la tabla para seleccionar todos los usuarios (hasta un máximo de 20 usuarios) y, a continuación, en el cuadro de diálogo **límite de selección** , haga clic en **continuar seleccionando todo** para completar la selección.

        ![Captura de pantalla de la página usuarios, que muestra el límite de selección](media/bulk-edit-user-settings-select-all-limit.png) <br> Se muestra un **&#x2713;** junto a los usuarios seleccionados.

        ![Captura de pantalla de la página usuarios, en la que se muestran 20 usuarios seleccionados](media/bulk-edit-user-settings-select-all.png)
4. Haga clic en **Editar configuración**, realice los cambios que desee y, a continuación, haga clic en **Guardar**.

    ![Captura de pantalla del panel Editar configuración](media/bulk-edit-user-settings-edit-settings.png)
