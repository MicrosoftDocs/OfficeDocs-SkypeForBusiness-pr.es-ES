---
title: Crear o modificar una cola en Skype Empresarial
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b9d6366a-839f-4651-a01d-9254546cadeb
description: Cree o modifique una cola de grupo de respuesta en Skype Empresarial Server Telefonía IP empresarial.
ms.openlocfilehash: 9ab714b974601599f591880886a2cf64e35262ba
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49808680"
---
# <a name="create-or-modify-a-queue-in-skype-for-business"></a><span data-ttu-id="78099-103">Crear o modificar una cola en Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="78099-103">Create or modify a queue in Skype for Business</span></span>
 
<span data-ttu-id="78099-104">Cree o modifique una cola de grupo de respuesta en Skype Empresarial Server Telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="78099-104">Create or modify a Response Group queue, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="78099-105">Las colas contienen autores de la llamada hasta que un agente atiende la llamada.</span><span class="sxs-lookup"><span data-stu-id="78099-105">Queues hold callers until an agent answers the call.</span></span> <span data-ttu-id="78099-106">Cuando la aplicación grupo de respuesta busca un agente disponible, busca grupos de agentes en el orden en que los enumera.</span><span class="sxs-lookup"><span data-stu-id="78099-106">When the Response Group application searches for an available agent, it searches agent groups in the order that you list them.</span></span> <span data-ttu-id="78099-107">Puede seleccionar los grupos de agentes asignados a la cola y especificar el comportamiento de la cola, como el límite de número de llamadas que puede contener la cola y cuánto tiempo debe esperar una llamada hasta que un agente la responda.</span><span class="sxs-lookup"><span data-stu-id="78099-107">You can select the agent groups that are assigned to the queue and specify queue behavior, such as limiting the number of calls that the queue can hold and the period of time that a call waits until an agent answers the call.</span></span>
  
<span data-ttu-id="78099-108">Use uno de los procedimientos siguientes para crear o modificar una cola.</span><span class="sxs-lookup"><span data-stu-id="78099-108">Use one of the following procedures to create or modify a queue.</span></span>
  
### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-a-queue"></a><span data-ttu-id="78099-109">Para usar el Panel de control de Skype Empresarial Server para crear o modificar una cola</span><span class="sxs-lookup"><span data-stu-id="78099-109">To use Skype for Business Server Control Panel to create or modify a queue</span></span>

1. <span data-ttu-id="78099-110">Inicie sesión como miembro del grupo RTCUniversalServerAdmins, o como miembro de un rol administrativo predefinido que admita el grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="78099-110">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="78099-111">Si es uno de los administradores delegados del grupo de respuesta para un flujo de trabajo administrado, puede crear o modificar colas de grupo de respuesta y asignarlas a los flujos de trabajo que administra.</span><span class="sxs-lookup"><span data-stu-id="78099-111">If you are one of the delegated Response Group Managers for a managed workflow, you can create or modify response group queues and assign them to the workflows that you manage.</span></span> 
  
2. <span data-ttu-id="78099-112">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="78099-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="78099-113">En la barra de navegación izquierda, haga clic en **Grupos de respuesta** y, a continuación, en **Cola**.</span><span class="sxs-lookup"><span data-stu-id="78099-113">In the left navigation bar, click **Response Groups**, and then click **Queue**.</span></span>
    
4. <span data-ttu-id="78099-114">En la **página** Cola, realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="78099-114">On the **Queue** page, do one of the following:</span></span>
    
   - <span data-ttu-id="78099-115">Para crear una cola nueva, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="78099-115">To create a new queue, click **New**.</span></span> <span data-ttu-id="78099-116">En **Seleccionar un servicio,** escriba parte o todo el nombre del servicio **ApplicationServer** donde desea agregar la cola en el campo de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="78099-116">In **Select a Service**, type part or all of the name of the **ApplicationServer** service where you want to add the queue in the search field.</span></span> <span data-ttu-id="78099-117">En la lista de resultados que aparece, haga clic en el servicio que desea y en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="78099-117">In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
   - <span data-ttu-id="78099-118">Para modificar una cola existente, escriba todo o parte del nombre de la cola en el campo de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="78099-118">To modify an existing queue, type all or part of the queue name in the search field.</span></span> <span data-ttu-id="78099-119">En la lista resultante de colas, haga clic en la cola que desee, haga clic en **Editar** y, a continuación, haga clic en **Mostrar detalles.**</span><span class="sxs-lookup"><span data-stu-id="78099-119">In the resulting list of queues, click the queue that you want, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="78099-120">En **Nombre,** escriba un nombre de identificación para la cola.</span><span class="sxs-lookup"><span data-stu-id="78099-120">In **Name**, type an identifying name for the queue.</span></span>
    
