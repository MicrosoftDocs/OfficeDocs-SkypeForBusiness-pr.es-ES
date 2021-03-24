---
title: Implementar varios sitios en Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e62413fd-f68e-4825-8384-c983076bdf23
description: Obtenga información sobre cómo implementar varios sitios RTC en Cloud Connector Edition.
ms.openlocfilehash: 059b9a39a082e876b1dd9cd772a235c384a29107
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098406"
---
# <a name="deploy-multiple-sites-in-cloud-connector"></a>Implementar varios sitios en Cloud Connector

> [!Important] 
> Cloud Connector Edition se retirará el 31 de julio de 2021 junto con Skype Empresarial Online. Una vez que la organización haya actualizado a Teams, obtenga información sobre cómo conectar la red de telefonía local a Teams mediante [enrutamiento directo.](/MicrosoftTeams/direct-routing-landing-page)

Obtenga información sobre cómo implementar varios sitios RTC en Cloud Connector Edition.
  
En esta sección se describe cómo implementar varios sitios de red telefónica conmutada (RTC). Los sitios se implementan de uno en uno con los mismos pasos que la implementación de un solo sitio. En este tema se describen las consideraciones y las diferencias entre los sitios de una implementación de varios sitios. 
  
## <a name="multiple-public-switched-telephone-network-pstn-sites"></a>Varios sitios de red telefónica conmutada (RTC)

A continuación se muestra un ejemplo de configuración para implementar Skype Empresarial Cloud Connector Edition para diferentes sitios RTC. Asegúrese de que las opciones de configuración son correctas antes de iniciar una implementación.
  
Sitio RTC 1
  
```console
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
  
```console
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

Para cada sitio RTC que desee agregar, siga los pasos descritos en [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md).
  
> [!IMPORTANT]
> La carpeta compartida para preparar la alta disponibilidad (HA) es por sitio RTC. La carpeta compartida **debe ser** diferente entre sitios RTC. No use la misma carpeta compartida para varios sites.> 
  
## <a name="single-site-with-high-availability-ha-compared-to-multi-site-deployments"></a>Sitio único con alta disponibilidad (HA) en comparación con las implementaciones de varios sitios
<a name="BKMK_SingleSitecomparedtomulti-site"> </a>

En la tabla siguiente se enumeran las diferencias entre un solo sitio con compatibilidad con HA y una implementación de varios sitios.
  
|**Categoría**|**Elemento**|**Sitio único con HA**|**Multi-Site**|
|:-----|:-----|:-----|:-----|
|Configurar  <br/> |Nombre de host del dispositivo <br/> |**Diferentes** entre dispositivos <br/> |**Diferente** entre sitios RTC <br/> |
|Configuración  <br/> |Carpeta compartida  <br/> |Requiere la **misma carpeta** compartida en todos los dispositivos <br/> |Requiere una **carpeta** compartida diferente en todos los dispositivos <br/> |
|Configurar  <br/> |VirtualMachineDomain  <br/> |Requiere el **mismo dominio** en todos los dispositivos <br/> |Requiere el **mismo dominio** entre sitios RTC <br/> |
|Configurar  <br/> |SIPDomains  <br/> |Los nombres de dominio y el orden deben ser **los mismos en** todos los dispositivos <br/> |Los nombres de dominio y el orden deben ser **los mismos** en los sitios RTC <br/> |
|Configurar  <br/> |Nombre del sitio  <br/> |**Igual** Nombre del sitio en todos los dispositivos <br/> |**Diferente** Nombre de sitio en sitios RTC <br/> |
|Configurar  <br/> |Nombres de servidor  <br/> |**Diferentes** entre dispositivos <br/> |**Diferente** entre sitios RTC <br/> |
|Configurar  <br/> |FQDN de grupo interno  <br/> |**Igual en** todos los dispositivos <br/> |**Lo mismo** en los sitios RTC <br/> |
|Configurar  <br/> |IP internas  <br/> |**Diferentes** entre dispositivos <br/> |**Diferente** entre sitios RTC <br/> |
|Configurar  <br/> |FQDN externo  <br/> |**Igual en** todos los dispositivos <br/> |**Diferente** entre sitios RTC <br/> |
|Configurar  <br/> |IP externas  <br/> |**Diferentes** entre dispositivos <br/> |**Diferente** entre sitios RTC <br/> |
|Configurar  <br/> |Configuración de RTC GW  <br/> |**Igual en** todos los dispositivos <br/> |**Diferente** entre sitios RTC <br/> |
|Configurar  <br/> |Registro DNS  <br/> |Agregar registros con los **mismos** FQDN de acceso externo y **diferentes direcciones** IP <br/> |Agregar registros con **diferentes** FQDN de acceso externo y **distintas** direcciones IP <br/> |
|Configuración  <br/> |Inquilino híbrido  <br/> |Establecer HybridPSTNSite  <br/> Establecer PeerDestination para reserva  <br/> |Establecer HybridPSTNSite  <br/> Establecer PeerDestination para reserva  <br/> |
|Configuración  <br/> |Puerta de enlace  <br/> |Asignación **MS GW M:N** en este sitio <br/> |Las puertas de enlace RTC en cada sitio RTC solo deben conectarse a los servidores de mediación del mismo sitio  <br/> |
|Configuración  <br/> |Usuario  <br/> |Establecer UserPSTNSettings  <br/> |Establecer UserPSTNSettings  <br/> |
