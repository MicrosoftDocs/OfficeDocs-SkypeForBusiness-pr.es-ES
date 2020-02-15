---
title: 'Lync Server 2013: conmutación por error del servidor de chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing over Persistent Chat Server
ms:assetid: 2cd79ffd-fee6-44ce-96cf-b98bf25e2690
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204772(v=OCS.15)
ms:contentKeyID: 48183726
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0d5ac758c1e4c87fd5559da1c2a9cf388dc8834
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043822"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-persistent-chat-server-in-lync-server-2013"></a>Conmutación por error del servidor de chat persistente en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-02-05_

La conmutación por error para el servidor de chat persistente está diseñada para ser principalmente un proceso manual.

El procedimiento de conmutación por error se basa en el supuesto de que el centro de datos secundario está en funcionamiento, pero los servicios del servidor de chat persistente donde se encuentra la base de datos de chat persistente principal no están disponibles, incluidos los siguientes:

  - La base de datos principal del servidor de chat persistente y la reflejada del servidor de chat persistente están inactivas.

  - El servidor front-end de Lync Server está inactivo.

El procedimiento se basa en dos pasos básicos:

  - Recuperar la base de datos de chat persistente principal (MGC).

  - La creación de reflejos para la nueva base de datos principal.

La base de datos de cumplimiento de chat persistente (mgccomp) no se conmuta por error. Los contenidos de esta base de datos son transitorios y se purgan cuando el adaptador de conformidad procesa los datos. Es su responsabilidad, como administrador de chat persistente, administrar correctamente la salida del adaptador para evitar la pérdida de datos.

<div>

## <a name="to-fail-over-persistent-chat-server"></a>Para conmutar por error el servidor de chat persistente

1.  Quite el trasvase de registros de la base de datos de trasvase de registros del servidor de chat persistente.
    
    1.  Mediante SQL Server Management Studio, conéctese a la instancia de base de datos donde se encuentra la base de datos de copia de seguridad del servidor de chat persistente.
    
    2.  Abra una ventana de consulta en la base de datos principal.
    
    3.  Utilice el siguiente comando para colocar el trasvase de registros:
        
            exec sp_delete_log_shipping_secondary_database mgc

2.  Copie cualquier archivo de copia de seguridad no copiado desde el recurso compartido de copia de seguridad a la carpeta de destino de copias del servidor de copias de seguridad.

3.  Aplique cualquier copia de seguridad de registro de transacciones no aplicadas en secuencia con la base de datos secundaria. Para obtener más información, consulte "Cómo: aplicar una copia de seguridad del registro de transacciones (Transact http://go.microsoft.com/fwlink/p/?linkid=247428-SQL)" en.

4.  Publique en línea la base de datos mgc de copia de seguridad. Utilizando la ventana de consultas que se abre en el paso 1b, realice lo siguiente:
    
    1.  Finalice todas las conexiones a la base de datos mgc, si existe alguna:
        
        1.  **exec Sp\_who2** para identificar conexiones a la base de datos MGC.
        
        2.  **Kill \<SPID\> ** para finalizar estas conexiones.
    
    2.  Publique en línea la base de datos:
        
        1.  **restaurar la base de datos MGC con recuperación**.

5.  En el shell de administración de Lync Server, use el comando **set-CsPersistentChatState-Identity "Service: ATL-CS-001.litwareinc.com" – PoolState FailedOver** para conmutar por error a la base de datos de copia de seguridad MGC. Asegúrese de sustituir el nombre de dominio completo del grupo de servidores de chat persistente por atl-cs-001.litwareinc.com.
    
    La base de datos de copia de seguridad mgc funciona actualmente como base de datos principal.

6.  En el shell de administración de Lync Server, use el cmdlet **install-CsMirrorDatabase** para establecer un reflejo de alta disponibilidad para la base de datos de copia de seguridad que ahora sirve como base de datos principal. Utilice la instancia de la base de datos de copia de seguridad como base de datos principal y la instancia de la base de datos reflejada de copia de seguridad como instancia reflejada. Este no es el mismo reflejo de lo que se configuró inicialmente para la base de datos principal durante la configuración. Para obtener más información, consulte la sección "uso de los cmdlets del shell de administración de Lync Server" en [DEPLOYING SQL Mirror for back end Server High Availability in Lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md).

7.  Establezca los servidores activos del servidor de chat persistente. Desde el shell de comandos de Lync Server, use el cmdlet **set-CsPersistentChatActiveServer** para establecer la lista de servidores activos.
    
    <div>
    

    > [!IMPORTANT]  
    > Todos los servidores activos deben estar ubicados dentro del mismo centro de datos como la nueva base de datos principal o en un centro de datos que tenga una latencia baja o un ancho de banda alto.

    
    </div>
    
    En este punto, la conmutación por error de la base de datos principal del servidor de chat persistente en la base de datos de copia de seguridad del servidor de chat persistente se completa correctamente.

</div>

</div>

<span> </span>

</div>

</div>

</div>

