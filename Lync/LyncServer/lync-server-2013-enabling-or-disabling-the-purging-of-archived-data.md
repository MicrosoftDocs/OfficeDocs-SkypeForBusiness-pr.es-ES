---
title: 'Lync Server 2013: habilitar o deshabilitar la purga de datos archivados'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enabling or disabling the purging of archived data
ms:assetid: 28cef09f-0970-4fc3-8315-f26689e3e187
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520968(v=OCS.15)
ms:contentKeyID: 48183678
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 28eba32895ca928b40e42a04d8d701c7257f1e43
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835237"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-or-disabling-the-purging-of-archived-data-in-lync-server-2013"></a>Habilitar o deshabilitar la purga de datos archivados en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-23_

En el panel de control de Lync Server 2013, se usan configuraciones de archivado para habilitar y deshabilitar la purga y configuración de la implementación de la purga. Esto incluye las siguientes configuraciones de archivado:

  - Una configuración global que se crea de forma predeterminada al implementar Lync Server 2013.

  - Configuraciones de nivel de sitio y de grupo opcionales que puede crear y usar para especificar cómo se implementa el archivado para grupos o sitios específicos.

Inicialmente, debe configurar las configuraciones de archivado al implementar el archivado, pero puede cambiar, agregar y eliminar configuraciones después de la implementación. Para obtener más información sobre cómo se implementan las configuraciones de archivado, incluidas las opciones que puede especificar y la jerarquía de las configuraciones de archivado, consulte [Cómo funciona el archivado en Lync Server 2013](lync-server-2013-how-archiving-works.md) en la documentación de planeación, implementación documentación u operación.

<div>


> [!NOTE]  
> Para usar el archivado para los usuarios alojados en Lync Server 2013 debe configurar las directivas de archivado para especificar si desea habilitar el archivado de las comunicaciones internas, de las comunicaciones externas o de ambos. De forma predeterminada, el archivado no está habilitado para las comunicaciones internas o externas. Antes de habilitar el archivado en cualquier directiva, debe especificar las configuraciones de archivado apropiadas para su implementación y, opcionalmente, para determinados sitios y grupos, tal y como se describe en esta sección. Para obtener más información sobre cómo habilitar el archivado, vea <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">configurar y asignar directivas de archivado en Lync Server 2013</A> en la documentación de implementación.<BR>Si decide que después de implementar el archivado desea usar la integración de Microsoft Exchange para almacenar datos y archivos en servidores de Exchange 2013 y todos los usuarios están alojados en los servidores de Exchange 2013, debe quitar la configuración de la base de datos de SQL Server desde su topología. Para ello, debe usar el generador de topología. Para obtener más información, vea <A href="lync-server-2013-changing-archiving-database-options.md">cambiar las opciones de base de datos de archivado en Lync Server 2013</A> en la documentación de operaciones.



</div>

<div>

## <a name="to-enable-or-disable-purging-for-archiving"></a>Para habilitar o deshabilitar la depuración para el archivado

1.  Desde una cuenta de usuario que se asigne al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, después, en **Configuración de archivado**.

4.  Haga clic en el nombre de la configuración global, de sitio o de grupo adecuada en la lista de configuraciones de archivado; haga clic en **Editar**, en **Mostrar detalles** y, luego, haga lo siguiente:
    
      - Para habilitar la purga, active la casilla **Habilitar purgado de los datos de archivado** y siga uno de estos procedimientos:
        
          - Para purgar todos los registros, haga clic en **Purgar los datos de archivado exportados y los datos de archivado almacenados tras la duración máxima (días)** y, luego, especifique la cantidad de días.
        
          - Para purgar solo los datos que se han exportado, haga clic en **Purgar solo datos de archivado exportados**.
    
      - Para deshabilitar la purga, desactive la casilla **Habilitar purgado de los datos de archivado**.

5.  Haga clic en **Confirmar**.

</div>

<div>

## <a name="enabling-or-disabling-the-purging-of-archiving-data-by-using-windows-powershell-cmdlets"></a>Habilitar o deshabilitar la purga de datos de archivado mediante cmdlets de Windows PowerShell

Habilitar y deshabilitar la purga automática de datos de archivado se puede administrar mediante Windows PowerShell y el cmdlet **set-CsArchivingConfiguration** . Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.

<div>

## <a name="to-enable-the-purging-of-all-archiving-data"></a>Para habilitar la purga de todos los datos de archivado

  - Para habilitar la purga de todos los datos de archivado, establezca la propiedad **EnablePurging** en true ($true). Por ejemplo:
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True
    
    Después de ejecutar este comando, cada día, Lync Server purgará todos los registros de archivado anteriores al valor especificado para la propiedad **KeepArchivingDataForDays** .

</div>

<div>

## <a name="to-enable-the-purging-only-of-exported-archiving-data"></a>Para habilitar la purga solamente de datos de archivado exportados

  - Para limitar la purga a los registros que se han exportado a un archivo de datos (mediante el cmdlet [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) ), también debe establecer la propiedad PurgeExportedArchivesOnly en True ($true). Por ejemplo:
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True -PurgeExportedArchivesOnly $True
    
    Después de ejecutar este comando, Lync Server solo purgará los registros de archivado que cumplan con dos criterios: 1) son anteriores al valor especificado para la propiedad **KeepArchivingDataForDays** ; y 2) se han exportado con el cmdlet **Export-CsArchivingData** .

</div>

<div>

## <a name="to-disable-the-purging-of-all-archiving-data"></a>Para deshabilitar la purga de todos los datos de archivado

  - Para deshabilitar la purga automática de registros archivados, establezca la propiedad **EnablePurging** en falso ($false). Por ejemplo:
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $False

</div>

Para obtener más información, incluidas opciones adicionales para purgar el archivado de datos, consulte el tema de ayuda sobre el cmdlet [set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration) .

</div>

<div>

## <a name="see-also"></a>Vea también


[Cómo funciona el archivado en Lync Server 2013](lync-server-2013-how-archiving-works.md)  


[Configurar y asignar directivas de archivado en Lync Server 2013](lync-server-2013-configuring-and-assigning-archiving-policies.md)  
[Administrar las opciones de configuración de archivado en Lync Server 2013 para su organización, sitios y grupos](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

