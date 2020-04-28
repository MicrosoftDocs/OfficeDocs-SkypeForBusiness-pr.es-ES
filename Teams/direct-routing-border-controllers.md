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
description: Administrador puede saber qué controladores de borde de sesión (SBCs) se han certificado para el enrutamiento directo.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4d0a4f5846b120559b2fbaea97e191f1740ad4be
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2020
ms.locfileid: "43901835"
---
# <a name="list-of-session-border-controllers-certified-for-direct-routing"></a>Lista de controladores de borde de sesión certificados para el enrutamiento directo

Microsoft se asocia con proveedores de controladores de borde de sesión (SBC) seleccionados para certificar que sus SBC pueden usarse con el Enrutamiento directo. 

Microsoft trabaja con cada proveedor para: 

- Trabajan conjuntamente en los protocolos de interconexión SIP.
- Realice pruebas intensivas con un laboratorio de terceros. Solo los dispositivos que pasen las pruebas están certificados. 
- Ejecutar pruebas diarias con todos los dispositivos certificados en entornos de producción y preproducción. al validar los dispositivos los entornos previos a la fase de producción, garantiza que las nuevas versiones del código de Enrutamiento directo en la nube funcionará con los SBC certificados; 
- Establezca un proceso de soporte conjunto con los proveedores de SBC.


  > [!NOTE]
  > Microsoft solo admite el sistema telefónico si un dispositivo o dispositivos certificados están conectados a través de un enrutamiento directo. Microsoft se reserva el derecho de rechazar casos de asistencia en los que un dispositivo no certificado se conecta al sistema telefónico a través del enrutamiento directo. 

En la tabla siguiente se enumeran los dispositivos certificados para el Enrutamiento directo. 

