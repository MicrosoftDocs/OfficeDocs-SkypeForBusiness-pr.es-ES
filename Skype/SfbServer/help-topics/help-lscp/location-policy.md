---
title: Directiva de ubicación
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.NcsLocMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5530cf17-4520-40b5-ba70-c62692685048
description: Las directivas de ubicación determinan si 9-1-1 mejorado (E9-1-1) está habilitado y el modo de usarlo, así como el modo en que la información de ubicación se usa para usuarios y contactos.
ms.openlocfilehash: fa1ca0907d3316066e2ca6e1fcf8a1d09a9c315a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="location-policy"></a><span data-ttu-id="34b89-103">Directiva de ubicación</span><span class="sxs-lookup"><span data-stu-id="34b89-103">Location Policy</span></span>
 
<span data-ttu-id="34b89-104">Las directivas de ubicación determinan si 9-1-1 mejorado (E9-1-1) está habilitado y el modo de usarlo, así como el modo en que la información de ubicación se usa para usuarios y contactos.</span><span class="sxs-lookup"><span data-stu-id="34b89-104">Location policies determine whether Enhanced 9-1-1 (E9-1-1) is enabled and how it is used, as well as how location information is used for users and contacts.</span></span> 
  
<span data-ttu-id="34b89-105">Las directivas de ubicación incluyen la directiva global y, de forma opcional, una o varias directivas de usuario y de sitio:</span><span class="sxs-lookup"><span data-stu-id="34b89-105">Location policies include the global policy and, optionally, one or more site and user policies:</span></span>
  
- <span data-ttu-id="34b89-106">**Directiva global:** De forma predeterminada, se crea la directiva global.</span><span class="sxs-lookup"><span data-stu-id="34b89-106">**Global policy:** The global policy is created by default.</span></span> <span data-ttu-id="34b89-107">Puede editar la directiva global, pero no puede eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="34b89-107">You can edit the global policy, but you cannot delete it.</span></span> <span data-ttu-id="34b89-108">Si intenta quitar la directiva global, todos los valores se restablecen a los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="34b89-108">If you try to remove the global policy, all the settings are reset to the default values.</span></span>
    
- <span data-ttu-id="34b89-109">**Sitio de directivas (opcionales):** Puede crear uno o más sitios ubicación directivas, cada una de ellas se aplica a un sitio específico.</span><span class="sxs-lookup"><span data-stu-id="34b89-109">**Site policies (optional):** You can create one or more site location policies, each of which applies to a specific site.</span></span> <span data-ttu-id="34b89-110">Directivas de sitio anulan la directiva global.</span><span class="sxs-lookup"><span data-stu-id="34b89-110">Site policies override the global policy.</span></span>
    
- <span data-ttu-id="34b89-111">**Las directivas de usuario (opcionales):** Puede crear uno o varios ubicación directivas de usuario, cada uno de los cuales se aplica a un usuario o grupo específico de usuarios.</span><span class="sxs-lookup"><span data-stu-id="34b89-111">**User policies (optional):** You can create one or more user location policies, each of which applies to a specific user or group of users.</span></span> <span data-ttu-id="34b89-112">Directivas de usuario anulan la directiva global y las políticas del sitio.</span><span class="sxs-lookup"><span data-stu-id="34b89-112">User policies override the global policy and site policies.</span></span>
    
