---
title: Instalación de informes de supervisión en Skype para Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6f417569-b100-442c-ad48-fdd794626cf7
description: 'Resumen: Obtenga información sobre cómo instalar un servicio que se va a generar informes de supervisión en Skype para Business Server.'
ms.openlocfilehash: ee500d3440e4211bc42566a7cbdd47ee2cd4cc0e
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30876425"
---
# <a name="install-monitoring-reports-in-skype-for-business-server"></a>Instalación de informes de supervisión en Skype para Business Server
 
**Resumen:** Obtenga información sobre cómo instalar un servicio que se va a generar informes de supervisión en Skype para Business Server.
  
Skype para los informes de supervisión del servidor empresarial proporcionarle una gran cantidad de información acerca de la calidad y la cantidad de las sesiones de comunicación que se producen en la organización. 
  
## <a name="install-monitoring-reports"></a>Instalar los informes de supervisión

Informes de supervisión no se instalan automáticamente al instalar Skype para Business Server; en su lugar, debe instalar los informes de supervisión por separado, y sólo después Skype para Business Server se ha instalado en el equipo.
  
> [!NOTE]
> Recomendamos que instale los informes de supervisión en el equipo en el que está instalada la base de datos de supervisión. De este modo, se simplifica el proceso de asignación de permisos para obtener acceso a los informes, ya que si instala los informes de supervisión en el equipo en que se hospeda el almacén de supervisión, no tendrá que configurar los permisos necesarios para que las bases de datos de un equipo interactúen con los servicios de Reporting Services que se ejecutan en otro equipo. 
  
Skype para los informes de supervisión del servidor empresarial incluir más de 30 informes diseñados para proporcionar información detallada acerca de las conferencias, las sesiones de mensajería instantánea de punto a punto, los registros de un usuario, la aplicación de grupo de respuesta y mucho más. Para la versión 2013, Skype para los informes de supervisión del servidor empresarial incluyen una serie de mejoras:
  
- **Informes nuevos sobre la calidad de voz**. Estos nuevos informes incluyen el [Informe de comparación de calidad de medios en Skype para Business Server](../../manage/health-and-monitoring/comparison.md), que se comparan calidad entre los diferentes tipos de llamadas (por ejemplo, entre llamadas por cable y llamadas inalámbricas); y el [Informe de tiempo de unirse a conferencia en Skype para Business Server](../../manage/health-and-monitoring/join-time-report.md), que proporciona información relativa a la cantidad de tiempo que se requiere para que los usuarios unirse a una conferencia. 
    
- **Informes mejorados para la solución de problemas y el análisis de las sesiones de uso compartido de aplicaciones y de vídeo.** el [Informe de resumen de calidad de medios en Skype para Business Server](../../manage/health-and-monitoring/summary.md) proporciona un método para analizar el vídeo y uso compartido de las llamadas, mientras que el [Informe de rendimiento del servidor en Skype para Business Server](../../manage/health-and-monitoring/server-performance.md) detalla el rendimiento de los servidores de generación de estos de aplicaciones llamadas. El [informe de detalles de la sesión de punto a punto en Skype para Business Server](../../manage/health-and-monitoring/peer-to-peer-session-detail-report.md) y el [Informe de detalles de conferencia en Skype para Business Server](../../manage/health-and-monitoring/detail-report.md)ahora también notifica vídeo y uso compartido de las métricas de aplicaciones.
    
- **Rendimiento mejorado de los informes**. Esto incluye una mayor rapidez del tiempo de respuesta y la recuperación de datos, y una navegación por los informes más sencilla y rápida.
    
En la documentación sobre los informes de supervisión se puede encontrar más información referente a cada informe individual.
  
> [!NOTE]
> Hay otro informe - QoE el subinforme de detalles de llamadas - incluida en Skype para Business Server. Pero, este informe se utiliza principalmente con fines internos y no está pensado para usarse por medio de un acceso directo. 
  
