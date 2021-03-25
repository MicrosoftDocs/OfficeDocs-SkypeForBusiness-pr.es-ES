---
title: 'Directiva de versión de clientes:'
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientCVPolicyMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 4f84bc0f-e1df-4acb-b8ef-57f165b0153b
ROBOTS: NOINDEX, NOFOLLOW
description: Puede especificar la versión de clientes que se admiten en su entorno. Cuando interactúan dos clientes que ejecutan versiones diferentes, las características disponibles para cualquiera de esos clientes pueden verse limitadas por las funciones del otro cliente.
ms.openlocfilehash: fd3abdae41b912e63391121c740912cde80e18c2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120299"
---
# <a name="client-version-policy"></a><span data-ttu-id="4b32b-104">Directiva de versiones de clientes:</span><span class="sxs-lookup"><span data-stu-id="4b32b-104">Client Version Policy</span></span>

<span data-ttu-id="4b32b-105">Puede especificar la versión de clientes que se admiten en su entorno.</span><span class="sxs-lookup"><span data-stu-id="4b32b-105">You can specify the version of clients that are supported in your environment.</span></span> <span data-ttu-id="4b32b-106">Cuando interactúan dos clientes que ejecutan versiones diferentes, las características disponibles para cualquiera de esos clientes pueden verse limitadas por las funciones del otro cliente.</span><span class="sxs-lookup"><span data-stu-id="4b32b-106">When two clients that are running different versions interact, the features that are available to either client can be limited by the capabilities of the other client.</span></span> <span data-ttu-id="4b32b-107">Para aprovechar al máximo las características incluidas en Skype Empresarial Server y mejorar la experiencia general del usuario, puede usar el filtro de versión de cliente para restringir las versiones de cliente que se usan en su entorno.</span><span class="sxs-lookup"><span data-stu-id="4b32b-107">To make the greatest use of features included in Skype for Business Server and to improve the overall user experience, you can use the client version filter to restrict the client versions that are used in your environment.</span></span> <span data-ttu-id="4b32b-108">Mediante el filtro de versiones de cliente también puede ayudar a reducir los costos asociados al uso de varias versiones de cliente.</span><span class="sxs-lookup"><span data-stu-id="4b32b-108">By using the client version filter, you can also help reduce costs associated with supporting multiple client versions.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="4b32b-109">Tareas que puede realizar</span><span class="sxs-lookup"><span data-stu-id="4b32b-109">Tasks you can perform</span></span>

<span data-ttu-id="4b32b-110">Puede realizar las siguientes tareas en la página **Directiva de versión de cliente**:</span><span class="sxs-lookup"><span data-stu-id="4b32b-110">You can perform the following tasks on the **Client Version Policy** page:</span></span>

- <span data-ttu-id="4b32b-111">Edite la directiva de versión de cliente predeterminada ( **Global**).</span><span class="sxs-lookup"><span data-stu-id="4b32b-111">Edit the default ( **Global**) client version policy.</span></span>

- <span data-ttu-id="4b32b-112">Crear directivas de versión de cliente para un grupo o sitio concreto.</span><span class="sxs-lookup"><span data-stu-id="4b32b-112">Create client version policies for a particular site or pool.</span></span>

- <span data-ttu-id="4b32b-113">Crear directivas de versión de cliente que se puedan asignar a usuarios individuales.</span><span class="sxs-lookup"><span data-stu-id="4b32b-113">Create client version policies that can be assigned to individual users.</span></span>

> [!NOTE]
> <span data-ttu-id="4b32b-114">Debido a que los usuarios anónimos no están asociados a un usuario, sitio o servicio, este tipo de usuarios solo se ven afectados por directivas de nivel global.</span><span class="sxs-lookup"><span data-stu-id="4b32b-114">Because anonymous users are not associated with a user, site, or service, anonymous users are affected by global-level policies only.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="4b32b-115">Referencia de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="4b32b-115">UI Reference</span></span>

<span data-ttu-id="4b32b-116">Las siguientes listas describen los menús, comandos, campos y propiedades de la página.</span><span class="sxs-lookup"><span data-stu-id="4b32b-116">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="4b32b-117">**Nuevo** Puede crear una o varias de las siguientes directivas de versión de cliente:</span><span class="sxs-lookup"><span data-stu-id="4b32b-117">**New** You can create one or more of each of the following client version policies:</span></span>

  - <span data-ttu-id="4b32b-118">Directiva de sitio</span><span class="sxs-lookup"><span data-stu-id="4b32b-118">Site policy</span></span>

  - <span data-ttu-id="4b32b-119">Directiva de grupo de servidores</span><span class="sxs-lookup"><span data-stu-id="4b32b-119">Pool policy</span></span>

  - <span data-ttu-id="4b32b-120">Directiva de usuario</span><span class="sxs-lookup"><span data-stu-id="4b32b-120">User policy</span></span>

- <span data-ttu-id="4b32b-121">**Editar** Puede cambiar las opciones de cualquiera de las directivas de versión de cliente.</span><span class="sxs-lookup"><span data-stu-id="4b32b-121">**Edit** You can change the options of any of the client version policies.</span></span> <span data-ttu-id="4b32b-122">Al usar esta opción, puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4b32b-122">Using this option, you can do the following:</span></span>

  - <span data-ttu-id="4b32b-123">**Mostrar detalles** Esta opción abre un cuadro de diálogo en el que puede cambiar las opciones de una directiva de versión de cliente.</span><span class="sxs-lookup"><span data-stu-id="4b32b-123">**Show details** This option opens a dialog box in which you can change the options for a client version policy.</span></span>

  - <span data-ttu-id="4b32b-124">**Seleccionar todo** Esta opción selecciona todas las directivas de versión de cliente de la lista.</span><span class="sxs-lookup"><span data-stu-id="4b32b-124">**Select All** This option selects all client version policies in the list.</span></span>

  - <span data-ttu-id="4b32b-125">**Eliminar** Esta opción elimina todas las directivas de versión de cliente seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="4b32b-125">**Delete** This option deletes all selected client version policies.</span></span>

- <span data-ttu-id="4b32b-126">**Actualizar** Puede actualizar la lista de directivas de versión de cliente para comprobar el estado de las opciones de todas las directivas de versión de cliente.</span><span class="sxs-lookup"><span data-stu-id="4b32b-126">**Refresh** You can refresh the client version policy list to verify the status of the options of all client version policies.</span></span>

<span data-ttu-id="4b32b-127">Para obtener más información sobre la interoperabilidad entre clientes y versiones de cliente, consulte [Client Interoperability](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013) en la documentación sobre planeación.</span><span class="sxs-lookup"><span data-stu-id="4b32b-127">For details about interoperability among clients and client versions, see [Client Interoperability](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013) in the Planning documentation.</span></span> <span data-ttu-id="4b32b-128">Para obtener detalles sobre cómo trabajar con las directivas de versión de cliente, vea [Specify the Client Versions Supported in Your Organization](/previous-versions/office/lync-server-2013/lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013) en la documentación de operaciones.</span><span class="sxs-lookup"><span data-stu-id="4b32b-128">For details about working with client version policies, see [Specify the Client Versions Supported in Your Organization](/previous-versions/office/lync-server-2013/lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013) in the Operations documentation.</span></span>