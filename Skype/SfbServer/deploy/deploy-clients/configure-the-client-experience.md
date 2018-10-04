---
title: Configurar la experiencia del cliente con Skype para profesionales de 2015
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 66867a96-ff00-497d-889c-2e908cc384ce
description: 'Resumen: Lea este tema para obtener información sobre cómo configurar la experiencia del cliente de Skype para los usuarios empresariales.'
ms.openlocfilehash: 9e2a7d53788eda36fc18cb9094cde096864ce2ba
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25375361"
---
# <a name="configure-the-client-experience-with-skype-for-business-2015"></a>Configurar la experiencia del cliente con Skype para profesionales de 2015
 
**Resumen:** Lea este tema para obtener información sobre cómo configurar la experiencia del cliente de Skype para los usuarios empresariales 2015.
  
Skype para profesionales de 2015 proporciona una experiencia de usuario nuevo que se basa en la experiencia de producto de consumidor de Skype. Además de todas las características de Lync, Skype para la empresa proporciona nuevas características con controles simplificados y los iconos que ya conoce. Para obtener información detallada acerca de la nueva experiencia del cliente, vea [Explore Skype para la empresa](https://go.microsoft.com/fwlink/?LinkId=529022).
  
Skype para Business Server es compatible con el nuevo Skype para la experiencia del cliente empresarial, así como la experiencia del cliente Lync. Como administrador, puede elegir la experiencia de cliente preferida para sus usuarios. Por ejemplo, es posible que desee implementar la experiencia del cliente Lync hasta que los usuarios de su organización están capacitados totalmente en la nueva Skype para que la experiencia empresarial. O bien, si no ha actualizado aún todos los usuarios a Skype para Business Server, es posible que desea que todos los usuarios tengan la misma experiencia de cliente hasta que todos se actualizan al nuevo servidor.
  
> [!IMPORTANT]
> Si su organización tiene ambos Skype para Business Server y a implementar Lync Server, la experiencia del cliente predeterminado variarán en función de las versiones de servidor y la configuración de la interfaz de usuario. Cuando los usuarios iniciar Skype para la empresa por primera vez, siempre verán la Skype para la interfaz de usuario de negocio--incluso si ha seleccionado la experiencia del cliente Lync. Después de varios minutos, se piden a los usuarios para cambiar al modo de Lync. Para más información, vea **Comportamiento del cliente en el primer inicio** más adelante en este tema.
  
> [!NOTE]
> La experiencia del cliente Lync 2013 no es una opción de Skype para versiones de cliente de 2016 empresarial o posterior. Antes de que intente configurar su entorno de cliente para usar el cliente de Lync 2013, compruebe la versión y asegúrese de que no empieza con el número 16; por ejemplo: 16.x.x.x. 
  
## <a name="configure-the-client-experience"></a>Configurar la experiencia del cliente

Puede especificar la experiencia que tendrán los usuarios de su organización mediante el cmdlet **Set-CSClientPolicy** y el parámetro EnableSkypeUI:
  
```
Set-CsClientPolicy  [-Identity <XdsIdentity] [-EnableSkypeUI <$true | $false>]
```

donde XdsIdentity se refiere a la directiva Global o a una directiva de sitio.
  
El comando siguiente selecciona la Skype para la experiencia del cliente empresarial para todos los usuarios de la organización afectada por la directiva Global (Recuerde, sitio o directivas específicas de usuario invalidación la directiva Global): 
  
```
Set-CsClientPolicy -Identity Global -EnableSkypeUI $true
```

El comando siguiente selecciona la experiencia del cliente Lync para todos los usuarios de la organización afectada por la directiva Global:
  
```
Set-CsClientPolicy -Identity Global -EnableSkypeUI $false
```

El comando siguiente selecciona la Skype para la experiencia del cliente empresarial para todos los usuarios dentro del sitio de Redmond:
  
```
Set-CsClientPolicy -Identity site:Redmond -EnableSkypeUI $true
```

Si desea configurar la experiencia del cliente para usuarios específicos dentro de la organización, puede crear una nueva directiva de usuario mediante el cmdlet **New-CsClientPolicy** y, a continuación, asigne la directiva a usuarios específicos mediante la **Grant-CsClientPolicy** cmdlet.
  
Por ejemplo, el siguiente comando crea una nueva directiva de cliente, SalesClientUI, que selecciona el Skype para la experiencia del cliente empresarial:
  
```
New-CsClientPolicy -Identity SalesClientUI -EnableSkypeUI $true
```

El siguiente comando asigna la directiva SalesClientUI a todos los miembros del departamento de Ventas:
  
```
Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesClientUI
```

## <a name="first-launch-client-behaviors"></a>Comportamientos del cliente en el primer inicio

De forma predeterminada, cuando los usuarios iniciar Skype para 2015 empresarial por primera vez, siempre verán la Skype para la interfaz de usuario de negocio--incluso si ha seleccionado la experiencia del cliente Lync estableciendo el valor del parámetro EnableSkypeUI en $False, tal como se describe anteriormente. Después de varios minutos, se les solicitará a los usuarios que cambien al modo Lync.
  
Si desea mostrar la interfaz de usuario de Lync cuando los usuarios inician el cliente Skype Empresarial por primera vez, siga estos pasos antes de que el cliente se inicie por primera vez después de la actualización:
  
1. Confirme que el valor de `EnableSkypeUI` está establecido en $False en la directiva que está utilizando como se describió anteriormente.
    
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
  
### <a name="control-the-display-of-the-welcome-screen-tutorial"></a>Controlar la visualización del tutorial de la pantalla de inicio de sesión

Cuando los usuarios abren la Skype para clientes empresariales, el comportamiento predeterminado es mostrar una pantalla de bienvenida que incluye la *mayoría de las personas formular a 7 sugerencias rápidas para*. Puede desactivar la visualización de la pantalla de inicio de sesión, pero puede permitir que los usuarios sigan teniendo acceso al tutorial agregando el siguiente valor de registro en el equipo del cliente:
  
En la clave **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]**, cree un **valor DWORD (32 bits)**. Es preciso que el **Nombre del valor** sea **IsBasicTutorialSeenByUser** y que los **Datos del valor** se establezcan en **1**.
  
