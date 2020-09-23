---
title: Expansor de configuración del servicio de mediación para Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.MediationServiceSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 230e0a08-9e16-4bbd-b550-1f04bad8ddbc
description: 'Para editar las propiedades del servicio de mediación, defina las propiedades siguientes:'
ms.openlocfilehash: 51fbd889d7e9d673fb75b1062a70ae55a9f8585c
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215111"
---
# <a name="mediation-service-settings-expander-for-lync-server-2010"></a>Expansor de configuración del servicio de mediación para Lync Server 2010
 
Para editar las propiedades del servicio de mediación, defina las propiedades siguientes:
  
- **Puertos de escucha**: defina el puerto **TLS** en el que va a escuchar el servicio de mediación. De forma predeterminada, el valor del puerto el TCP 5067 mediante seguridad de la capa de transporte (TLS)
    
    Opcionalmente, puede definir un valor de puerto **TCP**. El valor predeterminado es TCP 5068.
    
    > [!NOTE]
    > Para habilitar la configuración del valor de puerto TCP, seleccione **Habilitar puerto TCP**. Consulte la documentación de su puerta de enlace de red telefónica conmutada (RTC) o de la central de conmutación privada mediante protocolo de Internet (IP-PBX) para obtener información sobre los requisitos de configuración del puerto necesarios para comunicarse con el servicio de mediación. 
  
- Seleccione **Habilitar puerto TCP** para definir el valor de puerto de las comunicaciones TCP de una puerta de enlace RTC o IP-PBX.
    
- Una lista del **Tronco** (es decir, troncos del protocolo de inicio de sesión (SIP), la **Puerta de enlace** (puerta de enlace RTC o IP-PBX) y el **Sitio** (sitio configurado para el tronco y la puerta de enlace) existentes y los asociados actualmente.
    
- Seleccione un Tronco, una Puerta de enlace y un Sitio y haga clic en **Convertir en predeterminado** para definir la selección como predeterminada para este servicio de mediación. Seleccione los valores predeterminados actuales y haga clic en **Eliminar predeterminado** para eliminar la selección de los valores predeterminados. A continuación debe seleccionar un nuevo valor predeterminado y hacer clic en **Convertir en predeterminado**.
    
  **Aceptar** Acepta y confirma los cambios realizados en el cuadro de diálogo.
  
  **Cancelar** Descarta los cambios y cierra el cuadro de diálogo.
  
  **Ayuda** Muestra la ayuda de esta pantalla.
  

