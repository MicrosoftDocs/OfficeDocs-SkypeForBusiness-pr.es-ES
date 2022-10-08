---
title: Controladores de límites de sesión certificados para Enrutamiento directo
ms.author: crowe
ms.reviewer: FilippSe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.localizationpriority: high
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
hideEdit: true
f1.keywords:
- NOCSH
description: Sepa qué controladores de borde de sesión (SBC) fueron certificados para el Enrutamiento directo.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ac539938c21f500b4718a37aa970f1e5d6309202
ms.sourcegitcommit: 1be178dc3b34575e1914e629f004f897c02e0097
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/28/2022
ms.locfileid: "68138513"
---
# <a name="session-border-controllers-certified-for-direct-routing"></a>Controladores de borde de sesión certificados para Enrutamiento directo

Microsoft se asocia con proveedores de controladores de borde de sesión (SBC) seleccionados para certificar que sus SBC pueden usarse con el Enrutamiento directo.

Microsoft trabaja con cada proveedor para:

- Trabajar conjuntamente en los protocolos de interconexión SIP.
- Realizar pruebas intensivas mediante un laboratorio de terceros. Solo se certifican los dispositivos que superen las pruebas.
- Ejecutar pruebas a diario con todos los dispositivos certificados en entornos de producción y previos a la producción. Validar los dispositivos en entornos previos a la fase de producción garantiza que las nuevas versiones del código de Enrutamiento directo en la nube funcione con los CLS certificados;
- Establecer un proceso de soporte conjunto con los proveedores de CLS.

  > [!NOTE]
  > Microsoft solo admite un sistema telefónico con enrutamiento directo cuando se usa con dispositivos certificados. En caso de problemas, debe ponerse en contacto con el servicio de atención al cliente del proveedor de SBC  Si es necesario, el proveedor de CLS remitirá el problema a Microsoft a través de canales internos. Microsoft se reserva el derecho a rechazar casos de soporte técnico de dispositivos no certificados conectados al Sistema telefónico a través del Enrutamiento directo. Si Microsoft determina que el problema de Enrutamiento directo de un cliente está relacionado con el dispositivo de un proveedor de CLS, el cliente deberá ponerse en contacto con el proveedor de CLS para obtener soporte técnico.
  >
  > La certificación se concede a versiones de firmware CLS específicas. Cualquier versión de firmware CLS documentada a continuación está certificada y admitida. Se admiten versiones de firmware superiores a las documentadas siempre que la versión principal secundaria sea la misma.
  >
  > Ejemplo:
  >
  > - Compatible con 6.10.258: en este caso, Microsoft admite las versiones de firmware 6.10. (258 o superior).
  > - Recomendado 6.20.100: en este caso, Microsoft recomienda las versiones de firmware 6.20. (100 o superior).
  > - Si tiene preguntas de compatibilidad sobre una versión específica, póngase en contacto con su proveedor de CLS.

En las tablas siguientes se enumeran los dispositivos certificados para Enrutamiento directo. (Para obtener información sobre qué proveedores de CLS admiten la optimización de medios locales, vea [Configurar la optimización de medios locales para el enrutamiento directo](direct-routing-media-optimization-configure.md)).

