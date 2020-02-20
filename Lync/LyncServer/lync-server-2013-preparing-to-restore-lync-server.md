---
title: 'Lync Server 2013: preparación para restaurar Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing to restore Lync Server
ms:assetid: 857e4e02-908e-433a-96c6-be1795a9cb61
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202179(v=OCS.15)
ms:contentKeyID: 51541490
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b397f389de461a04974fe063437caaabd9d4137
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152394"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="preparing-to-restore-lync-server-2013"></a>Preparación de la restauración de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-21_

Antes de empezar a restaurar los servidores y las bases de datos tras un error, es necesario tener claro lo siguiente:

  - Qué se debe restaurar.

  - El hardware, el software, los datos y las herramientas que necesita para la restauración.

<div>

## <a name="determining-what-to-restore"></a>Saber qué hay que restaurar

En este tema se describe cómo restaurar las interrupciones de Lync Server que se producen en el nivel del servidor, del grupo de servidores o del almacén de administración central. Si se produce un error en el almacén de administración central, la implementación de Lync Server sigue funcionando, pero no se pueden realizar cambios en la configuración. Si se produce un error en un servidor back-end o un servidor Standard Edition, el grupo de usuarios deja de funcionar. Si se produce un error en cualquier otro servidor, la magnitud del error depende del rol de servidor que ejecute el servidor y de si el servidor hospeda una o más bases de datos.

### <a name="what-to-restore"></a>Qué restaurar

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
<td><p><a href="lync-server-2013-restoring-a-standard-edition-server.md">Restaurar un servidor Standard Edition en Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Almacén de administración central</p></td>
<td><p><a href="lync-server-2013-restoring-the-server-hosting-the-central-management-store.md">Restauración del servidor que hospeda el almacén de administración central en Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Back-end de Enterprise Edition</p></td>
<td><p><a href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">Restauración de un servidor back-end de Enterprise Edition en Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Servidor principal reflejado de Enterprise Edition</p></td>
<td><p><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md">Restauración de un servidor back-end de Enterprise Edition reflejado en Lync Server 2013-Primary</a></p></td>
</tr>
<tr class="odd">
<td><p>Servidor secundario reflejado de Enterprise Edition</p></td>
<td><p><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">Restauración de un servidor back-end de Enterprise Edition reflejado en Lync Server 2013-Mirror</a></p></td>
</tr>
<tr class="even">
<td><p>Cualquier servidor Enterprise Edition que ejecute una función de servidor, como un servidor front-end, un servidor perimetral, un director, un servidor de mediación o un servidor de chat persistente.</p></td>
<td><p><a href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">Restauración de un servidor miembro de Enterprise Edition en Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Un grupo completo de Lync Server</p></td>
<td><p><a href="lync-server-2013-restoring-a-lync-server-pool.md">Restauración de un grupo de servidores de Lync Server en Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Almacén de archivos de Enterprise Edition</p></td>
<td><p><a href="lync-server-2013-restoring-a-file-store.md">Restaurar un almacén de archivos en Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Una base de datos de supervisión independiente o base de datos de archivado</p></td>
<td><p><a href="lync-server-2013-restoring-monitoring-or-archiving-data.md">Restauración de datos de supervisión o archivado en Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Una base de datos de chat persistente independiente</p></td>
<td><p><a href="lync-server-2013-restoring-persistent-chat-data.md">Restauración de datos de chat persistente en Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="gathering-hardware-software-and-tools"></a>Recopilar el hardware, el software y las herramientas

Al restaurar un servidor, se debe empezar con un equipo nuevo o limpio. Además, debe tener el siguiente hardware y software disponibles:

  - Un servidor nuevo o limpio con el mismo nombre de dominio completo (FQDN) que el servidor con el error.
    
    <div>
    

    > [!IMPORTANT]  
    > Cuando instale el sistema operativo, asegúrese de no eliminar la cuenta de equipo en servicios de dominio de Active Directory y compruebe que se conservan los permisos de grupo de la cuenta.

    
    </div>

  - Un software de instalación del sistema operativo. Para instalar el sistema operativo, use las configuraciones y procedimientos de implementación de servidores que se hayan instaurado en la organización. Debe tener estos procedimientos y requisitos de configuración disponibles al restaurar el servicio.

  - Software de instalación de SQL Server 2012 o SQL Server 2008 R2. Para instalar un servidor de bases de datos, use la versión de servidor SQL Server que corresponda, además de las configuraciones y procedimientos de implementación de servidores de bases de datos que se hayan instaurado en la organización. Debe tener estos procedimientos y requisitos de configuración disponibles al restaurar el servicio.
    
    <div>
    

    > [!NOTE]  
    > El Asistente para la implementación de Lync Server instala automáticamente SQL Server 2012 Express en cada servidor Standard Edition y en cualquier otro servidor de Lync Server cuando se instala un almacén de configuración local, a menos que haya preinstalado SQL Server 2012 o SQL Server 2008 R2 en el servidor.

    
    </div>

  - Software para tomar imágenes del sistema.
    
    <div>
    

    > [!TIP]  
    > Le recomendamos que tome una copia de imagen del sistema después de instalar el sistema operativo y SQL Server, y antes de iniciar la restauración, para que pueda usar esta imagen como un punto de reversión en caso de que algo salga mal durante la restauración.

    
    </div>

  - Software de instalación de Lync Server 2013. El Asistente para la implementación de Lync Server se encuentra en la carpeta de instalación de \\Lync\\Server\\o en el medio de instalación de AMD64 Setup. exe.

Durante la restauración se usan las siguientes herramientas:

  - Cmdlets del shell de administración de Lync Server

  - Import-CsUserData

  - Herramientas para restaurar carpetas de Windows

  - Topology Builder

  - Utilidades de bases de datos de SQL Server, como SQL Server Management Studio

</div>

<div>

## <a name="preparing-to-restore-a-server"></a>Preparación para restaurar un servidor

Antes de restaurar el servidor, debe realizar los siguientes pasos:

1.  Instalar el sistema operativo.

2.  Si el servidor es un servidor back-end, instale SQL Server 2012 o SQL Server 2008 R2.

3.  Restaurar o volver a inscribir los certificados. Para obtener más información sobre los certificados, consulte "requisitos de copia de seguridad adicionales" en [requisitos de copia de seguridad y restauración en Lync Server 2013: datos](lync-server-2013-backup-and-restoration-requirements-data.md).

4.  Tome una imagen del sistema antes de iniciar la restauración para usarla como punto de retroceso, en caso de que algo salga mal durante la restauración.

<div>


> [!NOTE]  
> El Asistente para la implementación de Lync Server y los cmdlets descritos en los procedimientos de este tema y temas relacionados establecen todas las listas de control de acceso (ACL) necesarias.



</div>

Compruebe que el hardware y el software que necesita para los componentes que va a restaurar están disponibles antes de iniciar la restauración. Tras instalar el sistema operativo y el servidor SQL Server, la mayor parte de los pasos de los siguientes procedimientos de restauración se puede llevar a cabo de forma remota. Las excepciones se indicarán durante el procedimiento.

También debe tener el plan de copia de seguridad y restauración de su organización y la información de la última copia de seguridad, como la información de las hojas de cálculo de este documento (para obtener más información, vea [copia de seguridad y restauración de hojas de cálculo para Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md)), disponible antes de comenzar la restauración.

</div>

</div>

<span> </span>

</div>

</div>

</div>

