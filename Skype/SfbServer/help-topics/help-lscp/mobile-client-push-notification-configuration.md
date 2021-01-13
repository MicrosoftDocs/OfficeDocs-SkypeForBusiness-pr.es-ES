---
title: Configuración de notificaciones de inserción de cliente móvil
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientPushNotificationCfgMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b7a85d75-9d36-4980-b669-2a009799d905
description: Para configurar Notificaciones de inserción de Microsoft y Notificaciones de inserción de Apple, debe crear una directiva para definir qué tipos de notificaciones de inserción requiere.
ms.openlocfilehash: 493c8138e7c5dcaeab154ce1a44054cc082d1672
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49810880"
---
# <a name="mobile-client-push-notification-configuration"></a>Cliente móvil: Configuración de notificaciones de inserción
 
Para configurar **Notificaciones de inserción de Microsoft** y **Notificaciones de inserción de Apple**, debe crear una directiva para definir qué tipos de notificaciones de inserción requiere.
  
En la pantalla de configuración principal, puede hacer clic en **Actualizar** para actualizar y volver a llenar la lista de directivas. Se proporciona un cuadro de búsqueda para delimitar la lista de directivas mostradas. Conforme escriba el nombre que está buscando, la lista de directivas se filtra automáticamente.
  
> [!IMPORTANT]
> Las opciones de configuración de directiva que se aplican en un nivel de directiva pueden sobrescribir la configuración que se aplica en otro nivel de directiva. La prioridad de la directiva es: la directiva de usuario (más influencia) invalida una directiva de sitio y, a continuación, una directiva de sitio invalida una directiva global (menor influencia). Esto significa que cuanto más se aproxime la configuración de la directiva al objeto al que afecta la directiva, más influencia tendrá en el objeto. 
  
Hay dos selecciones disponibles para la creación y edición de directivas:
  
1. **Nueva**: haga clic para crear una nueva directiva. Debe proporcionar un sitio para que se aplique la directiva. Después, configure los ajustes para la notificación de inserciones. Para **Configuración de notificación de inserciones**, solo puede crear directivas para sitios que ya haya creado.
    
2. **Editar**: seleccione una directiva y haga clic en Editar para seleccionar una acción del menú desplegable. Solo puede editar sitios que ya haya creado o editar la directiva global:
    
   - **Mostrar detalles…**: muestra información sobre la directiva seleccionada actualmente. Podrá realizar cambios en la directiva existente.
    
   - **Seleccionar todo**: si tiene un número de directivas y necesita seleccionarlas todas, haga clic en Seleccionar todo.
    
   - **Eliminar**: quitará la directiva seleccionada. Al usar **Seleccionar todo** y **Eliminar**, se eliminarán todas las directivas.
    
     > [!NOTE]
     > No es posible eliminar la directiva **Global** predeterminada. Si intenta eliminarla, se le notificará que la directiva Global ha vuelto a los valores predeterminados (es decir, se eliminarán todos los ajustes), pero la directiva no se puede eliminar.
  
La creación de una directiva nueva o la edición de una directiva existente están asociadas con dos acciones:
  
- **Commit** La acción de confirmación crea o actualiza la directiva y guarda los cambios
    
- **Cancelar** La acción cancelar descarta los cambios realizados desde la última acción de confirmación. Si cancela, se perderán los cambios realizados.
    
Hay dos opciones posibles para **Configuración de notificaciones de inserción**. Los valores se asocian con los servicios de notificación de inserciones de Microsoft y Apple. Puede habilitar la notificación de inserciones para cualquier servicio activando la casilla que hay junto al nombre del servicio. Puede desactivar la casilla seleccionándola para desmarcarla. Una vez que haya hecho las selecciones, confirme o cancele. Al hacer clic en Confirmar, se guardarán todos los cambios en la directiva.
  

