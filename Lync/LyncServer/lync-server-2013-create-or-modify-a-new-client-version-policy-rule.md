---
title: 'Lync Server 2013: crear o modificar una nueva regla de directiva de versión de cliente'
description: 'Lync Server 2013: cree o modifique una nueva regla de directiva de versión de cliente.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a new client version policy rule
ms:assetid: 6f879d99-8401-41e0-a562-195c890d63ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898478(v=OCS.15)
ms:contentKeyID: 50873758
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 11ebcf17d5cb14fd519fba8ad36be10894fabdb9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574626"
---
# <a name="create-or-modify-a-new-client-version-policy-rule-in-lync-server-2013"></a><span data-ttu-id="1cedd-103">Crear o modificar una nueva regla de directiva de versión de cliente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1cedd-103">Create or modify a new client version policy rule in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1cedd-104">_**Última modificación del tema:** 2013-01-21_</span><span class="sxs-lookup"><span data-stu-id="1cedd-104">_**Topic Last Modified:** 2013-01-21_</span></span>

<span data-ttu-id="1cedd-105">Las reglas de directiva de versión de cliente definen las acciones que se deben llevar a cabo cuando los usuarios intentan iniciar sesión con clientes y versiones de cliente específicos.</span><span class="sxs-lookup"><span data-stu-id="1cedd-105">Client version policy rules define the actions that should be taken when users attempt to log on with specific clients and client versions.</span></span> <span data-ttu-id="1cedd-106">Puede crear o modificar reglas individuales para una directiva de versión de cliente desde el panel de control de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1cedd-106">You can create or modify individual rules for a client version policy from Lync Server 2013 Control Panel.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="1cedd-107">Las reglas se enumeran en orden de prioridad.</span><span class="sxs-lookup"><span data-stu-id="1cedd-107">Rules are listed in order of precedence.</span></span> <span data-ttu-id="1cedd-108">Por ejemplo, si tiene una regla que permite la conexión a los clientes que ejecutan la versión 1,5, seguido de una regla que bloquea los clientes que ejecutan una versión anterior a la 2,0, la primera regla tiene prioridad y los clientes que ejecutan la versión 1,5 tienen permiso para conectarse.</span><span class="sxs-lookup"><span data-stu-id="1cedd-108">For example, if you have a rule that allows clients running version 1.5 to connect, followed by a rule that blocks clients running a version earlier than 2.0, the first rule takes precedence, and clients running version 1.5 are allowed to connect.</span></span>



</div>

<div>

## <a name="to-create-or-modify-client-version-policy-rules-with-lync-server-control-panel"></a><span data-ttu-id="1cedd-109">Para crear o modificar reglas de directiva de versión de cliente con el panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="1cedd-109">To create or modify client version policy rules with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="1cedd-110">[Cree o modifique una nueva Directiva de versión de cliente en Lync server 2013 con el](lync-server-2013-create-or-modify-a-new-client-version-policy.md) panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1cedd-110">[Create or modify a new client version policy in Lync Server 2013](lync-server-2013-create-or-modify-a-new-client-version-policy.md) with Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="1cedd-111">En la página **Editar Directiva de versión de cliente** , realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="1cedd-111">On the **Edit Client Version Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="1cedd-112">Haga clic en **Nueva** para crear una regla nueva de versión de cliente.</span><span class="sxs-lookup"><span data-stu-id="1cedd-112">Click **New** to create a new client version rule.</span></span>
    
      - <span data-ttu-id="1cedd-113">Haga clic en uno de los tipos de cliente definidos en la lista y, a continuación, haga clic en **Mostrar detalles...**.</span><span class="sxs-lookup"><span data-stu-id="1cedd-113">Click one of the defined client types in the list, and then click **Show details**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1cedd-114">Puede usar comodines para indicar el tipo de cliente.</span><span class="sxs-lookup"><span data-stu-id="1cedd-114">You can use wildcards to indicate the client type.</span></span>

    
    </div>

