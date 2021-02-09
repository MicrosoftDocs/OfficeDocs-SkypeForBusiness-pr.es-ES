---
title: Administrar el acceso de usuarios a Insights para Educación
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: Administrar el acceso a Insights para Educación en Microsoft Teams
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 32bd773975ff6b67d28ab765ffa7c932e978af7d
ms.sourcegitcommit: 27bfa015413bc7742bca4ea227e0324da0c740d7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145944"
---
# <a name="manage-user-access-to-education-insights"></a><span data-ttu-id="c4bde-103">Administrar el acceso de usuarios a Insights para Educación</span><span class="sxs-lookup"><span data-stu-id="c4bde-103">Manage user access to Education Insights</span></span>

<span data-ttu-id="c4bde-104">Este documento proporciona los pasos necesarios para administrar el acceso de usuarios a [Insights para Educación en Microsoft Teams](class-insights.md).</span><span class="sxs-lookup"><span data-stu-id="c4bde-104">This document provides the steps required to manage user access to [Education Insights in Microsoft Teams](class-insights.md).</span></span>

<span data-ttu-id="c4bde-105">Debe proporcionar permisos para los líderes educativos, líderes de distrito, directores de escuela, profesores en jefe, consejeros, directores de áreas de aprendizaje, directores de programa, trabajadores sociales y psicólogos.</span><span class="sxs-lookup"><span data-stu-id="c4bde-105">You need to provide permissions for education leaders, district leaders, school principals, head teachers, counselors, heads of learning areas, program directors, social workers, and psychologists.</span></span> <span data-ttu-id="c4bde-106">A los formadores se les concede permiso *automáticamente* cuando son propietarios de un equipo de clase.</span><span class="sxs-lookup"><span data-stu-id="c4bde-106">Educators are *automatically* given permission when they own a class team.</span></span>

<span data-ttu-id="c4bde-107">Para emplear Insights a nivel de la organización, es necesario [importar los datos del Sistema de información de estudiantes (SIS)](education-insights-sis-data-sync.md) para que Insights tenga la estructura jerárquica del sistema educativo asignada correctamente.</span><span class="sxs-lookup"><span data-stu-id="c4bde-107">To provide organization-level Insights, you must [import data from the Student Information System (SIS)](education-insights-sis-data-sync.md) so that Insights has the hierarchical structure of the educational system mapped correctly.</span></span>

> [!NOTE]
> <span data-ttu-id="c4bde-108">Solo el Administrador global puede administrar el acceso de los usuarios a Insights.</span><span class="sxs-lookup"><span data-stu-id="c4bde-108">Only Global Administrator can manage user access to Insights.</span></span>

> [!TIP]
> <span data-ttu-id="c4bde-109">Le recomendamos que habilite Insights para todos los líderes educativos. Así, tendrán los datos necesarios para comprender cada centro educativo y podrán identificar rápidamente los problemas y dar soporte técnico a los educadores.</span><span class="sxs-lookup"><span data-stu-id="c4bde-109">We recommend that you enable Insights for all your education leaders so that they have the data to understand each school, and the ability to quickly identify problems and provide support to their educators.</span></span> <span data-ttu-id="c4bde-110">Incluso si decide realizar un piloto, podría ser útil mantener Insights habilitado para todos los líderes educativos, mientras centra las comunicaciones en el grupo piloto de usuarios.</span><span class="sxs-lookup"><span data-stu-id="c4bde-110">Even if you're running a pilot, it may still be helpful to keep Insights enabled for all education leaders, but only target communications to the pilot group of users.</span></span>



## <a name="grant-permissions"></a><span data-ttu-id="c4bde-111">Conceder permisos</span><span class="sxs-lookup"><span data-stu-id="c4bde-111">Grant permissions</span></span>

* <span data-ttu-id="c4bde-112">Abra la aplicación Insights, haga clic en **Configuración** y, después, seleccione **Permisos de usuario**</span><span class="sxs-lookup"><span data-stu-id="c4bde-112">Open the Insights app, click **Settings**, and select **User permissions**</span></span>

:::image type="content" source="media/insights-user-permissions.png" alt-text="Configuración":::

