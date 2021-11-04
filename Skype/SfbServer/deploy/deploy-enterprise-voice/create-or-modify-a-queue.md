---
title: Crear o modificar una cola en Skype Empresarial
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b9d6366a-839f-4651-a01d-9254546cadeb
description: Cree o modifique una cola de grupo de respuesta en Skype Empresarial Server Telefonía IP empresarial.
ms.openlocfilehash: 7cc079b458f4aae2748c212dd5c0bcf710142716
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60765908"
---
# <a name="create-or-modify-a-queue-in-skype-for-business"></a>Crear o modificar una cola en Skype Empresarial
 
Cree o modifique una cola de grupo de respuesta en Skype Empresarial Server Telefonía IP empresarial.
  
Las colas contienen autores de la llamada hasta que un agente atiende la llamada. Cuando la aplicación Grupo de respuesta busca un agente disponible, busca grupos de agentes en el orden en que los enumera. Puede seleccionar los grupos de agentes asignados a la cola y especificar el comportamiento de la cola, como el límite de número de llamadas que puede contener la cola y cuánto tiempo debe esperar una llamada hasta que un agente la responda.
  
Use uno de los siguientes procedimientos para crear o modificar una cola.
  
### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-a-queue"></a>Para usar Skype Empresarial Server panel de control para crear o modificar una cola

1. Inicie sesión como miembro del grupo RTCUniversalServerAdmins, o como miembro de un rol administrativo predefinido que admita el grupo de respuesta.
    
    > [!NOTE]
    > Si es uno de los administradores de grupos de respuesta delegados para un flujo de trabajo administrado, puede crear o modificar colas de grupo de respuesta y asignarlas a los flujos de trabajo que administre. 
  
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir Skype Empresarial Server Panel de control.  
    
3. En la barra de navegación izquierda, haga clic en **Grupos de respuesta** y, a continuación, en **Cola**.
    
4. En la **página** Cola, realice una de las siguientes acciones:
    
   - Para crear una cola nueva, haga clic en **Nuevo**. En **Seleccionar un servicio**, escriba parte o todo el nombre del servicio **ApplicationServer** donde desea agregar la cola en el campo de búsqueda. En la lista de resultados que aparece, haga clic en el servicio que desea y en **Aceptar**.
    
   - Para modificar una cola existente, escriba todo o parte del nombre de cola en el campo de búsqueda. En la lista resultante de colas, haga clic en la cola que desee, haga clic **en Editar** y, a continuación, haga clic en **Mostrar detalles.**
    
5. En **Nombre**, escriba un nombre de identificación para la cola.
    
6. En **Descripción**, escriba una descripción para la cola.
    
7. En **Grupos,** especifique los grupos que desea asignar a la cola. Realice una de las siguientes acciones: 
    
   - Para agregar un grupo a la cola, haga clic en **Seleccionar**. En **el** campo de búsqueda Seleccionar grupos, escriba todo o parte del nombre del grupo de agentes que desea asignar a la cola, haga clic en el grupo de agentes que desee y, a continuación, haga clic en **Aceptar**.
    
   - Para quitar un grupo de la cola, en la lista de grupos de agentes, haga clic en el grupo que desea quitar y, a continuación, haga clic en **Quitar**.
    
   - Para cambiar el orden en que se buscan los agentes, en la lista de grupos de agentes, haga clic en un grupo y, a continuación, haga clic en la flecha arriba o abajo.
    
     > [!NOTE]
     > Cuando el servidor busca un agente disponible para la cola, usa el orden de grupo. Es decir, primero se busca en el primer grupo de la lista, seguido del segundo grupo de la lista, y así sucesivamente. 
  