3.  <span data-ttu-id="1cedd-115">En **Aplicación**, seleccione un tipo de cliente.</span><span class="sxs-lookup"><span data-stu-id="1cedd-115">In **User agent**, select a client type.</span></span>

4.  <span data-ttu-id="1cedd-116">En **Número de versión**, siga este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="1cedd-116">Under **Version number**, do the following:</span></span>
    
      - <span data-ttu-id="1cedd-117">En **Versión principal**, escriba el número que se corresponde con la versión principal del cliente.</span><span class="sxs-lookup"><span data-stu-id="1cedd-117">In **Major version**, type the number that corresponds to the major release of the client.</span></span>
    
      - <span data-ttu-id="1cedd-118">En **Versión secundaria**, escriba el número que se corresponde con la versión secundaria del cliente.</span><span class="sxs-lookup"><span data-stu-id="1cedd-118">In **Minor version**, type the number that corresponds to the minor release of the client.</span></span>
    
      - <span data-ttu-id="1cedd-119">En **Versión**, escriba el número que se corresponde con la versión principal y secundaria del cliente.</span><span class="sxs-lookup"><span data-stu-id="1cedd-119">In **Build**, type the number that corresponds to the major and minor release of the client.</span></span>
    
      - <span data-ttu-id="1cedd-120">En **Actualización**, escriba el número que se corresponde con la versión actualizada del cliente.</span><span class="sxs-lookup"><span data-stu-id="1cedd-120">In **Update**, type the number that corresponds to the updated release of the client.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1cedd-121">Puede usar caracteres comodín para indicar el número de versión del cliente.</span><span class="sxs-lookup"><span data-stu-id="1cedd-121">You can use wildcards to indicate the client version number.</span></span>

    
    </div>

5.  <span data-ttu-id="1cedd-122">Para especificar la operación coincidente para la versión del cliente que haya especificado en los pasos anteriores, en **Operación de comparación**, haga clic en una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="1cedd-122">To specify the matching operation for the client version you specified in the preceding steps, in **Comparison operation**, click one of the following:</span></span>
    
      - <span data-ttu-id="1cedd-123">**Igual que**</span><span class="sxs-lookup"><span data-stu-id="1cedd-123">**Same as**</span></span>
    
      - <span data-ttu-id="1cedd-124">**No es**</span><span class="sxs-lookup"><span data-stu-id="1cedd-124">**Is not**</span></span>
    
      - <span data-ttu-id="1cedd-125">**Anterior a**</span><span class="sxs-lookup"><span data-stu-id="1cedd-125">**Newer than**</span></span>
    
      - <span data-ttu-id="1cedd-126">**Anterior a o igual que**</span><span class="sxs-lookup"><span data-stu-id="1cedd-126">**Newer than or same as**</span></span>
    
      - <span data-ttu-id="1cedd-127">**Posterior a**</span><span class="sxs-lookup"><span data-stu-id="1cedd-127">**Older than**</span></span>
    
      - <span data-ttu-id="1cedd-128">**Posterior a o igual que**</span><span class="sxs-lookup"><span data-stu-id="1cedd-128">**Older than or same as**</span></span>

