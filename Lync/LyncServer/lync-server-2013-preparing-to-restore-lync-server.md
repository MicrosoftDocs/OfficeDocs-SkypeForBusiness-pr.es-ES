---
title: 'Lync Server 2013: preparación de la restauración de Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Preparing to restore Lync Server
ms:assetid: 857e4e02-908e-433a-96c6-be1795a9cb61
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202179(v=OCS.15)
ms:contentKeyID: 51541490
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a470a338d05436be942201e6df6a864f955ac87c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823759"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-to-restore-lync-server-2013"></a>Prepararse para restaurar Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-21_

Antes de empezar a restaurar servidores y bases de datos después de un error, debe determinar lo siguiente:

  - Qué se debe restaurar.

  - El hardware, el software, los datos y las herramientas que necesita para la restauración.

<div>

## <a name="determining-what-to-restore"></a>Determinar qué restaurar

En este tema se describe cómo restaurar las interrupciones de Lync Server que se producen en el servidor, grupo o nivel de almacenamiento de administración central. Si se produce un error en el almacén de administración central, la implementación de Lync Server continúa funcionando, pero no puede realizar cambios de configuración. Si se produce un error en un servidor de back-end o un servidor Standard Edition, el grupo de usuarios deja de funcionar. Si se produce un error en cualquier otro servidor, la magnitud del error depende del rol de servidor que se esté ejecutando en el servidor y de si el servidor hospeda una o más bases de datos.

### <a name="what-to-restore"></a>Qué restaurar

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Si esto no se realizó correctamente</th>
<th>Consulte esta sección:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Servidor Standard Edition</p></td>
<td><p><a href="lync-server-2013-restoring-a-standard-edition-server.md">Restaurar un servidor Standard Edition en Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Almacén de administración central</p></td>
<td><p><a href="lync-server-2013-restoring-the-server-hosting-the-central-management-store.md">Restaurar el servidor que hospeda el almacén de administración central en Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Back-end Enterprise Edition</p></td>
<td><p><a href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">Restauración de un servidor de servicios de fondo de la edición empresarial en Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Enterprise Edition back end principal servidor principal</p></td>
<td><p><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md">Restaurar un servidor de servicios de fondo de la edición empresarial duplicada en Lync Server 2013-principal</a></p></td>
</tr>
<tr class="odd">
<td><p>Servidor secundario reflejado de Enterprise Edition</p></td>
<td><p><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">Restaurar un servidor de servicios de fondo de la edición empresarial duplicada en Lync Server 2013-Mirror</a></p></td>
</tr>
<tr class="even">
<td><p>Cualquier servidor Enterprise Edition que ejecute un rol de servidor, como un servidor front end, un servidor EDGE, un director, un servidor de mediación o un servidor de chat persistente.</p></td>
<td><p><a href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">Restaurar un servidor miembro de Enterprise Edition en Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Todo un grupo de servidores de Lync</p></td>
<td><p><a href="lync-server-2013-restoring-a-lync-server-pool.md">Restauración de un grupo de servidores de Lync en Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Enterprise Edition, almacén de archivos</p></td>
<td><p><a href="lync-server-2013-restoring-a-file-store.md">Restaurar un almacén de archivos en Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Una base de datos de seguimiento independiente o una base de datos de archivado</p></td>
<td><p><a href="lync-server-2013-restoring-monitoring-or-archiving-data.md">Restaurar o archivar datos en Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Una base de datos de chat persistente independiente</p></td>
<td><p><a href="lync-server-2013-restoring-persistent-chat-data.md">Restauración de datos de chat persistente en Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="gathering-hardware-software-and-tools"></a>Recopilar hardware, software y herramientas

Cuando restaura un servidor, debe empezar con un equipo nuevo o limpio. Además, debe tener el siguiente hardware y software disponibles:

  - Un servidor limpio o nuevo con el mismo nombre de dominio completo (FQDN) que el servidor con error.
    
    <div>
    

    > [!IMPORTANT]  
    > Cuando instale el sistema operativo, asegúrese de no eliminar la cuenta de equipo en servicios de dominio de Active Directory y compruebe que se conservan los permisos de grupo para la cuenta.

    
    </div>

  - Software de instalación para el sistema operativo. Para instalar el sistema operativo, use los procedimientos y las configuraciones de implementación del servidor que haya establecido su organización. Debe tener estos procedimientos y los requisitos de configuración disponibles al restaurar el servicio.

  - Software de instalación para SQL Server 2012 o SQL Server 2008 R2. Para instalar un servidor de base de datos, use la versión adecuada de SQL Server y los procedimientos y configuraciones de implementación del servidor de base de datos que haya establecido su organización. Debe tener estos procedimientos y los requisitos de configuración disponibles al restaurar el servicio.
    
    <div>
    

    > [!NOTE]  
    > El Asistente para la implementación de Lync Server instala automáticamente SQL Server 2012 Express en cada servidor Standard Edition y en cualquier otro servidor de Lync Server cuando se instala un almacén de configuración local, a menos que tenga SQL Server 2012 preinstalado o SQL Server 2008 R2 en el servidor.

    
    </div>

  - Software para tomar imágenes del sistema.
    
    <div>
    

    > [!TIP]  
    > Le recomendamos que tome una copia de imagen del sistema después de instalar el sistema operativo y SQL Server, y antes de iniciar la restauración para que pueda usar esta imagen como un punto de reversión en caso de que algo falle durante la restauración.

    
    </div>

  - Software de instalación de Lync Server 2013. El Asistente para la implementación de Lync Server se encuentra en la carpeta o los medios \\de\\instalación\\de Lync Server en la instalación AMD64 Setup. exe.

Durante la restauración, se usan las siguientes herramientas:

  - Cmdlets del shell de administración de Lync Server

  - Import-CsUserData

  - Herramientas para restaurar carpetas de Windows

  - Generador de topologías

  - Utilidades de la base de datos de SQL Server, como SQL Server Management Studio

</div>

<div>

## <a name="preparing-to-restore-a-server"></a>Prepararse para restaurar un servidor

Antes de restaurar el servidor, debe realizar los siguientes pasos:

1.  Instale el sistema operativo.

2.  Si el servidor es un servidor de servicios de fondo, instale SQL Server 2012 o SQL Server 2008 R2.

3.  Restaure o reinscriba los certificados. Para obtener más información sobre los certificados, consulte "requisitos de copia de seguridad adicionales" en requisitos de copia de seguridad [y restauración en Lync Server 2013: datos](lync-server-2013-backup-and-restoration-requirements-data.md).

4.  Tome una imagen del sistema antes de iniciar la restauración para usarla como punto de desinstalación, en caso de que algo falle durante la restauración.

<div>


> [!NOTE]  
> El Asistente para la implementación de Lync Server y los cmdlets que se describen en los procedimientos de este tema y temas relacionados, establezca todas las listas de control de acceso (ACL) necesarias.



</div>

Antes de comenzar la restauración, compruebe que el hardware y el software que necesita para los componentes que planea restaurar estén disponibles. Después de instalar el sistema operativo y SQL Server, la mayoría de los pasos de los procedimientos de restauración siguientes se pueden ejecutar de forma remota. Las excepciones se indican en los procedimientos.

También debe tener el plan de copia de seguridad y restauración de su organización y la información de la última copia de seguridad, como la información de las hojas de cálculo de este documento (para obtener información detallada, vea [copias de seguridad y restauración de hojas de cálculo para Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md)), disponible antes de comenzar la restauración.

</div>

</div>

<span> </span>

</div>

</div>

</div>

