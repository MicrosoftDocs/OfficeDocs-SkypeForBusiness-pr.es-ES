---
title: Expansor de configuración general del chat persistente
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.PersistentChatGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 275ee1ae-ca58-4963-bc95-523319f90d96
description: 'Para modificar la configuración General para el servidor de Chat persistente o grupo de servidores de Chat persistente, configure o defina estas propiedades:'
ms.openlocfilehash: 84d6600c6ff99d55233ad40c7238fbb2c0480c98
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2018
---
# <a name="persistent-chat-general-settings-expander"></a>Expansor de configuración general del chat persistente
 
Para modificar la configuración **General** para el servidor de Chat persistente o grupo de servidores de Chat persistente, configure o defina estas propiedades:
  
 **General**
  
- **FQDN**: modifique esta configuración para definir el nombre de dominio completo del servidor de Chat persistente o grupo de servidores de Chat persistente
    
- **Nombre para mostrar del grupo de chat persistente**: defina esta configuración para indicar una configuración comprensible y fácil de usar del servidor o el grupo de servidores. Esta configuración hará sea más fácil para los usuarios asociar un determinado servidor de Chat persistente o grupo de servidores de Chat persistente según el nombre para mostrar en lugar de un más difícil de entender el nombre de dominio completo.
    
- **Puerto de chat persistente**: especifique el puerto que se necesita usar para el chat persistente.
    
Modificar la configuración de **asociaciones** para el servidor de Chat persistente o grupo de servidores de Chat persistente, configure o defina estas propiedades:
  
 **Asociaciones**
  
- **Almacén de SQL Server**: elija el almacén de SQL Server y una instancia con nombre opcional de la lista.
    
    Haga clic en **Nuevo** para definir un nuevo almacén y una instancia de SQL Server opcional.
    
- Active la casilla de verificación **la creación de reflejo de almacén de habilitar SQL Server** si desea habilitar la creación de reflejo para el almacén principal de SQL Server.
    
    Si opta por habilitar la creación de reflejo del almacén de SQL Server, seleccione el almacén y la instancia en la lista **almacén de la creación de reflejos de SQL Server**.
    
    Haga clic en **Nuevo** para definir un nuevo almacén y una instancia de SQL Server opcional.
    
- Seleccione la casilla de verificación **usar SQL Server la creación de reflejos testigo para habilitar la conmutación por error automática** si desea que la conmutación por error automática del almacén de SQL Server principal.
    
    Si opta por habilitar el testigo para habilitar la conmutación por error automática de reflejo de almacén de SQL Server, seleccione el almacén y la instancia de la lista.
    
    Haga clic en **Nuevo** para definir un nuevo almacén de SQL Server y una instancia opcional para el almacén testigo.
    
- Seleccione la casilla de verificación **Usar copia de seguridad de almacenes de SQL Server para habilitar la recuperación ante desastres** si desea habilitar el uso de recuperación ante desastres de SQL Server
    
    Si optó por habilitar la recuperación ante desastres, seleccione un almacén y una instancia de la lista **Realizar copia de seguridad de almacén de SQL Server**.
    
    Haga clic en **Nuevo** para definir un nuevo almacén y una instancia de SQL Server opcional.
    
- Active la casilla de verificación **la creación de reflejo de almacén de habilitar SQL Server** si desea habilitar la creación de reflejo para el almacén de la creación de reflejos de SQL Server de reserva.
    
    Si opta por habilitar el reflejo del almacén de SQL Server copia de seguridad, seleccione el almacén y la instancia de la lista **reflejo del almacén de copia de seguridad de SQL Server**.
    
    Haga clic en **Nuevo** para definir un nuevo almacén y una instancia de SQL Server opcional.
    
- Si desea que la conmutación por error automática del almacén de SQL Server de copia de seguridad, seleccione la casilla de verificación **usar SQL Server testigo para habilitar la conmutación por error automática la creación de reflejo** .
    
    Si opta por habilitar el testigo para habilitar la conmutación por error automática de reflejo de almacén de SQL Server, seleccione el almacén y la instancia de la lista.
    
    Haga clic en **Nuevo** para definir un nuevo almacén de SQL Server y una instancia opcional para el almacén testigo.
    
- Active la casilla **Habilitar cumplimiento** si desea habilitar el uso de una base de datos de cumplimiento.
    
    Si optó por habilitar el cumplimiento, seleccione un almacén y una instancia de la lista **Almacén de SQL Server de cumplimiento**.
    
    Haga clic en **Nuevo** para definir un nuevo almacén y una instancia de SQL Server opcional.
    
- Active la casilla de verificación **la creación de reflejo de almacén de habilitar SQL Server** si desea habilitar la creación de reflejo para el almacén de SQL Server de cumplimiento.
    
    Si opta por habilitar el reflejo de almacén de SQL Server de cumplimiento, seleccione el almacén y la instancia de la lista **reflejo del almacén de SQL Server de cumplimiento**.
    
    Haga clic en **Nuevo** para definir un nuevo almacén y una instancia de SQL Server opcional.
    
- Seleccione la casilla de verificación **usar SQL Server la creación de reflejos testigo para habilitar la conmutación por error automática** si desea que la conmutación por error automática del almacén de SQL Server de cumplimiento.
    
    Si opta por habilitar el testigo para habilitar la conmutación por error automática de reflejo de almacén de SQL Server, seleccione el almacén y la instancia de la lista.
    
    Haga clic en **Nuevo** para definir un nuevo almacén de SQL Server y una instancia opcional para el almacén testigo.
    
- Si optó por habilitar el cumplimiento, seleccione un almacén y una instancia de la lista **Realizar copia de seguridad de almacén de SQL Server de cumplimiento**.
    
    Haga clic en **Nuevo** para definir un nuevo almacén y una instancia de SQL Server opcional.
    
- Active la casilla de verificación **la creación de reflejo de almacén de habilitar SQL Server** si desea habilitar la creación de reflejo para el almacén de SQL Server de cumplimiento.
    
    Si opta por habilitar el reflejo de almacén de SQL Server de cumplimiento, seleccione el almacén y la instancia de la lista **reflejo del almacén de SQL Server de cumplimiento de copia de seguridad**.
    
    Haga clic en **Nuevo** para definir un nuevo almacén y una instancia de SQL Server opcional.
    
- Si desea que la conmutación por error automática del almacén de SQL Server de cumplimiento de copia de seguridad, seleccione la casilla de verificación **usar SQL Server testigo para habilitar la conmutación por error automática la creación de reflejo** .
    
    Si opta por habilitar el testigo para habilitar la conmutación por error automática de reflejo de almacén de SQL Server, seleccione el almacén y la instancia de la lista.
    
    Haga clic en **Nuevo** para definir un nuevo almacén de SQL Server y una instancia opcional para el almacén testigo.
    
- **Almacén de archivo** Seleccione una ubicación de almacén de archivos de la lista, o haga clic en **nuevo** para crear un nuevo almacén de archivos.
    
 **Aceptar** Se aceptan y confirman los cambios en el cuadro de diálogo.
  
 **Cancelar** Se descartan los cambios y se cierra el cuadro de diálogo.
  
 **Ayuda** Abre esta pantalla de ayuda.
  
## <a name="see-also"></a>Vea también

#### 

[Planeación de servidor de Chat persistente en Skype para Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Agregar servidor de Chat persistente a su Skype para topología empresarial Server 2015](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[Configuración de alta disponibilidad y recuperación ante desastres para servidor de Chat persistente en Skype para Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)

