---
title: 'Business Server 2015: Configurar la alta disponibilidad y la recuperación ante desastres para el servidor de chat persistente'
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5fb5b189-56c1-49cf-92c8-e4fd6e2fdd5c
description: Obtenga información sobre cómo configurar la alta disponibilidad y la recuperación ante desastres para el servidor de chat persistente en Skype Empresarial Server 2015.
ms.openlocfilehash: 02eda20ae9db1a623fd17534cce4fb9ef7963b05
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "53772441"
---
# <a name="business-server-2015-configure-high-availability-and-disaster-recovery-for-persistent-chat-server"></a>Business Server 2015: Configurar la alta disponibilidad y la recuperación ante desastres para el servidor de chat persistente
 
**Resumen:** Lea este tema para obtener información sobre cómo configurar la alta disponibilidad y la recuperación ante desastres para el servidor de chat persistente en Skype Empresarial Server 2015.
  
Skype Empresarial Server admite varios modos de alta disponibilidad para los servidores back-end, incluida la creación de reflejo de la base de datos. Para obtener más información, vea [Plan for high availability and disaster recovery in Skype Empresarial Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  
> [!NOTE]
> Los grupos de disponibilidad AlwaysOn no se admiten con servidores de chat persistente. 
  
Antes de configurar la implementación de chat persistente para la alta disponibilidad y la recuperación ante desastres, asegúrese de que está familiarizado con los conceptos de [Plan for high availability and disaster recovery for Persistent Chat Server in Skype Empresarial Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md). La solución de recuperación ante desastres para el servidor de chat persistente que se describe en estos temas se basa en un grupo de servidores de chat persistente extendido. El contenido de planeación describe los requisitos de recursos y la topología de grupo extendido que permite la alta disponibilidad y la recuperación ante desastres para el servidor de chat persistente, incluido el uso de la creación de reflejo de SQL Server para alta disponibilidad y el trasvase de registros SQL Server para la recuperación ante desastres.
  
## <a name="use-topology-builder-to-configure-high-availability-and-disaster-recovery"></a>Usar el Generador de topologías para configurar la alta disponibilidad y la recuperación ante desastres

En el Generador de topologías, siga estos pasos para configurar la alta disponibilidad y la recuperación ante desastres para el servidor de chat persistente.
  
1. Agregue las bases de datos reflejadas y la base de datos secundaria de trasvase SQL Server almacenes.
    
2. Edite las propiedades del servicio del servidor de chat persistente para:
    
    a. Habilite el reflejo para la base de datos principal.
    
    b. Agregue el reflejo principal SQL Server almacén.
    
    c. Habilite la base SQL Server de trasvase de registros.
    
    d. Agregue el SQL Server secundario de trasvase SQL Server registro.
    
    e. Agregue el reflejo SQL Server almacén de la base de datos secundaria.
    
    f. Publique la topología.
    
## <a name="set-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database"></a>Configurar el trasvase SQL Server registro para la base de datos principal del servidor de chat persistente

Con SQL Server Management Studio, conéctese a la instancia de base de datos de trasvase de registros secundaria del servidor de chat persistente y asegúrese de que SQL Server se está ejecutando. A continuación, conéctese a la instancia de base de datos principal de chat persistente y realice los pasos siguientes:
  
1. Haga clic con el botón secundario en la base de datos de CGM y, a continuación, haga clic en **Propiedades**.
    
2. En **Seleccionar una página**, haga clic en **Trasvase de registros de transacciones**.
    
3. Seleccione la casilla **Habilitar esta como base de datos principal en una configuración de trasvase de registros**.
    
4. En **Copias de seguridad de registro de transacciones**, haga clic en **Configuración de copia de seguridad**.
    
5. En el cuadro **Ruta de acceso de red a la carpeta de copia de seguridad**, escriba la ruta de acceso de red al recurso compartido que creó para la carpeta de copia de seguridad de registro de las transacciones.
    
6. Si la carpeta de copia de seguridad está ubicada en el servidor primario, escriba la ruta de acceso local a dicha carpeta en el cuadro **Si la carpeta de copia de seguridad está ubicada en el servidor primario, escriba una ruta local a la carpeta (ejemplo: c:\backup)**. (Si la carpeta de copia de seguridad no está ubicada en el servidor primario, puede dejar vacío este cuadro).
    
    > [!IMPORTANT]
    > Si la SQL Server de servicio del servidor principal se ejecuta en la cuenta del sistema local, debe crear la carpeta de copia de seguridad en el servidor principal y especificar una ruta de acceso local a esa carpeta. 
  
7. Configure los parámetros **Eliminar archivos con más de** y **Mostrar una alerta si no se produce una copia de seguridad tras**.
    
8. Observe la programación de copia de seguridad incluida en el cuadro **Programación** en **Trabajo de copia de seguridad**. Para personalizar la programación de la instalación, haga clic en **Programar** y ajuste la programación SQL Server agente según sea necesario.
    
9. En **Compresión**, seleccione **Usar la configuración de servidor predeterminada** y, a continuación, haga clic en **Aceptar**.
    
10. En **Instancias de servidores secundarios y bases de datos**, haga clic en **Agregar**.
    
11. Haga **Conectar** y conéctese a la instancia de SQL Server que haya configurado como servidor secundario.
    
12. En el cuadro **Base de datos secundaria**, seleccione la base de datos de **CGM** de la lista.
    
13. En la pestaña **Inicializar** base de datos secundaria, elija la opción Sí, genere una copia de seguridad completa de la base de datos principal y restaurela en la base de datos secundaria (y cree la base de datos secundaria si no **existe).**
    
14. En la pestaña **Copiar archivos**, en el cuadro **Carpeta de destino de los archivos copiados**, escriba la ruta de acceso de la carpeta en la que deben copiarse las copias de seguridad de los registros de transacciones. Esa carpeta suele encontrarse en el servidor secundario.
    
15. Tenga en cuenta la programación de copia enumerada en el cuadro **Programación** en **Trabajo de copia**. Para personalizar la programación de la instalación, haga clic en **Programar** y ajuste la programación SQL Server agente según sea necesario. Esta programación debe ser aproximadamente la misma que la programación de copia de seguridad.
    
16. En la pestaña **Restaurar**, en **Estado de la base de datos al restaurar copias de seguridad**, elija la opción **Modo sin recuperación**.
    
17. En **Retrasar la restauración de las copias de seguridad al menos:**, seleccione **0 minutos**.
    
18. Elija un umbral de alerta en **Mostrar una alerta si no se produce una restauración tras**.
    
19. Observe la programación de copia de seguridad incluido en el cuadro **Programación** en **Trabajo de restauración**. Para personalizar la programación de la instalación, haga clic en **Programar**, ajuste la programación SQL Server agente según sea necesario y haga clic en **Aceptar**. Esta programación debe ser aproximadamente la misma que la programación de copia de seguridad.
    
20. En el cuadro de diálogo **Propiedades de base de datos**, haga clic en **Aceptar** para empezar el proceso de configuración.
    
## <a name="set-up-sql-server-log-shipping-between-the-primary-mirror-and-the-secondary-database"></a>Configurar el SQL Server de registros entre el reflejo principal y la base de datos secundaria

Realice los siguientes pasos para que el trasvase de registros continúe si la base de datos de chat persistente principal se ha con error en su base de datos reflejada.
  
1. Conmutar manualmente la conmutación por error de la base de datos de chat persistente principal al reflejo. Para ello, use el Shell Skype Empresarial Server administración y el cmdlet **Invoke-CsDatabaseFailover.**
    
2. Con el SQL Server Management Studio, conéctese a la instancia reflejada del servidor de chat persistente principal.
    
3. Asegúrese de que el agente SQL Server está ejecutándose.
    
4. Haga clic con el botón secundario en la base de datos de CGM y, a continuación, haga clic en **Propiedades**.
    
5. En **Seleccionar una página**, haga clic en **Trasvase de registros de transacciones**.
    
6. Seleccione la casilla **Habilitar esta como base de datos principal en una configuración de trasvase de registros**.
    
7. En **Copias de seguridad de registro de transacciones**, haga clic en **Configuración de copia de seguridad**.
    
8. En el cuadro **Ruta de acceso de red a la carpeta de copia de seguridad**, escriba la ruta de acceso de red al recurso compartido que creó para la carpeta de copia de seguridad del registro de transacciones.
    
9. Si la carpeta de copia de seguridad está ubicada en el servidor principal, escriba la ruta de acceso local a dicha carpeta en el cuadro  **Si la carpeta de copia de seguridad está ubicada en el servidor principal, escriba una ruta local a la carpeta (ejemplo: c:\backup)**. (Si la carpeta de copia de seguridad no está ubicada en el servidor principal, puede dejar vacío este cuadro).
    
    > [!IMPORTANT]
    > Si la SQL Server de servicio del servidor principal se ejecuta en la cuenta del sistema local, debe crear la carpeta de copia de seguridad en el servidor principal y especificar una ruta de acceso local a esa carpeta. 
  
10. Configure los parámetros **Eliminar archivos con más de** y **Mostrar una alerta si no se produce una copia de seguridad tras**.
    
11. Observe la programación de copia de seguridad incluida en el cuadro **Programación** en **Trabajo de copia de seguridad**. Para personalizar la programación de la instalación, haga clic en **Programar** y ajuste la programación SQL Server agente, según sea necesario.
    
    > [!IMPORTANT]
    > Use la misma configuración que usa para la base de datos principal. 
  
12. En **Compresión**, seleccione **Usar la configuración de servidor predeterminada** y, a continuación, haga clic en **Aceptar**.
    
13. En **Instancias de servidores secundarios y bases de datos**, haga clic en **Agregar**.
    
14. Haga clic en **Conectar**, y conéctese a la instancia de SQL Server que ha configurado como servidor secundario.
    
15. En el cuadro **Base de datos secundaria**, seleccione la base de datos de **CGM** de la lista.
    
16. En la pestaña **Inicializar base de datos secundaria**, seleccione la opción **No, la base de datos secundaria está inicializada**.
    
17. En la pestaña **Copiar archivos**, en el cuadro **Carpeta de destino de los archivos copiados**, escriba la ruta de acceso de la carpeta en la que deben copiarse las copias de seguridad de los registros de transacciones y haga clic en **Aceptar**. Esa carpeta suele encontrarse en el servidor secundario.
    
18. Abra la lista desplegable **Incluir configuración** y seleccione **Incluir configuración en una nueva ventana de consulta**.
    
19. En la nueva ventana de consulta, en **Propiedades de base de datos**, haga clic en **Aceptar** para comenzar el proceso de configuración.
    
20. Seleccione y ejecute la primera mitad de la consulta (vea el paso 18) hasta la línea: -- End: Script que se ejecutará \* \* \* \* \* \* en Primary: \* \* \* \* \* \* .
    
    > [!IMPORTANT]
    > La ejecución manual de este script es necesaria porque SQL Server Management Studio no admite varias bases de datos principales en una SQL Server de trasvase de registros. 
  
21. Seleccione **Cancelar** para cerrar el panel de configuración de envío del archivo de registro y establecer una configuración de trabajo que implemente correctamente el envío del archivo de registro a la base de datos principal y reflejada (en caso de conmutación por error).
    
22. Conmutación por recuperación manual de la base de datos de chat persistente principal a la principal. Para ello, use el Shell Skype Empresarial Server administración y el cmdlet **Invoke-CsDatabaseFailover.**
    