Hay dos formas de instalar Skype para los informes de supervisión del servidor empresarial: puede usar el Skype para el Asistente para la implementación de Business Server o puede usar un script de Windows PowerShell que se incluye con el Skype para los archivos de instalación de Business Server. Independientemente del método que elija, asegúrese de que:
  
- Dispone del derecho para agregar un rol de base de datos a una cuenta de usuario de la base de datos de supervisión.
    
- Tiene el rol de administrador de contenido en SQL Server Reporting Services. Este rol le otorga el derecho para implementar informes en SQL Server Reporting Services.
    
Para instalar los informes de supervisión con el Asistente para la implementación, siga estos pasos:
  
1. Haga clic en **Inicio**, haga clic en **Todos los programas**, haga clic en **Skype para Business Server**y, a continuación, haga clic en **Skype para el Asistente para la implementación de servidor de negocio**.
    
2. En el Asistente para la implementación, haga clic en **Implementar los informes de supervisión** para iniciar el asistente de implementación de los informes de supervisión.
    
3. Una vez en el asistente, en la página **Especificar la base de datos de supervisión**, asegúrese de que el nombre de dominio completo del equipo en que se hospeda su almacén de supervisión aparece en la lista desplegable **Base de datos de supervisión** (si dispone de varios almacenes de supervisión, seleccione el servidor correspondiente en la lista desplegable). Compruebe que en el cuadro **Instancia de SQL Server Reporting Services (SSRS)** aparece la instancia correcta de SQL Server (por ejemplo, **atl-sql-001.litwareinc.com/archinst**) y haga clic en **Siguiente**.
    
4. En la página **Especificar credenciales**, en el cuadro **Nombre de usuario**, escriba el nombre de dominio y el nombre de usuario de la cuenta que se utilizará para obtener acceso a los informes de supervisión (por ejemplo, **litwareinc\kenmyer**). Si no usa este formato (dominio\nombre de usuario), se producirá un error.
    
    Introduzca la contraseña de la cuenta de usuario en el cuadro **Contraseña** y haga clic en **Siguiente**. Tenga en cuenta que no se requieren permisos especiales para esta cuenta. Cuando termine la instalación, se concederán automáticamente los permisos de base de datos e inicio de sesión requeridos para la cuenta.
    
5. En la página **Especificar grupo de solo lectura**, en el cuadro Grupo de usuarios, escriba el nombre del grupo de seguridad al que se concederá acceso de solo lectura a SQL Server Reporting Services. Por ejemplo, para conceder acceso de administradores de solo lectura a los informes, escriba **RTCUniversalReadOnlyAdmins**. Después, haga clic en **Siguiente**.
    
6. En la página **Ejecutar comandos**, haga clic en **Finalizar**.
    
Informes de supervisión también pueden instalarse desde el Skype para Shell de administración de servidor empresarial mediante la ejecución de la secuencia de comandos DeployReports.ps1; Esta secuencia de comandos de Windows PowerShell puede encontrarse en el \<ubicación de instalación\>\Skype para la carpeta de 2015\Deployment\Setup Business Server. Para instalar los informes de supervisión con DeployReports.ps1, escriba un comando similar al siguiente en el símbolo del sistema del Shell de administración:
  
```
C:\Program Files\Skype for Business Server 2015\Deployment\Setup\DeployReports.ps1 -storedUserName "litwareinc\kenmyer" -storedPassword "p@ssw0rd" -readOnlyGroupName "RTCUniversalReadOnlyAdmins" -reportServerSqlInstance "atl-sql-001.litwareinc.com" -monitoringDatabaseId "MonitoringDatabase:atl-sql-001.litwareinc.com"
```

En la tabla siguiente se describen los parámetros utilizados en el comando anterior:
  
