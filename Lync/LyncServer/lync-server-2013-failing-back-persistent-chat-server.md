---
title: 'Lync Server 2013: Conmutación por recuperación de servidor de chat persistente'
TOCTitle: Conmutación por recuperación de servidor de chat persistente
ms:assetid: 67b91de4-6ddc-43e6-9812-5e1aa84a7980
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204970(v=OCS.15)
ms:contentKeyID: 48275548
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Conmutación por recuperación de servidor de chat persistente en Lync Server 2013

 

_**Última modificación del tema:** 2014-02-05_

En este procedimiento se trazan los pasos necesarios para recuperarse de un error del Servidor de chat persistente y restablecer las operaciones desde el centro de datos principal.

Durante el error del Servidor de chat persistente, el centro de datos principal sufre una interrupción completa y las bases de datos principal y reflejada dejan de estar disponibles. El centro de datos principal se conmuta por error al servidor de reserva.

En el siguiente procedimiento, se restaura el funcionamiento normal después de realizar una copia de seguridad del centro de datos principal y volver a generar los servidores. Aquí se da por hecho que el centro de datos principal se ha recuperado de la interrupción total y que las bases de datos mgc y mgccomp se han vuelto a generar y a instalar con el Generador de topologías.

También se da por hecho que no se ha implementado ningún servidor reflejado ni de copia de seguridad nuevo durante el período de conmutación por error y, asimismo, que el único servidor implementado es el de copia de seguridad y su servidor reflejado, tal como se define en [Conmutación por error del servidor de chat persistente en Lync Server 2013](lync-server-2013-failing-over-persistent-chat-server.md).

Estos pasos están pensados para recuperar la configuración tal y como estaba antes del desastre, lo que resulta en la conmutación por error del servidor principal al servidor de copia de seguridad.

## Para la conmutación por recuperación del Servidor de chat persistente

1.  Elimine todos los servidores de la lista de servidores activos de Servidor de chat persistente mediante el cmdlet `Set-CsPersistentChatActiveServer` del Shell de administración de Lync Server. Esto impide que los Servidores de chat persistente se conecten a las base de datos mgc y mgccomp durante la conmutación por recuperación.
    
    > [!IMPORTANT]  
	> El Agente SQL Server del servidor back-end secundario de Servidor de chat persistente debe ejecutarse con una cuenta con privilegios, que debe incluir específicamente:
    > <ul>
    > <li><p>Acceso de lectura al recurso compartido de red en el que están las copias de seguridad.</p></li>
    > <li><p>Acceso de escritura al directorio local en el que las copias de seguridad se copien.</p></li>
    > </ul>


2.  Deshabilitación de la creación de reflejos en la base de datos mgc de copia de seguridad:
    
    1.  Mediante SQL Server Management Studio, conéctese a la instancia mgc de copia de seguridad.
    
    2.  Haga clic con el botón derecho en la base de datos mgc, apunte a **Tareas** y, a continuación, haga clic en **Reflejo**.
    
    3.  Haga clic en **Eliminar creación de reflejos**.
    
    4.  Haga clic en **Aceptar**.
    
    5.  Lleve a cabo los mismos pasos con la base de datos mgccomp.

3.  Realice una copia de seguridad de la base de datos mgc de modo que se pueda restaurar a la nueva base de datos principal:
    
    1.  Mediante SQL Server Management Studio, conéctese a la instancia mgc de copia de seguridad.
    
    2.  Haga clic con el botón secundario a la base de datos mgc, apunte a **Tareas** y, a continuación, haga clic en **Copia de seguridad** . Aparecerá el cuadro de diálogo de la **Base de datos de copia de seguridad** .
    
    3.  En **Tipo de copia de seguridad**, seleccione **Completo**.
    
    4.  Para el **componente de copia de seguridad**, haga clic en **Base de datos**.
    
    5.  Puede aceptar el nombre del conjunto de copia de seguridad predeterminado que se sugiere en **Nombre**, o bien especificar otro.
    
    6.  *\<Opcional\>* En **Descripción**, incluya una descripción del conjunto de copia de seguridad.
    
    7.  Elimine la ubicación de copia de seguridad predeterminada de la lista de destino.
    
    8.  Agregue un archivo a la lista por medio de la ruta de acceso a la ubicación del recurso compartido que haya definido para el trasvase de registros. Esta ruta se encuentra disponible tanto para la base de datos principal como para la de copia de seguridad.
    
    9.  Haga clic en **Aceptar** para cerrar el cuadro de diálogo e iniciar el proceso de copia de seguridad.

4.  Restaure la base de datos principal a partir de la copia de seguridad creada en el paso anterior.
    
    1.  Mediante SQL Server Management Studio, conéctese a la instancia mgc principal.
    
    2.  Haga doble clic con el botón secundario en la base de datos mgc, apunte a **Tareas** , apunte a **Restaurar** y, a continuación, haga clic en **Base de datos** . Aparecerá el cuadro de diálogo **Restaurar base de datos** .
    
    3.  Seleccione **Desde dispositivo**.
    
    4.  Haga clic en el botón Examinar, que abre el cuadro de diálogo **Especificar copia de seguridad** . En **Medio para copia de seguridad** , seleccione **Archivo** . Haga clic en **Agregar** , seleccione el archivo de copia de seguridad que creó en el paso 3 y haga clic en **Aceptar** .
    
    5.  Seleccione la copia de seguridad en **Seleccionar los conjuntos de copia de seguridad que se van a restaurar**.
    
    6.  Haga clic en **Opciones** en el panel **Seleccionar una página**.
    
    7.  En **Restaurar opciones**, seleccione **Sobrescribir la base de datos existente**.
    
    8.  En **Estado de recuperación**, seleccione **Dejar la base de datos lista para usar**.
    
    9.  Haga clic en **Aceptar** para iniciar el proceso de restauración.

5.  Configure el trasvase de registros SQL Server de la base de datos principal. Siga los procedimientos en [Configurar servidores de chat persistente para la alta disponibilidad y la recuperación ante desastres en Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) para crear el trasvase de registros de la base de datos mgc principal.

6.  Defina los servidores activos del Servidor de chat persistente. En el Shell de administración de Lync Server, use el cmdlet **Set-CsPersistentChatActiveServer** para definir la lista de servidores activos.
    
    > [!IMPORTANT]  
    > Todos los servidores activos tienen que estar en el mismo centro de datos que la nueva base de datos principal o en un centro de datos que tenga una conexión con una latencia baja o un ancho de banda alto con la base de datos.
    


Para restaurar el grupo de servidores a su estado normal, ejecute el comando Windows PowerShell siguiente:

    Set-CsPersistentChatState -Identity "service: lyncpc.dci.discovery.com" -PoolState Normal

Consulte el tema de ayuda del cmdlet [Set-CsPersistentChatState](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsPersistentChatState) para obtener más información.

