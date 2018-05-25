---
title: Expansor de configuración de FQDN del servidor perimetral
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/25/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeFqdnsSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9e4e9445-0147-4dd6-84f0-b41de142b332
description: Para editar o especificar la configuración externa para los servidores perimetrales, primero debe determinar si va a usar direcciones IP independientes para acceso de protocolo de inicio de sesión (SIP), el servicio de servidor perimetral de conferencia Web y el servicio perimetral de Audio y vídeo.
ms.openlocfilehash: 8c686252e4fab89ad08608dceea92f06a3776737
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2018
---
# <a name="edge-server-fqdns-settings-expander"></a>Expansor de configuración de FQDN del servidor perimetral
 
Para editar o especificar la **configuración externa** de los servidores perimetrales, primero debe determinar si va a usar direcciones IP diferentes para el acceso SIP, el servicio de servidor perimetral de conferencia web de y el servicio de servidor perimetral A/V.
  
Si tiene previsto usar direcciones IP diferentes para cada uno, active la casilla **Habilitar combinaciones distintas de FQDN y dirección IP para conferencia web y A/V**. Cada servicio debe tener su propio registro de host DNS (A) creado para ello.
  
Especifique un nombre de dominio completo y un puerto asociado por cada uno de los servicios de tipo externo. Por ejemplo, para **Acceso SIP**, puede usar sip.contoso.com con un puerto asociado de 5061.
  
> [!IMPORTANT]
> Si selecciona nombres de dominio completos diferentes para cada uno de los servicios externos, cada servicio debe tener asociado un valor de puerto exclusivo. De forma predeterminada, SIP se encuentra en el puerto 5061/TLS, el servicio perimetral de conferencia web se encuentra en el puerto 444/TLS y el servidor perimetral de conferencia de audio y vídeo se encuentra en el puerto 443/TLS. Si efectúa cambios en cualquiera de estas opciones, incluido el uso de nombres de dominio completo y direcciones IP o puertos diferentes, debe actualizar todos los demás servicios que dependan de los valores configurados inicialmente. 
  
Si decide que la organización va a usar una sola dirección IP y un solo nombre de dominio completo para los servicios externos, desactive la casilla **Habilitar combinaciones distintas de FQDN y dirección IP para conferencia web y A/V**. A continuación, puede editar los valores del puerto y el nombre de dominio completo de **Acceso SIP** si es necesario.
  
> [!IMPORTANT]
> Si efectúa cambios en cualquiera de estas opciones, incluido el uso de FQDN y direcciones IP o puertos diferentes, necesita actualizar todos los demás servicios que dependan de los valores configurados inicialmente. 
  
Para obtener información detallada sobre cómo definir y configurar las opciones de los Servicios perimetrales, consulte [Define Your Edge Topology](http://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx).
  

