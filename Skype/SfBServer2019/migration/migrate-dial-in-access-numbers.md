---
title: Migrar los números de acceso telefónico
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Migrar números de acceso telefónico a Skype para Business Server 2019 requiere ejecutando el cmdlet Move-CsApplicationEndpoint para migrar los objetos de contacto. Durante la instalación heredado y Skype para el período de coexistencia de Business Server 2019, los números de acceso telefónico que creó en Skype para Business Server 2019 se comportan de forma similar a los números de acceso telefónico que se crean en la instalación heredada, tal como se describe en este sección.
ms.openlocfilehash: 7f7aef113018a27e70b88e166d365195c07dce9c
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32239586"
---
# <a name="migrate-dial-in-access-numbers"></a><span data-ttu-id="afca2-104">Migrar los números de acceso telefónico</span><span class="sxs-lookup"><span data-stu-id="afca2-104">Migrate dial-in access numbers</span></span>

<span data-ttu-id="afca2-105">Migrar números de acceso telefónico a Skype para Business Server 2019 requiere ejecutando el cmdlet **Move-CsApplicationEndpoint** para migrar los objetos de contacto.</span><span class="sxs-lookup"><span data-stu-id="afca2-105">Migrating dial-in access numbers to Skype for Business Server 2019 requires running the **Move-CsApplicationEndpoint** cmdlet to migrate the contact objects.</span></span> <span data-ttu-id="afca2-106">Durante la instalación heredado y Skype para el período de coexistencia de Business Server 2019, los números de acceso telefónico que creó en Skype para Business Server 2019 se comportan de forma similar a los números de acceso telefónico que se crean en la instalación heredada, tal como se describe en este sección.</span><span class="sxs-lookup"><span data-stu-id="afca2-106">During the legacy install and Skype for Business Server 2019 coexistence period, dial-in access numbers that you created in Skype for Business Server 2019 behave similarly to the dial-in access numbers that you create in the legacy install, as described in this section.</span></span> 

<span data-ttu-id="afca2-107">Los números de acceso telefónico que creó en el heredado instalación pero movido a Skype para Business Server 2019 o que haya creado en Skype para Business Server 2019 antes, durante o después de la migración, tienen las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="afca2-107">Dial-in access numbers that you created in the legacy install but moved to Skype for Business Server 2019, or that you created in Skype for Business Server 2019 before, during, or after migration, have the following characteristics:</span></span>

- <span data-ttu-id="afca2-108">No aparecen en las invitaciones a reuniones de Office Communications Server 2007 R2 y la página de números de acceso telefónico.</span><span class="sxs-lookup"><span data-stu-id="afca2-108">Do not appear on Office Communications Server 2007 R2 meeting invitations and the dial-in access number page.</span></span>

- <span data-ttu-id="afca2-109">Aparecen en las invitaciones a reuniones de instalación heredados y la página de números de acceso telefónico.</span><span class="sxs-lookup"><span data-stu-id="afca2-109">Appear on the legacy install meeting invitations and the dial-in access number page.</span></span>

- <span data-ttu-id="afca2-110">Aparecen en Skype para Business Server 2019 las invitaciones a reuniones y la página de números de acceso telefónico.</span><span class="sxs-lookup"><span data-stu-id="afca2-110">Appear on Skype for Business Server 2019 meeting invitations and the dial-in access number page.</span></span>

- <span data-ttu-id="afca2-111">No se puede ver ni modificar en la herramienta administrativa de Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="afca2-111">Cannot be viewed or modified in the Office Communications Server 2007 R2 administrative tool.</span></span>

- <span data-ttu-id="afca2-112">Se pueden ver y modificar en el Panel de Control de instalación heredada y en el Shell de administración de instalar heredado.</span><span class="sxs-lookup"><span data-stu-id="afca2-112">Can be viewed and modified in the legacy install Control Panel and in the legacy install Management Shell.</span></span>

- <span data-ttu-id="afca2-113">Se pueden ver y modificar en la Skype para el Panel de Control de Business Server 2019 y en Skype para Shell de administración de Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="afca2-113">Can be viewed and modified in the Skype for Business Server 2019 Control Panel and in Skype for Business Server 2019 Management Shell.</span></span>

- <span data-ttu-id="afca2-114">Se pueden volver a secuenciar en la región mediante el cmdlet Set-CsDialinConferencingAccessNumber con el parámetro Priority.</span><span class="sxs-lookup"><span data-stu-id="afca2-114">Can be re-sequenced within the region by using the Set-CsDialinConferencingAccessNumber cmdlet with the Priority parameter.</span></span>

<span data-ttu-id="afca2-115">Debe finalizar la migración de los números de acceso telefónico que apuntan a la heredada instalan el grupo de servidores antes de retirar el grupo de instalación heredado.</span><span class="sxs-lookup"><span data-stu-id="afca2-115">You must finish migrating dial-in access numbers that point to the legacy install pool before you decommission the legacy install pool.</span></span> <span data-ttu-id="afca2-116">Si no completa la migración del número de acceso telefónico como se describe en el procedimiento siguiente, se producirá un error en las llamadas entrantes a los números de acceso.</span><span class="sxs-lookup"><span data-stu-id="afca2-116">If you do not complete dial-in access number migration as described in the following procedure, incoming calls to the access numbers will fail.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="afca2-117">Debe realizar este procedimiento antes de retirar el grupo de instalación heredado.</span><span class="sxs-lookup"><span data-stu-id="afca2-117">You must perform this procedure prior to decommissioning the legacy install pool.</span></span> 

