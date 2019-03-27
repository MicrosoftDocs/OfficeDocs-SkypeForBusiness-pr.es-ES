---
title: Expansor de configuración de servicios web
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.WebServicesSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aefc9f51-a171-4a58-be65-7accb470cb2a
ROBOTS: NOINDEX, NOFOLLOW
description: Desde el generador de topología, puede modificar la configuración de puerto usada para ambos los servicios web internos y externos. Además, y si va a implementar el equilibrio de carga del sistema de nombres de dominio (DNS), puede usar el generador de topología para configurar el nombre de dominio completo (FQDN) del grupo de servidores que se resuelve en las direcciones IP físicas de todos los servidores de ese grupo.
ms.openlocfilehash: 75d73a81ec649c97149fd03125887116c947144c
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30889178"
---
# <a name="web-services-settings-expander"></a>Expansor de configuración de servicios web
 
Desde el generador de topología, puede modificar la configuración de puerto usada para ambos los servicios web internos y externos. Además, y si va a implementar el equilibrio de carga del sistema de nombres de dominio (DNS), puede usar el generador de topología para configurar el nombre de dominio completo (FQDN) del grupo de servidores que se resuelve en las direcciones IP físicas de todos los servidores de ese grupo.
  
### <a name="editing-web-services-settings"></a>Edición de la configuración de los servicios web

1. Seleccione el servidor front-end Standard Edition o grupo de servidores front-end Enterprise Edition adecuado y, luego, haga clic en **Editar propiedades**.
    
2. En el cuadro de diálogo **Editar propiedades**, haga clic en la pestaña **Servicios web**.
    
    > [!CAUTION]
    > Si tiene más de un grupo de servidores Front-End o servidor Front-End, los servicios Web externos FQDN debe ser único. Por ejemplo, si define el FQDN de un servidor Front-End de servicios Web externos como **pool01.contoso.com**, no puede usar **pool01.contoso.com** para otro grupo de servidores Front-End o servidor Front-End. Si va a implementar también los directores, la externa FQDN definido para cualquier Director de los servicios Web o debe ser único de cualquier otro grupo de directores Director o Director del grupo de servidores, así como cualquier otro grupo de servidores Front-End o un servidor Front-End. Si decide reemplazar los servicios web internos con un FQDN autodefinido, cada FQDN debe ser único de cualquier otro grupo de servidores Front-End, Director o un grupo de directores.
  
3. Si edita las propiedades de un grupo Enterprise Edition, tiene la opción de seleccionar **FQDN de reemplazo**. Esta opción se tendría que seleccionar solamente si usa el equilibrio de carga de Sistema de nombres de dominio (DNS). Si usa el equilibrio de carga de DNS, seleccione **FQDN de reemplazo** y, luego, en el cuadro de texto, escriba el FQDN del grupo que se resuelve en las direcciones IP físicas de todos los servidores del grupo. Si no usa el equilibrio de carga de DNS y no selecciona **FQDN de reemplazo**, no podrá cambiar el FQDN de los servicios web internos. Los servicios web internos FQDN es la dirección URL utilizada por los usuarios internos para conectarse a Skype para Business Server.
    
4. De manera opcional, especifique valores nuevos de HTTP, HTTPS o HTTP y HTTPS para los **Puertos de escucha** y los **Puertos publicados**. Los puertos de escucha son los puertos que usan Internet Information Services (IIS) para escuchar el tráfico entrante del Protocolo de inicio de sesión (SIP), mientras que los puertos publicados son los puertos configurados en un equilibrador de carga o servidor proxy inverso, y también se usan para escuchar el tráfico SIP entrante. De forma predeterminada, tanto el puerto de escucha HTTP como el puerto publicado HTTP están definidos en el puerto 80, mientras que los puertos HTTPS correspondientes se establecen ambos en 443. El valor predeterminado de los dos puertos publicados HTTP es 8080 y los puertos HTTPS correspondientes, en 4443.
    
5. Haga clic en **Aceptar**.
    
Si modifica el FQDN interno o cualquiera de los ajustes del puerto de escucha, necesitará restablecer la configuración local en todos los servidores del grupo para que los cambios surtan efecto.
  

