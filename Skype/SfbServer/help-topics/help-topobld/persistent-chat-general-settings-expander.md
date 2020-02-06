---
title: Expansor de configuración general del chat persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.PersistentChatGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 275ee1ae-ca58-4963-bc95-523319f90d96
description: 'Para editar la configuración general del servidor de chat persistente o del grupo de servidores de chat persistente, configure o defina estas propiedades:'
ms.openlocfilehash: d44818efa1909e0fd90e4c80fcd88b3d11a616ea
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41819482"
---
# <a name="persistent-chat-general-settings-expander"></a>Expansor de configuración general del chat persistente
 
Para editar la configuración **General** del servidor de chat persistente o del grupo de servidores de chat persistente, configure o defina estas propiedades:
  
 **General**
  
- **FQDN**: Edite esta configuración para definir el nombre de dominio completo del servidor de chat persistente o del grupo de servidores de chat persistente
    
- **Nombre para mostrar del grupo de chat persistente**: defina esta configuración para indicar una configuración comprensible y fácil de usar del servidor o el grupo de servidores. Esta configuración hará que sea más fácil para los usuarios asociar un servidor de chat persistente determinado o un grupo de servidores de chat persistente según el nombre para mostrar en lugar de un nombre de dominio completo más difícil de comprender.
    
- **Puerto de chat persistente**: especifique el puerto que se necesita usar para el chat persistente.
    
Para editar la configuración de las **asociaciones** del servidor de chat persistente o del grupo de servidores de chat persistente, configure o defina estas propiedades:
  
 **Asociaciones**
  
- **Almacén de SQL Server**: elija el almacén de SQL Server y una instancia con nombre opcional de la lista.
    
    Haga clic en **Nuevo** para definir un nuevo almacén y una instancia de SQL Server opcional.
    
- Active la casilla habilitar el reflejo de la **tienda de SQL Server** si quiere habilitar la creación de reflejos para el almacén principal de SQL Server.
    
    Si decide habilitar la creación de reflejo de la tienda de SQL Server, seleccione la tienda y la instancia en la lista de la lista **reflejo de SQL Server**.
    
    Haga clic en **Nuevo** para definir un nuevo almacén y una instancia de SQL Server opcional.
    
- Active la casilla **usar el testigo de reflejo de SQL Server para habilitar la conmutación por error automática** si quiere la conmutación automática por error del almacén principal de SQL Server.
    
    Si decide habilitar el testigo de reflejo de la tienda de SQL Server para habilitar la conmutación automática por error, seleccione la tienda y la instancia de la lista.
    
    Haga clic en **Nuevo** para definir un nuevo almacén de SQL Server y una instancia opcional para el almacén testigo.
    
- Si desea habilitar el uso de la recuperación de desastres de SQL Server, seleccione la casilla **usar la copia de seguridad de almacenes de SQL Server para habilitar** la recuperación de desastres
    
    Si optó por habilitar la recuperación ante desastres, seleccione un almacén y una instancia de la lista **Realizar copia de seguridad de almacén de SQL Server**.
    
    Haga clic en **Nuevo** para definir un nuevo almacén y una instancia de SQL Server opcional.
    
- Active la casilla habilitar el reflejo de la **tienda de SQL Server** si quiere habilitar la creación de reflejos para la copia de seguridad de la tienda de SQL Server.
    
    Si decide habilitar la creación de reflejos de la tienda SQL Server, seleccione la tienda y la instancia de la lista de copia de seguridad de la **tienda SQL Server**.
    
    Haga clic en **Nuevo** para definir un nuevo almacén y una instancia de SQL Server opcional.
    
- Active la casilla **usar el testigo de reflejo de SQL Server para habilitar la conmutación por error automática** si quiere la conmutación por error automática del almacén de SQL Server de copia de seguridad.
    
    Si decide habilitar el testigo de reflejo de la tienda de SQL Server para habilitar la conmutación automática por error, seleccione la tienda y la instancia de la lista.
    
    Haga clic en **Nuevo** para definir un nuevo almacén de SQL Server y una instancia opcional para el almacén testigo.
    
- Active la casilla **Habilitar cumplimiento** si desea habilitar el uso de una base de datos de cumplimiento.
    
    Si optó por habilitar el cumplimiento, seleccione un almacén y una instancia de la lista **Almacén de SQL Server de cumplimiento**.
    
    Haga clic en **Nuevo** para definir un nuevo almacén y una instancia de SQL Server opcional.
    
- Active la casilla habilitar el reflejo de la **tienda de SQL Server** si desea habilitar el reflejo para el almacén SQL Server de cumplimiento.
    
    Si decide habilitar la creación de reflejo de la tienda SQL Server de cumplimiento, seleccione la tienda y la instancia en la lista de cumplimiento de la **tienda SQL Server**.
    
    Haga clic en **Nuevo** para definir un nuevo almacén y una instancia de SQL Server opcional.
    
- Active la casilla **usar el testigo de reflejo de SQL Server para habilitar la conmutación por error automática** si quiere la conmutación automática por error del almacén de SQL Server de cumplimiento.
    
    Si decide habilitar el testigo de reflejo de la tienda de SQL Server para habilitar la conmutación automática por error, seleccione la tienda y la instancia de la lista.
    
    Haga clic en **Nuevo** para definir un nuevo almacén de SQL Server y una instancia opcional para el almacén testigo.
    
- Si optó por habilitar el cumplimiento, seleccione un almacén y una instancia de la lista **Realizar copia de seguridad de almacén de SQL Server de cumplimiento**.
    
    Haga clic en **Nuevo** para definir un nuevo almacén y una instancia de SQL Server opcional.
    
- Active la casilla habilitar el reflejo de la **tienda de SQL Server** si desea habilitar el reflejo para el almacén SQL Server de cumplimiento.
    
    Si decide habilitar el reflejo de la tienda SQL Server de cumplimiento, seleccione la tienda y la instancia de la lista de comprobación de cumplimiento de copia de seguridad de la **tienda SQL Server**.
    
    Haga clic en **Nuevo** para definir un nuevo almacén y una instancia de SQL Server opcional.
    
- Active la casilla **usar el testigo de reflejo de SQL Server para habilitar la conmutación por error automática** si quiere la conmutación automática por error del almacén SQL Server de cumplimiento de la copia de seguridad.
    
    Si decide habilitar el testigo de reflejo de la tienda de SQL Server para habilitar la conmutación automática por error, seleccione la tienda y la instancia de la lista.
    
    Haga clic en **Nuevo** para definir un nuevo almacén de SQL Server y una instancia opcional para el almacén testigo.
    
- **Almacén de archivos** Seleccione una ubicación de almacén de archivos de la lista o haga clic en **nuevo** para crear un nuevo almacén de archivos.
    
  **Aceptar.** Se aceptan y confirman los cambios en el cuadro de diálogo.
  
  **Cancelar.** Se descartan los cambios y se cierra el cuadro de diálogo.
  
  **Ayuda.** Abre esta pantalla de ayuda.
  
## <a name="see-also"></a>Vea también

[Planificar el servidor de chat persistente en Skype Empresarial Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Agregar un servidor de chat persistente a su topología de 2015 de Skype empresarial Server](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[Configurar la alta disponibilidad y la recuperación ante desastres para el servidor de chat persistente en Skype Empresarial Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
