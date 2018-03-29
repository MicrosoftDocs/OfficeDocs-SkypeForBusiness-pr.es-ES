---
title: Flujo de trabajo de grupos de respuesta
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.RgsWorkFlowMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e4ee8abb-e1e5-413c-919d-cd3fb7193840
description: Grupos de respuesta consisten en flujos de trabajo, colas y grupos de agentes. Flujos de trabajo de grupo de respuesta definen las acciones que se realizan cuando la aplicación de grupo de respuesta recibe una llamada de teléfono.
ms.openlocfilehash: d4fa4f946c8dd54d0abab6bea41cc632f780f747
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="response-groups-workflow"></a><span data-ttu-id="8f7d4-104">Flujo de trabajo de grupos de respuesta</span><span class="sxs-lookup"><span data-stu-id="8f7d4-104">Response Groups Workflow</span></span>
 
<span data-ttu-id="8f7d4-105">Grupos de respuesta consisten en flujos de trabajo, colas y grupos de agentes.</span><span class="sxs-lookup"><span data-stu-id="8f7d4-105">Response groups consist of agent groups, queues, and workflows.</span></span> <span data-ttu-id="8f7d4-106">Flujos de trabajo de grupo de respuesta definen las acciones que se realizan cuando la aplicación de grupo de respuesta recibe una llamada de teléfono.</span><span class="sxs-lookup"><span data-stu-id="8f7d4-106">Response Group workflows define the actions that are taken when the Response Group application receives a phone call.</span></span> 
  
<span data-ttu-id="8f7d4-107">Los **Grupos de respuesta** - página de**flujo de trabajo** muestra una lista de todos los flujos de trabajo de grupo de respuesta que se definen para su organización.</span><span class="sxs-lookup"><span data-stu-id="8f7d4-107">The **Response Groups** - **Workflow** page displays a list of all the Response Group workflows that are defined for your organization.</span></span>
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="8f7d4-108">Tareas que puede realizar</span><span class="sxs-lookup"><span data-stu-id="8f7d4-108">Tasks you can perform</span></span>

<span data-ttu-id="8f7d4-109">Puede realizar las siguientes tareas de los **Grupos de respuesta** - página de**flujo de trabajo** :</span><span class="sxs-lookup"><span data-stu-id="8f7d4-109">You can perform the following tasks from the **Response Groups** - **Workflow** page:</span></span>
  
- <span data-ttu-id="8f7d4-110">Crear o cambiar un flujo de trabajo de grupo de captura</span><span class="sxs-lookup"><span data-stu-id="8f7d4-110">Create or change a hunt group workflow</span></span>
    
- <span data-ttu-id="8f7d4-111">Crear o cambiar un flujo de trabajo interactivo</span><span class="sxs-lookup"><span data-stu-id="8f7d4-111">Create or change an interactive workflow</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="8f7d4-112">Referencia de interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="8f7d4-112">UI Reference</span></span>

<span data-ttu-id="8f7d4-113">En la siguiente lista se describen los comandos de la página.</span><span class="sxs-lookup"><span data-stu-id="8f7d4-113">The following list describes the commands on the page.</span></span>
  
- <span data-ttu-id="8f7d4-114">**Creación o edición de un flujo de trabajo** Abre la herramienta de configuración de grupo de respuesta para crear o editar un flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="8f7d4-114">**Create or edit a workflow** Opens the Response Group Configuration Tool for creating or editing a workflow.</span></span>
    
- <span data-ttu-id="8f7d4-115">**Actualizar** Actualiza la lista de flujos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="8f7d4-115">**Refresh** Refreshes the list of workflows.</span></span>
    
<span data-ttu-id="8f7d4-116">En la siguiente lista se describen los campos de la página.</span><span class="sxs-lookup"><span data-stu-id="8f7d4-116">The following list describes the fields on the page.</span></span>
  
- <span data-ttu-id="8f7d4-117">**Nombre** El nombre único que se asigna al flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="8f7d4-117">**Name** The unique name that is assigned to the workflow.</span></span>
    
- <span data-ttu-id="8f7d4-118">**Servicio** El servicio de **ApplicationServer** que alberga el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="8f7d4-118">**Service** The **ApplicationServer** service that hosts the workflow.</span></span>
    
- <span data-ttu-id="8f7d4-119">**Dirección SIP** La dirección SIP del grupo que responderá a las llamadas al flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="8f7d4-119">**SIP address** The SIP address of the group that will answer calls to the workflow.</span></span>
    
- <span data-ttu-id="8f7d4-120">**Teléfono** El número de teléfono al que se llama para llegar a este grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="8f7d4-120">**Telephone** The phone number that is called to reach this response group.</span></span>
    
- <span data-ttu-id="8f7d4-121">**Idioma** El idioma que se utiliza para texto a voz y reconocimiento de voz.</span><span class="sxs-lookup"><span data-stu-id="8f7d4-121">**Language** The language that is used for speech recognition and text-to-speech.</span></span>
    
- <span data-ttu-id="8f7d4-122">**IVR** Indica si el flujo de trabajo es un flujo de trabajo interactivo o un grupo de captura.</span><span class="sxs-lookup"><span data-stu-id="8f7d4-122">**IVR** Indicates whether the workflow is a hunt group or an interactive workflow.</span></span>
    
- <span data-ttu-id="8f7d4-123">**Habilitado** Indica si se activa el flujo de trabajo para recibir llamadas.</span><span class="sxs-lookup"><span data-stu-id="8f7d4-123">**Enabled** Indicates whether the workflow is activated to receive calls.</span></span>
    
<span data-ttu-id="8f7d4-124">Para obtener más información acerca de capacidades y características de los grupos de respuesta, vea [Planear la aplicación de grupo de respuesta en Skype para Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/response-group.md) en la documentación de planeamiento.</span><span class="sxs-lookup"><span data-stu-id="8f7d4-124">For details about Response Group features and capabilities, see [Plan for the Response Group application in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/response-group.md) in the Planning documentation.</span></span> <span data-ttu-id="8f7d4-125">Para obtener más información acerca de cómo trabajar con flujos de trabajo de grupo de respuesta, vea [Administrar flujos de trabajo de grupo de respuesta](http://technet.microsoft.com/library/42cfccdd-2844-4875-b4e3-813e1df15f08.aspx) en la documentación de las operaciones.</span><span class="sxs-lookup"><span data-stu-id="8f7d4-125">For details about working with Response Group workflows, see [Managing Response Group Workflows](http://technet.microsoft.com/library/42cfccdd-2844-4875-b4e3-813e1df15f08.aspx) in the Operations documentation.</span></span>
  

