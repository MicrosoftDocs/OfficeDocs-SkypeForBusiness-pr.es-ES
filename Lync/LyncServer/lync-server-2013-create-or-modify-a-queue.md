---
title: 'Lync Server 2013: crear o modificar una cola'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a queue
ms:assetid: b9d6366a-839f-4651-a01d-9254546cadeb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205207(v=OCS.15)
ms:contentKeyID: 48185247
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 672752856d7f36e374646782cc36a031c81a9af0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151832"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-queue-in-lync-server-2013"></a><span data-ttu-id="bf9cf-102">Crear o modificar una cola en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bf9cf-102">Create or modify a queue in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bf9cf-103">_**Última modificación del tema:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="bf9cf-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="bf9cf-104">Use uno de los siguientes procedimientos para crear o modificar una cola.</span><span class="sxs-lookup"><span data-stu-id="bf9cf-104">Use one of the following procedures to create or modify a queue.</span></span>

<div>

## <a name="to-use-lync-server-control-panel-to-create-or-modify-a-queue"></a><span data-ttu-id="bf9cf-105">Para usar el panel de control de Lync Server para crear o modificar una cola</span><span class="sxs-lookup"><span data-stu-id="bf9cf-105">To use Lync Server Control Panel to create or modify a queue</span></span>

1.  <span data-ttu-id="bf9cf-106">Inicie sesión como miembro del grupo RTCUniversalServerAdmins, o como miembro de un rol administrativo predefinido que admita el grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="bf9cf-106">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bf9cf-107">Si es uno de los administradores delegados del grupo de respuesta de un flujo de trabajo administrado, puede crear o modificar colas de grupo de respuesta y asignarlas a los flujos de trabajo que administre.</span><span class="sxs-lookup"><span data-stu-id="bf9cf-107">If you are one of the delegated Response Group Managers for a managed workflow, you can create or modify response group queues and assign them to the workflows that you manage.</span></span>

    
    </div>

2.  <span data-ttu-id="bf9cf-108">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bf9cf-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="bf9cf-109">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="bf9cf-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="bf9cf-110">En la barra de navegación izquierda, haga clic en **Grupos de respuesta** y, a continuación, en **Cola**.</span><span class="sxs-lookup"><span data-stu-id="bf9cf-110">In the left navigation bar, click **Response Groups**, and then click **Queue**.</span></span>

4.  <span data-ttu-id="bf9cf-111">En la página **cola** , lleve a cabo uno de los procedimientos siguientes:</span><span class="sxs-lookup"><span data-stu-id="bf9cf-111">On the **Queue** page, do one of the following:</span></span>
    
      - <span data-ttu-id="bf9cf-112">Para crear una nueva cola, haga clic en **nuevo**.</span><span class="sxs-lookup"><span data-stu-id="bf9cf-112">To create a new queue, click **New**.</span></span> <span data-ttu-id="bf9cf-113">En **seleccionar un servicio**, escriba la parte o la totalidad del nombre del servicio **ApplicationServer** en el que desea agregar la cola en el campo de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="bf9cf-113">In **Select a Service**, type part or all of the name of the **ApplicationServer** service where you want to add the queue in the search field.</span></span> <span data-ttu-id="bf9cf-114">En la lista de resultados que aparece, haga clic en el servicio que desea y en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="bf9cf-114">In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
      - <span data-ttu-id="bf9cf-115">Para modificar una cola existente, escriba todo o parte del nombre de la cola en el campo de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="bf9cf-115">To modify an existing queue, type all or part of the queue name in the search field.</span></span> <span data-ttu-id="bf9cf-116">En la lista resultante de colas, haga clic en la cola que desee, haga clic en **Editar**y, a continuación, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="bf9cf-116">In the resulting list of queues, click the queue that you want, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="bf9cf-117">En **nombre**, escriba un nombre de identificación para la cola.</span><span class="sxs-lookup"><span data-stu-id="bf9cf-117">In **Name**, type an identifying name for the queue.</span></span>

