---
title: Expansor de configuración de servicios web
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.WebServicesSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aefc9f51-a171-4a58-be65-7accb470cb2a
description: Desde el generador de topología, puede modificar la configuración de puerto que se usa para los servicios Web internos y externos. Además, y si va a implementar el equilibrio de carga del sistema de nombres de dominio (DNS), puede usar el generador de topología para configurar el nombre de dominio completo (FQDN) del grupo que se resuelve en las direcciones IP físicas de todos los servidores de ese grupo.
ms.openlocfilehash: 8b68a2318434c8849c180bdde188e0fe69dfd61f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34282066"
---
# <a name="web-services-settings-expander"></a>Expansor de configuración de servicios web
 
Desde el generador de topología, puede modificar la configuración de puerto que se usa para los servicios Web internos y externos. Además, y si va a implementar el equilibrio de carga del sistema de nombres de dominio (DNS), puede usar el generador de topología para configurar el nombre de dominio completo (FQDN) del grupo que se resuelve en las direcciones IP físicas de todos los servidores de ese grupo.
  
### <a name="editing-web-services-settings"></a>Edición de la configuración de los servicios web

1. Seleccione el servidor front-end Standard Edition o grupo de servidores front-end Enterprise Edition adecuado y, luego, haga clic en **Editar propiedades**.
    
2. En el cuadro de diálogo **Editar propiedades**, haga clic en la pestaña **Servicios web**.
    
    > [!CAUTION]
    > Si tiene más de un grupo de servidores front-end o un servidor front-end, el FQDN de los servicios web externos debe ser único. Por ejemplo, si define el FQDN de los servicios web externos de un servidor front-end como **pool01.contoso.com**, no puede usar **pool01.contoso.com** para otro grupo de servidores front-end o servidor front-end. Si también va a implementar directores, el FQDN de servicios Web externo definido para cualquier Director o grupo de directores debe ser único de cualquier otro grupo de directores o directores, así como de cualquier grupo de servidores front-end o servidor front-end. Si decide omitir los servicios Web internos con un FQDN autodefinido, cada FQDN debe ser único de cualquier otro grupo de servidores front-end, director o grupo de directores.
  
3. Si edita las propiedades de un grupo Enterprise Edition, tiene la opción de seleccionar **FQDN de reemplazo**. Esta opción se tendría que seleccionar solamente si usa el equilibrio de carga de Sistema de nombres de dominio (DNS). Si usa el equilibrio de carga de DNS, seleccione **FQDN de reemplazo** y, luego, en el cuadro de texto, escriba el FQDN del grupo que se resuelve en las direcciones IP físicas de todos los servidores del grupo. Si no usa el equilibrio de carga de DNS y no selecciona **FQDN de reemplazo**, no podrá cambiar el FQDN de los servicios web internos. El FQDN de los servicios Web internos es la dirección URL que usan los usuarios internos para conectarse a Skype empresarial Server.
    
4. De manera opcional, especifique valores nuevos de HTTP, HTTPS o HTTP y HTTPS para los **Puertos de escucha** y los **Puertos publicados**. Los puertos de escucha son los puertos que usan Internet Information Services (IIS) para escuchar el tráfico entrante del Protocolo de inicio de sesión (SIP), mientras que los puertos publicados son los puertos configurados en un equilibrador de carga o servidor proxy inverso, y también se usan para escuchar el tráfico SIP entrante. De forma predeterminada, tanto el puerto de escucha HTTP como el puerto publicado HTTP están definidos en el puerto 80, mientras que los puertos HTTPS correspondientes se establecen ambos en 443. El valor predeterminado de los dos puertos publicados HTTP es 8080 y los puertos HTTPS correspondientes, en 4443.
    
5. Haga clic en **Aceptar**.
    
Si modifica el FQDN interno o cualquiera de los ajustes del puerto de escucha, necesitará restablecer la configuración local en todos los servidores del grupo para que los cambios surtan efecto.
  

