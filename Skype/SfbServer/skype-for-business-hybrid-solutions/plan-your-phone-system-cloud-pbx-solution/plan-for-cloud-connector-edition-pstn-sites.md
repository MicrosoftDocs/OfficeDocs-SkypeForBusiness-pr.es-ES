---
title: Plan de sitios de RTC con Cloud Connector Edition
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/30/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: cec2d9bf-2deb-482c-841b-0e3599f94b50
description: Lea este tema para aprender a planear los sitios en la nube conector Edition RTC para garantizar el enrutamiento de llamadas rentable y eficiente.
ms.openlocfilehash: 4bf702314e46e1f8281ac6237dd8a7829900440e
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30897618"
---
# <a name="plan-for-cloud-connector-edition-pstn-sites"></a>Plan de sitios de RTC con Cloud Connector Edition
 
Lea este tema para aprender a planear los sitios en la nube conector Edition RTC para garantizar el enrutamiento de llamadas rentable y eficiente.
  
En este tema se describe lo que necesita saber acerca de la edición de conector en la nube y enrutamiento de modo que puede planear los sitios de RTC de conector en la nube de llamadas. Un sitio de RTC es una combinación de dispositivos de conector en la nube, implementado en la misma ubicación y con puertas de enlace RTC comunes conectados a ellos. En este tema se centra en cómo configurar la topología de sitio de conector en la nube para asegurarse de que los sitios de conector en la nube pueden controlar el enrutamiento de entrantes y salientes para todos los usuarios asignados a un sitio en la mayoría costo medio eficaz y eficiente posible. Para obtener más información acerca de conector en la nube y las ventajas de los sitios de RTC, asegúrese de leer [planeación de Skype para Business Edition de conector en la nube](plan-skype-for-business-cloud-connector-edition.md). 
  
## <a name="cloud-connector-pstn-sites-and-call-routing"></a>Sitios RTC con Cloud Connector y enrutamiento de llamadas

Los sitios de RTC de conector en la nube son una construcción de topología creada para evitar innecesario larga distancia y tarifas país entre granjas y asegurarse de que las llamadas salientes de emergencia se enrutan al tronco adecuado. Para garantizar el enrutamiento de llamadas, incluidas las llamadas a los servicios de emergencia, rentable y eficiente debe planear cuidadosamente los sitios de RTC y cómo los usuarios se asignan a cada sitio. 
  
Como parte de la planeación para el conector en la nube, es esencial que hable de los operadores donde se encuentran sus oficinas y los usuarios, y donde los troncos RTC terminar desde el operador de. Debe trabajar con los operadores para determinar cómo llamadas de emergencia se pueden redirigir y, a continuación, usar esa información para definir sitios de RTC de conector en la nube y asignar usuarios a los sitios apropiados. Por ejemplo, debe asegurarse de que los troncos que terminan en un centro de datos en el que se extiende el sitio RTC estén configurados para administrar tanto el enrutamiento de entrada como el de salida, para todos los números asignados a los usuarios en ese sitio. 
  
Cada dispositivo de conector de nube puede estar conectado a varias puertas de enlace IP, IP-PBX o controladores de borde de sesión (SBCs). Debido a que las puertas de enlace y PBX están conectadas a troncos de telecomunicaciones (troncos SIP o PRI), dispositivos de conector en la nube están conectados lógicamente a troncos RTC para las llamadas entrantes y salientes. Con el conector de la nube y la conectividad de RTC local, obtenga el tronco y el número de teléfono asociado de su operador de telefonía local. Si su compañía es una empresa grande, es posible que tenga más de un operador, en especial si su compañía se extiende a más de una ciudad, estado, país o región. Dado que el operador es propietario del número de teléfono, este es responsable de la administración de las llamadas de emergencia.
  
