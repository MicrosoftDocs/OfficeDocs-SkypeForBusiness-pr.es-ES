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
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 4598565a-c228-4265-ad03-d2aef95b31a0
description: Para que un usuario Use un sistema telefónico en Office 365 (PBX en la nube), primero debe habilitarlo para telefonía IP empresarial y asignarle un número de teléfono. Esto se hace con la implementación local mientras el usuario aún está alojado en la implementación local.
ms.openlocfilehash: fdd405d84cddcfe805063287b8330ccea43397de
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34287513"
---
# <a name="enable-the-users-for-enterprise-voice-on-premises"></a>Habilitar a los usuarios para Enterprise Voice local
 
Para que un usuario Use un sistema telefónico en Office 365 (PBX en la nube), primero debe habilitarlo para telefonía IP empresarial y asignarle un número de teléfono. Esto se hace con la implementación local mientras el usuario aún está alojado en la implementación local.
  
### <a name="to-enable-a-user-for-enterprise-voice-on-premises-and-assign-a-phone-number"></a>Para habilitar un usuario para Enterprise Voice local y asignar un número de teléfono

1. Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2. Use el menú Inicio o un acceso directo en el escritorio para abrir el Panel de control de Skype Empresarial Server.
    
    También puede abrir una ventana del explorador y, después, escribir la URL del administrador para abrir el Panel de control de Skype Empresarial Server.
    
3. En la barra de navegación izquierda, haga clic en **Usuarios**.
    
4. En el cuadro **Buscar usuarios**, escriba la primera parte del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de línea de la cuenta de usuario que desee habilitar y, a continuación, haga clic en **Buscar**.
    
5. En la tabla, haga clic en la cuenta de usuario de Skype empresarial online que desea habilitar para telefonía IP empresarial.
    
6. En el menú **Editar**, haga clic en **Mostrar detalles**.
    
7. En **Telefonía**, haga clic en **Telefonía IP empresarial**.
    
8. Haga clic en **URI de línea** y escriba un número de teléfono único y normalizado (por ejemplo, tel:+14255550200). Después, haga clic en **Confirmar**.
    
## <a name="special-considerations-when-enabling-users-for-enterprise-voice-on-premises"></a>Consideraciones especiales al habilitar usuarios para Enterprise Voice local

En algunos casos, es posible que necesite modificar la forma en que habilita los usuarios para telefonía IP empresarial, con el fin de asegurarse de que puedan realizar y recibir llamadas correctamente. Si tiene usuarios de su implementación que cumplen las siguientes condiciones, realice los pasos que se incluyen para habilitar al usuario para telefonía IP empresarial.
  
- Si se crea un usuario en su AD local y luego se sincroniza con Skype empresarial online sin estar habilitado para Skype empresarial o para telefonía IP empresarial y no tiene un conjunto de LineURI, ejecute los siguientes cmdlets para cada usuario afectado, sustituyendo los valores de < C0 > <b1></b1> con valores reales para su entorno:
    
  ```
  Enable-CsUser $username -HostingProvider sipfed.online.lync.com -SipAddress sip:<UserName>@<SIP Domain>
  ```

  ```
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- Si un usuario ya está habilitado para Skype empresarial local, pero no se ha habilitado para telefonía IP empresarial o ha asignado un LineURI antes de moverlo a Skype empresarial online, ejecute el siguiente cmdlet para cada usuario:
    
  ```
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- Si un usuario ya está habilitado en Skype empresarial local pero no habilitado para telefonía IP empresarial, incluso si ya tiene asignada una LineURI, ejecute el siguiente cmdlet para cada usuario afectado:
    
  ```
  Set-CsUser $username -EnterpriseVoiceEnabled $true
  ```