> [!NOTE]
> <span data-ttu-id="afca2-118">Se recomienda que mueva los números de acceso telefónico cuando el uso de la red sea bajo, en caso de que hay un período breve interrupción del servicio.</span><span class="sxs-lookup"><span data-stu-id="afca2-118">We recommend that you move dial-in access numbers when network usage is low, in case there is a short period of service outage.</span></span> 

## <a name="to-identify-and-move-dial-in-access-numbers"></a><span data-ttu-id="afca2-119">Para identificar y mueva los números de acceso telefónico</span><span class="sxs-lookup"><span data-stu-id="afca2-119">To identify and move dial-in access numbers</span></span>

1. <span data-ttu-id="afca2-120">Iniciar el Skype para Shell de administración de negocio Server: haga clic en **Inicio**, haga clic en **Todos los programas**, haga clic en **Microsoft Skype para Business Server 2019**y, a continuación, haga clic en **Skype para Shell de administración de servidor empresarial**.</span><span class="sxs-lookup"><span data-stu-id="afca2-120">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="afca2-121">Para mover cada número de acceso telefónico a un grupo hospedado en Skype para Business Server 2019, desde la línea de comandos ejecute:</span><span class="sxs-lookup"><span data-stu-id="afca2-121">To move each dial-in access number to a pool hosted on Skype for Business Server 2019, from the command line run:</span></span> 

   ```
   Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>
   ```

3. <span data-ttu-id="afca2-122">Abra Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="afca2-122">Open Skype for Business Server Control Panel.</span></span>

4. <span data-ttu-id="afca2-123">En la barra de navegación izquierda, haga clic en **Conferencia**.</span><span class="sxs-lookup"><span data-stu-id="afca2-123">In the left navigation bar, click **Conferencing**.</span></span>

5. <span data-ttu-id="afca2-124">Haga clic en la ficha **Número de acceso telefónico** .</span><span class="sxs-lookup"><span data-stu-id="afca2-124">Click the **Dial-in Access Number** tab.</span></span> 

6. <span data-ttu-id="afca2-125">Compruebe que no queda ningún número de acceso telefónico para el grupo de servidores heredados de instalación desde la que va a migrar.</span><span class="sxs-lookup"><span data-stu-id="afca2-125">Verify that no dial-in access numbers remain for the legacy install pool from which you are migrating.</span></span>

    > [!NOTE]
    > <span data-ttu-id="afca2-126">Cuando elija el Skype para el grupo de servidores de Business Server 2019 todos los números de acceso telefónico, a continuación, puede dar de baja el grupo de instalación heredado.</span><span class="sxs-lookup"><span data-stu-id="afca2-126">When all dial-in access numbers point to the Skype for Business Server 2019 pool, you can then decommission the legacy install pool.</span></span> 

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-control-panel"></a><span data-ttu-id="afca2-127">Comprobar la migración de números de acceso telefónico con Skype para el Panel de Control de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="afca2-127">Verify the dial-in access number migration using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="afca2-128">Desde una cuenta de usuario que se asigna al rol **CsUserAdministrator** o **csadministrator** , inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="afca2-128">From a user account that is assigned to the **CsUserAdministrator** role or the **CsAdministrator** role, log on to any computer in your internal deployment.</span></span> 

2. <span data-ttu-id="afca2-129">Abra Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="afca2-129">Open Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="afca2-130">En la barra de navegación izquierda, haga clic en **Conferencia**.</span><span class="sxs-lookup"><span data-stu-id="afca2-130">In the left navigation bar, click **Conferencing**.</span></span>

4. <span data-ttu-id="afca2-131">Haga clic en la ficha **Número de acceso telefónico** .</span><span class="sxs-lookup"><span data-stu-id="afca2-131">Click the **Dial-in Access Number** tab.</span></span> 

5. <span data-ttu-id="afca2-132">Compruebe que todos los números de acceso telefónico se migran al grupo de servidores hospedado en Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="afca2-132">Verify that all the dial-in access numbers are migrated to the pool hosted on Skype for Business Server 2019.</span></span>

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-management-shell"></a><span data-ttu-id="afca2-133">Comprobar la migración de números de acceso telefónico con Skype para Shell de administración de servidor empresarial</span><span class="sxs-lookup"><span data-stu-id="afca2-133">Verify the dial-in access number migration using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="afca2-134">Abra Skype para Shell de administración de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="afca2-134">Open Skype for Business Server Management Shell.</span></span>

2. <span data-ttu-id="afca2-135">Para devolver todos los números de acceso telefónico migran, desde la línea de comandos que se ejecute:</span><span class="sxs-lookup"><span data-stu-id="afca2-135">To return all the dial-in conferencing access numbers migrated, from the command line run:</span></span>

   ```
   Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}
   ```

3. <span data-ttu-id="afca2-136">Compruebe que todos los números de acceso telefónico se migran al grupo de servidores hospedado en Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="afca2-136">Verify that all the dial-in access numbers are migrated to the pool hosted on Skype for Business Server 2019.</span></span>