6. <span data-ttu-id="78099-121">En **Descripción**, escriba una descripción para la cola.</span><span class="sxs-lookup"><span data-stu-id="78099-121">In **Description**, type a description for the queue.</span></span>
    
7. <span data-ttu-id="78099-122">En **Grupos,** especifique los grupos que desea asignar a la cola.</span><span class="sxs-lookup"><span data-stu-id="78099-122">In **Groups**, specify the groups you want to assign to the queue.</span></span> <span data-ttu-id="78099-123">Realice una de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="78099-123">Do one of the following:</span></span> 
    
   - <span data-ttu-id="78099-124">Para agregar un grupo a la cola, haga clic en **Seleccionar**.</span><span class="sxs-lookup"><span data-stu-id="78099-124">To add a group to the queue, click **Select**.</span></span> <span data-ttu-id="78099-125">En **el** campo de búsqueda Seleccionar grupos, escriba todo o parte del nombre del grupo de agentes que desea asignar a la cola, haga clic en el grupo de agentes que desee y, a continuación, haga clic en **Aceptar.**</span><span class="sxs-lookup"><span data-stu-id="78099-125">In the **Select Groups** search field, type all or part of the name of the agent group that you want to assign to the queue, click the agent group that you want, and then click **OK**.</span></span>
    
   - <span data-ttu-id="78099-126">Para quitar un grupo de la cola, en la lista de grupos de agentes, haga clic en el grupo que desea quitar y, a continuación, haga clic en **Quitar**.</span><span class="sxs-lookup"><span data-stu-id="78099-126">To remove a group from the queue, in the list of agent groups, click the group that you want to remove, and then click **Remove**.</span></span>
    
   - <span data-ttu-id="78099-127">Para cambiar el orden en que se buscan los agentes, en la lista de grupos de agentes, haga clic en un grupo y, a continuación, haga clic en la flecha arriba o abajo.</span><span class="sxs-lookup"><span data-stu-id="78099-127">To change the order in which agents are searched, in the list of agent groups, click a group, and then click the up arrow or down arrow.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="78099-128">Cuando el servidor busca un agente disponible para la cola, usa el orden de grupo.</span><span class="sxs-lookup"><span data-stu-id="78099-128">When the server searches for an available agent for the queue, it uses group order.</span></span> <span data-ttu-id="78099-129">Es decir, primero se busca en el primer grupo de la lista, seguido del segundo grupo de la lista, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="78099-129">That is, the first group in the list is searched first, followed by the second group in the list, and so on.</span></span> 
  
