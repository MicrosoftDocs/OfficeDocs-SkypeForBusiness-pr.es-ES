---
title: 'Requisitos de copia de seguridad y restauracion: herramientas y permisos'
TOCTitle: 'Requisitos de copia de seguridad y restauracion: herramientas y permisos'
ms:assetid: 35ec2e33-f33e-4f84-9e64-6550fd78aa52
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Hh202171(v=OCS.15)
ms:contentKeyID: 52061622
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Requisitos de copia de seguridad y restauracion: herramientas y permisos

 

_**Última modificación del tema:** 2015-03-09_

En este tema se identifican las herramientas que puede usar para realizar copias de seguridad de Lync Server 2013 y restaurarlo, los permisos que necesita y si puede ejecutar comandos de forma remota o local. Particularmente, este tema hace hincapié en las herramientas proporcionadas con Lync Server para copia de seguridad y restauración.

## Copias de seguridad

Para realizar una copia de seguridad de Lync Server, utilice las herramientas identificadas en la siguiente tabla. Todos los comandos necesarios para realizar una copia de seguridad de Lync Server pueden generarse por script y ejecutarse de forma remota.

### Herramientas para realizar una copia de seguridad de Lync Server

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Para realizar una copia de seguridad de este elemento:</th>
<th>Use esta herramienta o cmdlet:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Datos de configuración de la topología (Xds.mdf)</p></td>
<td><p>Export-CsConfiguration</p></td>
</tr>
<tr class="even">
<td><p>Datos del servicio de información de ubicaciones (E9-1-1) (Lis.mdf)</p></td>
<td><p>Export-CsLisConfiguration</p></td>
</tr>
<tr class="odd">
<td><p>Datos de configuración del grupo de respuesta (RgsConfig.mdf)</p></td>
<td><p>Export-CsRgsConfiguration</p></td>
</tr>
<tr class="even">
<td><p>Datos de usuario persistentes (base de datos Rtcxds.mdf)</p>
<p>ID de conferencia</p></td>
<td><p>Export-CsUserData</p></td>
</tr>
<tr class="odd">
<td><ul>
<li><p>Base de datos de archivado (LcsLog.mdf)</p></li>
<li><p>Base de datos de registros de detalles de las llamadas de supervisión (LcsCDR.mdf)</p></li>
<li><p>Base de datos de QoE de supervisión (QoEMetrics.mdf)</p></li>
</ul></td>
<td><p>Herramienta de base de datos de SQL Server, como SQL Server Management Studio</p></td>
</tr>
<tr class="even">
<td><p>Base de datos de chat persistente (Mgc.mdf)</p></td>
<td><p>Procedimientos de copia de seguridad de SQL Server o Export-CsPersistentChatData. Export-CsPersistentChatData exporta los datos de chat persistente como un archivo.</p></td>
</tr>
<tr class="odd">
<td><p>Todos los almacenes de archivos: almacén de archivos de Lync Server, almacén de archivos de archivado</p>
<div>

> [!NOTE]
> No se deben hacer copias de seguridad de los archivos con el nombre <STRONG>Meeting.Active</STRONG>. Estos archivos se usan y bloquean cuando se desarrolla una reunión.


</div></td>
<td><p>Herramienta de administración de sistemas de archivos estándar, como Robocopy.</p></td>
</tr>
</tbody>
</table>


## Restauración

Para restaurar Lync Server, utilice las herramientas de la siguiente tabla. Todos los comandos necesarios para restaurar Lync Server pueden generarse por script. Algunos pueden ejecutarse de forma remota, pero otros deben ejecutarse de forma local, tal como se indica en la siguiente tabla.

