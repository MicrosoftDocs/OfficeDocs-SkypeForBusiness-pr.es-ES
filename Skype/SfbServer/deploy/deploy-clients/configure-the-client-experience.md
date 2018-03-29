---
title: Configurar la experiencia del cliente con Skype Empresarial
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 66867a96-ff00-497d-889c-2e908cc384ce
description: 'Resumen: Leer este tema para aprender a configurar la experiencia del cliente de Skype para usuarios de negocios.'
ms.openlocfilehash: 9c1bc182c383ea7d806ce779f3d727e7925a59d4
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="configure-the-client-experience-with-skype-for-business"></a>Configurar la experiencia del cliente con Skype Empresarial
 
**Resumen:** Lea este tema para aprender a configurar la experiencia del cliente de Skype para usuarios de negocios.
  
Skype para empresas proporciona una nueva experiencia de usuario que se basa en la experiencia de producto del consumidor de Skype. Además de todas las características de Lync, Skype para empresas proporciona nuevas características con controles simplificados y los iconos que ya conoce. Para obtener información detallada acerca de la nueva experiencia de cliente, consulte [Lync es ahora Skype para Business & #x 2014; consulte Novedades](https://go.microsoft.com/fwlink/?LinkId=529022).
  
Skype para Business Server es compatible con el nuevo Skype para la experiencia del cliente de negocios, así como la experiencia del cliente Lync. Como administrador, puede elegir la experiencia de cliente preferida para sus usuarios. Por ejemplo, que desea implementar la experiencia del cliente Lync hasta que los usuarios de su organización están plenamente capacitados en el nuevo Skype para la experiencia del negocio. O, si aún no ha actualizado los todos los usuarios a Skype para Business Server, todos los usuarios tengan la misma experiencia de cliente hasta que todos se actualicen al nuevo servidor.
  
> [!IMPORTANT]
> Si su organización tiene ambos Skype para Business Server e implementar Lync Server, la experiencia de cliente predeterminada variarán en función de las versiones de servidor y configuración de la interfaz de usuario. Cuando los usuarios iniciar Skype para el negocio por primera vez, siempre verán la Skype para la interfaz de usuario de negocio--incluso si ha seleccionado la experiencia del cliente Lync. Después de varios minutos, se solicita a los usuarios para cambiar al modo de Lync. Para más información, vea **Comportamiento del cliente en el primer inicio** más adelante en este tema.
  
> [!NOTE]
> La experiencia del cliente Lync 2013 no es una opción de Skype para versiones de cliente de empresa 2016. Antes de que intente configurar su entorno de cliente para usar el cliente de Lync 2013, compruebe la versión y asegúrese de que no empieza con el número 16; por ejemplo: 16.x.x.x. 
  
## <a name="configure-the-client-experience"></a>Configurar la experiencia del cliente

Puede especificar la experiencia que tendrán los usuarios de su organización mediante el cmdlet **Set-CSClientPolicy** y el parámetro EnableSkypeUI:
  
```
Set-CsClientPolicy  [-Identity <XdsIdentity] [-EnableSkypeUI <$true | $false>]
```

donde XdsIdentity se refiere a la directiva Global o a una directiva de sitio.
  
El comando siguiente selecciona el Skype para la experiencia del cliente empresarial para todos los usuarios de la organización afectada por la directiva Global (Recuerde, sitio o directivas específicas de usuario reemplaza la directiva Global): 
  
```
Set-CsClientPolicy -Identity Global -EnableSkypeUI $true
```

El comando siguiente selecciona la experiencia del cliente Lync para todos los usuarios de la organización afectada por la directiva Global:
  
```
Set-CsClientPolicy -Identity Global -EnableSkypeUI $false
```

El comando siguiente selecciona el Skype para la experiencia del cliente empresarial para todos los usuarios en el sitio de Redmond:
  
```
Set-CsClientPolicy -Identity site:Redmond -EnableSkypeUI $true
```

Si desea configurar la experiencia del cliente para usuarios específicos dentro de su organización, puede crear una nueva directiva de usuario mediante el cmdlet **New-CsClientPolicy** y después asigne la directiva a usuarios específicos mediante el uso de la **Concesión CsClientPolicy** cmdlet.
  
Por ejemplo, el siguiente comando crea una nueva directiva de cliente, SalesClientUI, que selecciona el Skype para la experiencia del cliente empresarial:
  
```
New-CsClientPolicy -Identity SalesClientUI -EnableSkypeUI $true
```

El siguiente comando asigna la directiva SalesClientUI a todos los miembros del departamento de Ventas:
  
```
Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesClientUI
```

## <a name="first-launch-client-behaviors"></a>Comportamientos del cliente en el primer inicio

De forma predeterminada, cuando los usuarios iniciar Skype para el negocio por primera vez, siempre verán la Skype para la interfaz de usuario de negocio--incluso si ha seleccionado la experiencia del cliente Lync estableciendo el valor del parámetro EnableSkypeUI en $False, como se describió anteriormente . Después de varios minutos, se les solicitará a los usuarios que cambien al modo Lync.
  
Si desea mostrar la interfaz de usuario de Lync cuando los usuarios inician el cliente Skype Empresarial por primera vez, siga estos pasos antes de que el cliente se inicie por primera vez después de la actualización:
  
1. Confirme que el valor de `EnableSkypeUI` se establece en $False en la directiva que se está utilizando como se describió anteriormente.
    
2. Actualice el registro del sistema en el equipo del usuario. Hágalo una sola vez antes de que los usuarios inicien el cliente Skype Empresarial por primera vez. Para obtener información sobre cómo crear un objeto de directiva de grupo para actualizar el registro en un equipo unido a un dominio, consulte la sección correspondiente en este mismo tema.
    
    En la clave **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]**, cree un valor **Binario**.
    
    El **Nombre del valor** debe ser **EnableSkypeUI** y los **Datos del valor** deben configurarse como **00 00 00 00**.
    
    La clave debería ser similar a esta:
    
  ```
  [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]
"CanSharePptInCollab"=dword:00000001
"CanShareOneNoteInCollab"=dword:00000001
"CanAppShareInCollab"=dword:00000001
"EnableSkypeUI"=hex:00,00,00,00
  ```

