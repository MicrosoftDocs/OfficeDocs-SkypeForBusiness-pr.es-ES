---
title: Configurar la alta disponibilidad y la recuperación ante desastres para el servidor de chat persistente en Skype Empresarial Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5fb5b189-56c1-49cf-92c8-e4fd6e2fdd5c
description: 'Resumen: Leer este tema para aprender a configurar alta disponibilidad y recuperación ante desastres para servidor de Chat persistente en Skype para Business Server 2015.'
ms.openlocfilehash: f0bf1a98bb8967a7310844d9aa85d17d4ef4d167
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="configure-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Configurar la alta disponibilidad y la recuperación ante desastres para el servidor de chat persistente en Skype Empresarial Server 2015
 
**Resumen:** Lea este tema para aprender a configurar alta disponibilidad y recuperación ante desastres para servidor de Chat persistente en Skype para Business Server 2015.
  
Skype para Business Server admite varios modos de alta disponibilidad para su nuevo servidores de fondo, incluidos el espejado de la base de datos. Para obtener más información, vea [Planear la alta disponibilidad y recuperación ante desastres en Skype para Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  
> [!NOTE]
> No se admiten grupos de disponibilidad AlwaysOn con servidores de charla persistente. 
  
Antes de configurar su implementación de Chat persistentes para alta disponibilidad y recuperación ante desastres, asegúrese de que está familiarizado con los conceptos de [Plan para alta disponibilidad y recuperación ante desastres para el servidor de charla persistente en Skype para Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md). La solución de recuperación ante desastres para servidor de Chat persistentes se describen en estos temas se basa en un grupo de servidores de charla persistente extendido. El contenido de planificación describe requisitos de recursos y la topología de grupo extendida que permite persistente Chat Server, incluyendo el uso de reflejos de SQL Server para alta disponibilidad y SQL Server trasvase de registros para alta disponibilidad y recuperación ante desastres recuperación ante desastres.
  
## <a name="use-topology-builder-to-configure-high-availability-and-disaster-recovery"></a>Usar el Generador de topologías para configurar la alta disponibilidad y la recuperación ante desastres

En el Generador de topologías, haga lo siguiente para configurar la alta disponibilidad y la recuperación ante desastres del servidor de chat persistente.
  
1. Agregar el registro envío secundario la base de datos de SQL Server almacena y de las bases de datos de reflejo.
    
2. Editar las propiedades del servicio servidor de Chat persistente para:
    
    a. Habilite la creación de reflejo para la base de datos principal.
    
    b. Agregar el almacén de SQL Server de espejo primario.
    
    c. Habilitar la base de datos de trasvase de registros de SQL Server.
    
    d. Agregar el almacén de SQL Server de secundario de trasvase de registros de SQL Server.
    
    e. Agregar el reflejo de almacén de SQL Server para la base de datos secundaria.
    
    f. Publique la topología.
    
## <a name="set-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database"></a>Configurar el trasvase de registros de SQL Server para la base de datos principal del servidor de chat persistente

Con SQL Server Management Studio, conectarse a la instancia de trasvase de registros secundaria de base de datos de servidor de charla persistente y asegúrese de que está ejecutando el agente de SQL Server. A continuación, conectarse a la instancia de base de datos principal de Chat persistentes y realice los pasos siguientes:
  
1. Haga clic con el botón secundario en la base de datos mgc y, luego, haga clic en **Propiedades**.
    
2. En **Seleccionar una página**, haga clic en **Trasvase de registros de transacciones**.
    
3. Seleccione la casilla **Habilitar esta como base de datos principal en una configuración de trasvase de registros**.
    
4. En **Copias de seguridad de registros de transacciones**, haga clic en **Configuración de la copia de seguridad**.
    
5. En el cuadro **Ruta de acceso de red a la carpeta de copia de seguridad**, escriba la ruta de acceso de red al recurso compartido que creó para la carpeta de copia de seguridad del registro de las transacciones.
    
6. Si la carpeta de copia de seguridad está ubicada en el servidor principal, escriba la ruta de acceso local a dicha carpeta en el cuadro **Si la carpeta de copia de seguridad está ubicada en el servidor principal, escriba una ruta de acceso local a la carpeta (por ejemplo: c:\backup)**. (Si la carpeta de copia de seguridad no está ubicada en el servidor principal, puede dejar vacío este cuadro).
    
    > [!IMPORTANT]
    > Si la cuenta de servicio de SQL Server en el servidor principal se ejecuta bajo la cuenta sistema local, debe crear la carpeta de copia de seguridad en el servidor principal y especificar una ruta de acceso local a esa carpeta. 
  
7. Configure los parámetros **Eliminar archivos con más de** y **Mostrar una alerta si no se produce una copia de seguridad tras**.
    
8. Consulte la programación de copia de seguridad incluida en el cuadro **Programación** en **Trabajo de copia de seguridad**. Para personalizar la programación de la instalación, haga clic en **programar**y ajustar la programación del agente de SQL Server según sea necesario.
    
9. En **Compresión**, seleccione **Usar la configuración de servidor predeterminada** y, luego, haga clic en **Aceptar**.
    
10. En **Instancias de servidores secundarios y bases de datos**, haga clic en **Agregar**.
    
11. Haga clic en **Conectar** y conectarse a la instancia de SQL Server que se ha configurado como el servidor secundario.
    
12. En el cuadro **Base de datos secundaria**, seleccione la base de datos de **mgc** de la lista.
    
13. En la pestaña **Inicializar base de datos secundaria**, elija la opción **Sí, generar una copia de seguridad completa de la base de datos principal y restaurarla en la base de datos secundaria (y crear la base de datos secundaria si no existe)**.
    
14. En la pestaña **Copiar archivos**, en el cuadro **Carpeta de destino de los archivos copiados**, escriba la ruta de acceso de la carpeta en la que es preciso copiar las copias de seguridad de los registros de transacciones. Esa carpeta suele encontrarse en el servidor secundario.
    
15. Tenga en cuenta la programación de copia enumerada en el cuadro **Programación** en **Trabajo de copia**. Para personalizar la programación de la instalación, haga clic en **programar**y ajustar la programación del agente de SQL Server según sea necesario. Esta programación necesita ser aproximadamente la misma que la programación de copia de seguridad.
    
16. En la pestaña **Restaurar**, en **Estado de la base de datos al restaurar copias de seguridad**, elija la opción **Modo sin recuperación**.
    
17. En **Retrasar la restauración de las copias de seguridad al menos:**, seleccione **0 minutos**.
    
18. Elija un umbral de alerta en **Mostrar una alerta si no se produce una restauración tras**.
    
19. Observe la programación de restauración incluida en el cuadro **Programación** en **Trabajo de restauración**. Para personalizar la programación de la instalación, haga clic en **programar**, ajustar la programación del agente de SQL Server según sea necesario y haga clic en **Aceptar**. Esta programación necesita ser aproximadamente la misma que la programación de copia de seguridad.
    
20. En el cuadro de diálogo **Propiedades de la base de datos**, haga clic en **Aceptar** para empezar el proceso de configuración.
    
## <a name="set-up-sql-server-log-shipping-between-the-primary-mirror-and-the-secondary-database"></a>Configurar el trasvase de registros de SQL Server entre el reflejo principal y la base de datos secundaria

Realice los pasos siguientes para el trasvase de registros para continuar si la base de datos principal de Chat persistentes se conmuta a su base de datos reflejada.
  
1. Conmutar manualmente la base de datos de Chat persistentes principal al reflejo. Esto se hace mediante el Skype para el Shell de administración de servidor empresarial y el cmdlet **Invoke-CsDatabaseFailover** .
    
2. Con la de SQL Server Management Studio, conectarse a la instancia de reflejo de persistente Chat Server principal.
    
3. Asegúrese de que está ejecutando el agente de SQL Server.
    
4. Haga clic con el botón secundario en la base de datos mgc y, luego, haga clic en **Propiedades**.
    
5. En **Seleccionar una página**, haga clic en **Trasvase de registros de transacciones**.
    
6. Seleccione la casilla **Habilitar esta como base de datos principal en una configuración de trasvase de registros**.
    
7. En **Copias de seguridad de registros de transacciones**, haga clic en **Configuración de la copia de seguridad**.
    
8. En el cuadro **Ruta de acceso de red a la carpeta de copia de seguridad**, escriba la ruta de acceso de red al recurso compartido que creó para la carpeta de copia de seguridad del registro de transacciones.
    
9. Si la carpeta de copia de seguridad está ubicada en el servidor principal, escriba la ruta de acceso local a dicha carpeta en el cuadro **Si la carpeta de copia de seguridad está ubicada en el servidor principal, escriba una ruta de acceso local a la carpeta**. (Si la carpeta de copia de seguridad no está ubicada en el servidor principal, puede dejar vacío este cuadro).
    
    > [!IMPORTANT]
    > Si la cuenta de servicio de SQL Server en el servidor principal se ejecuta bajo la cuenta sistema local, debe crear la carpeta de copia de seguridad en el servidor principal y especificar una ruta de acceso local a esa carpeta. 
  
10. Configure los parámetros **Eliminar archivos con más de** y **Mostrar una alerta si no se produce una copia de seguridad tras**.
    
11. Consulte la programación de copia de seguridad incluida en el cuadro **Programación** en **Trabajo de copia de seguridad**. Para personalizar la programación de la instalación, haga clic en **programar**y ajustar la programación del agente de SQL Server, según sea necesario.
    
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
    
20. Seleccionar y ejecutar la primera mitad de la consulta (consulte el paso 18) a la línea:-- \* \* \* \* \* \* fin: secuencia de comandos que se ejecutará en el principal: \* \* \* \* \* \*.
    
    > [!IMPORTANT]
    > Es necesario ejecutar manualmente el script porque SQL Server Management Studio no admite varias bases de datos principales en una configuración de trasvase de registros de SQL Server. 
  
21. Seleccione **Cancelar** para cerrar el panel de configuración del trasvase de archivos de registros y establecer una configuración de trabajo que implemente correctamente el trasvase de archivos de registros a la base de datos principal y reflejada (en caso de conmutación por error). 
    
22. Manualmente conmutar la base de datos de Chat persistentes principal para el principal. Esto se hace utilizando el Skype para el Shell de administración de servidor empresarial y el cmdlet **Invoke-CsDatabaseFailover** .
    