8. <span data-ttu-id="78099-130">Para especificar un período de tiempo máximo de espera para el autor de una llamada antes de que un agente le atienda, active la casilla **Habilitar tiempo de espera de la cola**.</span><span class="sxs-lookup"><span data-stu-id="78099-130">To specify a maximum period of time for a caller to wait on hold before an agent answers the call, select the **Enable queue time-out** check box, and then do the following:</span></span>
    
    <span data-ttu-id="78099-131">a.</span><span class="sxs-lookup"><span data-stu-id="78099-131">a.</span></span> <span data-ttu-id="78099-132">En **Tiempo de espera (segundos)**, especifique el número máximo de segundos que va a esperar el autor de una llamada para que le atienda un agente.</span><span class="sxs-lookup"><span data-stu-id="78099-132">In **Time-out period (seconds)**, specify the maximum number of seconds a caller waits for an agent to answer the call.</span></span>
    
    <span data-ttu-id="78099-133">b.</span><span class="sxs-lookup"><span data-stu-id="78099-133">b.</span></span> <span data-ttu-id="78099-134">En **Acción de llamada**, seleccione la acción que va a tener lugar cuando se agota el tiempo de espera de una llamada de la forma siguiente:</span><span class="sxs-lookup"><span data-stu-id="78099-134">In **Call Action**, select the action that occurs when a call times out as follows:</span></span>
    
   - <span data-ttu-id="78099-135">Para desconectar la llamada tras el tiempo de espera, haga clic en **Desconectar**.</span><span class="sxs-lookup"><span data-stu-id="78099-135">To disconnect the call after the timeout, click **Disconnect**.</span></span>
    
   - <span data-ttu-id="78099-136">Para reenviar la llamada al correo de voz, haga clic en Reenviar a correo de voz y, a continuación, en el campo Dirección **SIP,** escriba una dirección de correo de voz con el formato sip: *\<username\>* @  *\<domainname\>* (por ejemplo, sip:bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="78099-136">To forward the call to voice mail, click **Forward to voice mail**, and then in the **SIP address** field, type a voice mail address in the format sip: *\<username\>*@ *\<domainname\>* (for example, sip:bob@contoso.com).</span></span>
    
   - <span data-ttu-id="78099-137">Para reenviar la llamada a otro número de teléfono, haga clic en Reenviar a número de teléfono y, a continuación, en el campo Dirección **SIP,** escriba el número de teléfono con el formato sip: *\<number\>* @  *\<domainname\>* (por ejemplo, sip:+14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="78099-137">To forward the call to another telephone number, click **Forward to telephone number**, and then in the **SIP address** field, type the telephone number in the format sip: *\<number\>*@ *\<domainname\>* (for example, sip:+14255550121@contoso.com).</span></span>
    
   - <span data-ttu-id="78099-138">Para reenviar la llamada a otro usuario, haga clic en Reenviar a dirección **SIP** y, a continuación, en el campo dirección **SIP,** escriba el URI del usuario con el formato sip: _\<username\>_ @  _\<domainname\>_ .</span><span class="sxs-lookup"><span data-stu-id="78099-138">To forward the call to another user, click **Forward to SIP address**, and then in the **SIP address** field, type the URI for the user in the format sip: _\<username\>_@ _\<domainname\>_.</span></span>
    
   - <span data-ttu-id="78099-139">Para desviar la llamada a otra cola, haga clic en **Desviar a otra cola** y, a continuación, vaya a la cola que desee utilizar.</span><span class="sxs-lookup"><span data-stu-id="78099-139">To forward the call to another queue, click **Forward to another queue**, and then browse to the queue that you want to use.</span></span>
    
9. <span data-ttu-id="78099-140">Para especificar un número máximo de llamadas que puede contener la cola, active la casilla **Permitir desbordamiento de cola** y siga este procedimiento:</span><span class="sxs-lookup"><span data-stu-id="78099-140">To specify a maximum number of calls that the queue can hold, select the **Enable queue overflow** check box, and then do the following:</span></span>
    
    <span data-ttu-id="78099-141">a.</span><span class="sxs-lookup"><span data-stu-id="78099-141">a.</span></span> <span data-ttu-id="78099-142">En **Número máximo de llamadas**, seleccione el número máximo de llamadas que desea que contenga la cola.</span><span class="sxs-lookup"><span data-stu-id="78099-142">In **Maximum number of calls**, select the maximum number of calls that you want the queue to hold.</span></span> 
    
    <span data-ttu-id="78099-143">b.</span><span class="sxs-lookup"><span data-stu-id="78099-143">b.</span></span> <span data-ttu-id="78099-144">En **Desviar la llamada**, seleccione la llamada que se va a desviar cuando la cola esté llena. **Llamada más reciente** o **Llamada más antigua**.</span><span class="sxs-lookup"><span data-stu-id="78099-144">In **Forward the call**, select which call is to be forwarded when the queue is full: **Newest Call** or **Oldest Call**.</span></span>
    
    <span data-ttu-id="78099-145">c.</span><span class="sxs-lookup"><span data-stu-id="78099-145">c.</span></span> <span data-ttu-id="78099-146">En **Acción de llamada,** seleccione la acción que se produce cuando se alcanza el umbral de desbordamiento de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="78099-146">In **Call action**, select the action that occurs when the overflow threshold is met as follows:</span></span>
    
   - <span data-ttu-id="78099-147">Para desconectar la llamada tras el tiempo de espera, haga clic en **Desconectar**.</span><span class="sxs-lookup"><span data-stu-id="78099-147">To disconnect the call after the timeout, click **Disconnect**.</span></span>
    
   - <span data-ttu-id="78099-148">Para reenviar la llamada al correo de voz, haga clic en Reenviar a correo de voz y, a continuación, en el campo Dirección **SIP,** escriba una dirección de correo de voz con el formato sip: *\<username\>* @  *\<domainname\>* (por ejemplo, sip:bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="78099-148">To forward the call to voice mail, click **Forward to voice mail**, and then in the **SIP address** field, type a voice mail address in the format sip: *\<username\>*@ *\<domainname\>* (for example, sip:bob@contoso.com).</span></span>
    
   - <span data-ttu-id="78099-149">Para reenviar la llamada a otro número de teléfono, haga clic en Reenviar a número de teléfono y, a continuación, en el campo Dirección **SIP,** escriba el número de teléfono con el formato sip: *\<number\>* @  *\<domainname\>* (por ejemplo, sip:+14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="78099-149">To forward the call to another telephone number, click **Forward to telephone number**, and then in the **SIP address** field, type the telephone number in the format sip: *\<number\>*@ *\<domainname\>* (for example, sip:+14255550121@contoso.com).</span></span>
    
   - <span data-ttu-id="78099-150">Para reenviar la llamada a otro usuario, haga clic en Reenviar a dirección **SIP** y, a continuación, en el campo dirección **SIP,** escriba el URI del usuario con el formato sip: _\<username\>_ @  _\<domainname\>_ .</span><span class="sxs-lookup"><span data-stu-id="78099-150">To forward the call to another user, click **Forward to SIP address**, and then in the **SIP address** field, type the URI for the user in the format sip: _\<username\>_@ _\<domainname\>_.</span></span>
    
   - <span data-ttu-id="78099-151">Para desviar la llamada a otra cola, haga clic en **Desviar a otra cola** y, a continuación, vaya a la cola que desee utilizar.</span><span class="sxs-lookup"><span data-stu-id="78099-151">To forward the call to another queue, click **Forward to another queue**, and then browse to the queue that you want to use.</span></span>
    
10. <span data-ttu-id="78099-152">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="78099-152">Click **Commit**.</span></span>
    
### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-queue"></a><span data-ttu-id="78099-153">Para usar el Shell de administración de Skype Empresarial Server para crear o modificar una cola</span><span class="sxs-lookup"><span data-stu-id="78099-153">To use Skype for Business Server Management Shell to create or modify a queue</span></span>

1. <span data-ttu-id="78099-154">Inicie sesión como miembro del grupo RTCUniversalServerAdmins, o como miembro de un rol administrativo predefinido que admita el grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="78099-154">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="78099-155">Si es uno de los administradores delegados de grupos de respuesta para un flujo de trabajo administrado, podrá crear grupos de agentes y colas, y asignar grupos de agentes a las colas.</span><span class="sxs-lookup"><span data-stu-id="78099-155">If you are one of the delegated Response Group Managers for a managed workflow, you will be able to create agent groups and queues, and assign agent groups to queues.</span></span> 
  
2. <span data-ttu-id="78099-156">Inicie el Shell de administración de Skype Empresarial Server: Haga clic en **Inicio,** en Todos los **programas,** **en Skype Empresarial 2015** y, a continuación, en Shell de administración de Skype Empresarial **Server.**</span><span class="sxs-lookup"><span data-stu-id="78099-156">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="78099-157">Cree el mensaje que se reproducirá cuando se alcance el umbral de tiempo de espera de cola y guárdelo en una variable.</span><span class="sxs-lookup"><span data-stu-id="78099-157">Create the prompt to be played when the queue timeout threshold is met, and save it in a variable.</span></span> <span data-ttu-id="78099-158">En la línea de comandos, ejecute:</span><span class="sxs-lookup"><span data-stu-id="78099-158">At the command line, run:</span></span>
    
   ```powershell
   $promptTO = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
   ```

   <span data-ttu-id="78099-159">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="78099-159">For example:</span></span>
    
   ```console
   "All agents are currently busy. Please call back later."
   ```

   > [!NOTE]
   > <span data-ttu-id="78099-160">Para usar un archivo de audio para el mensaje, ejecute el cmdlet **Import-CsRgsAudioFile**.</span><span class="sxs-lookup"><span data-stu-id="78099-160">To use an audio file for the prompt, use the **Import-CsRgsAudioFile** cmdlet.</span></span> <span data-ttu-id="78099-161">Para obtener más información, [consulta Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="78099-161">For details, see [Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps).</span></span> 
  
4. <span data-ttu-id="78099-162">Defina la acción que se va a realizar cuando se alcance el umbral de tiempo de espera de cola y guárdelo en una variable.</span><span class="sxs-lookup"><span data-stu-id="78099-162">Define the action to be taken when the queue timeout threshold is met, and save it in a variable.</span></span> <span data-ttu-id="78099-163">En la línea de comandos, ejecute:</span><span class="sxs-lookup"><span data-stu-id="78099-163">At the command line, run:</span></span>
    
   ```powershell
   $actionTO = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
   ```

   > [!NOTE]
   > <span data-ttu-id="78099-164">Para obtener más información sobre las acciones posibles y su [sintaxis, vea New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="78099-164">For details about possible actions and their syntax, see [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps).</span></span> 
  
    <span data-ttu-id="78099-165">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="78099-165">For example:</span></span>
    
   ```powershell
   $action = New-CsRgsCallAction -Prompt $promptTO -Action Terminate
   ```

5. <span data-ttu-id="78099-166">Cree el mensaje que se reproducirá cuando se alcance el umbral de desbordamiento de cola y guárdelo en una variable.</span><span class="sxs-lookup"><span data-stu-id="78099-166">Create the prompt to be played when the queue overflow threshold is met, and save it in a variable.</span></span> <span data-ttu-id="78099-167">En la línea de comandos, ejecute:</span><span class="sxs-lookup"><span data-stu-id="78099-167">At the command line, run:</span></span>
    
   ```powershell
   $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
   ```

   <span data-ttu-id="78099-168">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="78099-168">For example:</span></span>
    
   ```powershell
   $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "Too many calls are waiting. Please call back later."
   ```

      > [!NOTE]
      > <span data-ttu-id="78099-169">Para usar un archivo de audio para el mensaje, ejecute el cmdlet **Import-CsRgsAudioFile**.</span><span class="sxs-lookup"><span data-stu-id="78099-169">To use an audio file for the prompt, use the **Import-CsRgsAudioFile** cmdlet.</span></span> <span data-ttu-id="78099-170">Para obtener más información, [consulta Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="78099-170">For details, see [Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps).</span></span> 
  
6. <span data-ttu-id="78099-171">Defina la acción que se va a realizar cuando se alcance el umbral de desbordamiento de cola y guárdelo en una variable.</span><span class="sxs-lookup"><span data-stu-id="78099-171">Define the action to be taken when the queue overflow threshold is met, and save it in a variable.</span></span> <span data-ttu-id="78099-172">En la línea de comandos, ejecute:</span><span class="sxs-lookup"><span data-stu-id="78099-172">At the command line, run:</span></span>
    
   ```powershell
   $actionOV = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
   ```

    > [!NOTE]
    > <span data-ttu-id="78099-173">Para obtener más información sobre las acciones posibles y su [sintaxis, vea New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="78099-173">For details about possible actions and their syntax, see [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps).</span></span> 
  
    <span data-ttu-id="78099-174">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="78099-174">For example:</span></span>
    
   ```powershell
   $action = New-CsRgsCallAction -Prompt $promptOV -Action Terminate
   ```

7. <span data-ttu-id="78099-175">Recupere el nombre del servicio para el servicio del grupo de respuesta y asígnelo a una variable.</span><span class="sxs-lookup"><span data-stu-id="78099-175">Retrieve the service name for the Response Group service and assign it to a variable.</span></span> <span data-ttu-id="78099-176">En la línea de comandos, ejecute:</span><span class="sxs-lookup"><span data-stu-id="78099-176">At the command line, run:</span></span>
    
   ```powershell
   $serviceId="service:"+(Get-CSService | ?{$_.Applications -Like "*RGS*"}).ServiceId;
   ```

8. <span data-ttu-id="78099-177">Obtenga la identidad del grupo de agentes que se asignará a la cola.</span><span class="sxs-lookup"><span data-stu-id="78099-177">Get the identity of the agent group to be assigned to the queue.</span></span> <span data-ttu-id="78099-178">En la línea de comandos, ejecute:</span><span class="sxs-lookup"><span data-stu-id="78099-178">At the command line, run:</span></span>
    
   ```powershell
   $agid = (Get-CsRgsAgentGroup -Name "Help Desk").Identity;
   ```

    > [!NOTE]
    > <span data-ttu-id="78099-179">Para obtener más información sobre cómo crear el grupo de agentes, [consulte New-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/new-csrgsagentgroup?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="78099-179">For details about creating the agent group, see [New-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/new-csrgsagentgroup?view=skype-ps)</span></span>
  
9. <span data-ttu-id="78099-180">Cree la cola.</span><span class="sxs-lookup"><span data-stu-id="78099-180">Create the queue.</span></span> <span data-ttu-id="78099-181">En la línea de comandos, ejecute:</span><span class="sxs-lookup"><span data-stu-id="78099-181">At the command line, run:</span></span>
    
   ```powershell
   $q = New-CsRgsQueue -Parent <saved service ID from previous step> -Name "<name of queue>" [-Description "<description for queue>"] [-TimeoutThreshold <# seconds before call times out>] [-TimeoutAction <saved timeout action>] [-OverflowThreshold <# calls queue can hold>] [-OverflowCandidate <call to be acted on when overflow threshold met>] [-OverflowAction <saved overflow action>] [-AgentGroupIDList(<agent group identity>)];
   ```

   <span data-ttu-id="78099-182">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="78099-182">For example:</span></span>
    
   ```powershell
   $q = New-CsRgsQueue -Parent $serviceId -Name "Help Desk" -Description "Contoso Help Desk" -TimeoutThreshold 300 -TimeoutAction $actionTO -OverflowThreshold 10 -OverflowCandidate NewestCall -OverflowAction $actionOV -AgentGroupIDList($agid.Identity;
   ```

10. <span data-ttu-id="78099-183">Confirme que se ha creado la cola.</span><span class="sxs-lookup"><span data-stu-id="78099-183">Confirm that the queue is created.</span></span> <span data-ttu-id="78099-184">Ejecute:</span><span class="sxs-lookup"><span data-stu-id="78099-184">Run:</span></span>
    
    ```powershell
    Get-CsRgsQueue -Name "Help Desk"
    ```

## <a name="see-also"></a><span data-ttu-id="78099-185">Vea también</span><span class="sxs-lookup"><span data-stu-id="78099-185">See also</span></span>

[<span data-ttu-id="78099-186">New-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="78099-186">New-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgsqueue?view=skype-ps)
  
[<span data-ttu-id="78099-187">Set-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="78099-187">Set-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csrgsqueue?view=skype-ps)
  
[<span data-ttu-id="78099-188">New-CsRgsPrompt</span><span class="sxs-lookup"><span data-stu-id="78099-188">New-CsRgsPrompt</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgsprompt?view=skype-ps)
  
[<span data-ttu-id="78099-189">New-CsRgsCallAction</span><span class="sxs-lookup"><span data-stu-id="78099-189">New-CsRgsCallAction</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps)
  
[<span data-ttu-id="78099-190">Get-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="78099-190">Get-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csrgsqueue?view=skype-ps)
  
[<span data-ttu-id="78099-191">Import-CsRgsAudioFile</span><span class="sxs-lookup"><span data-stu-id="78099-191">Import-CsRgsAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)
  
[<span data-ttu-id="78099-192">Remove-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="78099-192">Remove-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csrgsqueue?view=skype-ps)
