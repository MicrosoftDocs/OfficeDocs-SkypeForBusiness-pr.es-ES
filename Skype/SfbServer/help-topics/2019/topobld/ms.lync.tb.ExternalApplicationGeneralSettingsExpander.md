---
title: Expansor de configuración general de aplicación externa
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: eacc0c854290fcf24196a8e4c58829231dc725c4
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41793748"
---
# <a name="external-application-general-settings-expander"></a>Expansor de configuración general de aplicación externa
 
Para editar las propiedades de un servidor de aplicaciones de confianza que ya se ha definido, siga estas instrucciones.
  
Hay dos secciones que puede modificar:
  
> Configuración general
> 
> Configuración del próximo salto
    
## <a name="general-settings"></a>Configuración general

Puede modificar el nombre de dominio completo (FQDN) actual del grupo de servidores de aplicaciones de confianza. Edite el nombre del FQDN del grupo. Los registros de host (A) del sistema de nombres de dominio (DNS) deben existir para la nueva entrada antes de que los clientes o los servidores puedan conectarse al nuevo nombre de la agrupación.
  
Seleccione **Habilitar la replicación de datos de configuración en este grupo** si necesita tener replicación de datos de configuración en este grupo. Desactive la casilla si no desea replicar los datos de configuración.
  
## <a name="next-hop-settings"></a>Configuración del próximo salto

Puede especificar el servidor del próximo salto del grupo de servidores de aplicaciones de confianza seleccionando el grupo de servidores front-end de Enterprise Edition o el servidor front-end Standard Edition en la lista desplegable. Un director o grupo de directores no es una selección válida para el próximo salto de un servidor de aplicaciones de confianza y no aparecerá en la lista.
  

Haga clic en **Aceptar** para aceptar y guardar los cambios. Haga clic en **Cancelar** para descartar los cambios y salir de la página de propiedades.
  

