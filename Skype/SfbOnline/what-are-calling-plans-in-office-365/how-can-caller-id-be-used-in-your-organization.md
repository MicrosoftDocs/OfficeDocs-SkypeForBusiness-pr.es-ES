---
title: Cómo se puede usar la identificación de llamadas en su organización
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.assetid: 5a0bd8ba-3334-46ee-becf-1025597737f6
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
- Calling Plans
description: Identificador de autor de la llamada se puede controlar mediante el uso de una directiva denominada CallingLineIdentity para las llamadas entrantes y salientes para los usuarios del sistema telefónico.
ms.openlocfilehash: df6c7c053b5dce4ffb1d121a1adbf829efda9943
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32229891"
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a>Cómo se puede usar la identificación de llamadas en su organización

Identificador de autor de la llamada se puede controlar mediante el uso de una directiva denominada CallingLineIdentity para las llamadas entrantes y salientes para los usuarios del sistema telefónico.
  
La funcionalidad de identificador de autor de la llamada está disponible para todos los usuarios del sistema telefónico independientemente de la conectividad de RTC:
  
- Conectividad con RTC en línea
    
- Conectividad con RTC local con Skype Empresarial Cloud Connector Edition (requiere Cloud Connector Edition 1.4.2 y posterior)
    
- Conectividad con RTC local con Skype Empresarial Server (requiere Skype Empresarial Server 2015 CU5 y posterior)
    
> [!NOTE]
> Esta directiva no está disponible en Skype Empresarial 2015 Server. 
  
## <a name="outbound-caller-id"></a>Identificación de llamadas de salida

Hay tres opciones disponibles para la identificación de llamadas RTC de salida:
  
- El número de teléfono asignado al usuario, que es el valor predeterminado.
    
- A telephone number that is classified as a *service* and *toll-free* number in your Calling Plans in Office 365 telephone number inventory. It is usually assigned to an organizational auto attendant or call queue.
    
- Configurado como anónimo.
    
Sin embargo, no es posible asignar estos tipos de números de teléfono al identificador de llamadas de salida:
  
- Los números de teléfono que se clasifican como un *usuario* en su teléfono de planes de llamar al número de inventario
    
- Un número de teléfono de Skype Empresarial Server local.
    
Para establecer la identificación de llamadas de salida, consulte [Establecer el identificador de llamada de un usuario](set-the-caller-id-for-a-user.md).
  
### <a name="end-user-control-of-outbound-caller-id"></a>Control de usuario final para la identificación de llamadas de salida

The EnableUserOverride attribute enables single or multiple users to change their Caller ID setting to **Anonymous**. This only applies when a CallingLineIdentity policy is configured with a CallingIDSubstitute parameter of either LineURI or Substitute. The default value of EnableUserOverride is False.
  
Los usuarios finales pueden establecer su identificador de autor de la llamada a **anónimo** mediante la ficha **configuración** en el Skype para el cliente de escritorio empresarial, seleccione **llamadas a un usuario final** (si se habilita por admin), seleccione información del perfil y el número de **Ocultar Mi teléfono para todas las llamadas **.
  
||||
|:-----|:-----|:-----|
|**Windows** <br/> |**Versión** <br/> |**Compatible** <br/> |
|Hacer clic y ejecutar  <br/> |Canal actual publicado el 6 de diciembre de 2016 - Versión 1611 (Compilación 7571.2072)  <br/> |Sí  <br/> |
|Hacer clic y ejecutar  <br/> |Primera versión para el Canal diferido publicada el 22 de febrero de 2017 - Versión 1701 (Compilación 7766.2060)  <br/> |Sí  <br/> |
|Hacer clic y ejecutar  <br/> |Canal diferido publicado el 13 de junio de 2017 - versión 1701 (compilación 7766.2092)  <br/> |Sí  <br/> |
|MSI  <br/> |Skype for Business  <br/> |No  <br/> |
|Mac  <br/> |Skype Empresarial  <br/> |No  <br/> |
   
## <a name="inbound-caller-id"></a>Identificación de llamadas de entrada

The BlockIncomingCallerID attribute allows for blocking the caller ID on incoming PSTN calls. You can set this attribute, but it isn't available to your end users on the user settings page. And it is currently available only with Online PSTN connectivity.
  
Para establecer la identificación de llamadas de salida, consulte [Establecer el identificador de llamada de un usuario](set-the-caller-id-for-a-user.md).
  
## <a name="related-topics"></a>Temas relacionados
[Preguntas comunes sobre la transferencia de números de teléfono](/microsoftteams/transferring-phone-numbers-common-questions)

[Diferentes tipos de números de teléfono que se usan para Planes de llamada](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[Administrar los números de teléfono para su organización](/microsoftteams/manage-phone-numbers-for-your-organization)

[Términos y condiciones de las llamadas de emergencia](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype for Business Online: Etiqueta de aviso de declinación de responsabilidades de las llamadas de emergencia](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 
