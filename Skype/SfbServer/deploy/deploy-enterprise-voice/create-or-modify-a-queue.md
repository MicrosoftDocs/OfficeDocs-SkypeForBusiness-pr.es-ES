---
title: Crear o modificar una cola en Skype Empresarial 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b9d6366a-839f-4651-a01d-9254546cadeb
description: Crear o modificar una cola de grupo de respuesta, en Skype para Business Server Enterprise Voice.
ms.openlocfilehash: d959ca00829200ac8ad54168d72ca108adabb39f
ms.sourcegitcommit: a5b8b0a1e5ae5eb718e296ca6df6687368ee9174
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2018
ms.locfileid: "19500987"
---
# <a name="create-or-modify-a-queue-in-skype-for-business-2015"></a><span data-ttu-id="aabf3-103">Crear o modificar una cola en Skype Empresarial 2015</span><span class="sxs-lookup"><span data-stu-id="aabf3-103">Create or modify a queue in Skype for Business 2015</span></span>
 
<span data-ttu-id="aabf3-104">Crear o modificar una cola de grupo de respuesta, en Skype para Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="aabf3-104">Create or modify a Response Group queue, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="aabf3-105">Las colas contienen autores de la llamada hasta que un agente atiende la llamada.</span><span class="sxs-lookup"><span data-stu-id="aabf3-105">Queues hold callers until an agent answers the call.</span></span> <span data-ttu-id="aabf3-106">Cuando la aplicación de grupo de respuesta busca un agente disponible, busca grupos de agentes en el orden en que éstos se enumeran.</span><span class="sxs-lookup"><span data-stu-id="aabf3-106">When the Response Group application searches for an available agent, it searches agent groups in the order that you list them.</span></span> <span data-ttu-id="aabf3-107">Puede seleccionar los grupos de agentes asignados a la cola y especificar el comportamiento de la cola, como el límite de número de llamadas que puede contener la cola y cuánto tiempo debe esperar una llamada hasta que un agente la responda.</span><span class="sxs-lookup"><span data-stu-id="aabf3-107">You can select the agent groups that are assigned to the queue and specify queue behavior, such as limiting the number of calls that the queue can hold and the period of time that a call waits until an agent answers the call.</span></span>
  
<span data-ttu-id="aabf3-108">Use uno de los procedimientos siguientes para crear o modificar una cola.</span><span class="sxs-lookup"><span data-stu-id="aabf3-108">Use one of the following procedures to create or modify a queue.</span></span>
  
### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-a-queue"></a><span data-ttu-id="aabf3-109">Usar Skype para el Panel de Control de servidor empresarial para crear o modificar una cola</span><span class="sxs-lookup"><span data-stu-id="aabf3-109">To use Skype for Business Server Control Panel to create or modify a queue</span></span>

1. <span data-ttu-id="aabf3-110">Inicie sesión como miembro del grupo RTCUniversalServerAdmins o como miembro de uno de los roles administrativos predefinidos que admiten el Grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="aabf3-110">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="aabf3-111">Si es uno de los administradores delegados del grupo de respuesta de un flujo de trabajo administrado, puede crear o modificar colas de grupo de respuesta y asignarlas a los flujos de trabajo que administre.</span><span class="sxs-lookup"><span data-stu-id="aabf3-111">If you are one of the delegated Response Group Managers for a managed workflow, you can create or modify response group queues and assign them to the workflows that you manage.</span></span> 
  
2. <span data-ttu-id="aabf3-112">Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.</span><span class="sxs-lookup"><span data-stu-id="aabf3-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="aabf3-113">En la barra de navegación izquierda, haga clic en **Grupos de respuesta** y luego en **Cola**.</span><span class="sxs-lookup"><span data-stu-id="aabf3-113">In the left navigation bar, click **Response Groups**, and then click **Queue**.</span></span>
    
