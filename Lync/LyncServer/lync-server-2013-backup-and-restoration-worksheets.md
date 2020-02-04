---
title: 'Lync Server 2013: realizar copias de seguridad y restaurar hojas de cálculo'
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
ms.openlocfilehash: 390d6289daf8075c873e90319642f0e74b61d835
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730370"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-worksheets-for-lync-server-2013"></a>Copias de seguridad y restauración de hojas de cálculo para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-18_

El plan de copia de seguridad y restauración de la organización debe contener detalles sobre cómo y cuándo se realiza la copia de seguridad de los datos y la configuración. Puede usar las hojas de cálculo que se presentan aquí para ayudarle a documentar esta información para su implementación específica y los requisitos de copia de seguridad y restauración de su organización.

Use las siguientes hojas de cálculo para registrar la información que necesita para realizar copias de seguridad y restaurar la información de la base de datos, el almacén de archivos y la configuración de un grupo de servidores de Lync o un servidor Standard Edition. Mantenga una o más copias de estas hojas de cálculo en un lugar seguro para que sean accesibles si necesita restaurar Lync Server.

<div>


> [!NOTE]  
> Las hojas de cálculo de esta sección cubren solo la información necesaria para restaurar los datos y la configuración de las bases de datos y los servidores de Lync Server. Si necesita documentar otra información de restauración, como la información para reinstalar sistemas operativos y otro software, use los planes de implementación de su organización y los planes de copia de seguridad y restauración para cumplir esos requisitos.



</div>

<div>

## <a name="database-backup-and-restoration-worksheet"></a>Hoja de cálculo de copia de seguridad y restauración

Use la tabla siguiente para registrar la información que necesita para realizar copias de seguridad y restaurar las bases de datos de Lync Server.

### <a name="database-information-for-backup-and-restoration"></a>Información de la base de datos para copia de seguridad y restauración

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
<th>Database</th>
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
<td><p>Cmdlet <strong>Export-CsUserData</strong></p></td>
<td><p>Denomina</p>
<p>Currido</p>
<p>                   </p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
</tr>
<tr class="even">
<td><p>LcsLog (nombre predeterminado) base de datos en el servidor de base de datos de archivado</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>Herramienta de administración de SQL Server</p></td>
<td><p>Denomina</p>
<p>Currido</p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p>Base de datos de LcsCdr al supervisar el servidor de base de datos para registros de detalles de llamadas (CDRs)</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>Herramienta de administración de SQL Server</p></td>
<td><p>Denomina</p>
<p>Currido</p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="even">
<td><p>QoEMetrics base de datos de supervisión del servidor de base de datos para los datos de la calidad de la experiencia (QoE)</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>Herramienta de administración de SQL Server</p></td>
<td><p>Denomina</p>
<p>Currido</p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p>Base de datos de chat persistente</p></td>
<td></td>
<td></td>
<td><p>Herramienta de administración de SQL Server o cmdlet <strong>Export-CsPersistentChatData</strong></p></td>
<td><p>Denomina</p>
<p>Currido</p></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


No es necesario realizar copias de seguridad ni restauración de las siguientes bases de datos:

  - Rtcdyn. Los datos de usuario transitorios de esta base de datos no son necesarios para la restauración de servicio.

  - Rtcab. La base de datos de la libreta de direcciones se vuelve a crear automáticamente desde la lista global de direcciones (GAL) en los servicios de dominio de Active Directory.

  - Rgsdyn. Los datos transitorios del servicio de grupo de respuesta de esta base de datos no son necesarios para la restauración de servicio.

  - Cpsdyn. La información dinámica para la aplicación de estacionamiento de llamadas no es necesaria para la restauración del servicio.

  - MgcComp. La base de datos de cumplimiento de la conversación persistente no es necesaria para la restauración de servicio.

</div>

<div>

## <a name="file-store-backup-and-restoration-worksheet"></a>Hoja de cálculo de copia de seguridad y restauración del almacén de archivos

Use la tabla siguiente para registrar la información que necesita para hacer una copia de seguridad de los almacenes de archivos y restaurarlos. Los almacenes de archivos contienen datos como metadatos de contenido de la reunión, registros de cumplimiento de actualizaciones, registros de actualización de dispositivos y archivos de audio para el grupo de respuesta, las llamadas de estacionamiento y las aplicaciones de anuncios.

### <a name="file-store-information-for-backup-and-restoration"></a>Información del almacén de archivos para copia de seguridad y restauración

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
<th>Compartir archivos para realizar una copia de seguridad *</th>
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
<td><p>Servidor de archivos para Enterprise Edition. En Standard Edition de forma predeterminada, para la implementación de Standard Edition. Normalmente, uno por sitio.</p></td>
<td></td>
<td><p>No se debe realizar una copia de seguridad de los archivos llamados <strong>Meeting. Active</strong> . Estos archivos están en uso y se bloquean durante la reunión.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="settings-backup-and-restoration-worksheet"></a>Hoja de cálculo de copia de seguridad y restauración

Use la tabla siguiente para registrar la información que necesita para realizar copias de seguridad y restaurar la configuración.

### <a name="settings-information-for-backup-and-restoration"></a>Información de configuración de copia de seguridad y restauración

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
<th>Database</th>
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
<td><p>Base de datos XDS en el almacén de administración central para configuración de topología (global)</p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p>Cmdlet <strong>Export-CsConfiguration</strong></p></td>
<td><p>                   </p></td>
<td><p>                    </p></td>
<td><p>                   </p></td>
</tr>
<tr class="even">
<td><p>Base de datos de lis en el almacén central de administración para información de la ubicación E9-1-1 (global)</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>Cmdlet <strong>Export-CsLisConfiguration</strong></p></td>
<td></td>
<td><p> </p></td>
<td><p>                    </p></td>
</tr>
<tr class="odd">
<td><p>Base de datos RgsConfig en el servidor back-end para la configuración de grupo de respuesta (grupo)</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>Cmdlet <strong>Export-CsRgsConfiguration</strong></p></td>
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

