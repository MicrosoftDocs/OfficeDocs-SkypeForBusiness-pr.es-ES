---
title: 'Lync Server 2013: hojas de cálculo de copia de seguridad y restauración'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backup and restoration worksheets
ms:assetid: 26c78155-0306-41ac-845b-7ad58000a1d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202169(v=OCS.15)
ms:contentKeyID: 51541460
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3fcf163893a84e4b9244e43b12c702cf0076b1ed
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196033"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-worksheets-for-lync-server-2013"></a>Hojas de cálculo de copia de seguridad y restauración para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-18_

El plan de copia de seguridad y restauración de la organización debe contener detalles sobre cómo y cuándo se realiza la copia de seguridad de los datos y la configuración. Puede usar las hojas de cálculo que se presentan aquí para ayudarle a documentar esta información para su implementación específica y para los requisitos de restauración y copia de seguridad de su organización.

Use las siguientes hojas de trabajo para registrar la información necesaria para realizar copias de seguridad y restaurar la información de configuración de la base de datos, el almacén de archivos y la configuración de un grupo de servidores de Lync Server o un servidor Standard Edition. Conserve una o más copias de estas hojas de cálculo en una ubicación segura para que sean accesibles fácilmente si necesita restaurar Lync Server.

<div>


> [!NOTE]  
> Las hojas de cálculo de esta sección cubren solo la información necesaria para restaurar los datos y la configuración de las bases de datos y los servidores de Lync Server. Si necesita documentar otra información de restauración, como la información para volver a instalar sistemas operativos y otro software, use los planes de implementación de su organización y los planes de copia de seguridad y restauración para cumplir dichos requisitos.



</div>

<div>

## <a name="database-backup-and-restoration-worksheet"></a>Hoja de copia de seguridad y restauración de base de datos

Use la tabla siguiente para registrar la información necesaria para realizar una copia de seguridad de las bases de datos de Lync Server y restaurarlas.

### <a name="database-information-for-backup-and-restoration"></a>Información de base de datos para copia de seguridad y restauración

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th>Base de datos</th>
<th>Nombre del servidor (FQDN)</th>
<th>Programación de copia de seguridad</th>
<th>Herramienta copia de seguridad de base de datos</th>
<th>Conjunto de copia de seguridad</th>
<th>Destino de copia de seguridad</th>
<th>Notas</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Base de datos RTC en el servidor back-end para datos de usuario</p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p><strong>Export-CsUserData</strong> cmdlet</p></td>
<td><p>Denomina</p>
<p>Expiración</p>
<p>                   </p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
</tr>
<tr class="even">
<td><p>Base de datos de LcsLog (nombre predeterminado) en el servidor de base de datos de archivado</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>Herramienta de administración de SQL Server</p></td>
<td><p>Denomina</p>
<p>Expiración</p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p>Base de datos de LcsCdr en servidor de base de datos de supervisión para registros de detalles de llamadas (CDR)</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>Herramienta de administración de SQL Server</p></td>
<td><p>Denomina</p>
<p>Expiración</p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="even">
<td><p>Base de datos de QoEMetrics en el servidor de base de datos de supervisión para datos de calidad de la experiencia (QoE)</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>Herramienta de administración de SQL Server</p></td>
<td><p>Denomina</p>
<p>Expiración</p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p>Base de datos de chat persistente</p></td>
<td></td>
<td></td>
<td><p>Herramienta de administración de SQL Server o cmdlet <strong>Export-CsPersistentChatData</strong></p></td>
<td><p>Denomina</p>
<p>Expiración</p></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


No es necesaria ninguna copia de seguridad ni restauración de las siguientes bases de datos:

  - RTCDyn. Los datos de usuario transitorios de esta base de datos no son necesarios para la restauración del servicio.

  - Rtcab. La base de datos de la libreta de direcciones se vuelve a crear automáticamente a partir de la lista global de direcciones (GAL) de los servicios de dominio de Active Directory.

  - Rgsdyn. Los datos transitorios del servicio de grupo de respuesta de esta base de datos no son necesarios para la restauración del servicio.

  - Cpsdyn. La información dinámica para la aplicación estacionamiento de llamadas no es necesaria para la restauración del servicio.

  - MgcComp. La base de datos de cumplimiento de chat persistente no es necesaria para la restauración del servicio.

</div>

<div>

## <a name="file-store-backup-and-restoration-worksheet"></a>Hoja de cálculo de copia de seguridad y restauración del almacén de archivos

Use la tabla siguiente para registrar la información necesaria para realizar una copia de seguridad de los almacenes de archivos y restaurarlos. Los almacenes de archivos contienen datos como los metadatos de contenido de reuniones, los registros de cumplimiento de actualizaciones, los registros de actualización de dispositivos y los archivos de audio para el grupo de respuesta, estacionamiento de llamadas y aplicaciones de anuncio.

### <a name="file-store-information-for-backup-and-restoration"></a>Información del almacén de archivos para la copia de seguridad y restauración

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th>Contenido</th>
<th>Nombre del servidor (FQDN)</th>
<th>Programación de copia de seguridad</th>
<th>Herramienta de copia de seguridad del sistema de archivos</th>
<th>Copia de seguridad del recurso compartido de archivos *</th>
<th>Destino de copia de seguridad</th>
<th>Notas</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Almacén de archivos de Lync Server</p></td>
<td></td>
<td></td>
<td><p>Herramienta de copia de seguridad estándar, como Robocopy</p></td>
<td><p>Servidor de archivos para Enterprise Edition. De forma predeterminada en Standard Edition, para la implementación de Standard Edition. Normalmente, una por sitio.</p></td>
<td></td>
<td><p>No se deben hacer copias de seguridad de los archivos con el nombre <strong>Meeting.Active</strong>. Estos archivos están en uso y se bloquean mientras se realiza una reunión.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="settings-backup-and-restoration-worksheet"></a>Hoja de cálculo de copia de seguridad y restauración de configuración

Use la tabla siguiente para registrar la información necesaria para realizar una copia de seguridad de la configuración y restaurarla.

### <a name="settings-information-for-backup-and-restoration"></a>Información de configuración para copia de seguridad y restauración

<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th>Base de datos</th>
<th>Nombre del servidor (FQDN)</th>
<th>Programación de copia de seguridad</th>
<th>Herramienta de copia de seguridad</th>
<th>Nombre del archivo de configuración (. xml)</th>
<th>Ubicación de copia de seguridad</th>
<th>Notas</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Base de datos XDS en el almacén de administración central para la configuración de la topología (global)</p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p><strong>Export-CsConfiguration</strong> cmdlet</p></td>
<td><p>                   </p></td>
<td><p>                    </p></td>
<td><p>                   </p></td>
</tr>
<tr class="even">
<td><p>Base de datos de lis en el almacén de administración central para información de ubicación E9-1-1 (global)</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><strong>Export-CsLisConfiguration</strong> cmdlet</p></td>
<td></td>
<td><p> </p></td>
<td><p>                    </p></td>
</tr>
<tr class="odd">
<td><p>Base de datos de RgsConfig en el servidor back-end para la configuración del grupo de respuesta (grupo)</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p><strong>Export-CsRgsConfiguration</strong> cmdlet</p></td>
<td></td>
<td><p> </p></td>
<td><p>                    </p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

