---
title: Hojas de cálculo de copia de seguridad y restauración
TOCTitle: Hojas de cálculo de copia de seguridad y restauración
ms:assetid: 26c78155-0306-41ac-845b-7ad58000a1d6
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Hh202169(v=OCS.15)
ms:contentKeyID: 52061611
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Hojas de cálculo de copia de seguridad y restauración

 

_**Última modificación del tema:** 2015-03-09_

El plan de copia de seguridad y restauración de la organización debe incluir detalles sobre cómo y cuándo se crean copias de seguridad de los datos y la configuración. Puede usar las hojas de cálculo que se presentan aquí para documentar esta información para su implementación específica y para los requisitos de copia de seguridad y restauración de la organización.

Utilice las siguientes hojas de cálculo para registrar la información que necesita para la copia de seguridad y restauración de las bases de datos, el Almacén de archivos y la configuración de un grupo de servidores de Lync Server o un Servidor Standard Edition. Conserve una o varias copias de estas hojas de cálculo en una ubicación segura para poder tener acceso a ellas de inmediato si debe restaurar Lync Server.


> [!NOTE]
> Las hojas de cálculo de esta sección abarcan solamente la información necesaria para restaurar los datos y la configuración de bases de datos y servidores de Lync Server. Si necesita documentar otra información de restauración, como la información para reinstalar sistemas operativos y otro tipo de software, utilice los planes de implementación y los planes de copia de seguridad y restauración de la organización para satisfacer esos requisitos.



## Hoja de cálculo de copia de seguridad y restauración de bases de datos

Utilice la tabla siguiente para registrar la información que necesita para la copia de seguridad y restauración de bases de datos de Lync Server.

### Información de bases de datos para copia de seguridad y restauración

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
<th>Herramienta de copia de seguridad de bases de datos</th>
<th>Conjunto de copia de seguridad</th>
<th>Destino de copia de seguridad</th>
<th>Notas</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Base de datos Rtc en servidor back-end para datos de usuario</p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p>Cmdlet <strong>Export-CsUserData</strong></p></td>
<td><p>Nombre:</p>
<p>Expiración:</p>
<p>                   </p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
</tr>
<tr class="even">
<td><p>Base de datos LcsLog (nombre predeterminado) en servidor de Base de datos de archivado</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>Herramienta de administración de SQL Server</p></td>
<td><p>Nombre:</p>
<p>Expiración:</p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p>Base de datos LcsCdr en servidor de Base de datos de supervisión para registro detallado de llamadas (CDR)</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>Herramienta de administración de SQL Server</p></td>
<td><p>Nombre:</p>
<p>Expiración:</p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="even">
<td><p>Base de datos QoEMetrics en servidor de Base de datos de supervisión para datos QoE (Calidad de la experiencia)</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>Herramienta de administración de SQL Server</p></td>
<td><p>Nombre:</p>
<p>Expiración:</p></td>
<td><p> </p></td>
<td><p> </p></td>
</tr>
<tr class="odd">
<td><p>Base de datos de chat persistente</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p>Herramienta de administración de SQL Server o el cmdlet <strong>Export-CsPersistentChatData</strong></p></td>
<td><p>Nombre:</p>
<p>Expiración:</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>


No se requieren operaciones de copia de seguridad y restauración para las bases de datos siguientes:

  - Rtcdyn. Los datos de usuario transitorios de esta base de datos no son necesarios para la restauración del servicio.

  - Rtcab. La base de datos de la libreta de direcciones se vuelve a crear automáticamente a partir de la lista global de direcciones (LGD) en los Servicios de dominio de Active Directory.

  - Rgsdyn. Los datos del servicio de grupo de respuesta transitorios de esta base de datos no son necesarios para la restauración del servicio.

  - Cpsdyn. La información dinámica de la Aplicación de estacionamiento de llamadas no es necesaria para la restauración del servicio.

  - MgcComp. La base de datos de cumplimiento de Chat persistente no es necesaria para la restauración del servicio.

## Hoja de cálculo de copia de seguridad y restauración de almacenes de archivos

Utilice la tabla siguiente para registrar la información que necesita para la copia de seguridad y restauración de almacenes de archivos. Los almacenes de archivos contienen datos, como metadatos de contenido de reuniones, registros de cumplimiento de reuniones, registros de actualizaciones de dispositivos y archivos de audio para las aplicaciones Grupo de respuesta, Estacionamiento de llamadas y Anuncio.

### Información de almacenes de archivos para copia de seguridad y restauración

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
<th>Herramienta de copia de seguridad de sistemas de archivos</th>
<th>Recurso compartido de archivos que se incluirá en la copia de seguridad *</th>
<th>Destino de copia de seguridad</th>
<th>Notas</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Almacén de archivos de Lync Server</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p>Herramienta de copia de seguridad estándar, como Robocopy</p></td>
<td><p>En servidor de archivos para Enterprise Edition. En Standard Edition de forma predeterminada, para la implementación de Standard Edition. Normalmente, uno por sitio.</p></td>
<td><p></p></td>
<td><p>No se deben hacer copias de seguridad de los archivos con el nombre <strong>Meeting.Active</strong>. Estos archivos se usan y bloquean cuando se desarrolla una reunión.</p></td>
</tr>
</tbody>
</table>


## Hoja de cálculo de copia de seguridad y restauración de opciones de configuración

Utilice la tabla siguiente para registrar la información que necesita para la copia de seguridad y restauración de la configuración.

### Información de opciones de configuración para copia de seguridad y restauración

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
<th>Nombre del archivo de configuración (.xml)</th>
<th>Ubicación de copia de seguridad</th>
<th>Notas</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Base de datos Xds en el Almacén de administración central para configuración de topología (global)</p></td>
<td><p>                    </p></td>
<td><p>                    </p></td>
<td><p>Cmdlet <strong>Export-CsConfiguration</strong></p></td>
<td><p>                   </p></td>
<td><p>                    </p></td>
<td><p>                   </p></td>
</tr>
<tr class="even">
<td><p>Base de datos Lis en el Almacén de administración central para información de ubicaciones E9-1-1 (global)</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>Cmdlet <strong>Export-CsLisConfiguration</strong></p></td>
<td><p></p></td>
<td><p> </p></td>
<td><p>                    </p></td>
</tr>
<tr class="odd">
<td><p>Base de datos RgsConfig en servidor back-end para configuración del Grupo de respuesta (grupo de servidores)</p></td>
<td><p> </p></td>
<td><p> </p></td>
<td><p>Cmdlet <strong>Export-CsRgsConfiguration</strong></p></td>
<td><p></p></td>
<td><p> </p></td>
<td><p>                    </p></td>
</tr>
</tbody>
</table>

