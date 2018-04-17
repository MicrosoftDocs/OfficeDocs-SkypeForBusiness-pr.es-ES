---
title: Obtener teléfonos con Skype Empresarial Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.date: 01/22/2018
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
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
- Strat_SB_PSTN
description: 'Learn which phones work with Skype for Business from Polycom, HP, and Mitel, and the required licenses. '
ms.openlocfilehash: 6609a0393e2b0f641f843b917f8b14a079aeb923
ms.sourcegitcommit: dea27df69d948b7b9cc017b7023c4013cee8e4d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2018
---
# <a name="getting-phones-for-skype-for-business-online"></a>Obtener teléfonos con Skype Empresarial Online

Skype for Business Online qualifies and supports desktop phones for users who want to have a traditional phone experience, rather than use the Skype for Business app. This topic covers the phones and firmware versions that are supported for use in Skype for Business Online and other information that can help you when you are setting up phones in your organization.
  
To get the latest updates and most up-to-date information on supported devices, see the [Skype for Business Device Catalog](http://partnersolutions.skypeforbusiness.com/solutionscatalog).
  
## <a name="supported-phones"></a>Teléfonos compatibles

For Skype for Business Online users, you can choose from several models within the *Certified for Skype for Business Phones*  and phones running Lync Phone Edition (LPE) listed under the Skype for Business Online category in the [Skype for Business Device Catalog](http://partnersolutions.skypeforbusiness.com/solutionscatalog).
  
Microsoft is partnering and working closely with Polycom, Yealink, and AudioCodes to develop and certify a wide variety of devices through the Partner IP Phone Program (PIP) for the Phone System in Office 365 and Skype for Business Server.
  
When ordering new phones for Skype for Business, it is important to buy phones with the *right product ID*. These product IDs will ensure that the phones you receive have the Skype for Business Online qualified version already installed.
  
|||
|:-----|:-----|
|**Socio fabricante de teléfonos** <br/> |**Identificación de producto específica para Skype Empresarial** <br/> |
|Polycom  <br/> |Identificación de producto: 019  <br/> |
|Yealink  <br/> |SIP-TXXG versión para Skype Empresarial  <br/> |
|AudioCodes  <br/> |UCXXXHDEG (SfB)  <br/> |
   
Para obtener más información sobre los teléfonos de Polycom, consulte [Soluciones de voz para Microsoft](http://www.polycom.com/voice-conferencing-solutions/desktop-ip-phones.html).
  
Para obtener más información sobre los teléfonos de Yealink, consulte [Teléfonos IP para Skype Empresarial](http://www.yealink.com/products_list_10.html#filter2).
  
Para obtener más información sobre los teléfonos de AudioCodes, consulte [Teléfonos IP para Skype Empresarial](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions).
  
> [!NOTE]
> Lync Phone Edition is supported with Skype for Business Online. Mainstream support for LPE platform ended by April/10/2014, with extended support until April/11/2023 to align with the product support lifecycle of Lync Server 2013. See [Microsoft Product Lifecycle](https://support.microsoft.com/en-us/lifecycle/search?qid=&amp;alpha=Lync%20Phone%20Edition&amp;Filter=FilterNO) for details on LPE lifecycle. LPE CAP models aren't supported with Skype for Business Online.
  
## <a name="supported-firmware"></a>Firmware compatible

This is the minimum software release required for supported phones to work with Phone System in Office 365:
  
||||
|:-----|:-----|:-----|
|**Tipo de teléfono** <br/> |**Firmware mínimo** <br/> |**Release date** <br/> |
|Optimizado (Lync Phone Edition)  <br/> |4.0.7577.4463  <br/> |Mayo de 2015  <br/> |
|Polycom VVX Series certificado  <br/> |5.4.0A  <br/> |Diciembre de 2015  <br/> |
|Yealink  <br/> |X.8.1.52  <br/> |Febrero de 2017  <br/> |
|AudioCodes  <br/> |3.0.0.459.1  <br/> |Diciembre de 2016  <br/> |
   
> [!NOTE]
> Los teléfonos Lync Phone Edition (LPE) que configure para su implementación local tienen que estar actualizados con el firmware mínimo necesario (o versiones posteriores) antes de transferir los usuarios a Skype Empresarial Online. Si transfiere los usuarios desde una implementación local a Skype Empresarial Online antes de actualizar el firmware en los teléfonos, esos teléfonos no se podrán conectar a Skype Empresarial. 
  
## <a name="required-licenses"></a>Licencias necesarias

Skype for Business Online doesn't require any additional Microsoft license other than the user licenses. To learn more about the required user licenses, see [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
  
Manufacturer licensing models might vary between open SIP and Skype for Business Certified firmware. Si va a reutilizar un modelo certificado con un firmware SIP abierto, tendrá que verificar los requisitos de la licencia con el fabricante.
  
## <a name="skype-for-business-online-connected-phones-feature-set"></a>Conjunto de características de los teléfonos conectados para Skype Empresarial Online

For full device features and capabilities, check the manufacturer user guides.
  
||||||
|:-----|:-----|:-----|:-----|:-----|
|**Característica** <br/> |**3PIP de Polycom** <br/> |**3PIP de Yealink** <br/> |**3PIP de AudioCodes** <br/> |**LPE** <br/> |
|Inicio de sesión con las credenciales del usuario  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |No  <br/> |
|Inicio de sesión con un equipo (emparejamiento), solo Windows  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |
|Inicio de sesión con (inicio de sesión web)  <br/>  <br/> **Note:** Check the supportability matrix in deployment guide.           |Sí  <br/> |Sí  <br/> |Sí  <br/> |No  <br/> |
|Single-click join meeting  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |
|Clic para marcar (emparejamiento)  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |
|Controles de reunión  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |
|Correo de voz visual  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |
|Bloqueo de teléfono  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |
|Actualización de dispositivo  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |
|Aprovisionamiento en banda  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |
|QoE  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |No  <br/> |
|Carga de registros  <br/> <br/> **Note:** Currently, all logs are uploaded to the Microsoft Support team only; customer access to phone logs aren't yet available.           |Sí  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |
|Autenticación moderna  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |No  <br/> |
|Varios números de emergencia  <br/> |Sí  <br/> |No  <br/> |No  <br/> |Sí  <br/> |
|Integración con el calendario de Exchange*  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> <br/> **Note:** Requires PC tethering           |
|Integración de presencia  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |
|Directorio corporativo  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |
|Delegación  <br/> |Sí  <br/> |Sí  <br/> |Sí  <br/> |No  <br/> |
|Integración de imagen de contacto  <br/> |No  <br/> |Sí  <br/> |No  <br/> |Sí  <br/> |
||||||

    > [!NOTE]
    > CX 600 or any other Aries phones don't support multifactor authentication (MFA). If you force MFA, these devices will fail to sign-in. These devices must use only Org ID for authetication.
   
## <a name="what-else-should-you-know"></a>¿Qué más tengo que saber?
Para obtener instrucciones detalladas, consulte [Implementación de teléfonos de Skype Empresarial Online](deploying-skype-for-business-online-phones.md).

## <a name="related-topics"></a>Temas relacionados
[Obtener números de teléfono de servicio para Skype Empresarial y Microsoft Teams](../getting-service-phone-numbers.md)

[Esto es lo que conseguirá con Sistema telefónico en Office 365](../here-s-what-you-get-with-phone-system.md)

[Países y regiones donde Audioconferencia y Planes de llamada están disponibles](../../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

  
 