---
title: Expansor de configuración general del servidor de mediación
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 4/14/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.MediationServerGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0e0ad9f0-27d5-4975-ae88-0b8ff8a4c514
ms.openlocfilehash: 51e00323c3c0d5df3915b2652b273f1fa189143e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="mediation-server-general-settings-expander"></a>Expansor de configuración general del servidor de mediación
 
## 

### <a name="general-settings"></a>Configuración general

Nombre de dominio completo (FQDN) del servidor de mediación o grupo de servidores de mediación. Edite el FQDN del servidor para cambiar el valor correspondiente. Necesita haber un registro host (A) de DNS que coincida con el nuevo valor.
  
En la sección de **asociaciones** , seleccione un servidor perimetral o grupo de servidores de borde para asociar con el grupo de servidor de mediación o el servidor de mediación. Seleccione la arista que utilizarán los componentes de los medios de comunicación del servidor de mediación para Telefonía IP empresarial de usuario externo.
  
Si no tiene un servidor perimetral actualmente definidos y necesite asociar el servidor de mediación con un servidor perimetral, haga clic en **nuevo** y definir el nuevo servidor perimetral o grupo de servidores de borde en la definir el Asistente de grupo nuevo borde.
  
### <a name="next-hop-settings"></a>Configuración del próximo salto

Especificar el próximo salto de servidor de mediación o el grupo de servidor de mediación seleccionando el grupo definido de Enterprise Edition Front-End o Front End un servidor Standard Edition en la lista desplegable. Un Director o Director de grupo no es una selección válida para un grupo de servidor de mediación o siguiente salto de servidor de mediación y no aparecerá en la lista. Haga clic en **Aceptar** para aceptar y guardar los cambios. Haga clic en **Cancelar** para descartar los cambios y salir de la página de propiedades.
  
### <a name="pstn-gateway-settings"></a>Configuración de la puerta de enlace RTC

1. Definir puertas de enlace PSTN que están asociados con el grupo de servidor de mediación o el servidor de mediación. Si ya ha definido las puertas de enlace, estarán disponibles para asociar con el servidor de mediación. Si habilita la combinación del servidor de mediación, necesitará definir el intervalo de puertos de escucha del servidor en los servidores del grupo para la Seguridad de la capa de transporte (TLS). Este puerto es 5067 de forma predeterminada. Si selecciona **Habilitar puerto TCP**, necesita definir un puerto TCP para el servidor de mediación combinado. Se trata de una configuración opcional; recomendamos revisar los requisitos de la puerta de enlace o los de la RTC para saber si realmente necesita esto. El valor de este puerto es 5068 de forma predeterminada.
    
2. Los troncos asociados con el servidor de mediación combinado. Si ya ha definido troncos, se podrán asociar inmediatamente con el servidor de mediación. 
    
3. Si tiene más de un tronco asociada a un servidor de mediación, puede especificar un tronco predeterminada seleccionando el tronco y, a continuación, haga clic en **Establecer como predeterminado**. Para anular la selección de una puerta de enlace como predeterminada, haga clic en **No establecer como predeterminado**. 
    