[Obtenga más información sobre el Enrutamiento directo](https://aka.ms/dr). Si tiene preguntas sobre el programa de certificación de SBC para el enrutamiento directo, póngase en contacto con drsbccertification@microsoft.com.


|                                                       Proveedor                                                        |       Producto       | Omisión de elementos no multimedia | Omisión de medios | Versión del software | Validada con proveedores de E911 | Capacidad de ELIN
|---------------------------------------------------------------------------------------------------------------------|---------------------|------------------|--------------|------------------|-----------------|------------------|
| [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams) |   SBC Mediant 500   |     &#10004;     |   &#10004;    |  Compatible 7.20 A. 250 (recomendado 7.20 A. 256)   | <ul> <li> [Enrutamiento de ubicación dinámica de ancho de banda](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>Entrada ERS </li> <li>Entrada EGW</li> <li> Movilidad del horizonte de cielo rojo </li>  </ul> |  &#10004;  |
|                                                                                                                     |   SBC Mediant 800   |     &#10004;     |   &#10004;     |  Compatible 7.20 A. 250 (recomendado 7.20 A. 256)   | <ul> <li> [Enrutamiento de ubicación dinámica de ancho de banda](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>Entrada ERS </li> <li>Entrada EGW</li> <li> Movilidad del horizonte de cielo rojo </li>  </ul>  |  &#10004;  |
|                                                                                                                     |  SBC Mediant 2600   |     &#10004;     |   &#10004;    |  Compatible 7.20 A. 250 (recomendado 7.20 A. 256)   |   <ul> <li> [Enrutamiento de ubicación dinámica de ancho de banda](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>Entrada ERS </li> <li>Entrada EGW</li> <li> Movilidad del horizonte de cielo rojo </li>  </ul>  |  &#10004;  |    
|                                                                                                                     |  SBC Mediant 4000   |     &#10004;     |   &#10004;     |  Compatible 7.20 A. 250 (recomendado 7.20 A. 256)   |  <ul> <li> [Enrutamiento de ubicación dinámica de ancho de banda](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>Entrada ERS </li> <li>Entrada EGW</li> <li> Movilidad del horizonte de cielo rojo </li>  </ul>  |  &#10004;  |    
|                                                                                                                     | SBC Mediant 1000B  |     &#10004;     |   Pending     |  Compatible 7.20 A. 250 (recomendado 7.20 A. 256)  |  <ul> <li> [Enrutamiento de ubicación dinámica de ancho de banda](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>Entrada ERS </li> <li>Entrada EGW</li> <li> Movilidad del horizonte de cielo rojo </li>  </ul>  |  &#10004;  |    
|                                                                                                                     | SBC 9000  |     &#10004;     |   &#10004;     |  Compatible 7.20 A. 250 (recomendado 7.20 A. 256)   | <ul> <li> [Enrutamiento de ubicación dinámica de ancho de banda](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>Entrada ERS </li> <li>Entrada EGW</li> <li> Movilidad del horizonte de cielo rojo </li>  </ul>    |  &#10004;  |                                                                       
|                                                                                                                     | SBC Virtual Edition |     &#10004;     |   &#10004;     |  Compatible 7.20 A. 250 (recomendado 7.20 A. 256) |  <ul> <li> [Enrutamiento de ubicación dinámica de ancho de banda](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>Entrada ERS </li> <li>Entrada EGW</li> <li> Movilidad del horizonte de cielo rojo </li>  </ul>   |  &#10004;  |    
|  [Ribbon Communications](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-skype-business)  |      SBC 5110       |     &#10004;     |   &#10004;    |       Compatible 7,2 (recomendado 8,2)       | <ul> <li> [Enrutamiento de ubicación dinámica de ancho de banda](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>Entrada ERS </li> <li>Entrada EGW</li> <li> Movilidad del horizonte de cielo rojo </li>  </ul> |    |    
|                                                                                                                     |      SBC 5210       |     &#10004;     |  &#10004;    |       Compatible 7,2 (recomendado 8,2)       |  <ul> <li> [Enrutamiento de ubicación dinámica de ancho de banda](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>Entrada ERS </li> <li>Entrada EGW</li> <li> Movilidad del horizonte de cielo rojo </li> </ul> |    |    
|                                                                                                                     |      SBC 5400       |     &#10004;     |   &#10004;   |       Compatible 7,2 (recomendado 8,2)       |  <ul> <li> [Enrutamiento de ubicación dinámica de ancho de banda](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li><li>Entrada ERS </li> <li>Entrada EGW</li> <li> Movilidad del horizonte de cielo rojo </li> </ul>  ||    
|                                                                                                                     |      SBC 7000       |     &#10004;     |   &#10004;    |       Compatible 7,2 (recomendado 8,2)       |   <ul> <li> [Enrutamiento de ubicación dinámica de ancho de banda](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>Entrada ERS </li> <li>Entrada EGW</li> <li> Movilidad del horizonte de cielo rojo </li> </ul> |  |    
|                                                                                                                     |       SBC SWe       |     &#10004;     |   &#10004;   |       Compatible 7,2 (recomendado 8,2)       |   <ul> <li> [Enrutamiento de ubicación dinámica de ancho de banda](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>Entrada ERS </li> <li>Entrada EGW</li> <li> Movilidad del horizonte de cielo rojo </li> </ul> |    |    
|                                                                                                                     |      SBC 1000       |     &#10004;     |   &#10004;    |      8.0.3 (compilación 537)     |  <ul> <li> [Enrutamiento de ubicación dinámica de ancho de banda](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li> Entrada ERS </li> <li>Entrada EGW </li> <li> Movilidad del horizonte de cielo rojo </li> </ul>   |  &#10004;   |    
|                                                                                                                     |      SBC 2000       |     &#10004;     |   &#10004;   |     8.0.3 (compilación 537)     |  <ul> <li>[Enrutamiento de ubicación dinámica de ancho de banda](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li> Entrada ERS </li> <li>Entrada EGW </li> <li> Movilidad del horizonte de cielo rojo </li> </ul>   |     &#10004;     |    
|                                                                                                                     |    SBC SWe Lite     |     &#10004;     |  &#10004;    |      8.0.3 (compilación 216)    |  <ul> <li> [Enrutamiento de ubicación dinámica de ancho de banda](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li> Entrada ERS </li> <li>Entrada EGW </li> <li> Movilidad del horizonte de cielo rojo </li> </ul>    |     &#10004;     |   
| | Serie EdgeMarc |  &#10004; | | 15.6.1 | 
|                     [Thinktel](https://www.thinktel.ca/services/think-365/think-365-overview/)                      |    SBC Think 365    |     &#10004;     |           |       1,4       |     |    |    
|                     [Oracle](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)                      |    AP 1100      |    &#10004;     |    &#10004;    |   8.3.0.0.1 |   <ul> <li> [Enrutamiento de ubicación dinámica de ancho de banda](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>Entrada ERS </li> <li>Entrada EGW</li> <li> Movilidad del horizonte de cielo rojo </li>  </ul>   |  &#10004;  |    
|                                                                                                                    |    AP 3900           |    &#10004;     |    &#10004;   |   8.3.0.0.1  |  <ul> <li> [Enrutamiento de ubicación dinámica de ancho de banda](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>Entrada ERS </li> <li>Entrada EGW</li> <li> Movilidad del horizonte de cielo rojo </li>  </ul>  |  &#10004;  |    
|                                                                                                                    |      AP 4600         |    &#10004;   |    &#10004;     |     8.3.0.0.1  |  <ul> <li> [Enrutamiento de ubicación dinámica de ancho de banda](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>Entrada ERS </li> <li>Entrada EGW</li> <li> Movilidad del horizonte de cielo rojo </li>  </ul>  |  &#10004;  |    
|                                                                                                                    |      AP 6300         |    &#10004;   |    &#10004;     |     8.3.0.0.1  |  <ul> <li> [Enrutamiento de ubicación dinámica de ancho de banda](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>Entrada ERS </li> <li>Entrada EGW</li> <li> Movilidad del horizonte de cielo rojo </li>  </ul>   |  &#10004;  |    
|                                                                                                                   |      AP 6350           |    &#10004;   |    &#10004;    |     8.3.0.0.1  |   <ul> <li> [Enrutamiento de ubicación dinámica de ancho de banda](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>Entrada ERS </li> <li>Entrada EGW</li> <li> Movilidad del horizonte de cielo rojo </li>  </ul>  |  &#10004;  |                                            
|                                                                                                                    |      VME           |    &#10004;    |    &#10004;    |     8.3.0.0.1   |   <ul> <li> [Enrutamiento de ubicación dinámica de ancho de banda](https://www.bandwidth.com/partners/microsoft-teams-direct-routing) </li> <li>Entrada ERS </li> <li>Entrada EGW</li> <li> Movilidad del horizonte de cielo rojo </li>  </ul>  |  &#10004;  |    
|                     [TE-SYSTEMS](https://www.anynode.de/anynode-and-microsoft-teams/)                               |     anynode         |     &#10004;   |  &#10004;   |      Compatible 3,20 (recomendado 4,0)        |     |    |    
|                     [MetaSwitch](https://www.metaswitch.com/products/core-network/perimeta-sbc)                               |     Metaestado de perimeta        |     &#10004;   |  |      4,7      |     |    |    

En la siguiente tabla se enumeran los dispositivos verificados para la interoperabilidad entre el enrutamiento directo y los dispositivos analógicos.

|                                                       Proveedor                                                        |       Producto       | Probado
|---------------------------------------------------------------------------------------------------------------------|---------------------|------------------|
| [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams) |   [ATA-1](https://www.audiocodes.com/media/2373/mp-1xx-and-mp-124-datasheet.pdf)   |     &#10004;     |
| [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams) |   [ATA-2](https://www.audiocodes.com/media/2399/mediapack-20x-mp-20x-analog-telephone-adapters-datasheet.pdf)   |     &#10004;     |
| [Lazo](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) |   [SBC 1000. Versión del software: 8.1.1 (compilación 527)](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)   |     &#10004;     |
| [Lazo](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) |   [SBC 2000. Versión del software: 8.1.1 (compilación 527)](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)   |     &#10004;     |


Para enviarnos comentarios sobre los equipos, como ideas para nuevas características, vea [uservoice](https://microsoftteams.uservoice.com) Anote la certificación concedida a una versión principal. Eso significa que se admite el firmware con cualquier número en el firmware de SBC siguiendo la versión principal.