La clave debería ser similar a esta:
  
`"IsBasicTutorialSeenByUser"=dword:00000001`

### <a name="turn-off-the-client-tutorial"></a>Desactivar el tutorial del cliente

Si no desea que los usuarios puedan tener acceso al tutorial, puede desactivar el tutorial del cliente con el siguiente valor de registro:
  
En la clave **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]**, cree un **valor DWORD (32 bits)**. Es preciso que el **Nombre del valor** sea **TutorialFeatureEnabled** y que los **Datos del valor** se establezcan en **0**.
  
Lync
  
```
"TutorialFeatureEnabled"=dword:00000000
```

Puede volver a activar el tutorial al configurar los **Datos del valor** en **1**.
  
## <a name="default-client-behaviors"></a>Comportamientos predeterminados de los clientes

Si su organización tiene ambos Skype para Business Server y a implementar Lync Server, la experiencia del cliente variarán en función de las versiones de servidor y la UI de Skype configuración. La tabla siguiente muestra la experiencia de cliente inicial en función de la versión del servidor y la configuración de la interfaz de usuario:
  

|**Versión del servidor**|**Configuración de EnableSkypeUI**|**Experiencia del cliente**|
|:-----|:-----|:-----|
|Skype Empresarial Server |Predeterminado  <br/> |Skype Empresarial  <br/> |
|Skype Empresarial Server  |Verdadero  <br/> |Skype Empresarial  <br/> |
|Skype Empresarial Server  |Falso  <br/> |Usuario más frecuentes cambiar al modo de Lync (el usuario puede cambiar a Skype para la empresa más adelante si cambia la configuración de la interfaz de usuario en $true)  <br/> |
|Lync Server 2010 o Lync Server 2013 (con correcciones correctos)  <br/> |Predeterminado  <br/> |Usuario más frecuentes cambiar al modo de Lync (el usuario puede cambiar a Skype para la empresa más adelante si cambia la configuración de la interfaz de usuario en $true)  <br/> |
|Lync Server 2010 o Lync Server 2013 (con correcciones correctos)  <br/> |Verdadero  <br/> |Skype Empresarial  <br/> |
|Lync Server 2010 o Lync Server 2013 (con correcciones correctos)  <br/> |Falso  <br/> |Usuario más frecuentes cambiar al modo de Lync (el usuario puede cambiar a Skype para la empresa más adelante si cambia la configuración de la interfaz de usuario en $true)  <br/> |
|Lync Server 2010 o Lync Server 2013 (sin revisiones)  <br/> |Predeterminado  <br/> |Usuario más frecuentes cambiar al modo de Lync (el usuario no puede cambiar a Skype para la empresa más adelante)  <br/> |
   
