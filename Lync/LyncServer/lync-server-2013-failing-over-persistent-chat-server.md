---
title: 'Lync Server 2013: Conmutación por error del servidor de chat persistente'
TOCTitle: Conmutación por error del servidor de chat persistente
ms:assetid: 2cd79ffd-fee6-44ce-96cf-b98bf25e2690
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204772(v=OCS.15)
ms:contentKeyID: 48274782
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Conmutación por error del servidor de chat persistente en Lync Server 2013

 

_**Última modificación del tema:** 2014-02-05_

La conmutación por error de Servidor de chat persistente está diseñada para ser principalmente un proceso manual.

El procedimiento de conmutación por error se basa en el supuesto de que el centro de datos secundarios se encuentra en funcionamiento, pero los servicios de Servidor de chat persistente en el que está ubicada la base de datos Chat persistente principal están completamente no disponibles, incluidos los siguientes:

  - La base de datos principal Servidor de chat persistente y la base de datos de reflejo Servidor de chat persistente están inactivas.

  - El Lync ServerServidor front-end está inactivo.

El procedimiento se basa en dos pasos básicos:

  - La recuperación de la base de datos Chat persistente principal (mgc).

  - La creación de reflejos para la nueva base de datos principal.

La base de datos de conformidad Chat persistente (mgccomp) no se ha conmutado por error. Los contenidos de esta base de datos son transitorios y se purgan cuando el adaptador de conformidad procesa los datos. Es su responsabilidad, como Administrador de Chat persistente, gestionar correctamente la salida del adaptador para evitar la pérdida de datos.

## Conmutación por error del Servidor de chat persistente

1.  Elimine el trasvase de registros de la base de datos de trasvase de registros de copia de seguridad Servidor de chat persistente.
    
    1.  Mediante Management Studio SQL Server, conéctese a la instancia de la base de datos en la que se encuentra la base de datos mgc de copia de seguridad Servidor de chat persistente.
    
    2.  Abra una ventana de consulta en la base de datos principal.
    
    3.  Utilice el siguiente comando para colocar el trasvase de registros:
        
            exec sp_delete_log_shipping_secondary_database mgc

2.  Copie cualquier archivo de copia de seguridad no copiado desde el recurso compartido de copia de seguridad a la carpeta de destino de copias del servidor de copias de seguridad.

3.  Aplique cualquier copia de seguridad de registro de transacciones no aplicadas en secuencia con la base de datos secundaria. Para obtener información detallada, consulte "Cómo aplicar una copia de seguridad de registro de transacciones (Transact-SQL)" en http://go.microsoft.com/fwlink/?linkid=247428\&clcid=0xC0A

4.  Publique en línea la base de datos mgc de copia de seguridad. Utilizando la ventana de consultas que se abre en el paso 1b, realice lo siguiente:
    
    1.  Finalice todas las conexiones a la base de datos mgc, si existe alguna:
        
        1.  **exec sp\_who2** identifica las conexiones a la base de datos mgc.
        
        2.  **kill \<spid\>** para finalizar estas conexiones.
    
    2.  Publique en línea la base de datos:
        
        1.  **Restaurar la base de datos mgc con recuperación**

5.  En el Shell de administración de Lync Server, use el comando **Set-CsPersistentChatState -Identity "service:atl-cs-001.litwareinc.com" –PoolState FailedOver** para realizar la conmutación por error a la base de datos de copia de seguridad mgc. No olvide sustituir el nombre de dominio completo del grupo de chat persistente por atl-cs-001.litwareinc.com.
    
    La base de datos de copia de seguridad mgc funciona actualmente como base de datos principal.

6.  En el shell de administración Lync Server, utilice el cmdlet **Install-CsMirrorDatabase** para crear un reflejo con alta disponibilidad que funcione actualmente con la base de datos principal. Utilice la instancia de la base de datos de copia de seguridad como base de datos principal y la instancia de la base de datos reflejada de copia de seguridad como instancia reflejada. Este no es el mismo reflejo de lo que se configuró inicialmente para la base de datos principal durante la configuración. Para obtener información detallada, consulte la sección "Uso de cmdlets Shell de administración de Lync Server” en [Implementar un reflejo de SQL para alta disponibilidad de servidores back-end en Lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md).

7.  Defina los servidores activos Servidor de chat persistente. Desde el shell de comandos Lync Server, utilice el cmdlet: **Set-CsPersistentChatActiveServer** para definir la lista de servidores activos.
    
    > [!IMPORTANT]  
    > Todos los servidores activos tienen que estar en el mismo centro de datos que la nueva base de datos principal o en un centro de datos que tenga una conexión con una latencia baja o un ancho de banda alto con la base de datos.
    
    
    A este punto, la conmutación por error desde la base de datos principal Servidor de chat persistente a la base de datos de copia de seguridad del Servidor de chat persistente se completa con éxito.

