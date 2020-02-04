---
title: Expansor de configuración del servicio de mediación front-end para Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.FeMediationServiceSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 37166b87-8a43-42a6-a2aa-5a45bed8a6f3
description: 'Edite las propiedades de la configuración de la puerta de enlace RTC del servidor de mediación en este diálogo. Defina la siguiente configuración:'
ms.openlocfilehash: bd24c24d14e24ed7e4ce53bc30d01b2e955be6cf
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "41697285"
---
# <a name="front-end-mediation-service-settings-expander-for-lync-server-2010"></a>Expansor de configuración del servicio de mediación front-end para Lync Server 2010
 
Edite las propiedades de la configuración de la **puerta de enlace RTC del servidor de mediación** en este diálogo. Defina la siguiente configuración:
  
- Seleccione el **servidor de mediación agrupado habilitado** si desea Collocate el servidor de mediación con este servidor front-end o grupos front-end.
    
- **Puertos de escucha**: defina los puertos en los que escuchará el servidor de mediación. Puede definir un puerto para **TLS** o para la seguridad de la capa de transporte, **TCP**o protocolo de control de transporte. Para que la entrada de puerto para TCP esté disponible, debe activar la casilla de **Habilitar puerto TCP**. 
    
    > [!IMPORTANT]
    > Consulte la documentación y la configuración de la puerta de enlace de la red de telefonía pública conmutada (RTC) para determinar si necesita habilitar y definir los valores de los puertos TLS, TCP o ambos. TLS es un protocolo más seguro, que usa certificados para cifrar el tráfico entre el servidor de mediación y la puerta de enlace PSTN. No todas las puertas de enlace RTC admiten TLS. 
  
- Lista del **Tronco** (es decir, troncos SIP), **Puertas de enlace** (puerta de enlace RTC o IP-PBX) y **Sitio** (sitio configurado para el tronco y la puerta de enlace) existentes y actualmente asociados.
    
- Seleccione un tronco, una puerta de enlace y un sitio y haga clic en **Establecer como predeterminado** para definir la selección como predeterminada para este servicio de mediación. Seleccione los valores predeterminados actuales y haga clic en **No establecer como predeterminado** para eliminar la selección de los valores predeterminados. Luego, necesitará seleccionar un nuevo valor predeterminado y hacer clic en **Establecer como predeterminado**.
    
  **Aceptar.** Se aceptan y confirman los cambios en el cuadro de diálogo.
  
  **Cancelar.** Se descartan los cambios y se cierra el cuadro de diálogo.
  
  **Ayuda** Abre esta pantalla de ayuda.
  

