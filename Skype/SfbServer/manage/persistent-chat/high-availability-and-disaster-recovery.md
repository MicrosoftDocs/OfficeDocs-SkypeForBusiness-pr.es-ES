---
title: Administrar la alta disponibilidad y la recuperación ante desastres para el servidor de chat persistente en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4346e70b-ac48-4ab9-853e-3cdd6dcfe678
description: 'Summary: Learn how to manage Persistent Chat Server high availability and disaster recovery in Skype for Business Server 2015.'
ms.openlocfilehash: 4fb3a38fadf2a8a063715e389718859dcc7ddbdd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122414"
---
# <a name="manage-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Administrar la alta disponibilidad y la recuperación ante desastres para el servidor de chat persistente en Skype Empresarial Server 2015
 
**Resumen:** Obtenga información sobre cómo administrar la alta disponibilidad y recuperación ante desastres del servidor de chat persistente en Skype Empresarial Server 2015.
  
En este tema se describe cómo conmutar por error y devolver la conmutación por recuperación del servidor de chat persistente. Antes de leer este tema, asegúrese de leer [Plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md) y [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).

> [!NOTE]
> El chat persistente está disponible en Skype Empresarial Server 2015, pero ya no se admite en Skype Empresarial Server 2019. La misma funcionalidad está disponible en Teams. Para obtener más información, vea [Introducción a la actualización de Microsoft Teams](/microsoftteams/upgrade-start-here). Si necesita usar el chat persistente, las opciones son migrar usuarios que requieren esta funcionalidad a Teams o seguir usando Skype Empresarial Server 2015. 
  
## <a name="fail-over-persistent-chat-server"></a>Conmutación por error del servidor de chat persistente

La conmutación por error para el servidor de chat persistente está diseñada para ser principalmente un proceso manual.
  
El procedimiento de conmutación por error se basa en la suposición de que el centro de datos secundario está en funcionamiento, pero los servicios del servidor de chat persistente donde se encuentra la base de datos de chat persistente principal no están disponibles, incluidos los siguientes:
  
- La base de datos principal del servidor de chat persistente y la base de datos reflejada del servidor de chat persistente están abajo.
    
- El servidor front-end de Skype Empresarial Server no está disponible.
    
El procedimiento se basa en dos pasos básicos:
  
- Recupera la base de datos de chat persistente principal (mgc).
    
- La creación de reflejos para la nueva base de datos principal.
    
La base de datos de cumplimiento de chat persistente (mgccomp) no se ha podido superar. Los contenidos de esta base de datos son transitorios y se purgan cuando el adaptador de conformidad procesa los datos. Es su responsabilidad, como administrador de chat persistente, administrar correctamente la salida del adaptador para evitar la pérdida de datos.
  
Para conmutar por error el servidor de chat persistente:
  
1. Quite el trasvase de registros de la base de datos de trasvase de registros de copia de seguridad del servidor de chat persistente.
    
   - Con SQL Server Management Studio, conéctese a la instancia de base de datos donde se encuentra la base de datos mgc de copia de seguridad del servidor de chat persistente.
    
   - Abra una ventana de consulta en la base de datos principal.
    
   - Utilice el siguiente comando para colocar el trasvase de registros:
    
   ```SQL
   exec sp_delete_log_shipping_secondary_database mgc
   ```

2. Copie cualquier archivo de copia de seguridad no copiado desde el recurso compartido de copia de seguridad a la carpeta de destino de copias del servidor de copias de seguridad.
    
3. Aplique cualquier copia de seguridad de registro de transacciones no aplicadas en secuencia con la base de datos secundaria. Para obtener más información, [vea How to: Apply a Transaction Log Backup (Transact-SQL).](/previous-versions/sql/sql-server-2008-r2/ms187607(v=sql.105))
    
