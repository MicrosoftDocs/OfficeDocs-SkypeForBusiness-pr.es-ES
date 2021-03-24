---
title: Configuración de versiones de cliente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientCVSettingMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: cb17314e-b89e-4821-8855-12f8fd2edc9b
ROBOTS: NOINDEX, NOFOLLOW
description: Además de especificar la versión de los clientes que desea admitir en su entorno, también puede especificar una acción predeterminada para clientes que todavía no tengan definida una directiva de versión. Esto permite restringir las versiones de cliente que se usan en su entorno, lo que puede ayudar a controlar los costes asociados con la compatibilidad con distintas versiones de cliente.
ms.openlocfilehash: 69d8c15688e6afce2f1e92cebc20ad8fb6bc7464
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100656"
---
# <a name="client-version-configuration"></a><span data-ttu-id="9a793-104">Configuración de versiones de cliente</span><span class="sxs-lookup"><span data-stu-id="9a793-104">Client Version Configuration</span></span>

<span data-ttu-id="9a793-p102">Además de especificar la versión de los clientes que desea admitir en su entorno, también puede especificar una acción predeterminada para clientes que todavía no tengan definida una directiva de versión. Esto permite restringir las versiones de cliente que se usan en su entorno, lo que puede ayudar a controlar los costes asociados con la compatibilidad con distintas versiones de cliente.</span><span class="sxs-lookup"><span data-stu-id="9a793-p102">In addition to specifying the version of clients that you want to support in your environment, you can also specify a default action for clients that do not already have a version policy defined. This enables you to restrict which client versions are used in your environment, which can help you to control the costs associated with supporting multiple client versions.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="9a793-107">Tareas que puede realizar</span><span class="sxs-lookup"><span data-stu-id="9a793-107">Tasks you can perform</span></span>

<span data-ttu-id="9a793-108">Puede realizar las siguientes tareas en la página **Configuración de versión de cliente**:</span><span class="sxs-lookup"><span data-stu-id="9a793-108">You can perform the following tasks on the **Client Version Configuration** page:</span></span>

- <span data-ttu-id="9a793-109">Edite la configuración de versión de cliente predeterminada ( **Global**).</span><span class="sxs-lookup"><span data-stu-id="9a793-109">Edit the default ( **Global**) client version configuration.</span></span>

- <span data-ttu-id="9a793-110">Crear configuraciones de versión de cliente para un sitio concreto.</span><span class="sxs-lookup"><span data-stu-id="9a793-110">Create client version configuration for a particular site.</span></span>

- <span data-ttu-id="9a793-111">Habilitar y deshabilitar configuraciones de versión de cliente existentes.</span><span class="sxs-lookup"><span data-stu-id="9a793-111">Enable and disable existing client version configurations.</span></span>

> [!NOTE]
> <span data-ttu-id="9a793-112">Debido a que los usuarios anónimos no están asociados a un sitio, los usuarios solo se ven afectados por directivas de nivel global.</span><span class="sxs-lookup"><span data-stu-id="9a793-112">Because anonymous users are not associated with a site, anonymous users are affected by global-level policies only.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="9a793-113">Referencia de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="9a793-113">UI Reference</span></span>

<span data-ttu-id="9a793-114">Las siguientes listas describen los menús, comandos, campos y propiedades de la página.</span><span class="sxs-lookup"><span data-stu-id="9a793-114">The following lists describe the menus, command, fields, and properties on the page.</span></span>

- <span data-ttu-id="9a793-115">**Nuevo** Puede crear una configuración de versión de cliente para un sitio determinado.</span><span class="sxs-lookup"><span data-stu-id="9a793-115">**New** You can create a client version configuration for a particular site.</span></span>

- <span data-ttu-id="9a793-116">**Editar** Puede cambiar las opciones de cualquiera de las directivas de versión de cliente.</span><span class="sxs-lookup"><span data-stu-id="9a793-116">**Edit** You can change the options of any of the client version policies.</span></span> <span data-ttu-id="9a793-117">Al usar esta opción, puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9a793-117">Using this option, you can do the following:</span></span>

  - <span data-ttu-id="9a793-118">**Mostrar detalles** Esta opción abre un cuadro de diálogo en el que puede cambiar las opciones de una configuración de versión de cliente.</span><span class="sxs-lookup"><span data-stu-id="9a793-118">**Show details** This option opens a dialog box in which you can change the options for a client version configuration.</span></span>

  - <span data-ttu-id="9a793-119">**Seleccionar todo** Esta opción selecciona todas las configuraciones de versión de cliente de la lista.</span><span class="sxs-lookup"><span data-stu-id="9a793-119">**Select All** This option selects all client version configurations in the list.</span></span>

  - <span data-ttu-id="9a793-120">**Eliminar** Esta opción elimina todas las configuraciones de versión de cliente seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="9a793-120">**Delete** This option deletes all selected client version configurations.</span></span>

- <span data-ttu-id="9a793-121">**Actualizar** Puede actualizar la lista de configuración de versión de cliente para comprobar el estado de las opciones de todas las configuraciones de versión de cliente.</span><span class="sxs-lookup"><span data-stu-id="9a793-121">**Refresh** You can refresh the client version configuration list to verify the status of the options of all client version configurations.</span></span>

<span data-ttu-id="9a793-122">Para obtener más información sobre la interoperabilidad entre clientes y versiones de cliente, consulte [Client Interoperability](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013) en la documentación sobre planeación.</span><span class="sxs-lookup"><span data-stu-id="9a793-122">For details about interoperability among clients and client versions, see [Client Interoperability](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013) in the Planning documentation.</span></span> <span data-ttu-id="9a793-123">Para obtener detalles sobre cómo trabajar con configuraciones de versiones de clientes, vea [Modify the Default Action for Clients Not Explicitly Supported or Restricted](/previous-versions/office/lync-server-2013/lync-server-2013-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted) en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="9a793-123">For details about working with client version configurations, see [Modify the Default Action for Clients Not Explicitly Supported or Restricted](/previous-versions/office/lync-server-2013/lync-server-2013-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted) in the Operations documentation.</span></span>