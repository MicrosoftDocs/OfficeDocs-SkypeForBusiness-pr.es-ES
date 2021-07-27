---
title: Controladores de límites de sesión certificados para Enrutamiento directo
ms.author: crowe
ms.reviewer: FilippSe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Priority
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
hideEdit: true
f1.keywords:
- NOCSH
description: El administrador puede obtener información sobre qué controladores de límites de sesión (CLS) se han certificado para Enrutamiento directo.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 13d7103ecb4183674fe1e92c7d7e3a37182c0d50
ms.sourcegitcommit: beb66bc2ce70edbaf6c77eee6d8c050c5cb37fe1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/22/2021
ms.locfileid: "53515175"
---
# <a name="list-of-session-border-controllers-certified-for-direct-routing"></a>Lista de controladores de borde de sesión certificados para el enrutamiento directo

Microsoft se asocia con proveedores de controladores de borde de sesión (SBC) seleccionados para certificar que sus SBC pueden usarse con el Enrutamiento directo.

Microsoft trabaja con cada proveedor para:

- Trabajar conjuntamente en los protocolos de interconexión SIP.
- Realizar pruebas intensivas mediante un laboratorio de terceros. Solo se certifican los dispositivos que superen las pruebas.
- Ejecutar pruebas a diario con todos los dispositivos certificados en entornos de producción y previos a la producción. Validar los dispositivos en entornos previos a la fase de producción garantiza que las nuevas versiones del código de Enrutamiento directo en la nube funcione con los CLS certificados;
- Establecer un proceso de soporte conjunto con los proveedores de CLS.

  > [!NOTE]
  > Microsoft solo admite el Sistema telefónico si hay uno o varios dispositivos certificados conectados a través del Enrutamiento directo. Microsoft se reserva el derecho a rechazar casos de soporte técnico de dispositivos no certificados conectados al Sistema telefónico a través del Enrutamiento directo. Si Microsoft determina que el problema de Enrutamiento directo de un cliente está relacionado con el dispositivo CLS de un proveedor, el cliente deberá ponerse en contacto con el proveedor deL CLS para obtener soporte técnico.

En las tablas siguientes se enumeran los dispositivos certificados para Enrutamiento directo. (Para obtener información sobre qué proveedores de CLS admiten la optimización de medios locales, vea [Configurar la optimización de medios locales para el enrutamiento directo](direct-routing-media-optimization-configure.md)).