[Obtenga más información sobre el Enrutamiento directo](https://aka.ms/dr).

Tenga en cuenta que no aceptamos nuevas nominaciones para la certificación hasta nuevo aviso.

## <a name="certified-sbc-vendors"></a>Proveedores de CLS certificados

|Proveedor|Producto|Omisión de los que no son medios|Omisión de medios|Versión de software|Compatible con el proveedor de servicios 911*|Compatible con ELIN|
|---|---|---|---|---|---|---|
|[AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)|SBC Mediant 500|&#10004;|&#10004;|Compatible con 7.20A.258 (recomendado 7.40A.100 o 7.40A.250)|&#10004;|&#10004;|
||SBC Mediant 800|&#10004;|&#10004;|Compatible con 7.20A.258 (recomendado 7.40A.100 o 7.40A.250)|&#10004;|&#10004;|
||SBC Mediant 2600|&#10004;|&#10004;|Compatible con 7.20A.258 (recomendado 7.40A.100 o 7.40A.250)|&#10004;|&#10004;|
||SBC Mediant 4000|&#10004;|&#10004;|Compatible con 7.20A.258 (recomendado 7.40A.100 o 7.40A.250)|&#10004;|&#10004;|
||SBC Mediant 1000B|&#10004;|&#10004;|Compatible con 7.20A.250 (recomendado 7.40A.100 o 7.40A.250)|&#10004;|&#10004;|
||SBC Mediant 9000|&#10004;|&#10004;|Compatible con 7.20A.258 (recomendado 7.40A.100 o 7.40A.250)|&#10004;|&#10004;|
||SBC Virtual Edition|&#10004;|&#10004;|Compatible con 7.20A.258 (recomendado 7.40A.100 o 7.40A.250)|&#10004;|&#10004;|
||SBC de Mediant Cloud Edition|&#10004;|&#10004;|Compatible con 7.20A.258 (recomendado 7.40A.100 o 7.40A.250)|&#10004;|&#10004;|
|[Comunicaciones de cinta](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-skype-business)|SBC 5100/5110|&#10004;|&#10004;|Compatible con todas las versiones de 10.1, 9.2, 8.2 y 7.2 (recomendamos la última versión de 10.1)|&#10004;||
||SBC 5200/5210|&#10004;|&#10004;|Compatible con todas las versiones de 10.1, 9.2, 8.2 y 7.2 (recomendamos la última versión de 10.1)|&#10004;||
||SBC 5400|&#10004;|&#10004;|Compatible con todas las versiones de 10.1, 9.2, 8.2 y 7.2 (recomendamos la última versión de 10.1))|&#10004;||
||SBC 7000|&#10004;|&#10004;|Compatible con todas las versiones de 10.1, 9.2, 8.2 y 7.2 (recomendamos la última versión de 10.1)|&#10004;||
||Todas las variantes SBC SWe, incluidas las ofertas hospedadas|&#10004;|&#10004;|Compatible con todas las versiones de 10.1, 9.2, 8.2 y 7.2 (recomendamos la última versión de 10.1)|&#10004;||
||SBC 1000|&#10004;|&#10004;|8.x or 9.x|&#10004;|&#10004;|
||SBC 2000|&#10004;|&#10004;|8.x or 9.x|&#10004;|&#10004;|
||SBC SWe Lite|&#10004;|&#10004;|8.x or 9.x|&#10004;|&#10004;|
||Serie EdgeMarc|&#10004;|&#10004;|16.3.2||
|[Thinktel](https://www.thinktel.ca/services/think-365/think-365-overview/)|SBC Think 365|&#10004;||1.4|||
|[Oracle](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)|AP 1100|&#10004;|&#10004;|Compatible con 8.3.0.0.1 y recomendada 8.4.x y 9.x|&#10004;|&#10004;|
||AP 3900|&#10004;|&#10004;|Compatible con 8.3.0.0.1 y recomendada 8.4.x y 9.x|&#10004;|&#10004;|
||AP 4600|&#10004;|&#10004;|Compatible con 8.3.0.0.1 y recomendada 8.4.x y 9.x|&#10004;|&#10004;|
||AP 6300|&#10004;|&#10004;|Compatible con 8.3.0.0.1 y recomendada 8.4.x y 9.x|&#10004;|&#10004;|
||AP 6350|&#10004;|&#10004;|Compatible con 8.3.0.0.1 y recomendada 8.4.x y 9.x|&#10004;|&#10004;|
||VME|&#10004;|&#10004;|Compatible con 8.3.0.0.1 y recomendada 8.4.x y 9.x|&#10004;|&#10004;|
||AP 3950|&#10004;|&#10004;|Compatible con 9.x|&#10004;|&#10004;|
||AP 4900|&#10004;|&#10004;|Compatible con 9.x|&#10004;|&#10004;|
|[TE-SYSTEMS](https://www.anynode.de/anynode-and-microsoft-teams/)|anynode|&#10004;|&#10004;|Compatible con 3.20 (recomendado 4.0)|&#10004;|&#10004;|
|[Metaswitch](https://www.metaswitch.com/products/core-network/perimeta-sbc)|SBC Perimeta|&#10004;|&#10004;|4.7 (4.9 para omisión de medios)|&#10004;|&#10004;|
|[Cisco](https://www.cisco.com/c/en/us/solutions/enterprise/interoperability-portal/networking_solutions_products_genericcontent0900aecd805bd13d.html)|Elemento de borde unificado de Cisco (CUBE) para enrutadores de servicios integrados de la serie 1000|&#10004;|&#10004;|IOS XE Ámsterdam 17.2.1r compatible (recomendado 17.6.1a)|&#10004;||
||Elemento de borde unificado de Cisco (CUBE) para enrutadores de servicios integrados de la serie 4000|&#10004;|&#10004;|IOS XE Ámsterdam 17.2.1r compatible (recomendado 17.6.1a)|&#10004;||
||Elemento de borde unificado de Cisco (CUBE) para enrutador de servicios en la nube serie 1000V|&#10004;|&#10004;|IOS XE Ámsterdam 17.2.1r compatible (recomendado 17.3.3)|&#10004;||
||Elemento de borde unificado de Cisco (CUBE) para enrutadores de servicios de agregación de la serie 1000|&#10004;|&#10004;|IOS XE Ámsterdam 17.2.1r compatible (recomendado 17.6.1a)|&#10004;||
||Elemento de borde unificado de Cisco (CUBE) para plataformas perimetrales de Catalyst 8000|&#10004;|&#10004;|IOS XE Ámsterdam 17.3.2 compatible (recomendado 17.6.1a)|&#10004;||
|[Avaya](https://support.avaya.com/products/P0997/avaya-session-border-controller-for-enterprise/8.1.x)|Controlador de límites de sesión de Avaya para empresas (ASBCE)|&#10004;|&#10004;|Versión 8.1.1 (8.1.2 para omisión de medios)|||
|[Nokia](https://documentation.nokia.com/aces/cgi-bin/chk_access.cgi/3TB30222GBAAACZZA.zip)|Controlador de límites de sesión Nokia|&#10004;|&#10004;|22.0|&#10004;||
|[Italtel](https://www.italtel.com/italtel-provides-direct-routing-sbc-for-microsoft-teams/)|NetMatch-S CI|&#10004;|&#10004;|Compatible con 5.0 y 5.1 (recomendado 5.3)|||
|[Ericsson](https://www.ericsson.com/en/portfolio/digital-services/cloud-communication/enterprise-communication/business-communication-services-and-enablers/sip-trunking)|vSBC 2.16|&#10004;|||||
|[Cataleya](https://cataleya.com/orchidplatforms/)|Vínculo de Orchid|&#10004;||3.1|||
|[ULTATEL](https://www.ultatel.com/services/direct-routing-teams-sbc)|CLS de Teams|&#10004;|&#10004;|1.6|||
|[Atos](https://unify.com/en/solutions/voice-platforms/session-border-controller)|Controlador de límites de sesión de Atos Unify OpenScape|&#10004;|&#10004;|V10R2.2.0|||
|[Sansay Inc.](https://www.sansay.com/solutions/microsoft-teams/)|vmVSXi|&#10004;|&#10004;|10.5.1.354-vm-S-x64|&#10004;||
|[Enghouse Networks](https://www.enghousenetworks.com/portfolio/network-infrastructure/cloud-native-session-border-controller-sbc/)|CLS de BorderNet Dialogic|&#10004;|&#10004;|3.9.0-786|||
|[Patton Electronics Co.](https://www.patton.com/microsoft/)|Patton SmartNode eSBC|&#10004;||3.19.x|||
|[M5 Technologies (anteriormente conocido como Media5 Corporation)](https://www.m5t.com/solutions/sentinel-sbc-ms-teams-certified/)|Serie Sentinel de Mediatrix|&#10004;||DGW 48.0.2340 (DGW recomendado 48.1.2503)|||
|[Ekinops](https://www.ekinops.com/solutions/voice-data-access/microsoft-direct-routing-sbc)|Ekinops Session Border Controller (ONeSBC)|&#10004;|&#10004;|Compatible con 6.6.1m5ha1 (recomendada 6.8.x)|||
||Ekinops Virtual Session Border Controller (ONEvSBC)|&#10004;|&#10004;|Compatible con 6.6.1m5ha1 (recomendada 6.8.x)|||
|[46 Labs LLC](https://46labs.atlassian.net/wiki/spaces/peeredge/pages/61603842/Microsoft+Teams+Implementation+Guide+v1.0)|Peeredge Orchestrator|&#10004;|&#10004;|1.0.6|||
|[Frafos](https://www.frafos.com/ms-teams-abc-sbc)|ABC SBC|&#10004;||4.6|||

<br/>

\* **Proveedores de servicios 911**

- [Enrutamiento de ubicación dinámica de ancho de banda](https://www.bandwidth.com/partners/microsoft-teams-direct-routing/)
- [Servicio de enrutamiento de emergencia Intrado (ERS)](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)
- [Puerta de enlace de emergencia Intrado (EGW)](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)
- [Inteliquent](https://www.inteliquent.com/services/emergency-services/e911)

## <a name="support-for-local-media-optimization"></a>Soporte para la optimización de medios locales

En la tabla siguiente se describe qué proveedores de SBC admiten la [Optimización multimedia local](direct-routing-media-optimization.md).

|Proveedor|Producto|Versión de software|
|:---|:---|:---|
|[AudioCodes](https://www.audiocodes.com/media/13253/connecting-audiocodes-sbc-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf)|SBC Mediant 500|7.20A.256|
||SBC Mediant 800|Compatible con 7.20A.258 (recomendado 7.40A.100)|
||SBC Mediant 2600|Compatible con 7.20A.258 (recomendado 7.40A.100)|
||SBC Mediant 4000|Compatible con 7.20A.258 (recomendado 7.40A.100)|
||SBC Mediant 1000B|Compatible con 7.20A.258 (recomendado 7.40A.100)|
||SBC Mediant 9000|Compatible con 7.20A.258 (recomendado 7.40A.100)|
||SBC de Mediant Virtual Edition|Compatible con 7.20A.258 (recomendado 7.40A.100)|
||SBC de Mediant Cloud Edition|Compatible con 7.20A.258 (recomendado 7.40A.100)|
|[Cinta de SBC Core](https://support.sonus.net/display/ALLDOC/SBC+8.2+-+Configure+Local+Media+Optimization)|SBC 5110|8.2|
||SBC 5210|8.2|
||SBC 5400|8.2|
||SBC 7000|8.2|
||SBC SWe|8.2|
|[Cinta de SBC Edge](https://support.sonus.net/display/UXDOC81/Best+Practice+-+Configuring+Microsoft+Teams+Local+Media+Optimization)|SBC SWe Lite|8.1.5|
||SBC 1000|8.1.5|
||SBC 2000|8.1.5|
|[TE-SYSTEMS](https://www.anynode.de/local_media_optimization/)|anynode|4.0.1+|
|[Oracle](https://www.oracle.com/industries/communications/enterprise-communications/session-border-controller/microsoft.html)|AP 1100|8.4.0.0.0|
||AP 3900|8.4.0.0.1 y 9.x|
||AP 4600|8.4.0.0.1 y 9.x|
||AP 6300|8.4.0.0.1 y 9.x|
||AP 6350|8.4.0.0.1 y 9.x|
||VME|8.4.0.0.1 y 9.x|
||AP 3950|9.x|
||AP 4900|9.x|
|[Avaya](https://support.avaya.com/products/P0997/avaya-session-border-controller-for-enterprise/8.1.x)|Controlador de límites de sesión de Avaya para empresas (ASBCE)|10.1.2|

## <a name="direct-routing-and-analog-devices-interoperability"></a>Enrutamiento directo e interoperabilidad de dispositivos analógicos

En la tabla siguiente se enumeran los dispositivos que se comprueban para la interoperabilidad entre el Enrutamiento directo y los dispositivos analógicos.

|Proveedor|Producto|Verificada
|---|---|---|
|[AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)|[ATA-1](https://www.audiocodes.com/media/2373/mp-1xx-and-mp-124-datasheet.pdf)|&#10004;|
|[AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)|[ATA-2](https://www.audiocodes.com/media/2399/mediapack-20x-mp-20x-analog-telephone-adapters-datasheet.pdf)|&#10004;|
|[Cisco](https://www.cisco.com/c/en/us/products/collateral/unified-communications/ata-190-series-analog-telephone-adapters/datasheet-c78-740013.html)|Adaptador de teléfono analógico multiplataforma ATA 191|&#10004;|
|[Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html)|Versión de software AP 1100 compatible 8.3.0.1.2 y recomendada 8.4.x o 9.x|&#10004;|
|[Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html)|Versión de software AP 3900 compatible 8.3.0.1.2 y recomendada 8.4.x o 9.x|&#10004;|
|[Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html)|Versión de software AP 4600 compatible 8.3.0.1.2 y recomendada 8.4.x o 9.x|&#10004;|
|[Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html)|Versión de software AP 6300 compatible 8.3.0.1.2 y recomendada 8.4.x o 9.x|&#10004;|
|[Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html)|Versión de software AP 6350 compatible 8.3.0.1.2 y recomendada 8.4.x o 9.x|&#10004;|
|[Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html)|Versión de software de VME compatible 8.3.0.1.2 y recomendada 8.4.x o 9.x|&#10004;|
|[Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html)|Versión de software AP 3950 compatible 9.x|&#10004;|
|[Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html)|Versión de software AP 4900 compatible 9.x|&#10004;|
|[Cinta de opciones](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions)|[SBC 1000. Versión de software: 8.1.1 (compilación 527)](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)|&#10004;|
|[Cinta de opciones](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions)|[SBC 2000. Versión de software: 8.1.1 (compilación 527)](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)|&#10004;|
|[Cinta de opciones](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions)|[EdgeMarc 302. Versión de software: 16.1.1](https://ribboncommunications.com/products/service-provider-products/cloud-and-edge/session-border-controllers/session-border-controllers-edge-appliances)|&#10004;|
|[Cinta de opciones](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions)|[EdgeMarc 304. Versión de software: 16.1.1](https://ribboncommunications.com/products/service-provider-products/cloud-and-edge/session-border-controllers/session-border-controllers-edge-appliances)|&#10004;|
|[Cinta de opciones](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions)|[EdgeMarc 2900A. Versión de software: 16.1.1](https://ribboncommunications.com/products/service-provider-products/cloud-and-edge/session-border-controllers/session-border-controllers-edge-appliances)|&#10004;|
|[Cinta de opciones](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions)|[EdgeMarc 4806. Versión de software: 16.1.1](https://ribboncommunications.com/products/service-provider-products/cloud-and-edge/session-border-controllers/session-border-controllers-edge-appliances)|&#10004;|
|[Cinta de opciones](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions)|[EdgeMarc 4808. Versión de software: 16.1.1](https://ribboncommunications.com/products/service-provider-products/cloud-and-edge/session-border-controllers/session-border-controllers-edge-appliances)|&#10004;|
|[Cinta de opciones](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions)|[EdgeMarc 6000. Versión de software: 16.1.1](https://ribboncommunications.com/products/service-provider-products/cloud-and-edge/session-border-controllers/session-border-controllers-edge-appliances)|&#10004;|
|[TE-SYSTEMS](https://www.anynode.de/anynode-and-microsoft-teams/)|Anynode con GXW42xx de Grandstream (V1.0.7.10)|&#10004;|

Tenga en cuenta la certificación concedida a una versión principal. Esto significa que se admite el firmware con cualquier número en el firmware del CLS después de la versión principal.

Para proporcionar comentarios sobre Teams, como ideas para nuevas características, consulte el [portal de comentarios de Microsoft](https://feedbackportal.microsoft.com/).

> [!NOTE]
> No se admite el redireccionamiento de medios. Durante una llamada de Enrutamiento directo, si el CLS envía una nueva dirección IP de medios a Enrutamiento directo de Teams, aunque se negocia en la señalización SIP, los medios nunca se envían a la nueva dirección IP desde Enrutamiento directo de Teams.
