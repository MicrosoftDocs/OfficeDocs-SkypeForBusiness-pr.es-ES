---
title: 'Lync Server 2013: Administrar anuncios durante la recuperación ante desastres'
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
ms.openlocfilehash: dfc987ea579bef4e2b02c8da210efe9a707c5900
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733430"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-announcements-during-disaster-recovery-in-lync-server-2013"></a>Administrar anuncios durante la recuperación ante desastres en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-23_

Lync Server 2013 admite anuncios de llamadas a números no asignados durante las interrupciones. La función de restauración de la presentación durante una interrupción es opcional. Si decide restaurar los anuncios durante una interrupción, tendrá que volver a crear la configuración del anuncio en el grupo de copia de seguridad. En esta sección se describe lo que debe hacer si elige restaurar los anuncios durante la recuperación de desastres.

Esta sección se aplica a los intervalos de números sin asignar que usan la aplicación de anuncios. Esta sección no se aplica a los intervalos de números sin asignar que usan el operador automático de mensajería unificada (UM) de Exchange.

<div>

## <a name="before-an-outage"></a>Antes de una interrupción

Independientemente de si opta por usar anuncios durante las interrupciones, debe realizar copias de seguridad separadas de los archivos de audio personalizados que haya configurado para la aplicación de anuncios. No se realiza una copia de seguridad de los anuncios personalizados como parte del proceso de recuperación de desastres de Lync Server. Si no se realizan copias de seguridad separadas de los archivos y los archivos que ha cargado en el servidor o grupo de servidores están dañados, dañados o borrados, los archivos se perderán.

Si no tiene copias de seguridad de archivos de audio personalizados y los archivos de audio originales ya no están disponibles, puede buscar los archivos de audio que ha configurado para una aplicación de anuncio en el almacén de archivos del servidor o grupo de servidores donde originalmente ha importado los archivos. Puede copiar todos los archivos de audio que haya configurado para la aplicación de anuncios desde el almacén de archivos.

**Para copiar archivos de audio desde el almacén de archivos**

1.  En la línea de comandos, ejecute:
    
        Xcopy <Source: Pool Announcement Service File Store path> <Destination>
    
    Por ejemplo:
    
        Xcopy "<Pool File Store Path>\X-ApplicationServer-X\AppServerFiles\RGS\AS" "<Destination: Backup location>"
    
    Donde X-ApplicationServer-X se refiere al identificador de servicio del servidor de aplicaciones del grupo (por ejemplo, 1-ApplicationServer-1 ")


</div>

<div>

## <a name="during-an-outage"></a>Durante una interrupción

Para usar la aplicación de anuncios durante una interrupción, debe volver a crear la configuración del anuncio en el grupo de copias de seguridad llevando a cabo las tareas descritas en esta sección.

<div>


> [!NOTE]  
> Le recomendamos que realice estas tareas después de la conmutación por error al grupo de copias de seguridad, ya que, tan pronto como realice el paso 2, el grupo de copia de seguridad tomará la propiedad de los intervalos de números sin asignar.



</div>

<div>


> [!NOTE]  
> Estos pasos no son necesarios para los intervalos de números que usan un número de teléfono de operador automático de mensajería unificada de Exchange.



</div>

**Para volver a crear la configuración del anuncio en el grupo de copias de seguridad**

1.  Vuelva a crear los anuncios que ha implementado en el grupo principal del grupo de copias de seguridad de la siguiente manera:
    
    1.  Importe los archivos de audio que se usan en el grupo primario al grupo de copia de seguridad usando el cmdlet **Import-CsAnnouncementFile** y especificando el grupo de copia de seguridad para el parámetro principal.
    
    2.  Vuelva a crear cada anuncio con el cmdlet **New-CsAnnouncement** y especifique el grupo de copias de seguridad para el parámetro principal.
    
    <div>
    

    > [!NOTE]  
    > Para obtener detalles sobre el uso de estos parámetros para crear anuncios en el grupo de copia de seguridad, vea <A href="lync-server-2013-create-an-announcement.md">crear un anuncio en Lync Server 2013</A>.

    
    </div>

2.  Una vez que todos los anuncios se vuelvan a crear en el grupo de copia de seguridad, redirija todos los intervalos de números no asignados que usan anuncios en el grupo primario para los anuncios recreados en el grupo de copias de seguridad.
    
    Para cada intervalo de números no asignado que usa un anuncio en el grupo primario, ejecute lo siguiente:
    
        Set-CsUnassignedNumber -Identity "<name of number range>" -AnnouncementService "<FQDN of backup pool>" -AnnouncementName "<announcement name in backup pool>"

</div>

<div>

## <a name="after-the-outage"></a>Después de la interrupción

Cuando el grupo principal esté disponible, tendrá que redirigir los intervalos de números no asignados que ha cambiado para la interrupción en el repositorio principal.

<div>


> [!NOTE]  
> Estos pasos no son necesarios para los intervalos de números que usan un número de teléfono de operador automático de mensajería unificada de Exchange.



</div>

**Para restaurar anuncios en el grupo primario**

1.  Si tiene que reconstruir el grupo primario durante la recuperación, tendrá que volver a crear los anuncios en el grupo primario importando los archivos de audio y creando anuncios de la misma forma que lo hizo en el grupo de copias de seguridad, excepto que especifique el grupo primario para el principal parámetro. Para obtener más información, vea "durante una interrupción" anteriormente en este tema.

2.  Para cada intervalo de números no asignado que haya cambiado para la interrupción, ejecute lo siguiente:
    
        Set-CsUnassignedNumber [-Identity "<name of number range>"] -AnnouncementService "<FQDN of primary pool>" -AnnouncementName "<announcement name in primary pool>"

3.  De manera opcional, quite los anuncios que ha recreado en el grupo de copia de seguridad. Obtenga una lista de anuncios para la aplicación de anuncios del grupo de copia de seguridad. En la línea de comandos, ejecute:
    
        Get-CsAnnouncement -Identity "<Service:service ID>"
    
    Por ejemplo:
    
        Get-CsAnnouncement -Identity "ApplicationServer:redmond.contoso.com
    
    En la lista resultante, busque los anuncios que desea quitar y copie los GUIDs. Para cada anuncio que desee quitar, ejecute:
    
        Remove-CsAnnouncement -Identity "<Service:service ID/guid>"
    
    Por ejemplo:
    
        Remove-CsAnnouncement -Identity "ApplicationServer:redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"


</div>

</div>

<span> </span>

</div>

</div>

</div>

