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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Phone System
description: 'Obtenga información sobre qué teléfonos funcionan con Skype for Business de Polycom, HP y Mitel, y las licencias necesarias. '
ms.openlocfilehash: 4b4a5e48a531a694b006126221ddc7fcba40e1c3
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2021
ms.locfileid: "60013154"
---
# <a name="getting-phones-for-skype-for-business-online"></a>Obtener teléfonos para Skype for Business Online

[!INCLUDE [sfbo-retirement](../../../Hub/includes/sfbo-retirement.md)]

Skype Empresarial Online cumple los requisitos y es compatible con los teléfonos de escritorio para los usuarios que desean tener una experiencia de teléfono tradicional, en lugar de usar Skype Empresarial aplicación. En este tema se tratan los teléfonos y las versiones de firmware que se admiten para su uso en Skype Empresarial Online y otra información que puede ayudarle al configurar teléfonos en su organización.

> [!NOTE]
> Skype Para empresas se reemplazará lentamente por Microsoft Teams como el método de comunicación principal en Microsoft 365 y Office 365.  Vea [Una nueva visión para las comunicaciones inteligentes en Office 365](https://www.microsoft.com/microsoft-365/blog/2017/09/25/a-new-vision-for-intelligent-communications-in-office-365/) para obtener más información.
>
>Para obtener las actualizaciones más recientes y la información más actualizada en los dispositivos compatibles, vea los Microsoft Teams para [comunicaciones inteligentes.](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)
  
## <a name="supported-phones"></a>Teléfonos compatibles
  
Microsoft se asocia y trabaja estrechamente con Polycom, Yealink y AudioCodes para desarrollar y certificar una amplia variedad de dispositivos a través del Partner IP Teléfono Program (PIP) para el Sistema telefónico.
  
Al solicitar teléfonos nuevos para Skype Empresarial, es importante comprar teléfonos con el *id. de producto adecuado.* Estos IDs de producto garantizarán que los teléfonos que recibas tengan la Skype Empresarial versión calificada en línea ya instalada.
  
|Socio fabricante de teléfonos  |Identificación de producto específica para Skype for Business  |
|:-----|:-----|
|Polycom   |Identificación de producto: 019   |
|Yealink   |SIP-TXXG versión para Skype Empresarial   |
|AudioCodes   |UCXXXHDEG (SfB)   |
   
Para obtener más información sobre los teléfonos Polycom, vea [Biblioteca de documentación poly.](https://documents.polycom.com/category/voice)
  
Para obtener más información sobre los teléfonos de Yealink, consulte [Teléfonos IP para Skype for Business](http://www.yealink.com/products_list_10.html#filter2).
  
Para obtener más información sobre los teléfonos AudioCodes, [vea Skype Empresarial teléfonos IP.](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions)
  
> [!NOTE]
> Lync Phone Edition es compatible con Skype for Business Online, pero no con Microsoft Teams. El soporte estándar para la plataforma LPE finalizó el 10 de abril de 2014 y el soporte extendido continuará hasta el 11 de abril de 2023, coincidiendo con el ciclo de vida de soporte técnico del producto de Lync Server 2013. Consulte [Ciclo de vida de productos de Microsoft](https://support.microsoft.com/lifecycle/search?qid=&amp;alpha=Lync%20Phone%20Edition&amp;Filter=FilterNO) para obtener detalles sobre el ciclo de vida de LPE. Los modelos LPE CAP no son compatibles con Skype for Business Online.
>
> A finales de este año, Office 365 no admitirá ninguna versión de TLS anterior a 1.2. Dado que el sistema operativo subyacente de LPE no admite TLS 1.2, ya no se admitirá la conexión de LPE a Office 365. Para obtener más información, vea [Preparar el uso obligatorio de TLS 1.2 en Office 365](https://support.microsoft.com/en-gb/help/4057306/preparing-for-tls-1-2-in-office-365).
  
## <a name="supported-firmware"></a>Firmware compatible

Esta es la versión mínima de software necesaria para que los teléfonos compatibles funcionen con Sistema telefónico:
  

|Tipo de teléfono |Firmware mínimo |Fecha de lanzamiento |
|:-----|:-----|:-----|
|Optimizado (Lync Phone Edition)   |4.0.7577.4463   |Mayo de 2015   |
|Polycom VVX Series certificado   |5.4.0A   |Diciembre de 2015   |
|Yealink   |X.8.1.52   |Febrero de 2017   |
|AudioCodes   |3.0.0.459.1   |Diciembre de 2016   |

Para obtener más información sobre las versiones de firmware certificadas actuales, [vea Skype Empresarial teléfonos IP.](../../../SfbPartnerCertification/certification/devices-ip-phones.md)

> [!NOTE]
> Los teléfonos Lync Phone Edition (LPE) que configure para su implementación local tienen que estar actualizados con el firmware mínimo necesario (o versiones posteriores) antes de transferir los usuarios a Skype Empresarial Online. Si transfiere los usuarios desde una implementación local a Skype Empresarial Online antes de actualizar el firmware en los teléfonos, esos teléfonos no se podrán conectar a Skype Empresarial. 
  
## <a name="required-licenses"></a>Licencias necesarias

Skype Empresarial Online no requiere ninguna licencia adicional de Microsoft que no sea la licencia de usuario. Para obtener más información sobre las licencias de usuario necesarias, [vea Skype Empresarial y Microsoft Teams de complementos.](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
Los modelos de licencias del fabricante pueden variar entre sip abierto y Skype Empresarial firmware certificado. Si va a reutilizar un modelo certificado con un firmware SIP abierto, tendrá que verificar los requisitos de la licencia con el fabricante.
  
## <a name="skype-for-business-online-connected-phones-feature-set"></a>Skype Empresarial Conjunto de características de teléfonos conectados en línea

Para obtener características y funcionalidades completas del dispositivo, consulte las guías de usuario del fabricante.
  

|Característica  |3PIP de Polycom  |3PIP de Yealink |3PIP de AudioCodes |LPE |
|:-----|:-----|:-----|:-----|:-----|
|Inicio de sesión con las credenciales del usuario   |Sí  |Sí   |Sí   |No   |
|Inicio de sesión con un equipo (emparejamiento), solo Windows   |Sí   |Sí   |Sí   |Sí   |
|Inicio de sesión con (inicio de sesión web)  <br/>  <br/> **Nota:** Compruebe la matriz de compatibilidad en la guía de implementación.  |Sí   |Sí   |Sí   |No   |
|Unirse a la reunión con un solo clic   |Sí   |Sí   |Sí   |Sí   |
|Clic para marcar (emparejamiento)   |Sí   |Sí   |Sí   |Sí > |
|Controles de reunión   |Sí   |Sí   |Sí   |Sí   |
|Correo de voz visual   |Sí   |Sí   |Sí   |Sí   |
|Bloqueo de teléfono   |Sí   |Sí   |Sí   |Sí   |
|Actualización de dispositivo   |Sí   |Sí   |Sí   |Sí   |
|Aprovisionamiento en banda   |Sí   |Sí   |Sí   |Sí   |
|QoE   |Sí   |Sí   |Sí   |No  |
|Carga de registros  <br/> <br/> **Nota:** Actualmente, todos los registros se cargan solo en el equipo de soporte técnico de Microsoft; el acceso de los clientes a los registros telefónicos aún no está disponible.           |Sí   |Sí   |Sí   |Sí   |
|Autenticación moderna   |Sí   |Sí   |Sí   |No   |
|Varios números de emergencia   |Sí   |No   |No   |Sí   |
|Integración con el calendario de Exchange*   |Sí   |Sí   |Sí   |Sí  <br/> <br/> **Nota:** Requiere tethering de PC           |
|Integración de presencia   |Sí   |Sí   |Sí   |Sí   |
|Directorio corporativo   |Sí   |Sí   |Sí   |Sí   |
|Delegación   |Sí   |Sí   |Sí   |No   |
|Integración de imagen de contacto   |No   |Sí  |No   |Sí   |


     
> [!NOTE]
> Ni el CX 600 ni ningún otro teléfono Aries admite la autenticación multifactor (MFA). Si fuerza la MFA, estos dispositivos no iniciarán sesión. Estos dispositivos solo deben utilizar el id. de organización para la autenticación.
 
## <a name="what-else-should-you-know"></a>¿Qué más tengo que saber?
Para obtener instrucciones detalladas, consulte [Implementación de teléfonos de Skype Empresarial Online](deploying-skype-for-business-online-phones.md).

## <a name="related-topics"></a>Temas relacionados
[Obtener números de teléfono de servicio para Skype Empresarial y Microsoft Teams](/microsoftteams/getting-service-phone-numbers)

[Esto es lo obtiene con el Sistema telefónico](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[Países y regiones donde Audioconferencia y Planes de llamada están disponibles](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

  
