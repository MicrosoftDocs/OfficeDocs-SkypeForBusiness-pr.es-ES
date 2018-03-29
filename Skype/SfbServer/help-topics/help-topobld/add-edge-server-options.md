---
title: Agregar opciones de servidor perimetral
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2405f227-4297-40d0-a117-55427a9e4052
description: 'Seleccione cada una de las características que quiera habilitar para el grupo de servidores perimetrales. El grupo de servidores perimetrales admite de forma predeterminada usuarios remotos de la organización que inician sesión desde fuera del firewall mediante una red privada virtual (VPN). También tiene las siguientes opciones de características del grupo de servidores perimetrales:'
ms.openlocfilehash: c2c73a664e15a48fd0fae3282e987b5e9b2954e3
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="add-edge-server-options"></a>Agregar opciones de servidor perimetral
 
Seleccione cada una de las características que quiera habilitar para el grupo de servidores perimetrales. El grupo de servidores perimetrales admite de forma predeterminada usuarios remotos de la organización que inician sesión desde fuera del firewall mediante una red privada virtual (VPN). También tiene las siguientes opciones de características del grupo de servidores perimetrales: 
  
- Use un solo nombre de dominio completo (FQDN) y dirección IP para todos los servicios perimetrales, incluidos el servicio perimetral de acceso, el servicio perimetral de conferencia web y el servicio perimetral A/V. Si no selecciona la opción para usar un solo FQDN y dirección IP, necesitará especificar FQDN y dirección IP distintos para cada uno de estos tres servicios perimetrales como parte del proceso de implementación. Para obtener más información acerca de los servicios de borde, vea [componentes necesarios para el acceso de usuario externo](http://technet.microsoft.com/library/2d0f9817-14e7-4109-95dc-62420e3c29e2.aspx) en la documentación de planeamiento.
    
    > [!NOTE]
    > Si selecciona esta opción, necesita especificar un número de puerto diferente para cada uno de los servicios perimetrales (configuración de puerto por defecto recomendada: 444 para el servicio perimetral de acceso, 8057 para el servicio perimetral de conferencia web y 443 para el servicio perimetral A/V). Seleccionar esta opción puede ayudar a impedir posibles problemas de conectividad y a simplificar la configuración, ya que permite introducir un FQDN que se va a usar en los tres servicios. 
  
- Compatibilidad con federación. Seleccione esta opción si desea admitir la comunicación entre usuarios internos y externos y usuarios de dominios de confianza externos a la organización, incluidos todos los usuarios de un proveedor de mensajería instantánea (MI) pública compatible. Si selecciona esta opción, necesitará configurar la compatibilidad para los dominios federados y proveedores de servicio de conectividad de MI concretos que desea que sean compatibles. Para obtener más información acerca de cómo configurar la compatibilidad con la federación y otros tipos de acceso de usuarios externos, consulte [Configurar la compatibilidad para el acceso de usuario externo](http://technet.microsoft.com/library/f8424f8c-f965-4414-8485-30f07e10214a.aspx) en la documentación de implementación de servidor de borde.
    
    > [!NOTE]
    > Solamente se puede publicar externamente para federación un grupo front-end o servidor perimetral estándar en su organización. Todo el acceso de los usuarios federados, incluidos los usuarios de MI pública, pasa por el mismo grupo de servidores perimetrales o por un servidor perimetral único. Por ejemplo, si la implementación incluye la implementación en Nueva York de un grupo de servidores perimetrales o un servidor perimetral único y la implementación de uno en Londres y habilita la compatibilidad de federación en el grupo de servidores perimetrales o el servidor perimetral único de Nueva York, el tráfico de señales de los usuarios federales pasará por el grupo de servidores perimetrales o el servidor perimetral único de Nueva York. Esto es así incluso para las comunicaciones con usuarios de Londres, aunque un usuario interno de Londres que llame a un usuario federado de Londres usa el grupo de servidores o el servidor perimetral de Londres para el tráfico A/V. 
  
- Habilitar la federación XMPP. Seleccione esta opción si desea permitir la comunicación entre usuarios internos y socios XMPP de confianza.
    
La compatibilidad para el acceso de usuarios externos se puede agregar al implementar la topología inicial o más adelante. Para obtener más información sobre cómo agregar servidores de borde a una topología existente, vea [Definir su topología de borde](http://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) en la documentación de implementación de servidor de borde.
  

