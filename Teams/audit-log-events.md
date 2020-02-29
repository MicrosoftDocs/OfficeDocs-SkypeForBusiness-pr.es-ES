---
title: Buscar eventos en el registro de auditoría en Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.reviewer: anach
search.appverid: MET150
description: Aprenda a recuperar datos de Microsoft Teams del registro de auditoría de Office 365.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3f53d1a0b5e600de9d38233b243dba3486b88bf1
ms.sourcegitcommit: 6cfaadec5782ca7316db36472bd0be20217da693
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/29/2020
ms.locfileid: "42341628"
---
# <a name="search-the-audit-log-for-events-in-microsoft-teams"></a><span data-ttu-id="98b3a-103">Buscar eventos en el registro de auditoría en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="98b3a-103">Search the audit log for events in Microsoft Teams</span></span>

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="98b3a-104">El registro de auditoría puede ayudarle a investigar actividades específicas en los servicios de Office 365.</span><span class="sxs-lookup"><span data-stu-id="98b3a-104">The audit log can help you investigate specific activities across Office 365 services.</span></span> <span data-ttu-id="98b3a-105">Estas son algunas de las actividades que se auditan en Microsoft Teams:</span><span class="sxs-lookup"><span data-stu-id="98b3a-105">For Teams, here are some of the activities that are audited:</span></span>

- <span data-ttu-id="98b3a-106">Creación de equipos</span><span class="sxs-lookup"><span data-stu-id="98b3a-106">Team creation</span></span>

- <span data-ttu-id="98b3a-107">Eliminación de equipos</span><span class="sxs-lookup"><span data-stu-id="98b3a-107">Team deletion</span></span>

- <span data-ttu-id="98b3a-108">Agregación de canales</span><span class="sxs-lookup"><span data-stu-id="98b3a-108">Added channel</span></span>

- <span data-ttu-id="98b3a-109">Cambios en la configuración</span><span class="sxs-lookup"><span data-stu-id="98b3a-109">Changed setting</span></span>

> [!NOTE]
> <span data-ttu-id="98b3a-110">Los eventos de auditoría de canales privados también se registran como si se trataran de equipos y canales estándar.</span><span class="sxs-lookup"><span data-stu-id="98b3a-110">Audit events from private channels are also logged as they are for teams and standard channels.</span></span>

<span data-ttu-id="98b3a-111">Para ver la lista completa de actividades auditadas en Office 365, consulte [Buscar en el registro de auditoría del Centro de seguridad y cumplimiento de Office 365](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c).</span><span class="sxs-lookup"><span data-stu-id="98b3a-111">To see the complete list of activities that are audited in Office 365, read [Search the audit log in the Office 365 Security & Compliance Center](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c).</span></span>

## <a name="turn-on-auditing-in-teams"></a><span data-ttu-id="98b3a-112">Activar la auditoría en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="98b3a-112">Turn on auditing in Teams</span></span>

