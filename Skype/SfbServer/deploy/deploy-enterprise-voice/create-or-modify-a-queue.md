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
ms.openlocfilehash: 5ff696de582a1d0238e9b67bbe0b53affb33ffd2
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="create-or-modify-a-queue-in-skype-for-business-2015"></a>Crear o modificar una cola en Skype Empresarial 2015
 
Crear o modificar una cola de grupo de respuesta, en Skype para Business Server Enterprise Voice.
  
Las colas contienen autores de la llamada hasta que un agente atiende la llamada. Cuando la aplicación de grupo de respuesta busca un agente disponible, busca grupos de agentes en el orden en que éstos se enumeran. Puede seleccionar los grupos de agentes asignados a la cola y especificar el comportamiento de la cola, como el límite de número de llamadas que puede contener la cola y cuánto tiempo debe esperar una llamada hasta que un agente la responda.
  
Use uno de los procedimientos siguientes para crear o modificar una cola.
  
### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-a-queue"></a>Usar Skype para el Panel de Control de servidor empresarial para crear o modificar una cola

1. Inicie sesión como miembro del grupo RTCUniversalServerAdmins o como miembro de uno de los roles administrativos predefinidos que admiten el Grupo de respuesta.
    
    > [!NOTE]
    > Si es uno de los administradores delegados del grupo de respuesta de un flujo de trabajo administrado, puede crear o modificar colas de grupo de respuesta y asignarlas a los flujos de trabajo que administre. 
  
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Skype para el Panel de Control de servidor empresarial.  
    
3. En la barra de navegación izquierda, haga clic en **Grupos de respuesta** y luego en **Cola**.
    
4. En la página **Cola**, lleve a cabo alguna de estas acciones:
    
   - Para crear una cola nueva, haga clic en **Nuevo**. En **Seleccionar un servicio**, escriba parte o todo el nombre del servicio **ApplicationServer** donde desea agregar la cola en el campo de búsqueda. En la lista de servicios que aparezca, haga clic en el servicio que desea y en **Aceptar**.
    
   - Para modificar una cola actual, escriba total o parcialmente el nombre de la cola en el campo de búsqueda. En la lista de colas que aparezca, haga clic sucesivamente en la cola que desea, **Editar** y **Mostrar detalles**.
    
5. En **Nombre**, escriba un nombre de identificación para la cola.
    
6. En **Descripción**, escriba la descripción de la cola.
    
7. En **Grupos**, especifique los grupos que desea asignar a la cola. Lleve a cabo una de estas acciones: 
    
   - Para agregar un grupo a la cola, haga clic en **Seleccionar**. En el campo de búsqueda **Seleccionar grupos**, escriba total o parcialmente el nombre del grupo de agentes que desea asignar a la cola. A continuación, haga clic en el grupo de agentes que desea y en **Aceptar**.
    
   - Para quitar un grupo de la cola, en la lista de grupos de agentes, haga clic en el grupo que desea quitar y en **Aceptar**.
    
   - Para cambiar el orden en el que se buscan los agentes, en la lista de grupos de agentes, haga clic en un grupo y en la flecha arriba o abajo.
    
    > [!NOTE]
    > Cuando el servidor busca un agente disponible en la cola, usa el orden de grupo. Es decir, busca primero en el primer grupo de la lista, después en el segundo grupo y así sucesivamente. 
  
8. Para especificar un período máximo de tiempo de espera para el autor de una llamada antes de que un agente responda, active la casilla **Habilitar tiempo de espera de cola** y haga lo siguiente:
    
    a. En **Período de tiempo de espera (segundos)**, especifique el número máximo de segundos que el autor de una llamada debe esperar hasta que un agente responda.
    
    b. En **Acción de llamada**, seleccione la acción que debe producirse cuando se agote el tiempo de espera de una llamada:
    
     - Para desconectar la llamada una vez transcurrido el tiempo de espera, haga clic en **Desconectar**.
    
     - Para reenviar la llamada al correo de voz, haga clic en **desviar a correo de voz**y, a continuación, en el campo **dirección SIP** , escriba una dirección de correo de voz con el formato sip: _ \<nombre de usuario\>_@ _\<domainname\> _ (para ejemplo, sip:bob@contoso.com).
    
     - Para reenviar la llamada a otro número de teléfono, haga clic en **desviar a número de teléfono**y, a continuación, en el campo **dirección SIP** , escriba el número de teléfono en el formato sip: _ \<número\>_@ _\<domainname\>_ (por ejemplo, sip:+14255550121@contoso.com).
    
     - Para reenviar la llamada a otro usuario, haga clic en **Reenviar a dirección SIP**y, a continuación, en el campo **dirección SIP** , escriba el URI del usuario en el formato sip: _ \<nombre de usuario\>_@ _\<domainname\>_.
    
     - Para reenviar la llamada a otra cola, haga clic en **Desviar a otra cola** y busque la cola que desea usar.
    
