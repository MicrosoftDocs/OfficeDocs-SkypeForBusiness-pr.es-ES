---
title: Asociar informes de supervisión con una base de datos reflejada en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 42b797c6-8db8-4ad7-886e-8ddf8deb06f9
description: 'Resumen: obtenga información sobre cómo asociar informes de supervisión con una base de datos reflejada usada por Skype Empresarial Server.'
ms.openlocfilehash: 723d01f732259098c714eaac330eeaf8c686acac
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58600665"
---
# <a name="associate-monitoring-reports-with-a-mirror-database-in-skype-for-business-server"></a>Asociar informes de supervisión con una base de datos reflejada en Skype Empresarial Server 
 
**Resumen:** Obtenga información sobre cómo asociar informes de supervisión con una base de datos reflejada usada por Skype Empresarial Server.
  
## <a name="monitor-reports-with-a-mirror-database"></a>Supervisar informes con una base de datos reflejada

Si configura un reflejo para la base de datos de supervisión, esa base de datos reflejada tomará el control como base de datos principal si se produce una conmutación por error. Sin embargo, si usa Skype Empresarial Server de supervisión y se produce una conmutación por error, es posible que los informes de supervisión no se conecten a la base de datos reflejada. Esto se debe a que, al instalar informes de supervisión, se especifica solo la ubicación de la base de datos principal; no se especifica la ubicación de la base de datos reflejada.
  
Para obtener informes de supervisión para conmutar automáticamente por error a la base de datos reflejada, debe agregar la base de datos reflejada como un "partner de conmutación por error" a las dos bases de datos que usan los informes de supervisión (una base de datos para datos de registro de detalles de llamadas y otra para datos de calidad de la experiencia (QoE). (Tenga en cuenta que este paso debe realizarse después de instalar los informes de supervisión). Puede agregar la información del asociado de conmutación por error editando manualmente los valores de cadena de conexión usados por estas dos bases de datos. Para ello, lleve a cabo el procedimiento siguiente:
  
1. Use Internet Explorer para abrir la **SQL Server Reporting Services** principal. La dirección URL de la página principal de Reporting Services incluye:
    
   - Prefijo **http:.**
    
   - Nombre de dominio completo (FQDN) del equipo donde está instalado Reporting Services (por ejemplo, **atl-sql-001.litwareinc.com**).
    
   - La cadena de **caracteres /Reports_**.
    
   - Nombre de la instancia de base de datos donde están instalados los informes de supervisión (por ejemplo, **archinst**).
    
     Por ejemplo, si SQL Server Reporting Services se instaló en el equipo atl-sql-001.litwareinc.com y los informes de supervisión usan el archivador de instancia de base de datos, la dirección URL de la página principal tendría este aspecto:
    
     **http://atl-sql-001.litwareinc.com/Reports_archinst**
    
2. Después de tener acceso a la página principal de Reporting Services, haga clic en **ServerReports** y, a continuación, haga clic **en Reports_Content**. Esto le llevará a la página **Reports_Content** para los Skype Empresarial Server de supervisión.
    
3. En la **Reports_Content,** haga clic en el origen de **datos CDRDB.**
    
4. En la **página CDRDB,** en la ficha **Propiedades,** busque el cuadro de texto con la etiqueta **Cadena de conexión**. La cadena de conexión actual tendrá un aspecto similar al siguiente:
    
    Data source=(local)\archinst;initial catalog=LcsCDR
    
5. Edite la cadena de conexión para incluir el nombre del servidor y la instancia de la base de datos reflejada. Por ejemplo, si el servidor se denomina atl-mirror-001 y la base de datos reflejada está en la instancia de archivador, deberá agregar para especificar la base de datos reflejada con esta sintaxis:
    
    Failover Partner=atl-mirror-001\archinst
    
    La cadena de conexión editada tendrá este aspecto:
    
    Data source=(local)\archinst; Failover Partner=atl-mirror-001\archinst;initial catalog=LcsCDR
    
6. Después de actualizar la cadena de conexión, haga clic **en Aplicar**.
    
7. En la **página CDRDB,** haga clic en **Reports_Content** vínculo. Haga clic en **el origen de datos de QMSDB** y, a continuación, edite la cadena de conexión de la base de datos de QoE. Por ejemplo:
    
    Data source=(local)\archinst; Failover Partner=atl-mirror-001\archinst;initial catalog=QoEMetrics
    
8. Haga clic en **Aplicar**.
    
## <a name="see-also"></a>Consulte también

[Instalar informes de supervisión en Skype Empresarial Server](install-monitoring-reports.md)
  
[Uso de informes de supervisión en Skype Empresarial Server](../../manage/health-and-monitoring/monitoring-reports.md)