4. Publique en línea la base de datos mgc de copia de seguridad. Utilizando la ventana de consultas que se abre en el paso 1b, realice lo siguiente:
    
   - Finalice todas las conexiones a la base de datos mgc, si existe alguna:
    
   - **exec sp_who2** para identificar las conexiones a la base de datos mgc.
    
   - **kill \<spid\>** para finalizar estas conexiones.
    
   - Publique en línea la base de datos:
    
   - **restaurar la base de datos mgc con recuperación**.
    
5. En el Shell de administración de Skype Empresarial Server, use el comando **Set-CsPersistentChatState -Identity "service:atl-cs-001.litwareinc.com" -PoolState FailedOver** para conmutar por error a la base de datos de copia de seguridad de mgc. Asegúrese de sustituir el nombre de dominio completo del grupo de chat persistente por atl-cs-001.litwareinc.com.
    
    La base de datos de copia de seguridad mgc funciona actualmente como base de datos principal.
    
6. En el Shell de administración de Skype Empresarial Server, use el cmdlet **Install-CsMirrorDatabase** para establecer un reflejo de alta disponibilidad para la base de datos de copia de seguridad que ahora actúa como base de datos principal. Utilice la instancia de la base de datos de copia de seguridad como base de datos principal y la instancia de la base de datos reflejada de copia de seguridad como instancia reflejada. Este no es el mismo reflejo de lo que se configuró inicialmente para la base de datos principal durante la configuración.
    
7. Establezca los servidores activos del servidor de chat persistente. Desde el Shell de administración de Skype Empresarial Server, use el cmdlet **Set-CsPersistentChatActiveServer** para establecer la lista de servidores activos.
    
    > [!IMPORTANT]
    > Todos los servidores activos deben estar ubicados dentro del mismo centro de datos como la nueva base de datos principal o en un centro de datos que tenga una latencia baja o un ancho de banda alto. 
  
    En este momento, la conmutación por error de la base de datos principal del servidor de chat persistente a la base de datos de copia de seguridad del servidor de chat persistente se completa correctamente.
    
## <a name="fail-back-persistent-chat-server"></a>Conmutación por recuperación del servidor de chat persistente

En este procedimiento se describen los pasos necesarios para recuperarse de un error del servidor de chat persistente y restablecer las operaciones desde el centro de datos principal.
  
Durante el error del servidor de chat persistente, el centro de datos principal sufre una interrupción completa y las bases de datos principales y reflejadas no están disponibles. El centro de datos principal se conmuta por error al servidor de reserva.
  
En el siguiente procedimiento, se restaura el funcionamiento normal después de realizar una copia de seguridad del centro de datos principal y volver a generar los servidores. El procedimiento supone que el centro de datos principal se ha recuperado de la interrupción total y que la base de datos mgc y la base de datos mgccomp se han reconstruido y reinstalado mediante el Generador de topologías.
  
El procedimiento también supone que no se implementaron nuevos servidores reflejados y de copia de seguridad durante el período de conmutación por error y que el único servidor implementado es el servidor de copia de seguridad y su servidor reflejado, tal como se definió anteriormente en Conmutación por error sobre el servidor de chat persistente.
  
Estos pasos están pensados para recuperar la configuración tal y como estaba antes del desastre, lo que resulta en la conmutación por error del servidor principal al servidor de copia de seguridad.
  
1. Borre todos los servidores de la lista Servidor de chat persistente Active Server mediante el cmdlet **Set-CsPersistentChatActiveServer** desde el Shell de administración de Skype Empresarial Server. Esto impide que todos los servidores de chat persistente se conecten a la base de datos mgc y a la base de datos mgccomp durante la conmutación por recuperación.
    
    > [!IMPORTANT]
    > El SQL Server en el servidor back-end del servidor de chat persistente secundario debe ejecutarse con una cuenta con privilegios. En concreto, la cuenta debe incluir: 
  
   - Acceso de lectura al recurso compartido de red en el que están las copias de seguridad.
    
   - Acceso de escritura al directorio local en el que las copias de seguridad se copien.
    
