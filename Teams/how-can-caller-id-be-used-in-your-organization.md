---
title: Cómo se puede usar la identificación de llamadas en su organización
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.assetid: 5a0bd8ba-3334-46ee-becf-1025597737f6
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- ms.teamsadmincenter.voice.callerid.overview
description: La identificación de llamadas se puede controlar para las llamadas entrantes y salientes de usuarios de Sistema telefónico mediante una directiva llamada CallingLineIdentity.
ms.openlocfilehash: cd2074fec3027f1172b6ea681013f53994963cb5
ms.sourcegitcommit: 2874aec7768bb46ed4506c1a2d431841f47190bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2020
ms.locfileid: "47255453"
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a>Cómo se puede usar la identificación de llamadas en su organización

La identificación de llamadas se puede controlar para las llamadas entrantes y salientes de usuarios de Sistema telefónico mediante una directiva llamada CallingLineIdentity.
  
La funcionalidad de identificación de llamadas está disponible para todos los usuarios del sistema telefónico independientemente de la conectividad con RTC:

- Planes de llamadas de Microsoft 

- Enrutamiento directo del sistema telefónico 
  
- Conectividad con RTC en línea
    
- Conectividad con RTC local con Skype Empresarial Cloud Connector Edition (requiere Cloud Connector Edition 1.4.2 y posterior)
    
- Conectividad con RTC local con Skype Empresarial Server (requiere Skype Empresarial Server 2015 CU5 y posterior)
    
> [!NOTE]
> Esta directiva no está disponible en Skype Empresarial 2015 Server. 
  
## <a name="outbound-caller-id"></a>Identificación de llamadas de salida

Hay tres opciones disponibles para la identificación de llamadas RTC de salida:
  
- El número de teléfono asignado al usuario, que es el valor predeterminado.
    
- Un número de teléfono que  está clasificado como servicio *y* número gratuito en el inventario de números de teléfono de los planes de llamadas. Normalmente, se asigna a una cola de llamadas o de operador automático organizativos.
    
- Configurado como anónimo.
    
Sin embargo, no es posible asignar estos tipos de números de teléfono al identificador de llamadas de salida:
  
- Cualquier número de teléfono clasificado como usuario  *en el*  inventario de números de teléfono de planes de llamadas
    
- Un número de teléfono de Skype Empresarial Server local.
    
Para establecer la identificación de llamadas de salida, consulte [Establecer el identificador de llamada de un usuario](/microsoftteams/set-the-caller-id-for-a-user).
  
### <a name="end-user-control-of-outbound-caller-id"></a>Control de usuario final de identificador de llamada saliente

El atributo EnableUserOverride permite que uno o varios usuarios cambien su configuración de identificador de llamada a **Anónimo.** Esto solo se aplica cuando una directiva de CallingLineIdentity se configura con un parámetro CallingIDSubstitute de LineURI o Substitute. El valor predeterminado de EnableUserOverride es False.
  
Los usuarios finales pueden  establecer su  identificador de llamada en Anónimo mediante la pestaña Configuración del cliente de escritorio de Skype Empresarial, seleccionar Llamadas a un usuario final **(si** el administrador lo ha habilitado) y, a continuación, seleccionar Ocultar mi número de teléfono y la información de perfil para todas las **llamadas.** En Teams, los usuarios pueden ir a su imagen de perfil en la esquina superior derecha, seleccionar Llamadas de configuración y, a continuación, en Identificador de llamada, seleccionar Ocultar mi número de teléfono e información de perfil para todas las  >   **llamadas.** 
  
||||
|:-----|:-----|:-----|
|**Windows** <br/> |**Versión** <br/> |**Compatible** <br/> |
|Hacer clic y ejecutar  <br/> |Canal actual publicado el 6 de diciembre de 2016 - Versión 1611 (Compilación 7571.2072)  <br/> |Sí  <br/> |
|Hacer clic y ejecutar  <br/> |Primera versión para el Canal diferido publicada el 22 de febrero de 2017 - Versión 1701 (Compilación 7766.2060)  <br/> |Sí  <br/> |
|Hacer clic y ejecutar  <br/> |Canal diferido publicado el 13 de junio de 2017 - versión 1701 (compilación 7766.2092)  <br/> |Sí  <br/> |
|MSI  <br/> |Skype Empresarial  <br/> |No  <br/> |
|Mac  <br/> |Skype Empresarial  <br/> |No  <br/> |
   
## <a name="inbound-caller-id"></a>Identificación de llamadas entrantes

Sistema telefónico mostrará el id. de un número de teléfono externo si el número está asociado a un usuario en Azure AD. Si el número de teléfono no está en Azure AD, se mostrará el nombre para mostrar proporcionado por telco si está disponible.

El atributo BlockIncomingCallerID permite bloquear la identificación de llamadas en las llamadas RTC de entrada. Puede establecer este atributo, pero no está disponible para los usuarios finales en la página de configuración de usuario. En este momento está solo disponible con la conectividad con RTC en línea.
  
Para establecer la identificación de llamadas de salida, consulte [Establecer el identificador de llamada de un usuario](/microsoftteams/set-the-caller-id-for-a-user).
  
## <a name="related-topics"></a>Temas relacionados
[Preguntas comunes sobre la transferencia de números de teléfono](/microsoftteams/transferring-phone-numbers-common-questions)

[Diferentes tipos de números de teléfono que se usan para Planes de llamada](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[Administrar los números de teléfono para su organización](/microsoftteams/manage-phone-numbers-for-your-organization)

[Términos y condiciones de las llamadas de emergencia](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype Empresarial Online: Etiqueta de aviso de declinación de responsabilidades de las llamadas de emergencia](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 