* <span data-ttu-id="c4bde-114">Seleccione **Agregar usuarios**.</span><span class="sxs-lookup"><span data-stu-id="c4bde-114">Select **Add users**.</span></span>
* <span data-ttu-id="c4bde-115">Escriba el nombre de usuario o la dirección de correo electrónico de cada usuario.</span><span class="sxs-lookup"><span data-stu-id="c4bde-115">Enter the username or email address of each user.</span></span>
* <span data-ttu-id="c4bde-116">Seleccione el nivel de permisos:</span><span class="sxs-lookup"><span data-stu-id="c4bde-116">Select the permission level:</span></span>
  * <span data-ttu-id="c4bde-117">**El acceso a todas las organizaciones** significa que el usuario ve todas las unidades de la organización en todos los niveles.</span><span class="sxs-lookup"><span data-stu-id="c4bde-117">**Access to all organization** means the user sees all the org units at all levels.</span></span>
  * <span data-ttu-id="c4bde-118">**El acceso a escuelas específicas** quiere decir que el usuario ve las escuelas seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="c4bde-118">**Access to specific schools** means the user sees the selected schools.</span></span> <span data-ttu-id="c4bde-119">Comience a escribir y seleccione la escuela de la lista.</span><span class="sxs-lookup"><span data-stu-id="c4bde-119">Start typing and select the school from the list.</span></span> <span data-ttu-id="c4bde-120">Puede agregar varias escuelas conjuntamente.</span><span class="sxs-lookup"><span data-stu-id="c4bde-120">You can add multiple schools together.</span></span>
* <span data-ttu-id="c4bde-121">Haga clic en **Agregar nuevos usuarios**.</span><span class="sxs-lookup"><span data-stu-id="c4bde-121">Click **Add new users**.</span></span>

:::image type="content" source="media/insights-add-users.png" alt-text="Conceder permisos":::

> [!NOTE]
> <span data-ttu-id="c4bde-123">Proporcione solo permisos a los líderes educativos que los necesiten y solo para las unidades organizativas de las que sean responsables.</span><span class="sxs-lookup"><span data-stu-id="c4bde-123">Only provide permission to those education leaders that need them and only to the organizational units they are responsible for.</span></span> <span data-ttu-id="c4bde-124">Si no está seguro de si se requiere un permiso de usuario para una organización específica, consulte a los expertos en temas de privacidad de su institución, como personal de recursos humanos o jurídicos.</span><span class="sxs-lookup"><span data-stu-id="c4bde-124">If you are unsure whether user permission for a specific organization is required, consult your institution's privacy subject matter experts, such as legal or HR personnel.</span></span>

## <a name="edit-permissions"></a><span data-ttu-id="c4bde-125">Editar permisos</span><span class="sxs-lookup"><span data-stu-id="c4bde-125">Edit permissions</span></span>
* <span data-ttu-id="c4bde-126">Seleccione un usuario específico y, después, **Editar permisos**.</span><span class="sxs-lookup"><span data-stu-id="c4bde-126">Select specific user, then select **Edit permissions**.</span></span>
* <span data-ttu-id="c4bde-127">Actualice el nivel de permisos o la lista de escuelas y haga clic en **Actualizar permisos**.</span><span class="sxs-lookup"><span data-stu-id="c4bde-127">Update the permission level or schools list, and click **Update permissions**.</span></span>

:::image type="content" source="media/insights-edit-users.png" alt-text="Editar permisos":::

## <a name="remove-permissions"></a><span data-ttu-id="c4bde-129">Eliminar permisos</span><span class="sxs-lookup"><span data-stu-id="c4bde-129">Remove permissions</span></span>
* <span data-ttu-id="c4bde-130">Seleccione los usuarios que quiera quitar y, después, haga clic en **Quitar usuarios**.</span><span class="sxs-lookup"><span data-stu-id="c4bde-130">Select the users you want to remove, then select **Remove users**.</span></span>
* <span data-ttu-id="c4bde-131">Estos usuarios ya no tienen acceso a Insights a nivel de organización, pero pueden seguir accediendo a Insights a nivel de clase si son propietarios de un equipo de clase.</span><span class="sxs-lookup"><span data-stu-id="c4bde-131">These users no longer have access to organization-level Insights, but can still access class-level Insights if they own a class team.</span></span>

:::image type="content" source="media/insights-remove-users.png" alt-text="Quitar permisos":::
