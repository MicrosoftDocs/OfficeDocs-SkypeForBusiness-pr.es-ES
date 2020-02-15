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
ms.openlocfilehash: 96a0df07a44392857f4384a1285245229874cdaa
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038612"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="adding-commands-to-lync-menus-in-lync-server-2013"></a>Agregar comandos a los menús de Lync en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2016-04-11_

Puede Agregar comandos personalizados a los menús de Lync 2013 y pasar el identificador uniforme de recursos (URI) de SIP del usuario actual y los contactos seleccionados a la aplicación que inicia el comando personalizado.

Los comandos personalizados que usted agrega pueden aparecer en uno o en varios de los menús siguientes:

  - En el menú Herramientas, en la barra de menús en la ventana principal de Lync

  - En el menú contextual de contactos en la lista de contactos

  - El menú más opciones, en la ventana de conversación

  - En el menú contextual para las personas que aparecen en la lista de participantes de la ventana Conversación

  - En el menú de opciones de una tarjeta de contacto

Puede definir comandos personalizados para dos tipos de aplicaciones; en definitiva, para las aplicaciones que implican cualquiera de los siguientes supuestos:

  - Se aplican únicamente al usuario actual y se inician en el equipo local.

  - Suponen la participación de usuarios adicionales, como un programa de colaboración en línea, y deben iniciarse en el equipo de cada usuario.

El comando personalizado puede invocarse de las formas siguientes:

  - Seleccione uno o más usuarios y elija el comando personalizado.

  - Inicie una conversación de dos o más participantes y elija el comando personalizado.

<div>

## <a name="to-add-a-custom-command"></a>Para agregar un comando personalizado

Use la configuración del registro de la tabla siguiente para agregar un comando a los menús. Estas entradas se colocan en el registro en una de las siguientes ubicaciones:

  - Para el sistema operativo de\_32\_bits\\:\\el\\software\\del\\equipo\\local\\HKEY Microsoft Office 15,0 Lync SessionManager apps

  - Para sistemas operativos de 64\_bits\_:\\HKEY\\Wow6432Node\\de\\software\\del\\equipo\\local\\de Microsoft Office 15,0 Lync SessionManager apps

### <a name="custom-command-registry-entries"></a>Entradas del Registro de comandos personalizados

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
<td><p>ÚLTIMAS</p></td>
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
<td><p>Path</p></td>
<td><p>REG_SZ</p></td>
<td><p>Ruta de acceso completa que debe iniciarse junto con cualquier parámetro, incluidos los parámetros predeterminados <em>%user-id%</em> y <em>%contact-id%</em>.</p></td>
</tr>
<tr class="odd">
<td><p>SessionType</p></td>
<td><p>ÚLTIMAS</p></td>
<td><p>0 = Sesión local. La aplicación se inicia en el equipo local.</p>
<p>1 = Sesión entre dos participantes (valor predeterminado). Lync 2013 inicia la aplicación de forma local y, a continuación, envía una notificación de escritorio al otro usuario. El otro usuario hace clic en la notificación para iniciar la aplicación en su equipo.</p>
<p>2 = Sesión de varios participantes. Lync 2013 inicia la aplicación de forma local y, a continuación, envía notificaciones de escritorio a los demás usuarios. El otro usuario hace clic en la notificación para iniciar la aplicación especificada en su equipo.</p></td>
</tr>
<tr class="even">
<td><p>ExtensibleMenu</p></td>
<td><p>REG_SZ</p></td>
<td><p>Una lista de los menús en los que aparecerá este comando, separados por punto y coma. Los valores posibles son:</p>
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

Para obtener acceso a un comando personalizado después de que se haya agregado, siga uno de estos procedimientos, según los valores de ExtensibleMenu que defina:

  - **MainWindowActions**   en la ventana principal de Lync, haga clic en **herramientas**y, a continuación, haga clic en el comando personalizado.

  - **MainWindowRightClick**   en la ventana principal de Lync, haga clic con el botón secundario en un contacto y, a continuación, haga clic en el comando personalizado.

  - **ConversationWindowActions**   en la ventana conversación, haga clic en el icono **más opciones** y, a continuación, haga clic en el comando personalizado.

  - **ConversationWindowRightClick**   en la ventana conversación, haga clic con el botón secundario en el nombre de un contacto y, a continuación, haga clic en el comando personalizado.

</div>

</div>

<span> </span>

</div>

</div>

</div>