En la tabla siguiente muestra la experiencia del cliente cuando el administrador cambia la configuración inicial para la experiencia de Skype UI:
  

|**Versión del servidor**|**Configuración de EnableSkypeUI**|**La interfaz de usuario de cliente = Lync**|**IU del cliente = Skype Empresarial**|
|:-----|:-----|:-----|:-----|
|Skype Empresarial Server |Verdadero  <br/> |Usuario que se le pida que cambie a Skype para la empresa  <br/> |Skype Empresarial  <br/> |
|Skype Empresarial Server |Falso  <br/> |Modo de Lync  <br/> |Usuario más frecuentes cambiar al modo de Lync  <br/> |
|Lync Server 2010 o Lync Server 2013 (con correcciones correctos)  <br/> |Verdadero  <br/> |Usuario que se le pida que cambie a Skype para la empresa  <br/> |Skype Empresarial  <br/> |
|Lync Server 2010 o Lync Server 2013 (con correcciones correctos)  <br/> |Falso  <br/> |Modo de Lync  <br/> |Usuario más frecuentes cambiar al modo de Lync  <br/> |
|Lync Server 2010 o Lync Server 2013 (sin revisiones)  <br/> |Predeterminado  <br/> |Modo de Lync (no se puede cambiar a Skype para la empresa)  <br/> |Modo de Lync (no se puede cambiar a Skype para la empresa)  <br/> |
   
Las versiones de revisión necesarias para administrar la configuración de la Skype para clientes empresariales son:
  
- Lync Server 2010 - actualización acumulativa de febrero de 2015 (4.0.7577.710) para Lync Server 2010. Para obtener información, vea [actualizaciones de Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532771)
    
- Lync Server 2013 - actualización acumulativa de diciembre de 2014 (5.0.8308.857) para Lync Server 2013. Para obtener información, vea [actualizaciones de Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532772).
    
## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a>Crear un objeto de directiva de grupo para modificar el registro en un equipo unido a un dominio

La actualización del registro para mostrar la experiencia del cliente Lync la primera vez que un usuario inicia la Skype para cliente empresarial 2015 debe realizarse sólo una vez. Si utiliza un objeto de directiva de grupo (GPO) para actualizar el registro, es necesario que defina el objeto para crear un nuevo valor en lugar de actualizar los datos de valor. Cuando se aplica el GPO, si el nuevo valor no existe, el GPO lo creará y establecerá los datos del valor en 0. 
  
El siguiente procedimiento describe cómo modificar el registro para que la experiencia del cliente Lync se muestra la primera vez que un usuario inicia la Skype para cliente empresarial 2015. También puede usar este procedimiento para actualizar el registro para deshabilitar el tutorial de la pantalla de inicio de sesión como se ha descrito anteriormente.
  
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
    
A continuación, tendrá que vincular el GPO que ha creado al grupo de usuarios al que desea asignar la política, como una UO.
  
### <a name="to-use-the-gpo-to-assign-the-policy"></a>Utilizar el GPO para asignar la directiva

1. En la consola de administración de directivas de grupo, haga clic con el botón derecho en la UO a la que desea asignar la directiva y seleccione **Vincular a un GPO existente**.
    
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
  

