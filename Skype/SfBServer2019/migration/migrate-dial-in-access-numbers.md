---
title: Migrar los números de acceso telefónico
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: La migración de números de acceso telefónico a Skype Empresarial Server 2019 requiere ejecutar el cmdlet Move-CsApplicationEndpoint para migrar los objetos de contacto. Durante la instalación heredada y el período de coexistencia de Skype Empresarial Server 2019, los números de acceso telefónico que creó en Skype Empresarial Server 2019 se comportan de forma similar a los números de acceso telefónico local que crea en la instalación heredada, tal como se describe en esta sección.
ms.openlocfilehash: 0df71debe8a6d5c686d8bce17b837f32a4ca2bab
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752702"
---
# <a name="migrate-dial-in-access-numbers"></a>Migrar los números de acceso telefónico

La migración de números de acceso telefónico a Skype Empresarial Server 2019 requiere ejecutar el cmdlet **Move-CsApplicationEndpoint** para migrar los objetos de contacto. Durante la instalación heredada y el período de coexistencia de Skype Empresarial Server 2019, los números de acceso telefónico que creó en Skype Empresarial Server 2019 se comportan de forma similar a los números de acceso telefónico local que crea en la instalación heredada, tal como se describe en esta sección. 

Los números de acceso telefónico que creó en la instalación heredada pero que movió a Skype Empresarial Server 2019, o que creó en Skype Empresarial Server 2019 antes, durante o después de la migración, tienen las siguientes características:

- No aparecen en las invitaciones a reuniones de Office Communications Server 2007 R2, ni en la página del número de acceso telefónico.

- Aparecerá en las invitaciones a reuniones de instalación heredadas y en la página de números de acceso telefónico.

- Aparecen en las invitaciones a reuniones de Skype Empresarial Server 2019 y en la página de números de acceso telefónico local.

- No se pueden ver ni modificar en la herramienta administrativa de Office Communications Server 2007 R2.

- Se puede ver y modificar en el Panel de control de instalación heredado y en el Shell de administración de instalación heredado.

- Se puede ver y modificar en el Panel de control de Skype Empresarial Server 2019 y en el Shell de administración de Skype Empresarial Server 2019.

- Se pueden volver a secuenciar en la región con el cmdlet Set-CsDialinConferencingAccessNumber con el parámetro Priority.

Debe terminar de migrar los números de acceso telefónico que apuntan al grupo de instalación heredado antes de retirar el grupo de servidores de instalación heredado. Si no completa la migración de los números de acceso telefónico como se describe en el siguiente procedimiento, no se podrán realizar las llamadas entrantes a los números de acceso.

> [!IMPORTANT]
> Debe realizar este procedimiento antes de retirar el grupo de instalación heredado. 

> [!NOTE]
> Se recomienda que mueva los números de acceso telefónico cuando el uso de la red sea bajo, en caso de que se produzca una breve interrupción del servicio. 

## <a name="to-identify-and-move-dial-in-access-numbers"></a>Para identificar y mover números de acceso telefónico

1. Inicie el Shell de administración de Skype Empresarial Server: Haga clic en **Inicio,** en Todos los **programas,** en **Microsoft Skype Empresarial Server 2019** y, a continuación, en Shell de administración de Skype Empresarial **Server.**

2. Para mover cada número de acceso telefónico a un grupo hospedado en Skype Empresarial Server 2019, desde la línea de comandos ejecute: 

   ```PowerShell
   Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>
   ```

3. Abra el Panel de control de Skype Empresarial Server.

4. En la barra de navegación izquierda, haga clic en **Conferencia**.

5. Haga clic en la pestaña **Número de acceso telefónico**. 

6. Compruebe que no quedan números de acceso telefónico para el grupo de instalación heredado desde el que va a migrar.

    > [!NOTE]
    > Cuando todos los números de acceso telefónico local apunten al grupo de Skype Empresarial Server 2019, puede retirar el grupo de servidores de instalación heredado. 

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-control-panel"></a>Comprobar la migración de números de acceso telefónico local mediante el Panel de control de Skype Empresarial Server

1. Desde una cuenta de usuario asignada al rol **CsUserAdministrator** o al rol **CsAdministrator**, inicie sesión en cualquier PC de su implementación interna. 

2. Abra el Panel de control de Skype Empresarial Server.

3. En la barra de navegación izquierda, haga clic en **Conferencia**.

4. Haga clic en la pestaña **Número de acceso telefónico**. 

5. Compruebe que todos los números de acceso telefónico local se migran al grupo hospedado en Skype Empresarial Server 2019.

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-management-shell"></a>Comprobar la migración de números de acceso telefónico local mediante el Shell de administración de Skype Empresarial Server

1. Abra el Shell de administración de Skype Empresarial Server.

2. Para devolver todos los números de acceso de conferencias de acceso telefónico migrados, en la línea de comandos ejecute:

   ```PowerShell
   Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}
   ```

3. Compruebe que todos los números de acceso telefónico local se migran al grupo hospedado en Skype Empresarial Server 2019.


