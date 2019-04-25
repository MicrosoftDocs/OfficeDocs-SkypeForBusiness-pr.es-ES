---
title: Administrar la alta disponibilidad y la recuperación ante desastres para el servidor de chat persistente en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4346e70b-ac48-4ab9-853e-3cdd6dcfe678
description: 'Resumen: Obtenga información sobre cómo administrar el servidor de Chat persistente alta disponibilidad y recuperación ante desastres en Skype para Business Server 2015.'
ms.openlocfilehash: b7c898be275a4a3642eae88412a14686b258130f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32232685"
---
# <a name="manage-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Administrar la alta disponibilidad y la recuperación ante desastres para el servidor de chat persistente en Skype Empresarial Server 2015
 
**Resumen:** Obtenga información sobre cómo administrar el servidor de Chat persistente alta disponibilidad y recuperación ante desastres en Skype para Business Server 2015.
  
En este tema se describe cómo conmutar por error y se producirá un error en servidor de Chat persistente. Antes de leer este tema, asegúrese de leer [planeación de alta disponibilidad y recuperación ante desastres para servidor de Chat persistente en Skype para Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md) y [Configure una alta disponibilidad y recuperación ante desastres para servidor de Chat persistente en Skype para 2015 empresariales de servidor](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).

> [!NOTE]
> Chat persistente está disponible en Skype para Business Server 2015, pero ya no se admite en Skype para Business Server 2019. La misma funcionalidad está disponible en los equipos. Para obtener más información, vea [viaje de Skype para la empresa a los equipos de Microsoft](/microsoftteams/journey-skypeforbusiness-teams). Si necesita usar chat en grupo, las opciones son para migrar los usuarios que requieren esta funcionalidad a los equipos, o para continuar usando Skype para Business Server 2015. 
  
## <a name="fail-over-persistent-chat-server"></a>Conmutar por error servidor de Chat persistente

Conmutación por error para el servidor de Chat persistente está diseñada para ser principalmente un proceso manual.
  
El procedimiento de conmutación por error se basa en la suposición de que el centro de datos secundario es copia de seguridad y que se está ejecutando, pero los servicios de servidor de Chat persistente donde se encuentra la base de datos principal de Chat persistente no están completamente disponibles, incluidos los siguientes:
  
- Persistent base de datos principal del servidor de Chat y base de datos de servidor de Chat persistente reflejada están inactivos.
    
- Skype para Business Server Front-End Server está inactivo.
    
El procedimiento se basa en dos pasos básicos:
  
- Recuperar el Chat persistente base de datos principal (mgc).
    
- Establecer la creación de reflejo para la nueva base de datos principal.
    
El Chat persistente base de datos cumplimiento (mgccomp) no se conmuta por error. El contenido de esta base de datos es transitorio y se purga cuando el adaptador de cumplimiento procesa los datos. Es su responsabilidad, como administrador de Chat persistente, para administrar correctamente la salida del adaptador para evitar la pérdida de datos.
  
Para llevar a cabo la conmutación por error del servidor de chat persistente:
  
1. Quitar trasvase de registros de la base de datos Persistent Chat Server copia de seguridad del trasvase de registros.
    
   - Con SQL Server Management Studio, conéctese a la instancia de base de datos donde se encuentra la base de datos de CGM de copia de seguridad del servidor de Chat persistente.
    
   - Abra una ventana de consulta en la base de datos principal.
    
   - Utilice el siguiente comando para colocar el trasvase de registros:
    
   ```
   exec sp_delete_log_shipping_secondary_database mgc
   ```

2. Copie cualquier archivo de copia de seguridad no copiado desde el recurso compartido de copia de seguridad a la carpeta de destino de copias del servidor de copias de seguridad.
    
