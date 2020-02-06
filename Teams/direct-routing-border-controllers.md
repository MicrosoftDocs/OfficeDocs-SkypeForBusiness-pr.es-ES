---
title: Lista de controladores de borde de sesión certificados para el enrutamiento directo
ms.author: crowe
ms.reviewer: NMuravlyannikov
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
description: Microsoft se asocia con proveedores SBC seleccionados para certificar que sus SBC pueden usarse con el Enrutamiento directo.
ms.openlocfilehash: dfd5474ac0e70353823be48b44e0d5e2e2f39f1d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41823994"
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
| [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams) |   SBC Mediant 500   |     &#10004;     |   &#10004;    |  7.20 a. 250   |
|                                                                                                                     |   SBC Mediant 800   |     &#10004;     |   &#10004;     |  7.20 a. 250   |    |    |
|                                                                                                                     |  SBC Mediant 2600   |     &#10004;     |   &#10004;    |  7.20 a. 250   |     |    |    
|                                                                                                                     |  SBC Mediant 4000   |     &#10004;     |   &#10004;     |  7.20 a. 250   |     |    |    
|                                                                                                                     | SBC Mediant 1000B  |     &#10004;     |   Pending     |  7.20 a. 250  |    |    |    
|                                                                                                                     | SBC 9000  |     &#10004;     |   &#10004;     |  7.20 a. 250   |    |    |                                                                       
|                                                                                                                     | SBC Virtual Edition |     &#10004;     |   &#10004;     |  7.20 a. 250 |    |    |    
|  [Ribbon Communications](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-skype-business)  |      SBC 5110       |     &#10004;     |   &#10004;    |       V 7.2       |  Entrada ERS <br>Entrada EGW |   No |    
|                                                                                                                     |      SBC 5210       |     &#10004;     |  &#10004;    |       V 7.2       |   Entrada ERS <br>Entrada EGW  | No   |    
|                                                                                                                     |      SBC 5400       |     &#10004;     |   &#10004;   |       V 7.2       |  Entrada ERS <br>Entrada EGW    |No|    
|                                                                                                                     |      SBC 7000       |     &#10004;     |   &#10004;    |       V 7.2       |   Entrada ERS <br>Entrada EGW  |  No  |    
|                                                                                                                     |       SBC SWe       |     &#10004;     |   &#10004;   |       V 7.2       |   Entrada ERS <br>Entrada EGW |   No |    
|                                                                                                                     |      SBC 1000       |     &#10004;     |   &#10004;    |      v 8.0.3 (compilación 537)     |  Entrada ERS <br>Entrada EGW   |  Pending  |    
|                                                                                                                     |      SBC 2000       |     &#10004;     |   &#10004;   |     v 8.0.3 (compilación 537)     |  Entrada ERS <br>Entrada EGW  |  Pending  |    
|                                                                                                                     |    SBC SWe Lite     |     &#10004;     |  &#10004;    |      v 8.0.3 (compilación 216)    |  Entrada ERS <br>Entrada EGW   |  Pending  |    
|                     [Thinktel](https://www.thinktel.ca/services/think-365/think-365-overview/)                      |    SBC Think 365    |     &#10004;     |   Pending    |       V1.4       |     |    |    
|                     [Oracle](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)                      |    AP 1100      |    &#10004;     |    &#10004;    |   8.3.0.0.1 |    |    |    
|                                                                                                                    |    AP 3900           |    &#10004;     |    &#10004;   |   8.3.0.0.1  |    |    |    
|                                                                                                                    |      AP 4600         |    &#10004;   |    &#10004;     |     8.3.0.0.1  |   |    |    
|                                                                                                                    |      AP 6300         |    &#10004;   |    &#10004;     |     8.3.0.0.1  |   |    |    
|                                                                                                                   |      AP 6350           |    &#10004;   |    &#10004;    |     8.3.0.0.1  |        |    |                                            
|                                                                                                                    |      VME           |    &#10004;    |    &#10004;    |     8.3.0.0.1   |    |    |    
|                     [TE-SYSTEMS](https://www.anynode.de/anynode-and-microsoft-teams/)                               |     anynode         |     &#10004;   |  &#10004;   |      v3.16.2      |     |    |    

Para enviarnos comentarios sobre los equipos, como ideas para nuevas características, vea [uservoice](https://microsoftteams.uservoice.com) Anote la certificación concedida a una versión principal. Eso significa que se admite el firmware con cualquier número en el firmware de SBC siguiendo la versión principal.