4. <span data-ttu-id="aabf3-114">En la página **Cola**, lleve a cabo alguna de estas acciones:</span><span class="sxs-lookup"><span data-stu-id="aabf3-114">On the **Queue** page, do one of the following:</span></span>
    
   - <span data-ttu-id="aabf3-115">Para crear una cola nueva, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="aabf3-115">To create a new queue, click **New**.</span></span> <span data-ttu-id="aabf3-116">En **Seleccionar un servicio**, escriba parte o todo el nombre del servicio **ApplicationServer** donde desea agregar la cola en el campo de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="aabf3-116">In **Select a Service**, type part or all of the name of the **ApplicationServer** service where you want to add the queue in the search field.</span></span> <span data-ttu-id="aabf3-117">En la lista de servicios que aparezca, haga clic en el servicio que desea y en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="aabf3-117">In the resulting list of services, click the service that you want, and then click **OK**.</span></span>
    
   - <span data-ttu-id="aabf3-p103">Para modificar una cola actual, escriba total o parcialmente el nombre de la cola en el campo de búsqueda. En la lista de colas que aparezca, haga clic sucesivamente en la cola que desea, **Editar** y **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="aabf3-p103">To modify an existing queue, type all or part of the queue name in the search field. In the resulting list of queues, click the queue that you want, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="aabf3-120">En **Nombre**, escriba un nombre de identificación para la cola.</span><span class="sxs-lookup"><span data-stu-id="aabf3-120">In **Name**, type an identifying name for the queue.</span></span>
    
6. <span data-ttu-id="aabf3-121">En **Descripción**, escriba la descripción de la cola.</span><span class="sxs-lookup"><span data-stu-id="aabf3-121">In **Description**, type a description for the queue.</span></span>
    
7. <span data-ttu-id="aabf3-p104">En **Grupos**, especifique los grupos que desea asignar a la cola. Lleve a cabo una de estas acciones:</span><span class="sxs-lookup"><span data-stu-id="aabf3-p104">In **Groups**, specify the groups you want to assign to the queue. Do one of the following:</span></span> 
    
   - <span data-ttu-id="aabf3-p105">Para agregar un grupo a la cola, haga clic en **Seleccionar**. En el campo de búsqueda **Seleccionar grupos**, escriba total o parcialmente el nombre del grupo de agentes que desea asignar a la cola. A continuación, haga clic en el grupo de agentes que desea y en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="aabf3-p105">To add a group to the queue, click **Select**. In the **Select Groups** search field, type all or part of the name of the agent group that you want to assign to the queue, click the agent group that you want, and then click **OK**.</span></span>
    
   - <span data-ttu-id="aabf3-126">Para quitar un grupo de la cola, en la lista de grupos de agentes, haga clic en el grupo que desea quitar y en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="aabf3-126">To remove a group from the queue, in the list of agent groups, click the group that you want to remove, and then click **Remove**.</span></span>
    
   - <span data-ttu-id="aabf3-127">Para cambiar el orden en el que se buscan los agentes, en la lista de grupos de agentes, haga clic en un grupo y en la flecha arriba o abajo.</span><span class="sxs-lookup"><span data-stu-id="aabf3-127">To change the order in which agents are searched, in the list of agent groups, click a group, and then click the up arrow or down arrow.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="aabf3-p106">Cuando el servidor busca un agente disponible en la cola, usa el orden de grupo. Es decir, busca primero en el primer grupo de la lista, después en el segundo grupo y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="aabf3-p106">When the server searches for an available agent for the queue, it uses group order. That is, the first group in the list is searched first, followed by the second group in the list, and so on.</span></span> 
  