3. Aplique cualquier copia de seguridad de registro de transacciones no aplicadas en secuencia a la base de datos secundaria. Para obtener información detallada, vea [Cómo: aplicar una copia de seguridad del registro de transacciones (Transact-SQL)](https://go.microsoft.com/fwlink/p/?linkid=247428).
    
4. Publique en línea la base de datos mgc de copia de seguridad. Utilizando la ventana de consultas que se abre en el paso 1b, realice lo siguiente:
    
   - Finalice todas las conexiones a la base de datos mgc, si existe alguna:
    
   - **exec sp_who2** identifica las conexiones a la base de datos mgc.
    
   - **kill \<spid\> ** para finalizar estas conexiones.
    
   - Publique en línea la base de datos:
    
   - **Restaurar la base de datos mgc con la recuperación**.
    
5. En Skype para Shell de administración de servidor empresarial, use el comando **Set-CsPersistentChatState-Identity "service: atl-cs-001.litwareinc.com" - PoolState FailedOver** para conmutar por error a la base de datos de copia de seguridad de CGM. No olvide sustituir el nombre de dominio completo del grupo de chat persistente por atl-cs-001.litwareinc.com.
    
    La base de datos de copia de seguridad mgc funciona actualmente como base de datos principal.
    
6. En Skype para Shell de administración de servidor empresarial, use el cmdlet **Install-CsMirrorDatabase** para establecer un reflejo de alta disponibilidad para la base de datos de copia de seguridad que ahora sirve como la base de datos principal. Utilice la instancia de la base de datos de copia de seguridad como base de datos principal y la instancia de la base de datos reflejada de copia de seguridad como instancia reflejada. Este no es el mismo reflejo de lo que se configuró inicialmente para la base de datos principal durante la configuración.
    
7. Establecer los servidores activos del servidor de Chat persistente. De Skype para Shell de administración de servidor empresarial, use el cmdlet **Set-CsPersistentChatActiveServer** para establecer la lista de servidores de activos.
    
    > [!IMPORTANT]
    > Todos los servidores activos tienen que estar en el mismo centro de datos que la nueva base de datos principal o en un centro de datos que tenga una conexión con una latencia baja o un ancho de banda alto con la base de datos. 
  
    En este momento, la conmutación por error desde la base de datos principal de servidor de Chat persistente a la base de datos de copia de seguridad de servidor de Chat persistente se realiza correctamente.
    
## <a name="fail-back-persistent-chat-server"></a>Producirá un error en servidor de Chat persistente

Este procedimiento describe los pasos necesarios para recuperarse de un error del servidor de Chat persistente y restablecer las operaciones desde el centro de datos principal.
  
Durante errores del servidor de Chat persistente, el centro de datos principal sufre una interrupción completa y la principal y bases de datos reflejadas dejan de estar disponibles. El centro de datos principal se conmuta por error al servidor de copia de seguridad.
  
En el siguiente procedimiento, se restaura el funcionamiento normal después de realizar una copia de seguridad del centro de datos principal y volver a generar los servidores. El procedimiento se supone que se ha recuperado el centro de datos principal de interrupción total, y que la base de datos de CGM y la base de datos mgccomp se han reconstrucción y volver a instalar mediante el generador de topología.
  
También se da por hecho que no se ha implementado ningún servidor reflejado ni de copia de seguridad nuevo durante el período de conmutación por error y, asimismo, que el único servidor implementado es el de copia de seguridad y su servidor reflejado, tal como se especificó anteriormente en Conmutación por error del servidor de chat persistente.
  
Estos pasos están pensados para recuperar la configuración tal y como estaba antes del desastre, lo que resulta en la conmutación por error del servidor principal al servidor de copia de seguridad.
  
1. Borrar todos los servidores de la lista de Persistent Chat Server Active Server mediante el cmdlet **Set-CsPersistentChatActiveServer** desde el Skype para Shell de administración de servidor empresarial. Esto detiene todos los servidores de Chat persistente de conectarse a la base de datos de CGM y la base de datos mgccomp durante la conmutación por recuperación.
    
    > [!IMPORTANT]
    > El agente de SQL Server en el servidor secundario Persistent Chat Server servidor Back-End se debe ejecutar bajo una cuenta con privilegios. En concreto, la cuenta debe incluir: 
  
   - Acceso de lectura al recurso compartido de red en el que están las copias de seguridad
    
   - Acceso de escritura al directorio local específico en el que las copias de seguridad se copian
    
2. Deshabilite la creación de reflejo en la base de datos mgc de copia de seguridad:
    
   - Mediante SQL Server Management Studio, conéctese a la instancia mgc de copia de seguridad.
    
   - Haga clic con el botón secundario en la base de datos mgc, seleccione **Tareas** y, luego, haga clic en **Reflejo**.
    
   - Haga clic en **Quitar creación de reflejo**.
    
   - Haga clic en **Aceptar**.
    
   - Lleve a cabo los mismos pasos con la base de datos mgccomp.
    
3. Realice una copia de seguridad de la base de datos mgc, de modo que se pueda restaurar a la nueva base de datos principal:
    
   - Mediante SQL Server Management Studio, conéctese a la instancia mgc de copia de seguridad.
    
   - Haga clic con el botón secundario en la base de datos mgc, seleccione **Tareas** y, luego, haga clic en **Copia de seguridad**. Aparecerá el cuadro de diálogo de la **Base de datos de copia de seguridad**.
    
   - En **Tipo de copia de seguridad**, seleccione **Completo**.
    
   - Para el **Componente de copia de seguridad**, haga clic en **Base de datos**.
    
   - Puede aceptar el nombre del conjunto de copia de seguridad predeterminado que se sugiere en **Nombre**, o bien especificar otro.
    
   -  * \<Opcional\> *  En **Descripción**, escriba una descripción del conjunto de copia de seguridad.
    
   - Elimine la ubicación de copia de seguridad predeterminada de la lista de destino.
    
   - Agregue un archivo a la lista por medio de la ruta de acceso a la ubicación del recurso compartido que haya definido para el trasvase de registros. Esta ruta se encuentra disponible tanto para la base de datos principal como para la de copia de seguridad.
    
   - Haga clic en **Aceptar** para cerrar el cuadro de diálogo e iniciar el proceso de copia de seguridad.
    
4. Restaure la base de datos principal a partir de la copia de seguridad creada en el paso anterior.
    
   - Mediante SQL Server Management Studio, conéctese a la instancia mgc principal.
    
   - Haga clic con el botón secundario en la base de datos mgc, seleccione **Tareas**, **Restaurar** y, luego, haga clic en **Base de datos**. Aparecerá el cuadro de diálogo **Restaurar base de datos**.
    
   - Seleccione **Desde dispositivo**.
    
   - Haga clic en el botón Examinar, que abre el cuadro de diálogo **Especificar copia de seguridad**. En **Medio para copia de seguridad**, seleccione **Archivo**. Haga clic en **Agregar**, seleccione el archivo de copia de seguridad que creó en el paso 3 y haga clic en **Aceptar**.
    
   - En **Seleccionar los conjuntos de copia de seguridad que se van a restaurar**, seleccione la copia de seguridad.
    
   - Haga clic en **Opciones** en el panel **Seleccionar una página**.
    
   - En **Restaurar opciones**, seleccione **Sobrescribir la base de datos existente**.
    
   - En **Estado de recuperación**, seleccione **Dejar la base de datos lista para su uso**.
    
   - Haga clic en **Aceptar** para iniciar el proceso de restauración.
    
5. Configure el trasvase de registros de SQL Server para la base de datos principal. Siga los procedimientos descritos en [Configure una alta disponibilidad y recuperación ante desastres para servidor de Chat persistente en Skype para Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md) para establecer el trasvase de registros para la base de datos mgc principal.
    
6. Establecer los servidores activos del servidor de Chat persistente. De Skype para Shell de administración de servidor empresarial, use el cmdlet **Set-CsPersistentChatActiveServer** para establecer la lista de servidores de activos.
    
    > [!IMPORTANT]
    > Todos los servidores activos tienen que estar en el mismo centro de datos que la nueva base de datos principal o en un centro de datos que tenga una conexión con una latencia baja o un ancho de banda alto con la base de datos. 
  
Para restaurar el grupo de servidores a su estado normal, ejecute el siguiente comando de Windows PowerShell:
  
```
Set-CsPersistentChatState -Identity "service: lyncpc.dci.discovery.com" -PoolState Normal
```

Para más información, consulte el tema de ayuda para el cmdlet [Set-CsPersistentChatState](https://docs.microsoft.com/powershell/module/skype/set-cspersistentchatstate?view=skype-ps).
  

