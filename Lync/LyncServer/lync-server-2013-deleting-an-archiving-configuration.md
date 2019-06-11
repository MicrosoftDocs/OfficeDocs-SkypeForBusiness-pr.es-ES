---
title: 'Lync Server 2013: eliminar una configuración de archivado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deleting an Archiving configuration
ms:assetid: a8744d39-5cf2-474c-9a99-a0f3a37f846f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205167(v=OCS.15)
ms:contentKeyID: 48185093
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a67d944de9b2c35c9ea2428603b39ddabbbcb26
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835587"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-an-archiving-configuration-in-lync-server-2013"></a>Eliminar una configuración de archivado en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-23_

Puede eliminar una configuración de sitio o una configuración de grupo. No se puede quitar la configuración global. Si elimina la configuración global, esta se restablece automáticamente a sus valores predeterminados. Para obtener más información sobre cómo se implementan las configuraciones de archivado, incluidas las opciones que puede especificar y la jerarquía de las configuraciones de archivado, consulte [Cómo funciona el archivado en Lync Server 2013](lync-server-2013-how-archiving-works.md) en la documentación de planeación, implementación documentación u operación.

<div>

## <a name="to-delete-a-site-or-pool-configuration-for-archiving"></a>Para eliminar una configuración de sitio o grupo de servidores

1.  Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, después, en **Configuración de archivado**.

4.  En la lista de configuraciones de archivado, haga clic en la configuración de sitio o de grupo que desea eliminar y, luego, haga clic en **Editar** y en **Eliminar**.

5.  Haga clic en **Confirmar**.

</div>

<div>

## <a name="removing-archiving-configuration-settings-by-using-windows-powershell-cmdlets"></a>Quitar la configuración de archivado mediante cmdlets de Windows PowerShell

Los valores de configuración de archivado se pueden eliminar con Windows PowerShell y el cmdlet **Remove-CsArchivingConfiguration** . Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.

<div>

## <a name="to-remove-a-specified-collection-of-archiving-configuration-settings"></a>Para quitar una colección especificada de parámetros de configuración de archivado

  - El siguiente comando quita los valores de configuración de archivado que se aplican al sitio de Redmond:
    
        Remove-CsArchivingConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-archiving-configuration-settings-applied-to-the-site-scope"></a>Para quitar todas las opciones de configuración de archivado aplicadas al ámbito del sitio

  - Este comando quita todas las opciones de configuración de archivado aplicadas al ámbito de servicio:
    
        Get-CsArchivingConfiguration -Filter "site:*" | Remove-CsArchivingConfiguration

</div>

<div>

## <a name="to-remove-archiving-configuration-settings-based-on-a-specified-property-value"></a>Para quitar los valores de configuración de archivado basados en un valor de propiedad especificado

  - Este comando quita todas las opciones de configuración de archivado donde se ha deshabilitado el archivado de Exchange:
    
        Get-CsArchivingConfiguration | Where-Object {$_.EnableExchangeArchiving -eq $False} | Remove-CsArchivingConfiguration

</div>

Para obtener más información, consulte el tema de ayuda para el cmdlet [Remove-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsArchivingConfiguration) .

</div>

<div>

## <a name="see-also"></a>Vea también


[Cómo funciona el archivado en Lync Server 2013](lync-server-2013-how-archiving-works.md)  


[Administrar el archivado de comunicaciones internas y externas en Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