8. Para especificar un período de tiempo máximo de espera para el autor de una llamada antes de que un agente le atienda, active la casilla **Habilitar tiempo de espera de la cola**.
    
    a. En **Tiempo de espera (segundos)**, especifique el número máximo de segundos que va a esperar el autor de una llamada para que le atienda un agente.
    
    b. En **Acción de llamada**, seleccione la acción que va a tener lugar cuando se agota el tiempo de espera de una llamada de la forma siguiente:
    
   - Para desconectar la llamada tras el tiempo de espera, haga clic en **Desconectar**.
    
   - Para reenviar la llamada al correo de voz, haga clic en Reenviar a correo de voz y, a continuación, en el campo Dirección **SIP,** escriba una dirección de correo de voz en el formato sip: *\<username\>* @  *\<domainname\>* (por ejemplo, sip:bob@contoso.com).
    
   - Para reenviar la llamada a otro número de teléfono, haga clic en Reenviar al número de teléfono y, a continuación, en el campo Dirección **SIP,** escriba el número de teléfono con el formato sip: *\<number\>* @  *\<domainname\>* (por ejemplo, sip:+14255550121@contoso.com).
    
   - Para reenviar la llamada a otro usuario, haga clic en Reenviar a dirección **SIP** y, a continuación, en el campo Dirección **SIP,** escriba el URI del usuario con el formato sip: _\<username\>_ @  _\<domainname\>_ .
    
   - Para desviar la llamada a otra cola, haga clic en **Desviar a otra cola** y, a continuación, vaya a la cola que desee utilizar.
    
9. Para especificar un número máximo de llamadas que puede contener la cola, active la casilla **Permitir desbordamiento de cola** y siga este procedimiento:
    
    a. En **Número máximo de llamadas**, seleccione el número máximo de llamadas que desea que contenga la cola. 
    
    b. En **Desviar la llamada**, seleccione la llamada que se va a desviar cuando la cola esté llena. **Llamada más reciente** o **Llamada más antigua**.
    
    c. En **Acción de llamada,** seleccione la acción que se produce cuando se cumple el umbral de desbordamiento de la siguiente manera:
    
   - Para desconectar la llamada tras el tiempo de espera, haga clic en **Desconectar**.
    
   - Para reenviar la llamada al correo de voz, haga clic en Reenviar a correo de voz y, a continuación, en el campo Dirección **SIP,** escriba una dirección de correo de voz en el formato sip: *\<username\>* @  *\<domainname\>* (por ejemplo, sip:bob@contoso.com).
    
   - Para reenviar la llamada a otro número de teléfono, haga clic en Reenviar al número de teléfono y, a continuación, en el campo Dirección **SIP,** escriba el número de teléfono con el formato sip: *\<number\>* @  *\<domainname\>* (por ejemplo, sip:+14255550121@contoso.com).
    
   - Para reenviar la llamada a otro usuario, haga clic en Reenviar a dirección **SIP** y, a continuación, en el campo Dirección **SIP,** escriba el URI del usuario con el formato sip: _\<username\>_ @  _\<domainname\>_ .
    
   - Para desviar la llamada a otra cola, haga clic en **Desviar a otra cola** y, a continuación, vaya a la cola que desee utilizar.
    
10. Haga clic en **Confirmar**.
    
### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-queue"></a>Para usar Skype Empresarial Server Shell de administración para crear o modificar una cola

1. Inicie sesión como miembro del grupo RTCUniversalServerAdmins, o como miembro de un rol administrativo predefinido que admita el grupo de respuesta.
    
    > [!NOTE]
    > Si es uno de los administradores de grupos de respuesta delegados para un flujo de trabajo administrado, podrá crear grupos de agentes y colas y asignar grupos de agentes a colas. 
  
2. Inicie el Shell Skype Empresarial Server administración: haga clic en Inicio **,** todos los programas **,** haga clic en **Skype Empresarial 2015** y, a continuación, haga clic **Skype Empresarial Server Shell de administración**.
    
3. Cree el mensaje que se reproducirá cuando se alcance el umbral de tiempo de espera de cola y guárdelo en una variable. En la línea de comandos, ejecute:
    
   ```powershell
   $promptTO = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
   ```

   Por ejemplo:
    
   ```console
   "All agents are currently busy. Please call back later."
   ```

   > [!NOTE]
   > Para usar un archivo de audio para el mensaje, ejecute el cmdlet **Import-CsRgsAudioFile**. Para obtener más información, [vea Import-CsRgsAudioFile](/powershell/module/skype/import-csrgsaudiofile?view=skype-ps). 
  
