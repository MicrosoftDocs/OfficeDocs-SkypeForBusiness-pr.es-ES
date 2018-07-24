---
title: Directiva de versión de clientes
ms.author: SerdarS
author: SerdarSoysal
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientCVPolicyMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4f84bc0f-e1df-4acb-b8ef-57f165b0153b
ROBOTS: NOINDEX, NOFOLLOW
description: Puede especificar la versión de los clientes que se admiten en su entorno. Cuando dos clientes que ejecutan versiones diferentes interactúan entre sí, las características disponibles para cualquiera de esos clientes pueden verse limitadas por las funciones del otro cliente.
ms.openlocfilehash: 2743c62f6fbd692723c4ed9ea464e665a65d0abc
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "21009697"
---
# <a name="client-version-policy"></a><span data-ttu-id="e6eed-104">Directiva de versión de clientes</span><span class="sxs-lookup"><span data-stu-id="e6eed-104">Client Version Policy</span></span>
 
<span data-ttu-id="e6eed-105">Puede especificar la versión de los clientes que se admiten en su entorno.</span><span class="sxs-lookup"><span data-stu-id="e6eed-105">You can specify the version of clients that are supported in your environment.</span></span> <span data-ttu-id="e6eed-106">Cuando dos clientes que ejecutan versiones diferentes interactúan entre sí, las características disponibles para cualquiera de esos clientes pueden verse limitadas por las funciones del otro cliente.</span><span class="sxs-lookup"><span data-stu-id="e6eed-106">When two clients that are running different versions interact, the features that are available to either client can be limited by the capabilities of the other client.</span></span> <span data-ttu-id="e6eed-107">Para que el mayor uso de las características incluidas en Skype para Business Server y para mejorar la experiencia global del usuario, puede usar el filtro de versiones de cliente para restringir las versiones de cliente que se usan en su entorno.</span><span class="sxs-lookup"><span data-stu-id="e6eed-107">To make the greatest use of features included in Skype for Business Server and to improve the overall user experience, you can use the client version filter to restrict the client versions that are used in your environment.</span></span> <span data-ttu-id="e6eed-108">Mediante el filtro de versiones de cliente también puede ayudar a reducir los costes asociados al uso de varias versiones de cliente.</span><span class="sxs-lookup"><span data-stu-id="e6eed-108">By using the client version filter, you can also help reduce costs associated with supporting multiple client versions.</span></span>
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="e6eed-109">Tareas que puede realizar</span><span class="sxs-lookup"><span data-stu-id="e6eed-109">Tasks you can perform</span></span>

<span data-ttu-id="e6eed-110">En la página **Directiva de versión de cliente** puede realizar las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="e6eed-110">You can perform the following tasks on the **Client Version Policy** page:</span></span>
  
- <span data-ttu-id="e6eed-111">Editar la directiva de versión de cliente predeterminada ( **Global**).</span><span class="sxs-lookup"><span data-stu-id="e6eed-111">Edit the default ( **Global**) client version policy.</span></span>
    
- <span data-ttu-id="e6eed-112">Crear directivas de versión de cliente para un grupo o sitio concreto.</span><span class="sxs-lookup"><span data-stu-id="e6eed-112">Create client version policies for a particular site or pool.</span></span>
    
- <span data-ttu-id="e6eed-113">Crear directivas de versión de cliente que se puedan asignar a usuarios individuales.</span><span class="sxs-lookup"><span data-stu-id="e6eed-113">Create client version policies that can be assigned to individual users.</span></span>
    
> [!NOTE]
> <span data-ttu-id="e6eed-114">Debido a que los usuarios anónimos no están asociados a un usuario, sitio o servicio, este tipo de usuarios solo se ven afectados por directivas de nivel global.</span><span class="sxs-lookup"><span data-stu-id="e6eed-114">Because anonymous users are not associated with a user, site, or service, anonymous users are affected by global-level policies only.</span></span> 
  
## <a name="ui-reference"></a><span data-ttu-id="e6eed-115">Referencia de interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="e6eed-115">UI Reference</span></span>

<span data-ttu-id="e6eed-116">En las siguientes listas se describen los menús, comandos, campos y propiedades de la página.</span><span class="sxs-lookup"><span data-stu-id="e6eed-116">The following lists describe the menus, commands, fields, and properties on the page.</span></span>
  
- <span data-ttu-id="e6eed-117">**Nuevo** Puede crear uno o varios de cada una de las siguientes directivas de versión de cliente:</span><span class="sxs-lookup"><span data-stu-id="e6eed-117">**New** You can create one or more of each of the following client version policies:</span></span>
    
  - <span data-ttu-id="e6eed-118">Directiva de sitio</span><span class="sxs-lookup"><span data-stu-id="e6eed-118">Site policy</span></span>
    
  - <span data-ttu-id="e6eed-119">Directiva de grupo de servidores</span><span class="sxs-lookup"><span data-stu-id="e6eed-119">Pool policy</span></span>
    
  - <span data-ttu-id="e6eed-120">Directiva de usuario</span><span class="sxs-lookup"><span data-stu-id="e6eed-120">User policy</span></span>
    
- <span data-ttu-id="e6eed-121">**Editar** Puede cambiar las opciones de cualquiera de las directivas de versión de cliente.</span><span class="sxs-lookup"><span data-stu-id="e6eed-121">**Edit** You can change the options of any of the client version policies.</span></span> <span data-ttu-id="e6eed-122">Al usar esta opción, puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e6eed-122">Using this option, you can do the following:</span></span>
    
  - <span data-ttu-id="e6eed-123">**Mostrar detalles** Esta opción abre un cuadro de diálogo en el que puede cambiar las opciones para una directiva de versión de cliente.</span><span class="sxs-lookup"><span data-stu-id="e6eed-123">**Show details** This option opens a dialog box in which you can change the options for a client version policy.</span></span>
    
  - <span data-ttu-id="e6eed-124">**Seleccionar todo** Esta opción selecciona todas las directivas de versión de cliente de la lista.</span><span class="sxs-lookup"><span data-stu-id="e6eed-124">**Select All** This option selects all client version policies in the list.</span></span>
    
  - <span data-ttu-id="e6eed-125">**Eliminar** Esta opción elimina todas las directivas de versión de cliente seleccionada.</span><span class="sxs-lookup"><span data-stu-id="e6eed-125">**Delete** This option deletes all selected client version policies.</span></span>
    
- <span data-ttu-id="e6eed-126">**Actualizar** Puede actualizar la lista de directivas de versión de cliente para comprobar el estado de las opciones de todas las directivas de versión de cliente.</span><span class="sxs-lookup"><span data-stu-id="e6eed-126">**Refresh** You can refresh the client version policy list to verify the status of the options of all client version policies.</span></span>
    
<span data-ttu-id="e6eed-127">Para obtener información detallada acerca de la interoperabilidad entre clientes y versiones de cliente, consulte [Interoperabilidad del cliente](http://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="e6eed-127">For details about interoperability among clients and client versions, see [Client Interoperability](http://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx) in the Planning documentation.</span></span> <span data-ttu-id="e6eed-128">Para obtener información detallada sobre cómo trabajar con las directivas de versión de cliente, vea [Specify the Client Versions Supported in Your Organization](http://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) en la documentación sobre operaciones.</span><span class="sxs-lookup"><span data-stu-id="e6eed-128">For details about working with client version policies, see [Specify the Client Versions Supported in Your Organization](http://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx) in the Operations documentation.</span></span>

