---
title: Crear o modificar una colección de parámetros de configuración de la versión de cliente
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
ms.openlocfilehash: 7fc50696444ddd0602bbf21fd9e05b5bba6eddde
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722579"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-client-version-configuration-settings-in-lync-server-2013"></a>Crear o modificar una colección de parámetros de configuración de la versión de cliente en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-23_

Los ajustes de configuración de versión de cliente se usan para activar o desactivar el control de versiones de cliente. La configuración de la versión de cliente global se instala con Lync Server y se usa para habilitar o deshabilitar el control de versiones de cliente para toda la implementación del servidor. También puede configurar las opciones de configuración de versión de cliente para los sitios individuales. Puede crear o modificar los parámetros de configuración de la versión del cliente desde el panel de control de Lync Server 2013 o del shell de administración de Lync Server 2013.

<div>


> [!NOTE]
> Debido a que los usuarios anónimos no están asociados a un usuario, sitio o servicio, este tipo de usuarios solo se ven afectados por directivas de nivel global.



</div>

<div>

## <a name="to-create-or-modify-client-version-configuration-settings-by-using-lync-server-control-panel"></a>Para crear o modificar parámetros de configuración de la versión del cliente mediante el panel de control de Lync Server

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **clientes**y, a continuación, haga clic en el botón de navegación de **configuración de versión de cliente** .

4.  En la página Configuración de la **versión del cliente** , haga lo siguiente:
    
      - Para crear una nueva configuración, haga clic en **nuevo**, seleccione un sitio, haga clic en **Aceptar** nombre y actualice la configuración.
    
      - Para modificar una configuración, seleccione la configuración, haga clic en **Editar**, haga clic en **Mostrar detalles**y realice cambios en la configuración.

</div>

<div>

## <a name="creating-or-modifying-client-version-configuration-settings-by-using-windows-powershell-cmdlets"></a>Crear o modificar la configuración de la versión de cliente mediante cmdlets de Windows PowerShell

Puede crear parámetros de configuración de la versión de cliente con el cmdlet **New-CsClientVersionConfiguration** y modificarlos mediante el cmdlet **set-CsClientVersionConfiguration** . Estos cmdlets se pueden ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.

<div>

## <a name="to-create-a-new-collection-of-client-version-configuration-settings"></a>Para crear una nueva colección de parámetros de configuración de la versión de cliente

  - El siguiente comando crea una nueva colección de parámetros de configuración de la versión de cliente que se aplican al sitio de Redmond. En este ejemplo, el control de versiones del cliente está deshabilitado para el sitio de Redmond.
    
        New-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $False

</div>

<div>

## <a name="to-enable-client-versioning-for-a-site"></a>Para habilitar el control de versiones de cliente en un sitio

  - Este comando habilita el control de versiones de cliente para el sitio de Redmond.
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

<div>

## <a name="to-disable-client-versioning-throughout-the-organization"></a>Para deshabilitar el control de versiones de cliente en toda la organización

  - En este ejemplo, el control de versiones de cliente está deshabilitado para todas las opciones de configuración de la versión de cliente en uso en la organización.
    
        Get-CsClientVersionConfiguration | Set-CsClientVersionConfiguration  -Enabled $False

</div>

Para obtener más información, vea el tema de ayuda sobre los cmdlets [New-CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg399029(v=OCS.15)) y [set-CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg398623(v=OCS.15)) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

