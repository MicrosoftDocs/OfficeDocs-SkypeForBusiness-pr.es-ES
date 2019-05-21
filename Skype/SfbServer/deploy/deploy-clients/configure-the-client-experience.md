---
title: Configurar la experiencia de cliente con Skype empresarial 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 66867a96-ff00-497d-889c-2e908cc384ce
description: 'Resumen: Lea este tema para obtener información sobre cómo configurar la experiencia de cliente para usuarios de Skype empresarial.'
ms.openlocfilehash: bf6245b5b26875c7437990f09dd101ece01b1b47
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34298287"
---
# <a name="configure-the-client-experience-with-skype-for-business-2015"></a>Configurar la experiencia de cliente con Skype empresarial 2015
 
**Resumen:** Lea este tema para obtener información sobre cómo configurar la experiencia de cliente para usuarios de Skype empresarial 2015.
  
Skype empresarial 2015 ofrece una nueva experiencia de usuario que se basa en la experiencia de producto de consumo de Skype. Además de todas las características de Lync, Skype empresarial proporciona nuevas características con controles simplificados y iconos conocidos. Para obtener información detallada sobre la nueva experiencia de cliente, consulte [explorar Skype empresarial](https://go.microsoft.com/fwlink/?LinkId=529022).
  
Skype empresarial Server es compatible con la nueva experiencia de cliente de Skype empresarial, así como con la experiencia del cliente de Lync. Como administrador, puede elegir la experiencia de cliente preferida para sus usuarios. Por ejemplo, es posible que desee implementar la experiencia del cliente de Lync hasta que los usuarios de su organización estén completamente capacitados en la nueva experiencia de Skype empresarial. O bien, si aún no ha actualizado todos los usuarios a Skype empresarial Server, es posible que desee que todos los usuarios tengan la misma experiencia de cliente hasta que todos se actualicen al nuevo servidor.
  
> [!IMPORTANT]
> Si su organización tiene instalado Skype empresarial Server y Lync Server, la experiencia del cliente predeterminada variará según las versiones del servidor y la configuración de la interfaz de usuario. Cuando los usuarios inicien Skype empresarial por primera vez, verán siempre la interfaz de usuario de Skype empresarial, aunque haya seleccionado la experiencia del cliente de Lync. Después de varios minutos, se pide a los usuarios que cambien al modo de Lync. Para más información, vea **Comportamiento del cliente en el primer inicio** más adelante en este tema.
  
> [!NOTE]
> La experiencia de cliente de Lync 2013 no es una opción para las versiones de cliente de Skype empresarial 2016 o posterior. Antes de que intente configurar su entorno de cliente para usar el cliente de Lync 2013, compruebe la versión y asegúrese de que no empieza con el número 16; por ejemplo: 16.x.x.x. 
  
## <a name="configure-the-client-experience"></a>Configurar la experiencia del cliente

Puede especificar la experiencia que tendrán los usuarios de su organización mediante el cmdlet **Set-CSClientPolicy** y el parámetro EnableSkypeUI:
  
```
Set-CsClientPolicy  [-Identity <XdsIdentity] [-EnableSkypeUI <$true | $false>]
```

donde XdsIdentity se refiere a la directiva Global o a una directiva de sitio.
  
El siguiente comando selecciona la experiencia del cliente de Skype empresarial para todos los usuarios de su organización afectados por la directiva global (Recuerde que las directivas específicas del sitio o del usuario invalidan la directiva global): 
  
```
Set-CsClientPolicy -Identity Global -EnableSkypeUI $true
```

El siguiente comando selecciona la experiencia del cliente de Lync para todos los usuarios de su organización afectados por la directiva global:
  
```
Set-CsClientPolicy -Identity Global -EnableSkypeUI $false
```

El siguiente comando selecciona la experiencia del cliente de Skype empresarial para todos los usuarios del sitio de Redmond:
  
```
Set-CsClientPolicy -Identity site:Redmond -EnableSkypeUI $true
```

Si desea configurar la experiencia de cliente para usuarios específicos de su organización, puede crear una nueva Directiva de usuario con el cmdlet **New-ClientPolicy** y, a continuación, asignar la Directiva a usuarios específicos mediante la **concesión-ClientPolicy** cmdlet.
  
Por ejemplo, el siguiente comando crea una nueva Directiva de cliente, SalesClientUI, que selecciona la experiencia de cliente de Skype empresarial:
  
```
New-CsClientPolicy -Identity SalesClientUI -EnableSkypeUI $true
```

El siguiente comando asigna la directiva SalesClientUI a todos los miembros del departamento de Ventas:
  
```
Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesClientUI
```

## <a name="first-launch-client-behaviors"></a>Comportamientos del cliente en el primer inicio

De forma predeterminada, cuando los usuarios inician Skype empresarial 2015 por primera vez, siempre verán la interfaz de usuario de Skype empresarial, aunque haya seleccionado la experiencia del cliente de Lync al establecer el valor del parámetro EnableSkypeUI en $False tal como se describe. eran. Después de varios minutos, se les solicitará a los usuarios que cambien al modo Lync.
  
Si desea mostrar la interfaz de usuario de Lync cuando los usuarios inician el cliente Skype Empresarial por primera vez, siga estos pasos antes de que el cliente se inicie por primera vez después de la actualización:
  
1. Confirme que el valor de `EnableSkypeUI` se establece en $false de la Directiva que está usando como se ha descrito anteriormente.
    
2. Actualice el registro del sistema en el equipo del usuario. Hágalo una sola vez antes de que los usuarios inicien el cliente Skype Empresarial por primera vez. Para obtener información sobre cómo crear un objeto de directiva de grupo para actualizar el registro en un equipo unido a un dominio, consulte la sección correspondiente en este mismo tema.
    
    En la clave **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]**, cree un valor **Binario**.
    
    El **Nombre del valor** debe ser **EnableSkypeUI** y los **Datos del valor** deben configurarse como **00 00 00 00**.
    
    La clave debería ser similar a esta:
    
   <pre>
   [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]
   "CanSharePptInCollab"=dword:00000001
   "CanShareOneNoteInCollab"=dword:00000001
   "CanAppShareInCollab"=dword:00000001
   "EnableSkypeUI"=hex:00,00,00,00
   </pre>

