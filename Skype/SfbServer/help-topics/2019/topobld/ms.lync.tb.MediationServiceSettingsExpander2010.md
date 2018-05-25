---
title: Expansor de configuración del servicio de mediación de Lync Server 2010
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/26/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.MediationServiceSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 230e0a08-9e16-4bbd-b550-1f04bad8ddbc
description: 'Defina las siguientes propiedades para editar las propiedades del servicio de mediación:'
ms.openlocfilehash: d8529a97459de70270fbe709d06c92e5a1b37af3
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2018
---
# <a name="mediation-service-settings-expander-for-lync-server-2010"></a>Expansor de configuración del servicio de mediación de Lync Server 2010
 
Defina las siguientes propiedades para editar las propiedades del servicio de mediación:
  
- **Puertos de escucha**: defina el puerto **TLS** en el que va a escuchar el servicio de mediación. El valor del puerto TCP es 5067 de forma predeterminada mediante Seguridad de la capa de transporte (TLS)
    
    Opcionalmente, puede definir un valor de puerto **TCP**. El valor predeterminado es TCP 5068.
    
    > [!NOTE]
    > Para habilitar la configuración del valor de puerto TCP, seleccione **Habilitar puerto TCP**. Mire la documentación de su puerta de enlace de red telefónica conmutada (RTC) o de la central de conmutación privada mediante protocolo de Internet (IP-PBX) para más información sobre los requisitos necesarios de configuración del puerto para comunicarse con el servicio de mediación. 
  
- Seleccione **Habilitar puerto TCP** para definir el valor de puerto de las comunicaciones TCP de una puerta de enlace RTC o IP-PBX.
    
- Lista del **Tronco** (es decir, troncos SIP), **Puertas de enlace** (puerta de enlace RTC o IP-PBX) y **Sitio** (sitio configurado para el tronco y la puerta de enlace) existentes y actualmente asociados.
    
- Seleccione un tronco, una puerta de enlace y un sitio y haga clic en **Establecer como predeterminado** para definir la selección como predeterminada para este servicio de mediación. Seleccione los valores predeterminados actuales y haga clic en **No establecer como predeterminado** para eliminar la selección de los valores predeterminados. Luego, necesitará seleccionar un nuevo valor predeterminado y hacer clic en **Establecer como predeterminado**.
    
 **Aceptar** Se aceptan y confirman los cambios en el cuadro de diálogo.
  
 **Cancelar** Se descartan los cambios y se cierra el cuadro de diálogo.
  
 **Ayuda** Abre esta pantalla de ayuda.
  

