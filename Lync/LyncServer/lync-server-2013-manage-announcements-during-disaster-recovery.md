---
title: 'Lync Server 2013: administrar anuncios durante la recuperación ante desastres'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manage announcements during disaster recovery
ms:assetid: c33e51ea-421f-42d2-826b-b73968f6bd5b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721874(v=OCS.15)
ms:contentKeyID: 49733807
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6058974b8473bc2c6db91abaaeb1550647ba592d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037540"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-announcements-during-disaster-recovery-in-lync-server-2013"></a>Administrar anuncios durante la recuperación ante desastres en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-23_

Lync Server 2013 admite anuncios para las llamadas a números no asignados durante las interrupciones. La restauración de la funcionalidad de los anuncios durante una interrupción es opcional. Si decide hacerlo, debe volver a crear la configuración de los anuncios en el grupo de copia de seguridad. En esta sección se describe cómo puede restaurar los anuncios durante una recuperación ante desastres.

Esta sección se aplica a los intervalos de números sin asignar que usan la aplicación de anuncio. Esta sección no se aplica a los intervalos de números sin asignar que usan el operador automático de mensajería unificada (MU) de Exchange.

<div>

## <a name="before-an-outage"></a>Antes de la interrupción del servicio

Independientemente de si decide usar anuncios durante las interrupciones, debe realizar copias de seguridad separadas de los archivos de audio personalizados que haya configurado para la aplicación de anuncio. No se realiza una copia de seguridad de los anuncios personalizados como parte del proceso de recuperación ante desastres de Lync Server. Si no hace copias de seguridad independientes, los archivos que ha cargado en el servidor o en el grupo se perderán si se dañan o se borran.

Si no tiene copias de seguridad de los archivos de audio personalizados y los archivos de audio originales ya no están disponibles, puede buscar los archivos de audio que configuró para una aplicación de anuncio en el almacén de archivos del servidor o grupo de servidores donde originalmente importado los archivos. Puede copiar todos los archivos de audio que haya configurado para la aplicación de anuncio desde el almacén de archivos.

**Para copiar archivos de audio desde el almacén de archivos**

1.  En la línea de comandos, ejecute:
    
        Xcopy <Source: Pool Announcement Service File Store path> <Destination>
    
    Por ejemplo:
    
        Xcopy "<Pool File Store Path>\X-ApplicationServer-X\AppServerFiles\RGS\AS" "<Destination: Backup location>"
    
    Donde X-ApplicationServer-X se refiere al identificador de servicio del servidor de aplicaciones del grupo (por ejemplo, 1-ApplicationServer-1").


</div>

<div>

## <a name="during-an-outage"></a>Durante la interrupción del servicio

Para usar la aplicación de anuncio durante una interrupción, debe volver a crear la configuración del anuncio en el grupo de copia de seguridad; para ello, realice las tareas descritas en esta sección.

<div>


> [!NOTE]  
> Es aconsejable que realice estas tareas después de completar la conmutación por error del grupo de copia de seguridad, porque cuando realice las acciones del paso 2, el grupo de copia de seguridad se convertirá en propietario de los intervalos de números no asignados.



</div>

<div>


> [!NOTE]  
> Estos pasos no son necesarios para los intervalos de números que usan el número de teléfono del Operador automático de la mensajería unificada de Exchange.



</div>

**Para volver a crear la configuración del anuncio en el grupo de copia de seguridad**

1.  Cree de nuevo en el grupo de copia de seguridad los anuncios que implementó en el grupo principal tal como se indica:
    
    1.  Importe los archivos de audio que ha usado en el grupo principal en el grupo de copia de seguridad con el cmdlet **Import-CsAnnouncementFile**, y especifique el grupo de copia de seguridad para el parámetro Principal.
    
    2.  Cree de nuevo cada anuncio con el cmdlet **New-CsAnnouncement** y especifique el grupo de copia de seguridad para el parámetro Principal.
    
    <div>
    

    > [!NOTE]  
    > Para obtener información detallada sobre cómo usar estos parámetros para crear anuncios en el grupo de servidores de copia de seguridad, vea <A href="lync-server-2013-create-an-announcement.md">crear un anuncio en Lync Server 2013</A>.

    
    </div>

2.  Tras crear los anuncios en el grupo de copia de seguridad, redirija todos los intervalos de números sin asignar que usan anuncios del grupo principal a los anuncios recreados en el grupo de copia de seguridad.
    
    Para cada intervalo de números no asignados que use un anuncio en el grupo principal, ejecute lo siguiente:
    
        Set-CsUnassignedNumber -Identity "<name of number range>" -AnnouncementService "<FQDN of backup pool>" -AnnouncementName "<announcement name in backup pool>"

</div>

<div>

## <a name="after-the-outage"></a>Después de la interrupción del servicio

Cuando el grupo principal se encuentre disponible, deberá redirigir de nuevo a este grupo los intervalos de números no asignados que ha cambiado para la interrupción.

<div>


> [!NOTE]  
> Estos pasos no son necesarios para los intervalos de números que usan un número de teléfono del Operador automático de la mensajería unificada de Exchange.



</div>

**Para restaurar anuncios en el grupo de servidores principal**

1.  Si ha creado de nuevo el grupo principal durante la recuperación, deberá volver a crear los anuncios en este grupo. Para ello, importe los archivos de audio y cree los anuncios como lo hizo en el grupo de copia de seguridad, con la excepción de que deberá especificar el grupo principal para el parámetro Principal. Para más información, consulte "Durante la interrupción del servicio", más arriba en este tema.

2.  Para cada intervalo de números no asignados que haya cambiado para la interrupción del servicio, ejecute lo siguiente:
    
        Set-CsUnassignedNumber [-Identity "<name of number range>"] -AnnouncementService "<FQDN of primary pool>" -AnnouncementName "<announcement name in primary pool>"

3.  Si lo desea, quite los anuncios que ha creado de nuevo en el grupo de copia de seguridad. Obtenga una lista de anuncios para la aplicación de anuncio del grupo de copia de seguridad. En la línea de comandos, ejecute:
    
        Get-CsAnnouncement -Identity "<Service:service ID>"
    
    Por ejemplo:
    
        Get-CsAnnouncement -Identity "ApplicationServer:redmond.contoso.com
    
    En la lista resultante, localice los anuncios que desea quitar y copie los GUID. Para cada anuncio que desee quitar, ejecute:
    
        Remove-CsAnnouncement -Identity "<Service:service ID/guid>"
    
    Por ejemplo:
    
        Remove-CsAnnouncement -Identity "ApplicationServer:redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"


</div>

</div>

<span> </span>

</div>

</div>

</div>

