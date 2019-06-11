---
title: 'Lync Server 2013: crear o modificar una nueva regla de directiva de versión de cliente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a new client version policy rule
ms:assetid: 6f879d99-8401-41e0-a562-195c890d63ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898478(v=OCS.15)
ms:contentKeyID: 50873758
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa5f9074f928a9bec20ca275487806b790a0226b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835785"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-new-client-version-policy-rule-in-lync-server-2013"></a><span data-ttu-id="7e811-102">Crear o modificar una nueva regla de directiva de versión de cliente en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7e811-102">Create or modify a new client version policy rule in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7e811-103">_**Última modificación del tema:** 2013-01-21_</span><span class="sxs-lookup"><span data-stu-id="7e811-103">_**Topic Last Modified:** 2013-01-21_</span></span>

<span data-ttu-id="7e811-104">Las reglas de directiva de versión de cliente definen las acciones que se deben realizar cuando los usuarios intentan iniciar sesión con clientes específicos y versiones de cliente.</span><span class="sxs-lookup"><span data-stu-id="7e811-104">Client version policy rules define the actions that should be taken when users attempt to log on with specific clients and client versions.</span></span> <span data-ttu-id="7e811-105">Puede crear o modificar reglas individuales para una directiva de versión de cliente desde el panel de control de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7e811-105">You can create or modify individual rules for a client version policy from Lync Server 2013 Control Panel.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="7e811-106">Las reglas se muestran en orden de prioridad.</span><span class="sxs-lookup"><span data-stu-id="7e811-106">Rules are listed in order of precedence.</span></span> <span data-ttu-id="7e811-107">Por ejemplo, si tiene una regla que permite a los clientes que ejecutan la versión 1,5 se conecte, seguido de una regla que bloquea los clientes que ejecutan una versión anterior a la 2,0, la primera regla tiene prioridad y los clientes que ejecutan la versión 1,5 pueden conectarse.</span><span class="sxs-lookup"><span data-stu-id="7e811-107">For example, if you have a rule that allows clients running version 1.5 to connect, followed by a rule that blocks clients running a version earlier than 2.0, the first rule takes precedence, and clients running version 1.5 are allowed to connect.</span></span>



</div>

<div>

## <a name="to-create-or-modify-client-version-policy-rules-with-lync-server-control-panel"></a><span data-ttu-id="7e811-108">Para crear o modificar reglas de directiva de versión de cliente con el panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="7e811-108">To create or modify client version policy rules with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="7e811-109">[Cree o modifique una nueva Directiva de versión de cliente en Lync server 2013 con el](lync-server-2013-create-or-modify-a-new-client-version-policy.md) panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7e811-109">[Create or modify a new client version policy in Lync Server 2013](lync-server-2013-create-or-modify-a-new-client-version-policy.md) with Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="7e811-110">En la página **Editar Directiva de versión del cliente** , realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="7e811-110">On the **Edit Client Version Policy** page, do one of the following:</span></span>
    
      - <span data-ttu-id="7e811-111">Haga clic en **nuevo** para crear una nueva regla de versión de cliente.</span><span class="sxs-lookup"><span data-stu-id="7e811-111">Click **New** to create a new client version rule.</span></span>
    
      - <span data-ttu-id="7e811-112">Haga clic en uno de los tipos de cliente definidos en la lista y, a continuación, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="7e811-112">Click one of the defined client types in the list, and then click **Show details**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7e811-113">Puede usar caracteres comodín para indicar el tipo de cliente.</span><span class="sxs-lookup"><span data-stu-id="7e811-113">You can use wildcards to indicate the client type.</span></span>

    
    </div>

3.  <span data-ttu-id="7e811-114">En **agente de usuario**, seleccione un tipo de cliente.</span><span class="sxs-lookup"><span data-stu-id="7e811-114">In **User agent**, select a client type.</span></span>

4.  <span data-ttu-id="7e811-115">En **número de versión**, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7e811-115">Under **Version number**, do the following:</span></span>
    
      - <span data-ttu-id="7e811-116">En **versión principal**, escriba el número que corresponde a la versión principal del cliente.</span><span class="sxs-lookup"><span data-stu-id="7e811-116">In **Major version**, type the number that corresponds to the major release of the client.</span></span>
    
      - <span data-ttu-id="7e811-117">En **versión secundaria**, escriba el número que corresponde a la versión secundaria del cliente.</span><span class="sxs-lookup"><span data-stu-id="7e811-117">In **Minor version**, type the number that corresponds to the minor release of the client.</span></span>
    
      - <span data-ttu-id="7e811-118">En **crear**, escriba el número que corresponde a la versión principal y secundaria del cliente.</span><span class="sxs-lookup"><span data-stu-id="7e811-118">In **Build**, type the number that corresponds to the major and minor release of the client.</span></span>
    
      - <span data-ttu-id="7e811-119">En **Actualizar**, escriba el número que corresponde a la versión actualizada del cliente.</span><span class="sxs-lookup"><span data-stu-id="7e811-119">In **Update**, type the number that corresponds to the updated release of the client.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7e811-120">Puede usar caracteres comodín para indicar el número de versión del cliente.</span><span class="sxs-lookup"><span data-stu-id="7e811-120">You can use wildcards to indicate the client version number.</span></span>

    
    </div>

