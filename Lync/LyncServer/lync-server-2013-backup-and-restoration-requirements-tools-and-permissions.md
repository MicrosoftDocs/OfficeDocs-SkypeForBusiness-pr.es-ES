---
title: 'Lync Server 2013: requisitos de copia de seguridad y restauración: herramientas y permisos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: 'Backup and restoration requirements: tools and permissions'
ms:assetid: 35ec2e33-f33e-4f84-9e64-6550fd78aa52
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202171(v=OCS.15)
ms:contentKeyID: 51541465
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 53128d99abfd438c174b98544889781b5f29b57b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842751"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-requirements-in-lync-server-2013-tools-and-permissions"></a>Requisitos de copia de seguridad y restauración en Lync Server 2013: herramientas y permisos

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-17_

En este tema se identifican las herramientas que puede usar para realizar copias de seguridad y restaurar Lync Server 2013, los permisos que necesita y si puede ejecutar comandos de forma remota o local. En concreto, este tema se centra en las herramientas que se proporcionan con Lync Server para realizar copias de seguridad y restauraciones.

<div>

## <a name="backups"></a>Copias

Para hacer una copia de seguridad de Lync Server, use las herramientas identificadas en la tabla siguiente. Todos los comandos necesarios para realizar copias de seguridad de Lync Server se pueden ejecutar en secuencias de comandos y se pueden ejecutar de forma remota.

### <a name="tools-for-backing-up-lync-server"></a>Herramientas para realizar copias de seguridad de Lync Server

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Para hacer una copia de seguridad:</th>
<th>Use esta herramienta o cmdlet:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Datos de configuración de topología (XDS. MDF)</p></td>
<td><p>Export-CsConfiguration</p></td>
</tr>
<tr class="even">
<td><p>Datos del servicio de información de ubicación (E9-1-1) (LIS. MDF)</p></td>
<td><p>Export-CsLisConfiguration</p></td>
</tr>
<tr class="odd">
<td><p>Datos de configuración del grupo de respuesta (RgsConfig. MDF)</p></td>
<td><p>Export-CsRgsConfiguration</p></td>
</tr>
<tr class="even">
<td><p>Datos de usuario persistentes (base de datos Rtcxds. MDF)</p>
<p>Identificadores de conferencia</p></td>
<td><p>Export-CsUserData</p></td>
</tr>
<tr class="odd">
<td><ul>
<li><p>Base de datos de archivado (LcsLog. MDF)</p></li>
<li><p>Supervisión de la base de datos de registros de detalles de llamadas (LcsCDR. MDF)</p></li>
<li><p>Supervisión de la base de datos de QoE (QoEMetrics. MDF)</p></li>
</ul></td>
<td><p>Herramienta de base de datos de SQL Server, como SQL Server Management Studio</p></td>
</tr>
<tr class="even">
<td><p>Base de datos de chat persistente (MGC. MDF)</p></td>
<td><p>Procedimientos de copia de seguridad de SQL Server o Export-CsPersistentChatData. Export-CsPersistentChatData exporta datos de chat persistentes como un archivo.</p></td>
</tr>
<tr class="odd">
<td><p>Todos los almacenes de archivos: almacén de archivos de Lync Server, almacén de archivos de archivado</p>
<div>

> [!NOTE]  
> No se debe realizar una copia de seguridad de los archivos llamados <STRONG>Meeting. Active</STRONG> . Estos archivos están en uso y se bloquean durante la reunión.


</div></td>
<td><p>Herramienta estándar de administración del sistema de archivos, como Robocopy.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="restoration"></a>Restablecimiento

Para restaurar Lync Server, use las herramientas de la tabla siguiente. Todos los comandos que necesita para restaurar Lync Server se pueden incluir en secuencias de comandos. Algunas pueden ejecutarse de forma remota, pero otras personas deben ejecutarse de forma local, como se especifica en la tabla siguiente.

