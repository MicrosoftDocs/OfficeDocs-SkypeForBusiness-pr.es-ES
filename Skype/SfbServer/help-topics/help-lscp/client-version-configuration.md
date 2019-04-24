---
title: Configuración de versiones de cliente
ms.reviewer: ''
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
ms.openlocfilehash: 99938b2474a467c7c80148a7e0c3cab12320381f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32200945"
---
# <a name="client-version-configuration"></a><span data-ttu-id="31dd9-104">Configuración de versiones de cliente</span><span class="sxs-lookup"><span data-stu-id="31dd9-104">Client Version Configuration</span></span>

<span data-ttu-id="31dd9-105">Además de especificar la versión de los clientes que desea admitir en su entorno, también puede especificar una acción predeterminada para los clientes que aún no tiene una directiva de versión que se haya definido.</span><span class="sxs-lookup"><span data-stu-id="31dd9-105">In addition to specifying the version of clients that you want to support in your environment, you can also specify a default action for clients that do not already have a version policy defined.</span></span> <span data-ttu-id="31dd9-106">Esto le permite restringir qué versiones de cliente se usan en su entorno, que puede ayudar a controlar los costes asociados con el uso de varias versiones de cliente.</span><span class="sxs-lookup"><span data-stu-id="31dd9-106">This enables you to restrict which client versions are used in your environment, which can help you to control the costs associated with supporting multiple client versions.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="31dd9-107">Tareas que puede realizar</span><span class="sxs-lookup"><span data-stu-id="31dd9-107">Tasks you can perform</span></span>

<span data-ttu-id="31dd9-108">Puede realizar las siguientes tareas en la página **Configuración de la versión de cliente** :</span><span class="sxs-lookup"><span data-stu-id="31dd9-108">You can perform the following tasks on the **Client Version Configuration** page:</span></span>

- <span data-ttu-id="31dd9-109">Editar la configuración de versión de cliente predeterminada ( **Global**).</span><span class="sxs-lookup"><span data-stu-id="31dd9-109">Edit the default ( **Global**) client version configuration.</span></span>

- <span data-ttu-id="31dd9-110">Crear la configuración de la versión de cliente para un sitio concreto.</span><span class="sxs-lookup"><span data-stu-id="31dd9-110">Create client version configuration for a particular site.</span></span>

- <span data-ttu-id="31dd9-111">Habilitar y deshabilitar las configuraciones de versión de cliente existente.</span><span class="sxs-lookup"><span data-stu-id="31dd9-111">Enable and disable existing client version configurations.</span></span>

> [!NOTE]
> <span data-ttu-id="31dd9-112">Debido a que los usuarios anónimos no están asociados con un sitio, los usuarios anónimos se ven afectados por directivas de nivel global sólo.</span><span class="sxs-lookup"><span data-stu-id="31dd9-112">Because anonymous users are not associated with a site, anonymous users are affected by global-level policies only.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="31dd9-113">Referencia de interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="31dd9-113">UI Reference</span></span>

<span data-ttu-id="31dd9-114">En las siguientes listas se describen los menús, comandos, campos y propiedades de la página.</span><span class="sxs-lookup"><span data-stu-id="31dd9-114">The following lists describe the menus, command, fields, and properties on the page.</span></span>

- <span data-ttu-id="31dd9-115">**Nuevo** Puede crear una configuración de versión de cliente para un sitio concreto.</span><span class="sxs-lookup"><span data-stu-id="31dd9-115">**New** You can create a client version configuration for a particular site.</span></span>

- <span data-ttu-id="31dd9-116">**Editar** Puede cambiar las opciones de cualquiera de las directivas de versión de cliente.</span><span class="sxs-lookup"><span data-stu-id="31dd9-116">**Edit** You can change the options of any of the client version policies.</span></span> <span data-ttu-id="31dd9-117">Al usar esta opción, puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="31dd9-117">Using this option, you can do the following:</span></span>

  - <span data-ttu-id="31dd9-118">**Mostrar detalles** Esta opción abre un cuadro de diálogo en el que puede cambiar las opciones para una configuración de versión de cliente.</span><span class="sxs-lookup"><span data-stu-id="31dd9-118">**Show details** This option opens a dialog box in which you can change the options for a client version configuration.</span></span>

  - <span data-ttu-id="31dd9-119">**Seleccionar todo** Esta opción selecciona todas las configuraciones de versión de cliente de la lista.</span><span class="sxs-lookup"><span data-stu-id="31dd9-119">**Select All** This option selects all client version configurations in the list.</span></span>

  - <span data-ttu-id="31dd9-120">**Eliminar** Esta opción elimina todas las configuraciones de versión de cliente seleccionada.</span><span class="sxs-lookup"><span data-stu-id="31dd9-120">**Delete** This option deletes all selected client version configurations.</span></span>

- <span data-ttu-id="31dd9-121">**Actualizar** Puede actualizar la lista de configuración de versión de cliente para comprobar el estado de las opciones de todas las configuraciones de versión de cliente.</span><span class="sxs-lookup"><span data-stu-id="31dd9-121">**Refresh** You can refresh the client version configuration list to verify the status of the options of all client version configurations.</span></span>

<span data-ttu-id="31dd9-p104">Para más detalles sobre la interoperabilidad entre clientes y versiones de clientes, mire [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) en la documentación de planeación. Para más detalles sobre cómo trabajar con configuraciones de versiones de clientes, mire [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="31dd9-p104">For details about interoperability among clients and client versions, see [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation. For details about working with client version configurations, see [Modify the Default Action for Clients Not Explicitly Supported or Restricted](https://technet.microsoft.com/library/548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3.aspx) in the Operations documentation.</span></span>

