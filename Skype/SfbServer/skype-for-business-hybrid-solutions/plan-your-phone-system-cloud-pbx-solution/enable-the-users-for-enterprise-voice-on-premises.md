---
title: Habilitar a los usuarios para Enterprise Voice local
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 4598565a-c228-4265-ad03-d2aef95b31a0
description: Para que un usuario pueda usar el sistema telefónico (PBX en la nube), primero debe habilitarlo para telefonía IP empresarial y asignarle un número de teléfono. Para ello, use la implementación local mientras el usuario sigue hospedado en la implementación local.
ms.openlocfilehash: f02638f618b32190fafcded66550b5c3dcc52f2d
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221704"
---
# <a name="enable-the-users-for-enterprise-voice-on-premises"></a>Habilitar a los usuarios para Enterprise Voice local
 
Para que un usuario pueda usar el sistema telefónico (PBX en la nube), primero debe habilitarlo para telefonía IP empresarial y asignarle un número de teléfono. Para ello, use la implementación local mientras el usuario sigue hospedado en la implementación local.
  
### <a name="to-enable-a-user-for-enterprise-voice-on-premises-and-assign-a-phone-number"></a>Para habilitar a un usuario para telefonía IP empresarial en local y asignarle un número de teléfono

1. Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.
    
2. Use el menú Inicio o el acceso directo del escritorio para abrir el panel de control de Skype empresarial Server.
    
    También puede abrir una ventana del explorador y, a continuación, escribir la URL del administrador para abrir el panel de control de Skype empresarial Server.
    
3. En la barra de navegación izquierda, haga clic en **Usuarios**.
    
4. En el cuadro **Buscar usuarios**, escriba la primera parte del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de línea de la cuenta de usuario que desee habilitar y, a continuación, haga clic en **Buscar**.
    
5. En la tabla, haga clic en la cuenta de usuario de Skype empresarial online que desea habilitar para la telefonía IP empresarial.
    
6. En el menú **Editar** , haga clic en **Mostrar detalles**.
    
7. En **telefonía**, haga clic en telefonía **IP empresarial**.
    
8. Haga clic en **URI de línea**y escriba un número de teléfono único y normalizado (por ejemplo, Tel: + 14255550200). A continuación, haga clic en **confirmar**.
    
## <a name="special-considerations-when-enabling-users-for-enterprise-voice-on-premises"></a>Consideraciones especiales al habilitar usuarios para la telefonía IP empresarial local

En algunos casos, es posible que tenga que modificar la forma en que habilita a los usuarios para la telefonía IP empresarial para asegurarse de que puedan realizar y recibir llamadas correctamente. Si tiene usuarios en su implementación que cumplan las siguientes condiciones, siga los pasos que se incluyen para habilitar al usuario para telefonía IP empresarial.
  
- Si un usuario se crea en su AD local y, a continuación, se sincroniza con Skype empresarial online sin estar habilitado para Skype empresarial o para telefonía IP empresarial y no tiene un conjunto de LineURI, ejecute los siguientes cmdlets para cada usuario afectado, reemplazando los valores en \< \> con los valores reales de su entorno:
    
  ```powershell
  Enable-CsUser $username -HostingProvider sipfed.online.lync.com -SipAddress sip:<UserName>@<SIP Domain>
  ```

  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- Si un usuario ya está habilitado para Skype empresarial local, pero no está habilitado para telefonía IP empresarial o asignado a LineURI antes de que se mueva a Skype empresarial online, ejecute el siguiente cmdlet para cada usuario:
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- Si un usuario ya está habilitado en Skype empresarial local, pero no habilitado para telefonía IP empresarial, incluso si ya tiene asignado un LineURI, ejecute el siguiente cmdlet para cada usuario afectado:
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true
  ```


