---
title: Configuración de notificación de inserción de clientes móviles
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientPushNotificationCfgMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b7a85d75-9d36-4980-b669-2a009799d905
description: Para configurar las notificaciones de inserción de Microsoft y las notificaciones de inserción de Apple, debe crear una directiva para definir los tipos de notificación de inserción requiere.
ms.openlocfilehash: 946e083ab9f3f4dbc2b59f7f3026ec3a6dd5ed19
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="mobile-client-push-notification-configuration"></a>Cliente móvil: Configuración de notificación de inserción
 
Para configurar las **notificaciones de inserción de Microsoft** y **las notificaciones de inserción de Apple**, debe crear una directiva para definir qué tipos de notificación de inserción que necesite.
  
En la pantalla principal de configuración, haga clic en **Actualizar** para actualizar y volver a llenar la lista de directivas. Se proporciona un cuadro de búsqueda para limitar la lista de directivas mostradas. Mientras escribe el nombre que está buscando, la lista de directivas se reduce automáticamente.
  
> [!IMPORTANT]
> La configuración de directiva que se aplica en un nivel de directiva puede invalidar la configuración que se aplica en otro nivel de directiva. La precedencia de directiva es esta: la directiva de usuario (de mayor influencia) invalida una directiva de sitio, y una directiva de sitio invalida una directiva global (de menor influencia). Esto significa que, cuanto más cercana es la configuración de directiva al objeto al que la directiva afecta, mayor es la influencia que ejerce sobre el objeto. 
  
Dos selecciones están disponibles para la creación de directivas y edición:
  
1. **Nuevo**: haga clic para crear una nueva directiva. Debe proporcionar un sitio para aplicar a la directiva. A continuación, configure la configuración de la notificación de inserción. Para la **Configuración de las notificaciones Push**, sólo puede crear directivas para los sitios que ya ha creado.
    
2. **Editar**: seleccione una directiva y haga clic en Editar para seleccionar una acción de una lista desplegable. Sólo puede editar sitios que ya ha creado o modificar la directiva Global:
    
  - **Mostrar detalles...**: muestra información acerca de la directiva seleccionada actualmente. Podrá realizar cambios en la directiva existente.
    
  - **Seleccionar todo**: si tiene un número de directivas y necesita seleccionar todas las directivas, haga clic en Seleccionar todo
    
  - **Eliminar**: eliminará la directiva seleccionada. En **Seleccionar todo** y **Borrar** quitará todas las directivas
    
    > [!NOTE]
    > No se puede eliminar la directiva **Global** predeterminada. Si intenta eliminarlo, se le notificará que la directiva Global se ha vuelto a los valores predeterminados (es decir, se borran todas las configuraciones), pero no se puede quitar la directiva.
  
Crear una nueva directiva o editar una directiva existente está asociado a dos acciones:
  
- **Confirmar** La acción Confirmar crea o actualiza la directiva y guarda los cambios
    
- **Cancelar** La acción Cancelar descarta los cambios que se han realizado desde la última acción de confirmación. Si cancela, se perderán los cambios realizados.
    
Son las dos configuraciones posibles para la **Configuración de notificación de inserción**. Los valores están asociados con los servicios de notificación de inserción de Microsoft y de Apple. Habilitar notificación de inserción para cualquier servicio seleccionando la casilla de verificación situada junto al nombre del servicio. Puede desactivar la casilla de verificación para desactivarla seleccionando. Una vez realizadas las selecciones, confirmar o cancela. Al hacer clic en Confirmar guardará los cambios a la directiva.
  

