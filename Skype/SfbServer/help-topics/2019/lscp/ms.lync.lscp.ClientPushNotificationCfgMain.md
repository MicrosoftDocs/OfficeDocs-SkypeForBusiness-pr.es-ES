---
title: Configuración de notificación de inserción de clientes móviles
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientPushNotificationCfgMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b7a85d75-9d36-4980-b669-2a009799d905
ROBOTS: NOINDEX, NOFOLLOW
description: Para configurar las notificaciones de inserción de Microsoft y las notificaciones de inserción de Apple, debe crear una directiva para definir los tipos de notificaciones de inserción que requieren.
ms.openlocfilehash: 03142994c6d591ec524f6b67b28cb0ad9790fc06
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "21003594"
---
# <a name="mobile-client-push-notification-configuration"></a>Cliente móvil: Configuración de notificación de inserción
 
Para configurar las **notificaciones de inserción de Microsoft** y **las notificaciones de inserción de Apple**, debe crear una directiva para definir qué tipos de notificaciones de inserción que necesite.
  
En la pantalla de configuración principal, haga clic en **Actualizar** para actualizar y volver a rellenar la lista de directivas. Se proporciona un cuadro de búsqueda para limitar la lista de directivas que se muestra. Mientras se escribe el nombre que se va a buscar, la lista de directivas se reduce automáticamente.
  
> [!IMPORTANT]
> La configuración de directiva que se aplica en un nivel de directiva puede invalidar la configuración que se aplica en otro nivel de directiva. La precedencia de directiva es esta: la directiva de usuario (de mayor influencia) invalida una directiva de sitio, y una directiva de sitio invalida una directiva global (de menor influencia). Esto significa que, cuanto más cercana es la configuración de directiva al objeto al que la directiva afecta, mayor es la influencia que ejerce sobre el objeto. 
  
Hay dos selecciones están disponibles para la creación de directivas y de edición:
  
1. **New**: haga clic aquí para crear una nueva directiva. Debe proporcionar un sitio para que se aplican a la directiva. A continuación, configure la configuración de la notificación de inserción. **Configuración de notificación de inserción**, sólo puede crear directivas para los sitios que ya ha creado.
    
2. **Editar**: seleccione una directiva y haga clic en Editar para seleccionar una acción de una lista desplegable. Sólo puede editar sitios que ya ha creado o editar la directiva Global:
    
  - **Mostrar detalles …**: muestra información acerca de la directiva seleccionada actualmente. Podrá realizar cambios en la directiva existente.
    
  - **Seleccionar todo**: si tiene un número de directivas y necesita seleccionar todas las directivas, haga clic en Seleccionar todo
    
  - **Eliminar**: se quita la directiva seleccionada. En **Seleccionar todo** y **Eliminar** quitará todas las directivas
    
    > [!NOTE]
    > No se puede eliminar la directiva **Global** predeterminada. Si intenta eliminarlo, se le notificará que se ha devuelto la directiva Global para los valores predeterminados (es decir, se borran todas las opciones), pero no se puede quitar la directiva.
  
Crear una nueva directiva o editar una directiva existente está asociado a dos acciones:
  
- **Confirmar** La acción Confirmar crea o actualiza la directiva y guarda los cambios
    
- **Cancelar** La acción Cancelar descarta los cambios que se han realizado desde la última acción de confirmación. Si cancela, se perderán todos los cambios realizados.
    
Son las dos configuraciones posibles para la **Configuración de notificación de inserción**. La configuración se asocian con los servicios de notificación de inserción de Microsoft y de Apple. Habilitar notificación de inserción para alguno de los servicios mediante la selección de la casilla de verificación situada junto al nombre del servicio. Puede desactivar la casilla de verificación mediante la selección para desactivarla. Una vez realizadas las selecciones, confirmar o cancela. Hacer clic en Confirmar va a guardar los cambios en la directiva.
  

