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
description: La migración de números de acceso telefónico local a Skype empresarial Server 2019 requiere la ejecución del cmdlet Move-CsApplicationEndpoint para migrar los objetos de contacto. Durante la instalación heredada y el período de coexistencia de Skype empresarial Server 2019, los números de acceso telefónico que ha creado en Skype empresarial Server 2019 se comportan de forma similar a los números de acceso telefónico que crea en la instalación heredada, tal como se describe en esta sección.
ms.openlocfilehash: 0df71debe8a6d5c686d8bce17b837f32a4ca2bab
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752702"
---
# <a name="migrate-dial-in-access-numbers"></a><span data-ttu-id="b2fbe-104">Migrar los números de acceso telefónico</span><span class="sxs-lookup"><span data-stu-id="b2fbe-104">Migrate dial-in access numbers</span></span>

<span data-ttu-id="b2fbe-105">La migración de números de acceso telefónico local a Skype empresarial Server 2019 requiere la ejecución del cmdlet **Move-CsApplicationEndpoint** para migrar los objetos de contacto.</span><span class="sxs-lookup"><span data-stu-id="b2fbe-105">Migrating dial-in access numbers to Skype for Business Server 2019 requires running the **Move-CsApplicationEndpoint** cmdlet to migrate the contact objects.</span></span> <span data-ttu-id="b2fbe-106">Durante la instalación heredada y el período de coexistencia de Skype empresarial Server 2019, los números de acceso telefónico que ha creado en Skype empresarial Server 2019 se comportan de forma similar a los números de acceso telefónico que crea en la instalación heredada, tal como se describe en esta sección.</span><span class="sxs-lookup"><span data-stu-id="b2fbe-106">During the legacy install and Skype for Business Server 2019 coexistence period, dial-in access numbers that you created in Skype for Business Server 2019 behave similarly to the dial-in access numbers that you create in the legacy install, as described in this section.</span></span> 

<span data-ttu-id="b2fbe-107">Los números de acceso telefónico que ha creado en la instalación antigua, pero que se han movido a Skype empresarial Server 2019, o que ha creado en Skype empresarial Server 2019 antes, durante o después de la migración tienen las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="b2fbe-107">Dial-in access numbers that you created in the legacy install but moved to Skype for Business Server 2019, or that you created in Skype for Business Server 2019 before, during, or after migration, have the following characteristics:</span></span>

- <span data-ttu-id="b2fbe-108">No aparecen en las invitaciones a reuniones de Office Communications Server 2007 R2, ni en la página del número de acceso telefónico.</span><span class="sxs-lookup"><span data-stu-id="b2fbe-108">Do not appear on Office Communications Server 2007 R2 meeting invitations and the dial-in access number page.</span></span>

- <span data-ttu-id="b2fbe-109">Aparecen en las invitaciones de reunión heredadas y en la página de números de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="b2fbe-109">Appear on the legacy install meeting invitations and the dial-in access number page.</span></span>

- <span data-ttu-id="b2fbe-110">Aparecen en las invitaciones a reuniones de Skype empresarial Server 2019 y la página de número de acceso telefónico.</span><span class="sxs-lookup"><span data-stu-id="b2fbe-110">Appear on Skype for Business Server 2019 meeting invitations and the dial-in access number page.</span></span>

- <span data-ttu-id="b2fbe-111">No se pueden ver ni modificar en la herramienta administrativa de Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="b2fbe-111">Cannot be viewed or modified in the Office Communications Server 2007 R2 administrative tool.</span></span>

- <span data-ttu-id="b2fbe-112">Se pueden ver y modificar en el panel de control de instalación heredada y en el shell de administración de instalación heredada.</span><span class="sxs-lookup"><span data-stu-id="b2fbe-112">Can be viewed and modified in the legacy install Control Panel and in the legacy install Management Shell.</span></span>

- <span data-ttu-id="b2fbe-113">Se pueden ver y modificar en el panel de control de Skype empresarial Server 2019 y en el shell de administración de Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="b2fbe-113">Can be viewed and modified in the Skype for Business Server 2019 Control Panel and in Skype for Business Server 2019 Management Shell.</span></span>

- <span data-ttu-id="b2fbe-114">Se pueden volver a secuenciar en la región con el cmdlet Set-CsDialinConferencingAccessNumber con el parámetro Priority.</span><span class="sxs-lookup"><span data-stu-id="b2fbe-114">Can be re-sequenced within the region by using the Set-CsDialinConferencingAccessNumber cmdlet with the Priority parameter.</span></span>

<span data-ttu-id="b2fbe-115">Debe terminar de migrar los números de acceso telefónico que apuntan al grupo de instalación heredado antes de retirar el grupo de instalación heredado.</span><span class="sxs-lookup"><span data-stu-id="b2fbe-115">You must finish migrating dial-in access numbers that point to the legacy install pool before you decommission the legacy install pool.</span></span> <span data-ttu-id="b2fbe-116">Si no completa la migración de los números de acceso telefónico como se describe en el siguiente procedimiento, no se podrán realizar las llamadas entrantes a los números de acceso.</span><span class="sxs-lookup"><span data-stu-id="b2fbe-116">If you do not complete dial-in access number migration as described in the following procedure, incoming calls to the access numbers will fail.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b2fbe-117">Debe realizar este procedimiento antes de retirar el grupo de instalación heredado.</span><span class="sxs-lookup"><span data-stu-id="b2fbe-117">You must perform this procedure prior to decommissioning the legacy install pool.</span></span> 

