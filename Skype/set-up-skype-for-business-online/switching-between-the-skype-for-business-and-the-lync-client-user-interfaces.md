---
title: "Cambiar de la interfaz de usuario del cliente de Lync a la de Skype Empresarial"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 6/1/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_Skype4B_Online
- Adm_Skype4B_Online_Top
ms.custom: Adm_O365_FullSet
ms.assetid: a2394a4c-7522-484c-a047-7b3289742be0
description: "Learn how to switch between Skype for Business and Lync client user interfaces using PowerShell in Office 365 "
---

# Cambiar de la interfaz de usuario del cliente de Lync a la de Skype Empresarial

> [!IMPORTANT]
> Este artículo se ha traducido con traducción automática; vea la [declinación de responsabilidades](a2394a4c-7522-484c-a047-7b3289742be0.md#MT_Footer). Para su referencia, puede encontrar la versión en inglés de este artículo [aquí](https://support.office.com/en-us/article/a2394a4c-7522-484c-a047-7b3289742be0). 
  
Para las organizaciones de Skype Empresarial Online, puede usar Remote PowerShell en Office 365 para permitir que los usuarios de Skype Empresarial usen el cliente de Skype Empresarial o la interfaz de usuario de cliente de Skype Empresarial (Lync). La configuración predeterminada es para los usuarios que usen la interfaz de usuario de cliente de Skype Empresarial. Si prefiere usar la experiencia de cliente de Lync, administre el comportamiento del cliente en el primer inicio para que muestre la interfaz de usuario de Lync. Para ello, siga los pasos que se muestran en este mismo tema.
  
> [!NOTE]
> La experiencia de cliente con Lync 2013 no está disponible en las versiones de cliente de Skype Empresarial 2016. Antes de que intente configurar su entorno de cliente para usar el cliente de Lync 2013, compruebe la versión y asegúrese de que no empieza con el número 16; por ejemplo: 16.x.x.x. 
  
> [!TIP]
> Si desea cambiar fácilmente la interfaz de usuario y no desea realizar los pasos manuales, consulte el [Centro de descarga de Microsoft ](https://go.microsoft.com/fwlink/?LinkId=532431) para un script de PowerShell para que sea más fácil.
  
## Cambio de la interfaz de usuario de Skype Empresarial para los usuarios

El módulo de Windows PowerShell para Skype empresarial Online le permite crear una sesión de Windows PowerShell remoto que se conecta a Skype empresarial Online. Este módulo, que sólo se admite en equipos de 64 bits se puede descargar desde Microsoft Download Center en el [Módulo de Windows PowerShell para Skype empresarial Online](https://go.microsoft.com/fwlink/?LinkId=294688). Para más información, consulte [Configurar Skype para la administración empresarial Online en su equipo](https://go.microsoft.com/fwlink/?LinkId=534539).
  
> [!IMPORTANT]
> La configuración de la directiva  _Global_ para cambiar la interfaz de usuario no se aplicará a un usuario que ya tenga aplicada una directiva personalizada. Para poder cambiar la interfaz de usuario, tendrá que ejecutar lo siguiente para cada usuario que tenga aplicada una directiva personalizada:
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI -Identity <username>
```

> [!CAUTION]
> La directiva  _ClientPolicyEnableSkypeUI_ sustituirá a la configuración de la directiva personalizada existente para el usuario.
  
Para habilitar que todos los usuarios de su organización utilicen el cliente de Skype Empresarial, abra el PowerShell remoto y escriba lo siguiente:
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI
```

Si configura la directiva de forma correcta, verá:
  
![PowerShell: SkypeUIEnabled](../images/b6b9d2e1-1a37-46df-9757-f81c6054e93b.png)
  
Para habilitar que todos los usuarios de su organización utilicen el cliente de Skype Empresarial (Lync), abra el PowerShell remoto y escriba lo siguiente:
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

Si configura la directiva de forma correcta, verá:
  
![PowerShell: SkypeUIDisabled](../images/f14ec3ce-4eb8-4a11-826e-6029043ed054.png)
  
Para permitir que solo un usuario de su organización utilice el cliente de Skype Empresarial, abra el PowerShell remoto y escriba lo siguiente:
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI -Identity <username>
```

Si configura la directiva de forma correcta, verá:
  
![Skype Empresarial Online - Activar IU](../images/596aef69-41dc-4e1e-b689-2b7009ae58a1.gif)
  
Para permitir que solo un usuario de su organización utilice el cliente de Skype Empresarial (Lync), abra el PowerShell remoto y escriba lo siguiente:
  
```
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI -Identity <username>
```

Si configura la directiva de forma correcta, verá:
  
![Skype Empresarial Online - IU deshabilitada](../images/61c645e0-67fc-4e03-803c-b7028a47dae3.gif)
  
Para permitir que varios usuarios de su organización utilicen el cliente de Skype Empresarial, abra el PowerShell remoto y escriba lo siguiente:
  
> 
  ```
  $users = @("sip:bob@contoso.com","sip:fred@contoso.com")
  ```

> 
  ```
  $users | Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI
  ```

Para permitir que varios usuarios de su organización utilicen el cliente de Skype Empresarial (Lync), abra el PowerShell remoto y escriba lo siguiente:
  
> 
  ```
  $users = @("sip:bob@contoso.com","sip:fred@contoso.com")
  ```

> 
  ```
  $users | Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
  ```

Para permitir que un grupo de usuarios de su organización utilice el cliente de Skype Empresarial, abra el PowerShell remoto y escriba lo siguiente:
  
```
Get-CsOnlineUser -Filter {Department -eq "Sales"} | Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI
```

Para permitir que un grupo de usuarios de su organización utilice el cliente de Skype Empresarial (Lync), abra el PowerShell remoto y escriba lo siguiente:
  
```
Get-CsOnlineUser -Filter {Department -eq "Sales"} | Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

> [!NOTE]
>  El nombre del usuario es el nombre de la cuenta del usuario a la cual se asignará la directiva. El nombre de la cuenta del usuario se puede introducir en uno de los siguientes formatos:>  Dirección SIP del usuario>  Nombre principal de usuario (UPN) del usuario>  Dominio\\nombre de usuario del usuario>  Nombre para mostrar de Active Directory del usuario
  
[Usar Windows PowerShell para administrar Lync Online](https://go.microsoft.com/fwlink/?LinkID=525453)
  
## Configuración de directivas de Skype Empresarial Online

Esta tabla muestra la experiencia de usuario cuando la directiva se aplica primero a los usuarios:
  
|**Configuración de la directiva de administrador**|**Interfaz de usuario que se muestra**|
|:-----|:-----|
|La directiva no está configurada.  <br/> |El usuario continuará utilizando la interfaz de usuario del cliente de Skype Empresarial.  <br/> |
|
```
Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI
```

|El usuario continuará utilizando la interfaz de usuario del cliente de Skype Empresarial.  <br/> |
|
```
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

|Se le solicitará al usuario cambiar a la interfaz de usuario del cliente de Skype Empresarial (Lync). Pueden realizar el cambio más tarde.  <br/> |
|
```
Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI -Identity <username>
```

|El usuario utilizará la interfaz de usuario del cliente de Skype Empresarial.  <br/> |
|
```
Grant-CsClientPolicy-PolicyName ClientPolicyDisableSkypeUI -Identity <username>
```

|Se le solicitará al usuario cambiar a la interfaz de usuario del cliente de Skype Empresarial (Lync). Un administrador puede cambiar la configuración en el futuro, por lo que cambiará la interfaz de usuario del cliente de Skype Empresarial.  <br/> |
   
Esta tabla muestra la experiencia de usuario cuando se cambia la directiva:
  
|**Configuración de la directiva de administrador**|**Interfaz de usuario de Skype Empresarial (Lync)**|**Interfaz de usuario de Skype Empresarial**|
|:-----|:-----|:-----|
|
```
Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI
```

|Se le solicitará al usuario cambiar a la interfaz de usuario del cliente de Skype Empresarial.  <br/> |El usuario seguirá utilizando la interfaz de usuario del cliente de Skype Empresarial.  <br/> |
|
```
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

|El usuario seguirá utilizando la interfaz de Skype Empresarial (Lync).  <br/> |Se le solicitará al usuario cambiar a la interfaz de usuario del cliente de Skype Empresarial (Lync).  <br/> |
|La directiva no está configurada.  <br/> |Los usuarios nunca verán la interfaz de usuario del cliente de Skype Empresarial (Lync) si no se configura la directiva. Siempre utilizarán la interfaz de usuario del cliente de Skype Empresarial.  <br/> |El usuario seguirá utilizando la interfaz de usuario del cliente de Skype Empresarial.  <br/> |
   
Esta tabla muestra todas las directivas personalizadas disponibles en línea. Hay nuevas políticas creadas para dar flexibilidad a los administradores para que conserven la antigua directiva personalizada al cambiar entre las marcas EnableSkypeUI. Use los cmdlets de arriba para conceder una de las siguientes directivas a los usuarios.
  
|**Nombre de la directiva**|**EnableSkypeUI**|
|:-----|:-----|
|
```
ClientPolicyDefaultPhoto
```

||
|
```
ClientPolicyDefaultPhotoDisableSkypeUI
```

|Falsa  <br/> |
|
```
ClientPolicyNoIMURL
```

||
|
```
ClientPolicyNoIMURLDisableSkypeUI
```

|Falsa  <br/> |
|
```
ClientPolicyNoIMURLPhoto
```

||
|
```
ClientPolicyNoIMURLPhotoDisableSkypeUI
```

|Falsa  <br/> |
|
```
ClientPolicyNoSaveIMNoArchivingI
```

||
|
```
ClientPolicyNoSaveIMNoArchivingDisableSkypeUI
```

|Falsa  <br/> |
|
```
ClientPolicyNoSaveIMNoArchivingNoIMURL
```

||
|
```
ClientPolicyNoSaveIMNoArchivingNoIMURLDisableSkypeUI
```

|Falsa  <br/> |
|
```
ClientPolicyNoSaveIMNoArchivingNoIMURLPhoto
```

||
|
```
ClientPolicyNoSaveIMNoArchivingNoIMURLPhotoDisableSkypeUI
```

|Falsa  <br/> |
|
```
ClientPolicyNoSaveIMNoArchivingPhoto
```

||
|
```
ClientPolicyNoSaveIMNoArchivingPhotoDisableSkypeUI
```

|Falsa  <br/> |
   
Para empezar a utilizar Windows PowerShell, consulte estos temas:
  
- [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365]( https://go.microsoft.com/fwlink/?LinkId=525041)
    
- [Las mejores formas de administrar Office 365 con Windows PowerShell]( https://go.microsoft.com/fwlink/?LinkId=525142)
    
## Comportamientos de los clientes al iniciarse por primera vez

De forma predeterminada, cuando los usuarios inician Skype Empresarial por primera vez, siempre verán la interfaz de usuario de Skype Empresarial, incluso si han seleccionado la experiencia del cliente Lync estableciendo la directiva de cliente en la experiencia de cliente Lync ( `Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI`) como se ha descrito anteriormente. Después de varios minutos, se les solicitará a los usuarios que cambien al modo Lync.
  
Si desea mostrar la interfaz de usuario de Lync cuando los usuarios inician el cliente Skype Empresarial por primera vez, siga estos pasos antes de que el cliente se inicie por primera vez después de la actualización:
  
1. Siga los pasos descritos anteriormente en este tema y confirme que la directiva de cliente está configurada para deshabilitar la interfaz de usuario de Skype Empresarial.
    
2. Actualice el registro del sistema en el equipo del usuario. Hágalo una sola vez antes de que los usuarios inicien el cliente Skype Empresarial por primera vez. Para obtener información sobre cómo crear un objeto de directiva de grupo para actualizar el registro en un equipo unido a un dominio, consulte la sección correspondiente en este mismo tema.
    
    En la clave **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\Lync]**, cree un nuevo valor **Binario**. 
    
    El **Nombre del valor** debe ser **EnableSkypeUI** y los **Datos del valor** deben configurarse como **00 00 00 00**.
    
    La clave debería ser similar a esta:
    
> [HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\Lync]
    
    "CanSharePptInCollab" =dword:00000001
    
    "CanShareOneNoteInCollab"=dword:00000001
    
    "CanAppShareInCollab"=dword:00000001
    
    "EnableSkypeUI"=hex:00,00,00,00
    
La interfaz de usuario de Lync se mostrará ahora cuando los usuarios inicien el cliente Skype Empresarial por primera vez.
  
### Controlar la visualización del tutorial de la pantalla de inicio de sesión

Cuando los usuarios abren el cliente Skype Empresarial, el comportamiento predeterminado consiste en mostrar una pantalla de inicio de sesión que incluye  *7 consejos rápidos que la mayoría de las personas solicitan*  . Puede desactivar la visualización de la pantalla de inicio de sesión, pero puede permitir que los usuarios sigan teniendo acceso al tutorial agregando el siguiente valor de registro en el equipo del cliente:
  
En la clave **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\15.0 \\Lync]**, cree un nuevo **valor DWORD (32 bits)**. El **Nombre del valor** debe ser **IsBasicTutorialSeenByUser**y los **Datos del valor** deben configurarse como **1**.
  
La clave debería ser similar a esta:
  
```
"IsBasicTutorialSeenByUser"=dword:00000001
```

### Desactivar el tutorial del cliente

Si no desea que los usuarios puedan tener acceso al tutorial, puede desactivar el tutorial del cliente con el siguiente valor de registro:
  
En la clave **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\15.0 \\Lync]**, cree un nuevo **valor DWORD (32 bits)**. El **Nombre del valor** debe ser **TutorialFeatureEnabled**y los **Datos del valor** deben configurarse como **0**.
  
```
"TutorialFeatureEnabled"=dword:00000000
```

Puede volver a activar el tutorial configurando los **Datos del valor** como **1**.
  
## Crear un objeto de directiva de grupo para modificar el registro en un equipo unido a un dominio

La actualización del registro para visualizar la experiencia de cliente Lync la primera vez que el usuario inicia el cliente Skype Empresarial debe realizarse solo una vez. Si utiliza un objeto de directiva de grupo (GPO) para actualizar el registro, es necesario que defina el objeto para crear un nuevo valor en lugar de actualizar los datos de valor. Cuando se aplica el GPO, si el nuevo valor no existe, el GPO lo creará y establecerá los datos del valor en 0.
  
El procedimiento siguiente describe cómo modificar el registro de manera que la experiencia de cliente Lync se muestre la primera vez que el usuario inicie Skype Empresarial. También puede utilizar este procedimiento para actualizar el registro para desactivar el tutorial de la pantalla de inicio de sesión como se ha descrito anteriormente.
  
 **Para crear el GPO**
  
1. Inicie la **Consola de administración de directivas de grupo**.
    
    Para obtener información sobre cómo usar la consola de administración de directivas de grupo, consulte [Consola de administración de directivas de grupo](https://go.microsoft.com/fwlink/?LinkId=532759).
    
2. Haga clic con el botón derecho en el nodo **Objetos de directiva de grupo** y seleccione **Nuevo** en el menú.
    
3. En el diálogo **Nuevo GPO**, escriba un nombre para el GPO, por ejemplo, MakeLyncDefaultUIy haga clic en **Aceptar**.
    
4. Haga clic con el botón derecho en el GPO nuevo que acaba de crear y seleccione **Editar** en el menú.
    
5. En el **Editor de administración de directivas de grupo**, expanda **Configuración de usuario**, expanda **Preferencias**, expanda **Configuración de Windows** y seleccione el nodo **Registro**.
    
6. Haga clic con el botón derecho en el nodo **Registro** y seleccione **Nuevo** > **Elemento de registro**.
    
7. En el diálogo **Nuevas propiedades de registro**, actualice lo siguiente:
    
|**Campo**|**Valor para seleccionar o introducir**|
|:-----|:-----|
|**Acción** <br/> |**Creación** <br/> |
|**Subárbol** <br/> | HKEY_CURRENT_USER <br/> |
|**Ruta de la clave** <br/> |Software\\Microsoft\\Office\\Lync  <br/> |
|**Nombre de valor** <br/> |EnableSkypeUI  <br/> |
|**Tipo de valor** <br/> |REG_BINARY  <br/> |
|**Datos del valor** <br/> |00000000  <br/> |
   
8. Haga clic en **Aceptar** para guardar los cambios y cierre el GPO.
    
A continuación, tendrá que vincular el GPO que ha creado al grupo de usuarios al que desea asignar la política, como una UO.
  
 **Utilizar el GPO para asignar la directiva**
  
1. En la consola de administración de directivas de grupo, haga clic con el botón derecho en la UO a la que desea asignar la directiva y seleccione **Vincular a un GPO existente**.
    
2. En el diálogo **Seleccionar GPO**, seleccione el GPO que ha creado y seleccione **Aceptar**.
    
3. En el equipo del usuario de destino, abra un símbolo del sistema y escriba el comando siguiente:
    
    **gpupdate /target:usuario**
    
    El mensaje "Actualizando directiva..." se muestra mientras se aplica el GPO. Cuando se ha completado, aparece el mensaje "La actualización de la directiva de usuario ha concluido satisfactoriamente".
    
4. En el símbolo del sistema, escriba el siguiente comando:
    
    **gpresult /r**
    
    Debería ver "Objetos de directiva de grupo asignados" con el nombre del GPO que creó mostrado a continuación.
    
También puede comprobar que el GPO ha actualizado correctamente el registro en el equipo del usuario al examinar el registro. Abra el Editor del Registro y vaya a la clave **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\Lync]**. Si el GPO ha actualizado correctamente el registro, verá un valor denominado EnableSkypeUI con un valor de 0.
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Declinación de responsabilidades de traducción automática**: Este artículo se ha traducido con un sistema informático sin intervención humana. Microsoft ofrece estas traducciones automáticas para que los hablantes de otros idiomas distintos del inglés puedan disfrutar del contenido sobre los productos, los servicios y las tecnologías de Microsoft. Puesto que este artículo se ha traducido con traducción automática, es posible que contenga errores de vocabulario, sintaxis o gramática. 
  

