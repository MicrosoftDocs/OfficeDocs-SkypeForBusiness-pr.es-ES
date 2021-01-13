---
title: Configurar la experiencia de cliente con Skype Empresarial 2015
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
ms.assetid: 66867a96-ff00-497d-889c-2e908cc384ce
description: 'Resumen: lea este tema para obtener información sobre cómo configurar la experiencia de cliente para los usuarios de Skype Empresarial.'
ms.openlocfilehash: 2125f911927bfe1aa8898c89c6ad70439186a8c0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805960"
---
# <a name="configure-the-client-experience-with-skype-for-business-2015"></a>Configurar la experiencia de cliente con Skype Empresarial 2015
 
**Resumen:** Lea este tema para obtener información sobre cómo configurar la experiencia de cliente para los usuarios de Skype Empresarial 2015.
  
Skype Empresarial 2015 proporciona una nueva experiencia de usuario basada en la experiencia del producto de consumidor de Skype. Además de todas las características de Lync, Skype Empresarial proporciona nuevas características con controles simplificados e iconos conocidos. Para obtener información detallada sobre la nueva experiencia de cliente, consulte [Explorar Skype Empresarial.](https://go.microsoft.com/fwlink/?LinkId=529022)
  
Skype Empresarial Server admite la nueva experiencia de cliente de Skype Empresarial, así como la experiencia de cliente de Lync. Como administrador, puede elegir la experiencia de cliente preferida para los usuarios. Por ejemplo, es posible que desee implementar la experiencia de cliente lync hasta que los usuarios de su organización estén completamente formados en la nueva experiencia de Skype Empresarial. O bien, si aún no ha actualizado todos los usuarios a Skype Empresarial Server, es posible que desee que todos los usuarios tengan la misma experiencia de cliente hasta que todos se actualicen al nuevo servidor.
  
> [!IMPORTANT]
> Si su organización tiene implementados Skype Empresarial Server y Lync Server, la experiencia de cliente predeterminada variará en función de las versiones del servidor y la configuración de la interfaz de usuario. Cuando los usuarios inician Skype Empresarial por primera vez, siempre verán la interfaz de usuario de Skype Empresarial, incluso si ha seleccionado la experiencia de cliente de Lync. Después de varios minutos, se pide a los usuarios que cambien al modo Lync. Para obtener más información, vea **El comportamiento del cliente del primer inicio** más adelante en este tema.
  
> [!NOTE]
> La experiencia de cliente de Lync 2013 no es una opción para las versiones de cliente de Skype Empresarial 2016 o versiones posteriores. Antes de intentar configurar el entorno de cliente para usar el cliente de Lync 2013, compruebe la versión del cliente para asegurarse de que no comienza con el número 16; por ejemplo: 16.x.x.x. 
  
## <a name="configure-the-client-experience"></a>Configurar la experiencia del cliente

Puede especificar la experiencia de cliente que verán los usuarios de su organización con el cmdlet **Set-CSClientPolicy** con el parámetro EnableSkypeUI:
  
```powershell
Set-CsClientPolicy  [-Identity <XdsIdentity] [-EnableSkypeUI <$true | $false>]
```

donde XdsIdentity hace referencia a la directiva Global o a una directiva de sitio con nombre.
  
El siguiente comando selecciona la experiencia de cliente de Skype Empresarial para todos los usuarios de su organización afectados por la directiva global (recuerde que las directivas específicas del sitio o del usuario invalidan la directiva global): 
  
```powershell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $true
```

El siguiente comando selecciona la experiencia de cliente lync para todos los usuarios de la organización afectados por la directiva global:
  
```powershell
Set-CsClientPolicy -Identity Global -EnableSkypeUI $false
```

El siguiente comando selecciona la experiencia de cliente de Skype Empresarial para todos los usuarios del sitio Redmond:
  
```powershell
Set-CsClientPolicy -Identity site:Redmond -EnableSkypeUI $true
```

Si desea configurar la experiencia de cliente para usuarios específicos de su organización, puede crear una nueva directiva de usuario con el cmdlet **New-CsClientPolicy** y, a continuación, asignar la directiva a usuarios específicos mediante el cmdlet **Grant-CsClientPolicy.**
  
Por ejemplo, el siguiente comando crea una nueva directiva de cliente, SalesClientUI, que selecciona la experiencia de cliente de Skype Empresarial:
  
```powershell
New-CsClientPolicy -Identity SalesClientUI -EnableSkypeUI $true
```

El siguiente comando asigna la directiva, SalesClientUI, a todos los miembros del departamento de ventas:
  
```powershell
Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesClientUI
```

## <a name="first-launch-client-behaviors"></a>Comportamientos de cliente de primer inicio

De forma predeterminada, cuando los usuarios inician Skype Empresarial 2015 por primera vez, siempre verán la interfaz de usuario de Skype Empresarial, incluso si ha seleccionado la experiencia del cliente Lync estableciendo el valor del parámetro EnableSkypeUI en $False como se describió anteriormente. Después de varios minutos, se pedirá a los usuarios que cambien al modo Lync.
  
Si desea mostrar la interfaz de usuario de Lync cuando los usuarios inician el cliente de Skype Empresarial por primera vez, siga estos pasos antes de que el cliente se inicie por primera vez después de actualizarlo:
  
1. Confirme que el valor de está establecido en $False en la directiva que está usando como  `EnableSkypeUI` se describió anteriormente.
    
2. Actualice el Registro del sistema en el equipo del usuario. Debe hacerlo antes de la primera vez que los usuarios inicien el cliente de Skype Empresarial y solo debe hacerlo una vez. Para obtener información sobre cómo crear un objeto de directiva de grupo para actualizar el Registro en un equipo unido a un dominio, vea la sección más adelante en el tema.
    
    En la **clave [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync],** cree un nuevo **valor** binario.
    
    El **nombre del valor** debe ser **EnableSkypeUI** y los datos **del** valor deben establecerse en **00 00 00 00**.
    
    La clave debe tener el siguiente aspecto:
    
   <pre>
   [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]
   "CanSharePptInCollab"=dword:00000001
   "CanShareOneNoteInCollab"=dword:00000001
   "CanAppShareInCollab"=dword:00000001
   "EnableSkypeUI"=hex:00,00,00,00
   </pre>

La interfaz de usuario de Lync se mostrará ahora cuando los usuarios inicien el cliente de Skype Empresarial por primera vez.
  
### <a name="control-the-display-of-the-welcome-screen-tutorial"></a>Controlar la presentación del tutorial de la pantalla de bienvenida

Cuando los usuarios abren el cliente de Skype Empresarial, el comportamiento predeterminado es mostrar una pantalla de bienvenida que incluye 7 sugerencias rápidas que la mayoría de los usuarios *piden.* Puede desactivar la presentación de la pantalla de bienvenida, pero permitir a los usuarios tener acceso al tutorial agregando el siguiente valor del Registro en el equipo cliente:
  
En la **clave [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync],** cree un nuevo **valor DWORD (32 bits).** El **nombre del valor** debe ser **IsBasicTutorialSeenByUser** y los datos **del** valor deben establecerse en **1**.
  
La clave debe tener el siguiente aspecto:
  
`"IsBasicTutorialSeenByUser"=dword:00000001`

### <a name="turn-off-the-client-tutorial"></a>Desactivar el tutorial de cliente

Si no desea que los usuarios puedan tener acceso al tutorial, puede desactivar el tutorial de cliente con el siguiente valor del Registro:
  
En la **clave [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync],** cree un nuevo **valor DWORD (32 bits).** El **nombre del valor** debe ser **TutorialFeatureEnabled** y los datos **del** valor deben establecerse en **0**.
  
Lync
  
```console
"TutorialFeatureEnabled"=dword:00000000
```

Puede volver a activar el tutorial estableciendo los datos **de valor** **en 1**.
  
## <a name="default-client-behaviors"></a>Comportamientos de cliente predeterminados

Si su organización tiene implementados Skype Empresarial Server y Lync Server, la experiencia del cliente variará según las versiones del servidor y la configuración de la interfaz de usuario de Skype. En la tabla siguiente se muestra la experiencia de cliente inicial basada en la versión del servidor y la configuración de la interfaz de usuario:
  

|**Versión del servidor**|**Configuración de EnableSkypeUI**|**Experiencia del cliente**|
|:-----|:-----|:-----|
|Skype Empresarial Server |Predeterminado  <br/> |Skype Empresarial  <br/> |
|Skype Empresarial Server  |Verdadero  <br/> |Skype Empresarial  <br/> |
|Skype Empresarial Server  |False  <br/> |Usuario al que se le pide que cambie al modo Lync (el usuario puede cambiar a Skype Empresarial más adelante si cambia la configuración de la interfaz de usuario a $true)  <br/> |
|Lync Server 2010 o Lync Server 2013 (con revisiones correctas)  <br/> |Predeterminado  <br/> |Usuario al que se le pide que cambie al modo Lync (el usuario puede cambiar a Skype Empresarial más adelante si cambia la configuración de la interfaz de usuario a $true)  <br/> |
|Lync Server 2010 o Lync Server 2013 (con revisiones correctas)  <br/> |Verdadero  <br/> |Skype Empresarial  <br/> |
|Lync Server 2010 o Lync Server 2013 (con revisiones correctas)  <br/> |False  <br/> |Usuario al que se le pide que cambie al modo Lync (el usuario puede cambiar a Skype Empresarial más adelante si cambia la configuración de la interfaz de usuario a $true)  <br/> |
|Lync Server 2010 o Lync Server 2013 (sin revisiones)  <br/> |Predeterminado  <br/> |Usuario al que se le pide que cambie al modo Lync (el usuario no puede cambiar a Skype Empresarial más adelante)  <br/> |
   
En la siguiente tabla se muestra la experiencia del cliente cuando el administrador cambia la configuración inicial de la experiencia de la interfaz de usuario de Skype:
  

|**Versión del servidor**|**Configuración de EnableSkypeUI**|**Interfaz de usuario de cliente = Lync**|**Interfaz de usuario de cliente = Skype Empresarial**|
|:-----|:-----|:-----|:-----|
|Skype Empresarial Server |Verdadero  <br/> |Usuario al que se le pide que cambie a Skype Empresarial  <br/> |Skype Empresarial  <br/> |
|Skype Empresarial Server |False  <br/> |Modo Lync  <br/> |Usuario al que se le pide que cambie al modo Lync  <br/> |
|Lync Server 2010 o Lync Server 2013 (con revisiones correctas)  <br/> |Verdadero  <br/> |Usuario al que se le pide que cambie a Skype Empresarial  <br/> |Skype Empresarial  <br/> |
|Lync Server 2010 o Lync Server 2013 (con revisiones correctas)  <br/> |False  <br/> |Modo Lync  <br/> |Usuario al que se le pide que cambie al modo Lync  <br/> |
|Lync Server 2010 o Lync Server 2013 (sin revisiones)  <br/> |Predeterminado  <br/> |Modo Lync (no se puede cambiar a Skype Empresarial)  <br/> |Modo Lync (no se puede cambiar a Skype Empresarial)  <br/> |
   
Las versiones de revisión necesarias para administrar la configuración del cliente de Skype Empresarial son:
  
- Lync Server 2010- Actualización acumulativa de febrero de 2015 (4.0.7577.710) para Lync Server 2010. Para obtener información, consulte [Actualizaciones de Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532771)
    
- Lync Server 2013- Actualización acumulativa de diciembre de 2014 (5.0.8308.857) para Lync Server 2013. Para obtener información, [consulte Actualizaciones de Lync Server 2013.](https://go.microsoft.com/fwlink/p/?LinkId=532772)
    
## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a>Crear un objeto de directiva de grupo para modificar el Registro en un equipo unido a un dominio

La actualización del Registro para mostrar la experiencia del cliente Lync la primera vez que un usuario inicia el cliente de Skype Empresarial 2015 solo debe realizarse una vez. Si usas un objeto de directiva de grupo (GPO) para actualizar el Registro, debes definir el objeto para crear un nuevo valor en lugar de actualizar los datos del valor. Cuando se aplica el GPO, si el nuevo valor no existe, el GPO lo creará y establecerá los datos del valor en 0. 
  
El siguiente procedimiento describe cómo modificar el Registro para que la experiencia del cliente Lync se muestre la primera vez que un usuario inicie el cliente de Skype Empresarial 2015. También puede usar este procedimiento para actualizar el Registro para deshabilitar el tutorial de pantalla de bienvenida, como se describió anteriormente.
  
### <a name="to-create-the-gpo"></a>Para crear el GPO

1. Inicie la consola **de administración de directivas de grupo.**
    
    Para obtener información sobre cómo usar la Consola de administración de directivas de grupo, consulte [Consola de administración de directivas de grupo.](https://go.microsoft.com/fwlink/?LinkId=532759)
    
2. Haga clic con el botón secundario en el **nodo Objetos de directiva** de grupo y seleccione **Nuevo** en el menú.
    
3. En el cuadro de diálogo Nuevo **GPO,** escriba un nombre para el GPO, por ejemplo, MakeLyncDefaultUI y, a continuación, haga clic en **Aceptar**.
    
4. Haga clic con el botón secundario en el nuevo GPO que acaba de crear y, a continuación, **seleccione Editar** en el menú.
    
5. En el **Editor de administración de directivas** de grupo, expanda Configuración de usuario, Preferencias, Configuración de **Windows** y, a continuación, seleccione **el nodo del** Registro.  
    
6. Haga clic con el botón secundario en **el nodo registro** y, a continuación, seleccione Nuevo **elemento** del  >  **Registro.**
    
7. En el **cuadro de diálogo Nuevas propiedades del** Registro, actualice lo siguiente:
    
   |**Field**|**Valor para seleccionar o escribir**|
   |:-----|:-----|
   |**Acción** <br/> |**Crear** <br/> |
   |**Subárbol** <br/> | HKEY_CURRENT_USER <br/> |
   |**Ruta de acceso de teclas** <br/> |Software\Microsoft\Office\Lync  <br/> |
   |**Nombre del valor** <br/> |EnableSkypeUI  <br/> |
   |**Tipo de valor** <br/> |REG_BINARY  <br/> |
   |**Value data** <br/> |00000000  <br/> |
   
8. Haga **clic en** Aceptar para guardar los cambios y, a continuación, cierre el GPO.
    
A continuación, tendrás que vincular el GPO que creaste al grupo de usuarios a los que quieres asignar la directiva, como una ou.
  
### <a name="to-use-the-gpo-to-assign-the-policy"></a>Para usar el GPO para asignar la directiva

1. En la Consola de administración de directivas de grupo, haga clic con el botón secundario en la unidad organizativa a la que desea asignar la directiva y, a continuación, seleccione Vincular **a un GPO existente.**
    
2. En el **cuadro de diálogo Seleccionar GPO,** seleccione el GPO que creó y, a continuación, seleccione **Aceptar**.
    
3. En el equipo del usuario de destino, abra un símbolo del sistema y escriba el siguiente comando:
       
```console
gpupdate /target:user
```

    
    The message "Updating policy..." is displayed while the GPO is applied. When it is completed, the message "User Policy update has completed successfully" is displayed.
    
4. En el símbolo del sistema, escriba el siguiente comando:
    
    **gpresult /r**
    
    Debería ver "Objetos de directiva de grupo asignados" con el nombre del GPO que creó que se muestra a continuación.
    
También puede comprobar que el GPO ha actualizado correctamente el Registro en el equipo de un usuario examinando el Registro. Abra el Editor del Registro y vaya a **la clave [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync].** Si el GPO actualizó correctamente el Registro, verá un valor denominado EnableSkypeUI con un valor de 0.
  

