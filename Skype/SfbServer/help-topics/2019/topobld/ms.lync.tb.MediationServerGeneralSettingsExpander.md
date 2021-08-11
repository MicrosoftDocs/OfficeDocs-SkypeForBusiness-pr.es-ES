---
title: Expansor de configuración general del servidor de mediación
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.MediationServerGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0e0ad9f0-27d5-4975-ae88-0b8ff8a4c514
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 064255bc958f9c1b59ca105cb943dca766f7715e59c71a5f1d1e0dee8620e868
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54285160"
---
# <a name="mediation-server-general-settings-expander"></a>Expansor de configuración general del servidor de mediación
 


## <a name="general-settings"></a>Configuración general

Nombre de dominio completo (FQDN) del servidor de mediación o el grupo de servidores de mediación. Edite el nombre de dominio completo del servidor que se va a cambiar. Debe tener un registro host (A) de DNS que coincida con el nuevo valor.
  
En la sección **Asociaciones**, seleccione un servidor perimetral o un grupo de servidores perimetrales para asociar con el servidor de mediación o el grupo de servidores de mediación. Seleccione el servidor perimetral que los componentes multimedia del servidor de mediación usarán para los usuarios externos Telefonía IP empresarial.
  
Si no tiene definido ningún servidor perimetral y necesita asociar el servidor de mediación con un servidor perimetral, haga clic en **Nuevo** y defina el nuevo servidor perimetral o el grupo de servidores perimetrales en el asistente para definir un nuevo grupo de servidores perimetrales.
  
## <a name="next-hop-settings"></a>Configuración del próximo salto

Se especifica el servidor de mediación o el grupo de servidores de mediación del próximo salto seleccionando el grupo de servidores front-end Enterprise Edition o el servidor front-end Standard Edition en la lista desplegable. Un servidor o un grupo de servidores director no son una selección válida para el siguiente salto de un servidor de mediación o un grupo de servidores de mediación; por lo tanto, no figurarán en la lista. Haga **clic en** Aceptar para aceptar y guardar los cambios. Haga clic en **Cancelar** para descartar los cambios y salir de la página de propiedades.
  
## <a name="pstn-gateway-settings"></a>Configuración de la puerta de enlace RTC

1. Defina las puertas de enlace de RTC asociadas con el servidor de mediación o el grupo de servidores de mediación. Si ya ha definido puertas de enlace, estarán disponibles para asociar con el servidor de mediación. Si habilita la colocación del servidor de mediación, el puerto de escucha del servidor en los servidores del grupo debe definirse para Seguridad de la capa de transporte (TLS). De forma predeterminada, este puerto es 5067. Si selecciona **Habilitar puerto TCP**, debe definir un puerto TCP para el servidor de mediación colocado. Se trata de una configuración opcional; se recomienda consultar los requisitos de la puerta de enlace o los de la RTC para saber si realmente necesita esto. De forma predeterminada, el valor de este puerto es 5068.
    
2. Los troncos asociados con el servidor de mediación colocado. Si ya ha definido troncos, se podrán asociar inmediatamente con el servidor de mediación. 
    
3. Si tiene asociado más de un tronco con un servidor de mediación, se puede especificar un tronco predeterminado seleccionando ese tronco y haciendo clic en **Convertir en predeterminada**. Para anular la selección de una puerta de enlace como predeterminada, haga clic en **Anular como predeterminada**. 
    

