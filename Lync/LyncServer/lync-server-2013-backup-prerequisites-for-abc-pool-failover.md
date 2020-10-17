---
title: 'Lync Server 2013: requisitos previos de copia de seguridad para la conmutación por error del grupo ABC'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backup prerequisites for ABC pool failover
ms:assetid: 652046f5-6086-4592-902d-d5789581977d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945634(v=OCS.15)
ms:contentKeyID: 51541485
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0607a0ddc2a1b2a8249135fa1256f2cb706a250a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527037"
---
# <a name="backup-prerequisites-for-abc-pool-failover-in-lync-server-2013"></a>Requisitos previos de copia de seguridad para la conmutación por error del grupo ABC en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-03-26_

Para sacar el máximo provecho del uso del procedimiento de conmutación por error del grupo ABC, debe realizar ciertas copias de seguridad antes de que se produzca el desastre y la conmutación por error:

  - Debe realizar una copia de seguridad de los datos de configuración del servicio de información de ubicación (LIS) desde el grupo A con el cmdlet **Export-CsLISConfiguration** .
    
        Export-csLisConfiguration -FileName <C:\LISExportPrimary.zip>

  - Debe hacer una copia de seguridad de los datos de configuración del grupo de respuesta en el grupo A mediante el cmdlet **Export-CsRgsConfiguration** .
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    En general, se recomienda que realice copias de seguridad diarias, pero si tiene un gran volumen de cambios, es posible que desee programar copias de seguridad más frecuentes. La cantidad de información que puede perder en caso de que se produzca un desastre depende de la frecuencia de las copias de seguridad, así como de la frecuencia y el volumen de los cambios.
    
    La aplicación de grupo de respuesta solo puede almacenar un conjunto de opciones de configuración de nivel de aplicación por grupo de servidores. Se puede tener acceso a esta configuración a través de los cmdlets **Get-CsRgsConfiguration** . La configuración incluye la configuración predeterminada de música en espera, el archivo de audio de música en espera predeterminado, el período de gracia de timbre por anillo del agente y la configuración del contexto de llamada. Esta configuración se puede transferir de un grupo de servidores a otro mediante el cmdlet **Import-CsRgsConfiguration** mediante el parámetro **ReplaceExistingSettings** , pero esta operación anulará cualquier configuración de nivel de aplicación en el grupo de servidores de destino.
    
    <div>
    

    > [!TIP]  
    > En una ubicación independiente, conserve una copia de seguridad de todos los archivos de audio originales que se han usado para configurar la aplicación de grupo de respuesta (es decir, las grabaciones o los archivos de música en espera).

    
    </div>
    
    Si tiene archivos de música en espera personalizados que se han cargado para el estacionamiento de llamadas en un grupo de servidores, debe conservar una copia en otra ubicación. No se realiza una copia de seguridad de estos archivos como parte del proceso de recuperación ante desastres de Lync Server 2013 y se perderán si los archivos cargados en el grupo están dañados, están dañados o se han borrado.
    
        Xcopy  <Source: Pool A CPS File Store Path>  <Destination>
        Example: Xcopy  "<Pool A File Store Path>\LyncFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Destination:  Backup location 1>"
    
    <div>
    

    > [!NOTE]  
    > La aplicación estacionamiento de llamadas solo puede almacenar un conjunto de configuraciones y un archivo de audio de música en espera personalizado por grupo de servidores. Se puede tener acceso a esta configuración a través del cmdlet <STRONG>Get-CsCpsConfiguration</STRONG> . Debido a que el mecanismo de recuperación ante desastres para el estacionamiento de llamadas depende de la aplicación de estacionamiento de llamadas del grupo de copia de seguridad, no se realiza una copia de seguridad ni se conserva la configuración del grupo principal si se produce un desastre. Si se pierde el grupo principal, esta configuración no se puede recuperar y, cuando se implementa un nuevo grupo de servidores para reemplazar el grupo principal, la configuración del estacionamiento de llamadas y el archivo de audio de música en espera personalizado tendría que volver a configurarse.

    
    </div>

  - Si configura los anuncios como parte de la característica de voz de número sin asignar, le recomendamos que se mantenga en otra ubicación una copia de los archivos de audio originales que se usan durante la configuración inicial. Si no lo hizo, puede obtener una copia de los archivos de audio configurados en el almacén de archivos del servidor o del grupo de servidores al que se han importado los archivos de audio. No se realiza una copia de seguridad de estos archivos como parte del proceso de recuperación ante desastres de Lync Server 2013 y se perderán si los archivos cargados en el grupo están dañados, están dañados o se han borrado. Para copiar todos los archivos de audio que se usan para configurar la característica de voz de número sin asignar desde el almacén de archivos de un servidor o grupo de servidores, use:
    
        Use: Xcopy  <Source: Pool A Announcement Service File Store Path>  <Destination>
        Example Usage:  Xcopy  "<Pool A File Store Path>\X-ApplicationServer-X\AppServerFiles\RGS\AS"  "<Destination: Backup location>"

  - Si tiene bases de datos de supervisión y archivado en un grupo de servidores, debe usar las herramientas de administración de SQL Server para realizar una copia de seguridad de las mismas. En el procedimiento de conmutación por error ABC, las bases de datos de supervisión y archivado no se conservan si se colocan en el grupo A, porque no se realiza una copia de seguridad de estas bases de datos a través del servicio de copia de seguridad de Lync Server.

</div>

<span> </span>

</div>

</div>

</div>

