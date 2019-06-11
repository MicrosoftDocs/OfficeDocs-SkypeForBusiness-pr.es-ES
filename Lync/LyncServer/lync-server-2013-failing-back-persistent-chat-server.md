---
title: 'Lync Server 2013: Conmutación por recuperación de servidor de chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failing back Persistent Chat Server
ms:assetid: 67b91de4-6ddc-43e6-9812-5e1aa84a7980
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204970(v=OCS.15)
ms:contentKeyID: 48184396
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1d79c25d153de81906fcaf9355a543d31cb8fe0a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835182"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-back-persistent-chat-server-in-lync-server-2013"></a>Conmutación por recuperación de servidor de chat persistente en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-02-05_

Este procedimiento indica los pasos necesarios para recuperarse de un error del servidor de chat persistente y para restablecer las operaciones desde el centro de datos principal.

Durante un error de servidor de chat persistente, el centro de datos principal sufre una interrupción completa y las bases de datos principal y reflejada dejan de estar disponibles. El centro de datos principal se conmuta por error al servidor de copia de seguridad.

En el siguiente procedimiento, se restaura el funcionamiento normal después de realizar una copia de seguridad del centro de datos principal y volver a generar los servidores. El procedimiento presupone que el centro de datos principal se ha recuperado de la interrupción total y que la base de datos MGC y la base de datos mgccomp se han reconstruido y vuelto a instalar con el generador de topologías.

El procedimiento también presupone que no se han implementado nuevos servidores de reflejo y copia de seguridad durante el período de conmutación por error y que el único servidor implementado es el servidor de copia de seguridad y su servidor reflejado, según se define en [conmutación por error en el servidor de chat persistente en Lync server 2013](lync-server-2013-failing-over-persistent-chat-server.md).

Estos pasos están pensados para recuperar la configuración tal y como estaba antes del desastre, lo que resulta en la conmutación por error del servidor principal al servidor de copia de seguridad.

<div>

## <a name="to-fail-back-persistent-chat-server"></a>Para recuperar el servidor de la conversación persistente

1.  Borre todos los servidores de la lista de servidores activa del servidor de chat `Set-CsPersistentChatActiveServer` persistente mediante el cmdlet del shell de administración de Lync Server. Esto impide que todos los servidores de chat persistentes se conecten a la base de datos MGC y la base de datos mgccomp durante la conmutación por recuperación.
    
    <div>
    

    > [!IMPORTANT]  
    > El Agente SQL Server en el servidor de back-end de la mensajería instantánea secundaria debe estar ejecutándose en una cuenta privilegiada. En concreto, la cuenta debe incluir: 
    > <UL>
    > <LI>
    > <P>Acceso de lectura al recurso compartido de red en el que están las copias de seguridad</P>
    > <LI>
    > <P>Acceso de escritura al directorio local específico en el que las copias de seguridad se copian</P></LI></UL>

    
    </div>

2.  Deshabilite la creación de reflejo en la base de datos mgc de copia de seguridad:
    
    1.  Con SQL Server Management Studio, conéctese a la instancia de la copia de seguridad MGC.
    
    2.  Haga clic con el botón secundario en la base de datos mgc, seleccione **Tareas** y, luego, haga clic en **Reflejo**.
    
    3.  Haga clic en **Quitar creación de reflejo**.
    
    4.  Haga clic en **Aceptar**.
    
    5.  Lleve a cabo los mismos pasos con la base de datos mgccomp.

3.  Realice una copia de seguridad de la base de datos mgc, de modo que se pueda restaurar a la nueva base de datos principal:
    
    1.  Con SQL Server Management Studio, conéctese a la instancia de la copia de seguridad MGC.
    
    2.  Haga clic con el botón secundario en la base de datos mgc, seleccione **Tareas** y, luego, haga clic en **Copia de seguridad**. Aparecerá el cuadro de diálogo de la **Base de datos de copia de seguridad**.
    
    3.  En **Tipo de copia de seguridad**, seleccione **Completo**.
    
    4.  Para el **Componente de copia de seguridad**, haga clic en **Base de datos**.
    
    5.  Puede aceptar el nombre del conjunto de copia de seguridad predeterminado que se sugiere en **Nombre**, o bien especificar otro.
    
    6.  * \<Opcional\> * En **Descripción**, escriba una descripción para el conjunto de copia de seguridad.
    
    7.  Elimine la ubicación de copia de seguridad predeterminada de la lista de destino.
    
    8.  Agregue un archivo a la lista por medio de la ruta de acceso a la ubicación del recurso compartido que haya definido para el trasvase de registros. Esta ruta se encuentra disponible tanto para la base de datos principal como para la de copia de seguridad.
    
    9.  Haga clic en **Aceptar** para cerrar el cuadro de diálogo e iniciar el proceso de copia de seguridad.

4.  Restaure la base de datos principal a partir de la copia de seguridad creada en el paso anterior.
    
    1.  Con SQL Server Management Studio, conéctese a la instancia de MGC principal.
    
    2.  Haga clic con el botón secundario en la base de datos mgc, seleccione **Tareas**, **Restaurar** y, luego, haga clic en **Base de datos**. Aparecerá el cuadro de diálogo **Restaurar base de datos**.
    
    3.  Seleccione **Desde dispositivo**.
    
    4.  Haga clic en el botón Examinar, que abre el cuadro de diálogo **Especificar copia de seguridad**. En **Medio para copia de seguridad**, seleccione **Archivo**. Haga clic en **Agregar**, seleccione el archivo de copia de seguridad que creó en el paso 3 y haga clic en **Aceptar**.
    
    5.  En **Seleccionar los conjuntos de copia de seguridad que se van a restaurar**, seleccione la copia de seguridad.
    
    6.  Haga clic en **Opciones** en el panel **Seleccionar una página**.
    
    7.  En **Restaurar opciones**, seleccione **Sobrescribir la base de datos existente**.
    
    8.  En **Estado de recuperación**, seleccione **Dejar la base de datos lista para su uso**.
    
    9.  Haga clic en **Aceptar** para iniciar el proceso de restauración.

5.  Configure el trasvase de registros de SQL Server para la base de datos principal. Siga los procedimientos que se describen en [configurar el servidor de chat persistente para una alta disponibilidad y recuperación ante desastres en Lync Server 2013](lync-server-2013-configuring-persistent-chat-server-for-high-availability-and-disaster-recovery.md) para establecer el trasvase de registros para la base de datos principal de MGC.

6.  Configure los servidores activos del servidor de chat persistente. Desde el shell de administración de Lync Server, use el cmdlet **set-CsPersistentChatActiveServer** para establecer la lista de servidores activos.
    
    <div>
    

    > [!IMPORTANT]  
    > Todos los servidores activos tienen que estar en el mismo centro de datos que la nueva base de datos principal o en un centro de datos que tenga una conexión con una latencia baja o un ancho de banda alto con la base de datos.

    
    </div>

Para restaurar el grupo a su estado normal, ejecute el siguiente comando de Windows PowerShell:

    Set-CsPersistentChatState -Identity "service: lyncpc.dci.discovery.com" -PoolState Normal

Consulte el tema de ayuda sobre el cmdlet [set-CsPersistentChatState](https://docs.microsoft.com/powershell/module/skype/Set-CsPersistentChatState) para obtener más información.

</div>

</div>

<span> </span>

</div>

</div>

</div>

