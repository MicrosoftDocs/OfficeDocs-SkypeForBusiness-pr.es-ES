---
title: Plan de sitios de RTC con Cloud Connector Edition
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/30/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: cec2d9bf-2deb-482c-841b-0e3599f94b50
description: Lea este tema para obtener información sobre cómo planear los sitios RTC de Cloud Connector Edition para garantizar un enrutamiento de llamadas eficaz y rentable.
ms.openlocfilehash: b42f9109a52b5c30996abc3e42ef4ff0aa5f31dc
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096234"
---
# <a name="plan-for-cloud-connector-edition-pstn-sites"></a>Plan de sitios de RTC con Cloud Connector Edition

> [!Important]
> Cloud Connector Edition se retirará el 31 de julio de 2021 junto con Skype Empresarial Online. Una vez que la organización haya actualizado a Teams, obtenga información sobre cómo conectar la red de telefonía local a Teams mediante [enrutamiento directo.](/MicrosoftTeams/direct-routing-landing-page)
 
Lea este tema para obtener información sobre cómo planear los sitios RTC de Cloud Connector Edition para garantizar un enrutamiento de llamadas eficaz y rentable.
  
En este tema se describe lo que necesita saber acerca de Cloud Connector Edition y el enrutamiento de llamadas para poder planear los sitios RTC de Cloud Connector. Un sitio RTC es una combinación de dispositivos de Cloud Connector, implementados en la misma ubicación y con puertas de enlace RTC comunes conectadas a ellos. Este tema se centra en cómo configurar la topología de sitio de Cloud Connector para garantizar que los sitios de Cloud Connector puedan controlar el enrutamiento entrante y saliente para todos los usuarios asignados a un sitio de la manera más rentable y eficaz posible. Para obtener más información acerca de Cloud Connector y las ventajas de los sitios RTC, asegúrese de leer [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md). 
  
## <a name="cloud-connector-pstn-sites-and-call-routing"></a>Sitios RTC de Cloud Connector y enrutamiento de llamadas

Los sitios RTC de Cloud Connector son una construcción de topología creada para evitar las tarifas innecesarias de larga distancia y entre países, y para garantizar que las llamadas de emergencia salientes se enruten al tronco adecuado. Para garantizar un enrutamiento rentable y eficaz de las llamadas, incluidas las llamadas a servicios de emergencia, debe planear cuidadosamente los sitios RTC y cómo se asignan los usuarios a cada sitio. 
  
Como parte de la planeación de Cloud Connector, es esencial que hable con los operadores sobre dónde se encuentran sus oficinas y usuarios y dónde finalizan los troncos RTC del operador. Debe trabajar con los operadores para determinar cómo se pueden enrutar las llamadas de emergencia y, a continuación, usar esa información para definir sitios RTC de Cloud Connector y asignar usuarios a los sitios adecuados. Por ejemplo, debe asegurarse de que los troncos que terminan en un centro de datos donde se extiende el sitio RTC estén configurados para controlar el enrutamiento entrante y saliente de todos los números asignados a los usuarios de ese sitio. 
  
Cada dispositivo de Cloud Connector se puede conectar a varias puertas de enlace IP, IP PBX o controladores de borde de sesión (SBC). Dado que las puertas de enlace y pbx están conectadas a troncos de telecomunicaciones (troncos PRI o SIP), los dispositivos de Cloud Connector están conectados lógicamente a troncos RTC para llamadas entrantes y salientes. Con Cloud Connector y la conectividad RTC local, obtiene el tronco y los números de teléfono asociados de su operador local. Si su empresa es una empresa grande, es posible que tenga más de un operador, especialmente si su negocio abarca más de una ciudad, estado o país. Dado que el operador es propietario del número de teléfono, el operador es responsable de administrar las llamadas de emergencia.
  
