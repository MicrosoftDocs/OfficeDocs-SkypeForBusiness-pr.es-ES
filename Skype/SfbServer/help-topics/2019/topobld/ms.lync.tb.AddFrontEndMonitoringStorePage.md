---
title: Agregar página de almacén de supervisión de Front-End
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndMonitoringStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e8587d-a9d2-4fc5-acc5-2bf0abf133c6
description: 'Para definir el almacén de SQL Server de supervisión mediante la configuración de las siguientes propiedades:'
ms.openlocfilehash: bb53d2105bc3a412b06d1fc51fbd4413c49271e6
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/21/2018
ms.locfileid: "19988337"
---
# <a name="add-front-end-monitoring-store-page"></a>Agregar página de almacén de supervisión de Front-End
 
Para **definir el almacén de SQL Server de supervisión** mediante la configuración de las siguientes propiedades:
  
- **Almacén de SQL Server de supervisión**: seleccione un nombre de dominio completo de SQL Server (y, opcionalmente, una instancia) de la lista.
    
    Haga clic en **nuevo** para crear una nueva definición FQDN de SQL Server y, opcionalmente, un nombre de instancia para el almacén del servidor de supervisión.
    
- Active la casilla de verificación **la creación de reflejo de almacén de habilitar SQL Server** si desea agregar la creación de reflejos de base de datos para el servidor de supervisión.
    
    Seleccione un **reflejo de almacén de SQL Server de supervisión** existente de la lista.
    
    Haga clic en **nuevo** para crear una nueva definición FQDN de SQL Server y, opcionalmente, un nombre de instancia para el almacén de reflejo.
    
- Si seleccionó **la creación de reflejo de almacén de habilitar SQL Server**, seleccione opcionalmente **testigo para habilitar la conmutación por error automática de reflejo de utilizar SQL Server** para seleccionar un almacén de testigos de la lista de la creación de reflejos de SQL Server.
    
    Haga clic en **nuevo** para crear una nueva definición FQDN de SQL Server y, opcionalmente, un nombre de instancia para el almacén testigo de reflejo.
    
Haga clic en **Atrás** para retroceder al cuadro de diálogo anterior de definición del grupo de servidores.
  
Haga clic en **siguiente** cuando haya terminado de introducir las opciones de este cuadro de diálogo continuar con la configuración.
  
Haga clic en **Cancelar** para descartar todos los cambios y finalizar el asistente.
  
Haga clic en **Ayuda** para obtener acceso a la ayuda contextual, como esta página.
  
## <a name="see-also"></a>Vea también

[Asociar un almacén de supervisión a un grupo de servidores Front-End en Skype para Business Server](../../../deploy/deploy-monitoring/associate-a-monitoring-store.md)