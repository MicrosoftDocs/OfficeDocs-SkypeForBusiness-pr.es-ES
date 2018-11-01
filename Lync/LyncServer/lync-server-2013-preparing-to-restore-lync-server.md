---
title: Preparación para restaurar Lync Server
TOCTitle: Preparación para restaurar Lync Server
ms:assetid: 857e4e02-908e-433a-96c6-be1795a9cb61
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Hh202179(v=OCS.15)
ms:contentKeyID: 52061665
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Preparación para restaurar Lync Server

 

_**Última modificación del tema:** 2015-03-09_

Antes de empezar a restaurar los servidores y las bases de datos tras un error, es necesario tener claro lo siguiente:

  - Qué debe restaurarse.

  - Hardware, software, datos y herramientas que se necesitan para llevar a cabo la restauración.

## Saber qué hay que restaurar

En este tema se explica cómo recuperarse de las interrupciones de Lync Server que tienen lugar en el nivel de servidor, de grupo o de Almacén de administración central. En caso de que se produzca un error en el Almacén de administración central, la implementación de Lync Server seguirá funcionando, si bien no se podrá cambiar la configuración. Si el error tiene lugar en un servidor back-end o Standard Edition, el grupo de usuarios dejará de funcionar y, si ocurre en cualquier otro servidor, el alcance del error dependerá del rol de dicho servidor y de si este hospeda una o más bases de datos.

### Qué restaurar

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Si se produce un error en...</th>
<th>Consulte esta sección:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Servidor Standard Edition</p></td>
<td><p><a href="lync-server-2013-restoring-a-standard-edition-server.md">Restaurar un servidor Standard Edition</a></p></td>
</tr>
<tr class="even">
<td><p>Almacén de administración central</p></td>
<td><p><a href="lync-server-2013-restoring-the-server-hosting-the-central-management-store.md">Restaurar el servidor que hospeda el Almacén de administración central</a></p></td>
</tr>
<tr class="odd">
<td><p>Servidor back-end Enterprise Edition</p></td>
<td><p><a href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">Restaurar un servidor back-end Enterprise Edition</a></p></td>
</tr>
<tr class="even">
<td><p>Servidor back-end principal reflejado Enterprise Edition</p></td>
<td><p><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md">Restaurar un servidor back-end Enterprise Edition reflejado: principal</a></p></td>
</tr>
<tr class="odd">
<td><p>Servidor back-end secundario reflejado Enterprise Edition</p></td>
<td><p><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">Restaurar un servidor back-end Enterprise Edition reflejado: reflejar</a></p></td>
</tr>
<tr class="even">
<td><p>Cualquier servidor Enterprise Edition que tenga un rol de servidor, como un Servidor front-end, Servidor perimetral, Director, Servidor de mediación o servidor de chat persistente.</p></td>
<td><p><a href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">Restaurar un servidor miembro de Enterprise Edition</a></p></td>
</tr>
<tr class="odd">
<td><p>Un grupo de Lync Server entero</p></td>
<td><p><a href="lync-server-2013-restoring-a-lync-server-pool.md">Restaurar un grupo de servidores de Lync</a></p></td>
</tr>
<tr class="even">
<td><p>Almacén de archivos de Enterprise Edition</p></td>
<td><p><a href="lync-server-2013-restoring-a-file-store.md">Restaurar un almacén de archivos</a></p></td>
</tr>
<tr class="odd">
<td><p>Una base de datos independiente de supervisión o archivado</p></td>
<td><p><a href="lync-server-2013-restoring-monitoring-or-archiving-data.md">Restaurar, supervisar o archivar datos</a></p></td>
</tr>
<tr class="even">
<td><p>Una base de datos independiente de chat persistente</p></td>
<td><p><a href="lync-server-2013-restoring-persistent-chat-data.md">Restaurar datos de chat persistente</a></p></td>
</tr>
</tbody>
</table>