La interfaz de usuario de Lync se mostrará ahora cuando los usuarios inicien el cliente Skype Empresarial por primera vez.
  
### <a name="control-the-display-of-the-welcome-screen-tutorial"></a>Tutorial sobre controlar cómo se muestra la pantalla de bienvenida

Cuando los usuarios abren el cliente de Skype empresarial, el comportamiento predeterminado es mostrar una pantalla de bienvenida que incluye *7 consejos rápidos que la mayoría de las personas solicitan*. Puede desactivar la visualización de la pantalla de inicio de sesión, pero puede permitir que los usuarios sigan teniendo acceso al tutorial agregando el siguiente valor de registro en el equipo del cliente:
  
En la clave **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]**, cree un **valor DWORD (32 bits)**. Es preciso que el **Nombre del valor** sea **IsBasicTutorialSeenByUser** y que los **Datos del valor** se establezcan en **1**.
  
La clave necesita ser similar a la siguiente:
  
`"IsBasicTutorialSeenByUser"=dword:00000001`

### <a name="turn-off-the-client-tutorial"></a>Desactivar el tutorial del cliente

Si no quiere que los usuarios obtengan acceso al tutorial, puede desactivar el tutorial del cliente con el siguiente valor del registro:
  
En la clave **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]**, cree un **valor DWORD (32 bits)**. Es preciso que el **Nombre del valor** sea **TutorialFeatureEnabled** y que los **Datos del valor** se establezcan en **0**.
  
Lync
  
```
"TutorialFeatureEnabled"=dword:00000000
```

Puede volver a activar el tutorial al configurar los **Datos del valor** en **1**.
  
## <a name="default-client-behaviors"></a>Comportamientos predeterminados de los clientes

Si su organización tiene instalado Skype empresarial Server y Lync Server, la experiencia del cliente será distinta según las versiones del servidor y la configuración de la interfaz de usuario de Skype. La tabla siguiente muestra la experiencia de cliente inicial en función de la versión del servidor y la configuración de la interfaz de usuario:
  

|**Versión del servidor**|**Configuración de EnableSkypeUI**|**Experiencia del cliente**|
|:-----|:-----|:-----|
|Skype Empresarial Server |Valor predeterminado  <br/> |Skype Empresarial  <br/> |
|Skype Empresarial Server  |True  <br/> |Skype Empresarial  <br/> |
|Skype Empresarial Server  |False  <br/> |El usuario solicitó cambiar al modo de Lync (el usuario puede cambiar a Skype empresarial más adelante si cambia la configuración de la interfaz de usuario a $true)  <br/> |
|Lync Server 2010 o Lync Server 2013 (con las revisiones correctas)  <br/> |Valor predeterminado  <br/> |El usuario solicitó cambiar al modo de Lync (el usuario puede cambiar a Skype empresarial más adelante si cambia la configuración de la interfaz de usuario a $true)  <br/> |
|Lync Server 2010 o Lync Server 2013 (con las revisiones correctas)  <br/> |True  <br/> |Skype Empresarial  <br/> |
|Lync Server 2010 o Lync Server 2013 (con las revisiones correctas)  <br/> |False  <br/> |El usuario solicitó cambiar al modo de Lync (el usuario puede cambiar a Skype empresarial más adelante si cambia la configuración de la interfaz de usuario a $true)  <br/> |
|Lync Server 2010 o Lync Server 2013 (sin revisiones)  <br/> |Valor predeterminado  <br/> |El usuario solicitó cambiar al modo de Lync (el usuario no puede cambiar a Skype empresarial más tarde)  <br/> |
   
