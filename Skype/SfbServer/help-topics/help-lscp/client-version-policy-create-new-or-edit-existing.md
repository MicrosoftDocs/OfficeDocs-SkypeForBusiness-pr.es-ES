---
title: Directiva de versión del cliente crear o editar existente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.ClientCVPolicyEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e32c6712-6dc9-4de9-8d74-9fdccf3de1ba
description: Puede especificar la versión de los clientes que se admiten en su entorno. Cuando dos clientes que ejecutan versiones diferentes interactúan entre sí, las características disponibles para cualquiera de esos clientes pueden verse limitadas por las funciones del otro cliente. Para aprovechar al máximo las características incluidas en Skype empresarial Server 2015 y para mejorar la experiencia general del usuario, puede usar el filtro de versión del cliente para restringir las versiones de cliente que se usan en su entorno. Mediante el filtro de versiones de cliente también puede ayudar a reducir los costes asociados al uso de varias versiones de cliente.
ms.openlocfilehash: 1938c2f04f454ff084ad71fa4e16c2879508086d
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "41686973"
---
# <a name="client-version-policy-create-new-or-edit-existing"></a><span data-ttu-id="812ae-106">Directiva de versión de clientes: Crear nueva o editar existente</span><span class="sxs-lookup"><span data-stu-id="812ae-106">Client Version Policy: Create New or Edit Existing</span></span>

<span data-ttu-id="812ae-107">Puede especificar la versión de los clientes que se admiten en su entorno.</span><span class="sxs-lookup"><span data-stu-id="812ae-107">You can specify the version of clients that are supported in your environment.</span></span> <span data-ttu-id="812ae-108">Cuando dos clientes que ejecutan versiones diferentes interactúan entre sí, las características disponibles para cualquiera de esos clientes pueden verse limitadas por las funciones del otro cliente.</span><span class="sxs-lookup"><span data-stu-id="812ae-108">When two clients that are running different versions interact, the features that are available to either client can be limited by the capabilities of the other client.</span></span> <span data-ttu-id="812ae-109">Para aprovechar al máximo las características incluidas en Skype empresarial Server 2015 y para mejorar la experiencia general del usuario, puede usar el filtro de versión del cliente para restringir las versiones de cliente que se usan en su entorno.</span><span class="sxs-lookup"><span data-stu-id="812ae-109">To make the greatest use of features included in Skype for Business Server 2015 and to improve the overall user experience, you can use the client version filter to restrict the client versions that are used in your environment.</span></span> <span data-ttu-id="812ae-110">Mediante el filtro de versiones de cliente también puede ayudar a reducir los costes asociados al uso de varias versiones de cliente.</span><span class="sxs-lookup"><span data-stu-id="812ae-110">By using the client version filter, you can also help reduce costs associated with supporting multiple client versions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="812ae-p103">Los filtros se enumeran en orden de prioridad. Por ejemplo, si tiene un filtro que permite conectarse a los clientes que estén ejecutando la versión 1.5 o posterior, seguido de un filtro que bloquea los clientes que estén ejecutando una versión anterior a la 2.0, el primer filtro tiene prioridad y permitirá conectarse a los clientes que ejecuten la versión 1.5.</span><span class="sxs-lookup"><span data-stu-id="812ae-p103">Filters are listed in order of precedence. For example, if you have a filter that allows clients running version 1.5 to connect, followed by a filter that blocks clients running a version earlier than 2.0, the first filter takes precedence, and clients running version 1.5 are allowed to connect.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="812ae-113">Tareas que puede realizar</span><span class="sxs-lookup"><span data-stu-id="812ae-113">Tasks you can perform</span></span>

<span data-ttu-id="812ae-114">En las páginas **Nueva directiva de versión de cliente** o **Editar directiva de versión de cliente** puede realizar las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="812ae-114">You can perform the following tasks on the **New Client Version Policy** or **Edit Client Version Policy** page:</span></span>

- <span data-ttu-id="812ae-115">Agregar o modificar el nombre o la descripción de la directiva de versión de cliente.</span><span class="sxs-lookup"><span data-stu-id="812ae-115">Add or modify the name or description of the client version policy.</span></span>

- <span data-ttu-id="812ae-116">Agregar o modificar reglas de versión de cliente de la directiva de versión de cliente.</span><span class="sxs-lookup"><span data-stu-id="812ae-116">Add or modify client version rules for the client version policy.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="812ae-117">Referencia de interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="812ae-117">UI Reference</span></span>

<span data-ttu-id="812ae-118">En las siguientes listas se describen los menús, comandos, campos y propiedades de la página.</span><span class="sxs-lookup"><span data-stu-id="812ae-118">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="812ae-119">**Ámbito** Identifica el ámbito (sitio, grupo o usuario) de la Directiva de versión del cliente.</span><span class="sxs-lookup"><span data-stu-id="812ae-119">**Scope** Identifies the scope (Site, Pool, or User) of the client version policy.</span></span>

- <span data-ttu-id="812ae-120">**Nombre** Puede Agregar o modificar el nombre de la Directiva de versión de cliente.</span><span class="sxs-lookup"><span data-stu-id="812ae-120">**Name** You can add or modify the name of the client version policy.</span></span>

- <span data-ttu-id="812ae-121">**Descripción** Puede Agregar una descripción para ayudarle a identificar la Directiva en la lista de la página de directiva de versión del cliente.</span><span class="sxs-lookup"><span data-stu-id="812ae-121">**Description** You can add a description to help in identifying the policy in the list on the Client Version Policy page.</span></span>

- <span data-ttu-id="812ae-122">**Nuevo** Puede Agregar una nueva regla de versión de cliente a la Directiva.</span><span class="sxs-lookup"><span data-stu-id="812ae-122">**New** You can add a new client version rule to the policy.</span></span>

- <span data-ttu-id="812ae-123">**Mostrar detalles** Esta opción abre un cuadro de diálogo en el que puede cambiar las opciones para una regla de versión de cliente.</span><span class="sxs-lookup"><span data-stu-id="812ae-123">**Show details** This option opens a dialog box in which you can change the options for a client version rule.</span></span>

- <span data-ttu-id="812ae-124">**Quitar** Esta opción quita la regla de versión de cliente seleccionada de la Directiva.</span><span class="sxs-lookup"><span data-stu-id="812ae-124">**Remove** This option removes the selected client version rule from the policy.</span></span>

- <span data-ttu-id="812ae-125">**Flechas arriba y abajo** Esta opción mueve la regla de versión de cliente seleccionada hacia arriba o hacia abajo en prioridad.</span><span class="sxs-lookup"><span data-stu-id="812ae-125">**Up and down arrows** This option moves the selected client version rule up or down in priority.</span></span> <span data-ttu-id="812ae-126">Las reglas se procesan en el orden mostrado.</span><span class="sxs-lookup"><span data-stu-id="812ae-126">Rules are processed in the order listed.</span></span>

<span data-ttu-id="812ae-p105">Para más detalles sobre la interoperabilidad entre clientes y versiones de clientes, mire [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) en la documentación de planeación. Para más detalles sobre cómo trabajar con las directivas de versión de cliente, mire [Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="812ae-p105">For details about interoperability among clients and client versions, see [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation. For details about working with client version policies, see [Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) in the Operations documentation.</span></span>

