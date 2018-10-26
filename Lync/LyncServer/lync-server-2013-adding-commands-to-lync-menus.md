---
title: Agregar comandos a menús de Lync
TOCTitle: Agregar comandos a menús de Lync
ms:assetid: a8443bc2-e234-4022-870a-00700f38b1ea
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg412788(v=OCS.15)
ms:contentKeyID: 52061746
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Agregar comandos a menús de Lync

 

_**Última modificación del tema:** 2016-04-11_

Puede agregar comandos personalizados a los menús de Lync 2013 y enviar el identificador uniforme de recursos (URI) de SIP del usuario actual y de los contactos seleccionados a la aplicación que inicia el comando personalizado.

Los comandos personalizados que usted agrega pueden aparecer en uno o en varios de los menús siguientes:

  - En el menú Herramientas, en la barra de menús en la ventana principal de Lync

  - En el menú contextual de contactos en la lista de contactos

  - En el menú Más opciones, en la ventana Conversación

  - En el menú contextual para las personas que aparecen en la lista de participantes de la ventana Conversación

  - En el menú de opciones de una tarjeta de contacto

Puede definir comandos personalizados para dos tipos de aplicaciones; en definitiva, para las aplicaciones que implican cualquiera de los siguientes supuestos:

  - Se aplican únicamente al usuario actual y se inician en el equipo local.

  - Suponen la participación de usuarios adicionales, como un programa de colaboración en línea, y deben iniciarse en el equipo de cada usuario.

El comando personalizado puede invocarse de las formas siguientes:

  - Seleccione uno o más usuarios y elija el comando personalizado.

  - Inicie una conversación de dos o más participantes y elija el comando personalizado.

## Para agregar un comando personalizado

Use la configuración del Registro indicada en la tabla siguiente para agregar un comando a los menús. Estas entradas se incorporan en el Registro en la ubicación siguiente:

HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Office\\15.0\\Lync\\CustomCommands

### Entradas del Registro de comandos personalizados

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nombre</th>
<th>Tipo</th>
<th>Datos</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Nombre</p></td>
<td><p>REG_SZ</p></td>
<td><p>Nombre de la aplicación tal como aparece en el menú.</p></td>
</tr>
<tr class="even">
<td><p>ApplicationType</p></td>
<td><p>DWORD</p></td>
<td><p>0 = Ejecutable (valor predeterminado)</p>
<div>

> [!NOTE]
> Requiere ApplicationInstallPath.


</div>
<p>1 = Protocolo</p></td>
</tr>
<tr class="odd">
<td><p>ApplicationInstallPath</p></td>
<td><p>REG_SZ</p></td>
<td><p>Ruta de acceso completa del ejecutable.</p>
<div>

> [!NOTE]
> Debe especificarse si ApplicationType es igual a 0 (ejecutable).


</div></td>
</tr>
<tr class="even">
<td><p>Ruta</p></td>
<td><p>REG_SZ</p></td>
<td><p>Ruta de acceso completa que debe iniciarse junto con cualquier parámetro, incluidos los parámetros predeterminados <em>%user-id%</em> y <em>%contact-id%</em>.</p></td>
</tr>
<tr class="odd">
<td><p>SessionType</p></td>
<td><p>DWORD</p></td>
<td><p>0 = Sesión local. La aplicación se inicia en el equipo local.</p>
<p>1 = Sesión entre dos participantes (valor predeterminado). Lync 2013 inicia la aplicación localmente y envía una notificación de escritorio al otro usuario. El otro usuario hace clic en la notificación para iniciar la aplicación en su equipo.</p>
<p>2 = Sesión de varios participantes. Lync 2013 inicia la aplicación localmente y envía notificaciones de escritorio al resto de usuarios. El resto de usuarios hacen en la notificación para iniciar la aplicación especificada en su equipo.</p></td>
</tr>
<tr class="even">
<td><p>ExtensibleMenu</p></td>
<td><p>REG_SZ</p></td>
<td><p>Lista de menús en los que aparecerá este comando, separados por caracteres de punto y coma. Los valores posibles son:</p>
<p>MainWindowActions</p>
<p>MainWindowRightClick</p>
<p>ConversationWindowActions</p>
<p>ConversationWindowRightClick</p>
<p>ContactCardMenu</p>
<p>Si no se define ExtensibleMenu, se utilizan los valores predeterminados de MainWindowRightClick y ConversationWindowActions.</p></td>
</tr>
</tbody>
</table>


Por ejemplo, en el archivo de Editor del Registro (.REG) siguiente se muestran los resultados obtenidos al agregar un elemento de menú del Administrador de contactos de Contoso Sales al menú Acciones en la ventana Conversación:

    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\CustomCommands\{1F9F07C6-7E0B-462B-AAD7-98C6DBEA8F69}]
    "Name"="Contoso Sales Contact Manager"
    "HelpMessage"="The Contoso Sales Contact Manager is not installed. Contact the Help Desk for more information."
    "ApplicationType"=dword:00000000
    "ApplicationInstallPath"="C:\\cscm.exe"
    "Path"="C:\\cscm.exe %user-id% %contact-id%"
    "SessionType"=dword:00000001
    "ExtensibleMenu"="ConversationWindowActions;MainWindowRightClick"

## Para obtener acceso a un comando personalizado

Para obtener acceso a un comando personalizado una vez agregado, siga uno de los métodos siguientes en función de los valores ExtensibleMenu que defina:

  - **MainWindowActions**   En la ventana principal de Lync, haga clic en **Herramientas** y haga clic en el comando personalizado.

  - MainWindowRightClick   En la ventana principal de Lync, haga clic con el botón secundario en un contacto y luego haga clic en el comando personalizado.

  - **ConversationWindowActions**   En la ventana Conversación, haga clic en el icono de **Más opciones** y luego haga clic en el comando personalizado.

  - **ConversationWindowRightClick**   En la ventana Conversación, haga clic con el botón secundario en el nombre de un contacto y haga clic en el comando personalizado.

  - **ContactCardMenu**   En la tarjeta de contacto de una persona, haga clic en el icono de opciones y luego haga clic en el comando personalizado.