La interfaz de usuario de Lync se mostrará ahora cuando los usuarios inicien el cliente Skype Empresarial por primera vez.
  
### <a name="control-the-display-of-the-welcome-screen-tutorial"></a>Controlar la visualización del tutorial de la pantalla de inicio de sesión

Cuando los usuarios abren el cliente Skype Empresarial, el comportamiento predeterminado consiste en mostrar una pantalla de inicio de sesión que incluye  *7 consejos rápidos que la mayoría de las personas solicitan*  . Puede desactivar la visualización de la pantalla de inicio de sesión, pero puede permitir que los usuarios sigan teniendo acceso al tutorial agregando el siguiente valor de registro en el equipo del cliente:
  
En la clave **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]**, cree un **valor DWORD (32 bits)**. Es preciso que el **Nombre del valor** sea **IsBasicTutorialSeenByUser** y que los **Datos del valor** se establezcan en **1**.
  
La clave debería ser similar a esta:
  
```
"IsBasicTutorialSeenByUser"=dword:00000001
```

### <a name="turn-off-the-client-tutorial"></a>Desactivar el tutorial del cliente

Si no desea que los usuarios puedan tener acceso al tutorial, puede desactivar el tutorial del cliente con el siguiente valor de registro:
  
En la clave **[HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync]**, cree un **valor DWORD (32 bits)**. Es preciso que el **Nombre del valor** sea **TutorialFeatureEnabled** y que los **Datos del valor** se establezcan en **0**.
  
Lync
  
```
"TutorialFeatureEnabled"=dword:00000000
```

Puede volver a activar el tutorial al configurar los **Datos del valor** en **1**.
  
## <a name="default-client-behaviors"></a>Comportamientos predeterminados de los clientes

Si su organización tiene ambos Skype para Business Server e implementar Lync Server, la experiencia del cliente variarán en función de las versiones de servidor y la UI de Skype configuración. La tabla siguiente muestra la experiencia de cliente inicial en función de la versión del servidor y la configuración de la interfaz de usuario:
  

