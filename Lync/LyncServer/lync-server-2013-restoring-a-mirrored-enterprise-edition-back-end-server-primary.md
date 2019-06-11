---
title: 'Restaurar un servidor de servicios de fondo de la edición empresarial duplicada: principal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restoring a mirrored Enterprise Edition Back End Server - primary
ms:assetid: bc555b46-70c5-4eee-ae91-e195df238293
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945648(v=OCS.15)
ms:contentKeyID: 51541512
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dbf0c8562ed4180fb14bf0bda74a03dd4ee8f746
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823066"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-a-mirrored-enterprise-edition-back-end-server-in-lync-server-2013---primary"></a>Restaurar un servidor de servicios de fondo de la edición empresarial duplicada en Lync Server 2013-principal

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-17_

Si tiene un servidor de servicios de fondo Enterprise Edition en una configuración reflejada y solo se produce un error en la base de datos principal, siga los procedimientos de esta sección. Si la base de datos principal y el reflejo fallan, consulte [restaurar un servidor de servicios de fondo de la edición empresarial en Lync Server 2013](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md). Si solo se produce un error en el reflejo, vea [restaurar un servidor de servicios de fondo empresarial duplicado en Lync server 2013-Mirror](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md). Si se produce un error en la base de datos que hospeda el almacén de administración central, consulte [restaurar el servidor que hospeda el almacén de administración central en Lync server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md). Si se produce un error en un servidor miembro de Enterprise Edition que no es el servidor back-end, consulte [restaurar un servidor miembro de Enterprise Edition en Lync server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).

Le recomendamos que tome una copia de la imagen del sistema antes de comenzar la restauración. Puede usar esta imagen como punto de reversión, en caso de que algo falle durante la restauración. Es posible que desee tomar la copia de la imagen después de instalar el sistema operativo y SQL Server, y restaurar o volver a inscribir los certificados.

En este tema, la base de datos principal de ejemplo tendrá un nombre de dominio completo (FQDN) de BE1.contoso.com y la base de datos reflejada tendrá un FQDN de BE2.contoso.com.

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server-primary-database"></a>Para restaurar una base de datos principal del servidor de servicios de fondo de la edición Enterprise

1.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins, inicie sesión en un servidor front-end.

2.  Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.

3.  Fuerce la conmutación por error de todas las bases de datos configuradas en el reflejo. Para cada uno de los tipos de base de datos que ha configurado en este servidor, escriba el siguiente cmdlet:
    
        Invoke-CsDataBaseFailover -PoolFqdn <Pool FQDN> -DatabaseType <Configured Database Type> -NewPrincipal Mirror -Force -Verbose
    
    Por ejemplo:
    
        Invoke-CsDataBaseFailover -PoolFqdn pool0.vdomain.com -DatabaseType User -NewPrincipal Mirror -Force -Verbose
    
    <div>
    

    > [!WARNING]
    > Si ha configurado la base de datos back-end para usar el reflejo sincronizado con un testigo, la conmutación por error es automática.

    
    </div>

4.  Después de completar la conmutación por error, realice lo siguiente:
    
      - Iniciar generador de topología: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topología de Lync Server**.
    
      - Deshabilite el reflejo en el servidor back-end: haga clic con el botón derecho en la agrupación de **servidores front-end de Enterprise Edition** y seleccione **Editar propiedades**. En la pestaña **General** , en **asociaciones**, desactive la casilla habilitar el reflejo de la **tienda de SQL Server** . Haga esto para archivar y supervisar según sea necesario. A continuación, haga clic en **Aceptar**.
    
      - Haga clic con el botón secundario en el nodo de Lync Server 2013, haga clic en **topología**y, a continuación, en **publicar**.
    
      - Seleccione el back-end en funcionamiento continuado (BE2.contoso.com) para que sea la nueva tienda SQL. Para ello, haga clic con el botón secundario en el grupo de **servidores Enterprise Edition front end** y seleccione **Editar propiedades**. En la pestaña **General** , en **asociaciones**, escriba el FQDN del back-end en el campo del **almacén de SQL Server** (en nuestro ejemplo, BE2.contoso.com).
    
      - Haga clic con el botón secundario en el nodo de Lync Server 2013, haga clic en **topología**y, a continuación, en **publicar**.
    
      - Reinicie servicios para que cada servidor pueda leer la nueva topología. Desde un shell de administración de Lync Server, ejecute los siguientes cmdlets en cada servidor front-end que pertenece a este grupo:
        
            Stop-CsWindowsService
            Start-CsWindowsService

5.  Desinstalar reflejo. Desde un shell de administración de Lync Server, ejecute el siguiente cmdlet:
    
        Uninstall-CsMirrorDatabase -DatabaseType User -SqlServerFqdn <MirrorServerFqdn> -SqlInstanceName <SQLInstance> -verbose
    
    Por ejemplo:
    
        Uninstall-CsMirrorDatabase -DatabaseType User -SqlServerFqdn DB2.contoso.com -SqlInstanceName rtc -verbose
    
    Haga esto para todos los tipos de base de datos en este servidor.

6.  Cree un servidor limpio o nuevo que tenga el mismo FQDN (en este ejemplo, DB1.contoso.com) como el equipo que ha fallado, instale el sistema operativo y, a continuación, restaure o vuelva a inscribir los certificados. Este servidor funcionará como el nuevo reflejo.

7.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins, inicie sesión en el nuevo servidor.

8.  Instale SQL Server 2012 o SQL Server 2008 R2, manteniendo los mismos nombres de instancia que antes del error.

9.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins, inicie sesión en un servidor front-end.

10. Use el generador de topología para instalar la BD de reflejo. Realice los siguientes pasos:
    
      - Iniciar generador de topología: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **generador de topología de Lync Server**.
    
      - Habilitar el reflejo en el servidor back-end. Para ello, haga clic con el botón secundario en el grupo de **servidores Enterprise Edition front end** y seleccione **Editar propiedades**. En la pestaña **General** , en **asociaciones**, seleccione la casilla de verificación Habilitar el reflejo de la **tienda de SQL Server** . También puede hacer esto para archivar y supervisar, si es necesario.
        
        A continuación, en el campo **reflejar el almacén de SQL Server** , escriba el nombre completo del servidor nuevo (n este ejemplo, BE1.contoso.com). A continuación, haga clic en **Aceptar**.
    
      - Haga clic con el botón secundario en el nodo de Lync Server 2013, haga clic en **topología**y, a continuación, en **instalar base de datos**.
    
      - Siga el Asistente para la **instalación de bases de datos** . En la página **crear bases de datos** , seleccione las bases de datos que desea volver a crear.
    
      - Siga el asistente hasta que llegue a la pregunta, **cree una base de datos de reflejo**. Seleccione la base de datos que desee instalar y complete este proceso.

</div>

</div>

<span> </span>

</div>

</div>

</div>

