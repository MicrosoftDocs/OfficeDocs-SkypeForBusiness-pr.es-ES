---
title: Caso práctico de voz de Contoso
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: Estudio de casos de voz de Teams para la corporación multinacional
appliesto:
- Microsoft Teams
ms.openlocfilehash: f1ba92794b2ba17cc23e1bca55800c9307707636
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786073"
---
# <a name="contoso-case-study-location-based-routing"></a>Caso práctico de Contoso: enrutamiento basado en la ubicación

El enrutamiento basado en la ubicación (LBR) es una característica que restringe el omisión de peaje según la política y la ubicación física del usuario en el momento de poner o recibir una llamada.  

## <a name="overview"></a>Información general

Contoso tiene dos oficinas en un país en el que no se puede eludir el proveedor de la red de telefonía pública conmutada (RTC) para reducir los gastos de llamadas de larga distancia. La oficina principal tiene una conexión a Internet que es utilizada por la oficina principal y por la segunda oficina. Cada oficina tiene su propio controlador de borde de sesión (SBC) conectado a una portadora RTC.  
 
En este país, contoso tenía LBR configurado para la implementación de Skype empresarial. Para determinar cómo configurar LBR para Teams, plan de Contoso read [: enrutamiento basado en la ubicación para el enrutamiento directo](location-based-routing-plan.md). Contoso determinó que Teams y Skype empresarial siguen los mismos escenarios en los que se puede hacer una llamada, Cuándo se puede recibir, Cuándo se puede transferir una llamada RTC a un usuario de Teams y cuándo se puede transferir otro usuario de Teams a la llamada RTC.  

Para Skype empresarial, LBR se configuró con el tronco del SIP del controlador de borde de sesión (SBC) que se conecta a la portadora RTC. Para este SBC, contoso revisó la [lista de SBCS certificado](direct-routing-border-controllers.md) y determinó que el SBC implementado está certificado para enrutamiento directo, pero no está certificado para la omisión de medios. Para admitir LBR, debe configurarse el enrutamiento directo a la SBC en el sitio, debe haber una salida de Internet local y el SBC debe configurarse para la omisión de medios. En función de esta información, contoso decidió lo siguiente:

- Para retrasar la habilitación de Teams LBR hasta que se certifique el SBC existente para la omisión de medios.   

- Contoso decidió usar el SBC del sitio principal para la ruta directa a Office 365.  El SBC del sitio principal será el SBC de proxy para el sitio remoto.  

- Contoso usó un consultor de terceros basado en India para ayudarle con la certificación de la configuración de LBR con la empresa de telefonía en el país.  

- Para admitir usuarios que trabajan desde fuera de la oficina para realizar llamadas RTC, la empresa emitió el teléfono móvil a sus empleados. 

En los siguientes diagramas se muestran las implementaciones antes y después de un país con normativas de telefonía que requieren enrutamiento basado en la ubicación:

**Implementación original**

![Diagrama que muestra antes del estado](media/voice-case-study-5.png)

**Implementación con enrutamiento directo**

![Diagrama que muestra antes del estado](media/voice-case-study-6.png)


## <a name="configuration"></a>Configuración 

Para configurar los componentes de red de Teams, contoso siguió las instrucciones de la [topología de red para características de voz en la nube](manage-your-network-topology.md). Contoso completó los pasos siguientes para configurar el enrutamiento basado en la ubicación: 

- Definir regiones de red: se definió una región de red. 

- Definir sitios de red: se definieron dos sitios de red. Un sitio por cada ubicación de oficina de la región.

- Definir subredes de la red: cada planta de una ubicación de la oficina tiene su propia subred para la red cableada y la inalámbrica. Esta configuración ha dado lugar a 20 subredes para contoso. 

- Definir direcciones IP fiables: las direcciones IP de dirección externa de la SBC se agregaron a la dirección IP de confianza.  

