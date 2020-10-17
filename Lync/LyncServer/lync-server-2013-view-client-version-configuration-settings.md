---
title: 'Lync Server 2013: ver las opciones de configuración de la versión de cliente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View client version configuration settings
ms:assetid: c72df4e6-a889-4cb6-86f7-8334d7774c6e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ923062(v=OCS.15)
ms:contentKeyID: 50675353
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1ec472bff967bc2a8ffb75d09e3515654487be41
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506607"
---
# <a name="view-client-version-configuration-settings-in-lync-server-2013"></a>Ver las opciones de configuración de versión de cliente en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-23_

Los ajustes de configuración de versión de cliente se usan para activar o desactivar el control de versión de cliente. La configuración de la versión de cliente global se instala con Lync Server 2013 y se usa para habilitar o deshabilitar el control de versiones de cliente para toda la implementación del servidor. Si la configuración Global está habilitada, las directivas de versión de cliente que tenga activas tendrán efecto cuando los usuarios intenten iniciar sesión. Puede ver las opciones de configuración de versión de cliente desde el panel de control de Lync Server 2013 o el shell de administración de Lync Server 2013.

<div>


> [!NOTE]  
> Debido a que los usuarios anónimos no están asociados a un usuario, sitio o servicio, este tipo de usuarios solo se ven afectados por directivas de nivel global.



</div>

<div>

## <a name="to-view-client-version-configuration-settings-by-using-lync-server-control-panel"></a>Para ver las opciones de configuración de la versión de cliente mediante el panel de control de Lync Server

1.  Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **clientes**y, a continuación, haga clic en el botón de navegación **configuración de versión de cliente** .

4.  Haga doble clic en el nombre de la configuración de versión de cliente que desea ver.

</div>

<div>

## <a name="viewing-client-version-configuration-settings-by-using-windows-powershell-cmdlets"></a>Ver las opciones de configuración de la versión de cliente mediante cmdlets de Windows PowerShell

Puede ver las opciones de configuración de la versión de cliente con el cmdlet **Get-CsClientVersionConfiguration** . Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server 2010 mediante PowerShell remoto" en [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-view-client-version-configuration-information"></a>Para ver la información de configuración de versión de cliente

  - Para ver información sobre todas las opciones de configuración de la versión de cliente, escriba el siguiente comando en el shell de administración de Lync Server y, a continuación, presione ENTRAR:
    
        Get-CsClientVersionConfiguration
    
    Devolverá información similar a la siguiente:
    
        Identity      : Global
        DefaultAction : Allow
        DefaultURL    :
        Enabled       : True

</div>

Para obtener más información, consulte el tema de ayuda del cmdlet [Get-CsClientVersionConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsClientVersionConfiguration) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

