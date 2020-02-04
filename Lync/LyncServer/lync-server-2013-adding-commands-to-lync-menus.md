---
title: 'Lync Server 2013: agregar comandos a los menús de Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Adding commands to Lync menus
ms:assetid: a8443bc2-e234-4022-870a-00700f38b1ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412788(v=OCS.15)
ms:contentKeyID: 48185091
ms.date: 04/11/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1cbce99116159d119eaa604b7000764913b3cbe
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738180"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="adding-commands-to-lync-menus-in-lync-server-2013"></a>Agregar comandos a los menús de Lync en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2016-04-11_

Puede Agregar comandos personalizados a los menús de Lync 2013 y pasar el identificador uniforme de recursos (URI) SIP del usuario actual y los contactos seleccionados a la aplicación que inicia el comando personalizado.

Los comandos personalizados que agregue pueden aparecer en uno o varios de los siguientes menús:

  - El menú herramientas, en la barra de menús de la ventana principal de Lync

  - El menú contextual de contactos de la lista de contactos

  - El menú más opciones, en la ventana de conversación

  - El menú contextual de las personas que aparecen en la lista de participantes de la ventana de conversación

  - El menú opciones de una tarjeta de contacto

Puede definir comandos personalizados para dos tipos de aplicaciones: aplicaciones que realizan una de las siguientes acciones:

  - Se aplica solo al usuario actual y se inicia en el equipo local.

  - Incluya usuarios adicionales, como un programa de colaboración en línea, y se debe iniciar en el equipo de cada usuario.

El comando personalizado se puede invocar de las siguientes maneras:

  - Seleccione uno o más usuarios y, a continuación, elija el comando personalizado.

  - Inicie una conversación de dos o varias partes y, a continuación, elija el comando personalizado.

<div>

## <a name="to-add-a-custom-command"></a>Para agregar un comando personalizado

Use la configuración del registro de la tabla siguiente para agregar un comando a los menús. Estas entradas se colocan en el registro en una de las siguientes ubicaciones:

  - Para el sistema operativo de\_32\_bits\\:\\el\\software\\del\\equipo\\local\\HKEY Microsoft Office 15,0 Lync SessionManager apps

  - Para el sistema operativo de\_64\_bits\\:\\HKEY\\local\\Machine\\software\\Wow6432Node\\Microsoft\\Office 15,0 Lync SessionManager apps

### <a name="custom-command-registry-entries"></a>Entradas del registro de comandos personalizadas

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
<td><p>Nombre de la aplicación tal y como aparece en el menú.</p></td>
</tr>
<tr class="even">
<td><p>ApplicationType</p></td>
<td><p>ÚLTIMAS</p></td>
<td><p>0 = ejecutable (valor predeterminado)</p>
<div>

> [!NOTE]  
> Requiere ApplicationInstallPath.


</div>
<p>1 = Protocolo</p></td>
</tr>
<tr class="odd">
<td><p>ApplicationInstallPath</p></td>
<td><p>REG_SZ</p></td>
<td><p>Ruta de acceso completa del archivo ejecutable.</p>
<div>

> [!NOTE]  
> Debe especificarse si ApplicationType es 0 (ejecutable).


</div></td>
</tr>
<tr class="even">
<td><p> Ruta de acceso</p></td>
<td><p>REG_SZ</p></td>
<td><p>Ruta completa para iniciarse junto con cualquier parámetro, incluidos los parámetros predeterminados <em>% User-ID%</em> y <em>% Contact-ID</em>.</p></td>
</tr>
<tr class="odd">
<td><p>SessionType</p></td>
<td><p>ÚLTIMAS</p></td>
<td><p>0 = sesión local. La aplicación se inicia en el equipo local.</p>
<p>1 = sesión de dos partes (predeterminado). Lync 2013 inicia la aplicación de forma local y luego envía una notificación de escritorio al otro usuario. El otro usuario hace clic en la notificación para iniciar la aplicación en su equipo.</p>
<p>2 = sesión de varias partes. Lync 2013 inicia la aplicación de forma local y después envía notificaciones de escritorio a los demás usuarios. El otro usuario hace clic en la notificación para iniciar la aplicación especificada en su equipo.</p></td>
</tr>
<tr class="even">
<td><p>ExtensibleMenu</p></td>
<td><p>REG_SZ</p></td>
<td><p>Una lista de los menús en los que aparecerá este comando, separados por puntos y comas. Los valores posibles son:</p>
<p>MainWindowActions</p>
<p>MainWindowRightClick</p>
<p>ConversationWindowActions</p>
<p>ConversationWindowRightClick</p>
<p>ContactCardMenu</p>
<p>Si no se define ExtensibleMenu, se usan los valores predeterminados de MainWindowRightClick y ConversationWindowActions.</p></td>
</tr>
</tbody>
</table>


Por ejemplo, el siguiente editor del registro (. REG) muestra los resultados de agregar un elemento de menú de Contoso Sales Contact Manager en el menú de acciones en la ventana de conversación:

    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Office\15.0\Lync\SessionManager\Apps\{1F9F07C6-7E0B-462B-AAD7-98C6DBEA8F69}]
    "Name"="Contoso Sales Contact Manager"
    "HelpMessage"="The Contoso Sales Contact Manager is not installed. Contact the Help Desk for more information."
    "ApplicationType"=dword:00000000
    "ApplicationInstallPath"="C:\\cscm.exe"
    "Path"="C:\\cscm.exe %user-id% %contact-id%"
    "SessionType"=dword:00000001
    "ExtensibleMenu"="ConversationWindowActions;MainWindowRightClick"

</div>

<div>

## <a name="to-access-a-custom-command"></a>Para obtener acceso a un comando personalizado

Para obtener acceso a un comando personalizado después de agregarlo, siga uno de estos procedimientos, en función de los valores de ExtensibleMenu que defina:

  - **MainWindowActions**   en la ventana principal de Lync, haga clic en **herramientas**y, a continuación, haga clic en el comando personalizado.

  - **MainWindowRightClick**   en la ventana principal de Lync, haga clic con el botón secundario en un contacto y, a continuación, haga clic en el comando personalizado.

  - **ConversationWindowActions**   en la ventana de conversación, haga clic en el icono **más opciones** y, a continuación, haga clic en el comando personalizado.

  - **ConversationWindowRightClick**   en la ventana de conversación, haga clic con el botón secundario en el nombre de un contacto y, a continuación, haga clic en el comando personalizado.

</div>

</div>

<span> </span>

</div>

</div>

</div>

