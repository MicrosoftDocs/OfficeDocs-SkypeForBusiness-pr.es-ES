---
title: Plan de sitios de RTC con Cloud Connector Edition
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/30/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Hybrid
ms.assetid: cec2d9bf-2deb-482c-841b-0e3599f94b50
description: Lea este tema para aprender a planear sus sitios de nube conector Edition PSTN para garantizar el enrutamiento de llamadas eficaces y rentables.
ms.openlocfilehash: 70e5806ac6187d23b725f98ef288acaca7c03a54
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-cloud-connector-edition-pstn-sites"></a>Plan de sitios de RTC con Cloud Connector Edition
 
Lea este tema para aprender a planear sus sitios de nube conector Edition PSTN para garantizar el enrutamiento de llamadas eficaces y rentables.
  
Este tema describe lo que necesita saber acerca de la edición de conector de nube y llamar a enrutamiento de manera que puede planear sus sitios de nube conector PSTN. Un sitio de RTC es una combinación de dispositivos de conector de nube, implementado en la misma ubicación y con puertas de enlace PSTN comunes conectados a ellos. En este tema se centra en cómo configurar la topología de sitio de conector de nube para asegurarse de que los sitios de conector de nube pueden controlar el enrutamiento entrante y saliente para todos los usuarios asignados a un sitio en la mayoría costo medio eficaz y eficiente posible. Para obtener más información sobre el conector de la nube y las ventajas de sitios PSTN, asegúrese de leer el [Plan de Skype para conector de nube Business Edition](plan-skype-for-business-cloud-connector-edition.md). 
  
## <a name="cloud-connector-pstn-sites-and-call-routing"></a>Sitios RTC con Cloud Connector y enrutamiento de llamadas

Sitios de conector PSTN de nube son una construcción de topología creada para evitar innecesario larga distancia y los aranceles entre países y para garantizar que se enrutan llamadas salientes de emergencia al tronco apropiado. Para garantizar el enrutamiento rentable y efectivo de las llamadas, incluidas las llamadas a servicios de emergencia, debe planificar cuidadosamente los sitios RTC y el modo en que se asignan los usuarios a cada sitio. 
  
Como parte de la planificación de Cloud Connector, es fundamental que comunique a los operadores dónde se encuentran las oficinas y los usuarios, y el lugar donde terminan los troncos RTC del operador. Debe trabajar con los transportistas para determinar cómo llamadas de emergencia se pueden enrutar y, a continuación, utilizar esa información para definir sitios de nube conector PSTN y asignar usuarios a los sitios apropiados. Por ejemplo, debe asegurarse de que los troncos que terminan en un centro de datos en el que se extiende el sitio RTC estén configurados para administrar tanto el enrutamiento de entrada como el de salida, para todos los números asignados a los usuarios en ese sitio. 
  
Cada dispositivo de nube conector puede estar conectado a varias puertas de enlace IP, IP PBX o controladores de borde de sesión (SBCs). Porque los Gateways and PBXs están conectados a los troncos de telecomunicaciones (PRI o SIP troncos), equipos de nube conector estén conectados lógicamente a troncos PSTN para llamadas entrantes y salientes. Con Cloud Connector y la conectividad con RTC local, se obtiene el tronco y los números de teléfono asociados del operador local. Si su compañía es una empresa grande, es posible que tenga más de un operador, en especial si su compañía se extiende a más de una ciudad, estado, país o región. Dado que el operador es propietario del número de teléfono, este es responsable de la administración de las llamadas de emergencia.
  
Skype para los negocios en línea trata por igual todos los dispositivos de conector de nube en un sitio y usará para enrutar las llamadas salientes de forma rotativa a dispositivos de conector de nube en el mismo sitio. Cada Cloud Connector en un sitio está interconectado al mismo conjunto de troncos RTC (completamente en malla). Dado que cada usuario está asociado a un sitio de nube conector PSTN, todas las llamadas salientes desde ese usuario (normal o de emergencia) se asignará a uno de los dispositivos de la nube de conector en el sitio PSTN que está asociado el usuario. 
  
Cloud Connector realiza el enrutamiento estático de llamadas a sus puertas de enlace IP asociadas, las IP-PBX, los SBC o los troncos RTC directos. Cloud Connector aún no tiene la capacidad de realizar el enrutamiento dinámico a un tronco en base al destino (para el enrutamiento de menor coste) o en base al origen (llamadas de emergencia estáticas o dinámicas). Las llamadas entrantes no son un problema, ya que la llamada solo puede provenir de un tronco asociado a ese número. Llamadas salientes, sin embargo, pueden ir a cualquier dispositivo conector de nube en un sitio (y por extensión los troncos PSTN conectados a ese dispositivo conector de nube) que pueden causar las llamadas de larga distancia no deseadas. Además, las llamadas de emergencia no atravesará si se extiende el sitio nube conector PSTN en centros de datos con distintos códigos de área o compañías aéreas.
  
## <a name="an-example"></a>Un ejemplo

En el ejemplo siguiente se muestra cómo agrupar los troncos de acceso a sitios PSTN y cómo asignar a los usuarios a los sitios. Para la compañía Contoso, considere lo siguiente:
  
- Hay cuatro usuarios:   
    
  - Usuario A en Redmond, Washington (EE. UU.)
    
  - Usuario B en Bellevue, Washington (EE. UU.)
    
  - Usuario C en Centralia, Washington (EE. UU.)
    
  - Usuario D en Portland, Oregón (EE.)
    
- Transportista A proporciona números de teléfono y troncos en:
    
  - Redmond (código de área 425)
    
  - Bellevue (código de área 425)
    
  - Centralia (código de área 360)
    
- Transportista B proporciona números de teléfono y troncos en:
    
  -  Portland (código de área 503)
    
Como el usuario A en Redmond y el usuario B en Bellevue están en la periferia, uno al lado del otro y dentro del mismo código de área (425), el operador A debe tener la capacidad de tomar una llamada de emergencia del usuario A en Redmond en el tronco de Bellevue.   
  
En consecuencia, los usuarios A y B y los troncos de conector de nube para Bellevue y Redmond, probablemente puede en el mismo sitio PSTN como se muestra en el siguiente diagrama. Las llamadas de emergencia de los usuarios en una oficina pueden ser redirigidas a los troncos en la otra. Sin embargo, debe comprobar con la portadora que esto funcionará.
  
![Cómo configurar sitios PSTN](../../media/2659caa7-9c18-4d4f-9c7a-61d0e6a07dc3.png)
  
Considere también los ejemplos siguientes:
  
- El usuario C en Centralia, cuyo número es proporcionado por el operador A, está a un viaje en automóvil de dos horas y dentro de un código de área diferente (360) del de otros usuarios del operador A dentro del código de área 425 de Bellevue y Redmond.  
    
    Por lo tanto, incluso si una llamada está saliendo del transportista A, es posible que la llamada del transportista software de enrutamiento en el código de área de Centralia 360 puede rechazar una emergencia entrante llamar procedentes de usuario B en el código de área de Bellevue 425. En este caso es fundamental que el transportista confirme que conector de nube y sus troncos asociados en los sitios de Centralia PSTN pueden controlar las llamadas a través de distancias y códigos de área.
    
- Usuario D de Portland utiliza un número y tronco proporcionado por el transportista B, por lo que es muy improbable que transportista B tendrá una llamada desde un número de teléfono de emergencia es propiedad de transportista A. Modo usuario D y el dispositivo conector de nube y troncos asociados en Guadalajara tendrá que estar ubicado en un sitio diferente de RTC.
    

