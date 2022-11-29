---
title: Servidores proxy para Skype Empresarial Online o Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: jastark
ms.topic: reference
ms.assetid: 7acaf2c2-35fa-490f-84cd-822e446e0fc7
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Optimization
- seo-marvel-apr2020
description: En este artículo se proporciona información sobre el uso de un servidor proxy con Microsoft Teams o Skype Empresarial.
ms.openlocfilehash: cdb4e6ccf05f597c87d066c18b1722eb08f89374
ms.sourcegitcommit: e9718ad7e23317d490b238b3801267cb2e6b26e2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2022
ms.locfileid: "69176677"
---
# <a name="proxy-servers-for-teams-or-skype-for-business-online"></a>Servidores proxy para Skype Empresarial Online o Teams

Este artículo proporciona instrucciones sobre el uso de un servidor proxy con Teams o Skype Empresarial.
  
## <a name="not-using-a-proxy-server-is-recommended"></a>Se recomienda no usar un servidor proxy

En lo que respecta a Teams o Skype Empresarial tráfico a través de servidores proxy, Microsoft recomienda omitirlos. Los servidores proxy no hacen que Teams o Skype Empresarial sean más seguros porque el tráfico ya está cifrado.
  
Además, tener un proxy puede causar problemas. Los problemas relacionados con el rendimiento se pueden introducir en el entorno a través de la latencia y la pérdida de paquetes al intentar redirigir el tráfico de Teams a través de un servidor proxy. Problemas como estos provocarán una experiencia negativa en equipos o Skype Empresarial escenarios como audio y vídeo, donde las transmisiones en tiempo real son esenciales.

Se recomienda que el tráfico de Teams omita la infraestructura del servidor proxy.

## <a name="teams-phones"></a>Teléfonos de Teams

Los teléfonos de Teams no son compatibles con los servidores proxy.

Nuestra recomendación es asegurarse de que el tráfico de señalización (TCP 443) y multimedia (UDP 3478-3481) omita la infraestructura del servidor proxy.

## <a name="teams-meeting-rooms-and-panels"></a>Salas de reuniones y paneles de Teams

Nuestra recomendación es asegurarse de que las salas de reunión de Teams omitan la infraestructura de proxy.

Las salas de reuniones de Teams basadas en Windows admiten servidores proxy, pero no los servidores proxy que requieren autenticación. Las salas de reuniones de Teams basadas en Android no son compatibles con los servidores proxy.
  
## <a name="if-you-need-to-use-a-proxy-server"></a>Si necesita usar un servidor proxy

Algunas organizaciones no tienen ninguna opción para omitir un proxy para Teams o Skype Empresarial tráfico. Si ese es su caso, hay que tener en cuenta los problemas mencionados anteriormente.
  
Microsoft también recomienda:
  
- El uso de la resolución DNS externa local (algunas soluciones de proxy basadas en la nube pueden hacer que la resolución DNS se produzca en otra ubicación).
    
- Usar el enrutamiento basado en UDP directo en lugar de depender del enrutamiento basado en TCP para medios
    
- Permitir tráfico UDP (3478-3481)

- Permitir todas las direcciones URL e IP necesarias, incluidas las de Azure, Office 365, Intune y Teams Room Pro (donde se usen)
    
- Siguiendo las otras recomendaciones de nuestras directrices de redes: [Preparar la red de su organización para Teams](prepare-network.md)
  
    
Si se siguen estas instrucciones, la posibilidad de sufrir problemas debería ser mínima.
  
## <a name="related-topics"></a>Temas relacionados

[Principios de conectividad de red de Microsoft 365 y Office 365](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)

[Preparar la red de la organización para Microsoft Teams](prepare-network.md)