> [!NOTE]
> <span data-ttu-id="34b89-113">También puede asignar directivas de ubicación a sitios de red, que son grupos de subredes.</span><span class="sxs-lookup"><span data-stu-id="34b89-113">You can also assign location policies to network sites, which are groups of subnets.</span></span> <span data-ttu-id="34b89-114">Las directivas de ubicación asignadas a los sitios de red prevalecen sobre las demás directivas de usuario.</span><span class="sxs-lookup"><span data-stu-id="34b89-114">Location policies assigned to network sites take precedence over all other user policies.</span></span> <span data-ttu-id="34b89-115">Para obtener más información acerca de cómo asignar directivas de ubicación a los sitios de la red mediante cmdlets, vea [Agregar una directiva de ubicación en un sitio de red en Skype para Business Server 2015](../../deploy/deploy-enterprise-voice/add-a-location-policy-to-a-network-site.md).</span><span class="sxs-lookup"><span data-stu-id="34b89-115">For details about assigning location policies to network sites by using cmdlets, see [Add a location policy to a network site in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/add-a-location-policy-to-a-network-site.md).</span></span> <span data-ttu-id="34b89-116">Para obtener más información acerca de cómo utilizar Skype para Panel de Control de servidor empresarial para asignar una directiva de ubicación en un sitio de red, consulte [Configuración de sitios de red](http://technet.microsoft.com/library/358aa08a-c5bc-45fc-8017-19e6202f88c5.aspx).</span><span class="sxs-lookup"><span data-stu-id="34b89-116">For details about using Skype for Business Server Control Panel to assign a location policy to a network site, see [Configuring Network Sites](http://technet.microsoft.com/library/358aa08a-c5bc-45fc-8017-19e6202f88c5.aspx).</span></span> 
  
<span data-ttu-id="34b89-117">La página **Directiva de ubicación** muestra una lista de todas las directivas de ubicación definidas en la organización.</span><span class="sxs-lookup"><span data-stu-id="34b89-117">The **Location Policy** page displays a list of all the location policies that are defined for your organization.</span></span>
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="34b89-118">Tareas que puede realizar</span><span class="sxs-lookup"><span data-stu-id="34b89-118">Tasks you can perform</span></span>

<span data-ttu-id="34b89-119">En la página **Directiva de ubicación** puede realizar las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="34b89-119">You can perform the following tasks from the **Location Policy** page:</span></span>
  
- <span data-ttu-id="34b89-120">Crear una directiva de ubicación de sitio o de ubicación de usuario</span><span class="sxs-lookup"><span data-stu-id="34b89-120">Create a new site location policy or user location policy</span></span>
    
- <span data-ttu-id="34b89-121">Cambiar la directiva global o una directiva de sitio o de usuario existente</span><span class="sxs-lookup"><span data-stu-id="34b89-121">Change the global policy or an existing site policy or user policy</span></span>
    
- <span data-ttu-id="34b89-122">Eliminar una directiva de sitio o de usuario</span><span class="sxs-lookup"><span data-stu-id="34b89-122">Delete a site policy or user policy</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="34b89-123">Referencia de interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="34b89-123">UI Reference</span></span>

<span data-ttu-id="34b89-124">En la siguiente lista se describen los comandos de la página.</span><span class="sxs-lookup"><span data-stu-id="34b89-124">The following list describes the commands on the page.</span></span>
  
- <span data-ttu-id="34b89-125">**Nuevo** Inicia una nueva política de ubicación de sitio o ubicación usuario.</span><span class="sxs-lookup"><span data-stu-id="34b89-125">**New** Starts a new site location policy or user location policy.</span></span>
    
- <span data-ttu-id="34b89-126">**Editar** Abre la directiva de la ubicación seleccionada para modificarlo, selecciona todas las políticas de ubicación de la lista o elimina la política de sitio seleccionado o usuario.</span><span class="sxs-lookup"><span data-stu-id="34b89-126">**Edit** Opens the selected location policy to edit it, selects all location policies in the list, or deletes the selected site policy or user policy.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="34b89-127">En el caso de la directiva global, con **Eliminar** se restablece la configuración a los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="34b89-127">For the global policy, **Delete** resets the settings to the default values.</span></span>
  
- <span data-ttu-id="34b89-128">**Actualizar** Actualiza la lista de las directivas de ubicación.</span><span class="sxs-lookup"><span data-stu-id="34b89-128">**Refresh** Refreshes the list of location policies.</span></span>
    
<span data-ttu-id="34b89-129">En la siguiente lista se describen los campos de la página.</span><span class="sxs-lookup"><span data-stu-id="34b89-129">The following list describes the fields on the page.</span></span>
  
- <span data-ttu-id="34b89-130">**Nombre** Identifica la ubicación de directiva.</span><span class="sxs-lookup"><span data-stu-id="34b89-130">**Name** Identifies the location policy.</span></span>
    
- <span data-ttu-id="34b89-131">**Ámbito de aplicación** Identifica el ámbito de la política de ubicación: global, sitio o usuario.</span><span class="sxs-lookup"><span data-stu-id="34b89-131">**Scope** Identifies the scope of the location policy: global, site, or user.</span></span>
    
- <span data-ttu-id="34b89-132">**E9-1-1** Comprueba si están habilitados los usuarios asignados a esta directiva de ubicación para E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="34b89-132">**E9-1-1** Checked if users assigned this location policy are enabled for E9-1-1.</span></span>
    
- <span data-ttu-id="34b89-133">**Ubicación** Especifica si se pide a los usuarios para escribir información de ubicación cuando su cliente se registra con Skype para Business Server en una nueva ubicación, y si ven una renuncia si cerrar el símbolo del sistema sin introducir información de ubicación.</span><span class="sxs-lookup"><span data-stu-id="34b89-133">**Location** Specifies whether or not users are prompted to enter location information when their client registers with Skype for Business Server at a new location, and whether they see a disclaimer if they dismiss the prompt without entering location information.</span></span>
    
- <span data-ttu-id="34b89-134">**Uso PSTN** Especifica el uso de telefónica pública conmutada (RTC) de la red que se utiliza para determinar la ruta de voz utilizada para enrutar las llamadas de emergencia de los clientes con este perfil.</span><span class="sxs-lookup"><span data-stu-id="34b89-134">**PSTN usage** Specifies the public switched telephone network (PSTN) usage that is used to determine the voice route used to route emergency calls from clients using this profile.</span></span>
    
- <span data-ttu-id="34b89-135">**Número de E9-1-1** Especifica el número que se marca para llegar a los servicios de emergencia.</span><span class="sxs-lookup"><span data-stu-id="34b89-135">**E9-1-1 number** Specifies the number that is dialed to reach emergency services.</span></span>
    
- <span data-ttu-id="34b89-136">**Máscara de E9-1-1** Especifica un número que llama a un usuario y, a continuación, se convierte en el número de acceso telefónico de emergencia.</span><span class="sxs-lookup"><span data-stu-id="34b89-136">**E9-1-1 mask** Specifies a number that a user dials that is then translated into the emergency dial number.</span></span>
    
<span data-ttu-id="34b89-137">Para obtener más información acerca de capacidades y características de Telefonía IP empresarial servicio de emergencia, vea [Resumen de E9-1-1](http://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) en la documentación de planeamiento.</span><span class="sxs-lookup"><span data-stu-id="34b89-137">For details about Enterprise Voice emergency service features and capabilities, see [Overview of E9-1-1](http://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) in the Planning documentation.</span></span> <span data-ttu-id="34b89-138">Para obtener más información acerca de cómo trabajar con las políticas de ubicación, vea [Configurar la directiva de ubicación](http://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx) en la documentación de las operaciones.</span><span class="sxs-lookup"><span data-stu-id="34b89-138">For details about working with location policies, see [Configuring Location Policy](http://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx) in the Operations documentation.</span></span>
  

