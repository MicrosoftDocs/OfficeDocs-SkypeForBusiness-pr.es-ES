---
title: Instalar informes de supervisión en Skype Empresarial Server
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
ms.assetid: 6f417569-b100-442c-ad48-fdd794626cf7
description: 'Resumen: obtenga información sobre cómo instalar un servicio que generará informes de supervisión en Skype Empresarial Server.'
ms.openlocfilehash: 10a98bea4af3511c50a0b2b814f8b44911f3742f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802260"
---
# <a name="install-monitoring-reports-in-skype-for-business-server"></a>Instalar informes de supervisión en Skype Empresarial Server
 
**Resumen:** Obtenga información sobre cómo instalar un servicio que generará informes de supervisión en Skype Empresarial Server.
  
Los informes de supervisión de Skype Empresarial Server proporcionan una gran cantidad de información sobre la calidad y la cantidad de las sesiones de comunicación que tienen lugar en su organización. 
  
## <a name="install-monitoring-reports"></a>Instalar los informes de supervisión

Los informes de supervisión no se instalan automáticamente al instalar Skype Empresarial Server; en su lugar, debe instalar los informes de supervisión por separado y solo después de instalar Skype Empresarial Server en el equipo.
  
> [!NOTE]
> Se recomienda que instale los informes de supervisión en el equipo en el que está instalada la base de datos de supervisión. De este modo, se simplifica el proceso de asignación de permisos para obtener acceso a los informes, ya que si instala los informes de supervisión en el equipo en que se hospeda el almacén de supervisión, no tendrá que configurar los permisos necesarios para que las bases de datos de un equipo interactúen con los servicios de Reporting Services que se ejecutan en otro equipo. 
  
Los informes de supervisión de Skype Empresarial Server incluyen más de 30 informes diseñados para proporcionar información detallada sobre conferencias, sesiones de mensajería instantánea punto a punto, registros de usuarios, la aplicación Grupo de respuesta y mucho más. Para la versión 2013, los informes de supervisión de Skype Empresarial Server incluyen una serie de mejoras:
  
- **Informes nuevos sobre la calidad de voz**. Estos nuevos informes incluyen el informe de comparación de calidad de medios en Skype Empresarial [Server,](../../manage/health-and-monitoring/comparison.md)que compara la calidad entre diferentes tipos de llamadas (por ejemplo, entre llamadas cableadas y llamadas inalámbricas); y el informe de hora para unirse a la conferencia en Skype Empresarial [Server,](../../manage/health-and-monitoring/join-time-report.md)que proporciona información sobre la cantidad de tiempo necesario para que los usuarios se unan a una conferencia. 
    
- **Informes mejorados para la solución de problemas y el análisis de las sesiones de uso compartido de aplicaciones y de vídeo.** El informe de resumen de calidad de medios de Skype Empresarial [Server](../../manage/health-and-monitoring/summary.md) ofrece una forma de analizar las llamadas de uso compartido de aplicaciones y vídeo, mientras que el informe de rendimiento del servidor de [Skype Empresarial Server](../../manage/health-and-monitoring/server-performance.md) detalla el rendimiento de los servidores que generan estas llamadas. Las métricas de uso compartido de aplicaciones y vídeo también se notifican ahora mediante el informe de detalles de sesiones punto a punto en Skype Empresarial [Server](../../manage/health-and-monitoring/peer-to-peer-session-detail-report.md) y el informe de detalles de conferencia en [Skype Empresarial Server.](../../manage/health-and-monitoring/detail-report.md)
    
- **Rendimiento mejorado de los informes**. Esto incluye una mayor rapidez del tiempo de respuesta y la recuperación de datos, y una navegación por los informes más sencilla y rápida.
    
En la documentación sobre los informes de supervisión se puede encontrar más información referente a cada informe individual.
  
