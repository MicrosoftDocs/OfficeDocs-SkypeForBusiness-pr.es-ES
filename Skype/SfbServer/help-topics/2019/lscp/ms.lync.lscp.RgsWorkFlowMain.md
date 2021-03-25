---
title: Flujo de trabajo de grupos de respuesta
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.RgsWorkFlowMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: e4ee8abb-e1e5-413c-919d-cd3fb7193840
ROBOTS: NOINDEX, NOFOLLOW
description: Los grupos de respuestas constan de grupos de agentes, colas y flujos de trabajo. Los flujos de trabajo del grupo de respuesta definen las acciones que se toman cuando la aplicación grupo de respuesta recibe una llamada telefónica.
ms.openlocfilehash: dc34ec69af86658c6624ada6a9f25ff3aaa61499
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118769"
---
# <a name="response-groups-workflow"></a><span data-ttu-id="e625f-104">Flujo de trabajo de grupos de respuesta</span><span class="sxs-lookup"><span data-stu-id="e625f-104">Response Groups Workflow</span></span>

<span data-ttu-id="e625f-105">Los grupos de respuestas constan de grupos de agentes, colas y flujos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="e625f-105">Response groups consist of agent groups, queues, and workflows.</span></span> <span data-ttu-id="e625f-106">Los flujos de trabajo del grupo de respuesta definen las acciones que se toman cuando la aplicación grupo de respuesta recibe una llamada telefónica.</span><span class="sxs-lookup"><span data-stu-id="e625f-106">Response Group workflows define the actions that are taken when the Response Group application receives a phone call.</span></span>

<span data-ttu-id="e625f-107">La **página Flujo de trabajo** grupos de respuesta muestra una lista de todos los flujos de trabajo del grupo de respuesta  -   definidos para la organización.</span><span class="sxs-lookup"><span data-stu-id="e625f-107">The **Response Groups** - **Workflow** page displays a list of all the Response Group workflows that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="e625f-108">Tareas que puede realizar</span><span class="sxs-lookup"><span data-stu-id="e625f-108">Tasks you can perform</span></span>

<span data-ttu-id="e625f-109">Puede realizar las siguientes tareas desde la página Flujo de **trabajo de grupos**  -  **de** respuesta:</span><span class="sxs-lookup"><span data-stu-id="e625f-109">You can perform the following tasks from the **Response Groups** - **Workflow** page:</span></span>

- <span data-ttu-id="e625f-110">Crear o cambiar un flujo de trabajo de grupo de búsqueda</span><span class="sxs-lookup"><span data-stu-id="e625f-110">Create or change a hunt group workflow</span></span>

- <span data-ttu-id="e625f-111">Crear o cambiar el flujo de trabajo interactivo</span><span class="sxs-lookup"><span data-stu-id="e625f-111">Create or change an interactive workflow</span></span>

## <a name="ui-reference"></a><span data-ttu-id="e625f-112">Referencia de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="e625f-112">UI Reference</span></span>

<span data-ttu-id="e625f-113">En la siguiente lista se describen los comandos de la página.</span><span class="sxs-lookup"><span data-stu-id="e625f-113">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="e625f-114">**Crear o editar un flujo de trabajo** Abre la Herramienta de configuración de grupo de respuesta para crear o editar un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="e625f-114">**Create or edit a workflow** Opens the Response Group Configuration Tool for creating or editing a workflow.</span></span>

- <span data-ttu-id="e625f-115">**Actualizar** Actualiza la lista de flujos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="e625f-115">**Refresh** Refreshes the list of workflows.</span></span>

<span data-ttu-id="e625f-116">En la siguiente lista se describen los campos de la página.</span><span class="sxs-lookup"><span data-stu-id="e625f-116">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="e625f-117">**Nombre** Nombre único que se asigna al flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="e625f-117">**Name** The unique name that is assigned to the workflow.</span></span>

- <span data-ttu-id="e625f-118">**Servicio** El **servicio ApplicationServer** que hospeda el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="e625f-118">**Service** The **ApplicationServer** service that hosts the workflow.</span></span>

- <span data-ttu-id="e625f-119">**Dirección SIP** La dirección SIP del grupo que responderá las llamadas al flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="e625f-119">**SIP address** The SIP address of the group that will answer calls to the workflow.</span></span>

- <span data-ttu-id="e625f-120">**Teléfono** Número de teléfono al que se llama para llegar a este grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="e625f-120">**Telephone** The phone number that is called to reach this response group.</span></span>

- <span data-ttu-id="e625f-121">**Idioma** El idioma que se usa para el reconocimiento de voz y texto a voz.</span><span class="sxs-lookup"><span data-stu-id="e625f-121">**Language** The language that is used for speech recognition and text-to-speech.</span></span>

- <span data-ttu-id="e625f-122">**IVR** Indica si el flujo de trabajo es un grupo de extensiones o un flujo de trabajo interactivo.</span><span class="sxs-lookup"><span data-stu-id="e625f-122">**IVR** Indicates whether the workflow is a hunt group or an interactive workflow.</span></span>

- <span data-ttu-id="e625f-123">**Habilitado** Indica si el flujo de trabajo está activado para recibir llamadas.</span><span class="sxs-lookup"><span data-stu-id="e625f-123">**Enabled** Indicates whether the workflow is activated to receive calls.</span></span>

<span data-ttu-id="e625f-124">Para obtener más información sobre las características y capacidades del grupo de respuesta, vea [Plan for the Response Group application in Skype for Business Server](../../../plan-your-deployment/enterprise-voice-solution/response-group.md) en la documentación sobre planeación.</span><span class="sxs-lookup"><span data-stu-id="e625f-124">For details about Response Group features and capabilities, see [Plan for the Response Group application in Skype for Business Server](../../../plan-your-deployment/enterprise-voice-solution/response-group.md) in the Planning documentation.</span></span> <span data-ttu-id="e625f-125">Para obtener más información sobre cómo trabajar con flujos de trabajo de grupo de respuesta, consulte [Managing Response Group Workflows](/previous-versions/office/lync-server-2013/lync-server-2013-managing-response-group-workflows) en la documentación sobre operaciones.</span><span class="sxs-lookup"><span data-stu-id="e625f-125">For details about working with Response Group workflows, see [Managing Response Group Workflows](/previous-versions/office/lync-server-2013/lync-server-2013-managing-response-group-workflows) in the Operations documentation.</span></span>