---
title: Asocie los informes de supervisión con una base de datos reflejada en Skype para Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 42b797c6-8db8-4ad7-886e-8ddf8deb06f9
description: 'Resumen: Obtenga información sobre cómo asociar los informes de supervisión con una base de datos reflejada usado por Skype para Business Server.'
ms.openlocfilehash: ea087ad53466abd35f6ff221b8c9b2aec781922f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885898"
---
# <a name="associate-monitoring-reports-with-a-mirror-database-in-skype-for-business-server"></a>Asocie los informes de supervisión con una base de datos reflejada en Skype para Business Server 
 
**Resumen:** Obtenga información sobre cómo asociar los informes de supervisión con una base de datos reflejada usado por Skype para Business Server.
  
## <a name="monitor-reports-with-a-mirror-database"></a>Supervisar los informes con una base de datos reflejada

Si configura una base de datos reflejada para supervisar su base de datos, la reflejada asumirá el puesto de la base de datos principal cuando se produzca una conmutación por error. Sin embargo, si utiliza Skype para informes de supervisión del servidor de negocio y se produce una conmutación por error, es posible que los informes de supervisión no se conectan a la base de datos reflejada. Esto se debe a que, al instalar los informes de supervisión, solo se ha especificado la ubicación de la base de datos principal y no la de la base de datos reflejada.
  
Para que los informes de supervisión pasen automáticamente a la base datos reflejada en caso de conmutación por error, necesita agregar la base de datos reflejada como "socio de conmutación por error" a las dos bases de datos que utilizan informes de supervisión (una base datos para los datos del registro detallado de llamadas y otra para los datos de Calidad de la experiencia). Tenga presente que este paso se ha de realizar después de haber instalado los informes de supervisión. Puede agregar información de socio de conmutación por error manualmente editando los valores de la cadena de conexión que utilizan las dos bases de datos. Para ello, realice el procedimiento siguiente:
  
1. Use Internet Explorer para abrir la página de inicio de **SQL Server Reporting Services**. La dirección URL de la página de inicio de Reporting Services está formada por:
    
   - El prefijo **http:**.
    
   - El nombre de dominio completo (FQDN) del equipo en el que se ha instalado Reporting Services (por ejemplo, **atl-sql-001.litwareinc.com**).
    
   - La cadena de caracteres **/Reports_**.
    
   - El nombre de la instancia de la base de datos en la que están instalados los informes de supervisión (por ejemplo, **archinst**).
    
     Por ejemplo, si se ha instalado SQL Server Reporting Services en el equipo atl-sql-001.litwareinc.com y los informes de supervisión utilizan la instancia de base de datos archinst, la dirección URL de la página de inicio será:
    
     **http://atl-sql-001.litwareinc.com/Reports_archinst**
    
2. Cuando haya obtenido acceso a la página de inicio de Reporting Services, haga clic en **ServerReports** y en **Reports_Content**. Que le llevará a la página **Reports_Content** para la Skype para informes de supervisión del servidor de negocio.
    
3. En la página **Reports_Content**, haga clic en el origen de datos **CDRDB**.
    
4. En la página **CDRDB**, en la ficha **Propiedades**, busque el cuadro de texto titulado **Cadena de conexión**. La cadena de conexión actual será similar a:
    
    Data source=(local)\archinst;initial catalog=LcsCDR
    
5. Modifique la cadena de conexión para incluir el nombre del servidor y la instancia de base de datos de la base de datos reflejada. Por ejemplo, si el servidor se llama atl-mirror-001 y la base de datos reflejada se encuentra en la instancia archinst, tendrá que agregar para especificar la base de datos reflejada esta sintaxis:
    
    Failover Partner=atl-mirror-001\archinst
    
    La cadena de conexión resultante necesitará ser:
    
    Data source=(local)\archinst;Failover Partner=atl-mirror-001\archinst;initial catalog=LcsCDR
    
6. Cuando haya actualizado la cadena de conexión, haga clic en **Aplicar**.
    
7. En la página **CDRDB**, haga clic en el vínculo **Reports_Content**. Haga clic en el origen de datos **QMSDB** y, luego, modifique la cadena de conexión de la base de datos QoE. Por ejemplo:
    
    Data source=(local)\archinst;Failover Partner=atl-mirror-001\archinst;initial catalog=QoEMetrics
    
8. Haga clic en **Aplicar**.
    
## <a name="see-also"></a>Consulte también

[Instalación de informes de supervisión en Skype para Business Server](install-monitoring-reports.md)
  
[Uso de informes de supervisión en Skype para Business Server](../../manage/health-and-monitoring/monitoring-reports.md)
