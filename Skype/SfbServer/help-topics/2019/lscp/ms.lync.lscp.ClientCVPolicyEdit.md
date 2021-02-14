---
title: Directiva de versión de cliente Crear nueva o editar existente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientCVPolicyEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: e32c6712-6dc9-4de9-8d74-9fdccf3de1ba
ROBOTS: NOINDEX, NOFOLLOW
description: Puede especificar la versión de clientes que se admiten en su entorno. Cuando interactúan dos clientes que ejecutan versiones diferentes, las características disponibles para cualquiera de esos clientes pueden verse limitadas por las funciones del otro cliente.
ms.openlocfilehash: c2d6dc4f68a7c40668db9042d420f2f341e35ca0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824900"
---
# <a name="client-version-policy-create-new-or-edit-existing"></a><span data-ttu-id="f71c6-104">Directiva de versiones de cliente: Crear nuevos o editar los existentes</span><span class="sxs-lookup"><span data-stu-id="f71c6-104">Client Version Policy: Create New or Edit Existing</span></span>

<span data-ttu-id="f71c6-105">Puede especificar la versión de clientes que se admiten en su entorno.</span><span class="sxs-lookup"><span data-stu-id="f71c6-105">You can specify the version of clients that are supported in your environment.</span></span> <span data-ttu-id="f71c6-106">Cuando interactúan dos clientes que ejecutan versiones diferentes, las características disponibles para cualquiera de esos clientes pueden verse limitadas por las funciones del otro cliente.</span><span class="sxs-lookup"><span data-stu-id="f71c6-106">When two clients that are running different versions interact, the features that are available to either client can be limited by the capabilities of the other client.</span></span> <span data-ttu-id="f71c6-107">Para aprovechar al máximo las características incluidas en Skype Empresarial Server y mejorar la experiencia general del usuario, puede usar el filtro de versión de cliente para restringir las versiones de cliente que se usan en su entorno.</span><span class="sxs-lookup"><span data-stu-id="f71c6-107">To make the greatest use of features included in Skype for Business Server and to improve the overall user experience, you can use the client version filter to restrict the client versions that are used in your environment.</span></span> <span data-ttu-id="f71c6-108">Mediante el filtro de versiones de cliente también puede ayudar a reducir los costos asociados al uso de varias versiones de cliente.</span><span class="sxs-lookup"><span data-stu-id="f71c6-108">By using the client version filter, you can also help reduce costs associated with supporting multiple client versions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f71c6-p103">Los filtros se enumeran en orden de prioridad. Por ejemplo, si tiene un filtro que permite conectarse a los clientes que estén ejecutando la versión 1.5, seguido de un filtro que bloquee a los clientes que estén ejecutando una versión anterior a la 2.0, el primer filtro tiene prioridad y se permitirá conectarse a los clientes que ejecuten la versión 1.5.</span><span class="sxs-lookup"><span data-stu-id="f71c6-p103">Filters are listed in order of precedence. For example, if you have a filter that allows clients running version 1.5 to connect, followed by a filter that blocks clients running a version earlier than 2.0, the first filter takes precedence, and clients running version 1.5 are allowed to connect.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="f71c6-111">Tareas que puede realizar</span><span class="sxs-lookup"><span data-stu-id="f71c6-111">Tasks you can perform</span></span>

<span data-ttu-id="f71c6-112">Puede realizar las siguientes tareas en la página **Nueva directiva de versión de cliente** o **Editar directiva de versión de cliente**:</span><span class="sxs-lookup"><span data-stu-id="f71c6-112">You can perform the following tasks on the **New Client Version Policy** or **Edit Client Version Policy** page:</span></span>

- <span data-ttu-id="f71c6-113">Agregar o modificar el nombre o la descripción de la directiva de versión de cliente.</span><span class="sxs-lookup"><span data-stu-id="f71c6-113">Add or modify the name or description of the client version policy.</span></span>

- <span data-ttu-id="f71c6-114">Agregar o modificar reglas de versión de cliente de la directiva de versión de cliente.</span><span class="sxs-lookup"><span data-stu-id="f71c6-114">Add or modify client version rules for the client version policy.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="f71c6-115">Referencia de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="f71c6-115">UI Reference</span></span>

<span data-ttu-id="f71c6-116">Las siguientes listas describen los menús, comandos, campos y propiedades de la página.</span><span class="sxs-lookup"><span data-stu-id="f71c6-116">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="f71c6-117">**Ámbito** Identifica el ámbito (sitio, grupo o usuario) de la directiva de versión de cliente.</span><span class="sxs-lookup"><span data-stu-id="f71c6-117">**Scope** Identifies the scope (Site, Pool, or User) of the client version policy.</span></span>

- <span data-ttu-id="f71c6-118">**Nombre** Puede agregar o modificar el nombre de la directiva de versión de cliente.</span><span class="sxs-lookup"><span data-stu-id="f71c6-118">**Name** You can add or modify the name of the client version policy.</span></span>

- <span data-ttu-id="f71c6-119">**Descripción** Puede agregar una descripción para ayudar a identificar la directiva en la lista de la página Directiva de versión de cliente.</span><span class="sxs-lookup"><span data-stu-id="f71c6-119">**Description** You can add a description to help in identifying the policy in the list on the Client Version Policy page.</span></span>

- <span data-ttu-id="f71c6-120">**Nuevo** Puede agregar una nueva regla de versión de cliente a la directiva.</span><span class="sxs-lookup"><span data-stu-id="f71c6-120">**New** You can add a new client version rule to the policy.</span></span>

- <span data-ttu-id="f71c6-121">**Mostrar detalles** Esta opción abre un cuadro de diálogo en el que puede cambiar las opciones de una regla de versión de cliente.</span><span class="sxs-lookup"><span data-stu-id="f71c6-121">**Show details** This option opens a dialog box in which you can change the options for a client version rule.</span></span>

- <span data-ttu-id="f71c6-122">**Quitar** Esta opción quita la regla de versión de cliente seleccionada de la directiva.</span><span class="sxs-lookup"><span data-stu-id="f71c6-122">**Remove** This option removes the selected client version rule from the policy.</span></span>

- <span data-ttu-id="f71c6-123">**Flechas arriba y abajo** Esta opción mueve la regla de versión de cliente seleccionada hacia arriba o hacia abajo en prioridad.</span><span class="sxs-lookup"><span data-stu-id="f71c6-123">**Up and down arrows** This option moves the selected client version rule up or down in priority.</span></span> <span data-ttu-id="f71c6-124">Las reglas se procesan en el orden mostrado.</span><span class="sxs-lookup"><span data-stu-id="f71c6-124">Rules are processed in the order listed.</span></span>

<span data-ttu-id="f71c6-125">Para obtener más información sobre la interoperabilidad entre clientes y versiones de cliente, consulte [Interoperabilidad de clientes.](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx)</span><span class="sxs-lookup"><span data-stu-id="f71c6-125">For details about interoperability among clients and client versions, see [Client Interoperability](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx).</span></span> <span data-ttu-id="f71c6-126">Para obtener detalles sobre cómo trabajar con las directivas de versión de cliente, vea [Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="f71c6-126">For details about working with client version policies, see [Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) in the Operations documentation.</span></span>