|**Nombre del parámetro**|**Requerida.**|**Descripción**|
|:-----|:-----|:-----|
|storedUserName  <br/> |Sí  <br/> |Cuenta de usuario (en el formato dominio\nombredeusuario) utilizada para obtener acceso al almacén de supervisión; por ejemplo:  <br/> ```-storedUserName "litwareinc\kenmyer"```Esta cuenta debe tener los permisos de SQL Server y SQL Server Reporting Services especificado anteriormente o se producirá un error en la secuencia de comandos.  <br/> |
|storedPassword  <br/> |Sí  <br/> |Contraseña para la cuenta de usuario utilizada para obtener acceso al almacén de supervisión.  <br/> |
|readOnlyGroupName  <br/> |No  <br/> |Grupo de seguridad local o de dominio a cuyos miembros se les concederá acceso de solo lectura a los informes de supervisión. Tenga en cuenta que el script producirá errores si el grupo especificado no existe. Si más tarde decide revocar dichos permisos o si desea conceder permisos de acceso a otros usuarios o grupos, lo podrá hacer con el Administrador de informes de SQL Service Reporting Services.  <br/> |
|reportSqlServerInstance  <br/> |No  <br/> |La instancia de SQL Server en que se hospeda el servicio de informes. La instancia se tiene que especificar usando el nombre de dominio completo del servidor de informes; por ejemplo:<br/> ```-reportServerSqlInstance atl-sql-001.litwareinc.com```Si este parámetro no se incluye la secuencia de comandos se supone que se hospedan los servicios de informes por la misma instancia de SQL Server que hospeda la base de datos de supervisión.  <br/> |
|monitoringDatabaseId  <br/> |No  <br/> |Identidad de servicio para la base de datos de supervisión. Ejecute este comando para obtener las identidades de sus bases de datos de supervisión:<br/> ```Get-CsService -MonitoringDatabase```|
   
Después de instalar los informes de supervisión, use el cmdlet New-CsReportingConfiguration para configurar la dirección URL usada para obtener acceso a estos informes. Esta tarea puede llevarse a cabo desde el Skype para Shell de administración de Business Server ejecutando el siguiente comando de Windows PowerShell. Se recomienda, aunque no es obligatorio, usar el protocolo HTTPS en la configuración de la dirección URL de informes:
  
```
New-CsReportingConfiguration -Identity 'service:MonitoringDatabase:atl-sql-001.litwareinc.com' -ReportingURL 'https://atl-sql-001.litwareinc.com:443/Reports_ARCHINST'
```

En el comando anterior, para la propiedad ReportingUrl tendría que definirse la dirección URL del Administrador de informes utilizada por SQL Server 2008 R2 Reporting Services. Para determinar la dirección URL del Administrador de informes, siga los pasos siguientes en el equipo en el que se instaló SQL Server Reporting Services:
  
1. Haga clic en Inicio, Todos los programas, Microsoft SQL Server 2008 R2, Herramientas de configuración, y Administrador de configuración de Reporting Services.
    
2. En el cuadro de diálogo Conexión de configuración de Reporting Services, asegúrese de que el nombre del equipo de Reporting Services aparece en el cuadro Nombre del servidor. Seleccione la instancia de SQL Server en la lista desplegable de instancias del Servidor de informes y haga clic en Conectar.
    
3. En el Administrador de configuración de Reporting Services, haga clic en Dirección URL del Administrador de informes. En el panel Dirección URL del Administrador de informes, tendrían que aparecer una o varias direcciones URL. Puede usar cualquiera de ellas como la dirección URL de informes, aunque, de nuevo, recomendamos que ReportingUrl utilice el protocolo HTTPS.
    
Si ha configurado una base de datos reflejada para la base de datos de supervisión, también tendrá que asociar los informes de supervisión con la base de datos reflejada. Vea el artículo [Asociar los informes de supervisión con una base de datos reflejada en Skype para Business Server](monitoring-reports-with-a-mirror-database.md) para obtener información detallada.
  

