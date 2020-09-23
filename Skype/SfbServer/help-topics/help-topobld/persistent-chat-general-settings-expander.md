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
- CSH
ms.custom:
- ms.lync.tb.PersistentChatGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 275ee1ae-ca58-4963-bc95-523319f90d96
description: 'Para editar la configuración general del servidor de chat persistente o del grupo de servidores de chat persistente, configure o defina estas propiedades:'
ms.openlocfilehash: aae63b2d736f02b717b47aeff5fccb9b676daf99
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216001"
---
# <a name="persistent-chat-general-settings-expander"></a>Expansor de configuración general del chat persistente
 
Para editar la configuración **General** del servidor de chat persistente o del grupo de servidores de chat persistente, configure o defina estas propiedades:
  
 **General**
  
- **FQDN**: Edite esta configuración para definir el nombre de dominio completo del servidor de chat persistente o del grupo de servidores de chat persistente.
    
- **Mostrar nombre del grupo de servidores de chat persistente**: defina esta configuración para proporcionar una configuración comprensible y fácil de usar para el servidor o el grupo de servidores. Esta configuración hará que sea más fácil para los usuarios asociar un servidor de chat persistente determinado o un grupo de servidores de chat persistente según el nombre para mostrar en lugar de un nombre de dominio completo más difícil de comprender.
    
- **Puerto de chat persistente**: especifique el puerto que se debe usar para el chat persistente.
    
Para editar la configuración de las **asociaciones** del servidor de chat persistente o del grupo de servidores de chat persistente, configure o defina estas propiedades:
  
 **Asociaciones**
  
- **Almacén de SQL Server**: seleccione en la lista el almacén de SQL Server y una instancia con nombre opcional.
    
    Haga clic en **Nuevo** para definir un nuevo almacén y una instancia opcional de SQL Server.
    
- Active la casilla **Habilitar la creación de reflejo del almacén de SQL Server** si desea habilitar la creación de reflejo para el almacén de SQL Server principal.
    
    Si decidió habilitar la creación de reflejos del almacén de SQL Server, seleccione el almacén y la instancia en la lista **almacén de SQL Server de creación de reflejos**.
    
    Haga clic en **Nuevo** para definir un nuevo almacén y una instancia opcional de SQL Server.
    
- Active la casilla **usar el testigo de creación de reflejo de SQL Server para habilitar la conmutación por error automática** si desea la conmutación por error automática del almacén de SQL Server principal.
    
    Si decidió habilitar el testigo de creación de reflejos del almacén de SQL Server para habilitar la conmutación por error automática, seleccione el almacén y la instancia en la lista.
    
    Haga clic en **Nuevo** para definir un nuevo almacén de SQL Server y una instancia opcional para el almacén testigo.
    
- Active la casilla **usar almacenes de SQL Server de copia de seguridad para habilitar la recuperación ante desastres** si desea habilitar el uso de la recuperación ante desastres de SQL Server
    
    Si decidió habilitar la recuperación ante desastres, seleccione un almacén y una instancia de la lista **Almacén de SQL Server de reserva**.
    
    Haga clic en **Nuevo** para definir un nuevo almacén y una instancia opcional de SQL Server.
    
- Active la casilla **Habilitar creación de reflejos del almacén de SQL Server** si desea habilitar la creación de reflejo para el almacén de reflejos de SQL Server de copia de seguridad.
    
    Si decidió habilitar la creación de reflejos del almacén de SQL Server de copia de seguridad, seleccione el almacén y la instancia de la lista **reflejo de almacén de SQL Server de copia de seguridad**.
    
    Haga clic en **Nuevo** para definir un nuevo almacén y una instancia opcional de SQL Server.
    
- Active la casilla **usar el testigo de creación de reflejo de SQL Server para habilitar la conmutación por error automática** si desea la conmutación por error automática del almacén de SQL Server de copia de seguridad.
    
    Si decidió habilitar el testigo de creación de reflejos del almacén de SQL Server para habilitar la conmutación por error automática, seleccione el almacén y la instancia en la lista.
    
    Haga clic en **Nuevo** para definir un nuevo almacén de SQL Server y una instancia opcional para el almacén testigo.
    
- Active la casilla **Habilitar cumplimiento** si desea habilitar el uso de una base de datos de cumplimiento.
    
    Si decidió habilitar el cumplimiento, seleccione un almacén y una instancia de la lista **Almacén de SQL Server de cumplimiento**.
    
    Haga clic en **Nuevo** para definir un nuevo almacén y una instancia opcional de SQL Server.
    
- Active la casilla **Habilitar la creación de reflejos del almacén de SQL Server** si desea habilitar la creación de reflejos para el almacén de SQL Server de cumplimiento.
    
    Si optó por habilitar la creación de reflejos del almacén de SQL Server de cumplimiento, seleccione el almacén y la instancia en la lista **reflejo del almacén de SQL Server de cumplimiento**.
    
    Haga clic en **Nuevo** para definir un nuevo almacén y una instancia opcional de SQL Server.
    
- Active la casilla **usar el testigo de creación de reflejo de SQL Server para habilitar la conmutación por error automática** si desea la conmutación por error automática del almacén de SQL Server de cumplimiento.
    
    Si decidió habilitar el testigo de creación de reflejos del almacén de SQL Server para habilitar la conmutación por error automática, seleccione el almacén y la instancia en la lista.
    
    Haga clic en **Nuevo** para definir un nuevo almacén de SQL Server y una instancia opcional para el almacén testigo.
    
- Si decidió habilitar el cumplimiento, seleccione un almacén y una instancia de la lista **Almacén de SQL Server de cumplimiento de reserva**.
    
    Haga clic en **Nuevo** para definir un nuevo almacén y una instancia opcional de SQL Server.
    
- Active la casilla **Habilitar la creación de reflejos del almacén de SQL Server** si desea habilitar la creación de reflejos para el almacén de SQL Server de cumplimiento.
    
    Si optó por habilitar la creación de reflejos del almacén de SQL Server de cumplimiento, seleccione el almacén y la instancia de la lista **reflejo de almacén de SQL Server de cumplimiento de copia de seguridad**.
    
    Haga clic en **Nuevo** para definir un nuevo almacén y una instancia opcional de SQL Server.
    
- Seleccione la casilla **usar el testigo de creación de reflejo de SQL Server para habilitar la conmutación por error automática** si desea la conmutación por error automática del almacén de SQL Server de cumplimiento de copia de seguridad.
    
    Si decidió habilitar el testigo de creación de reflejos del almacén de SQL Server para habilitar la conmutación por error automática, seleccione el almacén y la instancia en la lista.
    
    Haga clic en **Nuevo** para definir un nuevo almacén de SQL Server y una instancia opcional para el almacén testigo.
    
- **Almacén de archivos** Seleccione una ubicación de almacén de archivos en la lista o haga clic en **nuevo** para crear un nuevo almacén de archivos.
    
  **Aceptar** Acepta y confirma los cambios realizados en el cuadro de diálogo.
  
  **Cancelar** Descarta los cambios y cierra el cuadro de diálogo.
  
  **Ayuda** Muestra la ayuda de esta pantalla.
  
## <a name="see-also"></a>Vea también

[Planeación del servidor de chat persistente en Skype empresarial Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Agregar un servidor de chat persistente a la topología de Skype empresarial Server 2015](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[Configurar la alta disponibilidad y la recuperación ante desastres para el servidor de chat persistente en Skype empresarial Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
