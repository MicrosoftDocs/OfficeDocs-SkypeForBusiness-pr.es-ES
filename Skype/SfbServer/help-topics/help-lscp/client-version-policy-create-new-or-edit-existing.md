---
title: Directiva de versión de cliente Crear nuevo o editar existente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientCVPolicyEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e32c6712-6dc9-4de9-8d74-9fdccf3de1ba
description: Puede especificar la versión de clientes que se admiten en su entorno. Cuando interactúan dos clientes que ejecutan versiones diferentes, las características disponibles para cualquiera de esos clientes pueden verse limitadas por las funciones del otro cliente. Para aprovechar al máximo las características incluidas en Skype Empresarial Server 2015 y mejorar la experiencia general del usuario, puede usar el filtro de versión de cliente para restringir las versiones de cliente que se usan en su entorno. Mediante el filtro de versiones de cliente también puede ayudar a reducir los costos asociados al uso de varias versiones de cliente.
ms.openlocfilehash: 614719a4d0152df4e451793e4845e7a6f72a59cc
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095614"
---
# <a name="client-version-policy-create-new-or-edit-existing"></a><span data-ttu-id="77ac9-106">Directiva de versiones de cliente: Crear nuevos o editar los existentes</span><span class="sxs-lookup"><span data-stu-id="77ac9-106">Client Version Policy: Create New or Edit Existing</span></span>

<span data-ttu-id="77ac9-107">Puede especificar la versión de clientes que se admiten en su entorno.</span><span class="sxs-lookup"><span data-stu-id="77ac9-107">You can specify the version of clients that are supported in your environment.</span></span> <span data-ttu-id="77ac9-108">Cuando interactúan dos clientes que ejecutan versiones diferentes, las características disponibles para cualquiera de esos clientes pueden verse limitadas por las funciones del otro cliente.</span><span class="sxs-lookup"><span data-stu-id="77ac9-108">When two clients that are running different versions interact, the features that are available to either client can be limited by the capabilities of the other client.</span></span> <span data-ttu-id="77ac9-109">Para aprovechar al máximo las características incluidas en Skype Empresarial Server 2015 y mejorar la experiencia general del usuario, puede usar el filtro de versión de cliente para restringir las versiones de cliente que se usan en su entorno.</span><span class="sxs-lookup"><span data-stu-id="77ac9-109">To make the greatest use of features included in Skype for Business Server 2015 and to improve the overall user experience, you can use the client version filter to restrict the client versions that are used in your environment.</span></span> <span data-ttu-id="77ac9-110">Mediante el filtro de versiones de cliente también puede ayudar a reducir los costos asociados al uso de varias versiones de cliente.</span><span class="sxs-lookup"><span data-stu-id="77ac9-110">By using the client version filter, you can also help reduce costs associated with supporting multiple client versions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="77ac9-p103">Los filtros se enumeran en orden de prioridad. Por ejemplo, si tiene un filtro que permite conectarse a los clientes que estén ejecutando la versión 1.5, seguido de un filtro que bloquee a los clientes que estén ejecutando una versión anterior a la 2.0, el primer filtro tiene prioridad y se permitirá conectarse a los clientes que ejecuten la versión 1.5.</span><span class="sxs-lookup"><span data-stu-id="77ac9-p103">Filters are listed in order of precedence. For example, if you have a filter that allows clients running version 1.5 to connect, followed by a filter that blocks clients running a version earlier than 2.0, the first filter takes precedence, and clients running version 1.5 are allowed to connect.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="77ac9-113">Tareas que puede realizar</span><span class="sxs-lookup"><span data-stu-id="77ac9-113">Tasks you can perform</span></span>

<span data-ttu-id="77ac9-114">Puede realizar las siguientes tareas en la página **Nueva directiva de versión de cliente** o **Editar directiva de versión de cliente**:</span><span class="sxs-lookup"><span data-stu-id="77ac9-114">You can perform the following tasks on the **New Client Version Policy** or **Edit Client Version Policy** page:</span></span>