4. Defina la acción que se debe realizar cuando se alcance el umbral de tiempo de espera de cola y guárdelo en una variable. En la línea de comandos, ejecute:
    
   ```powershell
   $actionTO = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
   ```

   > [!NOTE]
   > Para obtener más información sobre las acciones posibles y su sintaxis, [vea New-CsRgsCallAction](/powershell/module/skype/new-csrgscallaction?view=skype-ps). 
  
    Por ejemplo:
    
   ```powershell
   $action = New-CsRgsCallAction -Prompt $promptTO -Action Terminate
   ```

5. Cree el mensaje que se reproducirá cuando se alcance el umbral de desbordamiento de cola y guárdelo en una variable. En la línea de comandos, ejecute:
    
   ```powershell
   $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
   ```

   Por ejemplo:
    
   ```powershell
   $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "Too many calls are waiting. Please call back later."
   ```

      > [!NOTE]
      > Para usar un archivo de audio para el mensaje, ejecute el cmdlet **Import-CsRgsAudioFile**. Para obtener más información, [vea Import-CsRgsAudioFile](/powershell/module/skype/import-csrgsaudiofile?view=skype-ps). 
  
6. Defina la acción que se debe realizar cuando se alcance el umbral de desbordamiento de cola y guárdelo en una variable. En la línea de comandos, ejecute:
    
   ```powershell
   $actionOV = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
   ```

    > [!NOTE]
    > Para obtener más información sobre las acciones posibles y su sintaxis, [vea New-CsRgsCallAction](/powershell/module/skype/new-csrgscallaction?view=skype-ps). 
  
    Por ejemplo:
    
   ```powershell
   $action = New-CsRgsCallAction -Prompt $promptOV -Action Terminate
   ```

7. Recupere el nombre del servicio para el servicio del grupo de respuesta y asígnelo a una variable. En la línea de comandos, ejecute:
    
   ```powershell
   $serviceId="service:"+(Get-CSService | ?{$_.Applications -Like "*RGS*"}).ServiceId;
   ```

8. Obtener la identidad del grupo de agentes que se va a asignar a la cola. En la línea de comandos, ejecute:
    
   ```powershell
   $agid = (Get-CsRgsAgentGroup -Name "Help Desk").Identity;
   ```

    > [!NOTE]
    > Para obtener más información sobre cómo crear el grupo de agentes, [vea New-CsRgsAgentGroup](/powershell/module/skype/new-csrgsagentgroup?view=skype-ps)
  
9. Cree la cola. En la línea de comandos, ejecute:
    
   ```powershell
   $q = New-CsRgsQueue -Parent <saved service ID from previous step> -Name "<name of queue>" [-Description "<description for queue>"] [-TimeoutThreshold <# seconds before call times out>] [-TimeoutAction <saved timeout action>] [-OverflowThreshold <# calls queue can hold>] [-OverflowCandidate <call to be acted on when overflow threshold met>] [-OverflowAction <saved overflow action>] [-AgentGroupIDList(<agent group identity>)];
   ```

   Por ejemplo:
    
   ```powershell
   $q = New-CsRgsQueue -Parent $serviceId -Name "Help Desk" -Description "Contoso Help Desk" -TimeoutThreshold 300 -TimeoutAction $actionTO -OverflowThreshold 10 -OverflowCandidate NewestCall -OverflowAction $actionOV -AgentGroupIDList($agid.Identity;
   ```

10. Confirme que se ha creado la cola. Ejecute: 
    
    ```powershell
    Get-CsRgsQueue -Name "Help Desk"
    ```

## <a name="see-also"></a>Consulte también

[New-CsRgsQueue](/powershell/module/skype/new-csrgsqueue?view=skype-ps)
  
[Set-CsRgsQueue](/powershell/module/skype/set-csrgsqueue?view=skype-ps)
  
[New-CsRgsPrompt](/powershell/module/skype/new-csrgsprompt?view=skype-ps)
  
[New-CsRgsCallAction](/powershell/module/skype/new-csrgscallaction?view=skype-ps)
  
[Get-CsRgsQueue](/powershell/module/skype/get-csrgsqueue?view=skype-ps)
  
[Import-CsRgsAudioFile](/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)
  
[Remove-CsRgsQueue](/powershell/module/skype/remove-csrgsqueue?view=skype-ps)