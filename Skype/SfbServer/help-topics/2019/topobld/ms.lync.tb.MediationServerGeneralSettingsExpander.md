---
title: Expansor de configuración general del servidor de mediación
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.MediationServerGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0e0ad9f0-27d5-4975-ae88-0b8ff8a4c514
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: f7caab78838818362aa416a49ac8ef6142f7b844
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30877356"
---
# <a name="mediation-server-general-settings-expander"></a>Expansor de configuración general del servidor de mediación
 


## <a name="general-settings"></a>Configuración general

Nombre de dominio completo (FQDN) del grupo de servidores de mediación o del servidor de mediación. Edite el FQDN del servidor para cambiar el valor correspondiente. Necesita haber un registro host (A) de DNS que coincida con el nuevo valor.
  
En la sección **asociaciones** , seleccione un servidor perimetral o grupo de servidores perimetrales para asociar con el grupo de servidores de mediación o el servidor de mediación. Seleccione el borde que se va a usar componentes de medios del servidor de mediación para usuarios externos de Enterprise Voice.
  
Si no tiene un servidor perimetral actualmente definidos y necesita para asociar el servidor de mediación a un servidor perimetral, haga clic en **nuevo** y defina el nuevo servidor perimetral o grupo de servidores perimetrales en la definir el Asistente de grupo de servidores perimetrales nuevo.
  
## <a name="next-hop-settings"></a>Configuración del próximo salto

Especificar el grupo de servidores de mediación o próximo salto del servidor de mediación seleccionando el grupo definido de Front-End de Enterprise Edition o Standard Edition front-end de la lista desplegable. Un Director o el Director de grupo de servidores no es una selección válida para un grupo de servidores de mediación o el próximo salto del servidor de mediación y no aparecerán en la lista. Haga clic en **Aceptar** para guardar los cambios. Haga clic en **Cancelar** para descartar los cambios y salir de la página de propiedades.
  
## <a name="pstn-gateway-settings"></a>Configuración de la puerta de enlace RTC

1. Definir las puertas de enlace de RTC que están asociados con el grupo de servidores de mediación o el servidor de mediación. Si ya se han definido las puertas de enlace, estarán disponibles para asociar con el servidor de mediación. Si habilita la combinación del servidor de mediación, necesitará definir el intervalo de puertos de escucha del servidor en los servidores del grupo para la Seguridad de la capa de transporte (TLS). Este puerto es 5067 de forma predeterminada. Si selecciona **Habilitar puerto TCP**, necesita definir un puerto TCP para el servidor de mediación combinado. Se trata de una configuración opcional; recomendamos revisar los requisitos de la puerta de enlace o los de la RTC para saber si realmente necesita esto. El valor de este puerto es 5068 de forma predeterminada.
    
2. Los troncos asociados con el servidor de mediación combinado. Si ya ha definido troncos, se podrán asociar inmediatamente con el servidor de mediación. 
    
3. Si tiene más de un tronco asociado con un servidor de mediación, puede especificar un tronco predeterminada seleccionando el tronco y, a continuación, haga clic en **Establecer como predeterminado**. Para anular la selección de una puerta de enlace como predeterminada, haga clic en **No establecer como predeterminado**. 
    

