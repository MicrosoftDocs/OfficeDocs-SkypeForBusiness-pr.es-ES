---
title: Habilitar los usuarios para Telefonía IP empresarial local
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
description: Para que un usuario use Sistema telefónico (PBX en la nube), primero debe habilitarlos para Telefonía IP empresarial y asignarles un número de teléfono. Para ello, use la implementación local mientras el usuario aún esté en la implementación local.
ms.openlocfilehash: aef74877d1a12d136bddc7eedc2a414dfad100830a88bb9a21695004be91d1a3
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54289088"
---
# <a name="enable-the-users-for-enterprise-voice-on-premises"></a>Habilitar los usuarios para Telefonía IP empresarial local
 
Para que un usuario use Sistema telefónico (PBX en la nube), primero debe habilitarlos para Telefonía IP empresarial y asignarles un número de teléfono. Para ello, use la implementación local mientras el usuario aún esté en la implementación local.

> [!Important]
> Skype Empresarial Online se retirará el 31 de julio de 2021 después de lo cual el servicio ya no será accesible.  Además, ya no se admite la conectividad RTC entre el entorno local mediante Skype Empresarial Server o Cloud Connector Edition y Skype Empresarial Online.  Obtenga información sobre cómo conectar la red de telefonía local a Teams mediante [enrutamiento directo](/MicrosoftTeams/direct-routing-landing-page).
  
### <a name="to-enable-a-user-for-enterprise-voice-on-premises-and-assign-a-phone-number"></a>Para habilitar un usuario para Telefonía IP empresarial local y asignar un número de teléfono

1. Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.
    
2. Use el acceso directo menú Inicio o de escritorio para abrir el panel de control Skype Empresarial Server usuario.
    
    También puede abrir una ventana del explorador y, a continuación, escribir la dirección URL del administrador para abrir el panel Skype Empresarial Server control.
    
3. En la barra de navegación izquierda, haga clic en **Usuarios**.
    
4. En el cuadro **Buscar usuarios**, escriba la primera parte del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de línea de la cuenta de usuario que desee habilitar y, a continuación, haga clic en **Buscar**.
    
5. En la tabla, haga clic en Skype Empresarial cuenta de usuario en línea que desea habilitar para Telefonía IP empresarial.
    
6. En el **menú Editar,** haga clic **en Mostrar detalles**.
    
7. En **Telefonía,** haga clic **Telefonía IP empresarial**.
    
8. Haga **clic en URI** de línea y escriba un número de teléfono único normalizado (por ejemplo, tel:+14255550200). A continuación, haga clic **en Confirmar**.
    
## <a name="special-considerations-when-enabling-users-for-enterprise-voice-on-premises"></a>Consideraciones especiales al habilitar usuarios para Telefonía IP empresarial locales

En algunos casos, es posible que deba modificar la forma en que permite a los usuarios Telefonía IP empresarial asegurarse de que pueden realizar y recibir llamadas correctamente. Si tiene usuarios en la implementación que cumplen las siguientes condiciones, realice los pasos incluidos para habilitar al usuario para Telefonía IP empresarial.
  
- Si un usuario se crea en su AD local y, a continuación, se sincroniza con Skype Empresarial Online sin estar habilitado para Skype Empresarial o para Telefonía IP empresarial y no tiene un conjunto de LineURI, ejecute los siguientes cmdlets para cada usuario afectado, reemplazando los valores por valores reales para \< \> su entorno:
    
  ```powershell
  Enable-CsUser $username -HostingProvider sipfed.online.lync.com -SipAddress sip:<UserName>@<SIP Domain>
  ```

  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- Si un usuario ya está habilitado para Skype Empresarial local, pero no estaba habilitado para Telefonía IP empresarial o se le asignó un LineURI antes de moverlo a Skype Empresarial Online, ejecute el siguiente cmdlet para cada usuario:
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- Si un usuario ya está habilitado en Skype Empresarial local pero no está habilitado para Telefonía IP empresarial, incluso si ya tiene asignado un LineURI, ejecute el siguiente cmdlet para cada usuario afectado:
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true
  ```