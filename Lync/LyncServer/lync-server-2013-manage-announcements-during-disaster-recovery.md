---
title: 'Lync Server 2013: Administrar anuncios durante la recuperación ante desastres'
TOCTitle: Administrar anuncios durante la recuperación ante desastres
ms:assetid: c33e51ea-421f-42d2-826b-b73968f6bd5b
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ721874(v=OCS.15)
ms:contentKeyID: 49889665
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Administrar anuncios durante la recuperación ante desastres en Lync Server 2013

 

_**Última modificación del tema:** 2013-02-23_

Lync Server 2013 admite anuncios de llamadas a números no asignados durante las interrupciones del servicio. La restauración de la funcionalidad de los anuncios durante una interrupción es opcional. Si decide hacerlo, debe volver a crear la configuración de los anuncios en el grupo de copia de seguridad. En esta sección se describe cómo puede restaurar los anuncios durante una recuperación ante desastres.

Esta sección se aplica a los intervalos de números no asignados que usan Aplicación de anuncio y no se aplica a los intervalos de números no asignados que usan el Operador automático de mensajería unificada de Exchange.

## Antes de la interrupción del servicio

Con independencia de si decide usar anuncios durante las interrupciones de servicio, debe hacer copias de seguridad independientes de todos los archivos de audio personalizados que configure para Aplicación de anuncio. No se realiza esta copia de seguridad de los anuncios personalizados en el proceso de recuperación ante desastres de Lync Server. Si no hace copias de seguridad independientes, los archivos que ha cargado en el servidor o en el grupo se perderán si se dañan o se borran.

Si no tiene copias de seguridad de los archivos de audio personalizados y los archivos de audio originales ya no están disponibles, puede buscar los archivos de audio que ha configurado para Aplicación de anuncio en el almacén de archivos del servidor o grupo donde importó originalmente los archivos. Puede copiar todos los archivos de audio que ha configurado para Aplicación de anuncio desde el almacén de archivos.

**Para copiar archivos de audio desde el almacén de archivos**

1.  En la línea de comandos, ejecute:
    
        Xcopy <Source: Pool Announcement Service File Store path> <Destination>
    
    Por ejemplo:
    
        Xcopy "<Pool File Store Path>\X-ApplicationServer-X\AppServerFiles\RGS\AS" "<Destination: Backup location>"
    
    Donde X-ApplicationServer-X se refiere al identificador de servicio del servidor de aplicaciones del grupo (por ejemplo, 1-ApplicationServer-1").


## Durante la interrupción del servicio

Para usar Aplicación de anuncio durante una interrupción del servicio, debe crear de nuevo la configuración de los anuncios en el grupo de copia de seguridad. Para ello, realice las tareas que se describen en esta sección.


> [!NOTE]
> Es aconsejable que realice estas tareas después de completar la conmutación por error del grupo de copia de seguridad, porque cuando realice las acciones del paso 2, el grupo de copia de seguridad se convertirá en propietario de los intervalos de números no asignados.




> [!NOTE]
> Estos pasos no son necesarios para los intervalos de números que usan un número de teléfono del Operador automático de la mensajería unificada de Exchange.



**Para crear de nuevo la configuración de anuncios del grupo de copia de seguridad**

1.  Cree de nuevo en el grupo de copia de seguridad los anuncios que implementó en el grupo principal tal como se indica:
    
    1.  Importe los archivos de audio que ha usado en el grupo principal en el grupo de copia de seguridad con el cmdlet **Import-CsAnnouncementFile**, y especifique el grupo de copia de seguridad para el parámetro Principal.
    
    2.  Cree de nuevo cada anuncio con el cmdlet **New-CsAnnouncement** y especifique el grupo de copia de seguridad para el parámetro Principal.
    

    > [!NOTE]
    > Para más información sobre el uso de estos parámetros a la hora de crear anuncios en el grupo de copia de seguridad, consulte <A href="lync-server-2013-create-an-announcement.md">Crear un anuncio en Lync Server 2013</A>.



2.  Tras crear los anuncios en el grupo de copia de seguridad, redirija todos los intervalos de números sin asignar que usan anuncios del grupo principal a los anuncios recreados en el grupo de copia de seguridad.
    
    Para cada intervalo de números no asignados que use un anuncio en el grupo principal, ejecute lo siguiente:
    
        Set-CsUnassignedNumber -Identity "<name of number range>" -AnnouncementService "<FQDN of backup pool>" -AnnouncementName "<announcement name in backup pool>"

## Después de la interrupción del servicio

Cuando el grupo principal se encuentre disponible, deberá redirigir de nuevo a este grupo los intervalos de números no asignados que ha cambiado para la interrupción.


> [!NOTE]
> Estos pasos no son necesarios para los intervalos de números que usan un número de teléfono del Operador automático de la mensajería unificada de Exchange.



**Para restaurar anuncios en el grupo principal**

1.  Si ha creado de nuevo el grupo principal durante la recuperación, deberá volver a crear los anuncios en este grupo. Para ello, importe los archivos de audio y cree los anuncios como lo hizo en el grupo de copia de seguridad, con la excepción de que deberá especificar el grupo principal para el parámetro Principal. Para más información, consulte "Durante la interrupción del servicio", más arriba en este tema.

2.  Para cada intervalo de números no asignados que haya cambiado para la interrupción del servicio, ejecute lo siguiente:
    
        Set-CsUnassignedNumber [-Identity "<name of number range>"] -AnnouncementService "<FQDN of primary pool>" -AnnouncementName "<announcement name in primary pool>"

3.  Si lo desea, quite los anuncios que ha creado de nuevo en el grupo de copia de seguridad. Obtenga una lista de los anuncios para Aplicación de anuncio del grupo de copia de seguridad. En la línea de comandos, ejecute:
    
        Get-CsAnnouncement -Identity "<Service:service ID>"
    
    Por ejemplo:
    
        Get-CsAnnouncement -Identity "ApplicationServer:redmond.contoso.com
    
    En la lista resultante, localice los anuncios que desea quitar y copie los GUID. Para cada anuncio que desee quitar, ejecute:
    
        Remove-CsAnnouncement -Identity "<Service:service ID/guid>"
    
    Por ejemplo:
    
        Remove-CsAnnouncement -Identity "ApplicationServer:redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"


