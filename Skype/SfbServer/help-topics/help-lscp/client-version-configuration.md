---
title: Configuración de la versión de cliente
ms.author: SerdarS
author: SerdarSoysal
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientCVSettingMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cb17314e-b89e-4821-8855-12f8fd2edc9b
description: Además de especificar la versión de los clientes que desea admitir en su entorno, también puede especificar una acción predeterminada para los clientes que aún no tiene una directiva de versión que se haya definido. Esto le permite restringir qué versiones de cliente se usan en su entorno, que puede ayudar a controlar los costes asociados con el uso de varias versiones de cliente.
ms.openlocfilehash: 5740684ee266bf3f976e355fb222988a7261277a
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "21025929"
---
# <a name="client-version-configuration"></a><span data-ttu-id="9c062-104">Configuración de la versión de cliente</span><span class="sxs-lookup"><span data-stu-id="9c062-104">Client Version Configuration</span></span>
 
<span data-ttu-id="9c062-105">Además de especificar la versión de los clientes que desea admitir en su entorno, también puede especificar una acción predeterminada para los clientes que aún no tiene una directiva de versión que se haya definido.</span><span class="sxs-lookup"><span data-stu-id="9c062-105">In addition to specifying the version of clients that you want to support in your environment, you can also specify a default action for clients that do not already have a version policy defined.</span></span> <span data-ttu-id="9c062-106">Esto le permite restringir qué versiones de cliente se usan en su entorno, que puede ayudar a controlar los costes asociados con el uso de varias versiones de cliente.</span><span class="sxs-lookup"><span data-stu-id="9c062-106">This enables you to restrict which client versions are used in your environment, which can help you to control the costs associated with supporting multiple client versions.</span></span>
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="9c062-107">Tareas que puede realizar</span><span class="sxs-lookup"><span data-stu-id="9c062-107">Tasks you can perform</span></span>

<span data-ttu-id="9c062-108">Puede realizar las siguientes tareas en la página **Configuración de la versión de cliente** :</span><span class="sxs-lookup"><span data-stu-id="9c062-108">You can perform the following tasks on the **Client Version Configuration** page:</span></span>
  
- <span data-ttu-id="9c062-109">Editar la configuración de versión de cliente predeterminada ( **Global**).</span><span class="sxs-lookup"><span data-stu-id="9c062-109">Edit the default ( **Global**) client version configuration.</span></span>
    
- <span data-ttu-id="9c062-110">Crear la configuración de la versión de cliente para un sitio concreto.</span><span class="sxs-lookup"><span data-stu-id="9c062-110">Create client version configuration for a particular site.</span></span>
    
- <span data-ttu-id="9c062-111">Habilitar y deshabilitar las configuraciones de versión de cliente existente.</span><span class="sxs-lookup"><span data-stu-id="9c062-111">Enable and disable existing client version configurations.</span></span>
    
> [!NOTE]
> <span data-ttu-id="9c062-112">Debido a que los usuarios anónimos no están asociados con un sitio, los usuarios anónimos se ven afectados por directivas de nivel global sólo.</span><span class="sxs-lookup"><span data-stu-id="9c062-112">Because anonymous users are not associated with a site, anonymous users are affected by global-level policies only.</span></span> 
  
## <a name="ui-reference"></a><span data-ttu-id="9c062-113">Referencia de interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="9c062-113">UI Reference</span></span>

<span data-ttu-id="9c062-114">En las siguientes listas se describen los menús, comandos, campos y propiedades de la página.</span><span class="sxs-lookup"><span data-stu-id="9c062-114">The following lists describe the menus, command, fields, and properties on the page.</span></span>
  
- <span data-ttu-id="9c062-115">**Nuevo** Puede crear una configuración de versión de cliente para un sitio concreto.</span><span class="sxs-lookup"><span data-stu-id="9c062-115">**New** You can create a client version configuration for a particular site.</span></span>
    
- <span data-ttu-id="9c062-116">**Editar** Puede cambiar las opciones de cualquiera de las directivas de versión de cliente.</span><span class="sxs-lookup"><span data-stu-id="9c062-116">**Edit** You can change the options of any of the client version policies.</span></span> <span data-ttu-id="9c062-117">Al usar esta opción, puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9c062-117">Using this option, you can do the following:</span></span>
    
  - <span data-ttu-id="9c062-118">**Mostrar detalles** Esta opción abre un cuadro de diálogo en el que puede cambiar las opciones para una configuración de versión de cliente.</span><span class="sxs-lookup"><span data-stu-id="9c062-118">**Show details** This option opens a dialog box in which you can change the options for a client version configuration.</span></span>
    
  - <span data-ttu-id="9c062-119">**Seleccionar todo** Esta opción selecciona todas las configuraciones de versión de cliente de la lista.</span><span class="sxs-lookup"><span data-stu-id="9c062-119">**Select All** This option selects all client version configurations in the list.</span></span>
    
  - <span data-ttu-id="9c062-120">**Eliminar** Esta opción elimina todas las configuraciones de versión de cliente seleccionada.</span><span class="sxs-lookup"><span data-stu-id="9c062-120">**Delete** This option deletes all selected client version configurations.</span></span>
    
- <span data-ttu-id="9c062-121">**Actualizar** Puede actualizar la lista de configuración de versión de cliente para comprobar el estado de las opciones de todas las configuraciones de versión de cliente.</span><span class="sxs-lookup"><span data-stu-id="9c062-121">**Refresh** You can refresh the client version configuration list to verify the status of the options of all client version configurations.</span></span>
    
<span data-ttu-id="9c062-122">Para obtener información detallada acerca de la interoperabilidad entre clientes y versiones de cliente, consulte [Client Interoperability in Lync 2013 Preview](http://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="9c062-122">For details about interoperability among clients and client versions, see [Client Interoperability in Lync 2013 Preview](http://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation.</span></span> <span data-ttu-id="9c062-123">Para obtener información detallada sobre cómo trabajar con las configuraciones de versión de cliente, vea [modificar la acción predeterminada para los clientes no admiten explícitamente o restringidos](http://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) en la documentación sobre operaciones.</span><span class="sxs-lookup"><span data-stu-id="9c062-123">For details about working with client version configurations, see [Modify the Default Action for Clients Not Explicitly Supported or Restricted](http://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) in the Operations documentation.</span></span>

