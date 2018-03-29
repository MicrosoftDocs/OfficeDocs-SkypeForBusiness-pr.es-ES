---
title: Directiva de la versión de cliente crear nuevo o editar existente
ms.author: laurawi
author: LauraWi
manager: serdars
ms.date: 3/23/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientCVPolicyEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e32c6712-6dc9-4de9-8d74-9fdccf3de1ba
description: Puede especificar la versión de los clientes que se admiten en su entorno. Cuando dos clientes que ejecutan versiones diferentes interactúan entre sí, las características disponibles para cualquiera de esos clientes pueden verse limitadas por las funciones del otro cliente. Para hacer el mayor uso de las características incluidas en Skype para Business Server 2015 y mejorar la experiencia global del usuario, puede utilizar el filtro de la versión de cliente para restringir las versiones de cliente que se utilizan en su entorno. Mediante el filtro de versiones de cliente también puede ayudar a reducir los costes asociados al uso de varias versiones de cliente.
ms.openlocfilehash: 6c1e895dc03d094013f41a34cb21a12a24928172
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="client-version-policy-create-new-or-edit-existing"></a><span data-ttu-id="7aeff-106">Directiva de versión de clientes: Crear nueva o editar existente</span><span class="sxs-lookup"><span data-stu-id="7aeff-106">Client Version Policy: Create New or Edit Existing</span></span>
 
<span data-ttu-id="7aeff-107">Puede especificar la versión de los clientes que se admiten en su entorno.</span><span class="sxs-lookup"><span data-stu-id="7aeff-107">You can specify the version of clients that are supported in your environment.</span></span> <span data-ttu-id="7aeff-108">Cuando dos clientes que ejecutan versiones diferentes interactúan entre sí, las características disponibles para cualquiera de esos clientes pueden verse limitadas por las funciones del otro cliente.</span><span class="sxs-lookup"><span data-stu-id="7aeff-108">When two clients that are running different versions interact, the features that are available to either client can be limited by the capabilities of the other client.</span></span> <span data-ttu-id="7aeff-109">Para hacer el mayor uso de las características incluidas en Skype para Business Server 2015 y mejorar la experiencia global del usuario, puede utilizar el filtro de la versión de cliente para restringir las versiones de cliente que se utilizan en su entorno.</span><span class="sxs-lookup"><span data-stu-id="7aeff-109">To make the greatest use of features included in Skype for Business Server 2015 and to improve the overall user experience, you can use the client version filter to restrict the client versions that are used in your environment.</span></span> <span data-ttu-id="7aeff-110">Mediante el filtro de versiones de cliente también puede ayudar a reducir los costes asociados al uso de varias versiones de cliente.</span><span class="sxs-lookup"><span data-stu-id="7aeff-110">By using the client version filter, you can also help reduce costs associated with supporting multiple client versions.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="7aeff-p103">Los filtros se enumeran en orden de prioridad. Por ejemplo, si tiene un filtro que permite conectarse a los clientes que estén ejecutando la versión 1.5 o posterior, seguido de un filtro que bloquea los clientes que estén ejecutando una versión anterior a la 2.0, el primer filtro tiene prioridad y permitirá conectarse a los clientes que ejecuten la versión 1.5.</span><span class="sxs-lookup"><span data-stu-id="7aeff-p103">Filters are listed in order of precedence. For example, if you have a filter that allows clients running version 1.5 to connect, followed by a filter that blocks clients running a version earlier than 2.0, the first filter takes precedence, and clients running version 1.5 are allowed to connect.</span></span> 
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="7aeff-113">Tareas que puede realizar</span><span class="sxs-lookup"><span data-stu-id="7aeff-113">Tasks you can perform</span></span>

<span data-ttu-id="7aeff-114">En las páginas **Nueva directiva de versión de cliente** o **Editar directiva de versión de cliente** puede realizar las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="7aeff-114">You can perform the following tasks on the **New Client Version Policy** or **Edit Client Version Policy** page:</span></span>
  