2. Deshabilitación de la creación de reflejos en la base de datos mgc de copia de seguridad:
    
   - Con SQL Server Management Studio, conéctese a la instancia mgc de copia de seguridad.
    
   - Haga clic con el botón secundario en la base de datos mgc, apunte a **Tareas** y, a continuación, haga clic en **Reflejo**.
    
   - Haga clic en **Eliminar creación de reflejos**.
    
   - Haga clic en **Aceptar**.
    
   - Lleve a cabo los mismos pasos con la base de datos mgccomp.
    
3. Realice una copia de seguridad de la base de datos mgc de modo que se pueda restaurar a la nueva base de datos principal:
    
   - Con SQL Server Management Studio, conéctese a la instancia mgc de copia de seguridad.
    
   - Haga clic con el botón secundario a la base de datos mgc, apunte a **Tareas** y, a continuación, haga clic en **Copia de seguridad**. Aparecerá el cuadro de diálogo de la **Base de datos de copia de seguridad**.
    
   - En **Tipo de copia de seguridad**, seleccione **Completo**.
    
   - Para el **componente de copia de seguridad**, haga clic en **Base de datos**.
    
   - Puede aceptar el nombre del conjunto de copia de seguridad predeterminado que se sugiere en **Nombre**, o bien especificar otro.
    
   -  *\<Optional\>*  En **Descripción**, escriba una descripción del conjunto de copia de seguridad.
    
   - Elimine la ubicación de copia de seguridad predeterminada de la lista de destino.
    
   - Agregue un archivo a la lista por medio de la ruta de acceso a la ubicación del recurso compartido que haya definido para el trasvase de registros. Esta ruta se encuentra disponible tanto para la base de datos principal como para la de copia de seguridad.
    
   - Haga clic en **Aceptar** para cerrar el cuadro de diálogo e iniciar el proceso de copia de seguridad.
    
4. Restaure la base de datos principal a partir de la copia de seguridad creada en el paso anterior.
    
   - Con SQL Server Management Studio, conéctese a la instancia principal de mgc.
    
   - Haga doble clic con el botón secundario en la base de datos mgc, apunte a **Tareas**, apunte a **Restaurar** y, a continuación, haga clic en **Base de datos**. Aparecerá el cuadro de diálogo **Restaurar base de datos**.
    
   - Seleccione **Desde dispositivo**.
    
   - Haga clic en el botón Examinar, que abre el cuadro de diálogo **Especificar copia de seguridad**. En **Medio para copia de seguridad**, seleccione **Archivo**. Haga clic en **Agregar**, seleccione el archivo de copia de seguridad que creó en el paso 3 y haga clic en **Aceptar**.
    
   - Seleccione la copia de seguridad en **Seleccionar los conjuntos de copia de seguridad que se van a restaurar**.
    
   - Haga clic en **Opciones** en el panel **Seleccionar una página**.
    
   - En **Restaurar opciones**, seleccione **Sobrescribir la base de datos existente**.
    
   - En **Estado de recuperación**, seleccione **Dejar la base de datos lista para usar**.
    
   - Haga clic en **Aceptar** para iniciar el proceso de restauración.
    
5. Configure SQL Server de registro para la base de datos principal. Siga los procedimientos descritos en [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md) para establecer el trasvase de registros para la base de datos mgc principal.
    
6. Establezca los servidores activos del servidor de chat persistente. Desde el Shell de administración de Skype Empresarial Server, use el cmdlet **Set-CsPersistentChatActiveServer** para establecer la lista de servidores activos.
    
    > [!IMPORTANT]
    > Todos los servidores activos deben estar ubicados dentro del mismo centro de datos como la nueva base de datos principal o en un centro de datos que tenga una latencia baja o un ancho de banda alto. 
  
Para restaurar el grupo a su estado normal, ejecute el siguiente Windows PowerShell comando:
  
```PowerShell
Set-CsPersistentChatState -Identity "service: lyncpc.dci.discovery.com" -PoolState Normal
```

Para obtener más información, vea el tema de ayuda para el cmdlet [Set-CsPersistentChatState.](/powershell/module/skype/set-cspersistentchatstate?view=skype-ps)