Skype Empresarial Online trata todos los dispositivos de Cloud Connector de un sitio por igual y enruta las llamadas salientes de forma rotativa a los dispositivos de Cloud Connector en el mismo sitio. Cada conector de nube de un sitio está conectado al mismo conjunto de troncos RTC (totalmente mallado). Dado que cada usuario está asociado a un sitio RTC de Cloud Connector, cualquier llamada saliente de ese usuario (normal o de emergencia) se asignará a uno de los dispositivos de Cloud Connector en el sitio RTC al que está asociado el usuario. 
  
Cloud Connector realiza el enrutamiento de llamadas estáticas a sus puertas de enlace IP adjuntas, IP-PBX, SBC o troncos RTC directos. Cloud Connector todavía no es capaz de enrutamiento dinámico a un tronco basado en el destino (para el enrutamiento de menor costo) o en función del origen (llamadas de emergencia estáticas o dinámicas). Las llamadas entrantes no son un problema, ya que la llamada solo puede venir de un tronco asociado al número. Sin embargo, las llamadas salientes pueden ir a cualquier dispositivo de Cloud Connector de un sitio (y, por extensión, los troncos RTC conectados a ese dispositivo de Cloud Connector) que pueden provocar llamadas de larga distancia no deseadas. Además, las llamadas de emergencia no pasarán si el sitio RTC de Cloud Connector se extiende entre centros de datos con diferentes códigos de área o portadores.
  
## <a name="an-example"></a>Un ejemplo

En el ejemplo siguiente se muestra cómo agrupar troncos a sitios RTC y cómo asignar usuarios a los sitios. Para la compañía Contoso, suponga lo siguiente:
  
- Hay cuatro usuarios: 
    
  - Usuario A en Redmond WA (ESTADOS UNIDOS)
    
  - Usuario B en Bellevue WA (ESTADOS UNIDOS)
    
  - Usuario C en Centralia WA (ESTADOS UNIDOS)
    
  - Usuario D en Portland OR (EE.UU.)
    
- El operador A proporciona números de teléfono y troncos en:
    
  - Redmond (código de área 425)
    
  - Bellevue (código de área 425)
    
  - Centralia (código de área 360)
    
- El operador B proporciona números de teléfono y troncos en:
    
  -  Portland (código de área 503)
    
Dado que el usuario A en Redmond (Centro de datos A) y el usuario B en Bellevue (Centro de datos B) están en los barrios periféricos juntos y en el mismo código de área (425), el operador A debe poder realizar una llamada de emergencia del usuario A en Redmond en el tronco de Bellevue. 
  
Por lo tanto, los usuarios A y B, y los troncos de Cloud Connector para Bellevue y Redmond, probablemente pueden estar en el mismo sitio RTC de Cloud Connector como se muestra en el diagrama siguiente. Las llamadas de emergencia de los usuarios de una oficina se pueden enrutar a troncos en la otra. Sin embargo, debe comprobar con su operador que esto funcionará.
  
![Cómo configurar sitios RTC](../../media/2659caa7-9c18-4d4f-9c7a-61d0e6a07dc3.png)
  
Tenga en cuenta también los siguientes ejemplos:
  
- El usuario C de Centralia, cuyo número es proporcionado por el operador A, está a dos horas en coche y en un código de área diferente (360), de otros usuarios de la portadora A en el código de área Bellevue y Redmond 425. 
    
    Por lo tanto, incluso si una llamada proviene del operador A, es posible que el software de enrutamiento de llamadas del operador en el código de área centralia 360 pueda rechazar una llamada de emergencia entrante originada por el usuario B en el código de área de Bellevue 425. En este caso, es fundamental que el operador confirme que Cloud Connector y sus troncos asociados en los sitios RTC de Centralia pueden controlar llamadas a través de distancias y códigos de área.
    
- El usuario D de Portland usa un número y un tronco proporcionados por el operador B, por lo que es muy poco probable que el operador B haga una llamada de emergencia desde un número de teléfono que sea propiedad del operador A. Por lo tanto, el usuario D y el dispositivo de Cloud Connector y los troncos asociados en Portland tendrán que estar ubicados en un sitio RTC diferente.
