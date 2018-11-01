---
title: "Envío de registro de SQL Server entre reflejo principal y DB secund. de envío de reg."
TOCTitle: Configuración del envío de registro de SQL Server entre el reflejo principal y la base de datos secundaria de envío de registro
ms:assetid: 4e8e9ce9-4301-47f2-a0c3-669afeb53295
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204887(v=OCS.15)
ms:contentKeyID: 48275192
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuración del envío de registro de SQL Server entre el reflejo principal y la base de datos secundaria de envío de registro en Lync Server 2013

 

_**Última modificación del tema:** 2013-02-21_

Siga estos pasos para que continúe el trasvase de registros si la base de datos principal de Chat persistente se conmuta por error a su base de datos reflejada.

1.  Conmute por error manualmente la base de datos principal de Chat persistente al reflejo. Esto se realiza con la Shell de administración de Lync Server y el cmdlet **Invoke-CsDatabaseFailover**. Para más información, vea "Uso de cmdlets de la Shell de administración de Lync Server” en [Implementar un reflejo de SQL para alta disponibilidad de servidores back-end en Lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md).

2.  Mediante SQL Server Management Studio, conéctese a la instancia de reflejo principal de Servidor de chat persistente.

3.  Asegúrese de que el Agente SQL Server se está ejecutando.

4.  Haga clic con el botón secundario en la base de datos de CGM y, a continuación, haga clic en **Propiedades**.

5.  En **Seleccionar una página**, haga clic en **Trasvase de registros de transacciones**.

6.  Seleccione la casilla **Habilitar esta como base de datos primaria en una configuración de trasvase de registros** check box.

7.  En **Copias de seguridad de registro de transacciones**, haga clic en **Configuración de copia de seguridad**.

8.  En el cuadro **Ruta de acceso de red a la carpeta de copia de seguridad**, escriba la ruta de acceso de red al recurso compartido que creó para la carpeta de copia de seguridad del registro de transacciones.

9.  Si la carpeta de copia de seguridad está ubicada en el servidor primario, escriba la ruta de acceso local a dicha carpeta en el cuadro **Si la carpeta de copia de seguridad está ubicada en el servidor primario, escriba una ruta local a la carpeta (ejemplo: c:\\backup)**. (Si la carpeta de copia de seguridad no está ubicada en el servidor primario, puede dejar vacío este cuadro).
    
    > [!IMPORTANT]  
    > Si la cuenta de servicio de SQL Server del servidor principal se ejecuta debajo de la cuenta del sistema local, debe crear su carpeta de copia de seguridad en el servidor principal y especificar una ruta de acceso local a dicha carpeta.
    


10. Configure los parámetros **Eliminar archivos con más de** y **Mostrar una alerta si no se produce una copia de seguridad tras**.

11. Observe la programación de copia de seguridad incluida en el cuadro **Programación** en **Trabajo de copia de seguridad**. Para personalizar la programación para la instalación, haga clic en **Programación** y ajuste la programación del agente SQL Server según sea necesario.
    
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

20. Seleccione y ejecute la primera mitad de la consulta (vea el paso 18) hasta la línea:--\*\*\*\*\*\* Fin: script que se ejecutará en el principal: \*\*\*\*\*\*.
    
    > [!IMPORTANT]  
    > s necesario ejecutar manualmente este script porque SQL Server Management Studio no admite varias bases de datos principales en una configuración de trasvase de registros de SQL Server.
    


21. Seleccione **Cancelar** para cerrar el panel de configuración de envío del archivo de registro y establecer una configuración de trabajo que implemente correctamente el envío del archivo de registro a la base de datos principal y reflejada (en caso de conmutación por error).

22. Conmute por recuperación manualmente la base de datos de Chat persistente al principal. Esto se realiza con la Shell de administración de Lync Server y el cmdlet **Invoke-CsDatabaseFailover**. Para más información, vea “Uso de cmdlets del Shell de administración de Lync Server” en [Implementar un reflejo de SQL para alta disponibilidad de servidores back-end en Lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md).

## Vea también

#### Conceptos

[Implementar un reflejo de SQL para alta disponibilidad de servidores back-end en Lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)  
[Implementar un reflejo de SQL para alta disponibilidad de servidores back-end en Lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)

