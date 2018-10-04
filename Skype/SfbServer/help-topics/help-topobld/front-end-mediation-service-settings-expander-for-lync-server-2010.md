---
title: Expansor de configuración de servicio de mediación de Front-End de Lync Server 2010
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.FeMediationServiceSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 37166b87-8a43-42a6-a2aa-5a45bed8a6f3
description: 'Para editar las propiedades de la configuración de puerta de enlace de RTC del servidor de mediación en este cuadro de diálogo. Defina las opciones siguientes:'
ms.openlocfilehash: a70ec5e569b60c28e8ec91e86d09ac5f5285ee00
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25371494"
---
# <a name="front-end-mediation-service-settings-expander-for-lync-server-2010"></a>Expansor de configuración de servicio de mediación de Front-End de Lync Server 2010
 
Para editar las propiedades de la configuración de **puerta de enlace RTC del servidor de mediación** en este cuadro de diálogo. Defina las opciones siguientes:
  
- Seleccione el **servidor de mediación combinado habilitado** si desea instalar el servidor de mediación con este servidor Front-End o Front-End de grupos de servidores.
    
- **Puertos de escucha**: definir los puertos de escucha en el servidor de mediación. Puede definir un puerto para la seguridad de la capa de transporte o de **TLS** o **TCP**, o protocolo de control de transporte. Para el puerto de entrada para TCP para que esté disponible, debe seleccionar la casilla de verificación para **Habilitar el puerto TCP**. 
    
    > [!IMPORTANT]
    > Hacer referencia a la configuración de documentación y la configuración de la puerta de enlace de telefónica conmutada (RTC) para determinar si necesita habilitar y definir valores de puerto TLS, TCP o ambos. TLS es un protocolo más seguro, uso de certificados para cifrar el tráfico entre el servidor de mediación y la puerta de enlace de RTC. No todas las puertas de enlace de RTC admiten TLS. 
  
- Lista del **Tronco** (es decir, troncos SIP), **Puertas de enlace** (puerta de enlace RTC o IP-PBX) y **Sitio** (sitio configurado para el tronco y la puerta de enlace) existentes y actualmente asociados.
    
- Seleccione un tronco, una puerta de enlace y un sitio y haga clic en **Establecer como predeterminado** para definir la selección como predeterminada para este servicio de mediación. Seleccione los valores predeterminados actuales y haga clic en **No establecer como predeterminado** para eliminar la selección de los valores predeterminados. Luego, necesitará seleccionar un nuevo valor predeterminado y hacer clic en **Establecer como predeterminado**.
    
  **Aceptar** Se aceptan y confirman los cambios en el cuadro de diálogo.
  
  **Cancelar** Se descartan los cambios y se cierra el cuadro de diálogo.
  
  **Ayuda** Abre esta pantalla de ayuda.
  

