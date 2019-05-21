---
title: Expansor de configuración general del servidor de mediación
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.MediationServerGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0e0ad9f0-27d5-4975-ae88-0b8ff8a4c514
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 5ce9c16fe44f26bf43a6fdd9a9850ed741efdaa0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34299233"
---
# <a name="mediation-server-general-settings-expander"></a>Expansor de configuración general del servidor de mediación
 


## <a name="general-settings"></a>Configuración general

Nombre de dominio completo (FQDN) del grupo de servidores de mediación o el servidor de mediación. Edite el FQDN del servidor para cambiar el valor correspondiente. Necesita haber un registro host (A) de DNS que coincida con el nuevo valor.
  
En la sección **asociaciones** , seleccione un servidor perimetral o un grupo de servidores perimetrales para asociar con el grupo de servidores de mediación o el servidor de mediación. Seleccione el borde que usarán los componentes multimedia del servidor de mediación para la telefonía IP empresarial de usuario externo.
  
Si no tiene un servidor perimetral definido actualmente y necesita asociar el servidor de mediación con un servidor perimetral, haga clic en **nuevo** y defina el nuevo servidor perimetral o grupo de servidores perimetrales en el Asistente para definir el nuevo grupo de límites.
  
## <a name="next-hop-settings"></a>Configuración del próximo salto

Para especificar el grupo de servidores de mediación o el próximo salto del servidor de mediación, seleccione en la lista desplegable el servidor front-end de Enterprise Edition o el servidor front-end Standard Edition definido. Un director o grupo de directores no es una selección válida para un grupo de servidores de mediación o un próximo salto al servidor de mediación, y no aparecerá en la lista. Haga clic en **Aceptar** para aceptar y guardar los cambios. Haga clic en **Cancelar** para descartar los cambios y salir de la página de propiedades.
  
## <a name="pstn-gateway-settings"></a>Configuración de la puerta de enlace RTC

1. Defina las puertas de enlace RTC que se asocian con el grupo de servidores de mediación o el servidor de mediación. Si ya ha definido las puertas de enlace, estarán disponibles para asociarlas con el servidor de mediación. Si habilita la combinación del servidor de mediación, necesitará definir el intervalo de puertos de escucha del servidor en los servidores del grupo para la Seguridad de la capa de transporte (TLS). Este puerto es 5067 de forma predeterminada. Si selecciona **Habilitar puerto TCP**, necesita definir un puerto TCP para el servidor de mediación combinado. Se trata de una configuración opcional; recomendamos revisar los requisitos de la puerta de enlace o los de la RTC para saber si realmente necesita esto. El valor de este puerto es 5068 de forma predeterminada.
    
2. Los troncos asociados con el servidor de mediación combinado. Si ya ha definido troncos, se podrán asociar inmediatamente con el servidor de mediación. 
    
3. Si tiene más de un tronco asociado a un servidor de mediación, puede especificar un tronco predeterminado seleccionando el tronco y, a continuación, haciendo clic en **establecer como predeterminado**. Para anular la selección de una puerta de enlace como predeterminada, haga clic en **No establecer como predeterminado**. 
    