8. <span data-ttu-id="aabf3-130">Para especificar un período máximo de tiempo de espera para el autor de una llamada antes de que un agente responda, active la casilla **Habilitar tiempo de espera de cola** y haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="aabf3-130">To specify a maximum period of time for a caller to wait on hold before an agent answers the call, select the **Enable queue time-out** check box, and then do the following:</span></span>
    
    <span data-ttu-id="aabf3-131">a.</span><span class="sxs-lookup"><span data-stu-id="aabf3-131">a.</span></span> <span data-ttu-id="aabf3-132">En **Período de tiempo de espera (segundos)**, especifique el número máximo de segundos que el autor de una llamada debe esperar hasta que un agente responda.</span><span class="sxs-lookup"><span data-stu-id="aabf3-132">In **Time-out period (seconds)**, specify the maximum number of seconds a caller waits for an agent to answer the call.</span></span>
    
    <span data-ttu-id="aabf3-133">b.</span><span class="sxs-lookup"><span data-stu-id="aabf3-133">b.</span></span> <span data-ttu-id="aabf3-134">En **Acción de llamada**, seleccione la acción que debe producirse cuando se agote el tiempo de espera de una llamada:</span><span class="sxs-lookup"><span data-stu-id="aabf3-134">In **Call Action**, select the action that occurs when a call times out as follows:</span></span>
    
     - <span data-ttu-id="aabf3-135">Para desconectar la llamada una vez transcurrido el tiempo de espera, haga clic en **Desconectar**.</span><span class="sxs-lookup"><span data-stu-id="aabf3-135">To disconnect the call after the timeout, click **Disconnect**.</span></span>
    
     - <span data-ttu-id="aabf3-136">Para reenviar la llamada al correo de voz, haga clic en **desviar a correo de voz**y, a continuación, en el campo **dirección SIP** , escriba una dirección de correo de voz con el formato sip: _ \<nombre de usuario\>_@ _\<domainname\> _ (para ejemplo, sip:bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="aabf3-136">To forward the call to voice mail, click **Forward to voice mail**, and then in the **SIP address** field, type a voice mail address in the format sip: _\<username\>_@ _\<domainname\>_ (for example, sip:bob@contoso.com).</span></span>
    
     - <span data-ttu-id="aabf3-137">Para reenviar la llamada a otro número de teléfono, haga clic en **desviar a número de teléfono**y, a continuación, en el campo **dirección SIP** , escriba el número de teléfono en el formato sip: _ \<número\>_@ _\<domainname\>_ (por ejemplo, sip:+14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="aabf3-137">To forward the call to another telephone number, click **Forward to telephone number**, and then in the **SIP address** field, type the telephone number in the format sip: _\<number\>_@ _\<domainname\>_ (for example, sip:+14255550121@contoso.com).</span></span>
    
     - <span data-ttu-id="aabf3-138">Para reenviar la llamada a otro usuario, haga clic en **Reenviar a dirección SIP**y, a continuación, en el campo **dirección SIP** , escriba el URI del usuario en el formato sip: _ \<nombre de usuario\>_@ _\<domainname\>_.</span><span class="sxs-lookup"><span data-stu-id="aabf3-138">To forward the call to another user, click **Forward to SIP address**, and then in the **SIP address** field, type the URI for the user in the format sip: _\<username\>_@ _\<domainname\>_.</span></span>
    
     - <span data-ttu-id="aabf3-139">Para reenviar la llamada a otra cola, haga clic en **Desviar a otra cola** y busque la cola que desea usar.</span><span class="sxs-lookup"><span data-stu-id="aabf3-139">To forward the call to another queue, click **Forward to another queue**, and then browse to the queue that you want to use.</span></span>
    
9. <span data-ttu-id="aabf3-140">Para especificar el número máximo de llamadas que se pueden incluir en una cola, active la casilla **Habilitar desbordamiento de cola** y haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="aabf3-140">To specify a maximum number of calls that the queue can hold, select the **Enable queue overflow** check box, and then do the following:</span></span>
    
    <span data-ttu-id="aabf3-141">a.</span><span class="sxs-lookup"><span data-stu-id="aabf3-141">a.</span></span> <span data-ttu-id="aabf3-142">En **Número máximo de llamadas**, seleccione el número máximo de llamadas que desea incluir en la cola.</span><span class="sxs-lookup"><span data-stu-id="aabf3-142">In **Maximum number of calls**, select the maximum number of calls that you want the queue to hold.</span></span> 
    
    <span data-ttu-id="aabf3-143">b.</span><span class="sxs-lookup"><span data-stu-id="aabf3-143">b.</span></span> <span data-ttu-id="aabf3-144">En **Desviar la llamada**, seleccione la llamada que desea reenviar cuando la cola está completa: **Llamada más reciente** o **Llamada más antigua**.</span><span class="sxs-lookup"><span data-stu-id="aabf3-144">In **Forward the call**, select which call is to be forwarded when the queue is full: **Newest Call** or **Oldest Call**.</span></span>
    
    <span data-ttu-id="aabf3-145">c.</span><span class="sxs-lookup"><span data-stu-id="aabf3-145">c.</span></span> <span data-ttu-id="aabf3-146">En **Acción de llamada**, seleccione la acción que debe producirse cuando se alcance el umbral de desbordamiento conforme a lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="aabf3-146">In **Call action**, select the action that occurs when the overflow threshold is met as follows:</span></span>
    
     - <span data-ttu-id="aabf3-147">Para desconectar la llamada una vez transcurrido el tiempo de espera, haga clic en **Desconectar**.</span><span class="sxs-lookup"><span data-stu-id="aabf3-147">To disconnect the call after the timeout, click **Disconnect**.</span></span>
    
     - <span data-ttu-id="aabf3-148">Para reenviar la llamada al correo de voz, haga clic en **desviar a correo de voz**y, a continuación, en el campo **dirección SIP** , escriba una dirección de correo de voz con el formato sip: _ \<nombre de usuario\>_@ _\<domainname\> _ (para ejemplo, sip:bob@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="aabf3-148">To forward the call to voice mail, click **Forward to voice mail**, and then in the **SIP address** field, type a voice mail address in the format sip: _\<username\>_@ _\<domainname\>_ (for example, sip:bob@contoso.com).</span></span>
    
     - <span data-ttu-id="aabf3-149">Para reenviar la llamada a otro número de teléfono, haga clic en **desviar a número de teléfono**y, a continuación, en el campo **dirección SIP** , escriba el número de teléfono en el formato sip: _ \<número\>_@ _\<domainname\>_ (por ejemplo, sip:+14255550121@contoso.com).</span><span class="sxs-lookup"><span data-stu-id="aabf3-149">To forward the call to another telephone number, click **Forward to telephone number**, and then in the **SIP address** field, type the telephone number in the format sip: _\<number\>_@ _\<domainname\>_ (for example, sip:+14255550121@contoso.com).</span></span>
    
     - <span data-ttu-id="aabf3-150">Para reenviar la llamada a otro usuario, haga clic en **Reenviar a dirección SIP**y, a continuación, en el campo **dirección SIP** , escriba el URI del usuario en el formato sip: _ \<nombre de usuario\>_@ _\<domainname\>_.</span><span class="sxs-lookup"><span data-stu-id="aabf3-150">To forward the call to another user, click **Forward to SIP address**, and then in the **SIP address** field, type the URI for the user in the format sip: _\<username\>_@ _\<domainname\>_.</span></span>
    
     - <span data-ttu-id="aabf3-151">Para reenviar la llamada a otra cola, haga clic en **Desviar a otra cola** y busque la cola que desea usar.</span><span class="sxs-lookup"><span data-stu-id="aabf3-151">To forward the call to another queue, click **Forward to another queue**, and then browse to the queue that you want to use.</span></span>
    
10. <span data-ttu-id="aabf3-152">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="aabf3-152">Click **Commit**.</span></span>
    
### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-queue"></a><span data-ttu-id="aabf3-153">Usar Skype para Shell de administración de servidor empresarial para crear o modificar una cola</span><span class="sxs-lookup"><span data-stu-id="aabf3-153">To use Skype for Business Server Management Shell to create or modify a queue</span></span>

1. <span data-ttu-id="aabf3-154">Inicie sesión como miembro del grupo RTCUniversalServerAdmins o como miembro de uno de los roles administrativos predefinidos que admiten el Grupo de respuesta.</span><span class="sxs-lookup"><span data-stu-id="aabf3-154">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="aabf3-155">Si es uno de los administradores delegados del grupo de respuesta de un flujo de trabajo administrado, puede crear colas y grupos de agentes, y asignar estos grupos a las colas.</span><span class="sxs-lookup"><span data-stu-id="aabf3-155">If you are one of the delegated Response Group Managers for a managed workflow, you will be able to create agent groups and queues, and assign agent groups to queues.</span></span> 
  
2. <span data-ttu-id="aabf3-156">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="aabf3-156">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="aabf3-p112">Cree el aviso que debe reproducirse cuando se alcance el umbral de tiempo de espera de la cola y guárdelo en una variable. En la línea de comandos, ejecute:</span><span class="sxs-lookup"><span data-stu-id="aabf3-p112">Create the prompt to be played when the queue timeout threshold is met, and save it in a variable. At the command line, run:</span></span>
    
   ```
   $promptTO = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
   ```

   <span data-ttu-id="aabf3-159">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="aabf3-159">For example:</span></span>
    
   ```
   "All agents are currently busy. Please call back later."
   ```

   > [!NOTE]
   > <span data-ttu-id="aabf3-160">Para usar un archivo de audio para el símbolo del sistema, use el cmdlet **Import-CsRgsAudioFile** .</span><span class="sxs-lookup"><span data-stu-id="aabf3-160">To use an audio file for the prompt, use the **Import-CsRgsAudioFile** cmdlet.</span></span> <span data-ttu-id="aabf3-161">Para obtener información detallada, vea [Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="aabf3-161">For details, see [Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps).</span></span> 
  
4. <span data-ttu-id="aabf3-p114">Defina la acción que debe realizarse cuando se alcance el umbral de tiempo de espera de la cola y guárdela en una variable. En la línea de comandos ejecute:</span><span class="sxs-lookup"><span data-stu-id="aabf3-p114">Define the action to be taken when the queue timeout threshold is met, and save it in a variable. At the command line, run:</span></span>
    
   ```
   $actionTO = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
   ```

   > [!NOTE]
   > <span data-ttu-id="aabf3-164">Para obtener información detallada acerca de las posibles acciones y su sintaxis, consulte [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="aabf3-164">For details about possible actions and their syntax, see [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps).</span></span> 
  
    <span data-ttu-id="aabf3-165">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="aabf3-165">For example:</span></span>
    
   ```
   $action = New-CsRgsCallAction -Prompt $promptTO -Action Terminate
   ```

5. <span data-ttu-id="aabf3-p115">Cree el aviso que debe reproducirse cuando se alcance el umbral de desbordamiento de la cola y guárdelo en una variable. En la línea de comandos, ejecute:</span><span class="sxs-lookup"><span data-stu-id="aabf3-p115">Create the prompt to be played when the queue overflow threshold is met, and save it in a variable. At the command line, run:</span></span>
    
  ```
  $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
  ```

   <span data-ttu-id="aabf3-168">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="aabf3-168">For example:</span></span>
    
  ```
  $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "Too many calls are waiting. Please call back later."
  ```

      > [!NOTE]
      > <span data-ttu-id="aabf3-169">Para usar un archivo de audio para el símbolo del sistema, use el cmdlet **Import-CsRgsAudioFile** .</span><span class="sxs-lookup"><span data-stu-id="aabf3-169">To use an audio file for the prompt, use the **Import-CsRgsAudioFile** cmdlet.</span></span> <span data-ttu-id="aabf3-170">Para obtener información detallada, vea [Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="aabf3-170">For details, see [Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps).</span></span> 
  
6. <span data-ttu-id="aabf3-p117">Defina la acción que debe realizarse cuando se alcance el umbral de desbordamiento de la cola y guárdela en una variable. En la línea de comandos ejecute:</span><span class="sxs-lookup"><span data-stu-id="aabf3-p117">Define the action to be taken when the queue overflow threshold is met, and save it in a variable. At the command line, run:</span></span>
    
  ```
  $actionOV = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
  ```

    > [!NOTE]
    > <span data-ttu-id="aabf3-173">Para obtener información detallada acerca de las posibles acciones y su sintaxis, consulte [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="aabf3-173">For details about possible actions and their syntax, see [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps).</span></span> 
  
    <span data-ttu-id="aabf3-174">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="aabf3-174">For example:</span></span>
    
   ```
   $action = New-CsRgsCallAction -Prompt $promptOV -Action Terminate
   ```

7. <span data-ttu-id="aabf3-p118">Recupere el nombre de servicio del servicio Grupo de respuestas y asígnelo a una variable. En la línea de comandos, ejecute:</span><span class="sxs-lookup"><span data-stu-id="aabf3-p118">Retrieve the service name for the Response Group service and assign it to a variable. At the command line, run:</span></span>
    
   ```
   $serviceId="service:"+(Get-CSService | ?{$_.Applications -Like "*RGS*"}).ServiceId;
   ```

8. <span data-ttu-id="aabf3-p119">Obtenga la identidad del grupo de agentes que debe asignarse a la cola. En la línea de comandos, ejecute:</span><span class="sxs-lookup"><span data-stu-id="aabf3-p119">Get the identity of the agent group to be assigned to the queue. At the command line, run:</span></span>
    
   ```
   $agid = (Get-CsRgsAgentGroup -Name "Help Desk").Identity;
   ```

    > [!NOTE]
    > <span data-ttu-id="aabf3-179">Para obtener información detallada acerca de cómo crear el grupo de agentes, vea [New-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/new-csrgsagentgroup?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="aabf3-179">For details about creating the agent group, see [New-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/new-csrgsagentgroup?view=skype-ps)</span></span>
  
9. <span data-ttu-id="aabf3-p120">Cree la cola. En la línea de comandos, ejecute:</span><span class="sxs-lookup"><span data-stu-id="aabf3-p120">Create the queue. At the command line, run:</span></span>
    
   ```
   $q = New-CsRgsQueue -Parent <saved service ID from previous step> -Name "<name of queue>" [-Description "<description for queue>"] [-TimeoutThreshold <# seconds before call times out>] [-TimeoutAction <saved timeout action>] [-OverflowThreshold <# calls queue can hold>] [-OverflowCandidate <call to be acted on when overflow threshold met>] [-OverflowAction <saved overflow action>] [-AgentGroupIDList(<agent group identity>)];
   ```

   <span data-ttu-id="aabf3-182">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="aabf3-182">For example:</span></span>
    
   ```
   $q = New-CsRgsQueue -Parent $serviceId -Name "Help Desk" -Description "Contoso Help Desk" -TimeoutThreshold 300 -TimeoutAction $actionTO -OverflowThreshold 10 -OverflowCandidate NewestCall -OverflowAction $actionOV -AgentGroupIDList($agid.Identity;
   ```

10. <span data-ttu-id="aabf3-p121">Confirme que la cola se ha creado. Ejecute:</span><span class="sxs-lookup"><span data-stu-id="aabf3-p121">Confirm that the queue is created. Run:</span></span>
    
   ```
   Get-CsRgsQueue -Name "Help Desk"
   ```

## <a name="see-also"></a><span data-ttu-id="aabf3-185">Vea también</span><span class="sxs-lookup"><span data-stu-id="aabf3-185">See also</span></span>

[<span data-ttu-id="aabf3-186">New-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="aabf3-186">New-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgsqueue?view=skype-ps)
  
[<span data-ttu-id="aabf3-187">Set-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="aabf3-187">Set-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csrgsqueue?view=skype-ps)
  
[<span data-ttu-id="aabf3-188">New-CsRgsPrompt</span><span class="sxs-lookup"><span data-stu-id="aabf3-188">New-CsRgsPrompt</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgsprompt?view=skype-ps)
  
[<span data-ttu-id="aabf3-189">New-CsRgsCallAction</span><span class="sxs-lookup"><span data-stu-id="aabf3-189">New-CsRgsCallAction</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps)
  
[<span data-ttu-id="aabf3-190">Get-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="aabf3-190">Get-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csrgsqueue?view=skype-ps)
  
[<span data-ttu-id="aabf3-191">Import-CsRgsAudioFile</span><span class="sxs-lookup"><span data-stu-id="aabf3-191">Import-CsRgsAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)
  
[<span data-ttu-id="aabf3-192">Remove-CsRgsQueue</span><span class="sxs-lookup"><span data-stu-id="aabf3-192">Remove-CsRgsQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csrgsqueue?view=skype-ps)