6.  <span data-ttu-id="1cedd-129">Para especificar la acción a realizar cuando se cumplen los criterios de los pasos anteriores, haga clic en una de las siguientes opciones en **Acción**:</span><span class="sxs-lookup"><span data-stu-id="1cedd-129">To specify the action to perform when the criteria in the preceding steps are met, click one of the following in **Action**:</span></span>
    
      - <span data-ttu-id="1cedd-130">Para permitir que el usuario inicie sesión, haga clic en **Permitir**.</span><span class="sxs-lookup"><span data-stu-id="1cedd-130">To allow the client to log on, click **Allow**.</span></span>
    
      - <span data-ttu-id="1cedd-131">Para permitir que el cliente inicie sesión y reciba actualizaciones de Windows Server Update Service o Microsoft Update, haga clic en **permitir y actualizar**.</span><span class="sxs-lookup"><span data-stu-id="1cedd-131">To allow the client to log on and receive updates from Windows Server Update Service or Microsoft Update, click **Allow and Upgrade**.</span></span> <span data-ttu-id="1cedd-132">Esta acción solo está disponible cuando se selecciona **OC** del agente del usuario.</span><span class="sxs-lookup"><span data-stu-id="1cedd-132">This action is available only when user agent **OC** is selected.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="1cedd-133">Al seleccionar esta acción, aparecerá una notificación la próxima vez que los usuarios inicien sesión en Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="1cedd-133">Selecting this action causes a notification to appear the next time users sign in to Lync 2013.</span></span> <span data-ttu-id="1cedd-134">La notificación comunica que hay una actualización disponible, aunque las actualizaciones aún no se hayan publicado en Windows Server Update Service o en Microsoft Update.</span><span class="sxs-lookup"><span data-stu-id="1cedd-134">The notification states that an update is available, even if updates have not yet been released to Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="1cedd-135">Para evitar confusiones, se recomienda elegir esta acción solo cuando las actualizaciones estén disponibles.</span><span class="sxs-lookup"><span data-stu-id="1cedd-135">To avoid confusion, you should choose this action only after updates become available.</span></span>

        
        </div>
    
      - <span data-ttu-id="1cedd-p105">Para permitir que un cliente inicie sesión y muestre un mensaje sobre dónde descargar otra versión de cliente, haga clic en **Permitir con dirección URL**. En este procedimiento, la dirección URL se especifica más adelante.</span><span class="sxs-lookup"><span data-stu-id="1cedd-p105">To allow the client to log on and display a message about where to download another client version, click **Allow with URL**. You specify the URL later in this procedure.</span></span>
    
      - <span data-ttu-id="1cedd-138">Para impedir que el cliente inicie sesión, haga clic en **Bloquear**.</span><span class="sxs-lookup"><span data-stu-id="1cedd-138">To prevent the client from logging on, click **Block**.</span></span>
    
      - <span data-ttu-id="1cedd-139">Para evitar que el cliente inicie sesión y permitir que el cliente reciba actualizaciones de Windows Server Update Service o Microsoft Update, haga clic en **bloquear y actualizar**.</span><span class="sxs-lookup"><span data-stu-id="1cedd-139">To prevent the client from logging on and allow the client to receive updates from Windows Server Update Service or Microsoft Update, click **Block and Upgrade**.</span></span> <span data-ttu-id="1cedd-140">Esta acción solo está disponible cuando se selecciona **OC** del agente del usuario.</span><span class="sxs-lookup"><span data-stu-id="1cedd-140">This action is available only when user agent **OC** is selected.</span></span>
    
      - <span data-ttu-id="1cedd-p107">Para impedir que un cliente inicie sesión y se muestre un mensaje sobre dónde descargar otra versión de cliente, haga clic en **Bloquear con dirección URL**. En este procedimiento, la dirección URL se especifica más adelante.</span><span class="sxs-lookup"><span data-stu-id="1cedd-p107">To prevent the client from logging on and display a message about where to download another client version, click **Block with URL**. You specify the URL later in this procedure.</span></span>

7.  <span data-ttu-id="1cedd-143">(Opcional) Si hizo clic en **Permitir con dirección URL** o **Bloquear con dirección URL** en el paso anterior, escriba la dirección URL de descarga a incluir en el mensaje en **Dirección URL**.</span><span class="sxs-lookup"><span data-stu-id="1cedd-143">(Optional) If you clicked **Allow with URL** or **Block with URL** in the previous step, type the client download URL to include in the message in **URL**.</span></span>

8.  <span data-ttu-id="1cedd-144">Haga clic en **Aceptar** y, a continuación, en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="1cedd-144">Click **OK**, and then click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

