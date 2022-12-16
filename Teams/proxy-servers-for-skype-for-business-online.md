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
ms.openlocfilehash: b2d46cbaa46670daf0235bfd020cae90c5bf624b
ms.sourcegitcommit: 00a526c5b9829302f7c4e0631d0c2dac50b7d004
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/16/2022
ms.locfileid: "69436686"
---
# <a name="proxy-servers-for-teams-and-skype-for-business-online"></a>Servidores proxy para Teams y Skype Empresarial Online

Este artículo proporciona instrucciones sobre el uso de un servidor proxy con Teams o Skype Empresarial.
  
## <a name="not-using-a-proxy-server-is-recommended"></a>Se recomienda no usar un servidor proxy

En lo que respecta a Teams o Skype Empresarial tráfico a través de servidores proxy, Microsoft recomienda omitirlos. Los servidores proxy no hacen que Teams o Skype Empresarial sean más seguros porque el tráfico ya está cifrado.
  
Además, tener un proxy puede causar problemas. Los problemas relacionados con el rendimiento se pueden introducir en el entorno a través de la latencia y la pérdida de paquetes al intentar redirigir el tráfico de Teams a través de un servidor proxy. Problemas como estos provocarán una experiencia negativa en equipos o Skype Empresarial escenarios como audio y vídeo, donde las transmisiones en tiempo real son esenciales.

Se recomienda que el tráfico de Teams omita la infraestructura del servidor proxy. Es posible que desee lograr esto colocando los teléfonos y los dispositivos de la sala de reuniones de Teams en su propia VLAN y proporcionándoles acceso a Internet.

## <a name="windows-based-teams-devices"></a>Windows-Based dispositivos de Teams

Las salas de reuniones de Teams basadas en Windows y Surface Hub admiten algunos servidores proxy, pero no los servidores proxy que requieren autenticación.

Recomendamos que estos dispositivos omitan la infraestructura de proxy y accedan a los servicios de Microsoft 365 a través del firewall.

## <a name="android-based-teams-devices"></a>Android-Based dispositivos de Teams

Los dispositivos de Teams basados en Android, incluidos teléfonos, paneles, pantallas y paneles de Teams, no admiten servidores proxy.

Debido a la forma en que determinados componentes que se ejecutan en estos dispositivos acceden a Internet, no es posible redirigir todo el tráfico a través de un proxy. Debes asegurarte de que el tráfico entre estos dispositivos y los servicios de Microsoft 365 esté permitido a través del firewall.

## <a name="if-you-need-to-use-a-proxy-server"></a>Si necesita usar un servidor proxy

Algunas organizaciones no tienen ninguna opción para omitir un proxy para Teams o Skype Empresarial tráfico. Si ese es su caso, hay que tener en cuenta los problemas mencionados anteriormente.

> [!Note]
> Si usa un certificado firmado de forma privada en la infraestructura de proxy, tendrá que instalar el certificado firmado de forma privada y la cadena de certificados en el dispositivo de la sala de reuniones de Teams para permitir que el dispositivo confíe en el certificado. No se admite la instalación de certificados firmados de forma privada en los teléfonos de Teams y en otros dispositivos de Teams basados en Android.
  
Microsoft también recomienda:
  
- El uso de la resolución DNS externa local (algunas soluciones de proxy basadas en la nube pueden hacer que la resolución DNS se produzca en otra ubicación).

- Garantizar la ruta entre el dispositivo teams y nuestro servicio es lo más corta y directa posible
    
- Usar el enrutamiento basado en UDP directo en lugar de depender del enrutamiento basado en TCP para medios
    
- Permitir el tráfico UDP para los medios de Teams (3478-3481) a través del firewall

- Permitir todas las direcciones URL e IP necesarias, incluidas las de Azure, Office 365, Intune y Teams Room Pro (donde se usen) a través del firewall
    
- Siguiendo las otras recomendaciones de nuestras directrices de redes: [Preparar la red de su organización para Teams](prepare-network.md)
  
    
Si se siguen estas instrucciones, la posibilidad de sufrir problemas debería ser mínima.
  
## <a name="related-topics"></a>Temas relacionados

[Principios de conectividad de red de Microsoft 365 y Office 365](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)

[Preparar la red de la organización para Microsoft Teams](prepare-network.md)
