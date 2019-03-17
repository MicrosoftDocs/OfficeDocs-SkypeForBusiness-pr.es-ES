---
title: Habilitar a los usuarios para Enterprise Voice local
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 4598565a-c228-4265-ad03-d2aef95b31a0
description: Para un usuario usar el sistema telefónico en Office 365 (en la nube PBX), en primer lugar debe habilitarlos para Enterprise Voice y asígneles a un número de teléfono. Para ello, con la implementación local mientras el usuario todavía está hospedado en la implementación local.
ms.openlocfilehash: 8d00120b0b0fd74baed1ceb003a46cfc2468d502
ms.sourcegitcommit: 7ca7f5cd38742b6a1967bd792113348dfe689850
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/16/2019
ms.locfileid: "30657450"
---
# <a name="enable-the-users-for-enterprise-voice-on-premises"></a>Habilitar a los usuarios para Enterprise Voice local
 
Para un usuario usar el sistema telefónico en Office 365 (en la nube PBX), en primer lugar debe habilitarlos para Enterprise Voice y asígneles a un número de teléfono. Para ello, con la implementación local mientras el usuario todavía está hospedado en la implementación local.
  
### <a name="to-enable-a-user-for-enterprise-voice-on-premises-and-assign-a-phone-number"></a>Para habilitar a un usuario para Enterprise Voice local y asignar a un número de teléfono

1. Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2. Use el menú Inicio o un acceso directo en el escritorio para abrir el Panel de control de Skype Empresarial Server.
    
    También puede abrir una ventana del explorador y, después, escribir la URL del administrador para abrir el Panel de control de Skype Empresarial Server.
    
3. En la barra de navegación izquierda, haga clic en **Usuarios**.
    
4. En el cuadro **Buscar usuarios**, escriba la primera parte del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de línea de la cuenta de usuario que desee habilitar y, a continuación, haga clic en **Buscar**.
    
5. En la tabla, haga clic en el Skype para la cuenta de usuario en línea de negocio que desea habilitar para Enterprise Voice.
    
6. En el menú **Editar**, haga clic en **Mostrar detalles**.
    
7. En **Telefonía**, haga clic en **Telefonía IP empresarial**.
    
8. Haga clic en **URI de línea** y escriba un número de teléfono único y normalizado (por ejemplo, tel:+14255550200). Después, haga clic en **Confirmar**.
    
## <a name="special-considerations-when-enabling-users-for-enterprise-voice-on-premises"></a>Consideraciones especiales sobre la habilitación de usuarios para Enterprise Voice local

En algunos casos, es posible que necesite modificar la forma en que habilita los usuarios para telefonía IP empresarial, con el fin de asegurarse de que puedan realizar y recibir llamadas correctamente. Si tiene usuarios en su implementación que cumplen las condiciones siguientes, realice los pasos que se incluye para permitir que el usuario para Enterprise Voice.
  
- Si un usuario se crea en sus instalaciones AD y, a continuación, sincronizar con Skype para profesionales en línea sin que esté habilitado para Skype para la empresa o para Enterprise Voice y no tienen un LineURI conjunto, ejecute los siguientes cmdlets para cada usuario afectado, reemplazando los valores en < C0 > <b1></b1> con los valores reales para su entorno:
    
  ```
  Enable-CsUser $username -HostingProvider sipfed.online.lync.com -SipAddress sip:<UserName>@<SIP Domain>
  ```

  ```
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- Si un usuario ya está habilitado para Skype para la empresa de forma local, pero no se ha habilitado para Enterprise Voice o asignado un LineURI antes de moverse a Skype para profesionales en línea, ejecute el siguiente cmdlet para cada usuario:
    
  ```
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- Si un usuario está ya habilitado en Skype para la empresa local pero no habilitado para Enterprise Voice, incluso si ya ha asignado un LineURI, ejecute el siguiente cmdlet para cada usuario afectado:
    
  ```
  Set-CsUser $username -EnterpriseVoiceEnabled $true
  ```


