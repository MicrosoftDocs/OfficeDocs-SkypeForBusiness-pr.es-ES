---
title: Requisitos previos de copia de seguridad para la conmutación por error de grupo ABC
TOCTitle: Requisitos previos de copia de seguridad para la conmutación por error de grupo ABC
ms:assetid: 652046f5-6086-4592-902d-d5789581977d
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ945634(v=OCS.15)
ms:contentKeyID: 52061694
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Requisitos previos de copia de seguridad para la conmutación por error de grupo ABC

 

_**Última modificación del tema:** 2013-03-26_

Para aprovechar al máximo el procedimiento de conmutación por error de grupo ABC, debe realizar ciertas copias de seguridad antes de que se produzca un desastre o una conmutación por error:

  - De forma periódica, debe realizar una copia de seguridad de los datos de configuración del servicio de información de ubicaciones (LIS) del grupo A mediante el cmdlet **Export-CsLISConfiguration**.
    
        Export-csLisConfiguration -FileName <C:\LISExportPrimary.zip>

  - De forma periódica, debe realizar una copia de seguridad de los datos de configuración del grupo de respuesta del grupo A mediante el cmdlet **Export-CsRgsConfiguration**.
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    En general, se recomienda que realice copias de seguridad diarias, pero si tiene un gran volumen de cambios, puede resultar conveniente programar copias de seguridad más frecuentes. La cantidad de información que puede perder en caso de un desastre depende de la frecuencia de las copias de seguridad, así como de la frecuencia y el volumen de los cambios.
    
    La aplicación de grupo de respuesta solo puede almacenar un conjunto de valores de configuración de nivel de aplicación por grupo. Se puede acceder a esta configuración mediante el cmdlet **Get-CsRgsConfiguration**. La configuración incluye la configuración de música en espera predeterminada, el archivo de audio de música en espera predeterminado, el período de gracia de devolución de llamada del agente y la configuración del contexto de la llamada. Esta configuración se puede transferir de un grupo a otro mediante el cmdlet **Import-CsRgsConfiguration** con el parámetro **ReplaceExistingSettings**, pero esta operación invalidará cualquier configuración de nivel de aplicación en el grupo de destino.
    
    > [!TIP]  
    > En una ubicación independiente, guarde una copia de seguridad de todos los archivos de audio originales que se han usado para configurar la aplicación de grupo de respuesta (es decir, cualquier grabación o archivo de música en espera).
    
    
    Si en un grupo se han cargado archivos de música en espera personalizados para el estacionamiento de llamadas, debe guardar una copia de seguridad de estos archivos en otra ubicación. El proceso de recuperación ante desastres de Lync Server 2013 no realiza la copia de seguridad de estos archivos, por lo que se perderán si los archivos cargados en el grupo se dañan o borran.
    
        Xcopy  <Source: Pool A CPS File Store Path>  <Destination>
        Example: Xcopy  "<Pool A File Store Path>\LyncFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Destination:  Backup location 1>"
    

    > [!NOTE]
    > La aplicación de estacionamiento de llamadas solo puede almacenar un conjunto de valores de configuración y un archivo de audio de música en espera personalizado por grupo. Se puede acceder a esta configuración mediante el cmdlet <STRONG>Get-CsCpsConfiguration</STRONG>. Puesto que el mecanismo de recuperación ante desastres del estacionamiento de llamadas depende de la aplicación de estacionamiento de llamadas del grupo de copia de seguridad, no se conserva ni se realiza una copia de seguridad de la configuración del grupo principal en el caso de un desastre. Si se pierde el grupo principal, no se puede recuperar esta configuración y, cuando se implemente un nuevo grupo para reemplazar el grupo principal, deberá volver a establecerse la configuración del estacionamiento de llamadas y de todos los archivos de audio de música en espera personalizados.



  - Si configura anuncios como parte de la característica de voz de número no asignado, se recomienda guardar en otra ubicación una copia de los archivos de audio originales usados durante la configuración inicial. Si no lo hizo, puede obtener una copia de los archivos de audio configurados en el almacén de archivos del servidor o grupo donde se importaron estos archivos. El proceso de recuperación ante desastres de Lync Server 2013 no realiza la copia de seguridad de estos archivos, por lo que se perderán si los archivos cargados en el grupo se dañan o borran. Para copiar todos los archivos de audio usados para configurar la característica de voz de número no asignado desde el almacén de archivos de un servidor o grupo, use lo siguiente:
    
        Use: Xcopy  <Source: Pool A Announcement Service File Store Path>  <Destination>
        Example Usage:  Xcopy  "<Pool A File Store Path>\X-ApplicationServer-X\AppServerFiles\RGS\AS"  "<Destination: Backup location>"

  - Si tiene bases de datos de supervisión y archivado en un grupo, debe usar las herramientas de administración de SQL Server para realizar sus copias de seguridad. En el procedimiento de conmutación por error de ABC, no se conservan las bases de datos de supervisión y archivado si se han colocado en el grupo A, ya que sus copias de seguridad no se han realizado mediante el servicio de copia de seguridad de Lync Server.

