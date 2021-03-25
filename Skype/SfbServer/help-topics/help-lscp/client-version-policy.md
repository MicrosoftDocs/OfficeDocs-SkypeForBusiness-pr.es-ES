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
ms.openlocfilehash: 0af11ac26a73452412c653c04233df7b932f2b49
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118649"
---
# <a name="client-version-policy"></a><span data-ttu-id="eefc4-106">Directiva de versiones de clientes:</span><span class="sxs-lookup"><span data-stu-id="eefc4-106">Client Version Policy</span></span>

<span data-ttu-id="eefc4-107">Puede especificar la versión de clientes que se admiten en su entorno.</span><span class="sxs-lookup"><span data-stu-id="eefc4-107">You can specify the version of clients that are supported in your environment.</span></span> <span data-ttu-id="eefc4-108">Cuando interactúan dos clientes que ejecutan versiones diferentes, las características disponibles para cualquiera de esos clientes pueden verse limitadas por las funciones del otro cliente.</span><span class="sxs-lookup"><span data-stu-id="eefc4-108">When two clients that are running different versions interact, the features that are available to either client can be limited by the capabilities of the other client.</span></span> <span data-ttu-id="eefc4-109">Para aprovechar al máximo las características incluidas en Skype Empresarial Server 2015 y mejorar la experiencia general del usuario, puede usar el filtro de versión de cliente para restringir las versiones de cliente que se usan en su entorno.</span><span class="sxs-lookup"><span data-stu-id="eefc4-109">To make the greatest use of features included in Skype for Business Server 2015 and to improve the overall user experience, you can use the client version filter to restrict the client versions that are used in your environment.</span></span> <span data-ttu-id="eefc4-110">Mediante el filtro de versiones de cliente también puede ayudar a reducir los costos asociados al uso de varias versiones de cliente.</span><span class="sxs-lookup"><span data-stu-id="eefc4-110">By using the client version filter, you can also help reduce costs associated with supporting multiple client versions.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="eefc4-111">Tareas que puede realizar</span><span class="sxs-lookup"><span data-stu-id="eefc4-111">Tasks you can perform</span></span>

<span data-ttu-id="eefc4-112">Puede realizar las siguientes tareas en la página **Directiva de versión de cliente**:</span><span class="sxs-lookup"><span data-stu-id="eefc4-112">You can perform the following tasks on the **Client Version Policy** page:</span></span>

- <span data-ttu-id="eefc4-113">Edite la directiva de versión de cliente predeterminada ( **Global**).</span><span class="sxs-lookup"><span data-stu-id="eefc4-113">Edit the default ( **Global**) client version policy.</span></span>

- <span data-ttu-id="eefc4-114">Crear directivas de versión de cliente para un grupo o sitio concreto.</span><span class="sxs-lookup"><span data-stu-id="eefc4-114">Create client version policies for a particular site or pool.</span></span>

- <span data-ttu-id="eefc4-115">Crear directivas de versión de cliente que se puedan asignar a usuarios individuales.</span><span class="sxs-lookup"><span data-stu-id="eefc4-115">Create client version policies that can be assigned to individual users.</span></span>

> [!NOTE]
> <span data-ttu-id="eefc4-116">Debido a que los usuarios anónimos no están asociados a un usuario, sitio o servicio, este tipo de usuarios solo se ven afectados por directivas de nivel global.</span><span class="sxs-lookup"><span data-stu-id="eefc4-116">Because anonymous users are not associated with a user, site, or service, anonymous users are affected by global-level policies only.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="eefc4-117">Referencia de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="eefc4-117">UI Reference</span></span>

<span data-ttu-id="eefc4-118">Las siguientes listas describen los menús, comandos, campos y propiedades de la página.</span><span class="sxs-lookup"><span data-stu-id="eefc4-118">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="eefc4-119">**Nuevo** Puede crear una o varias de las siguientes directivas de versión de cliente:</span><span class="sxs-lookup"><span data-stu-id="eefc4-119">**New** You can create one or more of each of the following client version policies:</span></span>

  - <span data-ttu-id="eefc4-120">Directiva de sitio</span><span class="sxs-lookup"><span data-stu-id="eefc4-120">Site policy</span></span>

  - <span data-ttu-id="eefc4-121">Directiva de grupo de servidores</span><span class="sxs-lookup"><span data-stu-id="eefc4-121">Pool policy</span></span>

  - <span data-ttu-id="eefc4-122">Directiva de usuario</span><span class="sxs-lookup"><span data-stu-id="eefc4-122">User policy</span></span>

- <span data-ttu-id="eefc4-123">**Editar** Puede cambiar las opciones de cualquiera de las directivas de versión de cliente.</span><span class="sxs-lookup"><span data-stu-id="eefc4-123">**Edit** You can change the options of any of the client version policies.</span></span> <span data-ttu-id="eefc4-124">Al usar esta opción, puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="eefc4-124">Using this option, you can do the following:</span></span>

  - <span data-ttu-id="eefc4-125">**Mostrar detalles** Esta opción abre un cuadro de diálogo en el que puede cambiar las opciones de una directiva de versión de cliente.</span><span class="sxs-lookup"><span data-stu-id="eefc4-125">**Show details** This option opens a dialog box in which you can change the options for a client version policy.</span></span>

  - <span data-ttu-id="eefc4-126">**Seleccionar todo** Esta opción selecciona todas las directivas de versión de cliente de la lista.</span><span class="sxs-lookup"><span data-stu-id="eefc4-126">**Select All** This option selects all client version policies in the list.</span></span>

  - <span data-ttu-id="eefc4-127">**Eliminar** Esta opción elimina todas las directivas de versión de cliente seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="eefc4-127">**Delete** This option deletes all selected client version policies.</span></span>

- <span data-ttu-id="eefc4-128">**Actualizar** Puede actualizar la lista de directivas de versión de cliente para comprobar el estado de las opciones de todas las directivas de versión de cliente.</span><span class="sxs-lookup"><span data-stu-id="eefc4-128">**Refresh** You can refresh the client version policy list to verify the status of the options of all client version policies.</span></span>

<span data-ttu-id="eefc4-129">Para obtener detalles sobre la interoperabilidad entre clientes y versiones de clientes, vea [Client Interoperability in Lync 2013 Preview](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013) en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="eefc4-129">For details about interoperability among clients and client versions, see [Client Interoperability in Lync 2013 Preview](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013) in the Planning documentation.</span></span> <span data-ttu-id="eefc4-130">Para obtener detalles sobre cómo trabajar con las directivas de versión de cliente, vea [Specify the Client Versions Supported in Your Organization](/previous-versions/office/lync-server-2013/lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013) en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="eefc4-130">For details about working with client version policies, see [Specify the Client Versions Supported in Your Organization](/previous-versions/office/lync-server-2013/lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013) in the Operations documentation.</span></span>