---
title: Migrar los números de acceso telefónico
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate dial-in access numbers
ms:assetid: e0dfaed2-64c7-45cb-aaa9-d6117a26625d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721909(v=OCS.15)
ms:contentKeyID: 49733843
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eaef027180304fca2a64294177faffcc0811e565
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148919"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-dial-in-access-numbers"></a><span data-ttu-id="dad07-102">Migrar los números de acceso telefónico</span><span class="sxs-lookup"><span data-stu-id="dad07-102">Migrate dial-in access numbers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dad07-103">_**Última modificación del tema:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="dad07-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="dad07-104">La migración de números de acceso telefónico local de Lync Server 2010 a Lync Server 2013 requiere la ejecución del cmdlet **Move-CsApplicationEndpoint** para migrar los objetos de contacto.</span><span class="sxs-lookup"><span data-stu-id="dad07-104">Migrating dial-in access numbers from Lync Server 2010 to Lync Server 2013 requires running the **Move-CsApplicationEndpoint** cmdlet to migrate the contact objects.</span></span> <span data-ttu-id="dad07-105">Durante el período de coexistencia de Lync Server 2010 y Lync Server 2013, los números de acceso telefónico que ha creado en Lync Server 2013 se comportan de forma similar a los números de acceso telefónico que crea en Lync Server 2010, tal como se describe en esta sección.</span><span class="sxs-lookup"><span data-stu-id="dad07-105">During the Lync Server 2010 and Lync Server 2013 coexistence period, dial-in access numbers that you created in Lync Server 2013 behave similarly to the dial-in access numbers that you create in Lync Server 2010, as described in this section.</span></span>

<span data-ttu-id="dad07-106">Los números de acceso telefónico que ha creado en Lync Server 2010, pero que se han movido a Lync Server 2013 o que ha creado en Lync Server 2013 antes, durante o después de la migración tienen las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="dad07-106">Dial-in access numbers that you created in Lync Server 2010 but moved to Lync Server 2013 or that you created in Lync Server 2013 before, during or after migration have the following characteristics:</span></span>

  - <span data-ttu-id="dad07-107">No aparecen en las invitaciones a reuniones de Office Communications Server 2007 R2, ni en la página del número de acceso telefónico.</span><span class="sxs-lookup"><span data-stu-id="dad07-107">Do not appear on Office Communications Server 2007 R2 meeting invitations and the dial-in access number page.</span></span>

  - <span data-ttu-id="dad07-108">Aparecen en las invitaciones a reuniones de Lync Server 2010 y en la página del número de acceso telefónico.</span><span class="sxs-lookup"><span data-stu-id="dad07-108">Appear on Lync Server 2010 meeting invitations and the dial-in access number page.</span></span>

  - <span data-ttu-id="dad07-109">Aparecen en las invitaciones a reuniones de Lync Server 2013 y en la página del número de acceso telefónico.</span><span class="sxs-lookup"><span data-stu-id="dad07-109">Appear on Lync Server 2013 meeting invitations and the dial-in access number page.</span></span>

  - <span data-ttu-id="dad07-110">No se pueden ver ni modificar en la herramienta administrativa de Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="dad07-110">Cannot be viewed or modified in the Office Communications Server 2007 R2 administrative tool.</span></span>

  - <span data-ttu-id="dad07-111">Se pueden ver y modificar en el panel de control de Lync Server 2010 y en el shell de administración de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="dad07-111">Can be viewed and modified in the Lync Server 2010 Control Panel and in Lync Server 2010 Management Shell.</span></span>

  - <span data-ttu-id="dad07-112">Se pueden ver y modificar en el panel de control de Lync Server 2013 y en el shell de administración de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dad07-112">Can be viewed and modified in the Lync Server 2013 Control Panel and in Lync Server 2013 Management Shell.</span></span>

  - <span data-ttu-id="dad07-113">Se pueden volver a secuenciar en la región con el cmdlet Set-CsDialinConferencingAccessNumber con el parámetro Priority.</span><span class="sxs-lookup"><span data-stu-id="dad07-113">Can be re-sequenced within the region by using the Set-CsDialinConferencingAccessNumber cmdlet with the Priority parameter.</span></span>

