---
title: Crear o modificar una colección de opciones de configuración de versión de cliente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of client version configuration settings
ms:assetid: 4e6faffd-a36f-40f1-8734-78d84b7df921
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898477(v=OCS.15)
ms:contentKeyID: 50873757
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 56061b4d6c801263c30e471acef70e68c10bfea1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521747"
---
# <a name="create-or-modify-a-collection-of-client-version-configuration-settings-in-lync-server-2013"></a>Crear o modificar una colección de opciones de configuración de versión de cliente en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-23_

Los ajustes de configuración de versión de cliente se usan para activar o desactivar el control de versión de cliente. La configuración de la versión de cliente global se instala con Lync Server y se usa para habilitar o deshabilitar el control de versiones de cliente para toda la implementación del servidor. También puede configurar las opciones de configuración de versión de cliente para sitios individuales. Puede crear o modificar las opciones de configuración de versión de cliente desde el panel de control de Lync Server 2013 o el shell de administración de Lync Server 2013.

<div>


> [!NOTE]
> Debido a que los usuarios anónimos no están asociados a un usuario, sitio o servicio, este tipo de usuarios solo se ven afectados por directivas de nivel global.



</div>

<div>

## <a name="to-create-or-modify-client-version-configuration-settings-by-using-lync-server-control-panel"></a>Para crear o modificar las opciones de configuración de versión de cliente mediante el panel de control de Lync Server

1.  Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **clientes**y, a continuación, haga clic en el botón de navegación **configuración de versión de cliente** .

4.  En la página **configuración de versión de cliente** , haga lo siguiente:
    
      - Para crear una nueva configuración, haga clic en **nuevo**, seleccione un sitio, haga clic en nombre de **Aceptar** y actualice la configuración.
    
      - Para modificar una configuración, seleccione la configuración, haga clic en **Editar**, haga clic en **Mostrar detalles**y realice los cambios en la configuración.

</div>

<div>

## <a name="creating-or-modifying-client-version-configuration-settings-by-using-windows-powershell-cmdlets"></a>Creación o modificación de las opciones de configuración de la versión de cliente con cmdlets de Windows PowerShell

Puede crear opciones de configuración de versión de cliente con el cmdlet **New-CsClientVersionConfiguration** y modificarlas con el cmdlet **set-CsClientVersionConfiguration** . Estos cmdlets se pueden ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server 2010 mediante PowerShell remoto" en [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-create-a-new-collection-of-client-version-configuration-settings"></a>Para crear una nueva colección de opciones de configuración de versiones de cliente

  - El siguiente comando crea una nueva colección de opciones de configuración de versión de cliente que se aplican al sitio de Redmond. En este ejemplo, el control de versiones de cliente está deshabilitado para el sitio de Redmond.
    
        New-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $False

</div>

<div>

## <a name="to-enable-client-versioning-for-a-site"></a>Para habilitar el control de versiones de cliente para un sitio

  - Este comando habilita el control de versiones de cliente para el sitio de Redmond.
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

<div>

## <a name="to-disable-client-versioning-throughout-the-organization"></a>Para deshabilitar el control de versiones de cliente en toda la organización

  - En este ejemplo, el control de versiones de cliente está deshabilitado para todas las opciones de configuración de versión de cliente que se usan en la organización.
    
        Get-CsClientVersionConfiguration | Set-CsClientVersionConfiguration  -Enabled $False

</div>

Para obtener más información, consulte el tema de ayuda de los cmdlets [New-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg399029(v=OCS.15)) y [set-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg398623(v=OCS.15)) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