5.  <span data-ttu-id="7e811-121">Para especificar la operación correspondiente a la versión del cliente que especificó en los pasos anteriores, en **operación de comparación**, haga clic en una de las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="7e811-121">To specify the matching operation for the client version you specified in the preceding steps, in **Comparison operation**, click one of the following:</span></span>
    
      - <span data-ttu-id="7e811-122">**Igual que**</span><span class="sxs-lookup"><span data-stu-id="7e811-122">**Same as**</span></span>
    
      - <span data-ttu-id="7e811-123">**No es**</span><span class="sxs-lookup"><span data-stu-id="7e811-123">**Is not**</span></span>
    
      - <span data-ttu-id="7e811-124">**Anterior a**</span><span class="sxs-lookup"><span data-stu-id="7e811-124">**Newer than**</span></span>
    
      - <span data-ttu-id="7e811-125">**Anterior a o igual que**</span><span class="sxs-lookup"><span data-stu-id="7e811-125">**Newer than or same as**</span></span>
    
      - <span data-ttu-id="7e811-126">**Posterior a**</span><span class="sxs-lookup"><span data-stu-id="7e811-126">**Older than**</span></span>
    
      - <span data-ttu-id="7e811-127">**Posterior a o igual que**</span><span class="sxs-lookup"><span data-stu-id="7e811-127">**Older than or same as**</span></span>

6.  <span data-ttu-id="7e811-128">Para especificar la acción que se realizará cuando se cumplan los criterios de los pasos anteriores, haga clic en \*\*\*\* una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="7e811-128">To specify the action to perform when the criteria in the preceding steps are met, click one of the following in **Action**:</span></span>
    
      - <span data-ttu-id="7e811-129">Para permitir que el cliente inicie sesión, haga clic en **permitir**.</span><span class="sxs-lookup"><span data-stu-id="7e811-129">To allow the client to log on, click **Allow**.</span></span>
    
      - <span data-ttu-id="7e811-130">Para permitir que el cliente inicie sesión y reciba actualizaciones de Windows Server Update Services o Microsoft Update, haga clic en **permitir y actualizar**.</span><span class="sxs-lookup"><span data-stu-id="7e811-130">To allow the client to log on and receive updates from Windows Server Update Service or Microsoft Update, click **Allow and Upgrade**.</span></span> <span data-ttu-id="7e811-131">Esta acción solo está disponible cuando se selecciona **OC** como agente del usuario.</span><span class="sxs-lookup"><span data-stu-id="7e811-131">This action is available only when user agent **OC** is selected.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="7e811-132">Si selecciona esta acción, una notificación aparecerá la próxima vez que los usuarios inicien sesión en Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="7e811-132">Selecting this action causes a notification to appear the next time users sign in to Lync 2013.</span></span> <span data-ttu-id="7e811-133">La notificación comunica que hay una actualización disponible, aun cuando Windows Server Update Service o Microsoft Update todavía no la hayan publicado.</span><span class="sxs-lookup"><span data-stu-id="7e811-133">The notification states that an update is available, even if updates have not yet been released to Windows Server Update Service or Microsoft Update.</span></span> <span data-ttu-id="7e811-134">Para evitar confusiones, recomendamos elegir esta acción solo cuando las actualizaciones estén disponibles.</span><span class="sxs-lookup"><span data-stu-id="7e811-134">To avoid confusion, you should choose this action only after updates become available.</span></span>

        
        </div>
    
      - <span data-ttu-id="7e811-135">Para permitir que el cliente inicie sesión y muestre un mensaje sobre dónde Descargar otra versión del cliente, haga clic en **permitir con la dirección URL**.</span><span class="sxs-lookup"><span data-stu-id="7e811-135">To allow the client to log on and display a message about where to download another client version, click **Allow with URL**.</span></span> <span data-ttu-id="7e811-136">La dirección URL se especifica más adelante en este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="7e811-136">You specify the URL later in this procedure.</span></span>
    
      - <span data-ttu-id="7e811-137">Para evitar que el cliente inicie sesión, haga clic en **bloquear**.</span><span class="sxs-lookup"><span data-stu-id="7e811-137">To prevent the client from logging on, click **Block**.</span></span>
    
      - <span data-ttu-id="7e811-138">Para evitar que el cliente inicie sesión y permitir que el cliente reciba actualizaciones de Windows Server Update Services o Microsoft Update, haga clic en **bloquear y actualizar**.</span><span class="sxs-lookup"><span data-stu-id="7e811-138">To prevent the client from logging on and allow the client to receive updates from Windows Server Update Service or Microsoft Update, click **Block and Upgrade**.</span></span> <span data-ttu-id="7e811-139">Esta acción solo está disponible cuando se selecciona **OC** como agente del usuario.</span><span class="sxs-lookup"><span data-stu-id="7e811-139">This action is available only when user agent **OC** is selected.</span></span>
    
      - <span data-ttu-id="7e811-140">Para evitar que el cliente inicie sesión y muestre un mensaje sobre dónde Descargar otra versión del cliente, haga clic en **bloquear con dirección URL**.</span><span class="sxs-lookup"><span data-stu-id="7e811-140">To prevent the client from logging on and display a message about where to download another client version, click **Block with URL**.</span></span> <span data-ttu-id="7e811-141">La dirección URL se especifica más adelante en este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="7e811-141">You specify the URL later in this procedure.</span></span>

7.  <span data-ttu-id="7e811-142">Faculta Si hizo clic en **permitir con URL** o **bloque con dirección URL** en el paso anterior, escriba la dirección URL de descarga del cliente que se incluirá en el mensaje de la **dirección URL**.</span><span class="sxs-lookup"><span data-stu-id="7e811-142">(Optional) If you clicked **Allow with URL** or **Block with URL** in the previous step, type the client download URL to include in the message in **URL**.</span></span>

8.  <span data-ttu-id="7e811-143">Haga clic en **Aceptar**y, a continuación, en **Ejecutar**.</span><span class="sxs-lookup"><span data-stu-id="7e811-143">Click **OK**, and then click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

