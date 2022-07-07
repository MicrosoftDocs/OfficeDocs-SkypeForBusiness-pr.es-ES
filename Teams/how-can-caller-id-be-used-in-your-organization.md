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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- ms.teamsadmincenter.voice.callerid.overview
description: El identificador de llamada se puede controlar tanto para llamadas entrantes como salientes para usuarios de Phone System mediante una directiva denominada CallingLineIdentity.
ms.openlocfilehash: 250f8a1a516aec4c9941b0c6396e6d44771b4f53
ms.sourcegitcommit: f608811288c82a6348a6af1671246a93ed06e578
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2022
ms.locfileid: "66660966"
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a>Cómo se puede usar la identificación de llamadas en su organización

El identificador de llamada consta de dos elementos de información orientados a usuarios:

- Un número de teléfono (denominado CLID o id. de línea de llamada). Este es el número de la red telefónica conmutada (RTC) que se presenta como identificación del autor de la llamada.

- Un nombre de entidad de llamada (normalmente denominado CNAM). 
  
La funcionalidad de identificador de llamadas está disponible para todos los usuarios del sistema telefónico, independientemente de la [opción de conectividad con RTC](pstn-connectivity.md): Plan de llamadas de Microsoft, Conexión del operador o Enrutamiento directo. 
  
Puede controlar el identificador de llamada para llamadas entrantes y salientes mediante una directiva denominada CallingLineIdentity. Para obtener más información, consulte [Más información sobre el identificador de línea de llamada y el nombre del receptor de llamadas](more-about-calling-line-id-and-calling-party-name.md).

  
## <a name="outbound-pstn-caller-id"></a>Identificador de llamadas RTC salientes

Para el identificador de llamadas RTC de salida, están disponibles las siguientes opciones. 
  
- El número de teléfono asignado al usuario, que es el valor predeterminado.

- Anónimo, que está disponible quitando la presentación del número de RTC del usuario. 

- Un número de teléfono sustituto, que puede ser:

  - Un número de teléfono que se clasifica como número de servicio y gratuito en el inventario de números de teléfono de los planes de llamadas. Se asigna a un operador automático de Teams o a una cola de llamadas.

  - Un número de teléfono local mediante enrutamiento directo asignado a una cuenta de recursos que usa un operador automático de Teams o una cola de llamadas. 

- El nombre del receptor de la llamada o el CNAM establecido en la llamada RTC saliente.  
    
Para obtener más información, vea [Establecer el identificador de llamada de un usuario](./set-the-caller-id-for-a-user.md).
  
### <a name="end-user-control-of-outbound-caller-id"></a>Control de usuario final del identificador de llamadas saliente

Los usuarios pueden cambiar la configuración del identificador de llamada a **Anónimo** estableciendo el atributo EnableUserOverride. 

Si el identificador de llamada saliente se establece en Anónimo, EnableUserOverride no tiene ningún efecto y el identificador de llamada siempre se establece en Anónimo. El valor predeterminado de EnableUserOverride es False.

Los usuarios finales pueden establecer su identificador de llamada en Anónimo yendo a **Configuración > Llamadas** y, a continuación, en **Identificador de llamada**, seleccione **Ocultar mi número de teléfono e información de perfil para todas las llamadas**. Este cambio de configuración tarda unos minutos en reflejarse en las llamadas nuevas. 

### <a name="notes"></a>Notas

Tenga en cuenta lo siguiente:

- No puede asignar los siguientes tipos de números de teléfono para el identificador de llamada saliente:

  - Los números de teléfono que se clasifican como usuario en el inventario de números de teléfono de los Planes de llamadas.

  - Cualquier número de teléfono local a través de enrutamiento directo asignado a un usuario.

  - Un Skype Empresarial Server número de teléfono local.

- El uso de la sustitución de números de teléfono de la cuenta de recursos funciona para los usuarios de Teams. La sustitución del número de teléfono de servicio funciona para los usuarios de Teams.

- El nombre del autor de la llamada se envía en las llamadas en las que el identificador de llamada se sustituye por LineUri, un número de teléfono de cuenta de servicio o recurso y cuando el autor de la llamada es un usuario de Teams.

- El nombre de la entidad de llamada puede tener un máximo de 200 caracteres, pero los sistemas posteriores podrían admitir menos caracteres.

- Para el Ruteo directo, la sustitución de números de teléfono y el nombre de la entidad de llamada se envían en el encabezado DEL SIP. Si la correspondiente OnlinePstnGateway se configura con ForwardPai = True, el encabezado SIP P-ASSERTED-IDENTITY contendrá el usuario que realiza la llamada real.

- EnableUserOverride tiene prioridad sobre otras opciones de configuración de la directiva, a menos que la sustitución se establezca en Anónimo. Por ejemplo, supongamos que la instancia de directiva ha sustituido con una cuenta de recursos y enableUserOverride se establece y habilita por el usuario. En este caso, se bloqueará el identificador de llamada saliente y se usará Anónimo. Si una instancia de directiva tiene la sustitución establecida en Anonymous y EnableUserOverride se establece, el identificador de llamada saliente siempre será Anónimo, independientemente de la configuración del usuario final.

   
## <a name="inbound-caller-id"></a>Identificador de llamada entrante

Sistema telefónico muestra el número de teléfono externo entrante como identificador de llamada. Si el número está asociado a un usuario o contacto de Azure AD o a un contacto personal, el Skype Empresarial y los clientes de Teams mostrarán el identificador de llamada basándose en esa información. Si el número de teléfono no está en Azure AD o en un contacto personal, se mostrará el nombre para mostrar proporcionado por la compañía telefónica si está disponible.

El atributo BlockIncomingCallerID permite bloquear la identificación de llamadas en las llamadas RTC de entrada. Puede establecer este atributo, pero no está disponible para los usuarios finales en la página de configuración de usuario. Cuando esta configuración está habilitada, el autor de la llamada RTC entrante se muestra como procedente de Anónimo.
  
Para bloquear el identificador de llamada entrante, vea [Establecer el identificador de llamada de un usuario](./set-the-caller-id-for-a-user.md).
  
## <a name="related-topics"></a>Temas relacionados
[Preguntas comunes sobre la transferencia de números de teléfono](./phone-number-calling-plans/port-order-overview.md)

[Diferentes tipos de números de teléfono que se usan para Planes de llamada](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Administrar los números de teléfono para su organización](/microsoftteams/manage-phone-numbers-for-your-organization)

[Términos y condiciones de las llamadas de emergencia](./emergency-calling-terms-and-conditions.md)

[Skype Empresarial Online: Etiqueta de aviso de declinación de responsabilidades de las llamadas de emergencia](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
