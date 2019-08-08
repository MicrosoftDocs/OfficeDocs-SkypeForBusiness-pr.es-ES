---
title: Migrar los números de acceso telefónico
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: La migración de números de acceso telefónico local a Skype empresarial Server 2019 requiere ejecutar el cmdlet Move-CsApplicationEndpoint para migrar los objetos de contacto. Durante la instalación heredada y el período de coexistencia de Skype empresarial 2019, los números de acceso telefónico local creados en Skype empresarial Server 2019 se comportan de forma similar a los números de acceso telefónico local que se crean en la instalación heredada, como se describe en este sección.
ms.openlocfilehash: 81f100979d009f4f9b48cf9a538ec92095a67ad8
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36238049"
---
# <a name="migrate-dial-in-access-numbers"></a><span data-ttu-id="5578a-104">Migrar los números de acceso telefónico</span><span class="sxs-lookup"><span data-stu-id="5578a-104">Migrate dial-in access numbers</span></span>

<span data-ttu-id="5578a-105">La migración de números de acceso telefónico local a Skype empresarial Server 2019 requiere ejecutar el cmdlet **Move-CsApplicationEndpoint** para migrar los objetos de contacto.</span><span class="sxs-lookup"><span data-stu-id="5578a-105">Migrating dial-in access numbers to Skype for Business Server 2019 requires running the **Move-CsApplicationEndpoint** cmdlet to migrate the contact objects.</span></span> <span data-ttu-id="5578a-106">Durante la instalación heredada y el período de coexistencia de Skype empresarial 2019, los números de acceso telefónico local creados en Skype empresarial Server 2019 se comportan de forma similar a los números de acceso telefónico local que se crean en la instalación heredada, como se describe en este sección.</span><span class="sxs-lookup"><span data-stu-id="5578a-106">During the legacy install and Skype for Business Server 2019 coexistence period, dial-in access numbers that you created in Skype for Business Server 2019 behave similarly to the dial-in access numbers that you create in the legacy install, as described in this section.</span></span> 

<span data-ttu-id="5578a-107">Los números de acceso telefónico local que ha creado en la instalación heredada, pero que ha movido a Skype empresarial Server 2019, o que ha creado en Skype empresarial Server 2019 antes, durante o después de la migración, tienen las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="5578a-107">Dial-in access numbers that you created in the legacy install but moved to Skype for Business Server 2019, or that you created in Skype for Business Server 2019 before, during, or after migration, have the following characteristics:</span></span>

- <span data-ttu-id="5578a-108">No aparecen en las invitaciones a reuniones de Office Communications Server 2007 R2 y la página de número de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="5578a-108">Do not appear on Office Communications Server 2007 R2 meeting invitations and the dial-in access number page.</span></span>

- <span data-ttu-id="5578a-109">Aparece en la página heredar las invitaciones a reuniones y el número de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="5578a-109">Appear on the legacy install meeting invitations and the dial-in access number page.</span></span>

- <span data-ttu-id="5578a-110">Aparece en las invitaciones a reuniones de Skype empresarial Server 2019 y la página de número de acceso telefónico local.</span><span class="sxs-lookup"><span data-stu-id="5578a-110">Appear on Skype for Business Server 2019 meeting invitations and the dial-in access number page.</span></span>

- <span data-ttu-id="5578a-111">No se puede ver ni modificar en la herramienta administrativa de Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="5578a-111">Cannot be viewed or modified in the Office Communications Server 2007 R2 administrative tool.</span></span>

- <span data-ttu-id="5578a-112">Se puede ver y modificar en el panel de control de instalación heredado y en el shell de administración de instalación heredado.</span><span class="sxs-lookup"><span data-stu-id="5578a-112">Can be viewed and modified in the legacy install Control Panel and in the legacy install Management Shell.</span></span>

- <span data-ttu-id="5578a-113">Se puede ver y modificar en el panel de control de Skype empresarial Server 2019 y en el shell de administración de Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="5578a-113">Can be viewed and modified in the Skype for Business Server 2019 Control Panel and in Skype for Business Server 2019 Management Shell.</span></span>

- <span data-ttu-id="5578a-114">Se puede volver a secuenciar dentro de la región mediante el cmdlet Set-CsDialinConferencingAccessNumber con el parámetro Priority.</span><span class="sxs-lookup"><span data-stu-id="5578a-114">Can be re-sequenced within the region by using the Set-CsDialinConferencingAccessNumber cmdlet with the Priority parameter.</span></span>

<span data-ttu-id="5578a-115">Debe finalizar la migración de los números de acceso telefónico local que apunten al grupo de instalación heredado antes de retirar el grupo de instalación heredado.</span><span class="sxs-lookup"><span data-stu-id="5578a-115">You must finish migrating dial-in access numbers that point to the legacy install pool before you decommission the legacy install pool.</span></span> <span data-ttu-id="5578a-116">Si no completa la migración de números de acceso telefónico, como se describe en el siguiente procedimiento, se producirán errores en las llamadas entrantes a los números de acceso.</span><span class="sxs-lookup"><span data-stu-id="5578a-116">If you do not complete dial-in access number migration as described in the following procedure, incoming calls to the access numbers will fail.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5578a-117">Debe realizar este procedimiento antes de dar de baja al grupo de instalación heredado.</span><span class="sxs-lookup"><span data-stu-id="5578a-117">You must perform this procedure prior to decommissioning the legacy install pool.</span></span> 

