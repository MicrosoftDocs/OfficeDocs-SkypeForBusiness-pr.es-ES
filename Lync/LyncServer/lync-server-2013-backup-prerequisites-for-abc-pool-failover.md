---
title: 'Lync Server 2013: requisitos previos de copia de seguridad para la conmutación por error de grupo ABC'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Backup prerequisites for ABC pool failover
ms:assetid: 652046f5-6086-4592-902d-d5789581977d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945634(v=OCS.15)
ms:contentKeyID: 51541485
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7cdb228b0a748c830aa488e7b058bf8664360d0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842744"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-prerequisites-for-abc-pool-failover-in-lync-server-2013"></a>Requisitos previos de copia de seguridad de la conmutación por error de grupo ABC en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-03-26_

Para sacar el máximo provecho del uso del procedimiento de failover de grupo ABC, debe realizar ciertas copias de seguridad antes de que se produzca el desastre y el failover:

  - Debe realizar una copia de seguridad de los datos de configuración del servicio de información de ubicación (LIS) desde el grupo A mediante el cmdlet **Export-CsLISConfiguration** .
    
        Export-csLisConfiguration -FileName <C:\LISExportPrimary.zip>

  - Debe realizar una copia de seguridad de los datos de configuración del grupo de respuesta en el grupo A mediante el cmdlet **Export-CsRgsConfiguration** .
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    En general, le recomendamos que realice copias de seguridad diarias pero, si tiene un gran volumen de cambios, es posible que desee programar copias de seguridad más frecuentes. La cantidad de información que puede perder en caso de que se produzca un desastre depende de la frecuencia de las copias de seguridad, así como de la frecuencia y el volumen de los cambios.
    
    La aplicación de grupo de respuesta solo puede almacenar un conjunto de parámetros de nivel de aplicación por grupo. Se puede acceder a esta configuración a través de los cmdlets **Get-CsRgsConfiguration** . La configuración incluye la configuración predeterminada de música en espera, el archivo de audio de música activada predeterminada, el período de gracia con anillo de los agentes y la configuración del contexto de la llamada. Esta configuración se puede transferir de una agrupación a otra mediante el cmdlet **Import-CsRgsConfiguration** mediante el parámetro **ReplaceExistingSettings** , pero esta operación invalidará cualquier configuración de nivel de aplicación en el destino. agrupa.
    
    <div>
    

    > [!TIP]  
    > En una ubicación independiente, mantenga una copia de seguridad de todos los archivos de audio originales que se han usado para configurar la aplicación de grupo de respuesta (es decir, cualquier grabación o música en suspensión).

    
    </div>
    
    Si tiene algún archivo de música personalizada habilitada que se haya cargado para el servicio de estacionamiento de llamadas en un grupo, debe guardar una copia en otra ubicación. No se realiza una copia de seguridad de estos archivos como parte del proceso de recuperación de desastres de Lync Server 2013 y se perderán si los archivos cargados en el grupo están dañados, están dañados o se hayan borrado.
    
        Xcopy  <Source: Pool A CPS File Store Path>  <Destination>
        Example: Xcopy  "<Pool A File Store Path>\LyncFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Destination:  Backup location 1>"
    
    <div>
    

    > [!NOTE]  
    > La aplicación de estacionamiento de llamadas solo puede almacenar un conjunto de configuraciones y un archivo de audio de música en espera personalizado por grupo. Se puede acceder a esta configuración a través del cmdlet <STRONG>Get-CsCpsConfiguration</STRONG> . Puesto que el mecanismo de recuperación de desastres para el parque de llamadas depende de la aplicación de estacionamiento de llamadas del grupo de copias de seguridad, no se hace una copia de seguridad de la configuración del grupo principal ni se conserva si se produce un desastre. Si el grupo primario se pierde, esta configuración no se puede recuperar y cuando se implementa un nuevo grupo para reemplazar el grupo principal, la configuración de la suspensión de llamada y el archivo de audio de música personalizada en espera tendría que volver a configurarse.

    
    </div>

  - Si configura cualquier anuncio como parte de la característica de voz número no asignado, le recomendamos que se mantenga en otro lugar una copia de cualquier archivo de audio original que se haya usado durante la configuración inicial. Si no lo hizo, puede obtener una copia de los archivos de audio configurados en el almacén de archivos del servidor o del grupo en el que se han importado los archivos de audio. No se realiza una copia de seguridad de estos archivos como parte del proceso de recuperación de desastres de Lync Server 2013 y se perderán si los archivos cargados en el grupo están dañados, están dañados o se hayan borrado. Para copiar todos los archivos de audio que se usan para configurar la característica de voz de número sin asignar desde el almacén de archivos de un servidor o grupo, use:
    
        Use: Xcopy  <Source: Pool A Announcement Service File Store Path>  <Destination>
        Example Usage:  Xcopy  "<Pool A File Store Path>\X-ApplicationServer-X\AppServerFiles\RGS\AS"  "<Destination: Backup location>"

  - Si tiene bases de datos de supervisión y archivado en un grupo, debe usar las herramientas de administración de SQL Server para realizar copias de seguridad. En el procedimiento de conmutación por error ABC, las bases de datos de supervisión y archivado no se conservan si se colocan en el grupo A, porque estas bases de datos no se copian mediante el servicio de copia de seguridad de Lync Server.

</div>

<span> </span>

</div>

</div>

</div>

