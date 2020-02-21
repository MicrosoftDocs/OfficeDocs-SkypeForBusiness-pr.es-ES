---
title: 'Lync Server 2013: Asociación de informes de supervisión con una base de datos reflejada'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Associating Monitoring Reports with a mirror database
ms:assetid: 42b797c6-8db8-4ad7-886e-8ddf8deb06f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945624(v=OCS.15)
ms:contentKeyID: 51541467
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7ee0ddc9e5b505a03db1bb1b9f30780c4bc565b3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205412"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="associating-monitoring-reports-with-a-mirror-database-in-lync-server-2013"></a>Asociación de informes de supervisión a una base de datos reflejada en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-02-07_

Si configura un reflejo para la base de datos de supervisión, esa base de datos reflejada asumirá el control como la base de datos principal si se produce una conmutación por error. Sin embargo, si usa informes de supervisión de Lync Server y se produce una conmutación por error, es posible que los informes de supervisión no se conecten a la base de datos reflejada. Esto se debe a que, al instalar los informes de supervisión, solo se especifica la ubicación de la base de datos principal; no se especifica la ubicación de la base de datos reflejada.

Para obtener informes de supervisión para la conmutación por error automática en la base de datos reflejada, debe agregar la base de datos reflejada como "asociado de conmutación por error" a las dos bases de datos que usan los informes de supervisión (una base de datos para los datos del registro de detalles de llamadas y la otra para la calidad de Experience (QoE) de datos). (Tenga en cuenta que este paso debe realizarse después de haber instalado los informes de supervisión). Puede Agregar la información del asociado de conmutación por error editando manualmente los valores de la cadena de conexión que usan estas dos bases de datos. Para ello, lleve a cabo el procedimiento siguiente:

1.  Use Internet Explorer para abrir la Página principal de **SQL Server Reporting Services** . La dirección URL de la Página principal de Reporting Services incluye:
    
      - El prefijo **http:** .
    
      - El nombre de dominio completo (FQDN) del equipo donde está instalado Reporting Services (por ejemplo, **ATL-SQL-001.litwareinc.com**).
    
      - La cadena de **caracteres\_/Reports**.
    
      - El nombre de la instancia de base de datos donde se instalan los informes de supervisión (por ejemplo, **archinst**).
    
    Por ejemplo, si se instaló SQL Server Reporting Services en el equipo atl-sql-001.litwareinc.com y los informes de supervisión usan la instancia de base de datos archinst, la dirección URL de la Página principal tendría el siguiente aspecto:
    
    **http://atl-sql-001.litwareinc.com/Reports\_archinst**

2.  Una vez que haya tenido acceso a la Página principal de Reporting Services, haga clic en **LyncServerReports**y, a continuación, en **contenido de informes\_**. Esto le llevará a la página **de\_contenido de informes** de los informes de supervisión de Lync Server.

3.  En la **página\_contenido de informes** , haga clic en el origen de datos **CDRDB** .

4.  En la página **CDRDB** , en la ficha **propiedades** , busque el cuadro de texto denominado **cadena de conexión**. La cadena de conexión actual tendrá un aspecto similar a este:
    
    **Origen de datos = (local\\) archinst; Initial Catalog = LcsCDR**

5.  Edite la cadena de conexión para incluir el nombre del servidor y la instancia de base de datos de la base de datos reflejada. Por ejemplo, si el servidor se denomina ATL-Mirror-001 y la base de datos reflejada está en la instancia de archinst, tendrá que agregar para especificar la base de datos reflejada con esta sintaxis:
    
    **Asociado de conmutación por error = ATL-\\Mirror-001 archinst**
    
    La cadena de conexión modificada tendrá el siguiente aspecto:
    
    **Origen de datos = (local\\) archinst; Asociado de conmutación por error = ATL-\\Mirror-001 archinst; Initial Catalog = LcsCDR**

6.  Después de actualizar la cadena de conexión, haga clic en **aplicar**.

7.  En la página **CDRDB** , haga clic en el vínculo **contenido de informes\_** . Haga clic en el origen de datos **QMSDB** y, a continuación, edite la cadena de conexión para la base de datos de QoE. Por ejemplo:
    
    **Origen de datos = (local\\) archinst; Asociado de conmutación por error = ATL-\\Mirror-001 archinst; Initial Catalog = QoEMetrics**

8.  Haga clic en **Aplicar**.

<div>

## <a name="see-also"></a>Consulta también


[Instalación de informes de supervisión de Lync Server 2013](lync-server-2013-installing-lync-server-2013-monitoring-reports.md)  
[Uso de informes de supervisión en Lync Server 2013](lync-server-2013-using-monitoring-reports.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

