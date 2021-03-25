---
title: Componentes de conectividad RTC en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6b2a3f7d-760f-4f09-8432-312c98a7e6b7
description: Obtenga información sobre el enlace troncal SIP y las puertas de enlace RTC Telefonía IP empresarial en Skype Empresarial Server.
ms.openlocfilehash: 402aa365556ef52d135c3ee6c0a2e36e9bd2e780
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51114626"
---
# <a name="pstn-connectivity-components-in-skype-for-business-server"></a>Componentes de conectividad RTC en Skype Empresarial Server
 
Obtenga información sobre el enlace troncal SIP y las puertas de enlace RTC Telefonía IP empresarial en Skype Empresarial Server.
  
Una solución de telefonía VoIP profesional debe proporcionar llamadas entrantes y realizadas a la red telefónica conmutada (RTC) sin que la calidad de servicio se vea afectada. Además, los usuarios no tienen por qué conocer la tecnología subyacente cuando realizan o reciben llamadas. Desde la perspectiva del usuario, una llamada entre la infraestructura de Enterprise Voice y la RTC debe parecer exactamente igual que otra sesión de SIP.
  
Para las conexiones RTC, puede implementar un tronco SIP o una puerta de enlace RTC (con una PBX, también conocida como vínculo SIP directo o sin PBX).
  
## <a name="sip-trunking"></a>Enlace troncal SIP

Como alternativa al uso de puertas de enlace RTC, puede conectar la solución de Enterprise Voice a la RTC usando el enlace troncal SIP. El enlace troncal SIP habilita los siguientes escenarios:
  
- Un usuario de la empresa dentro o fuera del firewall corporativo puede realizar una llamada local o de larga distancia especificada por un número conforme a E.164 con terminación en la RTC como un servicio del proveedor de servicios correspondiente.
    
- Cualquier suscriptor de RTC pueda ponerse en contacto con un usuario de la empresa dentro o fuera del firewall corporativo marcando un número de llamada directa a la extensión (DID) asociado a ese usuario de la empresa.
    
El uso de esta solución de implementación requiere un proveedor de servicios de enlace troncal SIP. 
  
## <a name="pstn-gateways"></a>Puertas de enlace RTC

Las puertas de enlace RTC son dispositivos de otro fabricante que convierten la señalización y los medios entre la infraestructura de Enterprise Voice y una red telefónica conmutada (RTC) o una central de conmutación (PBX). Las puertas de enlace RTC trabajan con el servidor de mediación para presentar una llamada de RTC o de PBX a un cliente de Enterprise Voice. El servidor de mediación también presenta llamadas de los clientes de Enterprise Voice a la puerta de enlace RTC para redirigir las llamadas a la RTC o a la PBX. Para obtener una lista de socios que trabajan con Microsoft para proporcionar dispositivos que funcionan con Skype Empresarial Server, vea el sitio web de  [Microsoft Unified Communications Partners](https://go.microsoft.com/fwlink/p/?linkId=202836). 
  
## <a name="private-branch-exchanges"></a>Centrales de conmutación

 Si tiene una infraestructura de voz existente que usa una central de conmutación (PBX), puede usar la PBX con Telefonía IP empresarial.
  
Los escenarios de integración de Enterprise Voice y PBX admitidos son los siguientes:
  
- IP-PBX que admite desvío de medios, con un servidor de mediación.
    
- IP-PBX que requiere una puerta de enlace de RTC independiente.
    
- PBX de multiplexación por división de tiempo (TDM), con una puerta de enlace de RTC independiente.
    
> [!NOTE]
> El desvío de medios no interactuará con todas las puertas de RTC, los sistemas IP-PBX y las SBC. Microsoft ha probado un conjunto de puertas de enlace RTC y SBC con socios certificados y ha realizado algunas pruebas con IP-PBX de Cisco. La omisión de medios solo se admite con productos y versiones enumerados en el Programa de interoperabilidad abierta de comunicaciones unificadas [- Lync Server](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md). 
  
Para obtener más información acerca de los partners que ofrecen Telefonía IP empresarial soluciones, consulte el sitio web de [Microsoft Unified Communications Partners](https://go.microsoft.com/fwlink/p/?linkId=202836).
  
Para obtener más información acerca de los partners que ofrecen Telefonía IP empresarial de hardware, incluidas las puertas de enlace RTC, consulte el sitio web de [Microsoft Unified Communications Partners](https://go.microsoft.com/fwlink/p/?linkId=202836).
