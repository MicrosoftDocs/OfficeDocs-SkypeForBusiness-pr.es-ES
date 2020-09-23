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
- CSH
ms.custom:
- ms.lync.tb.FeMediationServiceSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 37166b87-8a43-42a6-a2aa-5a45bed8a6f3
description: 'Edite las propiedades de la configuración de la Puerta de enlace RTC del servidor de mediación en este cuadro de diálogo. Defina la configuración siguiente:'
ms.openlocfilehash: 37baf89b6100528c1485f939f69e20c697803123
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217731"
---
# <a name="front-end-mediation-service-settings-expander-for-lync-server-2010"></a>Expansor de configuración del servicio de mediación front-end para Lync Server 2010
 
Edite las propiedades de la configuración de la **Puerta de enlace RTC del servidor de mediación** en este cuadro de diálogo. Defina la configuración siguiente:
  
- Seleccione el **servidor de mediación combinado habilitado** si desea combinar el servidor de mediación con este servidor front-end o grupos de servidores front-end.
    
- **Puertos de escucha**: defina los puertos en los que escuchará el servidor de mediación. Puede definir un puerto para **TLS** o seguridad de la capa de transporte, o **TCP**, o protocolo de control de transporte. Para que la entrada de puerto de TCP esté disponible, debe seleccionar la casilla de verificación **Habilitar puerto TCP**. 
    
    > [!IMPORTANT]
    > Consulte la documentación y los ajustes de configuración de la puerta de enlace de la red telefónica conmutada (RTC) para determinar si necesita habilitar y definir valores de puerto TLS, TCP o ambos. TLS es un protocolo más seguro, con certificados para cifrar el tráfico entre el servidor de mediación y la puerta de enlace RTC. No todas las puertas de enlace de RTC admiten TLS. 
  
- Una lista del **Tronco** (es decir, troncos de protocolo de inicio de sesión (SIP)), **Puerta de enlace** (puerta de enlace RTC o IP-PBX) y **Sitio** (sitio configurado para el tronco y la puerta de enlace) existentes y actualmente asociados.
    
- Seleccione un Tronco, una Puerta de enlace y un Sitio y haga clic en **Convertir en predeterminado** para definir la selección como predeterminada para este servicio de mediación. Seleccione los valores predeterminados actuales y haga clic en **Eliminar predeterminado** para eliminar la selección de los valores predeterminados. A continuación debe seleccionar un nuevo valor predeterminado y hacer clic en **Convertir en predeterminado**.
    
  **Aceptar** Acepta y confirma los cambios realizados en el cuadro de diálogo.
  
  **Cancelar** Descarta los cambios y cierra el cuadro de diálogo.
  
  **Ayuda** Muestra la ayuda de esta pantalla.
  

