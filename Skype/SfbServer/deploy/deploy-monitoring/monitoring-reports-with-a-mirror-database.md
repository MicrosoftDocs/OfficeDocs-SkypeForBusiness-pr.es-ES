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
localization_priority: Normal
ms.assetid: 42b797c6-8db8-4ad7-886e-8ddf8deb06f9
description: 'Resumen: obtenga información sobre cómo asociar informes de supervisión con una base de datos reflejada usada por Skype Empresarial Server.'
ms.openlocfilehash: 4ce6d420f6b29a5c6160b9b220e5fd190a977f9d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802170"
---
# <a name="associate-monitoring-reports-with-a-mirror-database-in-skype-for-business-server"></a>Asociar informes de supervisión con una base de datos reflejada en Skype Empresarial Server 
 
**Resumen:** Obtenga información sobre cómo asociar informes de supervisión con una base de datos reflejada usada por Skype Empresarial Server.
  
## <a name="monitor-reports-with-a-mirror-database"></a>Supervisión de informes con una base de datos reflejada

Si configura un reflejo para la base de datos de supervisión, esa base de datos reflejada tomará el control como base de datos principal si se produce una conmutación por error. Sin embargo, si usa los informes de supervisión de Skype Empresarial Server y se produce una conmutación por error, es posible que los informes de supervisión no se conecten a la base de datos reflejada. Esto se debe a que, al instalar informes de supervisión, solo se especifica la ubicación de la base de datos principal; no se especifica la ubicación de la base de datos reflejada.
  
Para obtener informes de supervisión para conmutar automáticamente por error a la base de datos reflejada, debe agregar la base de datos reflejada como "socio de conmutación por error" a las dos bases de datos que usan los informes de supervisión (una base de datos para los datos del registro detallado de llamadas y otra para los datos de calidad de la experiencia (QoE). (Tenga en cuenta que este paso debe realizarse después de instalar los informes de supervisión). Puede agregar la información del asociado de conmutación por error editando manualmente los valores de cadena de conexión usados por estas dos bases de datos. Para ello, lleve a cabo el procedimiento siguiente:
  
1. Use Internet Explorer para abrir la **página principal SQL Server Reporting Services.** La dirección URL de la página principal de Reporting Services incluye:
    
   - Prefijo **http:**
    
   - El nombre de dominio completo (FQDN) del equipo donde está instalado Reporting Services (por ejemplo, **atl-sql-001.litwareinc.com**).
    
   - La cadena de caracteres **/Reports_**.
    
   - El nombre de la instancia de base de datos donde están instalados los informes de supervisión (por ejemplo, **archinst**).
    
     Por ejemplo, si SQL Server Reporting Services se instaló en el equipo atl-sql-001.litwareinc.com y los informes de supervisión usan el archivo de instancia de base de datos, la dirección URL de la página principal tendría este aspecto:
    
     **http://atl-sql-001.litwareinc.com/Reports_archinst**
    
2. Una vez que haya accedido a la página principal de Reporting Services, haga clic en **ServerReports** y, a **continuación, haga** clic en Reports_Content . Esto le llevará a la página **de Reports_Content** para los informes de supervisión de Skype Empresarial Server.
    
3. En la **Reports_Content** de datos, haga clic en el **origen de datos CDRDB.**
    
4. En la **página CDRDB,** en la pestaña **Propiedades,** busque el cuadro de texto con la etiqueta **Cadena de conexión**. La cadena de conexión actual tendrá un aspecto similar al siguiente:
    
    Data source=(local)\archinst;initial catalog=LcsCDR
    
5. Edite la cadena de conexión para incluir el nombre del servidor y la instancia de la base de datos reflejada. Por ejemplo, si el servidor se denomina atl-mirror-001 y la base de datos reflejada está en la instancia archinst, deberá agregarla para especificar la base de datos reflejada con esta sintaxis:
    
    Failover Partner=atl-mirror-001\archinst
    
    La cadena de conexión editada tendrá este aspecto:
    
    Data source=(local)\archinst; Failover Partner=atl-mirror-001\archinst;initial catalog=LcsCDR
    
6. Después de actualizar la cadena de conexión, haga clic **en Aplicar**.
    
7. En la **página CDRDB,** haga clic en **Reports_Content** vínculo. Haga clic **en el origen de datos QMSDB** y, a continuación, edite la cadena de conexión de la base de datos QoE. Por ejemplo:
    
    Data source=(local)\archinst; Failover Partner=atl-mirror-001\archinst;initial catalog=QoEMetrics
    
8. Haga clic en **Aplicar**.
    
## <a name="see-also"></a>Ver también

[Instalar informes de supervisión en Skype Empresarial Server](install-monitoring-reports.md)
  
[Uso de informes de supervisión en Skype Empresarial Server](../../manage/health-and-monitoring/monitoring-reports.md)