> [!NOTE]
> <span data-ttu-id="5578a-118">Le recomendamos que mueva los números de acceso telefónico cuando el uso de la red sea bajo, en caso de que haya un breve período de tiempo de servicio.</span><span class="sxs-lookup"><span data-stu-id="5578a-118">We recommend that you move dial-in access numbers when network usage is low, in case there is a short period of service outage.</span></span> 

## <a name="to-identify-and-move-dial-in-access-numbers"></a><span data-ttu-id="5578a-119">Para identificar y mover los números de acceso telefónico local</span><span class="sxs-lookup"><span data-stu-id="5578a-119">To identify and move dial-in access numbers</span></span>

1. <span data-ttu-id="5578a-120">Inicie el shell de administración de Skype empresarial Server: haga clic en **Inicio**, haga clic en **todos los programas**, haga clic en **Microsoft Skype empresarial Server 2019**y, a continuación, haga clic en **consola de administración de Skype empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="5578a-120">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="5578a-121">Para mover cada número de acceso de acceso telefónico local a un grupo hospedado en Skype empresarial Server 2019, ejecute:</span><span class="sxs-lookup"><span data-stu-id="5578a-121">To move each dial-in access number to a pool hosted on Skype for Business Server 2019, from the command line run:</span></span> 

   ```
   Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>
   ```

3. <span data-ttu-id="5578a-122">Abra el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="5578a-122">Open Skype for Business Server Control Panel.</span></span>

4. <span data-ttu-id="5578a-123">En la barra de navegación izquierda, haga clic en **Conferencia**.</span><span class="sxs-lookup"><span data-stu-id="5578a-123">In the left navigation bar, click **Conferencing**.</span></span>

5. <span data-ttu-id="5578a-124">Haga clic en la pestaña **número de acceso telefónico local** .</span><span class="sxs-lookup"><span data-stu-id="5578a-124">Click the **Dial-in Access Number** tab.</span></span> 

6. <span data-ttu-id="5578a-125">Compruebe que no quedan números de acceso telefónico local para el grupo de instalación heredado desde el que va a migrar.</span><span class="sxs-lookup"><span data-stu-id="5578a-125">Verify that no dial-in access numbers remain for the legacy install pool from which you are migrating.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5578a-126">Cuando todos los números de acceso telefónico local señalan al grupo de servidores de Skype empresarial 2019, puede desactivar el grupo de instalación heredado.</span><span class="sxs-lookup"><span data-stu-id="5578a-126">When all dial-in access numbers point to the Skype for Business Server 2019 pool, you can then decommission the legacy install pool.</span></span> 

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-control-panel"></a><span data-ttu-id="5578a-127">Comprobar la migración de números de acceso telefónico local con el panel de control de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="5578a-127">Verify the dial-in access number migration using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="5578a-128">Desde una cuenta de usuario que tenga asignada la función **CsUserAdministrator** o el rol **CsAdministrator** , inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="5578a-128">From a user account that is assigned to the **CsUserAdministrator** role or the **CsAdministrator** role, log on to any computer in your internal deployment.</span></span> 

2. <span data-ttu-id="5578a-129">Abra el panel de control de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="5578a-129">Open Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="5578a-130">En la barra de navegación izquierda, haga clic en **Conferencia**.</span><span class="sxs-lookup"><span data-stu-id="5578a-130">In the left navigation bar, click **Conferencing**.</span></span>

4. <span data-ttu-id="5578a-131">Haga clic en la pestaña **número de acceso telefónico local** .</span><span class="sxs-lookup"><span data-stu-id="5578a-131">Click the **Dial-in Access Number** tab.</span></span> 

5. <span data-ttu-id="5578a-132">Compruebe que todos los números de acceso telefónico local se migran al grupo hospedado en Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="5578a-132">Verify that all the dial-in access numbers are migrated to the pool hosted on Skype for Business Server 2019.</span></span>

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-management-shell"></a><span data-ttu-id="5578a-133">Comprobar la migración de números de acceso telefónico local con el shell de administración de Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="5578a-133">Verify the dial-in access number migration using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="5578a-134">Abra el shell de administración de Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="5578a-134">Open Skype for Business Server Management Shell.</span></span>

2. <span data-ttu-id="5578a-135">Para devolver todos los números de acceso de la Conferencia de acceso telefónico local migrados, desde la línea de comandos ejecute:</span><span class="sxs-lookup"><span data-stu-id="5578a-135">To return all the dial-in conferencing access numbers migrated, from the command line run:</span></span>

   ```
   Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}
   ```

3. <span data-ttu-id="5578a-136">Compruebe que todos los números de acceso telefónico local se migran al grupo hospedado en Skype empresarial Server 2019.</span><span class="sxs-lookup"><span data-stu-id="5578a-136">Verify that all the dial-in access numbers are migrated to the pool hosted on Skype for Business Server 2019.</span></span>


