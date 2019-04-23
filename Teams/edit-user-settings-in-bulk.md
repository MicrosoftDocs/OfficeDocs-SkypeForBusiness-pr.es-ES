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
# <a name="edit-microsoft-teams-user-settings-in-bulk"></a><span data-ttu-id="d5532-103">Editar la configuración de usuario de Microsoft Teams de forma masiva</span><span class="sxs-lookup"><span data-stu-id="d5532-103">Edit Microsoft Teams user settings in bulk</span></span>

<span data-ttu-id="d5532-104">Como administrador, puede administrar la configuración de usuario de los equipos en el centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d5532-104">As an admin, you manage Teams user settings in the Microsoft Teams admin center.</span></span> <span data-ttu-id="d5532-105">En la página **usuarios** , puede ver información como la cuenta y detalles de la licencia y editar Directiva y otras opciones de configuración.</span><span class="sxs-lookup"><span data-stu-id="d5532-105">On the **Users** page, you can view information such as account and licensing details and edit policy and other settings.</span></span> <span data-ttu-id="d5532-106">Puede editar la configuración de los usuarios individualmente o para varios usuarios al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="d5532-106">You can edit settings for users individually or for multiple users at the same time.</span></span>

## <a name="edit-user-settings-in-bulk"></a><span data-ttu-id="d5532-107">Editar la configuración de usuario de forma masiva</span><span class="sxs-lookup"><span data-stu-id="d5532-107">Edit user settings in bulk</span></span>

<span data-ttu-id="d5532-108">Use el centro de administración de Microsoft Teams para editar la configuración de varios usuarios a la vez.</span><span class="sxs-lookup"><span data-stu-id="d5532-108">Use the Microsoft Teams admin center to edit settings for multiple users at a time.</span></span> <span data-ttu-id="d5532-109">Se recomienda la edición de la configuración para 20 usuarios a la vez.</span><span class="sxs-lookup"><span data-stu-id="d5532-109">We recommend editing settings for 20 users at a time.</span></span> <span data-ttu-id="d5532-110">Para editar la configuración de un gran número de usuarios, use PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d5532-110">To edit settings for a large number of users, use PowerShell.</span></span> <span data-ttu-id="d5532-111">Para obtener más información, vea [Información general de los equipos de PowerShell](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d5532-111">For more information, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

1. <span data-ttu-id="d5532-112">En la izquierda el centro de administración de Microsoft Teams, seleccione **los usuarios**.</span><span class="sxs-lookup"><span data-stu-id="d5532-112">In the left navigation of the Microsoft Teams admin center, select **Users**.</span></span>
2. <span data-ttu-id="d5532-113">Búsqueda de los usuarios que desee editar o filtrar la vista para mostrar a los usuarios que desea editar.</span><span class="sxs-lookup"><span data-stu-id="d5532-113">Search for the users you want to edit or filter the view to show the users you want to edit.</span></span>
3. <span data-ttu-id="d5532-114">En la **& #x 2713;** columna (marca de verificación), seleccione los usuarios, realice una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="d5532-114">In the **&#x2713;** (check mark) column, select users by doing one of the following:</span></span>
    - <span data-ttu-id="d5532-115">Seleccione uno de los usuarios a la vez.</span><span class="sxs-lookup"><span data-stu-id="d5532-115">Select users one at a time.</span></span> <span data-ttu-id="d5532-116">Un **& #x 2713;** se muestra junto a cada usuario que seleccione.</span><span class="sxs-lookup"><span data-stu-id="d5532-116">A **&#x2713;** is displayed next to each user you select.</span></span> <span data-ttu-id="d5532-117">Si selecciona más de 20 usuarios, no se bloqueará pero tenga en cuenta que los usuarios más seleccione, se llevará más tiempo para completar la operación.</span><span class="sxs-lookup"><span data-stu-id="d5532-117">If you select more than 20 users, you won't be blocked but keep in mind that the more users you select, the operation will take longer to complete.</span></span>

        ![Captura de pantalla de la página de los usuarios que muestra la selección del usuario](media/bulk-edit-user-settings-select-users.png)

    - <span data-ttu-id="d5532-119">Haga clic en el & #x 2713; (marca de verificación) en la parte superior de la tabla para seleccionar todos los usuarios (hasta un máximo de 20 usuarios) y, a continuación, en el cuadro de diálogo **Limitar selección** , haga clic en **continuar seleccione todo** para completar la selección.</span><span class="sxs-lookup"><span data-stu-id="d5532-119">Click the &#x2713; (check mark) at the top of the table to select all users (up to a maximum of 20 users), and then in the **Selection limit** dialog box, click **Continue select all** to complete the selection.</span></span>

        <span data-ttu-id="d5532-120">![Captura de pantalla de la página usuarios, que muestra el límite de selección](media/bulk-edit-user-settings-select-all-limit.png)</span><span class="sxs-lookup"><span data-stu-id="d5532-120">![Screen shot of the Users page, showing the selection limit](media/bulk-edit-user-settings-select-all-limit.png)</span></span> <br> <span data-ttu-id="d5532-121">Un **& #x 2713;** se muestra junto a los usuarios seleccionados.</span><span class="sxs-lookup"><span data-stu-id="d5532-121">A **&#x2713;** is displayed next to the selected users.</span></span>

        ![Captura de pantalla de la página usuarios, que muestra 20 usuarios seleccionados](media/bulk-edit-user-settings-select-all.png)
4. <span data-ttu-id="d5532-123">Haga clic en **Editar configuración**, realice los cambios que desee y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="d5532-123">Click **Edit settings**, make the changes that you want, and then click **Save**.</span></span>

    ![Captura de pantalla del panel Editar configuración](media/bulk-edit-user-settings-edit-settings.png)
