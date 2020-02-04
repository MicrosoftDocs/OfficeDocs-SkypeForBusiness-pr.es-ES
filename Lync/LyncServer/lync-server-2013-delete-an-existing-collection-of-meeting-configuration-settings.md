---
title: Eliminar una colección existente de valores de configuración de reuniones
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing collection of meeting configuration settings
ms:assetid: 92ff8a91-05c5-4047-a533-5dff12f22299
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688136(v=OCS.15)
ms:contentKeyID: 49733736
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 96fe774830a8efc6f0cc88a2dd929b3126335b51
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737420"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-meeting-configuration-settings-in-lync-server-2013"></a>Eliminar una colección existente de opciones de configuración de reuniones en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-23_

Puede eliminar un sitio o una configuración de usuario. No se puede quitar la configuración global. Si elimina la configuración global, esta se restablece automáticamente a sus valores predeterminados.

<div>

## <a name="to-delete-a-site-or-user-meeting-configuration"></a>Para eliminar un sitio o una configuración de reunión de usuario

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Conferencia** y, a continuación, en **configuración de reunión**.

4.  En la lista de configuraciones de reunión, haga clic en la configuración de sitio o de grupo que desea eliminar, haga clic en **Editar** y después en **Eliminar**.

</div>

<div>

## <a name="removing-meeting-configuration-settings-by-using-windows-powershell-cmdlets"></a>Quitar la configuración de la reunión mediante cmdlets de Windows PowerShell

La configuración de la reunión se puede eliminar con Windows PowerShell y el cmdlet Remove-CsMeetingConfiguration. Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.

<div>

## <a name="to-remove-a-specified-collection-of-meeting-configuration-settings"></a>Para quitar una colección especificada de valores de configuración de reuniones

  - Este comando quita la configuración de la reunión aplicada al sitio de Redmond:
    
        Remove-CsMeetingConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-meeting-configuration-settings-applied-to-the-site-scope"></a>Para quitar todas las opciones de configuración de reunión aplicadas al ámbito del sitio

  - Este comando quita todas las opciones de configuración de reunión aplicadas al ámbito del sitio:
    
        Get-CsMeetingConfiguration -Filter "site:*" | Remove-CsMeetingConfiguration

</div>

<div>

## <a name="to-remove-all-the-meeting-configuration-settings-that-admit-anonymous-users-by-default"></a>Para quitar todas las opciones de configuración de la reunión que admiten usuarios anónimos de forma predeterminada

  - Esta opción quita todas las opciones de configuración que permiten a los usuarios anónimos ser admitidos de forma predeterminada:
    
        Get-CsMeetingConfiguration | Where-Object {$_.AdmitAnonymousUsersByDefault -eq $True} | Remove-CsMeetingConfiguration

</div>

Para obtener más información, consulte el tema de ayuda para el cmdlet [Remove-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/Gg412775(v=OCS.15)) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

