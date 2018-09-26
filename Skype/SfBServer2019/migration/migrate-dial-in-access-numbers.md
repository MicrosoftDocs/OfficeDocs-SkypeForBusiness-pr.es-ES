---
title: Migrar los números de acceso telefónico
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Migrar números de acceso telefónico a Skype para Business Server 2019 requiere ejecutando el cmdlet Move-CsApplicationEndpoint para migrar los objetos de contacto. Durante la instalación heredado y Skype para el período de coexistencia de Business Server 2019, los números de acceso telefónico que creó en Skype para Business Server 2019 se comportan de forma similar a los números de acceso telefónico que se crean en la instalación heredada, tal como se describe en este sección.
ms.openlocfilehash: 62d2d4f34f109c265a72a92283082601bd92b40b
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "25027728"
---
# <a name="migrate-dial-in-access-numbers"></a>Migrar los números de acceso telefónico

Migrar números de acceso telefónico a Skype para Business Server 2019 requiere ejecutando el cmdlet **Move-CsApplicationEndpoint** para migrar los objetos de contacto. Durante la instalación heredado y Skype para el período de coexistencia de Business Server 2019, los números de acceso telefónico que creó en Skype para Business Server 2019 se comportan de forma similar a los números de acceso telefónico que se crean en la instalación heredada, tal como se describe en este sección. 
  
Los números de acceso telefónico que creó en el heredado instalación pero movido a Skype para Business Server 2019 o que haya creado en Skype para Business Server 2019 antes, durante o después de la migración, tienen las siguientes características:
  
- No aparecen en las invitaciones a reuniones de Office Communications Server 2007 R2 y la página de números de acceso telefónico.
    
- Aparecen en las invitaciones a reuniones de instalación heredados y la página de números de acceso telefónico.
    
- Aparecen en Skype para Business Server 2019 las invitaciones a reuniones y la página de números de acceso telefónico.
    
- No se puede ver ni modificar en la herramienta administrativa de Office Communications Server 2007 R2.
    
- Se pueden ver y modificar en el Panel de Control de instalación heredada y en el Shell de administración de instalar heredado.
    
- Se pueden ver y modificar en la Skype para el Panel de Control de Business Server 2019 y en Skype para Shell de administración de Business Server 2019.
    
- Se pueden volver a secuenciar en la región mediante el cmdlet Set-CsDialinConferencingAccessNumber con el parámetro Priority.
    
Debe finalizar la migración de los números de acceso telefónico que apuntan a la heredada instalan el grupo de servidores antes de retirar el grupo de instalación heredado. Si no completa la migración del número de acceso telefónico como se describe en el procedimiento siguiente, se producirá un error en las llamadas entrantes a los números de acceso.
  
> [!IMPORTANT]
> Debe realizar este procedimiento antes de retirar el grupo de instalación heredado. 
  
> [!NOTE]
> Se recomienda que mueva los números de acceso telefónico cuando el uso de la red sea bajo, en caso de que hay un período breve interrupción del servicio. 
  
## <a name="to-identify-and-move-dial-in-access-numbers"></a>Para identificar y mueva los números de acceso telefónico

1. Iniciar el Skype para Shell de administración de negocio Server: haga clic en **Inicio**, haga clic en **Todos los programas**, haga clic en **Microsoft Skype para Business Server 2019**y, a continuación, haga clic en **Skype para Shell de administración de servidor empresarial**.
    
2. Para mover cada número de acceso telefónico a un grupo hospedado en Skype para Business Server 2019, desde la línea de comandos ejecute: 
    
  ```
  Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>
  
  ```

3. Abra Skype para el Panel de Control de servidor empresarial.
    
4. En la barra de navegación izquierda, haga clic en **Conferencia**.
    
5. Haga clic en la ficha **Número de acceso telefónico** . 
    
6. Compruebe que no queda ningún número de acceso telefónico para el grupo de servidores heredados de instalación desde la que va a migrar.
    
    > [!NOTE]
    > Cuando elija el Skype para el grupo de servidores de Business Server 2019 todos los números de acceso telefónico, a continuación, puede dar de baja el grupo de instalación heredado. 
  
## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-control-panel"></a>Comprobar la migración de números de acceso telefónico con Skype para el Panel de Control de servidor empresarial

1. Desde una cuenta de usuario que se asigna al rol **CsUserAdministrator** o **csadministrator** , inicie sesión en cualquier equipo en la implementación interna. 
    
2. Abra Skype para el Panel de Control de servidor empresarial.
    
3. En la barra de navegación izquierda, haga clic en **Conferencia**.
    
4. Haga clic en la ficha **Número de acceso telefónico** . 
    
5. Compruebe que todos los números de acceso telefónico se migran al grupo de servidores hospedado en Skype para Business Server 2019.
    
## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-management-shell"></a>Comprobar la migración de números de acceso telefónico con Skype para Shell de administración de servidor empresarial

1. Abra Skype para Shell de administración de servidor empresarial.
    
2. Para devolver todos los números de acceso telefónico migran, desde la línea de comandos que se ejecute:
    
  ```
  Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}
  ```

3. Compruebe que todos los números de acceso telefónico se migran al grupo de servidores hospedado en Skype para Business Server 2019.
    

