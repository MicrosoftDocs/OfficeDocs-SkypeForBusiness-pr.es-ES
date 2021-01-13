---
title: Expansor de configuración general de aplicación externa
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.ExternalApplicationGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa7268ac-b9e3-4d25-bff4-e59d305120f2
ROBOTS: NOINDEX, NOFOLLOW
description: Para editar las propiedades de un servidor de aplicaciones de confianza que ya se ha definido, siga estas instrucciones.
ms.openlocfilehash: 8cdf27598c916f84e96b11d8acfaeb115a0575dd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822430"
---
# <a name="external-application-general-settings-expander"></a>Expansor de configuración general de aplicación externa
 
Para editar las propiedades de un servidor de aplicaciones de confianza que ya se ha definido, siga estas instrucciones.
  
Hay dos secciones que puede modificar:
  
> Configuración general
> 
> Configuración del próximo salto
    
## <a name="general-settings"></a>Configuración general

Puede modificar el nombre de dominios completo (FQDN) actual del grupo de servidores de aplicaciones de confianza. Edite el nombre del FQDN del grupo de servidores. Los registros de host (A) del sistema de nombres de dominio debe existir para la nueva entrada para que los clientes o servidores puedan conectarse con el nuevo nombre de grupo de servidores.
  
Seleccione **Habilitar replicación de datos de configuración en este grupo de servidores** si necesita replicar los datos de configuración en este grupo de servidores. Quite la marca de la casilla si no desea replicar los datos de configuración.
  
## <a name="next-hop-settings"></a>Configuración del próximo salto

Puede especificar el servidor del próximo salto del grupo de servidores de aplicaciones de confianza seleccionando el grupo de servidores front-end Enterprise Edition definido o el servidor front-end Standard Edition en la lista desplegable. Un servidor o un grupo de servidores Director no son una selección válida para el siguiente salto de un servidor de aplicaciones de confianza; por lo tanto, no figurarán en la lista.
  

Haga **clic en** Aceptar para aceptar y guardar los cambios. Haga clic en **Cancelar** para descartar los cambios y salir de la página de propiedades.
  