<span data-ttu-id="98b3a-113">Para poder consultar los datos de auditoría, primero debe activar la auditoría en el [centro de cumplimiento de & de seguridad](https://protection.office.com).</span><span class="sxs-lookup"><span data-stu-id="98b3a-113">Before you can look at audit data, you have to first turn on auditing in the [Security & Compliance Center](https://protection.office.com).</span></span> <span data-ttu-id="98b3a-114">Para obtener ayuda para activar la auditoría, consulte [Activar o desactivar la búsqueda de registros de auditoría de Office 365](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).</span><span class="sxs-lookup"><span data-stu-id="98b3a-114">For help turning on auditing, read [Turn Office 365 audit log search on or off](https://support.office.com/article/Turn-Office-365-audit-log-search-on-or-off-e893b19a-660c-41f2-9074-d3631c95a014).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="98b3a-115">Los datos de auditoría solo están disponibles desde el momento en que se habilitó la auditoría.</span><span class="sxs-lookup"><span data-stu-id="98b3a-115">Audit data is only available from the point at which you turned on Auditing.</span></span>

## <a name="retrieve-teams-data-from-the-audit-log"></a><span data-ttu-id="98b3a-116">Recuperar datos de Microsoft Teams del registro de auditoría</span><span class="sxs-lookup"><span data-stu-id="98b3a-116">Retrieve Teams data from the audit log</span></span>

1. <span data-ttu-id="98b3a-117">Para recuperar los registros de auditoría, vaya al [Centro de seguridad y cumplimiento](https://go.microsoft.com/fwlink/?linkid=855775).</span><span class="sxs-lookup"><span data-stu-id="98b3a-117">To retrieve audit logs, go to the [Security & Compliance Center](https://go.microsoft.com/fwlink/?linkid=855775).</span></span> <span data-ttu-id="98b3a-118">En **Buscar**, seleccione **búsqueda de registros de auditoría**.</span><span class="sxs-lookup"><span data-stu-id="98b3a-118">Under **Search**, select **Audit log search**.</span></span>
1. <span data-ttu-id="98b3a-119">Use **Buscar** para filtrar por las actividades, las fechas y los usuarios que desee auditar.</span><span class="sxs-lookup"><span data-stu-id="98b3a-119">Use **Search** to filter by the activities, dates, and users you want to audit.</span></span>
1. <span data-ttu-id="98b3a-120">Exporte los resultados a Excel para continuar el análisis.</span><span class="sxs-lookup"><span data-stu-id="98b3a-120">Export your results to Excel for further analysis.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="98b3a-121">Los datos de auditoría solo están visibles en el registro de auditoría si está activada la auditoría.</span><span class="sxs-lookup"><span data-stu-id="98b3a-121">Audit data is only visible in the Audit Log if auditing is turned on.</span></span>

## <a name="external-user-scenario"></a><span data-ttu-id="98b3a-122">Escenario de usuario externo</span><span class="sxs-lookup"><span data-stu-id="98b3a-122">External user scenario</span></span>

<span data-ttu-id="98b3a-123">Un escenario que quizás desee mantener a la vista desde una perspectiva empresarial es la adición de usuarios externos a su entorno de equipos.</span><span class="sxs-lookup"><span data-stu-id="98b3a-123">One scenario you might want to keep an eye on, from a business perspective, is the addition of external users to your Teams environment.</span></span> <span data-ttu-id="98b3a-124">Si los usuarios externos están habilitados, la supervisión de su presencia es una buena idea.</span><span class="sxs-lookup"><span data-stu-id="98b3a-124">If external users are enabled, then monitoring their presence is a good idea.</span></span>

![Captura de pantalla de una lista de eventos desencadenada por eliminaciones masivas](media/TeamsExternalUserAddPolicy.png)

<span data-ttu-id="98b3a-126">La captura de pantalla de esta directiva para supervisar adiciones de usuarios externos le permite asignar un nombre a la Directiva, establecer la gravedad según sus necesidades empresariales, establecerla como (en este caso) una sola actividad y, a continuación, establecer los parámetros que solo supervisarán específicamente la adición. de usuarios no internos y limitar esta actividad a Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="98b3a-126">The screenshot of this policy to monitor external user adds allows you to name the policy, set the severity according to your business needs, set it as (in this case) a single activity, and then establish the parameters that will specifically monitor only the addition of non-internal users, and limit this activity to Microsoft Teams.</span></span>

<span data-ttu-id="98b3a-127">Entonces, los resultados de esta directiva podrán verse en el registro de actividades:</span><span class="sxs-lookup"><span data-stu-id="98b3a-127">Then results from this policy will be able to be viewed in the activity log:</span></span>

![Captura de pantalla de una lista de eventos desencadenada por eliminaciones masivas](media/TeamsExternalUserList.png)

<span data-ttu-id="98b3a-129">Aquí puede revisar las coincidencias con la Directiva que ha establecido, realizar los ajustes necesarios, o exportar los resultados para usarlos en otro lugar.</span><span class="sxs-lookup"><span data-stu-id="98b3a-129">Here you can review matches to the policy you've set, and make any adjustments as needed, or export the results to use elsewhere.</span></span>

## <a name="mass-delete-scenario"></a><span data-ttu-id="98b3a-130">Escenario de eliminación masiva</span><span class="sxs-lookup"><span data-stu-id="98b3a-130">Mass delete scenario</span></span>

<span data-ttu-id="98b3a-131">Como se mencionó anteriormente, puede supervisar los escenarios de eliminación.</span><span class="sxs-lookup"><span data-stu-id="98b3a-131">As mentioned above, you can monitor deletion scenarios.</span></span> <span data-ttu-id="98b3a-132">Es posible crear una directiva que supervisará la eliminación masiva de sitios de Teams:</span><span class="sxs-lookup"><span data-stu-id="98b3a-132">It's possible to create a policy that would monitor mass deletion of Teams sites:</span></span>

![Captura de pantalla de la página creación de directiva que muestra la configuración de una directiva para la detección masiva de la eliminación de equipos](media/TeamsMassDeletePolicy.png)

<span data-ttu-id="98b3a-134">Como se muestra en la captura de pantalla, puede establecer muchos parámetros diferentes para que esta directiva supervise las eliminaciones de Teams, incluyendo la gravedad, una acción única o repetida, y los parámetros que limitan esta posibilidad a los equipos y la eliminación de sitios.</span><span class="sxs-lookup"><span data-stu-id="98b3a-134">As the screenshot shows, you can set many different parameters for this policy to monitor Teams deletions, including severity, single or repeated action, and parameters limiting this to Teams and site deletion.</span></span> <span data-ttu-id="98b3a-135">Esto puede hacerse independientemente de una plantilla o puede tener una plantilla creada para basar esta directiva en función de las necesidades de la organización.</span><span class="sxs-lookup"><span data-stu-id="98b3a-135">This can be done independently of a template, or you may have a template created to base this policy off, depending on your organizational needs.</span></span>

<span data-ttu-id="98b3a-136">Una vez que haya establecido una directiva que funcione para su empresa, podrá revisar los resultados en el registro de actividades a medida que se activen los eventos:</span><span class="sxs-lookup"><span data-stu-id="98b3a-136">Once you've established a policy that will work for your business, you can then review the results in the activity log as events are triggered:</span></span>

![Captura de pantalla de una lista de eventos desencadenada por eliminaciones masivas](media/TeamsMassDeleteList.png)

<span data-ttu-id="98b3a-138">Puede filtrar hasta la Directiva que haya establecido para ver los resultados de esa Directiva.</span><span class="sxs-lookup"><span data-stu-id="98b3a-138">You can filter down to the policy you've set to see the results of that policy.</span></span> <span data-ttu-id="98b3a-139">Si los resultados que está recibiendo en el registro de actividades no son satisfactorios (quizá esté viendo un gran número de resultados o nada), esto puede ayudarle a ajustar la consulta para hacerla más relevante para lo que necesita.</span><span class="sxs-lookup"><span data-stu-id="98b3a-139">If the results you're getting in the activity log are not satisfactory (maybe you're seeing a lot of results, or nothing at all), this may help you to fine-tune the query to make it more relevant to what you need it to do.</span></span>

## <a name="video-techtip-using-audit-log-search-in-teams"></a><span data-ttu-id="98b3a-140">Vídeo: TechTip: Usar la búsqueda en el registro de auditoría en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="98b3a-140">Video: TechTip: Using Audit Log Search in Teams</span></span>

<span data-ttu-id="98b3a-141">Observe cómo Ansuman Acharya, un director de proyectos de Microsoft Teams, realiza una búsqueda en el registro de auditoría para Microsoft Teams en el Centro de seguridad y cumplimiento de Office 365.</span><span class="sxs-lookup"><span data-stu-id="98b3a-141">Join Ansuman Acharya, a program manager for Teams, as he demonstrates conducting an Audit Log search for Teams in the Office 365 Security & Compliance Center.</span></span>

> [!VIDEO https://www.youtube.com/embed/UBxaRySAxyE]
