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
description: Obtenga información sobre la implementación de varios sitios RTC en Cloud Connector Edition.
ms.openlocfilehash: 3c777c54690b1eb31671f71cff915f1bb4854a0d
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358926"
---
# <a name="deploy-multiple-sites-in-cloud-connector"></a>Implementar varios sitios en Cloud Connector

> [!Important] 
> Cloud Connector Edition se retirará del 31 de julio de 2021 junto con Skype empresarial online. Una vez que la organización haya actualizado a Teams, obtenga información sobre cómo conectar la red de telefonía local a Microsoft Teams mediante el [enrutamiento directo](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).

Obtenga información sobre la implementación de varios sitios RTC en Cloud Connector Edition.
  
En esta sección se describe cómo implementar varios sitios de red telefónica conmutada (RTC). Los sitios se implementan uno por vez con los mismos pasos que en la implementación de un único sitio. En este tema se describen las consideraciones y las diferencias entre los sitios en una implementación de varios sitios. 
  
## <a name="multiple-public-switched-telephone-network-pstn-sites"></a>Varios sitios de red telefónica conmutada (RTC)

A continuación se muestra un ejemplo de configuración para implementar Skype empresarial Cloud Connector Edition para diferentes sitios RTC. Asegúrese de que las opciones de configuración son correctas antes de iniciar una implementación.
  
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

Para cada sitio de RTC que quiera agregar, siga los pasos descritos en [deploy a Single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md).
  
> [!IMPORTANT]
> La carpeta compartida para preparar la alta disponibilidad (HA) es por cada sitio RTC. La carpeta compartida **debe** ser diferente entre los sitios RTC. No use la misma carpeta compartida para varios sitios. > 
  
## <a name="single-site-with-high-availability-ha-compared-to-multi-site-deployments"></a>Sitio único con alta disponibilidad (HA) comparado con implementaciones de varios sitios
<a name="BKMK_SingleSitecomparedtomulti-site"> </a>

En la siguiente tabla se enumeran las diferencias entre un sitio único con soporte de HA y una implementación de varios sitios.
  
|**Categoría**|**Elemento**|**Sitio único con HA**|**Varios sitios**|
|:-----|:-----|:-----|:-----|
|Configurar  <br/> |Nombre de host del dispositivo <br/> |**Diferente** en todos los dispositivos <br/> |**Diferente** en todos los sitios RTC <br/> |
|Instalación  <br/> |Carpeta compartida  <br/> |Requiere la **misma** carpeta compartida en todos los dispositivos. <br/> |Requiere una carpeta compartida **diferente** en los dispositivos <br/> |
|Configurar  <br/> |VirtualMachineDomain  <br/> |Requiere el **mismo** dominio en todos los dispositivos <br/> |Requiere el **mismo** dominio en todos los sitios RTC <br/> |
|Configurar  <br/> |SIPDomains  <br/> |Los nombres y el orden de los dominios deben ser los **mismos** en todos los dispositivos <br/> |Los nombres y el orden de los dominios deben ser los **mismos** en todos los sitios de RTC <br/> |
|Configurar  <br/> |Nombre del sitio  <br/> |**Misma** Nombre del sitio en todos los dispositivos <br/> |**Diferentes** Nombre del sitio en todos los sitios RTC <br/> |
|Configurar  <br/> |Nombres de servidor  <br/> |**Diferente** en todos los dispositivos <br/> |**Diferente** en todos los sitios RTC <br/> |
|Configurar  <br/> |FQDN de grupo interno  <br/> |**Igual** en todos los dispositivos <br/> |**Igual** en todos los sitios RTC <br/> |
|Configurar  <br/> |IP internas  <br/> |**Diferente** en todos los dispositivos <br/> |**Diferente** en todos los sitios RTC <br/> |
|Configurar  <br/> |FQDN externo  <br/> |**Igual** en todos los dispositivos <br/> |**Diferente** en todos los sitios RTC <br/> |
|Configurar  <br/> |IP externas  <br/> |**Diferente** en todos los dispositivos <br/> |**Diferente** en todos los sitios RTC <br/> |
|Configurar  <br/> |Configuración de RTC GW  <br/> |**Igual** en todos los dispositivos <br/> |**Diferente** en todos los sitios RTC <br/> |
|Configurar  <br/> |Registro DNS  <br/> |Agregar registros con los **mismos** FQDN de acceso externo y **diferentes** direcciones IP <br/> |Agregar registros con **diferentes** FQDN de acceso externo y **diferentes** direcciones IP <br/> |
|Instalación  <br/> |Inquilino híbrido  <br/> |Establecer HybridPSTNSite  <br/> Establecer PeerDestination para reserva  <br/> |Establecer HybridPSTNSite  <br/> Establecer PeerDestination para reserva  <br/> |
|Instalación  <br/> |Puerta de enlace  <br/> |Asignación **M:N** de MS GW en este sitio <br/> |Las puertas de enlace RTC en cada sitio RTC solo deben conectarse a los servidores de mediación en el mismo sitio.  <br/> |
|Instalación  <br/> |Usuario  <br/> |Establecer UserPSTNSettings  <br/> |Establecer UserPSTNSettings  <br/> |
   