Skype para profesionales Online trata por igual a todos los dispositivos de conector en la nube en un sitio y va a enrutar las llamadas salientes en forma cíclica a dispositivos de conector en la nube en el mismo sitio. Cada conector en la nube en un sitio es cruzado conectado en el mismo conjunto de troncos RTC (totalmente entrelazados). Debido a que cada usuario está asociada con un sitio de RTC de conector en la nube, todas las llamadas salientes desde ese usuario (normal o de emergencia) se asignará a uno de los dispositivos de conector en la nube en el sitio de RTC que está asociado el usuario. 
  
Conector de la nube lo hace una llamada estática enrutamiento a su adjunto puertas de enlace IP, IP-PBX, SBCs o directas troncos RTC. Conector de nube todavía no es capaz de enrutamiento dinámico a un tronco en función de destino (para el enrutamiento de menor costo) o en función de origen (dinámico o estático llamadas de emergencia). Las llamadas entrantes no son un problema, ya que la llamada solo puede provenir de un tronco asociado a ese número. Sin embargo, las llamadas salientes, pueden ir a cualquier dispositivo de conector en la nube en un sitio (y por extensión los troncos RTC acoplados a ese equipo de conector en la nube) que puede causar que las llamadas de larga distancia no deseadas. Además, las llamadas de emergencia no se vaya a través de si el sitio de RTC de conector en la nube se extiende en centros de datos con distintos códigos de área o compañías aéreas.
  
## <a name="an-example"></a>Un ejemplo

En el ejemplo siguiente se muestra cómo agrupar los troncos de acceso a sitios de RTC y cómo asignar a usuarios a los sitios. Para la compañía Contoso, considere lo siguiente:
  
- Hay cuatro usuarios:  
    
  - Usuario A en Redmond, Washington (EE. UU.)
    
  - Usuario B en Bellevue, Washington (EE. UU.)
    
  - Usuario C en Centralia, Washington (EE. UU.)
    
  - Usuario D en Portland OR (Estados Unidos)
    
- Operador A proporciona los números de teléfono y troncos en:
    
  - Redmond (código de área 425)
    
  - Bellevue (código de área 425)
    
  - Centralia (código de área 360)
    
- Operador B proporciona los números de teléfono y troncos en:
    
  -  Portland (código de área 503)
    
Debido a que el usuario A en Redmond (centro de datos A) y el usuario B en Bellevue (centro de datos B) están en suburbios uno junto a otro y en el mismo código de área (425), un operador debería poder realizar una llamada de emergencia desde usuario A Redmond en el tronco en Bellevue. 
  
Por consiguiente, los usuarios A y B y los troncos de conector en la nube para Bellevue y Redmond, es probable que pueden en el mismo sitio de RTC de conector en la nube tal como se muestra en el siguiente diagrama. Las llamadas de emergencia de los usuarios en una oficina pueden ser redirigidas a los troncos en la otra. Sin embargo, debe, compruebe con su operador de telefonía que esto funcionará.
  
![Cómo configurar sitios PSTN](../../media/2659caa7-9c18-4d4f-9c7a-61d0e6a07dc3.png)
  
Considere también los ejemplos siguientes:
  
- El usuario C en Centralia, cuyo número es proporcionado por el operador A, está a un viaje en automóvil de dos horas y dentro de un código de área diferente (360) del de otros usuarios del operador A dentro del código de área 425 de Bellevue y Redmond.  
    
    Por lo tanto, incluso si una llamada se procedentes de un operador, es posible que llamada del operador software de enrutamiento en el código de área de Centralia 360 puede rechazar una emergencia entrante llamadas salientes desde el usuario B en el código de área de Bellevue 425. En este caso es fundamental que el operador de confirmar que conector en la nube y sus troncos asociados en los sitios de RTC de Centralia pueden controlar las llamadas a través de distancias y códigos de área.
    
- Usuario D en Portland utiliza un número y tronco proporcionado por el operador de B, por lo que es muy poco probable que portadora B tendrá una llamada de emergencia desde un número de teléfono es propiedad de operador A. Por lo que el usuario D y el dispositivo de conector en la nube y los troncos asociados en Portland tendrán que estar ubicada en un sitio diferente de RTC.
    