## Recopilar el hardware, el software y las herramientas

Al restaurar un servidor, se debe empezar con un equipo nuevo o limpio. Además, se necesita disponer del siguiente hardware y software:

  - Un servidor nuevo o limpio con el mismo nombre de dominio completo (FQDN) que el servidor con el error.
    
    > [!IMPORTANT]  
    > Cuando instale el sistema operativo, tenga cuidado de no eliminar la cuenta de equipo en Servicios de dominio de Active Directory y confirme que sigue conservando los permisos de grupo para esa cuenta.
    


  - Software de instalación del sistema operativo. Para instalar el sistema operativo, use las configuraciones y procedimientos de implementación de servidores que se hayan instaurado en la organización. Deberá disponer de estos procedimientos y requisitos de configuración cuando restaure el servicio.

  - Software de instalación de SQL Server 2012 o SQL Server 2008 R2. Para instalar un servidor de bases de datos, use la versión de servidor SQL Server que corresponda, además de las configuraciones y procedimientos de implementación de servidores de bases de datos que se hayan instaurado en la organización. Deberá disponer de estos procedimientos y requisitos de configuración cuando restaure el servicio.
    

    > [!NOTE]
    > El Asistente para implementación de Lync Server instala automáticamente SQL Server 2012 Express en cada Servidor Standard Edition y en cualquier otro servidor Lync Server cuando hay instalado un almacén de configuración local, a menos que haya instalado previamente SQL Server 2012 o SQL Server 2008 R2 en el servidor.



  - Software para tomar imágenes del sistema.
    
    > [!TIP]  
    > Le recomendamos hacer una copia de imagen del sistema después de instalar el sistema operativo y el servidor SQL Server y antes de proceder con la restauración. De este modo, la imagen se podrá usar como punto de reversión en caso de que algo vaya mal durante la restauración.
    


  - Software de instalación de Lync Server 2013. El Asistente para implementación de Lync Server se encuentra en la carpeta o el medio de instalación de Lync Server, en \\setup\\amd64\\Setup.exe.

Durante la restauración se usan las siguientes herramientas:

  - Cmdlets del Shell de administración de Lync Server

  - Import-CsUserData

  - Herramientas para restaurar carpetas de Windows

  - Generador de topologías

  - Utilidades de bases de datos de SQL Server, como SQL Server Management Studio

## Preparación para restaurar un servidor

Antes de restaurar el servidor, haga lo siguiente:

1.  Instalar el sistema operativo.

2.  Si se trata de un servidor back-end, instale SQL Server 2012 o SQL Server 2008 R2.

3.  Restaure o vuelva a inscribir los certificados. Para más información sobre los certificados, consulte la sección “Requisitos adicionales de las copias de seguridad” en [Requisitos de copia de seguridad y restauración: datos](lync-server-2013-backup-and-restoration-requirements-data.md).

4.  Tome una imagen del sistema antes de iniciar la restauración. Podrá usarla como punto de reversión en caso de que algo vaya mal durante el proceso.


> [!NOTE]
> El Asistente para implementación de Lync Server y los cmdlets descritos en los procedimientos de este tema y en temas relacionados, definen todas las listas de control de acceso (ACL) que se necesitan.



Antes de empezar el proceso de restauración, compruebe que dispone del hardware y software que necesita para los componentes que planea restaurar. Tras instalar el sistema operativo y el servidor SQL Server, la mayor parte de los pasos de los siguientes procedimientos de restauración se puede llevar a cabo de forma remota. Las excepciones se indicarán durante el procedimiento.

También debe tener el plan de copia de seguridad y restauración de la organización y la información de la última copia de seguridad, como los datos de las hojas de cálculo de este documento (para obtener información detallada, consulte [Hojas de cálculo de copia de seguridad y restauración](lync-server-2013-backup-and-restoration-worksheets.md)), disponibles antes de iniciar la restauración.

