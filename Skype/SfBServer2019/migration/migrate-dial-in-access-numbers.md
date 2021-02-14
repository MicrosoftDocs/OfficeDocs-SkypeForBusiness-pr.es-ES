---
title: Migrar los números de acceso telefónico
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: La migración de números de acceso telefónico a Skype Empresarial Server 2019 requiere ejecutar el cmdlet Move-CsApplicationEndpoint para migrar los objetos de contacto. Durante la instalación heredada y el período de coexistencia de Skype Empresarial Server 2019, los números de acceso telefónico que creó en Skype Empresarial Server 2019 se comportan de forma similar a los números de acceso telefónico local que crea en la instalación heredada, tal como se describe en esta sección.
ms.openlocfilehash: 0df71debe8a6d5c686d8bce17b837f32a4ca2bab
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752702"
---
# <a name="migrate-dial-in-access-numbers"></a><span data-ttu-id="413f1-104">Migrar los números de acceso telefónico</span><span class="sxs-lookup"><span data-stu-id="413f1-104">Migrate dial-in access numbers</span></span>

<span data-ttu-id="413f1-105">La migración de números de acceso telefónico a Skype Empresarial Server 2019 requiere ejecutar el cmdlet **Move-CsApplicationEndpoint** para migrar los objetos de contacto.</span><span class="sxs-lookup"><span data-stu-id="413f1-105">Migrating dial-in access numbers to Skype for Business Server 2019 requires running the **Move-CsApplicationEndpoint** cmdlet to migrate the contact objects.</span></span> <span data-ttu-id="413f1-106">Durante la instalación heredada y el período de coexistencia de Skype Empresarial Server 2019, los números de acceso telefónico que creó en Skype Empresarial Server 2019 se comportan de forma similar a los números de acceso telefónico local que crea en la instalación heredada, tal como se describe en esta sección.</span><span class="sxs-lookup"><span data-stu-id="413f1-106">During the legacy install and Skype for Business Server 2019 coexistence period, dial-in access numbers that you created in Skype for Business Server 2019 behave similarly to the dial-in access numbers that you create in the legacy install, as described in this section.</span></span> 

<span data-ttu-id="413f1-107">Los números de acceso telefónico que creó en la instalación heredada pero que movió a Skype Empresarial Server 2019, o que creó en Skype Empresarial Server 2019 antes, durante o después de la migración, tienen las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="413f1-107">Dial-in access numbers that you created in the legacy install but moved to Skype for Business Server 2019, or that you created in Skype for Business Server 2019 before, during, or after migration, have the following characteristics:</span></span>

- <span data-ttu-id="413f1-108">No aparecen en las invitaciones a reuniones de Office Communications Server 2007 R2, ni en la página del número de acceso telefónico.</span><span class="sxs-lookup"><span data-stu-id="413f1-108">Do not appear on Office Communications Server 2007 R2 meeting invitations and the dial-in access number page.</span></span>

- <span data-ttu-id="413f1-109">Aparecerá en las invitaciones a reuniones de instalación heredadas y en la página de números de acceso telefónico.</span><span class="sxs-lookup"><span data-stu-id="413f1-109">Appear on the legacy install meeting invitations and the dial-in access number page.</span></span>

- <span data-ttu-id="413f1-110">Aparecen en las invitaciones a reuniones de Skype Empresarial Server 2019 y en la página de números de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="413f1-110">Appear on Skype for Business Server 2019 meeting invitations and the dial-in access number page.</span></span>

- <span data-ttu-id="413f1-111">No se pueden ver ni modificar en la herramienta administrativa de Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="413f1-111">Cannot be viewed or modified in the Office Communications Server 2007 R2 administrative tool.</span></span>

- <span data-ttu-id="413f1-112">Se puede ver y modificar en el Panel de control de instalación heredado y en el Shell de administración de instalación heredado.</span><span class="sxs-lookup"><span data-stu-id="413f1-112">Can be viewed and modified in the legacy install Control Panel and in the legacy install Management Shell.</span></span>

- <span data-ttu-id="413f1-113">Se puede ver y modificar en el Panel de control de Skype Empresarial Server 2019 y en el Shell de administración de Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="413f1-113">Can be viewed and modified in the Skype for Business Server 2019 Control Panel and in Skype for Business Server 2019 Management Shell.</span></span>

- <span data-ttu-id="413f1-114">Se pueden volver a secuenciar en la región con el cmdlet Set-CsDialinConferencingAccessNumber con el parámetro Priority.</span><span class="sxs-lookup"><span data-stu-id="413f1-114">Can be re-sequenced within the region by using the Set-CsDialinConferencingAccessNumber cmdlet with the Priority parameter.</span></span>

<span data-ttu-id="413f1-115">Debe terminar de migrar los números de acceso telefónico que apuntan al grupo de instalación heredado antes de retirar el grupo de servidores de instalación heredado.</span><span class="sxs-lookup"><span data-stu-id="413f1-115">You must finish migrating dial-in access numbers that point to the legacy install pool before you decommission the legacy install pool.</span></span> <span data-ttu-id="413f1-116">Si no completa la migración de los números de acceso telefónico como se describe en el siguiente procedimiento, no se podrán realizar las llamadas entrantes a los números de acceso.</span><span class="sxs-lookup"><span data-stu-id="413f1-116">If you do not complete dial-in access number migration as described in the following procedure, incoming calls to the access numbers will fail.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="413f1-117">Debe realizar este procedimiento antes de retirar el grupo de instalación heredado.</span><span class="sxs-lookup"><span data-stu-id="413f1-117">You must perform this procedure prior to decommissioning the legacy install pool.</span></span> 

