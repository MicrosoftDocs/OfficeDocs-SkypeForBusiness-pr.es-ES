---
title: Configurar el cliente de Skype empresarial en Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure the client experience
ms:assetid: 61e783f1-24f4-430b-ae52-c76a4d206dc7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn954919(v=OCS.15)
ms:contentKeyID: 65227958
ms.date: 09/18/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5bd70d0f37dbed8a38994af6dc806556380484b5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006616"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-client-experience-with-skype-for-business"></a>Configurar la experiencia de cliente con Skype empresarial

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2015-09-17_

**Resumen:** En este tema se describe cómo configurar la experiencia de cliente para los usuarios del cliente de Skype empresarial en un entorno de Lync Server 2013. Puede configurar la experiencia de cliente solo si está ejecutando Lync Server 2013 con la actualización acumulativa de diciembre de 2014 (5.0.8308.857) o una versión posterior instalada. Para obtener información acerca de la actualización de Lync Server 2013, consulte [actualizaciones para Lync server 2013](http://go.microsoft.com/fwlink/p/?linkid=532651).

Skype empresarial proporciona una nueva experiencia de usuario que se basa en la experiencia del producto de consumo de Skype. Además de todas las características de Lync, Skype empresarial proporciona nuevas características con controles simplificados e iconos conocidos. Para obtener información detallada sobre la nueva experiencia del cliente, consulte [Lync ahora es Skype empresarial: vea](http://go.microsoft.com/fwlink/?linkid=529022)las novedades.

Lync Server 2013 admite la nueva experiencia de cliente de Skype empresarial y la experiencia de cliente de Lync. Como administrador, puede elegir la experiencia de cliente preferida para los usuarios. Por ejemplo, es posible que desee implementar la experiencia del cliente de Lync hasta que los usuarios de su organización se hayan entrenado completamente en la nueva experiencia de Skype empresarial. O bien, si aún no ha actualizado todos los usuarios a Skype empresarial Server 2015, es posible que quiera que todos los usuarios tengan la misma experiencia de cliente hasta que se actualicen todos al nuevo servidor.

<div>


> [!IMPORTANT]  
> Si su organización tiene implementado tanto Skype empresarial Server 2015 como Lync Server 2013, la experiencia de cliente predeterminada será distinta en función de las versiones del servidor y la configuración de la interfaz de usuario. Cuando los usuarios inicien Skype empresarial por primera vez, siempre verán la interfaz de usuario de Skype empresarial, incluso si ha seleccionado la interfaz de usuario de Lync. Después de varios minutos, se pide a los usuarios que cambien al modo Lync. Para obtener más información, vea <STRONG>comportamiento del cliente del primer inicio</STRONG> más adelante en este tema.



</div>

<div>


> [!NOTE]  
> La experiencia de cliente de Lync 2013 no es una opción para las versiones de cliente de Skype empresarial 2016. Antes de intentar configurar el entorno del cliente para usar el cliente Lync 2013, Compruebe la versión del cliente para asegurarse de que no empieza con el número 16; por ejemplo: 16. x.x.x.



</div>

<div>

## <a name="configure-the-client-experience"></a>Configurar la experiencia del cliente

Puede especificar la experiencia de cliente que verán los usuarios de la organización mediante el cmdlet **set-CSClientPolicy** con el parámetro EnableSkypeUI. El siguiente comando selecciona la experiencia de cliente de Skype empresarial para todos los usuarios de la organización afectados por la directiva global (Recuerde que las directivas específicas de sitio o usuario invalidan la directiva global):

    Set-CsClientPolicy -Identity Global -EnableSkypeUI $true

El siguiente comando selecciona la experiencia del cliente Lync para todos los usuarios de su organización afectados por la directiva global:

    Set-CsClientPolicy -Identity Global -EnableSkypeUI $false

El siguiente comando selecciona la experiencia de cliente de Skype empresarial para todos los usuarios del sitio de Redmond:

    Set-CsClientPolicy -Identity site:Redmond -EnableSkypeUI $true

Si desea configurar la experiencia de cliente para determinados usuarios de la organización, puede crear una nueva Directiva de usuario con el cmdlet **New-CsClientPolicy** y, a continuación, asignar la Directiva a usuarios específicos mediante el cmdlet **Grant-CsClientPolicy** .

Por ejemplo, el siguiente comando crea una nueva Directiva de cliente, SalesClientUI, que selecciona la experiencia de cliente de Skype empresarial:

    New-CsClientPolicy -Identity SalesClientUI -EnableSkypeUI $true

El comando siguiente asigna la Directiva, SalesClientUI, a todos los miembros del Departamento de ventas:

    Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesClientUI

</div>

<div>

## <a name="first-launch-client-behaviors"></a>Comportamiento del primer inicio del cliente

De forma predeterminada, cuando los usuarios inician Skype empresarial por primera vez, siempre verán la interfaz de usuario de Skype empresarial, incluso si ha seleccionado la experiencia del cliente Lync estableciendo el valor del parámetro EnableSkypeUI en $False como se describió anteriormente. . Después de varios minutos, se le pedirá a los usuarios que cambien al modo Lync.

Si desea mostrar la interfaz de usuario de Lync cuando los usuarios inicien el cliente de Skype empresarial por primera vez, siga estos pasos antes de que se inicie el cliente por primera vez tras la actualización:

1.  Confirme que el valor de `EnableSkypeUI` se establece en $false en la Directiva que está usando como se describió anteriormente.

2.  Actualice el registro del sistema en el equipo del usuario. Debe hacer esto antes de la primera vez que los usuarios inicien el cliente de Skype empresarial y debe hacerlo solo una vez. Para obtener información sobre cómo crear un objeto de directiva de grupo para actualizar el registro en un equipo unido a un dominio, vea la sección más adelante en este tema.
    
    En la clave del ** \[software\\\\de usuario\\actual\\\_\_de\] HKEY Microsoft Office Lync** , cree un nuevo valor **binario** .
    
    El **nombre del valor** debe ser **EnableSkypeUI**y los **datos del valor** deben establecerse en **00 00 00 00**.
    
    La clave debe ser similar a la siguiente:
    
        [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]
        "CanSharePptInCollab"=dword:00000001
        "CanShareOneNoteInCollab"=dword:00000001
        "CanAppShareInCollab"=dword:00000001
        "EnableSkypeUI"=hex:00,00,00,00

La interfaz de usuario de Lync se mostrará ahora cuando los usuarios inicien el cliente de Skype empresarial por primera vez.

<div>

## <a name="control-the-display-of-the-welcome-screen-tutorial"></a>Controlar la visualización del tutorial de la pantalla de bienvenida

Cuando los usuarios abren el cliente de Skype empresarial, el comportamiento predeterminado es mostrar una pantalla de bienvenida que incluye *7 Sugerencias rápidas que la mayoría de las personas solicitan*. Puede desactivar la pantalla de bienvenida pero seguir permitiendo a los usuarios obtener acceso al tutorial agregando el siguiente valor del registro en el equipo cliente:

En la clave de ** \[Microsoft\_\_\\\\Office\\\\15,0\\Lync\] del software HKEY current user** , cree un nuevo **valor DWORD (32 bits)**. El **nombre del valor** debe ser **isbasictutorialseenbyusery**y los **datos del valor** deben establecerse en **1**.

La clave debe ser similar a la siguiente:

    "IsBasicTutorialSeenByUser"=dword:00000001

</div>

<div>

## <a name="turn-off-the-client-tutorial"></a>Desactivar el tutorial del cliente

Si no desea que los usuarios puedan obtener acceso al tutorial, puede desactivar el tutorial del cliente con el siguiente valor del registro:

En la clave de ** \[Microsoft\_\_\\\\Office\\\\15,0\\Lync\] del software HKEY current user** , cree un nuevo **valor DWORD (32 bits)**. El **nombre del valor** debe ser **tutorialfeatureenabledy**y los **datos del valor** deben establecerse en **0**.

    "TutorialFeatureEnabled"=dword:00000000

Puede volver a activar el tutorial si establece los **datos del valor** en **1**.

</div>

</div>

<div>

## <a name="default-client-experiences"></a>Experiencias de cliente predeterminadas

Si su organización tiene instalado Skype empresarial Server 2015 y Lync Server, la experiencia del cliente será distinta en función de las versiones del servidor y de la configuración de la interfaz de usuario de Skype. En la siguiente tabla se muestra la experiencia de cliente inicial en función de la versión del servidor y la configuración de la interfaz de usuario:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Versión del servidor</p></th>
<th><p>Configuración de EnableSkypeUI</p></th>
<th><p>Experiencia de cliente</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Skype Empresarial Server 2015</p></td>
<td><p>Valor predeterminado</p></td>
<td><p>Skype Empresarial</p></td>
</tr>
<tr class="even">
<td><p>Skype Empresarial Server 2015</p></td>
<td><p>True</p></td>
<td><p>Skype Empresarial</p></td>
</tr>
<tr class="odd">
<td><p>Skype Empresarial Server 2015</p></td>
<td><p>False</p></td>
<td><p>El usuario solicitó cambiar al modo Lync (el usuario puede cambiar a Skype empresarial más adelante si cambia la configuración de la interfaz de usuario a $true)</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2010 o Lync Server 2013 (con las revisiones correctas)</p></td>
<td><p>Valor predeterminado</p></td>
<td><p>El usuario solicitó cambiar al modo Lync (el usuario puede cambiar a Skype empresarial más adelante si cambia la configuración de la interfaz de usuario a $true)</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2010 o Lync Server 2013 (con las revisiones correctas)</p></td>
<td><p>True</p></td>
<td><p>Skype Empresarial</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2010 o Lync Server 2013 (con las revisiones correctas)</p></td>
<td><p>False</p></td>
<td><p>El usuario solicitó cambiar al modo Lync (el usuario puede cambiar a Skype empresarial más adelante si cambia la configuración de la interfaz de usuario a $true)</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2010 o Lync Server 2013 (sin revisiones)</p></td>
<td><p>Valor predeterminado</p></td>
<td><p>El usuario solicitó cambiar a la experiencia de cliente de Lync (el usuario no puede cambiar a Skype empresarial más adelante)</p></td>
</tr>
</tbody>
</table>


La siguiente tabla muestra la experiencia de cliente cuando el administrador cambia la configuración inicial para la experiencia de la interfaz de usuario de Skype:


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Versión del servidor</p></th>
<th><p>Configuración de UI de Skype</p></th>
<th><p>Interfaz de usuario de cliente = Lync</p></th>
<th><p>Interfaz de usuario de cliente = Skype empresarial</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Skype Empresarial Server 2015</p></td>
<td><p>True</p></td>
<td><p>El usuario solicitó cambiar a Skype empresarial</p></td>
<td><p>Skype Empresarial</p></td>
</tr>
<tr class="even">
<td><p>Skype Empresarial Server 2015</p></td>
<td><p>False</p></td>
<td><p>Interfaz de usuario de Lync</p></td>
<td><p>El usuario solicitó cambiar a la interfaz de usuario de Lync</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2010 o Lync Server 2013 (con las revisiones correctas)</p></td>
<td><p>True</p></td>
<td><p>El usuario solicitó cambiar a Skype empresarial</p></td>
<td><p>Skype Empresarial</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2010 o Lync Server 2013 (con las revisiones correctas)</p></td>
<td><p>False</p></td>
<td><p>Interfaz de usuario de Lync</p></td>
<td><p>El usuario solicitó cambiar a la interfaz de usuario de Lync</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2010 o Lync Server 2013 (sin revisiones)</p></td>
<td><p>Valor predeterminado</p></td>
<td><p>Modo Lync (no se puede cambiar a Skype empresarial)</p></td>
<td><p>Interfaz de usuario de Lync (no se puede cambiar a Skype empresarial)</p></td>
</tr>
</tbody>
</table>


Las versiones de revisión necesarias para administrar la configuración del cliente de Skype empresarial son:

  - Lync Server 2010-actualización acumulativa de febrero de 2015 (4.0.7577.710) para Lync Server 2010. Para obtener más información, consulte [actualizaciones para Lync Server 2010](http://go.microsoft.com/fwlink/p/?linkid=532771)

  - Lync Server 2013-actualización acumulativa de diciembre de 2014 (5.0.8308.857) para Lync Server 2013. Para obtener más información, consulte [actualizaciones para Lync Server 2013](http://go.microsoft.com/fwlink/p/?linkid=532772).

</div>

<div>

## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a>Crear un objeto de directiva de grupo para modificar el registro en un equipo unido a un dominio

La actualización del registro para mostrar la experiencia del cliente de Lync la primera vez que un usuario inicia el cliente de Skype empresarial solo debe realizarse una vez. Si usa un objeto de directiva de grupo (GPO) para actualizar el registro, debe definir el objeto para crear un nuevo valor en lugar de actualizar los datos del valor. Cuando se aplica el GPO, si el nuevo valor no existe, el GPO lo creará y establecerá los datos del valor en 0.

El siguiente procedimiento describe cómo modificar el registro para que la experiencia de cliente de Lync se muestre la primera vez que un usuario inicie Skype empresarial. También puede usar este procedimiento para actualizar el registro para deshabilitar el tutorial de la pantalla de bienvenida como se describió anteriormente.

**Para crear el GPO**

1.  Inicie la **consola de administración de directivas de grupo**.
    
    Para obtener información acerca de cómo usar la consola de administración de directivas de grupo, consulte [consola de administración de directivas de grupo](http://go.microsoft.com/fwlink/?linkid=532759).

2.  Haga clic con el botón secundario en el nodo **objetos de directiva de grupo** y seleccione **nuevo** en el menú.

3.  En el cuadro de diálogo **nuevo GPO** , escriba un nombre para el GPO, por ejemplo, **makelyncdefaultuiy**y, a continuación, haga clic en **Aceptar**.

4.  Haga clic con el botón secundario en el nuevo GPO que acaba de crear y, a continuación, seleccione **Editar** en el menú.

5.  En el **Editor de administración de directivas de grupo**, expanda **configuración de usuario**, **Opciones**, expanda **configuración de Windows**y, a continuación, seleccione el nodo **registro** .

6.  Haga clic con el botón secundario en el nodo **registro** y seleccione **nuevo** \> **elemento del registro**.

7.  En el cuadro de diálogo **nuevas propiedades del registro** , actualice lo siguiente:
    
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Campo</th>
    <th>Valor para seleccionar o escribir</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><strong>Acción</strong></p></td>
    <td><p><strong>Crear</strong></p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Subárbol</strong></p></td>
    <td><p>HKEY_CURRENT_USER</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Ruta de acceso de la clave</strong></p></td>
    <td><p>Software\Microsoft\Office\Lync</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Nombre del valor</strong></p></td>
    <td><p>EnableSkypeUI</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Tipo de valor</strong></p></td>
    <td><p>REG_BINARY</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Value data</strong></p></td>
    <td><p>00000000</p></td>
    </tr>
    </tbody>
    </table>


8.  Haga clic en **Aceptar** para guardar los cambios y, a continuación, cierre el GPO.

A continuación, tendrá que vincular el GPO que ha creado al grupo de usuarios al que desea asignar la Directiva, como una unidad organizativa (OU).

**Para usar el GPO para asignar la Directiva**

1.  En la consola de administración de directivas de grupo, haga clic con el botón secundario en la unidad organizativa a la que desea asignar la Directiva y, a continuación, seleccione **vincular a un GPO existente**.

2.  En el cuadro de diálogo **seleccionar GPO** , seleccione el GPO que ha creado y, después, haga clic en **Aceptar**.

3.  En el equipo del usuario de destino, abra un símbolo del sistema y escriba el siguiente comando:
    
    **GPUpdate/target: usuario**
    
    El mensaje "actualizando la Directiva..." se muestra mientras se aplica el GPO. Una vez completado, se muestra el mensaje "la actualización de la Directiva de usuario se ha completado correctamente".

4.  En el símbolo del sistema, escriba el siguiente comando:
    
    **Gpresult/r**
    
    Debe ver "objetos de directiva de grupo asignados" con el nombre del GPO que creó mostrado a continuación.

También puede comprobar que el GPO haya actualizado correctamente el registro en el equipo del usuario examinando el registro. Abra el editor del registro y vaya a la clave de ** \[Microsoft\\Office\\Lync\] del software\_\_\\\\HKEY current user** . Si el GPO ha actualizado correctamente el registro, verá un valor denominado EnableSkypeUI con un valor de 0.

</div>

</div>

<span> </span>

</div>

</div>

</div>