> [!NOTE]
> Hay otro informe, el Subinforme de detalles de llamadas qoE, incluido en Skype Empresarial Server. Sin embargo, este informe se utiliza principalmente con fines internos y no está pensado para usarse mediante un acceso directo. 
  
Hay dos formas de instalar los informes de supervisión de Skype Empresarial Server: puede usar el Asistente para la implementación de Skype Empresarial Server o puede usar un script Windows PowerShell incluido con los archivos de instalación de Skype Empresarial Server. Independientemente del método que elija, asegúrese de que:
  
- Dispone del derecho para agregar un rol de base de datos a una cuenta de usuario de la base de datos de supervisión.
    
- Tiene el rol de administrador de contenido en SQL Server Reporting Services. Este rol le otorga el derecho para implementar informes en SQL Server Reporting Services.
    
Para instalar los informes de supervisión con el Asistente para la implementación, siga estos pasos:
  
1. Haga **clic en Inicio,** **en Todos** los programas, en Skype Empresarial **Server** y, a continuación, en Asistente para la implementación de Skype **Empresarial Server.**
    
2. En el Asistente para la implementación, haga clic en **Implementar los informes de supervisión** para iniciar el asistente de implementación de los informes de supervisión.
    
3. Una vez en el asistente, en la página **Especificar la base de datos de supervisión**, asegúrese de que el nombre de dominio completo del equipo en que se hospeda su almacén de supervisión aparece en la lista desplegable **Base de datos de supervisión**. (Si dispone de varios almacenes de supervisión, seleccione el servidor correspondiente en la lista desplegable.) Compruebe que en el cuadro **Instancia de SQL Server Reporting Services (SSRS)** aparece la instancia correcta de SQL Server (por ejemplo, **atl-sql-001.litwareinc.com/archinst**) y haga clic en **Siguiente**.
    
