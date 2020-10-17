---
title: 'Lync Server 2013: habilitar o deshabilitar el control de versiones de cliente'
description: 'Lync Server 2013: habilitar o deshabilitar el control de versiones de cliente.'
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
ms.openlocfilehash: 0bbd190e827e028efc37365c3cd8ecab16b35dac
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546626"
---
# <a name="enable-or-disable-client-versioning-in-lync-server-2013"></a>Habilitar o deshabilitar el control de versiones de cliente en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-23_

Las opciones de configuración de versión de cliente se usan para activar o desactivar el control de versiones de cliente, ya sea de forma global o para determinados sitios. La configuración de la versión de cliente global se instala con Lync Server 2013 y se usa para habilitar o deshabilitar el control de versiones de cliente para toda la implementación del servidor. Cuando la configuración global está habilitada, las directivas de versión de cliente que haya implementado surtirán efecto cuando los usuarios intenten iniciar sesión. Puede deshabilitar la configuración de versión de cliente global si no desea que se produzca ningún control de versiones de cliente. Puede habilitar o deshabilitar el control de versiones de cliente desde el panel de control de Lync Server 2013 o el shell de administración de Lync Server 2013.

<div>


> [!NOTE]  
> Debido a que los usuarios anónimos no están asociados a un usuario, sitio o servicio, este tipo de usuarios solo se ven afectados por directivas de nivel global.



</div>

<div>

## <a name="to-enable-or-disable-client-versioning-by-using-lync-server-control-panel"></a>Para habilitar o deshabilitar el control de versiones de cliente mediante el panel de control de Lync Server

1.  Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **clientes**y, a continuación, haga clic en el botón de navegación **configuración de versión de cliente** .

4.  Haga lo siguiente:
    
      - Para habilitar o deshabilitar de forma global el control de versiones de cliente, haga doble clic en la configuración **global** y, a continuación, modifique la configuración.
    
      - Para habilitar o deshabilitar el control de versiones de cliente para un sitio en particular, haga clic en **nuevo**, seleccione el sitio, haga clic en **Aceptar**y, a continuación, modifique la configuración del sitio.

</div>

<div>

## <a name="enabling-or-disabling-client-versioning-by-using-windows-powershell-cmdlets"></a>Habilitación o deshabilitación del control de versiones de cliente mediante cmdlets de Windows PowerShell

Puede habilitar o deshabilitar el control de versiones de cliente mediante el cmdlet **set-CsClientVersionConfiguration** . Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server 2010 mediante PowerShell remoto" en [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-enable-client-versioning"></a>Para habilitar el control de versiones de cliente

  - Puede habilitar el control de versiones del cliente estableciendo la propiedad **Enabled** en True ($true).
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

<div>

## <a name="to-disable-client-versioning"></a>Para deshabilitar el control de versiones de cliente

  - Puede deshabilitar el control de versiones del cliente estableciendo la propiedad **Enabled** en False ($false).
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

Para obtener más información, consulte el tema de ayuda del cmdlet [set-CsClientVersionConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionConfiguration) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

