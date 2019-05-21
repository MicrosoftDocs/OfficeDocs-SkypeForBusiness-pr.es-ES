---
title: Configuración de notificaciones de inserción de cliente móvil
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientPushNotificationCfgMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b7a85d75-9d36-4980-b669-2a009799d905
ROBOTS: NOINDEX, NOFOLLOW
description: Para configurar las notificaciones de inserción de Microsoft y las notificaciones push de Apple, debe crear una directiva para definir qué tipos de notificaciones push necesita.
ms.openlocfilehash: 0211b3a8306297bd68402ad47d3c243541adf2bb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34300332"
---
# <a name="mobile-client-push-notification-configuration"></a>Cliente móvil: Configuración de notificaciones de inserción
 
Para configurar las **notificaciones de inserción de Microsoft** y las notificaciones push de **Apple**, debe crear una directiva para definir qué tipos de notificaciones push necesita.
  
En la pantalla principal de configuración, puede hacer clic en **Actualizar** para actualizar y volver a rellenar la lista de directivas. Se proporciona un cuadro de búsqueda para restringir la lista de directivas mostradas. A medida que escriba el nombre que está buscando, la lista de directivas se reducirá automáticamente.
  
> [!IMPORTANT]
> La configuración de directiva que se aplica en un nivel de directiva puede invalidar la configuración que se aplica en otro nivel de directiva. La precedencia de directiva es esta: la directiva de usuario (de mayor influencia) invalida una directiva de sitio, y una directiva de sitio invalida una directiva global (de menor influencia). Esto significa que, cuanto más cercana es la configuración de directiva al objeto al que la directiva afecta, mayor es la influencia que ejerce sobre el objeto. 
  
Hay dos opciones disponibles para la creación y edición de directivas:
  
1. **Nuevo**: haga clic para crear una nueva Directiva. Debe proporcionar un sitio para que la Directiva se aplique a. A continuación, configure las opciones de la notificación push. Para la configuración de notificaciones de **inserción**, solo puede crear directivas para sitios que ya haya creado.
    
2. **Editar**: Seleccione una directiva y haga clic en Editar para seleccionar una acción de una lista desplegable. Solo puede editar los sitios que ya ha creado o editar la directiva global:
    
   - **Mostrar detalles...**: muestra información sobre la Directiva seleccionada actualmente. Podrás realizar cambios en la directiva existente.
    
   - **Seleccionar todo**: Si tiene varias directivas y necesita seleccionar todas las directivas, haga clic en seleccionar todas.
    
   - **Eliminar**: quitará la Directiva seleccionada. Si usa **seleccionar todo** y **eliminar** , se eliminarán todas las directivas
    
     > [!NOTE]
     > No puede eliminar la directiva **global** predeterminada. Si intenta eliminarla, se le notificará que la directiva global se ha devuelto a los valores predeterminados (es decir, se ha desactivado toda la configuración), pero la Directiva no se puede quitar.
  
Crear una nueva Directiva o editar una directiva existente está asociado a dos acciones:
  
- **Confirmar** La acción confirmar crea o actualiza la Directiva y guarda los cambios.
    
- **Cancelar** La acción cancelar descarta los cambios que se hayan realizado desde la última acción de confirmación. Si cancelas, se perderán los cambios realizados.
    
Hay dos opciones posibles para la configuración de las **notificaciones push**. La configuración se asocia a los servicios de notificaciones de inserción para Microsoft y a Apple. Para habilitar la notificación de inserción para cualquiera de los servicios, active la casilla situada junto al nombre del servicio. Para desactivar la casilla, selecciónela para desactivarla. Una vez que haya realizado las selecciones, puede confirmar o cancelar. Al hacer clic en confirmar se guardarán los cambios en la Directiva.
  

