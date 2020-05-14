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
description: La identificación de llamadas se puede controlar tanto para llamadas entrantes como salientes de usuarios del sistema telefónico mediante una directiva denominada CallingLineIdentity.
ms.openlocfilehash: 2547e6ca3aed10d112897aa1b24900a479c5c8ef
ms.sourcegitcommit: a7c823f61d9ab88424bad924113d780ce11e509f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "44224213"
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a>Cómo se puede usar la identificación de llamadas en su organización

La identificación de llamadas se puede controlar tanto para llamadas entrantes como salientes de usuarios del sistema telefónico mediante una directiva denominada CallingLineIdentity.
  
La funcionalidad de identificación de llamadas está disponible para todos los usuarios del sistema telefónico con independencia de la conectividad RTC:
  
- Conectividad con RTC en línea
    
- Conectividad con RTC local con Skype Empresarial Cloud Connector Edition (requiere Cloud Connector Edition 1.4.2 y posterior)
    
- Conectividad con RTC local con Skype Empresarial Server (requiere Skype Empresarial Server 2015 CU5 y posterior)
    
> [!NOTE]
> Esta directiva no está disponible en Skype Empresarial 2015 Server. 
  
## <a name="outbound-caller-id"></a>Identificación de llamadas de salida

Hay tres opciones disponibles para la identificación de llamadas RTC salientes:
  
- El número de teléfono asignado al usuario, que es el predeterminado.
    
- A telephone number that is classified as a *service* and *toll-free* number in your Calling Plans in Office 365 telephone number inventory. It is usually assigned to an organizational auto attendant or call queue.
    
- Configurado como anónimo.
    
Sin embargo, no es posible asignar estos tipos de números de teléfono al identificador de llamadas de salida:
  
- Números de teléfono que se clasifican como un *usuario* en el inventario de números de teléfono de los planes de llamadas
    
- Un número de teléfono de Skype Empresarial Server local.
    
Para establecer la identificación de llamadas de salida, consulte [Establecer el identificador de llamada de un usuario](/microsoftteams/set-the-caller-id-for-a-user).
  
### <a name="end-user-control-of-outbound-caller-id"></a>Control del usuario final de la identificación de llamadas salientes

El atributo EnableUserOverride permite a los usuarios únicos o múltiples cambiar la configuración de identificación de llamadas a **anónimo**. Esto solo se aplica cuando una directiva de CallingLineIdentity está configurada con un parámetro CallingIDSubstitute de LineURI o sustituto. El valor predeterminado de EnableUserOverride es false.
  
Los usuarios finales pueden establecer la identificación de llamadas en **anónimo** mediante la pestaña **configuración** del cliente de escritorio de Skype empresarial, seleccione **llamadas a un usuario final** (si lo habilita el administrador) y, a continuación, seleccione **ocultar mi número de teléfono y la información del perfil para todas las llamadas**. En Teams, los usuarios pueden ir a su imagen de perfil en la esquina superior derecha **Settings**, seleccionar  >  **llamadas**de configuración y, a continuación, en **identificación de llamadas**, seleccionar **ocultar mi número de teléfono y la información del perfil para todas las llamadas**.
  
||||
|:-----|:-----|:-----|
|**Windows** <br/> |**Versión** <br/> |**Compatible** <br/> |
|Hacer clic y ejecutar  <br/> |Canal actual publicado el 6 de diciembre de 2016 - Versión 1611 (Compilación 7571.2072)  <br/> |Sí  <br/> |
|Hacer clic y ejecutar  <br/> |Primera versión para el Canal diferido publicada el 22 de febrero de 2017 - Versión 1701 (Compilación 7766.2060)  <br/> |Sí  <br/> |
|Hacer clic y ejecutar  <br/> |Canal diferido publicado el 13 de junio de 2017 - versión 1701 (compilación 7766.2092)  <br/> |Sí  <br/> |
|MSI  <br/> |Skype for Business  <br/> |No  <br/> |
|Mac  <br/> |Skype Empresarial  <br/> |No  <br/> |
   
## <a name="inbound-caller-id"></a>IDENTIFICACIÓN de llamadas entrantes

El sistema telefónico mostrará el identificador denominado para un número de teléfono externo si el número está asociado con un usuario en Azure AD. Si el número de teléfono no está en Azure AD, se mostrará el nombre para mostrar proporcionado por Telco, si está disponible.

El atributo BlockIncomingCallerID permite bloquear la identificación de llamadas en las llamadas RTC de entrada. Puede establecer este atributo, pero no está disponible para los usuarios finales en la página Configuración de usuario. En este momento está solo disponible con la conectividad con RTC en línea.
  
Para establecer la identificación de llamadas de salida, consulte [Establecer el identificador de llamada de un usuario](/microsoftteams/set-the-caller-id-for-a-user).
  
## <a name="related-topics"></a>Temas relacionados
[Preguntas comunes sobre la transferencia de números de teléfono](/microsoftteams/transferring-phone-numbers-common-questions)

[Diferentes tipos de números de teléfono que se usan para Planes de llamada](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[Administrar los números de teléfono para su organización](/microsoftteams/manage-phone-numbers-for-your-organization)

[Términos y condiciones de las llamadas de emergencia](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype Empresarial Online: Etiqueta de aviso de declinación de responsabilidades de las llamadas de emergencia](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 
