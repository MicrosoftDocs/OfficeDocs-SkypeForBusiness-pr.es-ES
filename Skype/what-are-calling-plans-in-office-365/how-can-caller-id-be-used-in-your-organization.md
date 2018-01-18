---
title: "Identificador de uso en su organización"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 5a0bd8ba-3334-46ee-becf-1025597737f6
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Calling Plans
- Strat_SB_PSTN
description: "Identificador de llamadas puede controlarse en llamadas entrantes y salientes para los usuarios del sistema de teléfono utilizando una directiva denominada CallingLineIdentity."
ms.openlocfilehash: b9e889ae9d87277939e844eeb911834f466942c5
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2017
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a>Identificador de uso en su organización

Identificador de llamadas puede controlarse en llamadas entrantes y salientes para los usuarios del sistema de teléfono utilizando una directiva denominada CallingLineIdentity.
  
La funcionalidad de identificador de llamadas está disponible para todos los usuarios del sistema telefónico independientemente de conectividad RTC:
  
- Conectividad RTC en línea
    
- Conectividad de RTC local con Skype para conector de nube Business Edition (requiere nube conector Edition 1.4.2 y posteriores)
    
- Conectividad de RTC local con Skype para Business Server (requiere Skype para Business Server 2015 CU5 y posteriores)
    
> [!NOTE]
> Esta directiva no está disponible en Skype para Business Server de 2015. 
  
## <a name="outbound-caller-id"></a>Identificador de llamada saliente

Hay tres opciones disponibles para el identificador de llamadas salientes de RTC:
  
- El número de teléfono asignado al usuario, que es el predeterminado.
    
- Un número de teléfono que se clasifica como un *servicio* y número de *línea gratuita* en sus planes de llamar en Office 365 teléfono número de inventario. Normalmente se asigna a una cola de operador o llamada de organización automática.
    
- Establece en anónimo.
    
Sin embargo, no puede asignar a estos tipos de números de teléfono para el identificador de llamadas salientes:
  
- Número de los números de teléfono que se clasifican como un *usuario* de su teléfono llamando a los planes de inventario
    
- Un Skype para Business Server número de teléfono local
    
Para establecer el identificador de llamadas salientes, vea [establecer el identificador de un usuario](set-the-caller-id-for-a-user.md).
  
### <a name="end-user-control-of-outbound-caller-id"></a>Control de usuario final de identificador de llamadas salientes

El atributo EnableUserOverride permite a los usuarios de uno o varios cambiar su configuración del identificador de llamadas a **anónimo**. Esto sólo se aplica cuando se configura una directiva de CallingLineIdentity con un parámetro de CallingIDSubstitute de LineURI o sustituto. El valor predeterminado de EnableUserOverride es False.
  
Los usuarios finales puede establecer su identificador a **anónimo** mediante la ficha **Llamar configuración hacia delante** en el Skype para cliente de escritorio de negocios.
  
||||
|:-----|:-----|:-----|
|**Windows** <br/> |**Versión** <br/> |**Admite** <br/> |
|Hacer clic y ejecutar  <br/> |Canal actual versión de 6 de diciembre de 2016 - 1611 (Build 7571.2072)  <br/> |Sí  <br/> |
|Hacer clic y ejecutar  <br/> |Primera versión para canal aplazado lanzado el 22 de febrero de 2017 - versión 1701 (Build 7766.2060)  <br/> |Sí  <br/> |
|Hacer clic y ejecutar  <br/> |Deferred canal lanzado el 13 de junio de 2017 - versión 1701 (Build 7766.2092)  <br/> |Sí  <br/> |
|MSI  <br/> |Skype Empresarial  <br/> |No  <br/> |
|Mac  <br/> |Skype Empresarial  <br/> |No  <br/> |
   
## <a name="inbound-caller-id"></a>Identificador de llamadas entrantes

El atributo BlockIncomingCallerID permite bloquear el identificador de llamadas en las llamadas entrantes de PSTN. Puede establecer este atributo, pero no está disponible para los usuarios finales en la página de configuración de usuario. Y actualmente sólo está disponible con conectividad PSTN en línea.
  
Para establecer el identificador de llamadas salientes, vea [establecer el identificador de un usuario](set-the-caller-id-for-a-user.md).
  
## <a name="related-topics"></a>Temas relacionados
[Transferencia de preguntas habituales de los números de teléfono](transferring-phone-numbers-common-questions.md)

[Diferentes tipos de números de teléfono utilizados para llamar a planes](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Administrar números de teléfono de la organización](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[Términos y condiciones de las llamadas de emergencias](emergency-calling-terms-and-conditions.md)

[Skype para los negocios en línea: etiqueta de descargo de responsabilidad llamada de emergencia](https://go.microsoft.com/fwlink/?LinkID=692099)