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
# <a name="edit-microsoft-teams-user-settings-in-bulk"></a><span data-ttu-id="bac8d-103">Editar la configuración de usuario de Microsoft Teams en masa</span><span class="sxs-lookup"><span data-stu-id="bac8d-103">Edit Microsoft Teams user settings in bulk</span></span>

<span data-ttu-id="bac8d-104">Como administrador, administra la configuración de usuario de Teams en el centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="bac8d-104">As an admin, you manage Teams user settings in the Microsoft Teams admin center.</span></span> <span data-ttu-id="bac8d-105">En la página **usuarios** , puede ver información como detalles de cuentas y licencias, así como editar directivas y otras opciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="bac8d-105">On the **Users** page, you can view information such as account and licensing details and edit policy and other settings.</span></span> <span data-ttu-id="bac8d-106">Puede editar la configuración de los usuarios de forma individual o para varios usuarios al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="bac8d-106">You can edit settings for users individually or for multiple users at the same time.</span></span>

## <a name="edit-user-settings-in-bulk"></a><span data-ttu-id="bac8d-107">Editar la configuración de usuario en masa</span><span class="sxs-lookup"><span data-stu-id="bac8d-107">Edit user settings in bulk</span></span>

<span data-ttu-id="bac8d-108">Use el centro de administración de Microsoft Teams para editar la configuración de varios usuarios a la vez.</span><span class="sxs-lookup"><span data-stu-id="bac8d-108">Use the Microsoft Teams admin center to edit settings for multiple users at a time.</span></span> <span data-ttu-id="bac8d-109">Recomendamos editar la configuración de 20 usuarios a la vez.</span><span class="sxs-lookup"><span data-stu-id="bac8d-109">We recommend editing settings for 20 users at a time.</span></span> <span data-ttu-id="bac8d-110">Para editar la configuración de un gran número de usuarios, use PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bac8d-110">To edit settings for a large number of users, use PowerShell.</span></span> <span data-ttu-id="bac8d-111">Para obtener más información, vea [información general de Teams PowerShell](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="bac8d-111">For more information, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

1. <span data-ttu-id="bac8d-112">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, seleccione **usuarios**.</span><span class="sxs-lookup"><span data-stu-id="bac8d-112">In the left navigation of the Microsoft Teams admin center, select **Users**.</span></span>
2. <span data-ttu-id="bac8d-113">Busque los usuarios que desea editar o filtre la vista para mostrar los usuarios que desea editar.</span><span class="sxs-lookup"><span data-stu-id="bac8d-113">Search for the users you want to edit or filter the view to show the users you want to edit.</span></span>
3. <span data-ttu-id="bac8d-114">En la columna **&#x2713;** (marca), seleccione los usuarios siguiendo uno de estos procedimientos:</span><span class="sxs-lookup"><span data-stu-id="bac8d-114">In the **&#x2713;** (check mark) column, select users by doing one of the following:</span></span>
    - <span data-ttu-id="bac8d-115">Seleccione los usuarios de uno en uno.</span><span class="sxs-lookup"><span data-stu-id="bac8d-115">Select users one at a time.</span></span> <span data-ttu-id="bac8d-116">Aparece una **&#x2713;** junto a cada uno de los usuarios que seleccione.</span><span class="sxs-lookup"><span data-stu-id="bac8d-116">A **&#x2713;** is displayed next to each user you select.</span></span> <span data-ttu-id="bac8d-117">Si selecciona más de 20 usuarios, no se bloqueará, pero tenga en cuenta que cuanto más usuarios seleccione, más tiempo tardará la operación en completarse.</span><span class="sxs-lookup"><span data-stu-id="bac8d-117">If you select more than 20 users, you won't be blocked but keep in mind that the more users you select, the longer the operation will take to complete.</span></span>

        ![Captura de pantalla de la página usuarios que muestra la selección de usuario](media/bulk-edit-user-settings-select-users.png)

    - <span data-ttu-id="bac8d-119">Haga clic en la &#x2713; (marca de verificación) situada en la parte superior de la tabla para seleccionar todos los usuarios (hasta un máximo de 20 usuarios) y, a continuación, en el cuadro de diálogo **límite de selección** , haga clic en **continuar seleccionando todo** para completar la selección.</span><span class="sxs-lookup"><span data-stu-id="bac8d-119">Click the &#x2713; (check mark) at the top of the table to select all users (up to a maximum of 20 users), and then in the **Selection limit** dialog box, click **Continue select all** to complete the selection.</span></span>

        <span data-ttu-id="bac8d-120">![Captura de pantalla de la página usuarios, que muestra el límite de selección](media/bulk-edit-user-settings-select-all-limit.png)</span><span class="sxs-lookup"><span data-stu-id="bac8d-120">![Screen shot of the Users page, showing the selection limit](media/bulk-edit-user-settings-select-all-limit.png)</span></span> <br> <span data-ttu-id="bac8d-121">Se muestra un **&#x2713;** junto a los usuarios seleccionados.</span><span class="sxs-lookup"><span data-stu-id="bac8d-121">A **&#x2713;** is displayed next to the selected users.</span></span>

        ![Captura de pantalla de la página usuarios, en la que se muestran 20 usuarios seleccionados](media/bulk-edit-user-settings-select-all.png)
4. <span data-ttu-id="bac8d-123">Haga clic en **Editar configuración**, realice los cambios que desee y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="bac8d-123">Click **Edit settings**, make the changes that you want, and then click **Save**.</span></span>

    ![Captura de pantalla del panel Editar configuración](media/bulk-edit-user-settings-edit-settings.png)
