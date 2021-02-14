---
title: Obtener teléfonos para Skype for Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.assetid: 91f2d947-45fc-4fab-bd8b-2e313531c477
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Phone System
description: 'Obtenga información sobre qué teléfonos funcionan con Skype for Business de Polycom, HP y Mitel, y las licencias necesarias. '
ms.openlocfilehash: f51465cc86baa37e54acddf732cc5f63e6274aa1
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "44220440"
---
# <a name="getting-phones-for-skype-for-business-online"></a>Obtener teléfonos para Skype for Business Online

Skype for Business Online qualifies and supports desktop phones for users who want to have a traditional phone experience, rather than use the Skype for Business app. This topic covers the phones and firmware versions that are supported for use in Skype for Business Online and other information that can help you when you are setting up phones in your organization.

> [!NOTE]
> Skype Empresarial será reemplazado lentamente por Microsoft Teams como método principal de comunicación en Microsoft 365 y Office 365.  Vea [una nueva visión de las comunicaciones inteligentes en Office 365](https://www.microsoft.com/microsoft-365/blog/2017/09/25/a-new-vision-for-intelligent-communications-in-office-365/) para obtener más información.
>
>Para obtener las actualizaciones más recientes y la información más actualizada sobre los dispositivos compatibles, consulte los dispositivos de Microsoft Teams para [obtener comunicaciones inteligentes.](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)
  
## <a name="supported-phones"></a>Teléfonos compatibles
  
Microsoft se asocia y trabaja estrechamente con Polycom, Yealink y AudioCodes para desarrollar y certificar una amplia variedad de dispositivos a través del Programa de teléfonos IP de socios (PIP) para el sistema telefónico.
  
Al solicitar teléfonos nuevos para Skype Empresarial, es importante comprar teléfonos con la *identificación de producto correcta.* Estos nombres de producto garantizarán que los teléfonos que recibe ya tengan instalada la versión de Skype Empresarial Online adecuada.
  
|||
|:-----|:-----|
|**Socio fabricante de teléfonos** <br/> |**Identificación de producto específica para Skype for Business** <br/> |
|Polycom  <br/> |Identificación de producto: 019  <br/> |
|Yealink  <br/> |SIP-TXXG versión para Skype Empresarial  <br/> |
|AudioCodes  <br/> |UCXXXHDEG (SfB)  <br/> |
   
Para obtener más información sobre los teléfonos polycom, consulte la [Biblioteca de documentación de Poly.](https://documents.polycom.com/category/voice)
  
Para obtener más información sobre los teléfonos de Yealink, consulte [Teléfonos IP para Skype for Business](http://www.yealink.com/products_list_10.html#filter2).
  
Para obtener más información sobre los teléfonos con AudioCodes, consulte [Teléfonos IP de Skype Empresarial.](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions)
  
> [!NOTE]
> Lync Phone Edition es compatible con Skype for Business Online, pero no con Microsoft Teams. El soporte estándar para la plataforma LPE finalizó el 10 de abril de 2014 y el soporte extendido continuará hasta el 11 de abril de 2023, coincidiendo con el ciclo de vida de soporte técnico del producto de Lync Server 2013. Consulte [Ciclo de vida de productos de Microsoft](https://support.microsoft.com/lifecycle/search?qid=&amp;alpha=Lync%20Phone%20Edition&amp;Filter=FilterNO) para obtener detalles sobre el ciclo de vida de LPE. Los modelos LPE CAP no son compatibles con Skype for Business Online.
>
> A partir de finales de este año, Office 365 no admitirá ninguna versión de TLS anterior a la 1.2. Dado que el sistema operativo subyacente de LPE no admite TLS 1.2, ya no se admitirá la conexión de LPE a Office 365. Para obtener más información, vea [Preparar el uso obligatorio de TLS 1.2 en Office 365](https://support.microsoft.com/en-gb/help/4057306/preparing-for-tls-1-2-in-office-365).
  
## <a name="supported-firmware"></a>Firmware compatible

Esta es la versión de software mínima necesaria para que los teléfonos compatibles funcionen con Sistema telefónico:
  
||||
|:-----|:-----|:-----|
|**Tipo de teléfono** <br/> |**Firmware mínimo** <br/> |**Fecha de lanzamiento** <br/> |
|Optimizado (Lync Phone Edition)  <br/> |4.0.7577.4463  <br/> |Mayo de 2015  <br/> |
|Polycom VVX Series certificado  <br/> |5.4.0A  <br/> |Diciembre de 2015  <br/> |
|Yealink  <br/> |X.8.1.52  <br/> |Febrero de 2017  <br/> |
|AudioCodes  <br/> |3.0.0.459.1  <br/> |Diciembre de 2016  <br/> |

Para obtener más información sobre las versiones de firmware certificadas actuales, consulte [Teléfonos IP para Skype Empresarial.](https://docs.microsoft.com/skypeforbusiness/certification/devices-ip-phones#conference-phones)

> [!NOTE]
> Los teléfonos Lync Phone Edition (LPE) que configure para su implementación local tienen que estar actualizados con el firmware mínimo necesario (o versiones posteriores) antes de transferir los usuarios a Skype Empresarial Online. Si transfiere los usuarios desde una implementación local a Skype Empresarial Online antes de actualizar el firmware en los teléfonos, esos teléfonos no se podrán conectar a Skype Empresarial. 
  
## <a name="required-licenses"></a>Licencias necesarias

Skype Empresarial Online no requiere ninguna otra licencia de Microsoft que no sea la de usuario. Para obtener más información sobre las licencias de usuario necesarias, consulte licencias de complementos de Skype Empresarial y [Microsoft Teams.](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
Los modelos de licencia del fabricante pueden variar entre el firmware SIP abierto y el certificado para Skype Empresarial. Si va a reutilizar un modelo certificado con un firmware SIP abierto, tendrá que verificar los requisitos de la licencia con el fabricante.
  
## <a name="skype-for-business-online-connected-phones-feature-set"></a>Conjunto de características de los teléfonos conectados de Skype Empresarial Online

Para obtener todas las características y funcionalidades del dispositivo, consulte las guías de usuario de los fabricantes.
  
||||||
|:-----|:-----|:-----|:-----|:-----|
|**Característica** <br/> |**3PIP de Polycom** <br/> |**3PIP de Yealink** <br/> |**3PIP de AudioCodes** <br/> |**LPE** <br/> |
|Inicio de sesión con las credenciales del usuario  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |No  <br/> |
|Inicio de sesión con un equipo (emparejamiento), solo Windows  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |
|Inicio de sesión con (inicio de sesión web)  <br/>  <br/> **Nota:** Consulte la matriz de compatibilidad en la guía de implementación.           |Sí  <br/> |Sí  <br/> |Sí  <br/> |No  <br/> |
|Unirse a la reunión con un solo clic  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |
|Clic para marcar (emparejamiento)  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |
|Controles de reunión  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |
|Correo de voz visual  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |
|Bloqueo de teléfono  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |
|Actualización de dispositivo  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |
|Aprovisionamiento en banda  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |
|QoE  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |No  <br/> |
|Carga de registros  <br/> <br/> **Nota:** Actualmente, todos los registros se cargan solo en el equipo de soporte técnico de Microsoft; el acceso de los clientes a los registros de teléfono aún no están disponibles.           |Sí  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |
|Autenticación moderna  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |No  <br/> |
|Varios números de emergencia  <br/> |Sí  <br/> |No  <br/> |No  <br/> |Sí  <br/> |
|Integración con el calendario de Exchange*  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> <br/> **Nota:** Requiere tethering de PC           |
|Integración de presencia  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |
|Directorio corporativo  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |
|Delegación  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |No  <br/> |
|Integración de imagen de contacto  <br/> |No  <br/> |Sí  <br/> |No  <br/> |Sí  <br/> |
||||||

     
> [!NOTE]
> Ni el CX 600 ni ningún otro teléfono Aries admite la autenticación multifactor (MFA). Si fuerza la MFA, estos dispositivos no iniciarán sesión. Estos dispositivos solo deben utilizar el id. de organización para la autenticación.
 
## <a name="what-else-should-you-know"></a>¿Qué más tengo que saber?
Para obtener instrucciones detalladas, consulte [Implementación de teléfonos de Skype Empresarial Online](deploying-skype-for-business-online-phones.md).

## <a name="related-topics"></a>Temas relacionados
[Obtener números de teléfono de servicio para Skype Empresarial y Microsoft Teams](../getting-service-phone-numbers.md)

[Esto es lo obtiene con el Sistema telefónico](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[Países y regiones donde Audioconferencia y Planes de llamada están disponibles](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

  
 