6.  <span data-ttu-id="bf9cf-118">En **Descripción**, escriba una descripción para la cola.</span><span class="sxs-lookup"><span data-stu-id="bf9cf-118">In **Description**, type a description for the queue.</span></span>

7.  <span data-ttu-id="bf9cf-119">En **grupos**, especifique los grupos que desea asignar a la cola.</span><span class="sxs-lookup"><span data-stu-id="bf9cf-119">In **Groups**, specify the groups you want to assign to the queue.</span></span> <span data-ttu-id="bf9cf-120">Realice una de las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="bf9cf-120">Do one of the following:</span></span>
    
      - <span data-ttu-id="bf9cf-121">Para agregar un grupo a la cola, haga clic en **seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="bf9cf-121">To add a group to the queue, click **Select**.</span></span> <span data-ttu-id="bf9cf-122">En el campo de búsqueda **seleccionar grupos** , escriba todo o parte del nombre del grupo de agentes que desee asignar a la cola, haga clic en el grupo de agentes que desee y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="bf9cf-122">In the **Select Groups** search field, type all or part of the name of the agent group that you want to assign to the queue, click the agent group that you want, and then click **OK**.</span></span>
    
      - <span data-ttu-id="bf9cf-123">Para quitar un grupo de la cola, en la lista de grupos de agentes, haga clic en el grupo que desea quitar y, a continuación, haga clic en **quitar**.</span><span class="sxs-lookup"><span data-stu-id="bf9cf-123">To remove a group from the queue, in the list of agent groups, click the group that you want to remove, and then click **Remove**.</span></span>
    
      - <span data-ttu-id="bf9cf-124">Para cambiar el orden en el que se buscan los agentes, en la lista de grupos de agentes, haga clic en un grupo y, a continuación, haga clic en la flecha hacia arriba o hacia abajo.</span><span class="sxs-lookup"><span data-stu-id="bf9cf-124">To change the order in which agents are searched, in the list of agent groups, click a group, and then click the up arrow or down arrow.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="bf9cf-125">Cuando el servidor busca un agente disponible para la cola, utiliza el orden de grupo.</span><span class="sxs-lookup"><span data-stu-id="bf9cf-125">When the server searches for an available agent for the queue, it uses group order.</span></span> <span data-ttu-id="bf9cf-126">Es decir, se busca primero en el primer grupo de la lista, después en el segundo grupo de la lista y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="bf9cf-126">That is, the first group in the list is searched first, followed by the second group in the list, and so on.</span></span>

        
        </div>