- <span data-ttu-id="77ac9-115">Agregar o modificar el nombre o la descripción de la directiva de versión de cliente.</span><span class="sxs-lookup"><span data-stu-id="77ac9-115">Add or modify the name or description of the client version policy.</span></span>

- <span data-ttu-id="77ac9-116">Agregar o modificar reglas de versión de cliente de la directiva de versión de cliente.</span><span class="sxs-lookup"><span data-stu-id="77ac9-116">Add or modify client version rules for the client version policy.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="77ac9-117">Referencia de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="77ac9-117">UI Reference</span></span>

<span data-ttu-id="77ac9-118">Las siguientes listas describen los menús, comandos, campos y propiedades de la página.</span><span class="sxs-lookup"><span data-stu-id="77ac9-118">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="77ac9-119">**Ámbito** Identifica el ámbito (Sitio, Grupo de servidores o Usuario) de la directiva de versión de cliente.</span><span class="sxs-lookup"><span data-stu-id="77ac9-119">**Scope** Identifies the scope (Site, Pool, or User) of the client version policy.</span></span>

- <span data-ttu-id="77ac9-120">**Nombre** Puede agregar o modificar el nombre de la directiva de versión de cliente.</span><span class="sxs-lookup"><span data-stu-id="77ac9-120">**Name** You can add or modify the name of the client version policy.</span></span>

- <span data-ttu-id="77ac9-121">**Descripción** Puede agregar una descripción para ayudar a identificar la directiva en la lista de la página Directiva de versión de cliente.</span><span class="sxs-lookup"><span data-stu-id="77ac9-121">**Description** You can add a description to help in identifying the policy in the list on the Client Version Policy page.</span></span>

- <span data-ttu-id="77ac9-122">**Nuevo** Puede agregar una nueva regla de versión de cliente a la directiva.</span><span class="sxs-lookup"><span data-stu-id="77ac9-122">**New** You can add a new client version rule to the policy.</span></span>

- <span data-ttu-id="77ac9-123">**Mostrar detalles** Esta opción abre un cuadro de diálogo en el que puede cambiar las opciones de una regla de versión de cliente.</span><span class="sxs-lookup"><span data-stu-id="77ac9-123">**Show details** This option opens a dialog box in which you can change the options for a client version rule.</span></span>

- <span data-ttu-id="77ac9-124">**Quitar** Esta opción quita la regla de versión de cliente seleccionada de la directiva.</span><span class="sxs-lookup"><span data-stu-id="77ac9-124">**Remove** This option removes the selected client version rule from the policy.</span></span>

- <span data-ttu-id="77ac9-125">**Flechas arriba y abajo** Esta opción mueve la regla de versión de cliente seleccionada hacia arriba o hacia abajo en prioridad.</span><span class="sxs-lookup"><span data-stu-id="77ac9-125">**Up and down arrows** This option moves the selected client version rule up or down in priority.</span></span> <span data-ttu-id="77ac9-126">Las reglas se procesan en el orden mostrado.</span><span class="sxs-lookup"><span data-stu-id="77ac9-126">Rules are processed in the order listed.</span></span>

<span data-ttu-id="77ac9-127">Para obtener detalles sobre la interoperabilidad entre clientes y versiones de clientes, vea [Client Interoperability in Lync 2013 Preview](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013) en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="77ac9-127">For details about interoperability among clients and client versions, see [Client Interoperability in Lync 2013 Preview](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013) in the Planning documentation.</span></span> <span data-ttu-id="77ac9-128">Para obtener detalles sobre cómo trabajar con las directivas de versión de cliente, vea [Specify the Client Versions Supported in Your Organization](/previous-versions/office/lync-server-2013/lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013) en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="77ac9-128">For details about working with client version policies, see [Specify the Client Versions Supported in Your Organization](/previous-versions/office/lync-server-2013/lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013) in the Operations documentation.</span></span>