- <span data-ttu-id="7aeff-115">Agregar o modificar el nombre o la descripción de la directiva de versión de cliente.</span><span class="sxs-lookup"><span data-stu-id="7aeff-115">Add or modify the name or description of the client version policy.</span></span>
    
- <span data-ttu-id="7aeff-116">Agregar o modificar reglas de versión de cliente de la directiva de versión de cliente.</span><span class="sxs-lookup"><span data-stu-id="7aeff-116">Add or modify client version rules for the client version policy.</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="7aeff-117">Referencia de interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="7aeff-117">UI Reference</span></span>

<span data-ttu-id="7aeff-118">En las siguientes listas se describen los menús, comandos, campos y propiedades de la página.</span><span class="sxs-lookup"><span data-stu-id="7aeff-118">The following lists describe the menus, commands, fields, and properties on the page.</span></span>
  
- <span data-ttu-id="7aeff-119">**Ámbito de aplicación** Identifica el ámbito (sitio, grupo o usuario) de la directiva de versión del cliente.</span><span class="sxs-lookup"><span data-stu-id="7aeff-119">**Scope** Identifies the scope (Site, Pool, or User) of the client version policy.</span></span>
    
- <span data-ttu-id="7aeff-120">**Nombre** Puede agregar o modificar el nombre de la directiva de versión del cliente.</span><span class="sxs-lookup"><span data-stu-id="7aeff-120">**Name** You can add or modify the name of the client version policy.</span></span>
    
- <span data-ttu-id="7aeff-121">**Descripción** Puede agregar una descripción para ayudar a identificar la directiva de la lista en la página Directiva de versión del cliente.</span><span class="sxs-lookup"><span data-stu-id="7aeff-121">**Description** You can add a description to help in identifying the policy in the list on the Client Version Policy page.</span></span>
    
- <span data-ttu-id="7aeff-122">**Nuevo** Puede agregar una nueva regla de versión del cliente a la directiva.</span><span class="sxs-lookup"><span data-stu-id="7aeff-122">**New** You can add a new client version rule to the policy.</span></span>
    
- <span data-ttu-id="7aeff-123">**Mostrar detalles** Esta opción abre un cuadro de diálogo en el que puede cambiar las opciones para una regla de la versión de cliente.</span><span class="sxs-lookup"><span data-stu-id="7aeff-123">**Show details** This option opens a dialog box in which you can change the options for a client version rule.</span></span>
    
- <span data-ttu-id="7aeff-124">**Quitar** Esta opción quita la regla de la versión de cliente seleccionado de la directiva.</span><span class="sxs-lookup"><span data-stu-id="7aeff-124">**Remove** This option removes the selected client version rule from the policy.</span></span>
    
- <span data-ttu-id="7aeff-125">**Flechas arriba y abajo** Esta opción mueve la regla de la versión de cliente seleccionado hacia arriba o hacia abajo según la prioridad.</span><span class="sxs-lookup"><span data-stu-id="7aeff-125">**Up and down arrows** This option moves the selected client version rule up or down in priority.</span></span> <span data-ttu-id="7aeff-126">Las reglas se procesan en el orden mostrado.</span><span class="sxs-lookup"><span data-stu-id="7aeff-126">Rules are processed in the order listed.</span></span>
    
<span data-ttu-id="7aeff-127">Para obtener más información acerca de la interoperabilidad entre los clientes y las versiones de cliente, vea [Interoperabilidad de cliente en la vista previa de 2013 Lync](http://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) en la documentación de planeamiento.</span><span class="sxs-lookup"><span data-stu-id="7aeff-127">For details about interoperability among clients and client versions, see [Client Interoperability in Lync 2013 Preview](http://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation.</span></span> <span data-ttu-id="7aeff-128">Para obtener más información sobre cómo trabajar con directivas de la versión de cliente, vea [especificar las versiones de cliente compatible en su organización](http://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) en la documentación de las operaciones.</span><span class="sxs-lookup"><span data-stu-id="7aeff-128">For details about working with client version policies, see [Specify the Client Versions Supported in Your Organization](http://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) in the Operations documentation.</span></span>

