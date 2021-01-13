---
title: Expansor de configuración de servicios web
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.WebServicesSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aefc9f51-a171-4a58-be65-7accb470cb2a
ROBOTS: NOINDEX, NOFOLLOW
description: Desde el Generador de topologías, puede modificar la configuración de puerto usada para los servicios web internos y externos. Además, y si va a implementar el equilibrio de carga del Sistema de nombres de dominio (DNS), puede usar el Generador de topologías para configurar el nombre de dominio completo (FQDN) del grupo de servidores que se resuelve en las direcciones IP físicas de todos los servidores de ese grupo.
ms.openlocfilehash: 99f052ebbfc4199f077744eee444333822075c24
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800700"
---
# <a name="web-services-settings-expander"></a>Expansor de configuración de servicios web
 
Desde el Generador de topologías, puede modificar la configuración de puerto usada para los servicios web internos y externos. Además, y si va a implementar el equilibrio de carga del Sistema de nombres de dominio (DNS), puede usar el Generador de topologías para configurar el nombre de dominio completo (FQDN) del grupo de servidores que se resuelve en las direcciones IP físicas de todos los servidores de ese grupo.
  
### <a name="editing-web-services-settings"></a>Edición de la configuración de los servicios web

1. Seleccione el servidor front-end Standard Edition adecuado o el grupo de servidores front-end Enterprise Edition adecuado y, a continuación, haga clic en **Editar propiedades**.
    
2. El el cuadro de diálogo **Editar propiedades**, haga clic en la pestaña **Servicios web**.
    
    > [!CAUTION]
    > Si tiene más de un grupo de servidores front-end o un servidor front-end, el FQDN de los servicios web externos debe ser único. Por ejemplo, si define el FQDN de servicios web externos de un servidor front-end como **pool01.contoso.com**, no puede usar **pool01.contoso.com** para otro grupo de servidores front-end o servidor front-end. Si también implementa directores, el FQDN de servicios web externos definido para cualquier director o grupo de directores debe ser único de cualquier otro director o grupo de directores, así como de cualquier grupo de servidores front-end o servidor front-end. Si decide invalidar los servicios web internos con un FQDN autodefinido, cada FQDN debe ser único de cualquier otro grupo de servidores front-end, director o grupo de directores.
  
3. Si edita las propiedades de un grupo Enterprise Edition, tiene la opción de seleccionar **FQDN de reemplazo**. Esta opción se debería seleccionar solamente si utiliza el equilibrio de carga del sistema de nombres de dominio (DNS). Si utiliza el equilibrio de carga de DNS, seleccione **FQDN de reemplazo** y, a continuación, en el cuadro de texto, escriba el FQDN del grupo que resuelve a las direcciones IP físicas de todos los servidores del grupo. Si no utiliza el equilibrio de carga de DNS y no selecciona **FQDN de reemplazo**, no podrá cambiar el FQDN de los servicios web internos. El FQDN de servicios web internos es la dirección URL que usan los usuarios internos para conectarse a Skype Empresarial Server.
    
4. De manera opcional, especifique valores nuevos de HTTP, HTTPS o HTTP y HTTPS para los **Puertos de escucha** y los **Puertos publicados**. Los puertos de escucha son los puertos que utilizan los Internet Information Services (IIS) para escuchar el tráfico entrante del protocolo de inicio de sesión (SIP); los puertos publicados son los puertos configurados en un equilibrador de cargas o servidor proxy inverso y también se utilizan para escuchar el tráfico SIP entrante. De forma predeterminada, tanto el puerto de escucha HTTP como el puerto publicado HTTP están definidos en el puerto 80; los puertos HTTPS correspondientes se establecen ambos a 443. El valor predeterminado de los dos puertos publicados HTTP es 8080 y los puertos HTTPS correspondientes se establecen a 4443.
    
5. Haga clic en **Aceptar**.
    
Si modifica el FQDN interno o cualquiera de los ajustes del puerto de escucha, deberá restablecer la configuración local en todos los servidores del grupo para que los cambios surjan efecto.
  

