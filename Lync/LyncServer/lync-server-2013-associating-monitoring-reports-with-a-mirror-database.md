---
title: 'Lync Server 2013: asociar informes de supervisión a una base de datos reflejada'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Associating Monitoring Reports with a mirror database
ms:assetid: 42b797c6-8db8-4ad7-886e-8ddf8deb06f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945624(v=OCS.15)
ms:contentKeyID: 51541467
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 19ff2455d473c83855320555cdffdc2e33001d0d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842906"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="associating-monitoring-reports-with-a-mirror-database-in-lync-server-2013"></a>Asociar informes de supervisión a una base de datos reflejada en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-02-07_

Si configura una base de datos reflejada para supervisar su base de datos, la reflejada asumirá el puesto de la base de datos principal cuando se produzca una conmutación por error. Sin embargo, si usa los informes de supervisión de Lync Server y se produce un error, es posible que los informes de supervisión no se conecten a la base de datos reflejada. Esto se debe a que, al instalar los informes de supervisión, solo se ha especificado la ubicación de la base de datos principal y no la de la base de datos reflejada.

Para que los informes de supervisión pasen automáticamente a la base datos reflejada en caso de conmutación por error, necesita agregar la base de datos reflejada como "socio de conmutación por error" a las dos bases de datos que utilizan informes de supervisión (una base datos para los datos del registro detallado de llamadas y otra para los datos de Calidad de la experiencia). Tenga presente que este paso se ha de realizar después de haber instalado los informes de supervisión. Puede agregar información de socio de conmutación por error manualmente editando los valores de la cadena de conexión que utilizan las dos bases de datos. Para ello, realice el procedimiento siguiente:

1.  Use Internet Explorer para abrir la página de inicio de **SQL Server Reporting Services**. La dirección URL de la página de inicio de Reporting Services está formada por:
    
      - El prefijo **http:**.
    
      - El nombre de dominio completo (FQDN) del equipo en el que se ha instalado Reporting Services (por ejemplo, **atl-sql-001.litwareinc.com**).
    
      - La cadena de **caracteres\_/Reports**.
    
      - El nombre de la instancia de la base de datos en la que están instalados los informes de supervisión (por ejemplo, **archinst**).
    
    Por ejemplo, si se ha instalado SQL Server Reporting Services en el equipo atl-sql-001.litwareinc.com y los informes de supervisión utilizan la instancia de base de datos archinst, la dirección URL de la página de inicio será:
    
    **http://atl-sql-001.litwareinc.com/Reports\_archinst**

2.  Una vez que haya tenido acceso a la Página principal de Reporting Services, haga clic **LyncServerReports**y luego en **contenido de informes\_**. Esto le llevará a la página **de\_contenido informes** de los informes de supervisión de Lync Server.

3.  En la página de **contenido informes\_** , haga clic en el origen de datos **CDRDB** .

4.  En la página **CDRDB**, en la ficha **Propiedades**, busque el cuadro de texto titulado **Cadena de conexión**. La cadena de conexión actual será similar a:
    
    **Origen de datos = (local\\) archinst; catálogo inicial = LcsCDR**

5.  Modifique la cadena de conexión para incluir el nombre del servidor y la instancia de base de datos de la base de datos reflejada. Por ejemplo, si el servidor se llama atl-mirror-001 y la base de datos reflejada se encuentra en la instancia archinst, tendrá que agregar para especificar la base de datos reflejada esta sintaxis:
    
    **Asociado de conmutación por error = ATL-\\Mirror-001 archinst**
    
    La cadena de conexión resultante necesitará ser:
    
    **Origen de datos = (local\\) archinst; Asociado de conmutación por error = ATL-\\Mirror-001 archinst; Initial Catalog = LcsCDR**

6.  Cuando haya actualizado la cadena de conexión, haga clic en **Aplicar**.

7.  En la página **CDRDB** , haga clic en el vínculo de **contenido informes\_** . Haga clic en el origen de datos **QMSDB** y, luego, modifique la cadena de conexión de la base de datos QoE. Por ejemplo:
    
    **Origen de datos = (local\\) archinst; Asociado de conmutación por error = ATL-\\Mirror-001 archinst; Initial Catalog = QoEMetrics**

8.  Haga clic en **Aplicar**.

<div>

## <a name="see-also"></a>Vea también


[Instalar los informes de supervisión de Lync Server 2013](lync-server-2013-installing-lync-server-2013-monitoring-reports.md)  
[Usar informes de supervisión en Lync Server 2013](lync-server-2013-using-monitoring-reports.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

