---
title: Cómo se puede usar la identificación de llamadas en su organización
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: jens, roykuntz
ms.topic: article
ms.assetid: 5a0bd8ba-3334-46ee-becf-1025597737f6
ms.tgt.pltfrm: cloud
search.appverid: MET150
ms.collection:
- M365-voice
ms.service: msteams
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
description: El identificador de llamadas se puede controlar tanto para las llamadas entrantes como salientes para Sistema telefónico usuarios mediante una directiva denominada CallingLineIdentity.
ms.openlocfilehash: 43d3d6633ca46485aa111a7d97b9bd37b0547818
ms.sourcegitcommit: 02e243d6c58eab463a00ed45dadd80112087006e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/02/2021
ms.locfileid: "52723551"
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a>Cómo se puede usar la identificación de llamadas en su organización

El identificador de llamada consta de dos partes de información identificables para el usuario:

- Un número de teléfono (normalmente conocido como CLID o id. de línea de llamada). Este es el número de teléfono conmutado público (RTC) que se presenta como la identificación del autor de la llamada.

- Un nombre de entidad de llamada (normalmente conocido como CNAM). 
  
La funcionalidad de identificador de llamada está disponible para todos los Sistema telefónico usuarios independientemente de la opción de conectividad RTC:

- Planes de llamadas de Microsoft 

- Enrutamiento directo del sistema telefónico 
  
Puede controlar el identificador de llamadas para las llamadas entrantes y salientes mediante una directiva denominada CallingLineIdentity. Para obtener más información, vea Más información sobre el identificador [de línea de llamadas y el nombre de la parte de llamadas.](more-about-calling-line-id-and-calling-party-name.md)

  
## <a name="outbound-pstn-caller-id"></a>Identificador de llamada RTC saliente

Para el identificador de llamada RTC saliente, están disponibles las siguientes opciones. 
  
- El número de teléfono asignado al usuario, que es el predeterminado.

- Anónimo, que está disponible quitando la presentación del número RTC del usuario. 

- Un número de teléfono sustituto, que puede ser:

  - Un número de teléfono que se clasifica como servicio y número gratuito en el inventario de números de teléfono planes de llamadas. Normalmente se asigna a un Teams Operador automático o cola de llamadas.

  - Un número de teléfono local a través del enrutamiento directo que se asigna a una cuenta de recursos usada por una Teams Operador automático o cola de llamadas. 

- El nombre de la parte de llamada o CNAM establecido en la llamada RTC saliente.  
    
Para obtener más información, vea [Establecer el identificador de llamada de un usuario.](./set-the-caller-id-for-a-user.md)
  
### <a name="end-user-control-of-outbound-caller-id"></a>Control de usuario final del identificador de llamada saliente

Los usuarios pueden cambiar su configuración de identificador de llamada a **Anónimo** estableciendo el atributo EnableUserOverride. 

Si el identificador de llamada saliente se establece en Anónimo, EnableUserOverride no tiene ningún efecto y el identificador de llamada siempre se establece en Anónimo. El valor predeterminado de EnableUserOverride es False.

Los usuarios finales pueden establecer su identificador de llamada en Anónimo yendo **a Configuración > Llamadas** y, a continuación, en Identificador de llamada, seleccione Ocultar mi número de teléfono e información de perfil para todas las **llamadas.** 

### <a name="notes"></a>Notas

Tenga en cuenta lo siguiente:

- No puede asignar los siguientes tipos de números de teléfono para el identificador de llamada saliente:

  - Cualquier número de teléfono que se clasifique como usuario en el inventario de números de teléfono planes de llamadas.

  - Cualquier número de teléfono local mediante enrutamiento directo asignado a un usuario.

  - Un Skype Empresarial Server de teléfono local.

- El uso de la sustitución de números de teléfono de cuenta de recursos solo funciona para Teams usuarios. La sustitución del número de teléfono de servicio funciona tanto para Skype Empresarial en línea como Teams usuarios.

- El nombre de la persona que llama solo se envía en las llamadas en las que el identificador de llamada se sustituye por LineUri, un número de teléfono de cuenta de servicio o recurso y cuando el autor de la llamada es Teams usuario.

- El nombre de la persona que llama puede tener un máximo de 200 caracteres, pero los sistemas descendentes pueden admitir menos caracteres.

- Para enrutamiento directo, la sustitución de números de teléfono y el nombre de la parte que llama se envían en el encabezado DE SIP. Si el correspondiente OnlinePstnGateway está configurado con ForwardPai = True, el encabezado SIP P-ASSERTED-IDENTITY contendrá el usuario real de las llamadas.

- EnableUserOverride tiene prioridad sobre otras opciones de configuración de la directiva, a menos que la sustitución se establezca en Anónimo. Por ejemplo, supongamos que la instancia de directiva ha sustituido con una cuenta de recursos y el usuario establece y habilita EnableUserOverride. En este caso, se bloqueará el identificador de llamada saliente y se usará Anónimo. Si una instancia de directiva tiene establecido el valor de sustitución en Anónimo y EnableUserOverride, el identificador de llamada saliente siempre será Anónimo, independientemente de la configuración del usuario final.

   
## <a name="inbound-caller-id"></a>Id. de llamada entrante

Sistema telefónico mostrará el número de teléfono externo entrante como identificador de llamada. Si el número está asociado a un usuario o contacto en Azure AD o a un contacto personal, los clientes Skype Empresarial y Teams mostrarán el identificador de llamada en función de esa información. Si el número de teléfono no está en Azure AD o en un contacto personal, el nombre para mostrar proporcionado por la compañía telefónica se mostrará si está disponible.

El atributo BlockIncomingCallerID permite bloquear la identificación de llamadas en las llamadas RTC de entrada. Puede establecer este atributo, pero no está disponible para los usuarios finales en la página de configuración de usuario. Cuando esta configuración está habilitada, el autor de la llamada RTC entrante se mostrará como procedente de Anónimo.
  
Para bloquear el identificador de llamada entrante, vea [Establecer el identificador de llamada para un usuario.](./set-the-caller-id-for-a-user.md)
  
## <a name="related-topics"></a>Temas relacionados
[Preguntas comunes sobre la transferencia de números de teléfono](./phone-number-calling-plans/port-order-overview.md)

[Diferentes tipos de números de teléfono que se usan para Planes de llamada](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Administrar los números de teléfono para su organización](/microsoftteams/manage-phone-numbers-for-your-organization)

[Términos y condiciones de las llamadas de emergencia](./emergency-calling-terms-and-conditions.md)

[Skype Empresarial Online: Etiqueta de aviso de declinación de responsabilidades de las llamadas de emergencia](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
