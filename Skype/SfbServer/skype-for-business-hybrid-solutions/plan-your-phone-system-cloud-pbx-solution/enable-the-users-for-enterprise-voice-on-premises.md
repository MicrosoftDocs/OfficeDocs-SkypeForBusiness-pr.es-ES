---
title: Habilitar a los usuarios para Telefonía IP empresarial local
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
description: Para que un usuario use sistema telefónico (PBX en la nube), primero debe habilitarlos para Telefonía IP empresarial y asignarles un número de teléfono. Para ello, use la implementación local mientras el usuario aún esté en la implementación local.
ms.openlocfilehash: 7fc629114900cb9f4d825bd8fdc8e946e6c63880
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359196"
---
# <a name="enable-the-users-for-enterprise-voice-on-premises"></a>Habilitar a los usuarios para Telefonía IP empresarial local
 
Para que un usuario use sistema telefónico (PBX en la nube), primero debe habilitarlos para Telefonía IP empresarial y asignarles un número de teléfono. Para ello, use la implementación local mientras el usuario aún esté en la implementación local.

> [!Important]
> Skype Empresarial Online se retirará el 31 de julio de 2021, tras lo cual el servicio ya no será accesible.  Además, ya no se admite la conectividad rtc entre su entorno local, ya sea a través de Skype Empresarial Server o Cloud Connector Edition y Skype Empresarial Online.  Obtenga información sobre cómo conectar la red de telefonía local a Teams mediante [enrutamiento directo.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)
  
### <a name="to-enable-a-user-for-enterprise-voice-on-premises-and-assign-a-phone-number"></a>Para habilitar un usuario para Telefonía IP empresarial local y asignar un número de teléfono

1. Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.
    
2. Use el menú Inicio o el acceso directo de escritorio para abrir el Panel de control de Skype Empresarial Server.
    
    También puede abrir una ventana del explorador y, a continuación, escribir la dirección URL del administrador para abrir el Panel de control de Skype Empresarial Server.
    
3. En la barra de navegación izquierda, haga clic en **Usuarios**.
    
4. En el cuadro **Buscar usuarios**, escriba la primera parte del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de línea de la cuenta de usuario que desee habilitar y, a continuación, haga clic en **Buscar**.
    
5. En la tabla, haga clic en la cuenta de usuario de Skype Empresarial Online que desea habilitar para Telefonía IP empresarial.
    
6. En el **menú Editar,** haga clic **en Mostrar detalles.**
    
7. En **Telefonía,** haga clic **Telefonía IP empresarial**.
    
8. Haga **clic en URI** de línea y escriba un número de teléfono único y normalizado (por ejemplo, tel:+14255550200). A continuación, haga clic **en Confirmar**.
    
## <a name="special-considerations-when-enabling-users-for-enterprise-voice-on-premises"></a>Consideraciones especiales al habilitar usuarios para Telefonía IP empresarial local

En algunos casos, es posible que deba modificar la forma en que habilita a los usuarios Telefonía IP empresarial para asegurarse de que pueden realizar y recibir llamadas correctamente. Si tiene usuarios en la implementación que cumplen las siguientes condiciones, realice los pasos incluidos para habilitar al usuario para Telefonía IP empresarial.
  
- Si se crea un usuario en ad local y, a continuación, se sincroniza con Skype Empresarial Online sin estar habilitado para Skype Empresarial o para Telefonía IP empresarial y no tiene un conjunto lineURI, ejecute los cmdlets siguientes para cada usuario afectado, reemplazando los valores por valores reales para \< \> su entorno:
    
  ```powershell
  Enable-CsUser $username -HostingProvider sipfed.online.lync.com -SipAddress sip:<UserName>@<SIP Domain>
  ```

  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- Si un usuario ya está habilitado para Skype Empresarial local, pero no se ha habilitado para Telefonía IP empresarial o se le ha asignado un LineURI antes de moverlo a Skype Empresarial Online, ejecute el siguiente cmdlet para cada usuario:
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- Si un usuario ya está habilitado en Skype Empresarial local pero no está habilitado para Telefonía IP empresarial, incluso si ya se ha asignado un LineURI, ejecute el siguiente cmdlet para cada usuario afectado:
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true
  ```


