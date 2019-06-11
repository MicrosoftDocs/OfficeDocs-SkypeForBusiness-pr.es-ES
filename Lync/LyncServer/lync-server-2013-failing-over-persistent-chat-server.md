---
title: 'Lync Server 2013: Conmutación por error del servidor de chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failing over Persistent Chat Server
ms:assetid: 2cd79ffd-fee6-44ce-96cf-b98bf25e2690
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204772(v=OCS.15)
ms:contentKeyID: 48183726
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 021b34cafd91397cc36da1dbc22f91b8665aea96
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835169"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-persistent-chat-server-in-lync-server-2013"></a>Conmutación por error del servidor de chat persistente en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-02-05_

El failover de servidor de chat persistente está diseñado para ser un proceso manual.

El procedimiento de conmutación por error se basa en la hipótesis de que el centro de datos secundario está en funcionamiento y que los servicios del servidor de chat persistente donde se encuentra la base de datos de chat persistente principal no están disponibles, incluidos los siguientes:

  - La base de datos principal del servidor de chat persistente y la de réplica del servidor de chat persistente están desactivadas.

  - El servidor front-end de Lync Server está desactivado.

El procedimiento se basa en dos pasos básicos:

  - Recupere la base de datos principal de chats persistentes (MGC).

  - Establecer la creación de reflejo para la nueva base de datos principal.

La base de datos de cumplimiento de chat persistente (mgccomp) no se conmuta por error. El contenido de esta base de datos es transitorio y se purga cuando el adaptador de cumplimiento procesa los datos. Es responsabilidad suya, como administrador de chat persistente, administrar correctamente la salida del adaptador para evitar la pérdida de datos.

<div>

## <a name="to-fail-over-persistent-chat-server"></a>Para conmutar por error el servidor de chat persistente

1.  Quitar el trasvase de registros de la base de datos del servidor de chat persistente
    
    1.  Con SQL Server Management Studio, conéctese a la instancia de base de datos en la que se encuentra la base de datos de copia de seguridad del servidor de chat.
    
    2.  Abra una ventana de consulta en la base de datos principal.
    
    3.  Utilice el siguiente comando para colocar el trasvase de registros:
        
            exec sp_delete_log_shipping_secondary_database mgc

2.  Copie cualquier archivo de copia de seguridad no copiado desde el recurso compartido de copia de seguridad a la carpeta de destino de copias del servidor de copias de seguridad.

3.  Aplique cualquier copia de seguridad de registro de transacciones no aplicadas en secuencia a la base de datos secundaria. Para obtener más información, consulte "Cómo: aplicar una copia de seguridad del registro de transacciones (Transact http://go.microsoft.com/fwlink/p/?linkid=247428-SQL)" en.

4.  Publique en línea la base de datos mgc de copia de seguridad. Utilizando la ventana de consultas que se abre en el paso 1b, realice lo siguiente:
    
    1.  Finalice todas las conexiones a la base de datos mgc, si existe alguna:
        
        1.  **exec Sp\_who2** para identificar conexiones a la base de datos MGC.
        
        2.  **Kill \<SPID\> ** para finalizar estas conexiones.
    
    2.  Publique en línea la base de datos:
        
        1.  **Restaurar la base de datos mgc con la recuperación**.

5.  En el shell de administración de Lync Server, use el comando **set-CsPersistentChatState-Identity "servicio: ATL-CS-001.litwareinc.com" – PoolState FailedOver** para conmutar por error a la base de datos de copia de seguridad de MGC. No olvide sustituir el nombre de dominio completo del grupo de chat persistente por atl-cs-001.litwareinc.com.
    
    La base de datos de copia de seguridad mgc funciona actualmente como base de datos principal.

6.  En el shell de administración de Lync Server, use el cmdlet **install-CsMirrorDatabase** para establecer un reflejo de disponibilidad para la base de datos de copia de seguridad que ahora sirve como la base de datos principal. Utilice la instancia de la base de datos de copia de seguridad como base de datos principal y la instancia de la base de datos reflejada de copia de seguridad como instancia reflejada. Este no es el mismo reflejo de lo que se configuró inicialmente para la base de datos principal durante la configuración. Para obtener información detallada, consulte la sección "usar los cmdlets del shell de administración de Lync Server" en [implementar el reflejo SQL para back-end servidor de alta disponibilidad en Lync server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md).

7.  Configure los servidores activos del servidor de chat persistente. En el shell de comandos de Lync Server, use el cmdlet **set-CsPersistentChatActiveServer** para establecer la lista de servidores activos.
    
    <div>
    

    > [!IMPORTANT]  
    > Todos los servidores activos tienen que estar en el mismo centro de datos que la nueva base de datos principal o en un centro de datos que tenga una conexión con una latencia baja o un ancho de banda alto con la base de datos.

    
    </div>
    
    En este momento, la conmutación por error de la base de datos principal del servidor de chat persistente en la base de datos de copia de seguridad del servidor de chat persistente se completa correctamente.

</div>

</div>

<span> </span>

</div>

</div>

</div>

