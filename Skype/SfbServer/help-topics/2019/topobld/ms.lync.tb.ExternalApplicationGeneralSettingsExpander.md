---
title: Expansor de configuración General de aplicación externa
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.ExternalApplicationGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa7268ac-b9e3-4d25-bff4-e59d305120f2
ROBOTS: NOINDEX, NOFOLLOW
description: Para editar las propiedades de un servidor de aplicaciones de confianza que ya se ha definido, siga estas instrucciones.
ms.openlocfilehash: 73010b40bd5c06c1e59d9b2fee0e4fde3d247732
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25374549"
---
# <a name="external-application-general-settings-expander"></a>Expansor de configuración General de aplicación externa
 
Para editar las propiedades de un servidor de aplicaciones de confianza que ya se ha definido, siga estas instrucciones.
  
Hay dos secciones que se pueden modificar:
  
> Configuración general
> 
> Configuración del próximo salto
    
## <a name="general-settings"></a>Configuración general

Puede modificar el nombre de dominio completo (FQDN) actual para el grupo de servidores de aplicaciones de confianza. Edite el nombre del FQDN del grupo. Los registros de host (A) del sistema de nombres de dominio (DNS) deben existir para la nueva entrada antes que los clientes o servidores pueden conectar con el nuevo nombre de grupo de servidores.
  
Si necesita tener la replicación de datos de configuración para este grupo de servidores, seleccione **Habilitar la replicación de datos de configuración para este grupo de servidores** . Desactive la casilla de verificación si no desea replicar los datos de configuración.
  
## <a name="next-hop-settings"></a>Configuración del próximo salto

Puede especificar el servidor del próximo salto del grupo de servidores de aplicaciones de confianza mediante la selección de la definido grupo de servidores Front-End de Enterprise Edition o Standard Edition front-end de la lista desplegable. Un Director o el Director de grupo de servidores no es una selección válida para una aplicación de confianza próximo salto del servidor y no aparecerán en la lista.
  

Haga clic en **Aceptar** para guardar los cambios. Haga clic en **Cancelar** para descartar los cambios y salir de la página de propiedades.
  

