---
title: Introducción a teams Manufacturing templates en la consola de administración
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: phecda louie
ms.collection:
- M365-collaboration
localization_priority: Normal
search.appverid: MET150
description: Obtenga información sobre cómo usar las plantillas de Teams para crear estructuras de equipo diseñadas para necesidades de fabricación proporcionando una configuración predefinida, canales y aplicaciones preinstaladas con la consola de administración.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 896435daaf7b1036a54649e8670b0a19d88b2474
ms.sourcegitcommit: 448606977ee67befbdc91060363cf90dd346a528
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2020
ms.locfileid: "48136127"
---
# <a name="use-teams-manufacturing-templates-in-the-admin-console"></a><span data-ttu-id="42b0c-103">Usar las plantillas de mecanizado de Teams en la consola de administración</span><span class="sxs-lookup"><span data-stu-id="42b0c-103">Use Teams manufacturing templates in the admin console</span></span>

[!INCLUDE [template](includes/preview-feature.md)]

<span data-ttu-id="42b0c-104">Las plantillas de Teams le permiten crear equipos de forma rápida y sencilla proporcionando una plantilla predefinida de configuración, canales y aplicaciones preinstaladas.</span><span class="sxs-lookup"><span data-stu-id="42b0c-104">Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="42b0c-105">Las plantillas de Teams tienen definiciones preconstruidas de estructuras de equipo diseñadas en relación con las necesidades de fabricación.</span><span class="sxs-lookup"><span data-stu-id="42b0c-105">Teams templates have pre-built definitions of team structures designed around manufacturing needs.</span></span> <span data-ttu-id="42b0c-106">También puede ampliar las plantillas de Teams para crear equipos que estén adaptados a las necesidades específicas de su organización.</span><span class="sxs-lookup"><span data-stu-id="42b0c-106">You can also extend the Teams templates to create teams that are tailored to your specific organizational needs.</span></span>

<span data-ttu-id="42b0c-107">En este artículo, presentaremos cada una de las plantillas de Teams y cómo le recomendamos que las use.</span><span class="sxs-lookup"><span data-stu-id="42b0c-107">In this article, we will introduce each of the Teams templates and how we recommend using them.</span></span>

<span data-ttu-id="42b0c-108">Este artículo le interesa si es responsable de planear, implementar y administrar varios equipos en la organización de fabricación.</span><span class="sxs-lookup"><span data-stu-id="42b0c-108">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your manufacturing organization.</span></span> <span data-ttu-id="42b0c-109">Damos por hecho que ya ha implementado el servicio de Teams en su organización.</span><span class="sxs-lookup"><span data-stu-id="42b0c-109">We assume that you already have deployed Teams service in your organization.</span></span> <span data-ttu-id="42b0c-110">Si aún no ha implementado Teams, empiece por leer [cómo implementar Microsoft Teams](How-to-roll-out-teams.md).</span><span class="sxs-lookup"><span data-stu-id="42b0c-110">If you haven't yet rolled out Teams, start by reading the [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span>

<span data-ttu-id="42b0c-111">Para obtener más información sobre las plantillas de equipo en general, consulte Introducción a [las plantillas](get-started-with-teams-templates-in-the-admin-console.md)de Teams.</span><span class="sxs-lookup"><span data-stu-id="42b0c-111">To learn more about team templates in general, please refer to [Get started with Teams templates](get-started-with-teams-templates-in-the-admin-console.md).</span></span>

## <a name="quality-and-safety"></a><span data-ttu-id="42b0c-112">Calidad y seguridad</span><span class="sxs-lookup"><span data-stu-id="42b0c-112">Quality and safety</span></span>

<span data-ttu-id="42b0c-113">Centralizar la comunicación, el acceso a los recursos y las operaciones en planta con un equipo de fábricas.</span><span class="sxs-lookup"><span data-stu-id="42b0c-113">Centralize communication, access to resources, and plant operations with a Manufacturing Plant team.</span></span> <span data-ttu-id="42b0c-114">Incluya documentos de directivas y procedimientos, vídeos de aprendizaje, avisos de seguridad, procesos de cambio de turno.</span><span class="sxs-lookup"><span data-stu-id="42b0c-114">Include policy and procedure documents, training videos, safety notices, shift handover processes.</span></span>

| <span data-ttu-id="42b0c-115">Tipo de plantilla base</span><span class="sxs-lookup"><span data-stu-id="42b0c-115">Base template type</span></span>|<span data-ttu-id="42b0c-116">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="42b0c-116">baseTemplateId</span></span> | <span data-ttu-id="42b0c-117">Propiedades que vienen con esta plantilla base</span><span class="sxs-lookup"><span data-stu-id="42b0c-117">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="42b0c-118">Calidad y seguridad</span><span class="sxs-lookup"><span data-stu-id="42b0c-118">Quality and safety</span></span>|`com.microsoft.teams.template.QualitySafety` |<span data-ttu-id="42b0c-119">Canales</span><span class="sxs-lookup"><span data-stu-id="42b0c-119">Channels:</span></span> <ul><li><span data-ttu-id="42b0c-120">General</span><span class="sxs-lookup"><span data-stu-id="42b0c-120">General</span></span><li><span data-ttu-id="42b0c-121">Anuncios</span><span class="sxs-lookup"><span data-stu-id="42b0c-121">Announcements</span></span></li><li><span data-ttu-id="42b0c-122">Línea 1</span><span class="sxs-lookup"><span data-stu-id="42b0c-122">Line 1</span></span></li><li><span data-ttu-id="42b0c-123">Línea 2</span><span class="sxs-lookup"><span data-stu-id="42b0c-123">Line 2</span></span></li><li><span data-ttu-id="42b0c-124">Línea 3</span><span class="sxs-lookup"><span data-stu-id="42b0c-124">Line 3</span></span></li><li><span data-ttu-id="42b0c-125">Opera</span><span class="sxs-lookup"><span data-stu-id="42b0c-125">Safety</span></span></li><li><span data-ttu-id="42b0c-126">Aprendizaje</span><span class="sxs-lookup"><span data-stu-id="42b0c-126">Training</span></span></li><li><span data-ttu-id="42b0c-127">Mantenimiento</span><span class="sxs-lookup"><span data-stu-id="42b0c-127">Maintenance</span></span></li><li><span data-ttu-id="42b0c-128">Cosas divertidas</span><span class="sxs-lookup"><span data-stu-id="42b0c-128">Fun stuff</span></span></li></ul> <span data-ttu-id="42b0c-129">Phone</span><span class="sxs-lookup"><span data-stu-id="42b0c-129">Apps:</span></span> <ul><li><span data-ttu-id="42b0c-130">Wiki</span><span class="sxs-lookup"><span data-stu-id="42b0c-130">Wiki</span></span></li></ul>|
||||