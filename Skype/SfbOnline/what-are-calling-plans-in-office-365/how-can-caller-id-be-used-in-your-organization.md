---
title: Cómo se puede usar la identificación de llamadas en su organización
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.assetid: 5a0bd8ba-3334-46ee-becf-1025597737f6
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
- Calling Plans
description: Identificador de autor de la llamada se puede controlar mediante el uso de una directiva denominada CallingLineIdentity para las llamadas entrantes y salientes para los usuarios del sistema telefónico.
ms.openlocfilehash: a1a809805b96152e4b205c8f38b3c8409014eb55
ms.sourcegitcommit: 2c084358844f02fbf7953f2ea49ed6d710cbf06f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2018
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
    
- Inventario de número de un número de teléfono que se clasifica como un *servicio* y el número de *gratuito* en su llamada planes en teléfono de Office 365. Normalmente, se asigna a una cola de llamada o de operador automático organizativa.
    
- Configurado como anónimo.
    
Sin embargo, no es posible asignar estos tipos de números de teléfono al identificador de llamadas de salida:
  
- Los números de teléfono que se clasifican como un *usuario* en su teléfono de planes de llamar al número de inventario
    
- Un número de teléfono de Skype Empresarial Server local.
    
Para establecer la identificación de llamadas de salida, consulte [Establecer el identificador de llamada de un usuario](set-the-caller-id-for-a-user.md).
  
### <a name="end-user-control-of-outbound-caller-id"></a>Control de usuario final para la identificación de llamadas de salida

El atributo EnableUserOverride permite a los usuarios de un o varias cambiar su configuración del identificador de autor de la llamada a **anónimo**. Esto sólo se aplica cuando se configura una directiva de CallingLineIdentity con un parámetro de CallingIDSubstitute de LineURI o sustituto. El valor predeterminado de EnableUserOverride es False.
  
Los usuarios finales puede establecer su identificador de autor de la llamada a **anónimo** mediante el uso de la ficha **Llamada configuración hacia delante** en el Skype para el cliente de escritorio empresarial.
  
||||
|:-----|:-----|:-----|
|**Windows** <br/> |**Versión** <br/> |**Compatible** <br/> |
|Hacer clic y ejecutar  <br/> |Canal actual publicado el 6 de diciembre de 2016 - Versión 1611 (Compilación 7571.2072)  <br/> |Sí  <br/> |
|Hacer clic y ejecutar  <br/> |Primera versión para el Canal diferido publicada el 22 de febrero de 2017 - Versión 1701 (Compilación 7766.2060)  <br/> |Sí  <br/> |
|Hacer clic y ejecutar  <br/> |Aplazado canal publicado en el 13 de junio de 2017 - versión 1701 (compilación 7766.2092)  <br/> |Sí  <br/> |
|MSI  <br/> |Skype Empresarial  <br/> |No  <br/> |
|Mac  <br/> |Skype Empresarial  <br/> |No  <br/> |
   
## <a name="inbound-caller-id"></a>Identificación de llamadas de entrada

Permite que el atributo BlockIncomingCallerID para bloquear el identificador de autor de la llamada en las llamadas RTC entrantes. Puede establecer este atributo, pero no está disponible para los usuarios finales en la página de configuración de usuario. En este momento está solo disponible con la conectividad con RTC en línea.
  
Para establecer la identificación de llamadas de salida, consulte [Establecer el identificador de llamada de un usuario](set-the-caller-id-for-a-user.md).
  
## <a name="related-topics"></a>Temas relacionados
[Preguntas comunes sobre la transferencia de números de teléfono](transferring-phone-numbers-common-questions.md)

[Diferentes tipos de números de teléfono que se usan para Planes de llamada](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Administrar los números de teléfono para su organización](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[Términos y condiciones de las llamadas de emergencia](../legal-and-regulatory/emergency-calling-terms-and-conditions.md)

[Skype Empresarial Online: Etiqueta de aviso de declinación de responsabilidades de las llamadas de emergencia](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 