### Herramientas para restaurar Lync Server

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Para ello:</th>
<th>Use esta herramienta o cmdlet:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Cree un equipo nuevo o limpio</p></td>
<td><ul>
<li><p>Software de instalación del sistema operativo Windows</p></li>
<li><p>Software de instalación de SQL Server</p></li>
<li><p>Complemento Certificates Microsoft Management Console (MMC), si se restauran certificados con una clave privada exportable</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Restaurar datos del almacén de archivos</p></td>
<td><p>Herramienta de administración de sistemas de archivos estándar, como Robocopy</p></td>
</tr>
<tr class="odd">
<td><p>Vuelva a crear bases de datos vacías y establecer permisos para lo siguiente:</p>
<ul>
<li><p>Almacén de administración central</p></li>
<li><p>Servidor back-end</p></li>
<li><p>Base de datos de supervisión</p></li>
<li><p>Base de datos de archivado</p></li>
</ul></td>
<td><p>Install-CSDatabase</p></td>
</tr>
<tr class="even">
<td><p>Restaurar el puntero de Servicios de dominio de Active Directory en Almacén de administración central</p>
<div>

> [!NOTE]
> Si pierde el punto de conexión de servicio en cualquier momento, puede volver a ejecutar este cmdlet.


</div></td>
<td><p>Set-CSConfigurationStoreLocation</p></td>
</tr>
<tr class="odd">
<td><p>Importar la topología, las directivas y las opciones de configuración a Almacén de administración central (Xds.mdf)</p></td>
<td><p>Import-CsConfiguration</p></td>
</tr>
<tr class="even">
<td><p>Publicar y habilitar la topología</p></td>
<td><p>Generador de topologías</p>
<p>o bien</p>
<p>Publish-CsTopology y Enable-CsTopology</p></td>
</tr>
<tr class="odd">
<td><p>Habilitar la última topología publicada</p></td>
<td><p>Enable-CSTopology</p></td>
</tr>
<tr class="even">
<td><p>Volver a instalar componentes de Lync Server</p></td>
<td><p>Instalación de Lync Server</p>
<div>

> [!NOTE]
> Ubicado en el medio o la carpeta de instalación de Lync Server en \setup\amd64\Setup.exe.


</div></td>
</tr>
<tr class="odd">
<td><p>Restaurar datos de información de ubicaciones (E9-1-1) (Lis.mdf)</p></td>
<td><p>Import-CsLisConfiguration</p></td>
</tr>
<tr class="even">
<td><p>Restaurar datos de usuario persistentes (Rtcxds.mdf)</p></td>
<td><p>Import-CsUserData</p></td>
</tr>
<tr class="odd">
<td><p>Restaurar datos de configuración del grupo de respuesta (RgsConfig.mdf)</p></td>
<td><p>Import-CsRgsConfiguration</p>
<div>

> [!NOTE]
> Si la configuración se está restaurando en un grupo recientemente implementado que aún no tiene datos del grupo de respuesta en la base de datos, debe usar la opción –OverwriteOwner. Use esta opción incluso si los datos se restauran en un grupo con el mismo nombre de dominio completo (FQDN). De lo contrario, la importación no se completará correctamente debido a que los objetos de contacto a los grupos de respuesta ya existirán en Active Directory.


</div></td>
</tr>
<tr class="even">
<td><p>Restaure las siguientes bases de datos:</p>
<ul>
<li><p>Base de datos de archivado (LcsLog.mdf)</p></li>
<li><p>Bases de datos de supervisión: base de datos de registros de detalles de las llamadas (LcsCDR.mdf) y base de datos QoE (QoEMetrics.mdf)</p></li>
</ul></td>
<td><p>Herramientas de administración de bases de datos de SQL Server</p></td>
</tr>
<tr class="odd">
<td><p>Base de datos de chat persistente (Mgs.mdf)</p></td>
<td><p>Procedimientos de restauración de SQL Server o Import-CsPersistentChatData. Puede usar Import-CsPersistentChatData con un archivo creado por Export-CsPersistentChatData para importar los datos en la base de datos de chat persistente.</p></td>
</tr>
</tbody>
</table>


## Permisos necesarios

Los usuarios deben ser miembros del grupo **RTCUniversalServerAdmins** para ejecutar todos los comandos descritos en este tema. La mayoría de los comandos de restauración y copia de seguridad no son compatibles con el control de acceso basado en roles (RBAC). Dos excepciones son los cmdlets de chat persistente Export-CsPersistentChatData e Import-CsPersistentChatData, los cuales debe ejecutar un usuario que pertenezca al grupo CsPersistentChatAdministrator. Para ejecutar el Asistente para la implementación de Lync Server, el usuario también debe pertenecer al grupo de administradores locales.

