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
ms.custom: Strat_SB_Hybrid
ms.assetid: e62413fd-f68e-4825-8384-c983076bdf23
description: Obtenga información sobre cómo implementar varios sitios PSTN en nube conector Edition.
ms.openlocfilehash: 04af3ffa69a0ba452277d497544d4ba6708b5cb8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-multiple-sites-in-cloud-connector"></a>Implementar varios sitios en Cloud Connector
 
Obtenga información sobre cómo implementar varios sitios PSTN en nube conector Edition.
  
En esta sección se describe cómo implementar varios sitios de red telefónica conmutada (RTC). Los sitios se implementan de uno en uno siguiendo los mismos pasos que para la implementación de un único sitio. En este tema se describen las consideraciones para los sitios y las diferencias entre ellos en una implementación de varios sitios.  
  
## <a name="multiple-public-switched-telephone-network-pstn-sites"></a>Varios sitios de red telefónica conmutada (RTC)

A continuación muestra un ejemplo de configuración para implementar Skype para conector de nube Business Edition para distintos sitios PSTN. Asegúrese de que los parámetros de configuración sean correctos antes de comenzar con una implementación.
  
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

Sitio RTC 2
  
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

Para cada sitio PSTN que desee agregar, siga los pasos de [implementar un único sitio en el conector de la nube](deploy-a-single-site-in-cloud-connector.md).
  
> [!IMPORTANT]
> La carpeta compartida para preparar la alta disponibilidad (HA) es por cada sitio RTC. La carpeta compartida **debe** ser diferente en cada sitio RTC. No utilice la misma carpeta compartida para varios sitios. > 
  
## <a name="single-site-with-high-availability-ha-compared-to-multi-site-deployments"></a>Sitio único con alta disponibilidad (HA) comparado con implementaciones de varios sitios
<a name="BKMK_SingleSitecomparedtomulti-site"> </a>

En la siguiente tabla se muestran las diferencias entre un sitio único compatible con HA y una implementación de varios sitios.
  
|**Categoría**|**Elemento**|**Solo sitio con alta disponibilidad**|**Múltiples sitios**|
|:-----|:-----|:-----|:-----|
|Configuración  <br/> |Carpeta compartida  <br/> |Requiere la **misma** carpeta compartida a través de dispositivos <br/> |Requiere una carpeta compartida **distinta** en cada dispositivo. <br/> |
|Configuración  <br/> |VirtualMachineDomain  <br/> |Requiere el **mismo** dominio en todos los dispositivos. <br/> |Requiere el **mismo** dominio en todos los sitios de RTC. <br/> |
|Configurar  <br/> |SIPDomains  <br/> |Orden y nombres de dominio deben ser el **mismo** en todos dispositivos <br/> |Orden y nombres de dominio deben ser el **mismo** en todos los sitios PSTN <br/> |
|Configurar  <br/> |Nombre del sitio  <br/> |Un nombre del sitio **igual** en todos los dispositivos. <br/> |Un nombre del sitio **diferente** en todos los sitios de RTC. <br/> |
|Configurar  <br/> |Nombres de servidores  <br/> |**Diferentes** en todos los dispositivos. <br/> |**Diferentes** en todos los sitios de RTC. <br/> |
|Configurar  <br/> |FQDN del grupo interno  <br/> |**Iguales** en todos los dispositivos. <br/> |**Iguales** en todos los sitios de RTC. <br/> |
|Configurar  <br/> |IP internas  <br/> |**Diferentes** en todos los dispositivos. <br/> |**Diferentes** en todos los sitios de RTC. <br/> |
|Configurar  <br/> |FQDN externo  <br/> |**Igual** en todos los dispositivos. <br/> |**Diferente** en todos los sitios de RTC. <br/> |
|Configurar  <br/> |IP externas  <br/> |**Diferentes** en todos los dispositivos. <br/> |**Diferentes** en todos los sitios de RTC. <br/> |
|Configurar  <br/> |Configuración de la puerta de enlace RTC  <br/> |**Igual** en todos los dispositivos. <br/> |**Diferente** en todos los sitios de RTC. <br/> |
|Configurar  <br/> |Registro DNS  <br/> |Agregar registros con el **mismo** FQDN de acceso externo y direcciones IP **diferentes** <br/> |Agregar registros con **diferentes** FQDN de acceso externo y **diferentes** direcciones IP <br/> |
|Configuración  <br/> |Inquilinos híbrido  <br/> |Configurar HybridPSTNSite  <br/> Configurar PeerDestination para la reserva  <br/> |Configurar HybridPSTNSite  <br/> Configurar PeerDestination para la reserva  <br/> |
|Configuración  <br/> |Puerta de enlace  <br/> |Asignación de MS GW **M:N** en este sitio <br/> |Las puertas de enlace RTC en cada sitio RTC deben conectarse solamente a los servidores de mediación en el mismo sitio.  <br/> |
|Configuración  <br/> |Usuario  <br/> |Configurar UserPSTNSettings  <br/> |Configurar UserPSTNSettings  <br/> |
   

