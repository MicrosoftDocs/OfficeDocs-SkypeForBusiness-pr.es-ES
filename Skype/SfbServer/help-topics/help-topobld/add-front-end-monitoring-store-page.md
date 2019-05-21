---
title: Página Agregar almacén de supervisión de front-end
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndMonitoringStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e8587d-a9d2-4fc5-acc5-2bf0abf133c6
description: 'Para definir el almacén de SQL Server de supervisión, configure las siguientes propiedades:'
ms.openlocfilehash: bd9a55e09a87f1c560f6e31d61094ddb915ad450
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275398"
---
# <a name="add-front-end-monitoring-store-page"></a>Página Agregar almacén de supervisión de front-end
 
Para **definir el almacén de SQL Server de supervisión** , configure las siguientes propiedades:
  
- **Supervisar el almacén de SQL Server**: Seleccione un nombre de dominio completo de SQL Server (y, opcionalmente, una instancia) de la lista.
    
    Haga clic en **nuevo** para crear una nueva definición de FQDN de SQL Server y, opcionalmente, un nombre de instancia para el almacén del servidor de supervisión.
    
- Active la casilla de verificación Habilitar el reflejo de la **tienda de SQL Server** si quiere agregar reflejo de base de datos para el servidor de supervisión.
    
    Seleccione en la lista un espejo de la **tienda SQL Server de supervisión** existente.
    
    Haga clic en **nuevo** para crear una nueva definición de FQDN de SQL Server y, opcionalmente, un nombre de instancia para el almacén de reflejo.
    
- Si seleccionó **Habilitar reflejo de la tienda SQL Server**, seleccione **usar el testigo de reflejo de SQL Server para habilitar la conmutación automática por error** para seleccionar un almacén testigo de reflejo de SQL Server de la lista.
    
    Haga clic en **nuevo** para crear una nueva definición de FQDN de SQL Server y, opcionalmente, un nombre de instancia para el almacén de testigo de reflejo.
    
Haga clic en **Atrás** para retroceder al cuadro de diálogo anterior de definición de grupo de servidores.
  
Cuando haya terminado de escribir las opciones de este cuadro de diálogo, haga clic en **siguiente** para continuar con la configuración.
  
Haga clic en **Cancelar** para descartar todos los cambios y finalizar el asistente.
  
Haga clic en **Ayuda** para obtener acceso a la ayuda contextual, como esta página.
  
## <a name="see-also"></a>Vea también

[Asociación de un almacén de supervisión a un grupo de servidores front-end en Skype Empresarial Server 2015](../../deploy/deploy-monitoring/associate-a-monitoring-store.md)