|**Versión del servidor**|**Configuración de EnableSkypeUI**|**Experiencia del cliente**|
|:-----|:-----|:-----|
|Skype Empresarial Server 2015  <br/> |Predeterminado  <br/> |Skype Empresarial  <br/> |
|Skype Empresarial Server 2015  <br/> |Verdadero  <br/> |Skype Empresarial  <br/> |
|Skype Empresarial Server 2015  <br/> |Falso  <br/> |Pregunta de usuario cambiar al modo de Lync (usuario puede pasar a Skype para empresas más tarde si cambia la configuración de la interfaz de usuario en $true)  <br/> |
|Lync Server 2010 o Lync Server 2013 (con correcciones correctos)  <br/> |Predeterminado  <br/> |Pregunta de usuario cambiar al modo de Lync (usuario puede pasar a Skype para empresas más tarde si cambia la configuración de la interfaz de usuario en $true)  <br/> |
|Lync Server 2010 o Lync Server 2013 (con correcciones correctos)  <br/> |Verdadero  <br/> |Skype Empresarial  <br/> |
|Lync Server 2010 o Lync Server 2013 (con correcciones correctos)  <br/> |Falso  <br/> |Pregunta de usuario cambiar al modo de Lync (usuario puede pasar a Skype para empresas más tarde si cambia la configuración de la interfaz de usuario en $true)  <br/> |
|Lync Server 2010 o Lync Server 2013 (sin revisiones)  <br/> |Predeterminado  <br/> |Pregunta de usuario cambiar al modo de Lync (el usuario no puede cambiar a Skype para empresas más adelante)  <br/> |
   
La tabla siguiente muestra la experiencia del cliente cuando el administrador cambia la configuración inicial de la experiencia de Skype UI:
  

|**Versión del servidor**|**Configuración de EnableSkypeUI**|**IU de cliente = Lync**|**IU de cliente = Skype para empresas**|
|:-----|:-----|:-----|:-----|
|Skype Empresarial Server 2015  <br/> |Verdadero  <br/> |Pregunta de usuario cambiar a Skype para empresas  <br/> |Skype Empresarial  <br/> |
|Skype Empresarial Server 2015  <br/> |Falso  <br/> |Modo de Lync  <br/> |Pregunta de usuario cambiar al modo de Lync  <br/> |
|Lync Server 2010 o Lync Server 2013 (con correcciones correctos)  <br/> |Verdadero  <br/> |Pregunta de usuario cambiar a Skype para empresas  <br/> |Skype Empresarial  <br/> |
|Lync Server 2010 o Lync Server 2013 (con correcciones correctos)  <br/> |Falso  <br/> |Modo de Lync  <br/> |Pregunta de usuario cambiar al modo de Lync  <br/> |
|Lync Server 2010 o Lync Server 2013 (sin revisiones)  <br/> |Predeterminado  <br/> |Modo de Lync (no puede cambiar a Skype para empresas)  <br/> |Modo de Lync (no puede cambiar a Skype para empresas)  <br/> |
   
Las versiones de revisión necesarias para administrar la configuración de la Skype para Business client son:
  
- Lync Server 2010 - actualización acumulativa de febrero de 2015 (4.0.7577.710) de Lync Server 2010. Para obtener información, vea [versiones de Lync Server 2010](https://go.microsoft.com/fwlink/p/?LinkId=532771)
    
- Lync Server 2013 - actualización acumulativa de diciembre de 2014 (5.0.8308.857) para Lync Server 2013. Para obtener información, vea [versiones de Lync Server 2013](https://go.microsoft.com/fwlink/p/?LinkId=532772).
    
## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a>Crear un objeto de directiva de grupo para modificar el registro en un equipo unido a un dominio

La actualización del registro para visualizar la experiencia de cliente Lync la primera vez que el usuario inicia el cliente Skype Empresarial debe realizarse solo una vez. Si utiliza un objeto de directiva de grupo (GPO) para actualizar el registro, es necesario que defina el objeto para crear un nuevo valor en lugar de actualizar los datos de valor. Cuando se aplica el GPO, si el nuevo valor no existe, el GPO lo creará y establecerá los datos del valor en 0. 
  
El procedimiento siguiente describe cómo modificar el registro de manera que la experiencia de cliente Lync se muestre la primera vez que el usuario inicie Skype Empresarial. También puede utilizar este procedimiento para actualizar el registro para desactivar el tutorial de la pantalla de inicio de sesión como se ha descrito anteriormente.
  
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
    
    **gpupdate /target:usuario**
    
    El mensaje "Actualizando directiva..." se muestra mientras se aplica el GPO. Cuando se ha completado, aparece el mensaje "La actualización de la directiva de usuario ha concluido satisfactoriamente".
    
4. En el símbolo del sistema, escriba el siguiente comando:
    
    **gpresult /r**
    
    Junto con el nombre del GPO que creó verá abajo "Objetos de directiva de grupo asignados".
    
Asimismo, puede comprobar si el GPO ha actualizado correctamente el registro en el equipo de un usuario al examinar el registro. Para ello, abra el Editor del Registro y diríjase a la clave **[HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]**. Si el GPO ha actualizado correctamente el registro, verá el valor denominado EnableSkypeUI con un valor de 0.
  