<span data-ttu-id="dad07-p102">Finalice la migración de los números de acceso telefónico que apuntan a un grupo de servidores de Lync Server 2010, para dar de baja el grupo de servidores de Lync Server 2010. Si no finaliza la migración tal como se describe en el procedimiento siguiente, las llamadas entrantes a los números de acceso serán erróneas.</span><span class="sxs-lookup"><span data-stu-id="dad07-p102">You must finish migrating dial-in access numbers that point to a Lync Server 2010 pool before you decommission the Lync Server 2010 pool. If you do not complete dial-in access number migration as described in the following procedure, incoming calls to the access numbers will fail.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="dad07-116">Debe realizar este procedimiento antes de retirar el grupo de servidores de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="dad07-116">You must perform this procedure prior to decommissioning the Lync Server 2010 pool.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="dad07-117">Se recomienda que mueva los números de acceso telefónico cuando el uso de la red sea bajo, en caso de que se produzca una breve interrupción del servicio.</span><span class="sxs-lookup"><span data-stu-id="dad07-117">We recommend that you move dial-in access numbers when network usage is low, in case there is a short period of service outage.</span></span>



</div>

<span data-ttu-id="dad07-118">**Para identificar y mover números de acceso telefónico**</span><span class="sxs-lookup"><span data-stu-id="dad07-118">**To identify and move dial-in access numbers**</span></span>

1.  <span data-ttu-id="dad07-119">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="dad07-119">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="dad07-120">Para mover cada número de acceso telefónico a un grupo hospedado en Lync Server 2013, en la línea de comandos, ejecute:</span><span class="sxs-lookup"><span data-stu-id="dad07-120">To move each dial-in access number to a pool hosted on Lync Server 2013, from the command line run:</span></span>
    
        Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>

3.  <span data-ttu-id="dad07-121">Abra Panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="dad07-121">Open Lync Server Control Panel.</span></span>

4.  <span data-ttu-id="dad07-122">En la barra de navegación izquierda, haga clic en **Conferencia**.</span><span class="sxs-lookup"><span data-stu-id="dad07-122">In the left navigation bar, click **Conferencing**.</span></span>

5.  <span data-ttu-id="dad07-123">Haga clic en la pestaña **Número de acceso telefónico**.</span><span class="sxs-lookup"><span data-stu-id="dad07-123">Click the **Dial-in Access Number** tab.</span></span>

6.  <span data-ttu-id="dad07-124">Compruebe que no quedan números de acceso telefónico para el grupo de servidores de Lync 2010 desde el que está migrando.</span><span class="sxs-lookup"><span data-stu-id="dad07-124">Verify that no dial-in access numbers remain for the Lync Server 2010 pool from which you are migrating.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="dad07-125">Cuando todos los números de acceso telefónico local señalan al grupo de servidores de Lync Server 2013, puede retirar el grupo de servidores de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="dad07-125">When all dial-in access numbers point to the Lync Server 2013 pool, you can then decommission the Lync Server 2010 pool.</span></span>

    
    </div>

<span data-ttu-id="dad07-126">**Comprobar la migración del número de acceso telefónico con el panel de control de Lync Server**</span><span class="sxs-lookup"><span data-stu-id="dad07-126">**Verify the dial-in access number migration using Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="dad07-127">Desde una cuenta de usuario asignada al rol **CsUserAdministrator** o al rol **CsAdministrator**, inicie sesión en cualquier PC de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="dad07-127">From a user account that is assigned to the **CsUserAdministrator** role or the **CsAdministrator** role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="dad07-128">Abra Panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="dad07-128">Open Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="dad07-129">En la barra de navegación izquierda, haga clic en **Conferencia**.</span><span class="sxs-lookup"><span data-stu-id="dad07-129">In the left navigation bar, click **Conferencing**.</span></span>

4.  <span data-ttu-id="dad07-130">Haga clic en la pestaña **Número de acceso telefónico**.</span><span class="sxs-lookup"><span data-stu-id="dad07-130">Click the **Dial-in Access Number** tab.</span></span>

5.  <span data-ttu-id="dad07-131">Compruebe que todo el número de acceso telefónico local se ha migrado al grupo hospedado en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dad07-131">Verify all the dial-in access number are migrated to the pool hosted on Lync Server 2013.</span></span>

<span data-ttu-id="dad07-132">**Comprobar la migración del número de acceso telefónico con el shell de administración de Lync Server**</span><span class="sxs-lookup"><span data-stu-id="dad07-132">**Verify the dial-in access number migration using Lync Server Management Shell**</span></span>

1.  <span data-ttu-id="dad07-133">Abra el shell de administración de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="dad07-133">Open Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="dad07-134">Para devolver todos los números de acceso de conferencias de acceso telefónico migrados, en la línea de comandos ejecute:</span><span class="sxs-lookup"><span data-stu-id="dad07-134">To return all the dial-in conferencing access numbers migrated, from the command line run:</span></span>
    
        Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}

3.  <span data-ttu-id="dad07-135">Compruebe que todos los números de acceso telefónico local se migren al grupo hospedado en Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dad07-135">Verify all the dial-in access numbers are migrated to the pool hosted on Lync Server 2013.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