> [!NOTE]
> <span data-ttu-id="413f1-118">Se recomienda que mueva los números de acceso telefónico cuando el uso de la red sea bajo, en caso de que se produzca una breve interrupción del servicio.</span><span class="sxs-lookup"><span data-stu-id="413f1-118">We recommend that you move dial-in access numbers when network usage is low, in case there is a short period of service outage.</span></span> 

## <a name="to-identify-and-move-dial-in-access-numbers"></a><span data-ttu-id="413f1-119">Para identificar y mover números de acceso telefónico</span><span class="sxs-lookup"><span data-stu-id="413f1-119">To identify and move dial-in access numbers</span></span>

1. <span data-ttu-id="413f1-120">Inicie el Shell de administración de Skype Empresarial Server: Haga clic en **Inicio,** en Todos los **programas,** en **Microsoft Skype Empresarial Server 2019** y, a continuación, en Shell de administración de Skype Empresarial **Server.**</span><span class="sxs-lookup"><span data-stu-id="413f1-120">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="413f1-121">Para mover cada número de acceso telefónico a un grupo hospedado en Skype Empresarial Server 2019, desde la línea de comandos ejecute:</span><span class="sxs-lookup"><span data-stu-id="413f1-121">To move each dial-in access number to a pool hosted on Skype for Business Server 2019, from the command line run:</span></span> 

   ```PowerShell
   Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>
   ```

3. <span data-ttu-id="413f1-122">Abra el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="413f1-122">Open Skype for Business Server Control Panel.</span></span>

4. <span data-ttu-id="413f1-123">En la barra de navegación izquierda, haga clic en **Conferencia**.</span><span class="sxs-lookup"><span data-stu-id="413f1-123">In the left navigation bar, click **Conferencing**.</span></span>

5. <span data-ttu-id="413f1-124">Haga clic en la pestaña **Número de acceso telefónico**.</span><span class="sxs-lookup"><span data-stu-id="413f1-124">Click the **Dial-in Access Number** tab.</span></span> 

6. <span data-ttu-id="413f1-125">Compruebe que no quedan números de acceso telefónico para el grupo de instalación heredado desde el que va a migrar.</span><span class="sxs-lookup"><span data-stu-id="413f1-125">Verify that no dial-in access numbers remain for the legacy install pool from which you are migrating.</span></span>

    > [!NOTE]
    > <span data-ttu-id="413f1-126">Cuando todos los números de acceso telefónico local apunten al grupo de Skype Empresarial Server 2019, puede retirar el grupo de servidores de instalación heredado.</span><span class="sxs-lookup"><span data-stu-id="413f1-126">When all dial-in access numbers point to the Skype for Business Server 2019 pool, you can then decommission the legacy install pool.</span></span> 

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-control-panel"></a><span data-ttu-id="413f1-127">Comprobar la migración de números de acceso telefónico local mediante el Panel de control de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="413f1-127">Verify the dial-in access number migration using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="413f1-128">Desde una cuenta de usuario asignada al rol **CsUserAdministrator** o al rol **CsAdministrator**, inicie sesión en cualquier PC de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="413f1-128">From a user account that is assigned to the **CsUserAdministrator** role or the **CsAdministrator** role, log on to any computer in your internal deployment.</span></span> 

2. <span data-ttu-id="413f1-129">Abra el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="413f1-129">Open Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="413f1-130">En la barra de navegación izquierda, haga clic en **Conferencia**.</span><span class="sxs-lookup"><span data-stu-id="413f1-130">In the left navigation bar, click **Conferencing**.</span></span>

4. <span data-ttu-id="413f1-131">Haga clic en la pestaña **Número de acceso telefónico**.</span><span class="sxs-lookup"><span data-stu-id="413f1-131">Click the **Dial-in Access Number** tab.</span></span> 

5. <span data-ttu-id="413f1-132">Compruebe que todos los números de acceso telefónico local se migran al grupo hospedado en Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="413f1-132">Verify that all the dial-in access numbers are migrated to the pool hosted on Skype for Business Server 2019.</span></span>

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-management-shell"></a><span data-ttu-id="413f1-133">Comprobar la migración de números de acceso telefónico local mediante el Shell de administración de Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="413f1-133">Verify the dial-in access number migration using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="413f1-134">Abra el Shell de administración de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="413f1-134">Open Skype for Business Server Management Shell.</span></span>

2. <span data-ttu-id="413f1-135">Para devolver todos los números de acceso de conferencias de acceso telefónico migrados, en la línea de comandos ejecute:</span><span class="sxs-lookup"><span data-stu-id="413f1-135">To return all the dial-in conferencing access numbers migrated, from the command line run:</span></span>

   ```PowerShell
   Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}
   ```

3. <span data-ttu-id="413f1-136">Compruebe que todos los números de acceso telefónico local se migran al grupo hospedado en Skype Empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="413f1-136">Verify that all the dial-in access numbers are migrated to the pool hosted on Skype for Business Server 2019.</span></span>


