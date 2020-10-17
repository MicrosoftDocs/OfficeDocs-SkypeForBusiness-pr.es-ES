---
title: 'Lync Server 2013: habilitar o deshabilitar la depuración de datos archivados'
description: 'Lync Server 2013: habilitar o deshabilitar la depuración de datos archivados.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling or disabling the purging of archived data
ms:assetid: 28cef09f-0970-4fc3-8315-f26689e3e187
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520968(v=OCS.15)
ms:contentKeyID: 48183678
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 442b99e2cfa6db303ca8edd216cbdf3b5c13cea9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546466"
---
# <a name="enabling-or-disabling-the-purging-of-archived-data-in-lync-server-2013"></a>Habilitación o deshabilitación de la purga de datos archivados en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-23_

En el panel de control de 2013 de Lync Server, se usan configuraciones de archivado para habilitar y deshabilitar la purga y configurar la forma en que se implementa la purga. Esto incluye las siguientes configuraciones de archivado:

  - Una configuración global que se crea de forma predeterminada al implementar Lync Server 2013.

  - Unas configuraciones en el nivel de sitio y de grupo que se pueden crear y usar para especificar cómo se implementa el archivado en sitios o grupos determinados.

Las configuraciones de archivado se instalan inicialmente al implementar el archivado, pero podrá cambiar, agregar y eliminar las configuraciones después de la implementación. Para obtener más información sobre cómo se implementan las configuraciones de archivado, incluidas las opciones que puede especificar y la jerarquía de las configuraciones de archivado, consulte [how archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) en la documentación sobre Planeación, la documentación sobre la implementación o las operaciones.

<div>


> [!NOTE]  
> Para usar el archivado para los usuarios hospedados en Lync Server 2013, debe configurar las directivas de archivado para especificar si desea habilitar el archivado para las comunicaciones internas, para las comunicaciones externas o para ambos. De manera predeterminada, el archivado no está habilitado para las comunicaciones ni internas, ni externas. Antes de habilitar el archivado en ninguna directiva, debe especificar las configuraciones de archivado apropiadas para su implementación y, si lo desea, para sitios y grupos de servidores concretos, como se describe en este apartado. Para obtener más información sobre cómo habilitar el archivado, consulte <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">configuración y asignación de directivas de archivado en Lync Server 2013</A> en la documentación sobre implementación.<BR>Si decide que después de implementar el archivado desea usar la integración de Microsoft Exchange para almacenar los datos y archivos de archivado en servidores de Exchange 2013 y que todos los usuarios estén hospedados en los servidores de Exchange 2013, debe quitar la configuración de la base de datos de SQL Server de la topología. Debe usar el generador de topologías para hacerlo. Para obtener más información, consulte <A href="lync-server-2013-changing-archiving-database-options.md">cambiar las opciones de base de datos de archivado en Lync Server 2013</A> en la documentación de operaciones.



</div>

<div>

## <a name="to-enable-or-disable-purging-for-archiving"></a>Para habilitar o deshabilitar la depuración para el archivado

1.  Desde una cuenta de usuario asignada al rol CsArchivingAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Supervisión y archivado** y, a continuación, haga clic en **Configuración de archivado**.

4.  Haga clic en el nombre de la configuración global, de sitio o de grupo adecuada de la lista de configuraciones de archivado, en **Editar** y en **Mostrar detalles**. A continuación, haga lo siguiente:
    
      - Para habilitar la depuración, active la casilla **Habilitar purgado de los datos de archivado** y, a continuación, realice una de las siguientes acciones:
        
          - Para purgar todos los registros, haga clic en **Purgar los datos de archivado exportados y los datos de archivado almacenados tras la duración máxima (días)** y, a continuación, especifique el número de días.
        
          - Para purgar solo los datos que se han exportado, haga clic en **depurar solo datos de archivado exportados**.
    
      - Para deshabilitar la depuración, desactive la casilla **Habilitar purgado de los datos de archivado** .

5.  Haga clic en **Confirmar**.

</div>

<div>

## <a name="enabling-or-disabling-the-purging-of-archiving-data-by-using-windows-powershell-cmdlets"></a>Habilitación o deshabilitación de la purga de datos de archivado con los cmdlets de Windows PowerShell

La habilitación y deshabilitación de la purga automatizada de datos de archivado se puede administrar con Windows PowerShell y el cmdlet **set-CsArchivingConfiguration** . Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server 2010 mediante PowerShell remoto" en [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-enable-the-purging-of-all-archiving-data"></a>Para habilitar la purga de todos los datos de archivado

  - Para habilitar la purga de todos los datos de archivado, establezca la propiedad **EnablePurging** en true ($true). Por ejemplo:
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True
    
    Después de ejecutar este comando, todos los días que Lync Server depurará todos los registros de archivado con una antigüedad superior al valor especificado para la propiedad **KeepArchivingDataForDays** .

</div>

<div>

## <a name="to-enable-the-purging-only-of-exported-archiving-data"></a>Para habilitar la purga sólo de los datos de archivado exportados

  - Para limitar la purga a los registros de archivado que se han exportado a un archivo de datos (mediante el cmdlet [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) ), también debe establecer la propiedad PurgeExportedArchivesOnly en True ($true). Por ejemplo:
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True -PurgeExportedArchivesOnly $True
    
    Después de ejecutar este comando, Lync Server solo purgará los registros de archivado que cumplan dos criterios: 1) son más antiguos que el valor especificado para la propiedad **KeepArchivingDataForDays** ; y 2) que se han exportado mediante el cmdlet **Export-CsArchivingData** .

</div>

<div>

## <a name="to-disable-the-purging-of-all-archiving-data"></a>Para deshabilitar la purga de todos los datos de archivado

  - Para deshabilitar la depuración automatizada de los registros de archivado, establezca la propiedad **EnablePurging** en False ($false). Por ejemplo:
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $False

</div>

Para obtener más información, incluidas las opciones adicionales para purgar los datos de archivado, consulte el tema de ayuda del cmdlet [set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration) .

</div>

<div>

## <a name="see-also"></a>Consulte también


[Cómo funciona el archivado en Lync Server 2013](lync-server-2013-how-archiving-works.md)  


[Configuración y asignación de directivas de archivado en Lync Server 2013](lync-server-2013-configuring-and-assigning-archiving-policies.md)  
[Administración de las opciones de configuración de archivado en Lync Server 2013 para la organización, los sitios y los grupos de servidores](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

