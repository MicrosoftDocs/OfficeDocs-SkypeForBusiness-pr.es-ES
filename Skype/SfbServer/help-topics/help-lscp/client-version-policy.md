---
title: 'Directiva de versión de clientes:'
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
- ms.lync.lscp.ClientCVPolicyMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4f84bc0f-e1df-4acb-b8ef-57f165b0153b
description: Puede especificar la versión de clientes que se admiten en su entorno. Cuando interactúan dos clientes que ejecutan versiones diferentes, las características disponibles para cualquiera de esos clientes pueden verse limitadas por las funciones del otro cliente. Para aprovechar al máximo las características incluidas en Skype Empresarial Server 2015 y mejorar la experiencia general del usuario, puede usar el filtro de versión de cliente para restringir las versiones de cliente que se usan en su entorno. Mediante el filtro de versiones de cliente también puede ayudar a reducir los costos asociados al uso de varias versiones de cliente.
ms.openlocfilehash: 7147df6d6f2460c1b341cced6a9ecc207943da8d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833400"
---
# <a name="client-version-policy"></a><span data-ttu-id="e681a-106">Directiva de versiones de clientes:</span><span class="sxs-lookup"><span data-stu-id="e681a-106">Client Version Policy</span></span>

<span data-ttu-id="e681a-107">Puede especificar la versión de clientes que se admiten en su entorno.</span><span class="sxs-lookup"><span data-stu-id="e681a-107">You can specify the version of clients that are supported in your environment.</span></span> <span data-ttu-id="e681a-108">Cuando interactúan dos clientes que ejecutan versiones diferentes, las características disponibles para cualquiera de esos clientes pueden verse limitadas por las funciones del otro cliente.</span><span class="sxs-lookup"><span data-stu-id="e681a-108">When two clients that are running different versions interact, the features that are available to either client can be limited by the capabilities of the other client.</span></span> <span data-ttu-id="e681a-109">Para aprovechar al máximo las características incluidas en Skype Empresarial Server 2015 y mejorar la experiencia general del usuario, puede usar el filtro de versión de cliente para restringir las versiones de cliente que se usan en su entorno.</span><span class="sxs-lookup"><span data-stu-id="e681a-109">To make the greatest use of features included in Skype for Business Server 2015 and to improve the overall user experience, you can use the client version filter to restrict the client versions that are used in your environment.</span></span> <span data-ttu-id="e681a-110">Mediante el filtro de versiones de cliente también puede ayudar a reducir los costos asociados al uso de varias versiones de cliente.</span><span class="sxs-lookup"><span data-stu-id="e681a-110">By using the client version filter, you can also help reduce costs associated with supporting multiple client versions.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="e681a-111">Tareas que puede realizar</span><span class="sxs-lookup"><span data-stu-id="e681a-111">Tasks you can perform</span></span>

<span data-ttu-id="e681a-112">Puede realizar las siguientes tareas en la página **Directiva de versión de cliente**:</span><span class="sxs-lookup"><span data-stu-id="e681a-112">You can perform the following tasks on the **Client Version Policy** page:</span></span>

- <span data-ttu-id="e681a-113">Edite la directiva de versión de cliente predeterminada **(global).**</span><span class="sxs-lookup"><span data-stu-id="e681a-113">Edit the default ( **Global**) client version policy.</span></span>

- <span data-ttu-id="e681a-114">Crear directivas de versión de cliente para un grupo o sitio concreto.</span><span class="sxs-lookup"><span data-stu-id="e681a-114">Create client version policies for a particular site or pool.</span></span>

- <span data-ttu-id="e681a-115">Crear directivas de versión de cliente que se puedan asignar a usuarios individuales.</span><span class="sxs-lookup"><span data-stu-id="e681a-115">Create client version policies that can be assigned to individual users.</span></span>

> [!NOTE]
> <span data-ttu-id="e681a-116">Debido a que los usuarios anónimos no están asociados a un usuario, sitio o servicio, este tipo de usuarios solo se ven afectados por directivas de nivel global.</span><span class="sxs-lookup"><span data-stu-id="e681a-116">Because anonymous users are not associated with a user, site, or service, anonymous users are affected by global-level policies only.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="e681a-117">Referencia de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="e681a-117">UI Reference</span></span>

<span data-ttu-id="e681a-118">Las siguientes listas describen los menús, comandos, campos y propiedades de la página.</span><span class="sxs-lookup"><span data-stu-id="e681a-118">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="e681a-119">**Nuevo** Puede crear una o varias de las siguientes directivas de versión de cliente:</span><span class="sxs-lookup"><span data-stu-id="e681a-119">**New** You can create one or more of each of the following client version policies:</span></span>

  - <span data-ttu-id="e681a-120">Directiva de sitio</span><span class="sxs-lookup"><span data-stu-id="e681a-120">Site policy</span></span>

  - <span data-ttu-id="e681a-121">Directiva de grupo de servidores</span><span class="sxs-lookup"><span data-stu-id="e681a-121">Pool policy</span></span>

  - <span data-ttu-id="e681a-122">Directiva de usuario</span><span class="sxs-lookup"><span data-stu-id="e681a-122">User policy</span></span>

- <span data-ttu-id="e681a-123">**Editar** Puede cambiar las opciones de cualquiera de las directivas de versión de cliente.</span><span class="sxs-lookup"><span data-stu-id="e681a-123">**Edit** You can change the options of any of the client version policies.</span></span> <span data-ttu-id="e681a-124">Al usar esta opción, puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e681a-124">Using this option, you can do the following:</span></span>

  - <span data-ttu-id="e681a-125">**Mostrar detalles** Esta opción abre un cuadro de diálogo en el que puede cambiar las opciones de una directiva de versión de cliente.</span><span class="sxs-lookup"><span data-stu-id="e681a-125">**Show details** This option opens a dialog box in which you can change the options for a client version policy.</span></span>

  - <span data-ttu-id="e681a-126">**Seleccionar todo** Esta opción selecciona todas las directivas de versión de cliente de la lista.</span><span class="sxs-lookup"><span data-stu-id="e681a-126">**Select All** This option selects all client version policies in the list.</span></span>

  - <span data-ttu-id="e681a-127">**Eliminar** Esta opción elimina todas las directivas de versión de cliente seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="e681a-127">**Delete** This option deletes all selected client version policies.</span></span>

- <span data-ttu-id="e681a-128">**Actualizar** Puede actualizar la lista de directivas de versión de cliente para comprobar el estado de las opciones de todas las directivas de versión de cliente.</span><span class="sxs-lookup"><span data-stu-id="e681a-128">**Refresh** You can refresh the client version policy list to verify the status of the options of all client version policies.</span></span>

<span data-ttu-id="e681a-129">Para obtener detalles sobre la interoperabilidad entre clientes y versiones de clientes, vea [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="e681a-129">For details about interoperability among clients and client versions, see [Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation.</span></span> <span data-ttu-id="e681a-130">Para obtener detalles sobre cómo trabajar con las directivas de versión de cliente, vea [Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="e681a-130">For details about working with client version policies, see [Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) in the Operations documentation.</span></span>