### <a name="tools-for-restoring-lync-server"></a>Herramientas para restaurar Lync Server

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Para ello, haga lo siguiente:</th>
<th>Use esta herramienta o cmdlet:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Crear un equipo nuevo o limpio</p></td>
<td><ul>
<li><p>Software de instalación del sistema operativo Windows</p></li>
<li><p>Software de instalación de SQL Server</p></li>
<li><p>Complemento certificados de Microsoft Management Console (MMC), si se restauran certificados con una clave privada exportable</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Restaurar datos del almacén de archivos</p></td>
<td><p>Herramienta estándar de administración del sistema de archivos, como Robocopy</p></td>
</tr>
<tr class="odd">
<td><p>Vuelva a crear bases de datos vacías y establezca los permisos para lo siguiente:</p>
<ul>
<li><p>Almacén de administración central</p></li>
<li><p>Servidor back-end</p></li>
<li><p>Base de datos de supervisión</p></li>
<li><p>Base de datos de archivado</p></li>
</ul></td>
<td><p>Install-CSDatabase</p></td>
</tr>
<tr class="even">
<td><p>Restaurar el puntero de servicios de dominio de Active Directory al almacén de administración central</p>
<div>

> [!NOTE]  
> Si pierde el punto de conexión de servicio en cualquier momento, puede volver a ejecutar este cmdlet.


</div></td>
<td><p>Set-CsConfigurationStoreLocation</p></td>
</tr>
<tr class="odd">
<td><p>Importar la topología, las directivas y las opciones de configuración en el almacén de administración central (XDS. MDF)</p></td>
<td><p>Import-CsConfiguration</p></td>
</tr>
<tr class="even">
<td><p>Publicar y habilitar la topología</p></td>
<td><p>Generador de topologías</p>
<p>ni</p>
<p>Publish-CsTopology y enable-CsTopology</p></td>
</tr>
<tr class="odd">
<td><p>Habilitar la última topología Publicada</p></td>
<td><p>Enable-CsTopology</p></td>
</tr>
<tr class="even">
<td><p>Reinstalar los componentes de Lync Server</p></td>
<td><p>Instalación de Lync Server</p>
<div>

> [!NOTE]  
> Se encuentra en la carpeta o el medio de instalación de Lync Server en \setup\amd64\Setup.exe.


</div></td>
</tr>
<tr class="odd">
<td><p>Restaurar datos de ubicación (E9-1-1) (LIS. MDF)</p></td>
<td><p>Import-CsLisConfiguration</p></td>
</tr>
<tr class="even">
<td><p>Restaurar datos de usuario persistentes (Rtcxds. MDF)</p></td>
<td><p>Import-CsUserData</p></td>
</tr>
<tr class="odd">
<td><p>Restaurar datos de configuración de grupo de respuesta (RgsConfig. MDF)</p></td>
<td><p>Import-CsRgsConfiguration</p>
<div>

> [!NOTE]  
> Si la configuración se está restaurando en un grupo recién implementado que no tiene datos de grupo de respuesta en la base de datos, debe usar la opción – OverwriteOwner. Use esta opción incluso si los datos que se están restaurando están en un grupo con el mismo nombre de dominio completo (FQDN). De lo contrario, la importación no se realizará correctamente, debido a los objetos de contacto de los grupos de respuesta que ya existen en Active Directory.


</div></td>
</tr>
<tr class="even">
<td><p>Restaure las siguientes bases de datos:</p>
<ul>
<li><p>Base de datos de archivado (LcsLog. MDF)</p></li>
<li><p>Supervisar bases de datos: base de datos de registros de detalles de llamadas (LcsCDR. MDF) y base de datos de QoE (QoEMetrics. MDF)</p></li>
</ul></td>
<td><p>Herramientas de administración de bases de datos de SQL Server</p></td>
</tr>
<tr class="odd">
<td><p>Base de datos de chat persistente (MGS. MDF)</p></td>
<td><p>Procedimientos de restauración de SQL Server o Import-CsPersistentChatData. Puede usar Import-CsPersistentChatData con un archivo creado por Export-CsPersistentChatData y los datos se importarán a la base de datos de chat persistente.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="required-permissions"></a>Permisos necesarios

Los usuarios deben ser miembros del grupo **RTCUniversalServerAdmins** para poder ejecutar todos los comandos que se describen en este tema. La mayoría de los comandos de copia de seguridad y restauración no admiten el control de acceso basado en roles (RBAC). Dos excepciones son los cmdlets de chat persistentes Export-CsPersistentChatData e import-CsPersistentChatData, que deben ser ejecutados por un usuario que sea miembro del grupo CsPersistentChatAdministrator. Para ejecutar el Asistente para la implementación de Lync Server, un usuario también debe ser miembro del grupo de administradores locales.

</div>

</div>

<span> </span>

</div>

</div>

</div>

