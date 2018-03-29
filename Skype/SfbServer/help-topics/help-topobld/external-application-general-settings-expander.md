---
title: Ampliador de configuración General de aplicación externo
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.ExternalApplicationGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa7268ac-b9e3-4d25-bff4-e59d305120f2
description: Para editar las propiedades de un servidor de aplicaciones de confianza que ya se ha definido, siga estas instrucciones.
ms.openlocfilehash: 4104b9cf22a3db36afd159c0b7d9812142112ece
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="external-application-general-settings-expander"></a>Ampliador de configuración General de aplicación externo
 
Para editar las propiedades de un servidor de aplicaciones de confianza que ya se ha definido, siga estas instrucciones.
  
Hay dos secciones que se pueden modificar:
  
> Configuración general
    
> Configuración del próximo salto
    
## <a name="general-settings"></a>Configuración general

Puede modificar el nombre de dominio completo (FQDN) actual para el grupo de servidor de aplicaciones de confianza. Edite el nombre del FQDN del grupo. Los registros de host (A) del sistema de nombres de dominio (DNS) deben existir para la nueva entrada antes que los clientes o servidores pueden conectarse al nuevo nombre de grupo.
  
Seleccione **Habilitar la replicación de datos de configuración a este grupo** si es necesario tener la replicación de datos de configuración para este grupo. Desactive la casilla de verificación si no desea replicar los datos de configuración.
  
## <a name="next-hop-settings"></a>Configuración de salto siguiente

Puede especificar el servidor del próximo salto del grupo de aplicaciones de confianza servidor seleccionando el servidor Front End un servidor Standard Edition o Enterprise Edition Front-End grupo definido en la lista desplegable. Un Director o Director de grupo no es una selección válida para un salto siguiente del servidor de aplicaciones de confianza y no aparecerá en la lista.
  
## 

Haga clic en **Aceptar** para aceptar y guardar los cambios. Haga clic en **Cancelar** para descartar los cambios y salir de la página de propiedades.
  

