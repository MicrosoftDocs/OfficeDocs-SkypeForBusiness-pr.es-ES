---
title: "Lync Server 2013: Transacciones SQL Server de base de datos servidor chat persistente"
TOCTitle: Configurar registro de transacciones de SQL Server para base de datos principal del servidor de chat persistente
ms:assetid: 088ea1c2-d592-4a11-b3b8-f1e2f8beae93
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204653(v=OCS.15)
ms:contentKeyID: 48274350
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar registro de transacciones de SQL Server para base de datos principal del servidor de chat persistente en Lync Server 2013

 

_**Última modificación del tema:** 2012-11-12_

Mediante SQL Server Management Studio, conéctese a la instancia de base de datos de trasvase de registros secundaria del Servidor de chat persistente y asegúrese de que el Agente SQL Server se está ejecutando.

Mediante SQL Server Management Studio conectado a la instancia de base de datos primaria del Chat persistente, siga estos pasos:

1.  Asegúrese de que el Agente SQL Server se está ejecutando.

2.  Haga clic con el botón secundario en la base de datos de CGM y, a continuación, haga clic en **Propiedades**.

3.  En **Seleccionar una página**, haga clic en **Trasvase de registros de transacciones**.

4.  Seleccione la casilla **Habilitar esta como base de datos primaria en una configuración de trasvase de registros** check box.

5.  En **Copias de seguridad de registro de transacciones**, haga clic en **Configuración de copia de seguridad**.

6.  En el cuadro **Ruta de acceso de red a la carpeta de copia de seguridad**, escriba la ruta de acceso de red al recurso compartido que creó para la carpeta de copia de seguridad de registro de las transacciones.

7.  Si la carpeta de copia de seguridad está ubicada en el servidor primario, escriba la ruta de acceso local a dicha carpeta en el cuadro **Si la carpeta de copia de seguridad está ubicada en el servidor primario, escriba una ruta local a la carpeta (ejemplo: c:\\backup)**. (Si la carpeta de copia de seguridad no está ubicada en el servidor primario, puede dejar vacío este cuadro).
    
    > [!IMPORTANT]  
    > Si la cuenta de servicio de SQL Server del servidor principal se ejecuta debajo de la cuenta del sistema local, debe crear su carpeta de copia de seguridad en el servidor principal y especificar una ruta de acceso local a dicha carpeta.
    


8.  Configure los parámetros **Eliminar archivos con más de** y **Mostrar una alerta si no se produce una copia de seguridad tras**.

9.  Mire la programación de copia de seguridad incluida en el cuadro **Programación** en **Trabajo de copia de seguridad**. Para personalizar la programación para la instalación, haga clic en **Programación** y ajuste la programación del Agente SQL Server según sea necesario.

10. En **Compresión**, seleccione **Usar la configuración de servidor predeterminada** y, a continuación, haga clic en **Aceptar**.

11. En **Instancias de servidores secundarios y bases de datos**, haga clic en **Agregar**.

12. Haga clic en **Conectar** y conéctese a la instancia de SQL Server que ha configurado como servidor secundario.

13. En el cuadro **Base de datos secundaria**, seleccione la base de datos de **CGM** de la lista.

14. En la pestaña **Inicializar base de datos secundaria**, elija la opción **Sí, generar una copia de seguridad completa de la base de datos principal y restaurarla en la base de datos secundaria (y crear la base de datos secundaria si no existe)**.

15. En la pestaña **Copiar archivos**, en el cuadro **Carpeta de destino de los archivos copiados**, escriba la ruta de acceso de la carpeta en la que deben copiarse las copias de seguridad de los registros de transacciones. Esa carpeta suele encontrarse en el servidor secundario.

16. Tenga en cuenta la programación de copia enumerada en el cuadro **Programación** en **Trabajo de copia**. Para personalizar la programación para la instalación, haga clic en **Programación** y ajuste la programación del Agente SQL Server según sea necesario. Esta programación debe ser aproximadamente la misma que la programación de copia de seguridad.

17. En la pestaña **Restaurar**, en **Estado de la base de datos al restaurar copias de seguridad**, elija la opción **Modo sin recuperación**.

18. En **Retrasar la restauración de las copias de seguridad al menos:**, seleccione **0 minutos**.

19. Elija un umbral de alerta en **Mostrar una alerta si no se produce una restauración tras**.

20. Observe la programación de copia de seguridad incluido en el cuadro **Programación** en **Trabajo de restauración**. Para personalizar la programación para la instalación, haga clic en **Programación**, ajuste la programación del Agente SQL Server según sea necesario y haga clic en **Aceptar**. Esta programación debe ser aproximadamente la misma que la programación de copia de seguridad.

21. En el cuadro de diálogo **Propiedades de base de datos**, haga clic en **Aceptar** para empezar el proceso de configuración.

