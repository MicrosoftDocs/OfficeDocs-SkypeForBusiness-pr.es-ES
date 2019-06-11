---
title: Quitar la base de datos de SQL Server para un grupo de servidores front-end
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Remove the SQL Server database for a Front End pool
ms:assetid: 6bb932df-3ed7-49b6-ae17-61e4c6a5fe82
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688084(v=OCS.15)
ms:contentKeyID: 49733681
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a6dcbe9bcab20438d02fe489666f9b4c0c0f6d0b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849857"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-the-sql-server-database-for-a-front-end-pool"></a>Quitar la base de datos de SQL Server para un grupo de servidores front-end

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-04_

Después de quitar un grupo front-end de Microsoft Lync Server 2010 o volver a configurar el grupo para que use una base de datos diferente, puede quitar las bases de datos de SQL Server que hospedaron los datos del grupo. Use los procedimientos siguientes para quitar las definiciones del generador de topología y, a continuación, quite los archivos de base de datos y de registro del servidor de base de datos.

<div>

## <a name="to-remove-the-sql-server-database-using-topology-builder"></a>Para quitar la base de datos de SQL Server con el generador de topologías

1.  Desde el servidor front-end de Lync Server 2013, abra Topology Builder y descargue la topología existente.

2.  En el generador de topología, vaya a **componentes** compartidos y, a continuación, a **almacenes de SQL Server**, haga clic con el botón secundario en la instancia de SQL Server asociada al grupo front-end eliminado o reconfigurado y, a continuación, haga clic en **eliminar**.

3.  Publique la topología y, a continuación, compruebe el estado de replicación.

</div>

<div>

## <a name="to-remove-user-and-application-databases-from-the-sql-server"></a>Para quitar bases de datos de usuario y de aplicación de SQL Server

1.  Para quitar las bases de datos de SQL Server, debe ser miembro del grupo de administradores de bases de datos de SQL Server para el servidor SQL donde va a quitar los archivos de base de datos.

2.  Abrir el shell de administración de Lync Server

3.  Para quitar la base de datos para el almacén de usuario del grupo, escriba:
    
        Uninstall-CsDataBase -DatabaseType User -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    Donde \<FQDN\> es el nombre de dominio completo (FQDN) del servidor de la base de \<datos\> , e instancia es la instancia de la base de datos con nombre (es decir, si se definió una).

4.  Para quitar la base de datos para el almacén de aplicaciones del grupo, escriba:
    
        Uninstall-CsDataBase -DatabaseType Application -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    Donde \<FQDN\> es el nombre completo del servidor de la base \<de\> datos e instancia es la instancia de la base de datos nombrada (es decir, si se definió una).

5.  Cuando el cmdlet **Uninstall-CsDataBase** le pida que confirme las acciones, lea la información y, a continuación, presione **s** (o presione Entrar) para continuar, o presione **N** y después entrar si quiere detener el cmdlet (es decir, en caso de que se produzcan errores).

</div>

</div>

<span> </span>

</div>

</div>

</div>

