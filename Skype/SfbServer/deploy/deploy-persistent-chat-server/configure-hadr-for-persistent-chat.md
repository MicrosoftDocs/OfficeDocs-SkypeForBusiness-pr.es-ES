---
title: Configurar la alta disponibilidad y la recuperación ante desastres para el servidor de chat persistente en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5fb5b189-56c1-49cf-92c8-e4fd6e2fdd5c
description: 'Resumen: Lea este tema para obtener información sobre cómo configurar la alta disponibilidad y la recuperación ante desastres para el servidor de chat persistente en Skype empresarial Server 2015.'
ms.openlocfilehash: e9e313cf83fd784e94efe98fe7a49bbbb800f83f
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239841"
---
# <a name="configure-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Configurar la alta disponibilidad y la recuperación ante desastres para el servidor de chat persistente en Skype Empresarial Server 2015
 
**Resumen:** Lea este tema para obtener información sobre cómo configurar la alta disponibilidad y la recuperación ante desastres para el servidor de chat persistente en Skype empresarial Server 2015.
  
Skype empresarial Server admite varios modos de alta disponibilidad para los servidores back-end, incluyendo la creación de reflejos de bases de datos. Para más información, vea [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  
> [!NOTE]
> Los grupos de disponibilidad AlwaysOn no son compatibles con los servidores de chat persistentes. 

> [!NOTE] 
> Chat persistente está disponible en Skype empresarial Server 2015, pero ya no es compatible con Skype empresarial Server 2019. La misma funcionalidad está disponible en Teams. Para obtener más información, consulte [Introducción a la actualización de Microsoft Teams](/microsoftteams/upgrade-start-here). Si necesita usar una conversación persistente, puede elegir entre migrar los usuarios que tienen esta funcionalidad a teams o continuar usando Skype empresarial Server 2015.
  
Antes de configurar la implementación de chat persistente para una alta disponibilidad y recuperación ante desastres, asegúrese de que está familiarizado con los conceptos de [plan de alta disponibilidad y recuperación ante desastres para el servidor de chat persistente en Skype empresarial server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md). La solución de recuperación ante desastres para el servidor de chat persistente que se describe en estos temas se ha creado en un grupo de servidores de chat persistente ampliado. En el contenido de planeación se describen los requisitos de recursos y la topología de grupo expandida que permite una alta disponibilidad y recuperación ante desastres para el servidor de chat persistente, incluyendo el reflejo de SQL Server para una mayor disponibilidad y el trasvase de registros de SQL Server para recuperación ante desastres.
  
## <a name="use-topology-builder-to-configure-high-availability-and-disaster-recovery"></a>Usar el Generador de topologías para configurar la alta disponibilidad y la recuperación ante desastres

En el Generador de topologías, haga lo siguiente para configurar la alta disponibilidad y la recuperación ante desastres del servidor de chat persistente.
  
1. Agregue las bases de datos reflejadas y de trasvase de registros que SQL Server almacena.
    
2. Edite las propiedades del servicio del servidor de chat persistentes en:
    
    a. Habilite la creación de reflejo para la base de datos principal.
    
    b. Agregue el almacén de SQL Server de reflejo principal.
    
    c. Habilite la base de datos de trasvase de registros de SQL Server.
    
    d. Agregue el almacén de SQL Server secundario de trasvase de registros de SQL Server.
    
    &. Agregue el reflejo de la tienda SQL Server para la base de datos secundaria.
    
    f. Publique la topología.
    
## <a name="set-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database"></a>Configurar el trasvase de registros de SQL Server para la base de datos principal del servidor de chat persistente

Con SQL Server Management Studio, conéctese a la instancia de base de datos de trasvase de registros secundaria del servidor de chat persistente y asegúrese de que el Agente SQL Server se esté ejecutando. A continuación, conéctese a la instancia principal de la base de datos de chat persistente y realice los siguientes pasos:
  
1. Haga clic con el botón secundario en la base de datos mgc y, luego, haga clic en **Propiedades**.
    
2. En **Seleccionar una página**, haga clic en **Trasvase de registros de transacciones**.
    
3. Seleccione la casilla **Habilitar esta como base de datos principal en una configuración de trasvase de registros**.
    
4. En **Copias de seguridad de registros de transacciones**, haga clic en **Configuración de la copia de seguridad**.
    
5. En el cuadro **Ruta de acceso de red a la carpeta de copia de seguridad**, escriba la ruta de acceso de red al recurso compartido que creó para la carpeta de copia de seguridad del registro de las transacciones.
    
6. Si la carpeta de copia de seguridad está ubicada en el servidor principal, escriba la ruta de acceso local a dicha carpeta en el cuadro **Si la carpeta de copia de seguridad está ubicada en el servidor principal, escriba una ruta de acceso local a la carpeta (por ejemplo: c:\backup)**. (Si la carpeta de copia de seguridad no está ubicada en el servidor principal, puede dejar vacío este cuadro).
    
    > [!IMPORTANT]
    > Si la cuenta de servicio de SQL Server del servidor principal se ejecuta en la cuenta del sistema local, debe crear la carpeta de copia de seguridad en el servidor principal y especificar una ruta de acceso local a esa carpeta. 
  
7. Configure los parámetros **Eliminar archivos con más de** y **Mostrar una alerta si no se produce una copia de seguridad tras**.
    
8. Consulte la programación de copia de seguridad incluida en el cuadro **Programación** en **Trabajo de copia de seguridad**. Para personalizar la programación de la instalación, haga clic en **programación**y ajuste la programación del Agente SQL Server según sea necesario.
    
9. En **Compresión**, seleccione **Usar la configuración de servidor predeterminada** y, luego, haga clic en **Aceptar**.
    
10. En **Instancias de servidores secundarios y bases de datos**, haga clic en **Agregar**.
    
11. Haga clic en **conectar** y conéctese a la instancia de SQL Server que haya configurado como servidor secundario.
    
12. En el cuadro **Base de datos secundaria**, seleccione la base de datos de **mgc** de la lista.
    
13. En la pestaña **Inicializar base de datos secundaria**, elija la opción **Sí, generar una copia de seguridad completa de la base de datos principal y restaurarla en la base de datos secundaria (y crear la base de datos secundaria si no existe)**.
    
14. En la pestaña **Copiar archivos**, en el cuadro **Carpeta de destino de los archivos copiados**, escriba la ruta de acceso de la carpeta en la que es preciso copiar las copias de seguridad de los registros de transacciones. Esa carpeta suele encontrarse en el servidor secundario.
    
15. Tenga en cuenta la programación de copia enumerada en el cuadro **Programación** en **Trabajo de copia**. Para personalizar la programación de la instalación, haga clic en **programación**y ajuste la programación del Agente SQL Server según sea necesario. Esta programación necesita ser aproximadamente la misma que la programación de copia de seguridad.
    
16. En la pestaña **Restaurar**, en **Estado de la base de datos al restaurar copias de seguridad**, elija la opción **Modo sin recuperación**.
    
17. En **Retrasar la restauración de las copias de seguridad al menos:**, seleccione **0 minutos**.
    
18. Elija un umbral de alerta en **Mostrar una alerta si no se produce una restauración tras**.
    
19. Observe la programación de restauración incluida en el cuadro **Programación** en **Trabajo de restauración**. Para personalizar la programación de la instalación, haga clic en **programación**, ajuste la programación del Agente SQL Server según sea necesario y haga clic en **Aceptar**. Esta programación necesita ser aproximadamente la misma que la programación de copia de seguridad.
    
20. En el cuadro de diálogo **Propiedades de la base de datos**, haga clic en **Aceptar** para empezar el proceso de configuración.
    
## <a name="set-up-sql-server-log-shipping-between-the-primary-mirror-and-the-secondary-database"></a>Configurar el trasvase de registros de SQL Server entre el reflejo principal y la base de datos secundaria

Siga estos pasos para que el trasvase de registros continúe si la base de datos de chat principal persistente se conmuta por error a su base de datos reflejada.
  
1. Failover manual de la base de datos principal de chat persistente en el reflejo. Esto se realiza mediante el shell de administración de Skype empresarial Server y el cmdlet **Invoke-CsDatabaseFailover** .
    
2. Con SQL Server Management Studio, conéctese a la instancia principal de reflejo del servidor de chat persistente.
    
3. Asegúrese de que el Agente SQL Server se esté ejecutando.
    
4. Haga clic con el botón secundario en la base de datos mgc y, luego, haga clic en **Propiedades**.
    
5. En **Seleccionar una página**, haga clic en **Trasvase de registros de transacciones**.
    
6. Seleccione la casilla **Habilitar esta como base de datos principal en una configuración de trasvase de registros**.
    
7. En **Copias de seguridad de registros de transacciones**, haga clic en **Configuración de la copia de seguridad**.
    
8. En el cuadro **Ruta de acceso de red a la carpeta de copia de seguridad**, escriba la ruta de acceso de red al recurso compartido que creó para la carpeta de copia de seguridad del registro de transacciones.
    
9. Si la carpeta de copia de seguridad está ubicada en el servidor principal, escriba la ruta de acceso local a dicha carpeta en el cuadro **Si la carpeta de copia de seguridad está ubicada en el servidor principal, escriba una ruta de acceso local a la carpeta**. (Si la carpeta de copia de seguridad no está ubicada en el servidor principal, puede dejar vacío este cuadro).
    
    > [!IMPORTANT]
    > Si la cuenta de servicio de SQL Server del servidor principal se ejecuta en la cuenta del sistema local, debe crear la carpeta de copia de seguridad en el servidor principal y especificar una ruta de acceso local a esa carpeta. 
  
10. Configure los parámetros **Eliminar archivos con más de** y **Mostrar una alerta si no se produce una copia de seguridad tras**.
    
11. Consulte la programación de copia de seguridad incluida en el cuadro **Programación** en **Trabajo de copia de seguridad**. Para personalizar la programación de la instalación, haga clic en **programación**y ajuste la programación del Agente SQL Server, según sea necesario.
    
    > [!IMPORTANT]
    > Use la misma configuración que usa para la base de datos principal. 
  
12. En **Compresión**, seleccione **Usar la configuración de servidor predeterminada** y, luego, haga clic en **Aceptar**.
    
13. En **Instancias de servidores secundarios y bases de datos**, haga clic en **Agregar**.
    
14. Haga clic en **Conectar**, y conéctese a la instancia de SQL Server que ha configurado como servidor secundario.
    
15. En el cuadro **Base de datos secundaria**, seleccione la base de datos de **mgc** de la lista.
    
16. En la pestaña **Inicializar base de datos secundaria**, seleccione la opción **No, la base de datos secundaria está inicializada**.
    
17. En la pestaña **Copiar archivos**, en **Carpeta de destino de los archivos copiados**, escriba la ruta de acceso de la carpeta en la que es preciso copiar las copias de seguridad de los registros de transacciones y haga clic en **Aceptar**. Esta carpeta suele encontrarse en el servidor secundario.
    
18. Abra la lista desplegable **Incluir configuración** y seleccione **Incluir configuración en una nueva ventana de consulta**.
    
19. En la nueva ventana de consulta, en **Propiedades de la base de datos**, haga clic en **Aceptar** para empezar el proceso de configuración.
    
20. Seleccione y ejecute la primera mitad de la consulta (vea el paso 18) hasta la línea:-- \* \* \* \* \* \* end: script \* \* \* \* \* \*que se ejecutará en Primary:.
    
    > [!IMPORTANT]
    > La ejecución manual de este script es necesaria porque SQL Server Management Studio no admite varias bases de datos principales en una configuración de trasvase de registros de SQL Server. 
  
21. Seleccione **Cancelar** para cerrar el panel de configuración del trasvase de archivos de registros y establecer una configuración de trabajo que implemente correctamente el trasvase de archivos de registros a la base de datos principal y reflejada (en caso de conmutación por error). 
    
22. Failback manual de la base de datos principal de chat persistente al principal. Esto se realiza mediante el shell de administración de Skype empresarial Server y el cmdlet **Invoke-CsDatabaseFailover** .
    

