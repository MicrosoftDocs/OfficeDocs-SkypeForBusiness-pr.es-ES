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
description: Microsoft se asocia con proveedores SBC seleccionados para certificar que sus SBC pueden usarse con el Enrutamiento directo.
ms.openlocfilehash: 5fa0cb728beed0f308a4d168cd149ef1e75e2809
ms.sourcegitcommit: 100ba1409bf0af58e4430877c1d29622d793d23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2019
ms.locfileid: "37572250"
---
# <a name="list-of-session-border-controllers-certified-for-direct-routing"></a>Lista de controladores de borde de sesión certificados para el enrutamiento directo

Microsoft se asocia con proveedores de controladores de borde de sesión (SBC) seleccionados para certificar que sus SBC pueden usarse con el Enrutamiento directo. 

Con cada proveedor, Microsoft: 

- colabora con los proveedores de SBC en los protocolos de interconexión SIP;
- realiza pruebas muy intensas a través de un laboratorio de terceros, de manera que solo se certifican los dispositivos que pasan estas pruebas; 
- ejecuta pruebas a diario con todos los dispositivos certificados en entornos de producción y previos a la producción. al validar los dispositivos los entornos previos a la fase de producción, garantiza que las nuevas versiones del código de Enrutamiento directo en la nube funcionará con los SBC certificados; 
- tiene un proceso de soporte conjunto con los proveedores de SBC.


  > [!NOTE]
  > Microsoft solo admite el Sistema telefónico si hay uno o varios dispositivos certificados conectados a través del Enrutamiento directo. Microsoft se reserva el derecho a rechazar casos de soporte técnico en los que haya un dispositivo no certificado conectado al Sistema telefónico a través del Enrutamiento directo. 

En la tabla siguiente se enumeran los dispositivos certificados para el Enrutamiento directo. 

[Obtenga más información sobre el Enrutamiento directo](https://aka.ms/dr). Si tiene alguna pregunta sobre el programa de certificación de SBC para el Enrutamiento directo, escriba un correo electrónico a drsbccertification@microsoft.com


|                                                       Proveedor                                                        |       Producto       | Desvío de lo que no son medios | Desvío de medios | Versión de software |
|---------------------------------------------------------------------------------------------------------------------|---------------------|------------------|--------------|------------------|
| [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams) |   SBC Mediant 500   |     &#10004;     |   &#10004;    |  7.20 a. 250   |
|                                                                                                                     |   SBC Mediant 800   |     &#10004;     |   &#10004;     |  7.20 a. 250   |
|                                                                                                                     |  SBC Mediant 2600   |     &#10004;     |   &#10004;    |  7.20 a. 250   |
|                                                                                                                     |  SBC Mediant 4000   |     &#10004;     |   &#10004;     |  7.20 a. 250   |
|                                                                                                                     | SBC Mediant 1000B  |     &#10004;     |   Pending     |  7.20 a. 250  |
|                                                                                                                     | SBC 9000  |     &#10004;     |   &#10004;     |  7.20 a. 250   |                                                                       
|                                                                                                                     | SBC Virtual Edition |     &#10004;     |   &#10004;     |  7.20 a. 250 |
|  [Ribbon Communications](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-skype-business)  |      SBC 5110       |     &#10004;     |   &#10004;    |       V6.2       |
|                                                                                                                     |      SBC 5210       |     &#10004;     |  &#10004;    |       V6.2       |
|                                                                                                                     |      SBC 5400       |     &#10004;     |   &#10004;   |       V6.2       |
|                                                                                                                     |      SBC 7000       |     &#10004;     |   &#10004;    |       V6.2       |
|                                                                                                                     |       SBC SWe       |     &#10004;     |   &#10004;   |       V6.2       |
|                                                                                                                     |      SBC 1000       |     &#10004;     |   &#10004;    |      v8.0.1     |
|                                                                                                                     |      SBC 2000       |     &#10004;     |   &#10004;   |     v8.0.1     |
|                                                                                                                     |    SBC SWe Lite     |     &#10004;     |  &#10004;    |      v8.0.1    |
|                     [Thinktel](https://www.thinktel.ca/services/think-365/think-365-overview/)                      |    SBC Think 365    |     &#10004;     |   Pending    |       V1.4       |
|                     [Oracle](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)                      |    AP 1100      |    &#10004;     |    &#10004;    |   8.3.0.0.1 |
|                                                                                                                    |    AP 3900           |    &#10004;     |    &#10004;   |   8.3.0.0.1  | 
|                                                                                                                    |      AP 4600         |    &#10004;   |    &#10004;     |     8.3.0.0.1  |
|                                                                                                                    |      AP 6300         |    &#10004;   |    &#10004;     |     8.3.0.0.1  |
|                                                                                                                   |      AP 6350           |    &#10004;   |    &#10004;    |     8.3.0.0.1  |                                             
|                                                                                                                    |      VME           |    &#10004;    |    &#10004;    |     8.3.0.0.1   |
|                     [TE-SYSTEMS](https://www.anynode.de/anynode-and-microsoft-teams/)                               |     anynode         |     &#10004;   |  &#10004;   |      v3.16.2      |

Para enviarnos comentarios sobre los equipos, como ideas para nuevas características, visite [uservoice](https://microsoftteams.uservoice.com) , la certificación concedida a una versión principal. Eso significa que se admite el firmware con cualquier número en el firmware de SBC siguiendo la versión principal.
