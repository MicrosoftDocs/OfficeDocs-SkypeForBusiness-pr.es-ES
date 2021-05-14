---
title: Controladores de borde de sesión certificados para enrutamiento directo
ms.author: crowe
ms.reviewer: FilippSe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
hideEdit: true
f1.keywords:
- NOCSH
description: El administrador puede obtener información sobre qué controladores de borde de sesión (SBC) se han certificado para enrutamiento directo.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4eab3bb25690c939afd2687f5a67e63a2c417a89
ms.sourcegitcommit: 272e8cf0075a566f055801433c9eb0313050530f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2021
ms.locfileid: "52486374"
---
# <a name="list-of-session-border-controllers-certified-for-direct-routing"></a>Lista de controladores de borde de sesión certificados para el enrutamiento directo

Microsoft se asocia con proveedores de controladores de borde de sesión (SBC) seleccionados para certificar que sus SBC pueden usarse con el Enrutamiento directo.

Microsoft trabaja con cada proveedor para:

- Trabaje conjuntamente en los protocolos de interconexión SIP.
- Realice pruebas intensas con un laboratorio de terceros. Solo los dispositivos que pasan las pruebas están certificados.
- Ejecute pruebas diarias con todos los dispositivos certificados en entornos de producción y preproducción. al validar los dispositivos los entornos previos a la fase de producción, garantiza que las nuevas versiones del código de Enrutamiento directo en la nube funcionará con los SBC certificados;
- Establecer un proceso de soporte técnico conjunto con los proveedores de SBC.

  > [!NOTE]
  > Microsoft solo admite Sistema telefónico dispositivos certificados o dispositivos conectados a través del enrutamiento directo. Microsoft se reserva el derecho de rechazar los casos de soporte técnico en los que un dispositivo no certificado esté conectado al Sistema telefónico mediante enrutamiento directo. Si Microsoft determina que el problema de enrutamiento directo de un cliente es con el dispositivo SBC de un proveedor, el cliente tendrá que contratar al proveedor de SBC para obtener soporte técnico.

Las tablas que siguen a los dispositivos de lista certificados para enrutamiento directo. (Para obtener información sobre qué proveedores de SBC admiten la optimización de medios locales, vea Configurar la optimización [de medios locales para enrutamiento directo).](direct-routing-media-optimization-configure.md)

