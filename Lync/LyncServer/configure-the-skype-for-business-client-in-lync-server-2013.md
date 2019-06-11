---
title: Configurar el cliente de Skype empresarial en Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure the client experience
ms:assetid: 61e783f1-24f4-430b-ae52-c76a4d206dc7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn954919(v=OCS.15)
ms:contentKeyID: 65227958
ms.date: 09/18/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5fa863fd1775fbc2a726806f2dd4fff5fed5dbfd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842777"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-client-experience-with-skype-for-business"></a>Configure the client experience with Skype for Business

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2015-09-17_

**Resumen:** En este tema se describe cómo configurar la experiencia de cliente para los usuarios de clientes de Skype empresarial en un entorno de Lync Server 2013. Puede configurar la experiencia de cliente solo si está ejecutando Lync Server 2013 con la actualización acumulativa de diciembre de 2014 (5.0.8308.857) o una versión posterior instalada. Para obtener más información sobre cómo actualizar Lync Server 2013, vea [actualizaciones para Lync server 2013](http://go.microsoft.com/fwlink/p/?linkid=532651).

Skype empresarial ofrece una nueva experiencia de usuario que se basa en la experiencia de producto de consumo de Skype. Además de todas las características de Lync, Skype empresarial proporciona nuevas características con controles simplificados y iconos conocidos. Para obtener información detallada sobre la nueva experiencia del cliente, vea [Lync ahora es Skype empresarial: vea](http://go.microsoft.com/fwlink/?linkid=529022)las novedades.

Lync Server 2013 admite la nueva experiencia de cliente de Skype empresarial, así como la experiencia del cliente de Lync. Como administrador, puede elegir la experiencia de cliente preferida para sus usuarios. Por ejemplo, es posible que desee implementar la experiencia del cliente de Lync hasta que los usuarios de su organización estén completamente capacitados en la nueva experiencia de Skype empresarial. O bien, si aún no ha actualizado todos los usuarios a Skype empresarial Server 2015, es posible que quiera que todos los usuarios tengan la misma experiencia de cliente hasta que se actualicen al nuevo servidor.

<div>


> [!IMPORTANT]  
> Si su organización tiene implementadas las versiones de Skype empresarial Server 2015 y de Lync Server 2013, la experiencia del cliente predeterminada variará según las versiones del servidor y la configuración de la interfaz de usuario. Cuando los usuarios inicien Skype empresarial por primera vez, verán siempre la interfaz de usuario de Skype empresarial, aunque haya seleccionado la interfaz de usuario de Lync. Después de varios minutos, se pide a los usuarios que cambien al modo de Lync. Para más información, vea <STRONG>Comportamiento del cliente en el primer inicio</STRONG> más adelante en este tema.



</div>

<div>


> [!NOTE]  
> La experiencia de cliente de Lync 2013 no es una opción para las versiones de cliente de Skype empresarial 2016. Antes de que intente configurar su entorno de cliente para usar el cliente de Lync 2013, compruebe la versión y asegúrese de que no empieza con el número 16; por ejemplo: 16.x.x.x.



</div>

<div>

## <a name="configure-the-client-experience"></a>Configure the client experience

Puede especificar la experiencia del cliente que verán los usuarios de su organización mediante el cmdlet **set-ClientPolicy** con el parámetro EnableSkypeUI. El siguiente comando selecciona la experiencia del cliente de Skype empresarial para todos los usuarios de su organización afectados por la directiva global (Recuerde que las directivas específicas del sitio o del usuario invalidan la directiva global):

    Set-CsClientPolicy -Identity Global -EnableSkypeUI $true

El siguiente comando selecciona la experiencia del cliente de Lync para todos los usuarios de su organización afectados por la directiva global:

    Set-CsClientPolicy -Identity Global -EnableSkypeUI $false

El siguiente comando selecciona la experiencia del cliente de Skype empresarial para todos los usuarios del sitio de Redmond:

    Set-CsClientPolicy -Identity site:Redmond -EnableSkypeUI $true

Si desea configurar la experiencia de cliente para usuarios específicos de su organización, puede crear una nueva Directiva de usuario con el cmdlet **New-ClientPolicy** y, a continuación, asignar la Directiva a usuarios específicos mediante la **concesión-ClientPolicy** cmdlet.

Por ejemplo, el siguiente comando crea una nueva Directiva de cliente, SalesClientUI, que selecciona la experiencia de cliente de Skype empresarial:

    New-CsClientPolicy -Identity SalesClientUI -EnableSkypeUI $true

El siguiente comando asigna la directiva SalesClientUI a todos los miembros del departamento de Ventas:

    Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesClientUI

</div>

<div>

## <a name="first-launch-client-behaviors"></a>Comportamientos del cliente en el primer inicio

De forma predeterminada, cuando los usuarios inician Skype empresarial por primera vez, siempre verán la interfaz de usuario de Skype empresarial, aunque haya seleccionado la experiencia del cliente de Lync al establecer el valor del parámetro EnableSkypeUI en $False según se describe anteriormente. . Después de varios minutos, se les solicitará a los usuarios que cambien al modo Lync.

Si desea mostrar la interfaz de usuario de Lync cuando los usuarios inician el cliente Skype Empresarial por primera vez, siga estos pasos antes de que el cliente se inicie por primera vez después de la actualización:

1.  Confirme que el valor de `EnableSkypeUI` se establece en $false de la Directiva que está usando como se ha descrito anteriormente.

2.  Actualice el registro del sistema en el equipo del usuario. Hágalo una sola vez antes de que los usuarios inicien el cliente Skype Empresarial por primera vez. Para obtener información sobre cómo crear un objeto de directiva de grupo para actualizar el registro en un equipo unido a un dominio, consulte la sección correspondiente en este mismo tema.
    
    En la ** \[clave\_del software HKEY\\current\\\_User\\software\] de Microsoft Office\\Lync** , cree un nuevo valor **binario** .
    
    El **Nombre del valor** debe ser **EnableSkypeUI** y los **Datos del valor** deben configurarse como **00 00 00 00**.
    
    La clave debería ser similar a esta:
    
        [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]
        "CanSharePptInCollab"=dword:00000001
        "CanShareOneNoteInCollab"=dword:00000001
        "CanAppShareInCollab"=dword:00000001
        "EnableSkypeUI"=hex:00,00,00,00

La interfaz de usuario de Lync se mostrará ahora cuando los usuarios inicien el cliente Skype Empresarial por primera vez.

<div>

## <a name="control-the-display-of-the-welcome-screen-tutorial"></a>Tutorial sobre controlar cómo se muestra la pantalla de bienvenida

Cuando los usuarios abren el cliente de Skype empresarial, el comportamiento predeterminado es mostrar una pantalla de bienvenida que incluye *7 consejos rápidos que la mayoría de las personas solicitan*. Puede desactivar la visualización de la pantalla de inicio de sesión, pero puede permitir que los usuarios sigan teniendo acceso al tutorial agregando el siguiente valor de registro en el equipo del cliente:

En la clave del ** \[\_software HKEY\\current\\\_User\\software\\de\] Microsoft Office\\15,0 Lync** , cree un nuevo **valor de DWORD (32 bits)**. El **Nombre del valor** debe ser **IsBasicTutorialSeenByUser**y los **Datos del valor** deben configurarse como **1**.

La clave debería ser similar a esta:

    "IsBasicTutorialSeenByUser"=dword:00000001

</div>

<div>

## <a name="turn-off-the-client-tutorial"></a>Desactivar el tutorial del cliente

Si no desea que los usuarios puedan tener acceso al tutorial, puede desactivar el tutorial del cliente con el siguiente valor de registro:

En la clave del ** \[\_software HKEY\\current\\\_User\\software\\de\] Microsoft Office\\15,0 Lync** , cree un nuevo **valor de DWORD (32 bits)**. El **Nombre del valor** debe ser **TutorialFeatureEnabled**y los **Datos del valor** deben configurarse como **0**.

    "TutorialFeatureEnabled"=dword:00000000

Puede volver a activar el tutorial configurando los **Datos del valor** como **1**.

</div>

</div>

<div>

## <a name="default-client-experiences"></a>Experiencias de cliente predeterminadas

Si su organización tiene instalados tanto Skype empresarial Server 2015 como Lync Server, la experiencia del cliente será diferente según las versiones del servidor y la configuración de la interfaz de usuario de Skype. La tabla siguiente muestra la experiencia de cliente inicial en función de la versión del servidor y la configuración de la interfaz de usuario:


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
<th><p>Experiencia del cliente</p></th>
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
<td><p>El usuario solicitó cambiar al modo de Lync (el usuario puede cambiar a Skype empresarial más adelante si cambia la configuración de la interfaz de usuario a $true)</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2010 o Lync Server 2013 (con las revisiones correctas)</p></td>
<td><p>Valor predeterminado</p></td>
<td><p>El usuario solicitó cambiar al modo de Lync (el usuario puede cambiar a Skype empresarial más adelante si cambia la configuración de la interfaz de usuario a $true)</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2010 o Lync Server 2013 (con las revisiones correctas)</p></td>
<td><p>True</p></td>
<td><p>Skype Empresarial</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2010 o Lync Server 2013 (con las revisiones correctas)</p></td>
<td><p>False</p></td>
<td><p>El usuario solicitó cambiar al modo de Lync (el usuario puede cambiar a Skype empresarial más adelante si cambia la configuración de la interfaz de usuario a $true)</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2010 o Lync Server 2013 (sin revisiones)</p></td>
<td><p>Valor predeterminado</p></td>
<td><p>El usuario solicitó cambiar a la experiencia del cliente de Lync (el usuario no puede cambiar a Skype empresarial más tarde)</p></td>
</tr>
</tbody>
</table>


La siguiente tabla muestra la experiencia del cliente cuando el administrador cambia la configuración inicial para la experiencia de la interfaz de usuario de Skype:


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
<th><p>Configuración de la interfaz de usuario de Skype</p></th>
<th><p>Interfaz de usuario de cliente = Lync</p></th>
<th><p>IU del cliente = Skype Empresarial</p></th>
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
<td><p>IU de Lync</p></td>
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
<td><p>IU de Lync</p></td>
<td><p>El usuario solicitó cambiar a la interfaz de usuario de Lync</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2010 o Lync Server 2013 (sin revisiones)</p></td>
<td><p>Valor predeterminado</p></td>
<td><p>Modo de Lync (no se puede cambiar a Skype empresarial)</p></td>
<td><p>Interfaz de usuario de Lync (no se puede cambiar a Skype empresarial)</p></td>
</tr>
</tbody>
</table>


Las versiones de parche necesarias para administrar la configuración del cliente de Skype empresarial son las siguientes:

  - Lync Server 2010: actualización acumulativa de febrero de 2015 (4.0.7577.710) para Lync Server 2010. Para obtener más información, consulte [actualizaciones para Lync Server 2010](http://go.microsoft.com/fwlink/p/?linkid=532771)

  - Lync Server 2013-diciembre 2014 actualización acumulativa (5.0.8308.857) para Lync Server 2013. Para obtener más información, consulte [actualizaciones para Lync Server 2013](http://go.microsoft.com/fwlink/p/?linkid=532772).

</div>

<div>

## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a>Crear un objeto de directiva de grupo para modificar el registro en un equipo unido a un dominio

La actualización del registro para visualizar la experiencia de cliente Lync la primera vez que el usuario inicia el cliente Skype Empresarial debe realizarse solo una vez. Si utiliza un objeto de directiva de grupo (GPO) para actualizar el registro, es necesario que defina el objeto para crear un nuevo valor en lugar de actualizar los datos de valor. Cuando se aplica el GPO, si el nuevo valor no existe, el GPO lo creará y establecerá los datos del valor en 0.

El procedimiento siguiente describe cómo modificar el registro de manera que la experiencia de cliente Lync se muestre la primera vez que el usuario inicie Skype Empresarial. También puede utilizar este procedimiento para actualizar el registro para desactivar el tutorial de la pantalla de inicio de sesión como se ha descrito anteriormente.

**Para crear el GPO**

1.  Inicie la **Consola de administración de directivas de grupo**.
    
    Para obtener información acerca de cómo usar la consola de administración de directivas de grupo, consulte [Consola de administración de directivas de grupo](http://go.microsoft.com/fwlink/?linkid=532759).

2.  Haga clic con el botón derecho en el nodo **Objetos de directiva de grupo** y seleccione **Nuevo** en el menú.

3.  En el diálogo **Nuevo GPO**, escriba un nombre para el GPO, por ejemplo, **MakeLyncDefaultUI** y, luego, haga clic en **Aceptar**.

4.  Haga clic con el botón secundario en el nuevo GPO que acaba de crear y, luego en el menú, seleccione **Editar**.

5.  En el **Editor de administración de directivas de grupo**, expanda **Configuración de usuario**, expanda **Preferencias**, expanda **Configuración de Windows** y seleccione el nodo **Registro**.

6.  Haga clic con el botón derecho en el nodo **registro** y, después, seleccione **nuevo** \> **elemento del registro**.

7.  En el diálogo **Nuevas propiedades de Registro**, actualice lo siguiente:
    
    
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
    <td><p><strong>Creación</strong></p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Subárbol</strong></p></td>
    <td><p>HKEY_CURRENT_USER</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Ruta de acceso a la clave</strong></p></td>
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
    <td><p><strong>Datos del valor</strong></p></td>
    <td><p>00000000</p></td>
    </tr>
    </tbody>
    </table>


8.  Haga clic en **Aceptar** para guardar los cambios y cierre el GPO.

A continuación, tendrá que vincular el GPO que ha creado al grupo de usuarios al que desea asignar la política, como una UO.

**Para usar el GPO para asignar la Directiva**

1.  En la consola de administración de directivas de grupo, haga clic con el botón derecho en la UO a la que desea asignar la directiva y seleccione **Vincular a un GPO existente**.

2.  En el diálogo **Seleccionar GPO**, seleccione el GPO que ha creado y seleccione **Aceptar**.

3.  En el equipo del usuario de destino, abra un símbolo del sistema y escriba el comando siguiente:
    
    **gpupdate /target:usuario**
    
    El mensaje "Actualizando directiva..." se muestra mientras se aplica el GPO. Cuando se ha completado, aparece el mensaje "La actualización de la directiva de usuario ha concluido satisfactoriamente".

4.  En el símbolo del sistema, escriba el siguiente comando:
    
    **gpresult /r**
    
    Debería ver "Objetos de directiva de grupo asignados" con el nombre del GPO que creó mostrado a continuación.

También puede comprobar que el GPO ha actualizado correctamente el registro en el equipo del usuario al examinar el registro. Abra el editor del registro y vaya a la clave del ** \[\_software\\\\HKEY\\current\] \_User\\de Microsoft Office Lync** . Si el GPO ha actualizado correctamente el registro, verá un valor denominado EnableSkypeUI con un valor de 0.

</div>

</div>

<span> </span>

</div>

</div>

</div>

