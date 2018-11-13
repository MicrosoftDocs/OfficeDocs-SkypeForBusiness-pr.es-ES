---
title: Implementar varios sitios en Cloud Connector
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e62413fd-f68e-4825-8384-c983076bdf23
description: Obtenga información sobre la implementación de varios sitios de RTC en la nube conector Edition.
ms.openlocfilehash: b6d4c489136f038a5d4dbe7188958ef60e4a5aed
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2018
ms.locfileid: "26295716"
---
# <a name="deploy-multiple-sites-in-cloud-connector"></a>Implementar varios sitios en Cloud Connector
 
Obtenga información sobre la implementación de varios sitios de RTC en la nube conector Edition.
  
En esta sección se describe cómo implementar varios sitios de red telefónica conmutada (RTC). Los sitios se implementan de uno en uno siguiendo los mismos pasos que para la implementación de un único sitio. En este tema se describen las consideraciones para los sitios y las diferencias entre ellos en una implementación de varios sitios.  
  
## <a name="multiple-public-switched-telephone-network-pstn-sites"></a>Varios sitios de red telefónica conmutada (RTC)

A continuación muestra un ejemplo de configuración para implementar Skype para Business Edition de conector en la nube para distintos sitios de RTC. Asegúrese de que los parámetros de configuración sean correctos antes de comenzar con una implementación.
  
Sitio de RTC 1
  
```
[Common]
SiteName=Site1
[EdgeServer]
InternalMachineName= cc-edge1
InternalPoolName=cc-edgepool
InternalMachineIPs=192.168.0.241

ExternalSIPPoolName=access1
ExternalSIPIPs=192.168.1.4

ExternalMRFQDNPoolName=mr1
ExternalMRIPs=192.168.1.4
ExternalMRPublicIPs=23.99.115.35
```

Sitio de RTC 2
  
```
[Common]
SiteName=Site2
[EdgeServer]
InternalMachineName= cc-edge2
InternalPoolName=cc-edgepool
InternalMachineIPs=192.168.0.242

ExternalSIPPoolName=access2
ExternalSIPIPs=192.168.1.5

ExternalMRFQDNPoolName=mr2
ExternalMRIPs=192.168.1.5
ExternalMRPublicIPs=104.42.226.134
```

Para cada sitio de RTC que desee agregar, siga los pasos de [implementar un sitio de conector en la nube](deploy-a-single-site-in-cloud-connector.md).
  
> [!IMPORTANT]
> La carpeta compartida para preparar la alta disponibilidad (HA) es por cada sitio RTC. La carpeta compartida **debe** ser diferente en cada sitio RTC. No use la misma carpeta compartida para varios sitios. > 
  
## <a name="single-site-with-high-availability-ha-compared-to-multi-site-deployments"></a>Sitio único con alta disponibilidad (HA) comparado con implementaciones de varios sitios
<a name="BKMK_SingleSitecomparedtomulti-site"> </a>

En la siguiente tabla se muestran las diferencias entre un sitio único compatible con HA y una implementación de varios sitios.
  
|**Categoría**|**Elemento**|**Sitio único con HA**|**Varios sitios**|
|:-----|:-----|:-----|:-----|
|Configuración  <br/> |Carpeta compartida  <br/> |Requiere la **misma** carpeta compartida a través de dispositivos <br/> |Requiere una carpeta compartida **distinta** en cada dispositivo. <br/> |
|Configuración  <br/> |VirtualMachineDomain  <br/> |Requiere el **mismo** dominio en todos los dispositivos. <br/> |Requiere el **mismo** dominio en todos los sitios de RTC. <br/> |
|Configuración  <br/> |SIPDomains  <br/> |Orden y nombres de dominio deben ser el **mismo** a través de dispositivos <br/> |Orden y nombres de dominio deben ser el **mismo** en todos los sitios de RTC <br/> |
|Configuración  <br/> |Nombre del sitio  <br/> |Un nombre del sitio **igual** en todos los dispositivos. <br/> |Un nombre del sitio **diferente** en todos los sitios de RTC. <br/> |
|Configuración  <br/> |Nombres de servidores  <br/> |**Diferentes** en todos los dispositivos. <br/> |**Diferentes** en todos los sitios de RTC. <br/> |
|Configuración  <br/> |FQDN del grupo interno  <br/> |**Iguales** en todos los dispositivos. <br/> |**Iguales** en todos los sitios de RTC. <br/> |
|Configuración  <br/> |IP internas  <br/> |**Diferentes** en todos los dispositivos. <br/> |**Diferentes** en todos los sitios de RTC. <br/> |
|Configuración  <br/> |FQDN externo  <br/> |**Igual** en todos los dispositivos. <br/> |**Diferente** en todos los sitios de RTC. <br/> |
|Configuración  <br/> |IP externas  <br/> |**Diferentes** en todos los dispositivos. <br/> |**Diferentes** en todos los sitios de RTC. <br/> |
|Configuración  <br/> |Configuración de la puerta de enlace RTC  <br/> |**Igual** en todos los dispositivos. <br/> |**Diferente** en todos los sitios de RTC. <br/> |
|Configuración  <br/> |Registro DNS  <br/> |Agregar registros con el **mismo** FQDN externos de acceso y direcciones IP **diferentes** <br/> |Agregar registros con **diferentes** FQDN de acceso externo y **diferentes** direcciones IP <br/> |
|Configuración  <br/> |Inquilino híbrida  <br/> |Configurar HybridPSTNSite  <br/> Configurar PeerDestination para la reserva  <br/> |Configurar HybridPSTNSite  <br/> Configurar PeerDestination para la reserva  <br/> |
|Configuración  <br/> |Puerta de enlace  <br/> |Asignación de MS GW **M:N** en este sitio <br/> |Las puertas de enlace RTC en cada sitio RTC deben conectarse solamente a los servidores de mediación en el mismo sitio.  <br/> |
|Configuración  <br/> |Usuario  <br/> |Configurar UserPSTNSettings  <br/> |Configurar UserPSTNSettings  <br/> |
   

