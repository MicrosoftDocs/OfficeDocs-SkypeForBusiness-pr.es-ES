---
title: Permitir que los usuarios de Telefonía IP empresarial en instalaciones
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
ms.custom: Strat_SB_Hybrid
ms.assetid: 4598565a-c228-4265-ad03-d2aef95b31a0
description: Para un usuario usar el sistema telefónico en Office 365 (PBX nube), primero debe habilitarlas para Telefonía IP empresarial y asignarles a un número de teléfono. Para ello, mediante su implementación local mientras el usuario todavía está alojado en la implementación local.
ms.openlocfilehash: c661d6da46cc42843346541b29841a728ab0fc16
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="enable-the-users-for-enterprise-voice-on-premises"></a>Permitir que los usuarios de Telefonía IP empresarial en instalaciones
 
Para un usuario usar el sistema telefónico en Office 365 (PBX nube), primero debe habilitarlas para Telefonía IP empresarial y asignarles a un número de teléfono. Para ello, mediante su implementación local mientras el usuario todavía está alojado en la implementación local.
  
### <a name="to-enable-a-user-for-enterprise-voice-on-premises-and-assign-a-phone-number"></a>Para habilitar a un usuario para Telefonía IP empresarial en instalaciones y asignar a un número de teléfono

1. Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2. Use el menú Inicio o un acceso directo en el escritorio para abrir el Panel de control de Skype Empresarial Server.
    
    También puede abrir una ventana del explorador y, después, escribir la URL del administrador para abrir el Panel de control de Skype Empresarial Server.
    
3. En la barra de navegación izquierda, haga clic en **Usuarios**.
    
4. En el cuadro **Buscar usuarios**, escriba la primera parte del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de línea de la cuenta de usuario que desee habilitar y, a continuación, haga clic en **Buscar**.
    
5. En la tabla, haga clic en el Skype para los negocios en línea cuenta de usuario que desea habilitar para Telefonía IP empresarial.
    
6. En el menú **Editar**, haga clic en **Mostrar detalles**.
    
7. En **Telefonía**, haga clic en **Telefonía IP empresarial**.
    
8. Haga clic en **URI de línea** y escriba un número de teléfono único y normalizado (por ejemplo, tel:+14255550200). Después, haga clic en **Confirmar**.
    
## <a name="special-considerations-when-enabling-users-for-enterprise-voice-on-premises"></a>Consideraciones especiales al permitir a los usuarios de Telefonía IP empresarial en instalaciones

En algunos casos, es posible que necesite modificar la forma en que habilita los usuarios para telefonía IP empresarial, con el fin de asegurarse de que puedan realizar y recibir llamadas correctamente. Si tiene usuarios en la implementación que cumplen las condiciones siguientes, realice los pasos que se incluyen para permitir al usuario para Telefonía IP empresarial.
  
- Si se crea un usuario en sus instalaciones AD y sincroniza con Skype para los negocios en línea sin que esté habilitado para Skype de negocios o de Telefonía IP empresarial y no tiene una LineURI establecida, ejecute los siguientes cmdlets para cada usuario afectado, reemplazando los valores en < C0 > <b1></b1> con valores reales para su entorno:
    
  ```
  Enable-CsUser $username -HostingProvider sipfed.online.lync.com -SipAddress sip:<UserName>@<SIP Domain>
  ```

  ```
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- Si un usuario ya está habilitado para Skype para el negocio en locales, pero no se ha habilitado para Telefonía IP empresarial o asignado un LineURI antes de moverse a Skype para los negocios en línea, ejecute el siguiente cmdlet para cada usuario:
    
  ```
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- Si un usuario está ya habilitado en Skype para el negocio en locales pero no habilitado para la Telefonía IP empresarial, incluso si ya ha asignado una LineURI, ejecute el siguiente cmdlet para cada usuario afectado:
    
  ```
  Set-CsUser $username -EnterpriseVoiceEnabled $true
  ```


