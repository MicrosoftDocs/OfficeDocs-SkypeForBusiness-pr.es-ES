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
ms.openlocfilehash: 3b4320e12a87c771e28fce445102327c7783a5d2
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358806"
---
# <a name="plan-for-cloud-connector-edition-pstn-sites"></a>Plan de sitios de RTC con Cloud Connector Edition

> [!Important]
> Cloud Connector Edition se retirará del 31 de julio de 2021 junto con Skype empresarial online. Una vez que la organización haya actualizado a Teams, obtenga información sobre cómo conectar la red de telefonía local a Microsoft Teams mediante el [enrutamiento directo](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).
 
Lea este tema para obtener información sobre cómo planear los sitios RTC de Cloud Connector Edition para garantizar un enrutamiento de llamadas eficaz y rentable.
  
En este tema se describe lo que debe saber sobre Cloud Connector Edition y el enrutamiento de llamadas para poder planear los sitios RTC de Cloud Connector. Un sitio RTC es una combinación de dispositivos de Cloud Connector, implementado en la misma ubicación y con puertas de enlace RTC comunes conectadas a ellos. Este tema se centra en cómo configurar la topología de sitio de Cloud Connector para garantizar que los sitios de Cloud Connector puedan controlar el enrutamiento de entrada y de salida para todos los usuarios asignados a un sitio de la forma más rentable y eficaz posible. Para obtener más información acerca de Cloud Connector y las ventajas de los sitios RTC, asegúrese de leer [Plan for Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md). 
  
## <a name="cloud-connector-pstn-sites-and-call-routing"></a>Sitios RTC y enrutamiento de llamadas de Cloud Connector

Los sitios RTC de Cloud Connector son una construcción de topología creada para evitar tarifas innecesarias de larga distancia y entre países, y para garantizar que las llamadas de emergencia salientes se enruten al tronco adecuado. Para garantizar un enrutamiento rentable y eficaz de las llamadas, incluidas las llamadas a los servicios de emergencia, debe planear cuidadosamente los sitios RTC y cómo se asignan los usuarios a cada sitio. 
  
Como parte de la planeación de Cloud Connector, es esencial que hable con sus Carriers sobre dónde están ubicados sus oficinas y usuarios, y dónde los troncos de RTC terminan desde el operador. Debe trabajar con los operadores para determinar cómo se pueden enrutar las llamadas de emergencia y, a continuación, usar esa información para definir los sitios RTC de Cloud Connector y asignar usuarios a los sitios apropiados. Por ejemplo, debe asegurarse de que los troncos que terminan en un centro de recursos en el que se expande el sitio RTC están configurados para controlar el enrutamiento entrante y saliente de todos los números asignados a los usuarios de ese sitio. 
  
Cada dispositivo de Cloud Connector puede conectarse a varias puertas de enlace IP, IP PBX o controladores de borde de sesión (SBCs). Debido a que las puertas de enlace y las PBX están conectadas a troncos de Telco (troncos de PRI o SIP), los equipos de Cloud Connector se conectan lógicamente a troncos RTC para llamadas entrantes y salientes. Con Cloud Connector y la conectividad con RTC local, se obtiene el tronco y los números de teléfono asociados del operador local. Si su empresa es una empresa grande, es posible que tenga más de una portadora, especialmente si su negocio abarca más de una ciudad, estado o país. Como su operador es propietario del número de teléfono, el operador es responsable del tratamiento de las llamadas de emergencia.
  
Skype empresarial online trata todos los dispositivos de Cloud Connector en un sitio por igual y enrutará las llamadas salientes de manera rotativa a los dispositivos de Cloud Connector en el mismo sitio. Cada conector de nube en un sitio está conectado al mismo conjunto de troncos RTC (completamente con malla). Como cada usuario está asociado a un sitio RTC de Cloud Connector, cualquier llamada saliente de ese usuario (normal o de emergencia) se asignará a uno de los dispositivos de Cloud Connector en el sitio RTC al que está asociado el usuario. 
  
Cloud Connector realiza un enrutamiento estático de llamadas a sus puertas de enlace IP conectadas, IP-PBX, SBC o troncos RTC directos. Cloud Connector todavía no es capaz de realizar el enrutamiento dinámico a un tronco en función del destino (para el enrutamiento de menor costo) o en función del origen (llamadas de emergencia estáticas o dinámicas). Las llamadas entrantes no son un problema, ya que la llamada solo puede provenir de un tronco asociado con el número. Sin embargo, las llamadas salientes pueden ir a cualquier dispositivo de Cloud Connector de un sitio (y por extensión de los troncos RTC conectados a ese dispositivo de Cloud Connector), lo que puede provocar llamadas de larga distancia no deseadas. Además, las llamadas de emergencia no pasarán si el sitio RTC de Cloud Connector se estira entre centros de recursos con diferentes códigos de área u operadores.
  
## <a name="an-example"></a>Un ejemplo

En el ejemplo siguiente se muestra cómo agrupar troncos en sitios RTC y cómo asignar usuarios a los sitios. Para contoso Company, asuma lo siguiente:
  
- Hay cuatro usuarios: 
    
  - Usuario A en Redmond WA (Estados Unidos)
    
  - Usuario B en Bellevue WA (Estados Unidos)
    
  - Usuario C en Centralia WA (Estados Unidos)
    
  - Usuario D en Portland o (EE.
    
- El operador A proporciona números de teléfono y troncos en:
    
  - Redmond (código de área 425)
    
  - Bellevue (código de área 425)
    
  - Centralia (código de área 360)
    
- El operador B proporciona números de teléfono y troncos en:
    
  -  Portland (código de área 503)
    
Como el usuario A en Redmond (centro de datos A) y el usuario B en Bellevue (centro de datos B) están en Suburbs junto a otros y en el mismo código de área (425), el operador A debe poder realizar una llamada de emergencia del usuario A en Redmond en el tronco de Bellevue. 
  
Por lo tanto, los usuarios A y B, y los troncos de Cloud Connector para Bellevue y Redmond, pueden estar en el mismo sitio RTC de Cloud Connector, tal y como se muestra en el siguiente diagrama. Las llamadas de emergencia de los usuarios de una oficina pueden enrutarse a troncos en el otro. Sin embargo, debe consultar a su portadora que funcionará.
  
![Cómo configurar sitios RTC](../../media/2659caa7-9c18-4d4f-9c7a-61d0e6a07dc3.png)
  
Tenga en cuenta también los siguientes ejemplos:
  
- El usuario C de Centralia, cuyo número lo proporciona el operador A, es una unidad de dos horas y en un código de área diferente (360), de otros usuarios de transporte en el código de área de Bellevue y Redmond 425. 
    
    Por lo tanto, incluso si una llamada procede del operador A, es posible que el software de enrutamiento de llamadas del transportista en el código de área 360 pueda rechazar una llamada de emergencia entrante originada por el usuario B en el código de área de Bellevue 425. En este caso, es esencial que el operador confirme que Cloud Connector y sus troncos asociados en los sitios RTC de Centralia pueden controlar las llamadas entre las distancias y los códigos de área.
    
- El usuario D en Portland utiliza un número y tronco proporcionados por el operador B, por lo que es muy improbable que la compañía B realice una llamada de emergencia desde un número de teléfono perteneciente al operador A. Por lo tanto, el usuario D y el dispositivo de Cloud Connector y los troncos asociados en Portland deberán estar ubicados en un sitio RTC diferente.
    

