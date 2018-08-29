---
title: Flujo de trabajo de grupos de respuesta
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.RgsWorkFlowMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e4ee8abb-e1e5-413c-919d-cd3fb7193840
description: Grupos de respuesta constan de grupos de agentes, colas y flujos de trabajo. Los flujos de trabajo de grupo de respuesta definen las acciones que se toman cuando la aplicación de grupo de respuesta recibe una llamada de teléfono.
ms.openlocfilehash: c2b57fd156689b5804e2705d79c515ffe52498b6
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/28/2018
ms.locfileid: "23258287"
---
# <a name="response-groups-workflow"></a><span data-ttu-id="51a50-104">Flujo de trabajo de grupos de respuesta</span><span class="sxs-lookup"><span data-stu-id="51a50-104">Response Groups Workflow</span></span>

<span data-ttu-id="51a50-105">Grupos de respuesta constan de grupos de agentes, colas y flujos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="51a50-105">Response groups consist of agent groups, queues, and workflows.</span></span> <span data-ttu-id="51a50-106">Los flujos de trabajo de grupo de respuesta definen las acciones que se toman cuando la aplicación de grupo de respuesta recibe una llamada de teléfono.</span><span class="sxs-lookup"><span data-stu-id="51a50-106">Response Group workflows define the actions that are taken when the Response Group application receives a phone call.</span></span>

<span data-ttu-id="51a50-107">Los **Grupos de respuesta** - página de**flujo de trabajo** muestra una lista de todos los flujos de trabajo de grupo de respuesta que se definen para su organización.</span><span class="sxs-lookup"><span data-stu-id="51a50-107">The **Response Groups** - **Workflow** page displays a list of all the Response Group workflows that are defined for your organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="51a50-108">Tareas que puede realizar</span><span class="sxs-lookup"><span data-stu-id="51a50-108">Tasks you can perform</span></span>

<span data-ttu-id="51a50-109">Puede realizar las siguientes tareas desde los **Grupos de respuesta** - página de**flujo de trabajo** :</span><span class="sxs-lookup"><span data-stu-id="51a50-109">You can perform the following tasks from the **Response Groups** - **Workflow** page:</span></span>

- <span data-ttu-id="51a50-110">Crear o cambiar un flujo de trabajo de grupo de búsqueda</span><span class="sxs-lookup"><span data-stu-id="51a50-110">Create or change a hunt group workflow</span></span>

- <span data-ttu-id="51a50-111">Crear o cambiar un flujo de trabajo interactivo</span><span class="sxs-lookup"><span data-stu-id="51a50-111">Create or change an interactive workflow</span></span>

## <a name="ui-reference"></a><span data-ttu-id="51a50-112">Referencia de interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="51a50-112">UI Reference</span></span>

<span data-ttu-id="51a50-113">En la siguiente lista se describen los comandos de la página.</span><span class="sxs-lookup"><span data-stu-id="51a50-113">The following list describes the commands on the page.</span></span>

- <span data-ttu-id="51a50-114">**Crear o editar un flujo de trabajo** Se abre la herramienta de configuración de grupo de respuesta para crear o editar un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="51a50-114">**Create or edit a workflow** Opens the Response Group Configuration Tool for creating or editing a workflow.</span></span>

- <span data-ttu-id="51a50-115">**Actualizar** Actualiza la lista de flujos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="51a50-115">**Refresh** Refreshes the list of workflows.</span></span>

<span data-ttu-id="51a50-116">En la siguiente lista se describen los campos de la página.</span><span class="sxs-lookup"><span data-stu-id="51a50-116">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="51a50-117">**Nombre** El nombre único que se asigna al flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="51a50-117">**Name** The unique name that is assigned to the workflow.</span></span>

- <span data-ttu-id="51a50-118">**Servicio** El servicio de **ApplicationServer** que hospeda el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="51a50-118">**Service** The **ApplicationServer** service that hosts the workflow.</span></span>

- <span data-ttu-id="51a50-119">**Dirección SIP** La dirección SIP del grupo que responderá las llamadas al flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="51a50-119">**SIP address** The SIP address of the group that will answer calls to the workflow.</span></span>

- <span data-ttu-id="51a50-120">**Teléfono** El número de teléfono que se llama para llegar a este grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="51a50-120">**Telephone** The phone number that is called to reach this response group.</span></span>

- <span data-ttu-id="51a50-121">**Idioma** El idioma que se usa para el reconocimiento de voz y texto a voz.</span><span class="sxs-lookup"><span data-stu-id="51a50-121">**Language** The language that is used for speech recognition and text-to-speech.</span></span>

- <span data-ttu-id="51a50-122">**IVR** Indica si el flujo de trabajo es un grupo de extensiones o un flujo de trabajo interactivo.</span><span class="sxs-lookup"><span data-stu-id="51a50-122">**IVR** Indicates whether the workflow is a hunt group or an interactive workflow.</span></span>

- <span data-ttu-id="51a50-123">**Habilitado** Indica si el flujo de trabajo está activado para recibir llamadas.</span><span class="sxs-lookup"><span data-stu-id="51a50-123">**Enabled** Indicates whether the workflow is activated to receive calls.</span></span>

<span data-ttu-id="51a50-124">Para obtener información detallada sobre las características de grupo de respuesta y funciones, consulte [Plan para la aplicación de grupo de respuesta en Skype para Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/response-group.md) en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="51a50-124">For details about Response Group features and capabilities, see [Plan for the Response Group application in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/response-group.md) in the Planning documentation.</span></span> <span data-ttu-id="51a50-125">Para obtener información detallada sobre cómo trabajar con flujos de trabajo de grupo de respuesta, vea [Administrar flujos de trabajo de grupo de respuesta](https://technet.microsoft.com/library/42cfccdd-2844-4875-b4e3-813e1df15f08.aspx) en la documentación sobre operaciones.</span><span class="sxs-lookup"><span data-stu-id="51a50-125">For details about working with Response Group workflows, see [Managing Response Group Workflows](https://technet.microsoft.com/library/42cfccdd-2844-4875-b4e3-813e1df15f08.aspx) in the Operations documentation.</span></span>


