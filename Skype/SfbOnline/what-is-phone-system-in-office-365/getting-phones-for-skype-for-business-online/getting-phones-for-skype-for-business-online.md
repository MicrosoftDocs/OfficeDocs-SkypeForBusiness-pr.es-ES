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
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 'Obtenga información sobre qué teléfonos funcionan con Skype for Business de Polycom, HP y Mitel, y las licencias necesarias. '
ms.openlocfilehash: e79c942923e9a9d4d0df0bc18172eb10caff57bc
ms.sourcegitcommit: f9a9a7e4b7f6c821a3372f7dcb966a8a6d458752
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2019
ms.locfileid: "30952401"
---
# <a name="getting-phones-for-skype-for-business-online"></a>Obtener teléfonos para Skype for Business Online

Skype for Business Online qualifies and supports desktop phones for users who want to have a traditional phone experience, rather than use the Skype for Business app. This topic covers the phones and firmware versions that are supported for use in Skype for Business Online and other information that can help you when you are setting up phones in your organization.
  
Para obtener las actualizaciones más recientes y la mayoría de la información actualizada en dispositivos compatibles, vea el [Skype para el catálogo de dispositivo de negocio](http://partnersolutions.skypeforbusiness.com/solutionscatalog).
  
## <a name="supported-phones"></a>Teléfonos compatibles

Para Skype para usuarios profesionales en línea, puede elegir entre varios modelos de *certificado para Skype para teléfonos de negocio* y teléfonos que ejecutan Lync Phone Edition (LPE) enumeran en la Skype para categoría empresarial en línea en el [Skype para dispositivos de negocio Catálogo de](http://partnersolutions.skypeforbusiness.com/solutionscatalog).
  
Microsoft es la asociación y trabajar estrechamente con Polycom, Yealink y AudioCodes para desarrollar y certifica una amplia variedad de dispositivos a través del programa socio de teléfono IP (puntos) para el sistema telefónico en Office 365 y Skype para Business Server.
  
When ordering new phones for Skype for Business, it is important to buy phones with the *right product ID*. These product IDs will ensure that the phones you receive have the Skype for Business Online qualified version already installed.
  
|||
|:-----|:-----|
|**Socio fabricante de teléfonos** <br/> |**Identificación de producto específica para Skype for Business** <br/> |
|Polycom  <br/> |Identificación de producto: 019  <br/> |
|Yealink  <br/> |SIP-TXXG versión para Skype Empresarial  <br/> |
|AudioCodes  <br/> |UCXXXHDEG (SfB)  <br/> |
   
Para obtener más información sobre los teléfonos de Polycom, consulte [Soluciones de voz para Microsoft](http://www.polycom.com/voice-conferencing-solutions/desktop-ip-phones.html).
  
Para obtener más información sobre los teléfonos de Yealink, consulte [Teléfonos IP para Skype for Business](http://www.yealink.com/products_list_10.html#filter2).
  
Para obtener más detalles en los teléfonos AudioCodes, vea [Skype para teléfonos IP de negocio](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions).
  
> [!NOTE]
> Lync Phone Edition is supported with Skype for Business Online, but not with Microsoft Teams. Mainstream support for the LPE platform ended by April/10/2014, with extended support until April/11/2023 to align with the product support lifecycle of Lync Server 2013. See [Microsoft Product Lifecycle](https://support.microsoft.com/lifecycle/search?qid=&amp;alpha=Lync%20Phone%20Edition&amp;Filter=FilterNO) for details on the LPE lifecycle. LPE CAP models aren't supported with Skype for Business Online.
>
> Later this year, Office 365 will not support any version of TLS older than 1.2. Since the underlying operating system of LPE does not support TLS 1.2, LPE will not be supported to connect to Office 365 anymore. See [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/en-gb/help/4057306/preparing-for-tls-1-2-in-office-365) for more information.
  
## <a name="supported-firmware"></a>Firmware compatible

Esta es la versión de software mínima necesaria para que los teléfonos compatibles funcionen con el Sistema telefónico de Office 365:
  
||||
|:-----|:-----|:-----|
|**Tipo de teléfono** <br/> |**Firmware mínimo** <br/> |**Fecha de lanzamiento** <br/> |
|Optimizado (Lync Phone Edition)  <br/> |4.0.7577.4463  <br/> |Mayo de 2015  <br/> |
|Polycom VVX Series certificado  <br/> |5.4.0A  <br/> |Diciembre de 2015  <br/> |
|Yealink  <br/> |X.8.1.52  <br/> |Febrero de 2017  <br/> |
|AudioCodes  <br/> |3.0.0.459.1  <br/> |Diciembre de 2016  <br/> |

Para obtener más detalles sobre las versiones actuales de firmware certificadas, vea [Skype para teléfonos IP de negocio](https://docs.microsoft.com/skypeforbusiness/certification/devices-ip-phones#conference-phones).

> [!NOTE]
> Los teléfonos Lync Phone Edition (LPE) que configure para su implementación local tienen que estar actualizados con el firmware mínimo necesario (o versiones posteriores) antes de transferir los usuarios a Skype Empresarial Online. Si transfiere los usuarios desde una implementación local a Skype Empresarial Online antes de actualizar el firmware en los teléfonos, esos teléfonos no se podrán conectar a Skype Empresarial. 
  
## <a name="required-licenses"></a>Licencias necesarias

Skype para profesionales Online no requiere ninguna licencia adicional de Microsoft que no sean las licencias de usuario. Para obtener más información acerca de las licencias de usuario necesarias, vea [Skype para profesionales y los equipos de Microsoft complemento licencias](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
  
Fabricante de los modelos de licencia puede variar entre open SIP y Skype para firmware de certificación empresarial. Si va a reutilizar un modelo certificado con un firmware SIP abierto, tendrá que verificar los requisitos de la licencia con el fabricante.
  
## <a name="skype-for-business-online-connected-phones-feature-set"></a>Skype para conjunto de características de teléfonos empresariales en línea conectados

Para funciones y características del dispositivo completa, compruebe las guías de usuario del fabricante.
  
||||||
|:-----|:-----|:-----|:-----|:-----|
|**Característica** <br/> |**3PIP de Polycom** <br/> |**3PIP de Yealink** <br/> |**3PIP de AudioCodes** <br/> |**LPE** <br/> |
|Inicio de sesión con las credenciales del usuario  <br/> |Sí  <br/> |Sí  <br/> |Sí   <br/> |Compatibilidad para reuniones privadas con id. de conferencia de reunión dinámicos  <br/> |
|Inicio de sesión con un equipo (emparejamiento), solo Windows  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |Sí   <br/> |
|Inicio de sesión con (inicio de sesión web)  <br/>  <br/> **Nota:** Comprobación de la matriz de compatibilidad en la Guía de implementación.           |Sí  <br/> |Sí  <br/> |Sí   <br/> |Compatibilidad para reuniones privadas con id. de conferencia de reunión dinámicos  <br/> |
|Unirse a la reunión con un solo clic  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |Sí   <br/> |
|Clic para marcar (emparejamiento)  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |Sí   <br/> |
|Controles de reunión  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |Sí   <br/> |
|Correo de voz visual  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |Sí   <br/> |
|Bloqueo de teléfono  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |Sí   <br/> |
|Actualización de dispositivo  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |Sí   <br/> |
|Aprovisionamiento en banda  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |Sí   <br/> |
|QoE  <br/> |Sí  <br/> |Sí  <br/> |Sí   <br/> |Compatibilidad para reuniones privadas con id. de conferencia de reunión dinámicos  <br/> |
|Carga de registros  <br/> <br/> **Nota:** Actualmente, todos los registros se cargan en el equipo de Microsoft Support solamente; acceso de cliente a los registros de teléfono aún no están disponibles.           |Sí  <br/> |Sí  <br/> |Sí  <br/> |Sí   <br/> |
|Autenticación moderna  <br/> |Sí  <br/> |Sí  <br/> |Sí   <br/> |Compatibilidad para reuniones privadas con id. de conferencia de reunión dinámicos  <br/> |
|Varios números de emergencia  <br/> |No  <br/> |No  <br/> |Página de invitación a la reunión con números de teléfono de acceso telefónico predeterminados  <br/> |Sí  <br/> |
|Integración con el calendario de Exchange*  <br/> |Sí  <br/> |Sí  <br/> |Sí   <br/> |Sí   <br/> <br/> **Nota:** Requiere siempre de PC           |
|Integración de presencia  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |Sí   <br/> |
|Directorio corporativo  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |
|Delegación  <br/> |Sí  <br/> |Sí  <br/> |Sí   <br/> |No  <br/> |
|Integración de imagen de contacto  <br/> |No  <br/> |Sí  <br/> |Compatibilidad para reuniones privadas con id. de conferencia de reunión dinámicos  <br/> |Sí  <br/> |
||||||

     
> [!NOTE]
> Ni el CX 600 ni ningún otro teléfono Aries admite la autenticación multifactor (MFA). Si fuerza la MFA, estos dispositivos no iniciarán sesión. Estos dispositivos solo deben utilizar el id. de organización para la autenticación.
 
## <a name="what-else-should-you-know"></a>¿Qué más tengo que saber?
Para obtener instrucciones detalladas, consulte [Implementación de teléfonos de Skype Empresarial Online](deploying-skype-for-business-online-phones.md).

## <a name="related-topics"></a>Temas relacionados
[Obtener números de teléfono de servicio para Skype Empresarial y Microsoft Teams](../getting-service-phone-numbers.md)

[Esto es lo obtiene con el Sistema telefónico de Office 365](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[Países y regiones donde Audioconferencia y Planes de llamada están disponibles](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

  
 