4. En la página **Especificar credenciales**, en el cuadro **Nombre de usuario**, escriba el nombre de dominio y el nombre de usuario de la cuenta que se utilizará para obtener acceso a los informes de supervisión (por ejemplo, **litwareinc\kenmyer**). Si no usa este formato (dominio #A0 o nombre de usuario), se producirá un error.
    
    Introduzca la contraseña de la cuenta de usuario en el cuadro **Contraseña** y haga clic en **Siguiente**. Tenga en cuenta que no se requieren derechos especiales para esta cuenta. A la cuenta se le concederán automáticamente los permisos necesarios de inicio de sesión y base de datos cuando se complete la instalación.
    
5. En la página **Especificar grupo de solo lectura**, en el cuadro Grupo de usuarios, escriba el nombre del grupo de seguridad al que se concederá acceso de solo lectura a SQL Server Reporting Services. Por ejemplo, para conceder acceso de administradores de solo lectura a los informes, escriba **RTCUniversalReadOnlyAdmins**. Después, haga clic en **Siguiente**.
    
6. En la página **Ejecutar comandos**, haga clic en **Finalizar**.
    
Los informes de supervisión también se pueden instalar desde el Shell de administración de Skype Empresarial Server ejecutando el script DeployReports.ps1; este Windows PowerShell script puede encontrarse en la carpeta \<install location\> \Skype Empresarial Server 2015\Deployment\Setup. Para instalar los informes de supervisión con el script DeployReports.ps1, escriba un comando como el siguiente en el símbolo del sistema del Shell de administración:
  
```powershell
C:\Program Files\Skype for Business Server 2015\Deployment\Setup\DeployReports.ps1 -storedUserName "litwareinc\kenmyer" -storedPassword "p@ssw0rd" -readOnlyGroupName "RTCUniversalReadOnlyAdmins" -reportServerSqlInstance "atl-sql-001.litwareinc.com" -monitoringDatabaseId "MonitoringDatabase:atl-sql-001.litwareinc.com"
```

En la tabla siguiente se describen los parámetros utilizados en el comando anterior:
  
|**Nombre del parámetro**|**Obligatorio**|**Descripción**|
|:-----|:-----|:-----|
|storedUserName  <br/> |Sí  <br/> |Cuenta de usuario (en el formato dominio\nombredeusuario) utilizada para obtener acceso al almacén de supervisión; por ejemplo:  <br/> ```-storedUserName "litwareinc\kenmyer"``` Esta cuenta debe tener los permisos especificados anteriormente SQL Server y SQL Server Reporting Services o el script producirá un error.  <br/> |
|storedPassword  <br/> |Sí  <br/> |Contraseña para la cuenta de usuario utilizada para obtener acceso al almacén de supervisión.  <br/> |
|readOnlyGroupName  <br/> |No  <br/> |Grupo de seguridad local o de dominio a cuyos miembros se les concederá acceso de solo lectura a los informes de supervisión. Tenga en cuenta que el script fallará si el grupo especificado no existe. Si más tarde decide revocar dichos permisos o si desea conceder permisos de acceso a otros usuarios o grupos, lo podrá hacer con el Administrador de informes de SQL Service Reporting Services.  <br/> |
|reportSqlServerInstance  <br/> |No  <br/> |La instancia de SQL Server en que se hospeda el servicio de informes. La instancia se debe especificar usando el nombre de dominio completo del servidor de informes; por ejemplo:<br/> ```-reportServerSqlInstance atl-sql-001.litwareinc.com``` Si no se incluye este parámetro, el script supondrá que los servicios de informes se hospedan en la misma instancia de SQL Server que hospeda la base de datos de supervisión.  <br/> |
|monitoringDatabaseId  <br/> |No  <br/> |Identidad de servicio para la base de datos de supervisión. Ejecute este comando para obtener las identidades de sus bases de datos de supervisión:<br/> ```Get-CsService -MonitoringDatabase```|
   
Una vez instalados los informes de supervisión, debe usar el cmdlet New-CsReportingConfiguration para configurar la dirección URL usada para tener acceso a estos informes. Esta tarea se puede llevar a cabo desde el Shell de administración de Skype Empresarial Server ejecutando el siguiente comando Windows PowerShell servidor. Tenga en cuenta que se recomienda, aunque no es obligatorio, utilizar el protocolo HTTPS en la configuración de la dirección URL de informes:
  
```powershell
New-CsReportingConfiguration -Identity 'service:MonitoringDatabase:atl-sql-001.litwareinc.com' -ReportingURL 'https://atl-sql-001.litwareinc.com:443/Reports_ARCHINST'
```

En el comando anterior, para la propiedad ReportingUrl debería definirse la dirección URL del Administrador de informes utilizada por SQL Server 2008 R2 Reporting Services. Para determinar la dirección URL del Administrador de informes, siga los pasos siguientes en el equipo en el que se instaló SQL Server Reporting Services:
  
1. Haga clic en Inicio, Todos los programas, Microsoft SQL Server 2008 R2, Herramientas de configuración, y Administrador de configuración de Reporting Services.
    
2. En el cuadro de diálogo Conexión de configuración de Reporting Services, asegúrese de que el nombre del equipo de Reporting Services aparece en el cuadro Nombre del servidor. Seleccione la instancia de SQL Server en la lista desplegable de instancias del Servidor de informes y haga clic en Conectar.
    
3. En el Administrador de configuración de Reporting Services, haga clic en Dirección URL del Administrador de informes. En el panel Dirección URL del Administrador de informes, deberían aparecer una o varias direcciones URL. Puede usar cualquiera de ellas como la dirección URL de informes, aunque, de nuevo, se recomienda que ReportingUrl utilice el protocolo HTTPS.
    
Si ha configurado una base de datos reflejada para la base de datos de supervisión, también debe asociar los informes de supervisión con la base de datos reflejada. Consulte el artículo Asociar informes de supervisión con una base de datos [reflejada en Skype Empresarial Server](monitoring-reports-with-a-mirror-database.md) para obtener más información.
  

