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
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Phone System
description: 'Obtenga información sobre qué teléfonos funcionan con Skype for Business de Polycom, HP y Mitel, y las licencias necesarias. '
ms.openlocfilehash: 92a91d97efabeaaebb074e41e41bc9a8812fa0c5
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2018
ms.locfileid: "23780613"
---
# <a name="getting-phones-for-skype-for-business-online"></a>Obtener teléfonos para Skype for Business Online

Skype for Business Online admite y es compatible con los teléfonos de escritorio, para los usuarios que deseen tener una experiencia de teléfono tradicional en lugar de usar la aplicación Skype for Business. En este tema se tratan los teléfonos y las versiones de firmware que son compatibles para su uso en Skype for Business Online y otra información que le ayudarán al configurar teléfonos en su organización.
  
Para obtener las actualizaciones más recientes y la información más actualizada sobre los dispositivos admitidos, consulte el [Catálogo de dispositivos de Skype for Business](http://partnersolutions.skypeforbusiness.com/solutionscatalog).
  
## <a name="supported-phones"></a>Teléfonos compatibles

Para usuarios de Skype for Business Online, puede elegir entre los diversos modelos del conjunto de  *Teléfonos certificados para Skype for Business* y los teléfonos con Lync Phone Edition (LPE) que se enumeran en la categoría Skype for Business Online en el [Catálogo de dispositivos de Skype for Business](http://partnersolutions.skypeforbusiness.com/solutionscatalog).
  
Microsoft se asocia y trabaja en estrecha colaboración con Polycom, Yealink y AudioCodes para desarrollar y certificar una amplia variedad de dispositivos a través del Programa de teléfonos IP de socios (PIP) para el Sistema telefónico de Office 365 y Skype for Business Server.
  
Al solicitar teléfonos nuevos para Skype for Business, es importante comprar dispositivos que tengan la *identificación de producto correcta*. Estas identificaciones de producto garantizan que los teléfonos que recibirá ya tendrán instalada la versión de Skype for Business Online adecuada.
  
|||
|:-----|:-----|
|**Socio fabricante de teléfonos** <br/> |**Identificación de producto específica para Skype for Business** <br/> |
|Polycom  <br/> |Identificación de producto: 019  <br/> |
|Yealink  <br/> |SIP-TXXG versión para Skype Empresarial  <br/> |
|AudioCodes  <br/> |UCXXXHDEG (SfB)  <br/> |
   
Para obtener más información sobre los teléfonos de Polycom, consulte [Soluciones de voz para Microsoft](http://www.polycom.com/voice-conferencing-solutions/desktop-ip-phones.html).
  
Para obtener más información sobre los teléfonos de Yealink, consulte [Teléfonos IP para Skype for Business](http://www.yealink.com/products_list_10.html#filter2).
  
Para obtener más información sobre los teléfonos de AudioCodes, consulte [Teléfonos IP para Skype for Business](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions).
  
> [!NOTE]
> Lync Phone Edition es compatible con Skype for Business Online, pero no con Microsoft Teams. El soporte estándar para la plataforma LPE finalizó el 10 de abril de 2014 y el soporte extendido continuará hasta el 11 de abril de 2023, coincidiendo con el ciclo de vida de soporte técnico del producto de Lync Server 2013. Consulte [Ciclo de vida de productos de Microsoft](https://support.microsoft.com/en-us/lifecycle/search?qid=&amp;alpha=Lync%20Phone%20Edition&amp;Filter=FilterNO) para obtener detalles sobre el ciclo de vida de LPE. Los modelos LPE CAP no son compatibles con Skype for Business Online.
>
> Más adelante en este año, Office 365 no será compatible con ninguna versión de TLS anterior a 1.2. Dado que el sistema operativo subyacente de LPE no admite TLS 1.2, ya no se admitirá la conexión de LPE a Office 365. Para obtener más información, vea [Preparar el uso obligatorio de TLS 1.2 en Office 365](https://support.microsoft.com/en-gb/help/4057306/preparing-for-tls-1-2-in-office-365).
  
## <a name="supported-firmware"></a>Firmware compatible

Esta es la versión de software mínima necesaria para que los teléfonos compatibles funcionen con el Sistema telefónico de Office 365:
  
||||
|:-----|:-----|:-----|
|**Tipo de teléfono** <br/> |**Firmware mínimo** <br/> |**Fecha de publicación** <br/> |
|Optimizado (Lync Phone Edition)  <br/> |4.0.7577.4463  <br/> |Mayo de 2015  <br/> |
|Polycom VVX Series certificado  <br/> |5.4.0A  <br/> |Diciembre de 2015  <br/> |
|Yealink  <br/> |X.8.1.52  <br/> |Febrero de 2017  <br/> |
|AudioCodes  <br/> |3.0.0.459.1  <br/> |Diciembre de 2016  <br/> |
   
> [!NOTE]
Los teléfonos Lync Phone Edition (LPE) que configure para su implementación local tienen que estar actualizados con el firmware mínimo necesario (o versiones posteriores) antes de transferir los usuarios a Skype Empresarial Online. Si transfiere los usuarios desde una implementación local a Skype Empresarial Online antes de actualizar el firmware en los teléfonos, esos teléfonos no se podrán conectar a Skype Empresarial. 
  
## <a name="required-licenses"></a>Licencias necesarias

Skype for Business Online no necesita licencias adicionales de Microsoft, excepto las licencias de usuario. Para más información sobre las licencias de usuario necesarias, vea [Licencias de complementos de Skype for Business y Microsoft Teams](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
  
Los modelos de licencias del fabricante puede variar entre el firmware SIP abierto y el certificado para Skype for Business. Si va a reutilizar un modelo certificado con un firmware SIP abierto, tendrá que verificar los requisitos de la licencia con el fabricante.
  
## <a name="skype-for-business-online-connected-phones-feature-set"></a>Conjunto de características de los teléfonos conectados a Skype for Business Online

Para ver una lista completa de las características y funciones de los dispositivos, consulte las guías de usuario de los fabricantes.
  
||||||
|:-----|:-----|:-----|:-----|:-----|
|**Característica** <br/> |**3PIP de Polycom** <br/> |**3PIP de Yealink** <br/> |**3PIP de AudioCodes** <br/> |**LPE** <br/> |
|Inicio de sesión con las credenciales del usuario  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |No  <br/> |
|Inicio de sesión con un equipo (emparejamiento), solo Windows  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |
|Inicio de sesión con (inicio de sesión web)  <br/>  <br/> **Nota:** compruebe la matriz de compatibilidad en la guía de implementación.           |Sí  <br/> |Sí  <br/> |Sí  <br/> |No  <br/> |
|Unirse a la reunión con un solo clic  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |
|Clic para marcar (emparejamiento)  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |
|Controles de reunión  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |
|Correo de voz visual  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |
|Bloqueo de teléfono  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |
|Actualización de dispositivo  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |
|Aprovisionamiento en banda  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |
|QoE  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |No  <br/> |
|Carga de registros  <br/> <br/> **Nota:** actualmente los registros se cargan solo para el equipo de soporte técnico de Microsoft; el acceso a los registros del teléfono por parte del cliente todavía no está disponible.           |Sí  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |
|Autenticación moderna  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |No  <br/> |
|Varios números de emergencia  <br/> |Sí  <br/> |No  <br/> |No  <br/> |Sí  <br/> |
|Integración con el calendario de Exchange*  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> <br/> **Nota:** requiere tethering en el PC           |
|Integración de presencia  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |
|Directorio corporativo  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |
|Delegación  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |No  <br/> |
|Integración de imagen de contacto  <br/> |No  <br/> |Sí  <br/> |No  <br/> |Sí  <br/> |
||||||

     
> [!NOTE]
> Ni el CX 600 ni ningún otro teléfono Aries admite la autenticación multifactor (MFA). Si fuerza la MFA, estos dispositivos no iniciarán sesión. Estos dispositivos solo deben utilizar el id. de organización para la autenticación.
 
## <a name="what-else-should-you-know"></a>¿Qué más tengo que saber?
Para obtener instrucciones detalladas, consulte [Implementación de teléfonos de Skype for Business Online](deploying-skype-for-business-online-phones.md).

## <a name="related-topics"></a>Temas relacionados
[Obtener números de teléfono de servicio para Skype for Business y Microsoft Teams](../getting-service-phone-numbers.md)

[Esto es lo que conseguirá con Sistema telefónico en Office 365](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[Países y regiones donde la Audioconferencia y los Planes de llamada están disponibles](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

  
 