[Obtenga más información sobre el Enrutamiento directo](https://aka.ms/dr).
Si tiene alguna pregunta sobre el programa de certificación SBC para enrutamiento directo, póngase en contacto con drsbccertification@microsoft.com.
<br/>

## <a name="certified-sbc-vendors"></a>Proveedores de SBC certificados

|                                                       Proveedor                                                        |       Producto       | Omisión no multimedia | Omisión de medios | Versión de software | 911 Proveedor de servicios compatible | Compatible con ELIN
|---------------------------------------------------------------------------------------------------------------------|---------------------|------------------|--------------|------------------|-----------------|------------------|
| [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams) |   SBC Mediant 500   |     &#10004;     |   &#10004;    |  Compatible con 7.20A.250 (recomendado 7.20A.258)   | &#10004;   |  &#10004;  |
|                                                                                                                     |   SBC Mediant 800   |     &#10004;     |   &#10004;     |  Compatible con 7.20A.250 (recomendado 7.20A.258)   | &#10004;   |  &#10004;  |
|                                                                                                                     |  SBC Mediant 2600   |     &#10004;     |   &#10004;    |  Compatible con 7.20A.250 (recomendado 7.20A.258)   |   &#10004;   |  &#10004;  |    
|                                                                                                                     |  SBC Mediant 4000   |     &#10004;     |   &#10004;     |  Compatible con 7.20A.250 (recomendado 7.20A.258)   |  &#10004;   |  &#10004;  |    
|                                                                                                                     | SBC Mediant 1000B  |     &#10004;     |   Pending     |  Compatible con 7.20A.250 (recomendado 7.20A.258)  |  &#10004;   |  &#10004;  |    
|                                                                                                                     | Mediant 9000 SBC  |     &#10004;     |   &#10004;     |  Compatible con 7.20A.250 (recomendado 7.20A.258)   | &#10004;     |  &#10004;  |                                                                       
|                                                                                                                     | SBC Virtual Edition |     &#10004;     |   &#10004;     |  Compatible con 7.20A.250 (recomendado 7.20A.258) |  &#10004;    |  &#10004;  |    
|  [Ribbon Communications](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-skype-business)  |      SBC 5100/5110       |     &#10004;     |   &#10004;    |       Compatible con 8.2 y 7.2 (recomendado 9.2)       | &#10004;   |     |    
|                                                                                                                     |      SBC 5200/5210       |     &#10004;     |  &#10004;    |       Compatible con 8.2 y 7.2 (recomendado 9.2)       |   &#10004; |    |    
|                                                                                                                     |      SBC 5400       |     &#10004;     |   &#10004;   |       Compatible con 8.2 y 7.2 (recomendado 9.2)       |   &#10004;  ||    
|                                                                                                                     |      SBC 7000       |     &#10004;     |   &#10004;    |       Compatible con 8.2 y 7.2 (recomendado 9.2)       |    &#10004;  |  |    
|                                                                                                                     |       SBC SWe       |     &#10004;     |   &#10004;   |       Compatible con 8.2 y 7.2 (recomendado 9.2)          |  &#10004;    |    |    
|                                                                                                                     |      SBC 1000       |     &#10004;     |   &#10004;    |      8.x o 9.x     |   &#10004;  |  &#10004;     |    
|                                                                                                                     |      SBC 2000       |     &#10004;     |   &#10004;   |     8.x o 9.x     |   &#10004;   |     &#10004;     |    
|                                                                                                                     |    SBC SWe Lite     |     &#10004;     |  &#10004;    |      8.x o 9.x    |   &#10004;    |     &#10004;     |   
| | Serie EdgeMarc |  &#10004; | | 15.6.1 | 
|                     [Thinktel](https://www.thinktel.ca/services/think-365/think-365-overview/)                      |    SBC Think 365    |     &#10004;     |           |       1.4       |     |    |    
|                     [Oracle](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)                      |    AP 1100      |    &#10004;     |    &#10004;    |   8.3.0.0.1 |   &#10004;    |  &#10004;  |    
|    |    AP 3900           |    &#10004;     |    &#10004;   |   8.3.0.0.1  |  &#10004;    |  &#10004;  |    
|                                                                                                                    |      AP 4600         |    &#10004;   |    &#10004;     |     8.3.0.0.1  |  &#10004;    |  &#10004;  |    
|                                                                                                                    |      AP 6300         |    &#10004;   |    &#10004;     |     8.3.0.0.1  |  &#10004;    |  &#10004;  |    
|                                                                                                                   |      AP 6350           |    &#10004;   |    &#10004;    |     8.3.0.0.1  |   &#10004;   |  &#10004;  |                                            
|                                                                                                                    |      VME           |    &#10004;    |    &#10004;    |     8.3.0.0.1   |   &#10004;   |  &#10004;  |    
|                     [TE-SYSTEMS](https://www.anynode.de/anynode-and-microsoft-teams/)                               |     anynode         |     &#10004;   |  &#10004;   |      Compatible con 3.20 (recomendado 4.0)        |  &#10004;    |  &#10004;   |    
|                     [Metaswitch](https://www.metaswitch.com/products/core-network/perimeta-sbc)                               |     Perimeta SBC        |     &#10004;   |  |      4.7      |     |    |  
|                     [Cisco](https://www.cisco.com/c/en/us/solutions/enterprise/interoperability-portal/networking_solutions_products_genericcontent0900aecd805bd13d.html)                               |     Elemento de borde unificado de Cisco (CUBO) para enrutadores de servicios integrados de la serie 1000        |     &#10004;   | &#10004; |      Compatible con IOS XE Amsterdam 17.2.1r (recomendado 17.3.2)         |    &#10004;     |   |  
|                                   |     Elemento de borde unificado de Cisco (CUBO) para enrutadores de servicios integrados de la serie 4000        |     &#10004;   | &#10004; |   Compatible con IOS XE Amsterdam 17.2.1r (recomendado 17.3.2)         |   &#10004;      |    |  
|                                   |     Elemento de borde unificado de Cisco (CUBO) para enrutador de servicios en la nube de la serie 1000V       |     &#10004;   | &#10004; |      Compatible con IOS XE Amsterdam 17.2.1r (recomendado 17.3.2)         |    &#10004;     |    |  
|                                 |     Elemento de borde unificado de Cisco (CUBO) para enrutadores de servicios de agregación de 1000 series      |     &#10004;   | &#10004; |      Compatible con IOS XE Amsterdam 17.2.1r (recomendado 17.3.2)         |    &#10004;     |    |
|                                 |     Elemento de borde unificado de Cisco (CUBO) para plataformas perimetrales de Catalyst 8000      |     &#10004;   | &#10004; |      IOS XE Amsterdam 17.3.2      |    &#10004;     |    |
|                     [Avaya](https://support.avaya.com/products/P0997/avaya-session-border-controller-for-enterprise/8.1.x)|    Controlador de borde de sesión de Avaya para Enterprise (ASBCE)    |     &#10004;     |       &#10004;     |       Versión 8.1.1 (8.1.2 para omisión de medios)      |     |    | 
|                     [Nokia](https://documentation.nokia.com/aces/cgi-bin/chk_access.cgi/3TB30222GBAAACZZA.zip)|    Controlador de borde de sesión de Nokia    |     &#10004;     |           |       19.5 (1908)       |     |    | 
|                     |    Controlador de borde de sesión de Nokia    |     &#10004;     |           |       20.8       |      &#10004;        |    | 
|                     [Italtel](https://www.italtel.com/italtel-provides-direct-routing-sbc-for-microsoft-teams/)|    NetMatch-S CI     |     &#10004;     |           |       Compatible con 5.0 (recomendado 5.1)     |     |    | 
|                     [Ericsson](https://www.ericsson.com/en/portfolio/digital-services/cloud-communication/enterprise-communication/business-communication-services-and-enablers/sip-trunking)|    vSBC 2.16     |     &#10004;     |           |              |     |    | 
|                     [Cataleya](https://cataleya.com/orchidplatforms/)|    Vínculo de orquídeas    |     &#10004;     |           |      3.1        |     |    | 
|                     [ULTATEL](https://www.ultatel.com/services/direct-routing-teams-sbc)|    Teams SBC    |     &#10004;     |     &#10004;      |      1.6        |     |    | 
|                     [Atos](https://unify.com/en/solutions/voice-platforms/session-border-controller)|    Controlador de borde de sesión de Atos Unify OpenScape   |     &#10004;     |          |      V10R1.2       |     |    | 
|                     [Sansay Inc.](https://www.sansay.com/solutions/microsoft-teams/)|    vmVSXi   |     &#10004;     |     &#10004;     |      10.5.1.354-vm-S-x64      |     |    |
|                     [Redes de Enghouse](https://www.enghousenetworks.com/portfolio/network-infrastructure/cloud-native-session-border-controller-sbc/)|    Dialogic BorderNet SBC   |     &#10004;     |     &#10004;     |      3.9.0-786      |     |    |
|                     [Patton Electronics Co.](https://www.patton.com/microsoft/)|    Patton SmartNode eSBC   |     &#10004;     |         |      3.19.x      |     |    |

<br/>
<br/>

## <a name="direct-routing-and-analog-devices-interoperability"></a>Interoperabilidad de enrutamiento directo y dispositivos analógicos

En la tabla siguiente se enumeran los dispositivos comprobados para la interoperabilidad entre enrutamiento directo y dispositivos analógicos.

|                                                       Proveedor                                                        |       Producto       | Comprobado
|---------------------------------------------------------------------------------------------------------------------|---------------------|------------------|
| [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams) |   [ATA-1](https://www.audiocodes.com/media/2373/mp-1xx-and-mp-124-datasheet.pdf)   |     &#10004;     |
| [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams) |   [ATA-2](https://www.audiocodes.com/media/2399/mediapack-20x-mp-20x-analog-telephone-adapters-datasheet.pdf)   |     &#10004;     | 
| [Cisco](https://www.cisco.com/c/en/us/products/collateral/unified-communications/ata-190-series-analog-telephone-adapters/datasheet-c78-740013.html) |  Adaptador de teléfono analógico multiplataforma ATA 191 |     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |   Ap1100 Versión de software 8.3.0.1.2 |     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  Ap3900 Versión de software 8.3.0.1.2|     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  Ap4600 Versión de software 8.3.0.1.2|     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  Ap6300 Versión de software 8.3.0.1.2|     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  Ap6350 Versión de software 8.3.0.1.2|     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  Versión 8.3.0.1.2 del software VME |     &#10004;     |
| [Cinta de opciones](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) |   [SBC 1000. Versión de software: 8.1.1 (compilación 527)](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)   |     &#10004;     |
| [Cinta de opciones](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) |   [SBC 2000. Versión de software: 8.1.1 (compilación 527)](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)   |     &#10004;     |
| [TE-SYSTEMS](https://www.anynode.de/anynode-and-microsoft-teams/) |  anynode con Grandstream GXW42xx (V1.0.7.10) |     &#10004;     |
  
Para enviarnos comentarios sobre Teams, como ideas para nuevas características, vea [Uservoice](https://microsoftteams.uservoice.com).


[!INCLUDE [uservoice-disclaimer-note](includes/uservoice-disclaimer-note.md)]

Tenga en cuenta la certificación concedida a una versión principal. Esto significa que se admite el firmware con cualquier número en el firmware de SBC que sigue a la versión principal.
