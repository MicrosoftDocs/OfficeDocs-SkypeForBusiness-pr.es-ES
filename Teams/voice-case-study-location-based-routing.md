---
title: Caso práctico de Teams voice Contoso
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
description: Caso práctico de voz de Teams para una corporación multinacional
appliesto:
- Microsoft Teams
ms.openlocfilehash: f1ba92794b2ba17cc23e1bca55800c9307707636
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786073"
---
# <a name="contoso-case-study-location-based-routing"></a>Caso práctico Contoso: Location-Based de correo electrónico

Location-Based de destino (LBR) es una característica que restringe la omisión de pago en función de la directiva y la ubicación física del usuario al realizar o recibir una llamada.  

## <a name="overview"></a>Información general

Contoso tiene dos oficinas en un país donde es ilegal omitir el proveedor de red telefónica conmutada (RTC) para disminuir los costes de las llamadas de larga distancia. La oficina principal tiene una conexión a Internet que se usa en la oficina principal y en la segunda oficina. Cada oficina tiene su propio controlador de borde de sesión (SBC) conectado a un operador RTC.  
 
En este país, Contoso tenía LBR configurado para su implementación de Skype Empresarial. Para determinar cómo configurar LBR para Teams, lea Plan de [Location-Based de enrutamiento directo.](location-based-routing-plan.md) Contoso determinó que Teams y Skype Empresarial siguen los mismos escenarios en los que se puede realizar una llamada, cuando se puede recibir, cuando una llamada RTC se puede transferir a un usuario de Teams y cuando puede transferir otro usuario de Teams a la llamada RTC.  

Para Skype Empresarial, LBR se configuró con el tronco SIP del controlador de borde de sesión (SBC) conectado al operador RTC. Para este SBC, Contoso [](direct-routing-border-controllers.md) revisó la lista de SBC certificados y determinó que el SBC implementado está certificado para enrutamiento directo pero no está certificado para omisión de medios. To support LBR, Direct Routing needs to be configured to the SBC on-site, there needs to be a local Internet egress, and the SBC needs to be configured for Media Bypass. Basándose en esta información, Contoso decidió lo siguiente:

- Para retrasar la habilitación de Teams LBR hasta que el SBC existente esté certificado para la omisión de medios.   

- Contoso ha decidido usar el sitio principal SBC para la ruta directa a Office 365.  El sitio principal SBC será el SBC proxy para el sitio remoto.  

- Contoso usó un consultor de terceros con sede en India para ayudar con la certificación de la configuración LBR con la compañía de telefonía del país.  

- Para que los usuarios que trabajan fuera de la oficina puedan realizar llamadas RTC, se proporcionó a los empleados el teléfono móvil emitido por la empresa. 

En los siguientes diagramas se muestran las implementaciones de antes y después de un país con normativas de telefonía que requieren Location-Based distribución:

**Implementación original**

![Diagrama que se muestra antes del estado](media/voice-case-study-5.png)

**Implementación con enrutamiento directo**

![Diagrama que se muestra antes del estado](media/voice-case-study-6.png)


## <a name="configuration"></a>Configuración: 

Para configurar los componentes de red en Teams, Contoso ha seguido las instrucciones de Administración de la topología de red para [las características de voz en la nube.](manage-your-network-topology.md) Contoso completó los pasos siguientes para configurar el Location-Based electrónico: 

- Definir regiones de red: se definió una región de red. 

- Definir sitios de red: se definieron dos sitios de red. Un sitio por cada ubicación de oficina de la región.

- Definir subredes de red: cada planta de una ubicación de oficina tiene su propia subred para la red inalámbrica y cableada. Esta configuración ha dado como resultado 20 subredes para Contoso. 

- Definir direcciones IP de confianza: las direcciones IP externas para la SBC se agregaron a la dirección IP de confianza.  

