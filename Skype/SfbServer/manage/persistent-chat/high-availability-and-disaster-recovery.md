---
title: Administrar la alta disponibilidad y la recuperación ante desastres para el servidor de chat persistente en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4346e70b-ac48-4ab9-853e-3cdd6dcfe678
description: 'Resumen: Obtenga información sobre cómo administrar la alta disponibilidad del servidor de chat persistente y la recuperación ante desastres en Skype empresarial Server 2015.'
ms.openlocfilehash: ea81f72dfa65fd350b7c8b8c3aaf61bee6999b34
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817231"
---
# <a name="manage-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Administrar la alta disponibilidad y la recuperación ante desastres para el servidor de chat persistente en Skype Empresarial Server 2015
 
**Resumen:** Obtenga información sobre cómo administrar la alta disponibilidad y la recuperación ante desastres de un servidor de chat persistente en Skype empresarial Server 2015.
  
En este tema se describe cómo se conmuta por error el servidor de chat persistente y conmuta por error. Antes de leer este tema, asegúrese de leer [plan de alta disponibilidad y recuperación ante desastres para el servidor de chat persistente en Skype empresarial server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md) y [configurar la alta disponibilidad y la recuperación ante desastres para el servidor de chat persistente en skype empresarial Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).

> [!NOTE]
> Chat persistente está disponible en Skype empresarial Server 2015, pero ya no es compatible con Skype empresarial Server 2019. La misma funcionalidad está disponible en Teams. Para obtener más información, consulte [Introducción a la actualización de Microsoft Teams](/microsoftteams/upgrade-start-here). Si necesita usar una conversación persistente, puede elegir entre migrar los usuarios que tienen esta funcionalidad a teams o continuar usando Skype empresarial Server 2015. 
  
## <a name="fail-over-persistent-chat-server"></a>Conmutación por error en el servidor de chat persistente

El failover de servidor de chat persistente está diseñado para ser un proceso manual.
  
El procedimiento de conmutación por error se basa en la hipótesis de que el centro de datos secundario está en funcionamiento y que los servicios del servidor de chat persistente donde se encuentra la base de datos de chat persistente principal no están disponibles, incluidos los siguientes:
  
- La base de datos principal del servidor de chat persistente y la de réplica del servidor de chat persistente están desactivadas.
    
- El servidor front-end de Skype empresarial Server está desactivado.
    
El procedimiento se basa en dos pasos básicos:
  
- Recupere la base de datos principal de chats persistentes (MGC).
    
- Establecer la creación de reflejo para la nueva base de datos principal.
    
La base de datos de cumplimiento de chat persistente (mgccomp) no se conmuta por error. El contenido de esta base de datos es transitorio y se purga cuando el adaptador de cumplimiento procesa los datos. Es responsabilidad suya, como administrador de chat persistente, administrar correctamente la salida del adaptador para evitar la pérdida de datos.
  
Para llevar a cabo la conmutación por error del servidor de chat persistente:
  
1. Quitar el trasvase de registros de la base de datos del servidor de chat persistente
    
   - Con SQL Server Management Studio, conéctese a la instancia de base de datos en la que se encuentra la base de datos de copia de seguridad del servidor de chat.
    
   - Abra una ventana de consulta en la base de datos principal.
    
   - Utilice el siguiente comando para colocar el trasvase de registros:
    
   ```SQL
   exec sp_delete_log_shipping_secondary_database mgc
   ```

2. Copie cualquier archivo de copia de seguridad no copiado desde el recurso compartido de copia de seguridad a la carpeta de destino de copias del servidor de copias de seguridad.
    
