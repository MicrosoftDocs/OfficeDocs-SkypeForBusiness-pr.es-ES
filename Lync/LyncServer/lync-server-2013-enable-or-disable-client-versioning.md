---
title: 'Lync Server 2013: habilitar o deshabilitar el control de versiones del cliente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable client versioning
ms:assetid: 33a98cb9-a979-4bb6-afb2-512f601d7ac5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898475(v=OCS.15)
ms:contentKeyID: 50873755
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f413df3ec1d35438155492a32d9fdff449aec3c3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736200"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-client-versioning-in-lync-server-2013"></a>Habilitar o deshabilitar el control de versiones del cliente en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-23_

La configuración de la versión del cliente se usa para activar o desactivar el control de versiones del cliente, ya sea de forma global o para sitios concretos. La configuración de la versión de cliente global se instala con Lync Server 2013 y se usa para habilitar o deshabilitar el control de versiones de cliente para toda la implementación del servidor. Cuando se habilita la configuración global, las directivas de versión de cliente que tenga vigentes se aplicarán cuando los usuarios intenten iniciar sesión. Puede deshabilitar la configuración de la versión de cliente global si no desea que se produzca ningún control de versión de cliente. Puede habilitar o deshabilitar las versiones de cliente desde el panel de control de Lync Server 2013 o del shell de administración de Lync Server 2013.

<div>


> [!NOTE]  
> Debido a que los usuarios anónimos no están asociados a un usuario, sitio o servicio, este tipo de usuarios solo se ven afectados por directivas de nivel global.



</div>

<div>

## <a name="to-enable-or-disable-client-versioning-by-using-lync-server-control-panel"></a>Para habilitar o deshabilitar el control de versiones de cliente mediante el panel de control de Lync Server

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **clientes**y, a continuación, haga clic en el botón de navegación de **configuración de versión de cliente** .

4.  Siga este procedimiento:
    
      - Para habilitar o deshabilitar globalmente el control de versiones del cliente, haga doble clic en la configuración **global** y, a continuación, modifique la configuración.
    
      - Para habilitar o deshabilitar el control de versiones de un sitio en particular, haga clic en **nuevo**, seleccione el sitio, haga clic en **Aceptar**y, a continuación, modifique la configuración del sitio.

</div>

<div>

## <a name="enabling-or-disabling-client-versioning-by-using-windows-powershell-cmdlets"></a>Habilitar o deshabilitar el control de versiones de cliente mediante cmdlets de Windows PowerShell

Puede habilitar o deshabilitar el control de versiones de cliente mediante el cmdlet **set-CsClientVersionConfiguration** . Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.

<div>

## <a name="to-enable-client-versioning"></a>Para habilitar el control de versiones de cliente

  - Para habilitar el control de versiones del cliente, establezca la propiedad **Enabled** en True ($true).
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

<div>

## <a name="to-disable-client-versioning"></a>Para deshabilitar el control de versiones del cliente

  - Puede deshabilitar el control de versiones del cliente si establece la propiedad **Enabled** en False ($false).
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

Para obtener más información, vea el tema de ayuda sobre el cmdlet [set-CsClientVersionConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionConfiguration) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

