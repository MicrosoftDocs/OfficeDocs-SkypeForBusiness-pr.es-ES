---
title: Quitar la base de datos de SQL Server de un servidor de supervisión
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove the SQL Server database for a Monitoring server
ms:assetid: aed5e394-d63e-4ad4-af40-f12d3a044344
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721848(v=OCS.15)
ms:contentKeyID: 49733781
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f175f17b41a72c63aba77e6eb59aadce985ced82
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42189393"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-the-sql-server-database-for-a-monitoring-server"></a>Quitar la base de datos de SQL Server de un servidor de supervisión

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-04_

Después de quitar un servidor de supervisión de 2010 de Microsoft Lync Server, puede quitar las bases de datos de SQL Server que hospedaban los datos del servidor. Use los procedimientos siguientes para quitar las definiciones del generador de topologías y, a continuación, quite la base de datos y los archivos de registro del servidor de bases de datos.

<div>

## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>Para quitar la base de datos de SQL Server mediante el generador de topologías

1.  En el servidor front-end de Lync Server 2013, abra el generador de topologías.

2.  En el generador de topologías, vaya a **componentes compartidos** y a **almacenes de SQL Server**, haga clic con el botón secundario en la instancia de SQL Server asociada con el servidor de supervisión quitado o reconfigurado y, a continuación, haga clic en **eliminar**.

3.  Publique la topología y compruebe el estado de replicación.

</div>

<div>

## <a name="to-remove-the-database-files-from-the-sql-server"></a>Para quitar los archivos de base de datos del servidor SQL Server

1.  Para quitar las bases de datos del servidor basado en SQL Server, el usuario debe ser miembro del grupo sysadmins de SQL Server en el servidor SQL Server del que se vayan a quitar los archivos de base de datos.

2.  Abra el Shell de administración de Lync Server.

3.  Escriba lo siguiente en la línea de comandos:
    
        Uninstall-CsDataBase -DatabaseType Monitoring -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    Donde \<FQDN\> es el nombre de dominio completo (FQDN) del servidor de base de datos \<e\> instancia es la instancia opcional de base de datos con nombre.

4.  Cuando el cmdlet **Uninstall-CsDataBase** le pida que confirme las acciones, lea la información y presione **Y** (o Entrar) para continuar, o bien presione **N** y, a continuación, Entrar si desea detener el cmdlet (esto es, cuando haya errores).

</div>

</div>

<span> </span>

</div>

</div>

</div>

