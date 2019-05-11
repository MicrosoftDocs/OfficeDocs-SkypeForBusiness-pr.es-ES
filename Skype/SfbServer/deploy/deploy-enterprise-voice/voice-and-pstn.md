---
title: Configurar directivas de voz, registros de uso de RTC y rutas de voz de Skype para la empresa
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 1e5a15f9-6f42-4dc6-baaa-24daf54afc4d
description: 'Resumen: Obtenga información sobre cómo configurar las directivas de voz, registros de uso de RTC y rutas de voz de Skype para Business Server.'
ms.openlocfilehash: 491d70a8bdec9017169a7937f52bb5403e94335f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33892233"
---
# <a name="configure-voice-policies-pstn-usage-records-and-voice-routes-in-skype-for-business"></a>Configurar directivas de voz, registros de uso de RTC y rutas de voz de Skype para la empresa
 
**Resumen:** Obtenga información sobre cómo configurar las directivas de voz, registros de uso de RTC y rutas de voz de Skype para Business Server.
  
Las directivas de voz, los registros de uso de RTC y las rutas de voz están totalmente relacionados. Para configurar las directivas de voz, debe seleccionar un grupo de características de llamada y luego asignar a la directiva un grupo de registros de uso de RTC, que especifican los derechos que se otorgarán a los usuarios o grupos a los que se les asigne la directiva de voz. A las rutas de voz también se les asignan registros de uso de RTC, que sirven para asociar las rutas con los usuarios autorizados para usarlas. Es decir, los usuarios solo pueden realizar llamadas que usan rutas para las que tienen registros de uso de RTC coincidentes.
  
El flujo de trabajo recomendado para una nueva implementación de Enterprise Voice es comenzar configurando una directiva de voz que incluya los registros de uso de RTC adecuados y, a continuación, asociar las rutas apropiadas para cada registro de uso de RTC. 
  
> [!NOTE]
> También puede crear directivas de voz con ámbito de *usuario* y asignarlas a usuarios individuales o grupos.
  
Para consultar los pasos detallados que se deben seguir para realizar cada una de estas tareas, consulte los procedimientos que se explican en esta sección.
  
## <a name="in-this-section"></a>En esta sección

- [Crear o modificar una directiva de voz y configurar registros de uso de RTC en Skype para la empresa](voice-policy-and-pstn-usage-records.md)
    
- [Configurar escape de correo de voz de Skype para la empresa](configure-voice-mail-escape.md)
    
- [Ver registros de uso de RTC de Skype para la empresa](view-pstn-usage-records.md)
    
- [Crear o modificar una ruta de voz de Skype para la empresa](create-or-modify-a-voice-route.md)
    
- [Exportar o importar un archivo de configuración de ruta de voz de Skype para la empresa](voice-route-configuration-import-export.md)
    
- [Publicar cambios pendientes en la configuración de enrutamiento de voz de Skype para la empresa](voice-route-config-changes.md)
    