> [!NOTE]
> <span data-ttu-id="b2fbe-118">Se recomienda que mueva los números de acceso telefónico cuando el uso de la red sea bajo, en caso de que se produzca una breve interrupción del servicio.</span><span class="sxs-lookup"><span data-stu-id="b2fbe-118">We recommend that you move dial-in access numbers when network usage is low, in case there is a short period of service outage.</span></span> 

## <a name="to-identify-and-move-dial-in-access-numbers"></a><span data-ttu-id="b2fbe-119">Para identificar y mover números de acceso telefónico</span><span class="sxs-lookup"><span data-stu-id="b2fbe-119">To identify and move dial-in access numbers</span></span>

1. <span data-ttu-id="b2fbe-120">Inicie el shell de administración de Skype empresarial Server: haga clic en **Inicio**, **todos los programas**, **Microsoft Skype empresarial Server 2019**y, a continuación, haga clic en **Shell de administración de Skype empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="b2fbe-120">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="b2fbe-121">Para mover cada número de acceso telefónico a un grupo hospedado en Skype empresarial Server 2019, en la línea de comandos, ejecute:</span><span class="sxs-lookup"><span data-stu-id="b2fbe-121">To move each dial-in access number to a pool hosted on Skype for Business Server 2019, from the command line run:</span></span> 

   ```PowerShell
   Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>
   ```

3. <span data-ttu-id="b2fbe-122">Abra el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="b2fbe-122">Open Skype for Business Server Control Panel.</span></span>

4. <span data-ttu-id="b2fbe-123">En la barra de navegación izquierda, haga clic en **Conferencia**.</span><span class="sxs-lookup"><span data-stu-id="b2fbe-123">In the left navigation bar, click **Conferencing**.</span></span>

5. <span data-ttu-id="b2fbe-124">Haga clic en la pestaña **Número de acceso telefónico**.</span><span class="sxs-lookup"><span data-stu-id="b2fbe-124">Click the **Dial-in Access Number** tab.</span></span> 

6. <span data-ttu-id="b2fbe-125">Compruebe que no quedan números de acceso telefónico para el grupo de instalación heredado desde el que va a migrar.</span><span class="sxs-lookup"><span data-stu-id="b2fbe-125">Verify that no dial-in access numbers remain for the legacy install pool from which you are migrating.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b2fbe-126">Cuando todos los números de acceso telefónico local señalan al grupo de servidores de Skype empresarial Server 2019, puede retirar el grupo de instalación heredado.</span><span class="sxs-lookup"><span data-stu-id="b2fbe-126">When all dial-in access numbers point to the Skype for Business Server 2019 pool, you can then decommission the legacy install pool.</span></span> 

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-control-panel"></a><span data-ttu-id="b2fbe-127">Comprobar la migración del número de acceso telefónico local mediante el panel de control de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="b2fbe-127">Verify the dial-in access number migration using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="b2fbe-128">Desde una cuenta de usuario asignada al rol **CsUserAdministrator** o al rol **CsAdministrator**, inicie sesión en cualquier PC de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="b2fbe-128">From a user account that is assigned to the **CsUserAdministrator** role or the **CsAdministrator** role, log on to any computer in your internal deployment.</span></span> 

2. <span data-ttu-id="b2fbe-129">Abra el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="b2fbe-129">Open Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="b2fbe-130">En la barra de navegación izquierda, haga clic en **Conferencia**.</span><span class="sxs-lookup"><span data-stu-id="b2fbe-130">In the left navigation bar, click **Conferencing**.</span></span>

4. <span data-ttu-id="b2fbe-131">Haga clic en la pestaña **Número de acceso telefónico**.</span><span class="sxs-lookup"><span data-stu-id="b2fbe-131">Click the **Dial-in Access Number** tab.</span></span> 

5. <span data-ttu-id="b2fbe-132">Compruebe que todos los números de acceso telefónico local se han migrado al grupo de servidores hospedado en Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="b2fbe-132">Verify that all the dial-in access numbers are migrated to the pool hosted on Skype for Business Server 2019.</span></span>

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-management-shell"></a><span data-ttu-id="b2fbe-133">Comprobar la migración del número de acceso telefónico local mediante el shell de administración de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="b2fbe-133">Verify the dial-in access number migration using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="b2fbe-134">Abra el shell de administración de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="b2fbe-134">Open Skype for Business Server Management Shell.</span></span>

2. <span data-ttu-id="b2fbe-135">Para devolver todos los números de acceso de conferencias de acceso telefónico migrados, en la línea de comandos ejecute:</span><span class="sxs-lookup"><span data-stu-id="b2fbe-135">To return all the dial-in conferencing access numbers migrated, from the command line run:</span></span>

   ```PowerShell
   Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}
   ```

3. <span data-ttu-id="b2fbe-136">Compruebe que todos los números de acceso telefónico local se han migrado al grupo de servidores hospedado en Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="b2fbe-136">Verify that all the dial-in access numbers are migrated to the pool hosted on Skype for Business Server 2019.</span></span>