8.  <span data-ttu-id="bf9cf-127">Para especificar un período de tiempo máximo de espera para el autor de una llamada antes de que un agente le atienda, active la casilla **Habilitar tiempo de espera de la cola**.</span><span class="sxs-lookup"><span data-stu-id="bf9cf-127">To specify a maximum period of time for a caller to wait on hold before an agent answers the call, select the **Enable queue time-out** check box, and then do the following:</span></span>
    
    1.  <span data-ttu-id="bf9cf-128">En **Tiempo de espera (segundos)**, especifique el número máximo de segundos que va a esperar el autor de una llamada para que le atienda un agente.</span><span class="sxs-lookup"><span data-stu-id="bf9cf-128">In **Time-out period (seconds)**, specify the maximum number of seconds a caller waits for an agent to answer the call.</span></span>
    
    2.  <span data-ttu-id="bf9cf-129">En **Acción de llamada**, seleccione la acción que va a tener lugar cuando se agota el tiempo de espera de una llamada de la forma siguiente:</span><span class="sxs-lookup"><span data-stu-id="bf9cf-129">In **Call Action**, select the action that occurs when a call times out as follows:</span></span>
    
    <!-- end list -->
    
      - <span data-ttu-id="bf9cf-130">Para desconectar la llamada tras el tiempo de espera, haga clic en **Desconectar**.</span><span class="sxs-lookup"><span data-stu-id="bf9cf-130">To disconnect the call after the timeout, click **Disconnect**.</span></span>
    
      - <span data-ttu-id="bf9cf-131">Para reenviar la llamada al correo de voz, haga clic en **desviar a correo de voz**y, a continuación, en el campo **dirección SIP** , escriba una\<dirección\>@\<de\> correo de voz con el formato SIP: username domainname (por ejemplo, SIP:Bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="bf9cf-131">To forward the call to voice mail, click **Forward to voice mail**, and then in the **SIP address** field, type a voice mail address in the format sip:\<username\>@\<domainname\> (for example, sip:bob@contoso.com).</span></span>
    
      - <span data-ttu-id="bf9cf-132">Para reenviar la llamada a otro número de teléfono, haga clic en **desviar a número de teléfono**y, a continuación, en el campo **dirección SIP** , escriba\<el\>@\<número\> de teléfono con el formato SIP: Number domainname (por ejemplo, SIP:+14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="bf9cf-132">To forward the call to another telephone number, click **Forward to telephone number**, and then in the **SIP address** field, type the telephone number in the format sip:\<number\>@\<domainname\> (for example, sip:+14255550121@contoso.com).</span></span>
    
      - <span data-ttu-id="bf9cf-133">Para reenviar la llamada a otro usuario, haga clic en **desviar a dirección SIP**y, a continuación, en el campo **dirección SIP** , escriba el URI del usuario\<con\>@\<el\>formato SIP: nombreusuario nombredominio.</span><span class="sxs-lookup"><span data-stu-id="bf9cf-133">To forward the call to another user, click **Forward to SIP address**, and then in the **SIP address** field, type the URI for the user in the format sip:\<username\>@\<domainname\>.</span></span>
    
      - <span data-ttu-id="bf9cf-134">Para desviar la llamada a otra cola, haga clic en **Desviar a otra cola** y, a continuación, vaya a la cola que desee utilizar.</span><span class="sxs-lookup"><span data-stu-id="bf9cf-134">To forward the call to another queue, click **Forward to another queue**, and then browse to the queue that you want to use.</span></span>

9.  <span data-ttu-id="bf9cf-135">Para especificar un número máximo de llamadas que puede contener la cola, active la casilla **Permitir desbordamiento de cola** y siga este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="bf9cf-135">To specify a maximum number of calls that the queue can hold, select the **Enable queue overflow** check box, and then do the following:</span></span>
    
    1.  <span data-ttu-id="bf9cf-136">En **Número máximo de llamadas**, seleccione el número máximo de llamadas que desea que contenga la cola.</span><span class="sxs-lookup"><span data-stu-id="bf9cf-136">In **Maximum number of calls**, select the maximum number of calls that you want the queue to hold.</span></span>
    
    2.  <span data-ttu-id="bf9cf-137">En **Desviar la llamada**, seleccione la llamada que se va a desviar cuando la cola esté llena. **Llamada más reciente** o **Llamada más antigua**.</span><span class="sxs-lookup"><span data-stu-id="bf9cf-137">In **Forward the call**, select which call is to be forwarded when the queue is full: **Newest Call** or **Oldest Call**.</span></span>
    
    3.  <span data-ttu-id="bf9cf-138">En **acción de llamada**, seleccione la acción que debe producirse cuando se alcance el umbral de desbordamiento de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="bf9cf-138">In **Call action**, select the action that occurs when the overflow threshold is met as follows:</span></span>
    
    <!-- end list -->
    
      - <span data-ttu-id="bf9cf-139">Para desconectar la llamada tras el tiempo de espera, haga clic en **Desconectar**.</span><span class="sxs-lookup"><span data-stu-id="bf9cf-139">To disconnect the call after the timeout, click **Disconnect**.</span></span>
    
      - <span data-ttu-id="bf9cf-140">Para reenviar la llamada al correo de voz, haga clic en **desviar a correo de voz**y, a continuación, en el campo **dirección SIP** , escriba una\<dirección\>@\<de\> correo de voz con el formato SIP: username domainname (por ejemplo, SIP:Bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="bf9cf-140">To forward the call to voice mail, click **Forward to voice mail**, and then in the **SIP address** field, type a voice mail address in the format sip:\<username\>@\<domainname\> (for example, sip:bob@contoso.com).</span></span>
    
      - <span data-ttu-id="bf9cf-141">Para reenviar la llamada a otro número de teléfono, haga clic en **desviar a número de teléfono**y, a continuación, en el campo **dirección SIP** , escriba\<el\>@\<número\> de teléfono con el formato SIP: Number domainname (por ejemplo, SIP:+14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="bf9cf-141">To forward the call to another telephone number, click **Forward to telephone number**, and then in the **SIP address** field, type the telephone number in the format sip:\<number\>@\<domainname\> (for example, sip:+14255550121@contoso.com).</span></span>
    
      - <span data-ttu-id="bf9cf-142">Para reenviar la llamada a otro usuario, haga clic en **desviar a dirección SIP**y, a continuación, en el campo **dirección SIP** , escriba el URI del usuario\<con\>@\<el\>formato SIP: nombreusuario nombredominio.</span><span class="sxs-lookup"><span data-stu-id="bf9cf-142">To forward the call to another user, click **Forward to SIP address**, and then in the **SIP address** field, type the URI for the user in the format sip:\<username\>@\<domainname\>.</span></span>
    
      - <span data-ttu-id="bf9cf-143">Para desviar la llamada a otra cola, haga clic en **Desviar a otra cola** y, a continuación, vaya a la cola que desee utilizar.</span><span class="sxs-lookup"><span data-stu-id="bf9cf-143">To forward the call to another queue, click **Forward to another queue**, and then browse to the queue that you want to use.</span></span>

10. <span data-ttu-id="bf9cf-144">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="bf9cf-144">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-a-queue"></a><span data-ttu-id="bf9cf-145">Para usar Windows PowerShell para crear o modificar una cola</span><span class="sxs-lookup"><span data-stu-id="bf9cf-145">To use Windows PowerShell to create or modify a queue</span></span>

1.  <span data-ttu-id="bf9cf-146">Inicie sesión como miembro del grupo RTCUniversalServerAdmins, o como miembro de un rol administrativo predefinido que admita el grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="bf9cf-146">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bf9cf-147">Si es uno de los administradores del grupo de respuesta delegado de un flujo de trabajo administrado, podrá crear colas y grupos de agentes, y asignar grupos de agentes a las colas.</span><span class="sxs-lookup"><span data-stu-id="bf9cf-147">If you are one of the delegated Response Group Managers for a managed workflow, you will be able to create agent groups and queues, and assign agent groups to queues.</span></span>

    
    </div>

2.  <span data-ttu-id="bf9cf-148">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="bf9cf-148">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="bf9cf-149">Cree el mensaje que se reproducirá cuando se alcance el umbral de tiempo de espera de la cola y guárdelo en una variable.</span><span class="sxs-lookup"><span data-stu-id="bf9cf-149">Create the prompt to be played when the queue timeout threshold is met, and save it in a variable.</span></span> <span data-ttu-id="bf9cf-150">En la línea de comandos, ejecute:</span><span class="sxs-lookup"><span data-stu-id="bf9cf-150">At the command line, run:</span></span>
    
        $promptTO = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
    
    <span data-ttu-id="bf9cf-151">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bf9cf-151">For example:</span></span>
    
        "All agents are currently busy. Please call back later."
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bf9cf-152">Para usar un archivo de audio para el mensaje, ejecute el cmdlet <STRONG>Import-CsRgsAudioFile</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="bf9cf-152">To use an audio file for the prompt, use the <STRONG>Import-CsRgsAudioFile</STRONG> cmdlet.</span></span> <span data-ttu-id="bf9cf-153">Para obtener más información, consulte <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</A>.</span><span class="sxs-lookup"><span data-stu-id="bf9cf-153">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</A>.</span></span>

    
    </div>

4.  <span data-ttu-id="bf9cf-154">Defina la acción que se llevará a cabo cuando se alcance el umbral de tiempo de espera de la cola y guárdela en una variable.</span><span class="sxs-lookup"><span data-stu-id="bf9cf-154">Define the action to be taken when the queue timeout threshold is met, and save it in a variable.</span></span> <span data-ttu-id="bf9cf-155">En la línea de comandos, ejecute:</span><span class="sxs-lookup"><span data-stu-id="bf9cf-155">At the command line, run:</span></span>
    
        $actionTO = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bf9cf-156">Para obtener más información sobre las posibles acciones y su sintaxis, consulte <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction">New-CsRgsCallAction</A>.</span><span class="sxs-lookup"><span data-stu-id="bf9cf-156">For details about possible actions and their syntax, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction">New-CsRgsCallAction</A>.</span></span>

    
    </div>
    
    <span data-ttu-id="bf9cf-157">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bf9cf-157">For example:</span></span>
    
        $action = New-CsRgsCallAction -Prompt $promptTO -Action Terminate

5.  <span data-ttu-id="bf9cf-158">Cree el mensaje que se reproducirá cuando se alcance el umbral de desbordamiento de la cola y guárdelo en una variable.</span><span class="sxs-lookup"><span data-stu-id="bf9cf-158">Create the prompt to be played when the queue overflow threshold is met, and save it in a variable.</span></span> <span data-ttu-id="bf9cf-159">En la línea de comandos, ejecute:</span><span class="sxs-lookup"><span data-stu-id="bf9cf-159">At the command line, run:</span></span>
    
        $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
    
    <span data-ttu-id="bf9cf-160">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bf9cf-160">For example:</span></span>
    
        $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "Too many calls are waiting. Please call back later."
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bf9cf-161">Para usar un archivo de audio para el mensaje, ejecute el cmdlet <STRONG>Import-CsRgsAudioFile</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="bf9cf-161">To use an audio file for the prompt, use the <STRONG>Import-CsRgsAudioFile</STRONG> cmdlet.</span></span> <span data-ttu-id="bf9cf-162">Para obtener más información, consulte <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</A>.</span><span class="sxs-lookup"><span data-stu-id="bf9cf-162">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-CsRgsAudioFile</A>.</span></span>

    
    </div>

6.  <span data-ttu-id="bf9cf-163">Defina la acción que se llevará a cabo cuando se alcance el umbral de desbordamiento de la cola y guárdelo en una variable.</span><span class="sxs-lookup"><span data-stu-id="bf9cf-163">Define the action to be taken when the queue overflow threshold is met, and save it in a variable.</span></span> <span data-ttu-id="bf9cf-164">En la línea de comandos, ejecute:</span><span class="sxs-lookup"><span data-stu-id="bf9cf-164">At the command line, run:</span></span>
    
        $actionOV = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bf9cf-165">Para obtener más información sobre las posibles acciones y su sintaxis, consulte <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction">New-CsRgsCallAction</A>.</span><span class="sxs-lookup"><span data-stu-id="bf9cf-165">For details about possible actions and their syntax, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction">New-CsRgsCallAction</A>.</span></span>

    
    </div>
    
    <span data-ttu-id="bf9cf-166">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bf9cf-166">For example:</span></span>
    
        $action = New-CsRgsCallAction -Prompt $promptOV -Action Terminate

7.  <span data-ttu-id="bf9cf-167">Recupere el nombre del servicio para el servicio del grupo de respuesta y asígnelo a una variable.</span><span class="sxs-lookup"><span data-stu-id="bf9cf-167">Retrieve the service name for the Response Group service and assign it to a variable.</span></span> <span data-ttu-id="bf9cf-168">En la línea de comandos, ejecute:</span><span class="sxs-lookup"><span data-stu-id="bf9cf-168">At the command line, run:</span></span>
    
        $serviceId="service:"+(Get-CSService | ?{$_.Applications -Like "*RGS*"}).ServiceId;

8.  <span data-ttu-id="bf9cf-169">Obtiene la identidad del grupo de agentes que se va a asignar a la cola.</span><span class="sxs-lookup"><span data-stu-id="bf9cf-169">Get the identity of the agent group to be assigned to the queue.</span></span> <span data-ttu-id="bf9cf-170">En la línea de comandos, ejecute:</span><span class="sxs-lookup"><span data-stu-id="bf9cf-170">At the command line, run:</span></span>
    
        $agid = (Get-CsRgsAgentGroup -Name "Help Desk").Identity;
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bf9cf-171">Para obtener más información sobre cómo crear el grupo de agentes, consulte <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsAgentGroup">New-CsRgsAgentGroup</A></span><span class="sxs-lookup"><span data-stu-id="bf9cf-171">For details about creating the agent group, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsAgentGroup">New-CsRgsAgentGroup</A></span></span>

    
    </div>

9.  <span data-ttu-id="bf9cf-172">Cree la cola.</span><span class="sxs-lookup"><span data-stu-id="bf9cf-172">Create the queue.</span></span> <span data-ttu-id="bf9cf-173">En la línea de comandos, ejecute:</span><span class="sxs-lookup"><span data-stu-id="bf9cf-173">At the command line, run:</span></span>
    
        $q = New-CsRgsQueue -Parent <saved service ID from previous step> -Name "<name of queue>" [-Description "<description for queue>"] [-TimeoutThreshold <# seconds before call times out>] [-TimeoutAction <saved timeout action>] [-OverflowThreshold <# calls queue can hold>] [-OverflowCandidate <call to be acted on when overflow threshold met>] [-OverflowAction <saved overflow action>] [-AgentGroupIDList(<agent group identity>)];
    
    <span data-ttu-id="bf9cf-174">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="bf9cf-174">For example:</span></span>
    
        $q = New-CsRgsQueue -Parent $serviceId -Name "Help Desk" -Description "Contoso Help Desk" -TimeoutThreshold 300 -TimeoutAction $actionTO -OverflowThreshold 10 -OverflowCandidate NewestCall -OverflowAction $actionOV -AgentGroupIDList($agid.Identity;

10. <span data-ttu-id="bf9cf-175">Confirme que se ha creado la cola.</span><span class="sxs-lookup"><span data-stu-id="bf9cf-175">Confirm that the queue is created.</span></span> <span data-ttu-id="bf9cf-176">Realizar</span><span class="sxs-lookup"><span data-stu-id="bf9cf-176">Run:</span></span>
    
        Get-CsRgsQueue -Name "Help Desk"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bf9cf-177">Vea también</span><span class="sxs-lookup"><span data-stu-id="bf9cf-177">See Also</span></span>


[<span data-ttu-id="bf9cf-178">New-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="bf9cf-178">New-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsQueue)  
[<span data-ttu-id="bf9cf-179">Set-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="bf9cf-179">Set-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsQueue)  
[<span data-ttu-id="bf9cf-180">New-CsRgsPrompt</span><span class="sxs-lookup"><span data-stu-id="bf9cf-180">New-CsRgsPrompt</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsPrompt)  
[<span data-ttu-id="bf9cf-181">New-CsRgsCallAction</span><span class="sxs-lookup"><span data-stu-id="bf9cf-181">New-CsRgsCallAction</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction)  
[<span data-ttu-id="bf9cf-182">Get-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="bf9cf-182">Get-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsQueue)  
[<span data-ttu-id="bf9cf-183">Import-CsRgsAudioFile</span><span class="sxs-lookup"><span data-stu-id="bf9cf-183">Import-CsRgsAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile)  
[<span data-ttu-id="bf9cf-184">Remove-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="bf9cf-184">Remove-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsRgsQueue)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