La siguiente tabla muestra la experiencia del cliente cuando el administrador cambia la configuración inicial para la experiencia de la interfaz de usuario de Skype:
  

|**Versión del servidor**|**Configuración de EnableSkypeUI**|**Interfaz de usuario de cliente = Lync**|**IU del cliente = Skype Empresarial**|
|:-----|:-----|:-----|:-----|
|Skype Empresarial Server |True  <br/> |El usuario solicitó cambiar a Skype empresarial  <br/> |Skype Empresarial  <br/> |
|Skype Empresarial Server |False  <br/> |Modo de Lync  <br/> |El usuario solicitó cambiar al modo de Lync  <br/> |
|Lync Server 2010 o Lync Server 2013 (con las revisiones correctas)  <br/> |True  <br/> |El usuario solicitó cambiar a Skype empresarial  <br/> |Skype Empresarial  <br/> |
|Lync Server 2010 o Lync Server 2013 (con las revisiones correctas)  <br/> |False  <br/> |Modo de Lync  <br/> |El usuario solicitó cambiar al modo de Lync  <br/> |
|Lync Server 2010 o Lync Server 2013 (sin revisiones)  <br/> |Valor predeterminado  <br/> |Modo de Lync (no se puede cambiar a Skype empresarial)  <br/> |Modo de Lync (no se puede cambiar a Skype empresarial)  <br/> |
   
Las versiones de parche necesarias para administrar la configuración del cliente de Skype empresarial son las siguientes:
  
- Lync Server 2010: actualización acumulativa de febrero de 2015 (4.0.7577.710) para Lync Server 2010. Para obtener más información, consulte [actualizaciones para Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532771)
    
- Lync Server 2013-diciembre 2014 actualización acumulativa (5.0.8308.857) para Lync Server 2013. Para obtener más información, consulte [actualizaciones para Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532772).
    
## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a>Crear un objeto de directiva de grupo para modificar el registro en un equipo unido a un dominio

La actualización del registro para mostrar la experiencia del cliente de Lync la primera vez que un usuario inicia el cliente de Skype empresarial 2015 solo debe realizarse una vez. Si utiliza un objeto de directiva de grupo (GPO) para actualizar el registro, es necesario que defina el objeto para crear un nuevo valor en lugar de actualizar los datos de valor. Cuando se aplica el GPO, si el nuevo valor no existe, el GPO lo creará y establecerá los datos del valor en 0. 
  
En el procedimiento siguiente se describe cómo modificar el registro para que se muestre la experiencia del cliente de Lync la primera vez que un usuario inicie el cliente de Skype empresarial 2015. También puede usar este procedimiento para actualizar el registro para deshabilitar el tutorial de la pantalla de inicio de sesión como se ha descrito anteriormente.
  
### <a name="to-create-the-gpo"></a>Para crear el GPO

1. Inicie la **Consola de administración de directivas de grupo**.
    
    Para obtener información acerca de cómo usar la consola de administración de directivas de grupo, consulte [Consola de administración de directivas de grupo](https://go.microsoft.com/fwlink/?LinkId=532759).
    
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
   |**Ruta de acceso a la clave** <br/> |Software\Microsoft\Office\Lync  <br/> |
   |**Nombre del valor** <br/> |EnableSkypeUI  <br/> |
   |**Tipo de valor** <br/> |REG_BINARY  <br/> |
   |**Datos del valor** <br/> |00000000  <br/> |
   
8. Haga clic en **Aceptar** para guardar los cambios y cierre el GPO.
    
A continuación, es preciso que vincule el GPO que creó con el grupo de usuarios al que desea asignar la directiva, como una UO.
  
### <a name="to-use-the-gpo-to-assign-the-policy"></a>Para usar el GPO a fin de asignar la directiva

1. En la Consola de administración de directivas de grupo, haga clic con el botón secundario en la UO a la que desea asignar la directiva y, luego, seleccione **Vincular con un GPO existente**.
    
2. En el diálogo **Seleccionar GPO**, seleccione el GPO que ha creado y seleccione **Aceptar**.
    
3. En el equipo del usuario de destino, abra un símbolo del sistema y escriba el comando siguiente:
       
```
gpupdate /target:user
```

    
    The message "Updating policy..." is displayed while the GPO is applied. When it is completed, the message "User Policy update has completed successfully" is displayed.
    
4. En el símbolo del sistema, escriba el siguiente comando:
    
    **gpresult /r**
    
    Junto con el nombre del GPO que creó verá abajo "Objetos de directiva de grupo asignados".
    
Asimismo, puede comprobar si el GPO ha actualizado correctamente el registro en el equipo de un usuario al examinar el registro. Para ello, abra el Editor del Registro y diríjase a la clave **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]**. Si el GPO ha actualizado correctamente el registro, verá el valor denominado EnableSkypeUI con un valor de 0.
  