[Obtenga más información sobre el Enrutamiento directo](https://aka.ms/dr).
Si tiene alguna pregunta sobre el programa de certificación de CLS para Enrutamiento directo, escriba un correo electrónico a drsbccertification@microsoft.com
<br/>

## <a name="certified-sbc-vendors"></a>Proveedores de CLS certificados

|                                                       Proveedor                                                        |       Producto       | Omisión de los que no son medios | Omisión de medios | Versión de software | Compatible con el proveedor de servicios 911* | Compatible con ELIN |  
|---------------------------------------------------------------------------------------------------------------------|---------------------|------------------|--------------|------------------|-----------------|------------------|  
| [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams) |   SBC Mediant 500   |     &#10004;     |   &#10004;    |  Compatible con 7.20A.250 (recomendado 7.20A.258)   | &#10004;   |  &#10004;  |  
|                                                                                                                     |   SBC Mediant 800   |     &#10004;     |   &#10004;     |  Compatible con 7.20A.250 (recomendado 7.20A.258)   | &#10004;   |  &#10004;  |  
|                                                                                                                     |  SBC Mediant 2600   |     &#10004;     |   &#10004;    |  Compatible con 7.20A.250 (recomendado 7.20A.258)   |   &#10004;   |  &#10004;  |
|                                                                                                                     |  SBC Mediant 4000   |     &#10004;     |   &#10004;     |  Compatible con 7.20A.250 (recomendado 7.20A.258)   |  &#10004;   |  &#10004;  |
|                                                                                                                     | SBC Mediant 1000B  |     &#10004;     |   Pending     |  Compatible con 7.20A.250 (recomendado 7.20A.258)  |  &#10004;   |  &#10004;  |
|                                                                                                                     | SBC Mediant 9000  |     &#10004;     |   &#10004;     |  Compatible con 7.20A.250 (recomendado 7.20A.258)   | &#10004;     |  &#10004;  |
|                                                                                                                     | SBC Virtual Edition |     &#10004;     |   &#10004;     |  Compatible con 7.20A.250 (recomendado 7.20A.258) |  &#10004;    |  &#10004;  |
|  [Comunicaciones de cinta](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-skype-business)  |      SBC 5100/5110       |     &#10004;     |   &#10004;    |       Compatible con 8.2 y 7.2 (recomendado 9.2)       | &#10004;   |     |
|                                                                                                                     |      SBC 5200/5210       |     &#10004;     |  &#10004;    |       Compatible con 8.2 y 7.2 (recomendado 9.2)       |   &#10004; |    |
|                                                                                                                     |      SBC 5400       |     &#10004;     |   &#10004;   |       Compatible con 8.2 y 7.2 (recomendado 9.2)       |   &#10004;  | |
|                                                                                                                     |      SBC 7000       |     &#10004;     |   &#10004;    |       Compatible con 8.2 y 7.2 (recomendado 9.2)       |    &#10004;  |  |
|                                                                                                                     |       SBC SWe       |     &#10004;     |   &#10004;   |       Compatible con 8.2 y 7.2 (recomendado 9.2)          |  &#10004;    |    |
|                                                                                                                     |      SBC 1000       |     &#10004;     |   &#10004;    |      8.x or 9.x     |   &#10004;  |  &#10004;     |
|                                                                                                                     |      SBC 2000       |     &#10004;     |   &#10004;   |     8.x or 9.x     |   &#10004;   |     &#10004;     |
|                                                                                                                     |    SBC SWe Lite     |     &#10004;     |  &#10004;    |      8.x or 9.x    |   &#10004;    |     &#10004;     |
| | Serie EdgeMarc |  &#10004; | | 15.6.1 | |  
|                     [Thinktel](https://www.thinktel.ca/services/think-365/think-365-overview/)                      |    SBC Think 365    |     &#10004;     |           |       1.4       |     |    |
|                     [Oracle](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)                      |    AP 1100      |    &#10004;     |    &#10004;    |   8.3.0.0.1 |   &#10004;    |  &#10004;  |
|    |    AP 3900           |    &#10004;     |    &#10004;   |   8.3.0.0.1  |  &#10004;    |  &#10004;  |
|                                                                                                                    |      AP 4600         |    &#10004;   |    &#10004;     |     8.3.0.0.1  |  &#10004;    |  &#10004;  |
|                                                                                                                    |      AP 6300         |    &#10004;   |    &#10004;     |     8.3.0.0.1  |  &#10004;    |  &#10004;  |
|                                                                                                                   |      AP 6350           |    &#10004;   |    &#10004;    |     8.3.0.0.1  |   &#10004;   |  &#10004;  |
|                                                                                                                    |      VME           |    &#10004;    |    &#10004;    |     8.3.0.0.1   |   &#10004;   |  &#10004;  |
|                     [TE-SYSTEMS](https://www.anynode.de/anynode-and-microsoft-teams/)                               |     anynode         |     &#10004;   |  &#10004;   |      Compatible con 3.20 (recomendado 4.0)        |  &#10004;    |  &#10004;   |
|                     [Metaswitch](https://www.metaswitch.com/products/core-network/perimeta-sbc)                               |     SBC Perimeta        |     &#10004;   | &#10004; |      4.7 (4.9 para omisión de medios)      |     |    |  
|                     [Cisco](https://www.cisco.com/c/en/us/solutions/enterprise/interoperability-portal/networking_solutions_products_genericcontent0900aecd805bd13d.html)                               |     Elemento de borde unificado de Cisco (CUBE) para enrutadores de servicios integrados de la serie 1000        |     &#10004;   | &#10004; |      IOS XE Ámsterdam 17.2.1r compatible (recomendado 17.3.2)         |    &#10004;     |   |  
|                                   |     Elemento de borde unificado de Cisco (CUBE) para enrutadores de servicios integrados de la serie 4000        |     &#10004;   | &#10004; |   IOS XE Ámsterdam 17.2.1r compatible (recomendado 17.3.2)         |   &#10004;      |    |  
|                                   |     Elemento de borde unificado de Cisco (CUBE) para enrutador de servicios en la nube serie 1000V       |     &#10004;   | &#10004; |      IOS XE Ámsterdam 17.2.1r compatible (recomendado 17.3.2)         |    &#10004;     |    |  
|                                 |     Elemento de borde unificado de Cisco (CUBE) para enrutadores de servicios de agregación de la serie 1000      |     &#10004;   | &#10004; |      IOS XE Ámsterdam 17.2.1r compatible (recomendado 17.3.2)         |    &#10004;     |    |
|                                 |     Elemento de borde unificado de Cisco (CUBE) para plataformas perimetrales de Catalyst 8000      |     &#10004;   | &#10004; |      IOS XE Ámsterdam 17.3.2      |    &#10004;     |    |
|                     [Avaya](https://support.avaya.com/products/P0997/avaya-session-border-controller-for-enterprise/8.1.x)|    Controlador de límites de sesión de Avaya para empresas (ASBCE)    |     &#10004;     |       &#10004;     |       Versión 8.1.1 (8.1.2 para omisión de medios)      |     |    |
|                     [Nokia](https://documentation.nokia.com/aces/cgi-bin/chk_access.cgi/3TB30222GBAAACZZA.zip)|    Controlador de límites de sesión Nokia    |     &#10004;     |           |       19.5 (1908)       |     |    |
|                     |    Controlador de límites de sesión Nokia    |     &#10004;     |           |       20.8       |      &#10004;        |    |
|                     [Italtel](https://www.italtel.com/italtel-provides-direct-routing-sbc-for-microsoft-teams/)|    NetMatch-S CI     |     &#10004;     |           |       Compatible con 5.0 (recomendado 5.1)     |     |    |
|                     [Ericsson](https://www.ericsson.com/en/portfolio/digital-services/cloud-communication/enterprise-communication/business-communication-services-and-enablers/sip-trunking)|    vSBC 2.16     |     &#10004;     |           |              |     |    |
|                     [Cataleya](https://cataleya.com/orchidplatforms/)|    Vínculo de Orchid    |     &#10004;     |           |      3.1        |     |    |
|                     [ULTATEL](https://www.ultatel.com/services/direct-routing-teams-sbc)|    CLS de Teams    |     &#10004;     |     &#10004;      |      1.6        |     |    |
|                     [Atos](https://unify.com/en/solutions/voice-platforms/session-border-controller)|    Controlador de límites de sesión de Atos Unify OpenScape   |     &#10004;     |          |      V10R1.2       |     |    |
|                     [Sansay Inc.](https://www.sansay.com/solutions/microsoft-teams/)|    vmVSXi   |     &#10004;     |     &#10004;     |      10.5.1.354-vm-S-x64      |     |    |
|                     [Enghouse Networks](https://www.enghousenetworks.com/portfolio/network-infrastructure/cloud-native-session-border-controller-sbc/)|    CLS de BorderNet Dialogic   |     &#10004;     |     &#10004;     |      3.9.0-786      |     |    |
|                     [Patton Electronics Co.](https://www.patton.com/microsoft/)|    Patton SmartNode eSBC   |     &#10004;     |         |      3.19.x      |     |    |
|                     [M5 Technologies (anteriormente conocido como Media5 Corporation)](https://www.m5t.com/solutions/sentinel-sbc-ms-teams-certified/)|    Serie Sentinel de Mediatrix   |     &#10004;     |         |      DGW 48.0.2340 (DGW recomendado 48.1.2503)      |     |    |
|                     [Ekinops](https://www.ekinops.com/solutions/voice-data-access/microsoft-direct-routing-sbc)|    Controlador de límites de sesión de Ekinops (ONeSBC)   |     &#10004;     |     &#10004;     |      6.6.1m5ha1      |     |    |
|                     |    Controlador de límites de sesión virtual de Ekinops (ONEvSBC)   |     &#10004;     |    &#10004;      |      6.6.1m5ha1      |     |    |
|                     [46 Labs LLC](https://46labs.com/docs/hcvoice/teams/)|    Voz hiperconvergida   |     &#10004;     |     &#10004;      |      HCVoice 1.0.6       |     |    |

<br/>

* Proveedores de servicios 911

- [Enrutamiento de ubicación dinámica de ancho de banda](https://www.bandwidth.com/partners/microsoft-teams-direct-routing/)
- [Servicio de enrutamiento de emergencia Intrado (ERS)](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)
- [Puerta de enlace de emergencia Intrado (EGW)](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)
<br/>

## <a name="direct-routing-and-analog-devices-interoperability"></a>Enrutamiento directo e interoperabilidad de los dispositivos analógicos

En la tabla siguiente se enumeran los dispositivos que se comprueban para la interoperabilidad entre el Enrutamiento directo y los dispositivos analógicos.

|                                                       Proveedor                                                        |       Producto       | Verificada
|---------------------------------------------------------------------------------------------------------------------|---------------------|------------------|
| [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams) |   [ATA-1](https://www.audiocodes.com/media/2373/mp-1xx-and-mp-124-datasheet.pdf)   |     &#10004;     |
| [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams) |   [ATA-2](https://www.audiocodes.com/media/2399/mediapack-20x-mp-20x-analog-telephone-adapters-datasheet.pdf)   |     &#10004;     | 
| [Cisco](https://www.cisco.com/c/en/us/products/collateral/unified-communications/ata-190-series-analog-telephone-adapters/datasheet-c78-740013.html) |  Adaptador de teléfono analógico multiplataforma ATA 191 |     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |   AP1100 Versión de software 8.3.0.1.2 |     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  AP3900 Versión de software 8.3.0.1.2|     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  AP4600 Versión de software 8.3.0.1.2|     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  AP6300 Versión de software 8.3.0.1.2|     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  AP6350 Versión de software 8.3.0.1.2|     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  VME Versión de software 8.3.0.1.2 |     &#10004;     |
| [Cinta de opciones](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) |   [SBC 1000. Versión de software: 8.1.1 (compilación 527)](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)   |     &#10004;     |
| [Cinta de opciones](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) |   [SBC 2000. Versión de software: 8.1.1 (compilación 527)](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)   |     &#10004;     |
| [TE-SYSTEMS](https://www.anynode.de/anynode-and-microsoft-teams/) |  Anynode con GXW42xx de Grandstream (V1.0.7.10) |     &#10004;     |
  
Para enviarnos sus comentarios sobre Microsoft Teams, como ideas para nuevas características, consulte [UserVoice](https://microsoftteams.uservoice.com).


[!INCLUDE [uservoice-disclaimer-note](includes/uservoice-disclaimer-note.md)]

Tenga en cuenta la certificación concedida a una versión principal. Esto significa que se admite el firmware con cualquier número en el firmware del CLS después de la versión principal.