3. Aplique cualquier copia de seguridad de registro de transacciones no aplicadas en secuencia a la base de datos secundaria. Para obtener más información, vea [Cómo aplicar una copia de seguridad del registro de transacciones (Transact-SQL)](https://go.microsoft.com/fwlink/p/?linkid=247428).
    
4. Publique en línea la base de datos mgc de copia de seguridad. Utilizando la ventana de consultas que se abre en el paso 1b, realice lo siguiente:
    
   - Finalice todas las conexiones a la base de datos mgc, si existe alguna:
    
   - **exec sp_who2** identifica las conexiones a la base de datos mgc.
    
   - **Kill \<SPID\> ** para finalizar estas conexiones.
    
   - Publique en línea la base de datos:
    
   - **Restaurar la base de datos mgc con la recuperación**.
    
5. En el shell de administración de Skype empresarial Server, use el comando **set-CsPersistentChatState-Identity "servicio: ATL-CS-001.litwareinc.com"-PoolState FailedOver** para conmutar por error a la base de datos de copia de seguridad de MGC. No olvide sustituir el nombre de dominio completo del grupo de chat persistente por atl-cs-001.litwareinc.com.
    
    La base de datos de copia de seguridad mgc funciona actualmente como base de datos principal.
    
6. En el shell de administración de Skype empresarial Server, use el cmdlet **install-CsMirrorDatabase** para establecer un reflejo de alta disponibilidad para la base de datos de copia de seguridad que ahora sirve como la base de datos principal. Utilice la instancia de la base de datos de copia de seguridad como base de datos principal y la instancia de la base de datos reflejada de copia de seguridad como instancia reflejada. Este no es el mismo reflejo de lo que se configuró inicialmente para la base de datos principal durante la configuración.
    
7. Configure los servidores activos del servidor de chat persistente. Desde el shell de administración de Skype empresarial Server, use el cmdlet **set-CsPersistentChatActiveServer** para establecer la lista de servidores activos.
    
    > [!IMPORTANT]
    > Todos los servidores activos tienen que estar en el mismo centro de datos que la nueva base de datos principal o en un centro de datos que tenga una conexión con una latencia baja o un ancho de banda alto con la base de datos. 
  
    En este momento, la conmutación por error de la base de datos principal del servidor de chat persistente en la base de datos de copia de seguridad del servidor de chat persistente se completa correctamente.
    
## <a name="fail-back-persistent-chat-server"></a>Conmutación por error en el servidor de chat persistente

Este procedimiento indica los pasos necesarios para recuperarse de un error del servidor de chat persistente y para restablecer las operaciones desde el centro de datos principal.
  
Durante un error de servidor de chat persistente, el centro de datos principal sufre una interrupción completa y las bases de datos principal y reflejada dejan de estar disponibles. El centro de datos principal se conmuta por error al servidor de copia de seguridad.
  
En el siguiente procedimiento, se restaura el funcionamiento normal después de realizar una copia de seguridad del centro de datos principal y volver a generar los servidores. El procedimiento presupone que el centro de datos principal se ha recuperado de la interrupción total y que la base de datos MGC y la base de datos mgccomp se han reconstruido y vuelto a instalar con el generador de topologías.
  
También se da por hecho que no se ha implementado ningún servidor reflejado ni de copia de seguridad nuevo durante el período de conmutación por error y, asimismo, que el único servidor implementado es el de copia de seguridad y su servidor reflejado, tal como se especificó anteriormente en Conmutación por error del servidor de chat persistente.
  
Estos pasos están pensados para recuperar la configuración tal y como estaba antes del desastre, lo que resulta en la conmutación por error del servidor principal al servidor de copia de seguridad.
  
1. Borre todos los servidores de la lista de servidores activa del servidor de chat persistente mediante el cmdlet **set-CsPersistentChatActiveServer** del shell de administración de Skype empresarial Server. Esto impide que todos los servidores de chat persistentes se conecten a la base de datos MGC y la base de datos mgccomp durante la conmutación por recuperación.
    
    > [!IMPORTANT]
    > El Agente SQL Server en el servidor de back-end de la mensajería instantánea secundaria debe estar ejecutándose en una cuenta privilegiada. En concreto, la cuenta debe incluir: 
  
   - Acceso de lectura al recurso compartido de red en el que están las copias de seguridad
    
   - Acceso de escritura al directorio local específico en el que las copias de seguridad se copian
    
2. Deshabilite la creación de reflejo en la base de datos mgc de copia de seguridad:
    
   - Con SQL Server Management Studio, conéctese a la instancia de la copia de seguridad MGC.
    
   - Haga clic con el botón secundario en la base de datos mgc, seleccione **Tareas** y, luego, haga clic en **Reflejo**.
    
   - Haga clic en **Quitar creación de reflejo**.
    
   - Haga clic en **Aceptar**.
    
   - Lleve a cabo los mismos pasos con la base de datos mgccomp.
    
3. Realice una copia de seguridad de la base de datos mgc, de modo que se pueda restaurar a la nueva base de datos principal:
    
   - Con SQL Server Management Studio, conéctese a la instancia de la copia de seguridad MGC.
    
   - Haga clic con el botón secundario en la base de datos mgc, seleccione **Tareas** y, luego, haga clic en **Copia de seguridad**. Aparecerá el cuadro de diálogo de la **Base de datos de copia de seguridad**.
    
   - En **Tipo de copia de seguridad**, seleccione **Completo**.
    
   - Para el **Componente de copia de seguridad**, haga clic en **Base de datos**.
    
   - Puede aceptar el nombre del conjunto de copia de seguridad predeterminado que se sugiere en **Nombre**, o bien especificar otro.
    
   -  * \<Opcional\> *  En **Descripción**, escriba una descripción para el conjunto de copia de seguridad.
    
   - Elimine la ubicación de copia de seguridad predeterminada de la lista de destino.
    
   - Agregue un archivo a la lista por medio de la ruta de acceso a la ubicación del recurso compartido que haya definido para el trasvase de registros. Esta ruta se encuentra disponible tanto para la base de datos principal como para la de copia de seguridad.
    
   - Haga clic en **Aceptar** para cerrar el cuadro de diálogo e iniciar el proceso de copia de seguridad.
    
4. Restaure la base de datos principal a partir de la copia de seguridad creada en el paso anterior.
    
   - Con SQL Server Management Studio, conéctese a la instancia de MGC principal.
    
   - Haga clic con el botón secundario en la base de datos mgc, seleccione **Tareas**, **Restaurar** y, luego, haga clic en **Base de datos**. Aparecerá el cuadro de diálogo **Restaurar base de datos**.
    
   - Seleccione **Desde dispositivo**.
    
   - Haga clic en el botón Examinar, que abre el cuadro de diálogo **Especificar copia de seguridad**. En **Medio para copia de seguridad**, seleccione **Archivo**. Haga clic en **Agregar**, seleccione el archivo de copia de seguridad que creó en el paso 3 y haga clic en **Aceptar**.
    
   - En **Seleccionar los conjuntos de copia de seguridad que se van a restaurar**, seleccione la copia de seguridad.
    
   - Haga clic en **Opciones** en el panel **Seleccionar una página**.
    
   - En **Restaurar opciones**, seleccione **Sobrescribir la base de datos existente**.
    
   - En **Estado de recuperación**, seleccione **Dejar la base de datos lista para su uso**.
    
   - Haga clic en **Aceptar** para iniciar el proceso de restauración.
    
5. Configure el trasvase de registros de SQL Server para la base de datos principal. Siga los procedimientos de [configurar la alta disponibilidad y la recuperación ante desastres para el servidor de chat persistente en Skype empresarial server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md) para establecer el trasvase de registros para la base de datos principal de MGC.
    
6. Configure los servidores activos del servidor de chat persistente. Desde el shell de administración de Skype empresarial Server, use el cmdlet **set-CsPersistentChatActiveServer** para establecer la lista de servidores activos.
    
    > [!IMPORTANT]
    > Todos los servidores activos tienen que estar en el mismo centro de datos que la nueva base de datos principal o en un centro de datos que tenga una conexión con una latencia baja o un ancho de banda alto con la base de datos. 
  
Para restaurar el grupo a su estado normal, ejecute el siguiente comando de Windows PowerShell:
  
```PowerShell
Set-CsPersistentChatState -Identity "service: lyncpc.dci.discovery.com" -PoolState Normal
```

Para más información, consulte el tema de ayuda para el cmdlet [Set-CsPersistentChatState](https://docs.microsoft.com/powershell/module/skype/set-cspersistentchatstate?view=skype-ps).
  

