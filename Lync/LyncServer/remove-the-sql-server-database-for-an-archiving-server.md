---
title: Quitar la base de datos de SQL Server de un servidor de archivado
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove the SQL Server database for an Archiving server
ms:assetid: 6e8a1fcd-ed09-43b0-82c9-60e7ce116a01
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688087(v=OCS.15)
ms:contentKeyID: 49733686
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 57a820780b7ca3646ba9fa6cc5d02a3c5022db9d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765571"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-the-sql-server-database-for-an-archiving-server"></a>Quitar la base de datos de SQL Server de un servidor de archivado

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-04_

Después de quitar un servidor de archivado de Microsoft Lync Server 2010, puede quitar las bases de datos de SQL Server que hospedaron los datos del grupo. Use los procedimientos siguientes para quitar las definiciones del generador de topología y, a continuación, quite los archivos de base de datos y de registro del servidor de base de datos.

<div>

## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>Para quitar la base de datos de SQL Server con el generador de topologías

1.  En el servidor front-end de Lync Server 2013, abra Topology Builder.

2.  En el generador de topología, vaya a **componentes compartidos** y, a continuación, a **almacenes de SQL Server**, haga clic con el botón secundario en la instancia de SQL Server asociada al servidor de archivado reconfigurado o quitado y, a continuación, haga clic en **eliminar**.

3.  Publique la topología y, a continuación, compruebe el estado de replicación.

</div>

<div>

## <a name="to-remove-the-database-files-from-the-sql-server"></a>Para quitar los archivos de base de datos de SQL Server

1.  Para quitar las bases de datos de SQL Server, debe ser miembro del grupo de administradores de bases de datos de SQL Server para el servidor SQL donde va a quitar los archivos de base de datos.

2.  Abra el shell de administración de Lync Server.

3.  En la línea de comandos, escriba:
    
        Uninstall-CsDataBase -DatabaseType Archiving -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    Donde \<FQDN\> es el nombre de dominio completo (FQDN) del servidor de la base de \<datos\> , e instancia es la instancia de la base de datos con nombre (es decir, si se definió una).

4.  Cuando el cmdlet **Uninstall-CsDataBase** le pida que confirme las acciones, lea la información y, a continuación, presione **s** (o presione Entrar) para continuar, o presione **N** y después entrar si quiere detener el cmdlet (es decir, en caso de que se produzcan errores).

</div>

</div>

<span> </span>

</div>

</div>

</div>