9. Para especificar el número máximo de llamadas que se pueden incluir en una cola, active la casilla **Habilitar desbordamiento de cola** y haga lo siguiente:
    
    a. En **Número máximo de llamadas**, seleccione el número máximo de llamadas que desea incluir en la cola. 
    
    b. En **Desviar la llamada**, seleccione la llamada que desea reenviar cuando la cola está completa: **Llamada más reciente** o **Llamada más antigua**.
    
    c. En **Acción de llamada**, seleccione la acción que debe producirse cuando se alcance el umbral de desbordamiento conforme a lo siguiente:
    
     - Para desconectar la llamada una vez transcurrido el tiempo de espera, haga clic en **Desconectar**.
    
     - Para reenviar la llamada al correo de voz, haga clic en **desviar a correo de voz**y, a continuación, en el campo **dirección SIP** , escriba una dirección de correo de voz con el formato sip: _ \<nombre de usuario\>_@ _\<domainname\> _ (para ejemplo, sip:bob@contoso.com).
    
     - Para reenviar la llamada a otro número de teléfono, haga clic en **desviar a número de teléfono**y, a continuación, en el campo **dirección SIP** , escriba el número de teléfono en el formato sip: _ \<número\>_@ _\<domainname\>_ (por ejemplo, sip:+14255550121@contoso.com).
    
     - Para reenviar la llamada a otro usuario, haga clic en **Reenviar a dirección SIP**y, a continuación, en el campo **dirección SIP** , escriba el URI del usuario en el formato sip: _ \<nombre de usuario\>_@ _\<domainname\>_.
    
     - Para reenviar la llamada a otra cola, haga clic en **Desviar a otra cola** y busque la cola que desea usar.
    
10. Haga clic en **Confirmar**.
    
### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-queue"></a>Usar Skype para Shell de administración de servidor empresarial para crear o modificar una cola

1. Inicie sesión como miembro del grupo RTCUniversalServerAdmins o como miembro de uno de los roles administrativos predefinidos que admiten el Grupo de respuesta.
    
    > [!NOTE]
    > Si es uno de los administradores delegados del grupo de respuesta de un flujo de trabajo administrado, puede crear colas y grupos de agentes, y asignar estos grupos a las colas. 
  
2. Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.
    
3. Cree el aviso que debe reproducirse cuando se alcance el umbral de tiempo de espera de la cola y guárdelo en una variable. En la línea de comandos, ejecute:
    
   ```
   $promptTO = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
   ```

   Por ejemplo:
    
   ```
   "All agents are currently busy. Please call back later."
   ```

   > [!NOTE]
   > Para usar un archivo de audio para el símbolo del sistema, use el cmdlet **Import-CsRgsAudioFile** . Para obtener información detallada, vea [Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps). 
  
4. Defina la acción que debe realizarse cuando se alcance el umbral de tiempo de espera de la cola y guárdela en una variable. En la línea de comandos ejecute:
    
   ```
   $actionTO = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
   ```

   > [!NOTE]
   > Para obtener información detallada acerca de las posibles acciones y su sintaxis, consulte [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps). 
  
    Por ejemplo:
    
   ```
   $action = New-CsRgsCallAction -Prompt $promptTO -Action Terminate
   ```

5. Cree el aviso que debe reproducirse cuando se alcance el umbral de desbordamiento de la cola y guárdelo en una variable. En la línea de comandos, ejecute:
    
  ```
  $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
  ```

   Por ejemplo:
    
  ```
  $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "Too many calls are waiting. Please call back later."
  ```

      > [!NOTE]
      > Para usar un archivo de audio para el símbolo del sistema, use el cmdlet **Import-CsRgsAudioFile** . Para obtener información detallada, vea [Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps). 
  
6. Defina la acción que debe realizarse cuando se alcance el umbral de desbordamiento de la cola y guárdela en una variable. En la línea de comandos ejecute:
    
  ```
  $actionOV = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
  ```

    > [!NOTE]
    > Para obtener información detallada acerca de las posibles acciones y su sintaxis, consulte [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps). 
  
    Por ejemplo:
    
   ```
   $action = New-CsRgsCallAction -Prompt $promptOV -Action Terminate
   ```

7. Recupere el nombre de servicio del servicio Grupo de respuestas y asígnelo a una variable. En la línea de comandos, ejecute:
    
   ```
   $serviceId="service:"+(Get-CSService | ?{$_.Applications -Like "*RGS*"}).ServiceId;
   ```

8. Obtenga la identidad del grupo de agentes que debe asignarse a la cola. En la línea de comandos, ejecute:
    
   ```
   $agid = (Get-CsRgsAgentGroup -Name "Help Desk").Identity;
   ```

    > [!NOTE]
    > Para obtener información detallada acerca de cómo crear el grupo de agentes, vea [New-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/new-csrgsagentgroup?view=skype-ps)
  
9. Cree la cola. En la línea de comandos, ejecute:
    
   ```
   $q = New-CsRgsQueue -Parent <saved service ID from previous step> -Name "<name of queue>" [-Description "<description for queue>"] [-TimeoutThreshold <# seconds before call times out>] [-TimeoutAction <saved timeout action>] [-OverflowThreshold <# calls queue can hold>] [-OverflowCandidate <call to be acted on when overflow threshold met>] [-OverflowAction <saved overflow action>] [-AgentGroupIDList(<agent group identity>)];
   ```

   Por ejemplo:
    
   ```
   $q = New-CsRgsQueue -Parent $serviceId -Name "Help Desk" -Description "Contoso Help Desk" -TimeoutThreshold 300 -TimeoutAction $actionTO -OverflowThreshold 10 -OverflowCandidate NewestCall -OverflowAction $actionOV -AgentGroupIDList($agid.Identity;
   ```

10. Confirme que la cola se ha creado. Ejecute:
    
   ```
   Get-CsRgsQueue -Name "Help Desk"
   ```

## <a name="see-also"></a>Vea también

#### 

[New-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/new-csrgsqueue?view=skype-ps)
  
[Set-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/set-csrgsqueue?view=skype-ps)
  
[New-CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/new-csrgsprompt?view=skype-ps)
  
[New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps)
  
[Get-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/get-csrgsqueue?view=skype-ps)
  
[Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)
  
[Remove-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/remove-csrgsqueue?view=skype-ps)

