---
title: Configuración de servicio de Front-End mediación Expander para Lync Server 2010
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.FeMediationServiceSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 37166b87-8a43-42a6-a2aa-5a45bed8a6f3
description: 'Editar las propiedades de la configuración de puerta de enlace PSTN del servidor de mediación en este cuadro de diálogo. Defina las siguientes opciones:'
ms.openlocfilehash: e3ec392aac08121296769a9d5170886c61c7511b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="front-end-mediation-service-settings-expander-for-lync-server-2010"></a>Configuración de servicio de Front-End mediación Expander para Lync Server 2010
 
Editar las propiedades de la configuración de **puerta de enlace PSTN del servidor de mediación** en este cuadro de diálogo. Defina las siguientes opciones:
  
- Si desea colocar el servidor de mediación con este servidor Front-End o Front-End de grupos, seleccione el **servidor de mediación ubicados habilitado** .
    
- **Puertos de escucha**: definir los puertos de escucha en el servidor de mediación. Puede definir un puerto para la seguridad de la capa de transporte o **TLS** o **TCP**, o protocolo de control de transporte. Para la entrada de puerto para TCP esté disponible, debe seleccionar la casilla de verificación para **Habilitar el puerto TCP**. 
    
    > [!IMPORTANT]
    > Consulte la configuración de configuración y documentación de la puerta de enlace de telefónica pública conmutada (PSTN) de red para determinar si necesita habilitar y definir los valores de puerto TLS, TCP o ambos. TLS es un protocolo más seguro, el uso de certificados para cifrar el tráfico entre el servidor de mediación y la puerta de enlace PSTN. No todas las puertas de enlace PSTN compatible con TLS. 
  
- Lista del **Tronco** (es decir, troncos SIP), **Puertas de enlace** (puerta de enlace RTC o IP-PBX) y **Sitio** (sitio configurado para el tronco y la puerta de enlace) existentes y actualmente asociados.
    
- Seleccione un tronco, una puerta de enlace y un sitio y haga clic en **Establecer como predeterminado** para definir la selección como predeterminada para este servicio de mediación. Seleccione los valores predeterminados actuales y haga clic en **No establecer como predeterminado** para eliminar la selección de los valores predeterminados. Luego, necesitará seleccionar un nuevo valor predeterminado y hacer clic en **Establecer como predeterminado**.
    
 **Aceptar** Se aceptan y confirman los cambios en el cuadro de diálogo.
  
 **Cancelar** Se descartan los cambios y se cierra el cuadro de diálogo.
  
 **Ayuda** Abre esta pantalla de ayuda.
  

