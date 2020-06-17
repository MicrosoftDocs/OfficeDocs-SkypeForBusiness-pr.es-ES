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
description: La migración de números de acceso telefónico local a Skype empresarial Server 2019 requiere la ejecución del cmdlet Move-CsApplicationEndpoint para migrar los objetos de contacto. Durante la instalación heredada y el período de coexistencia de Skype empresarial Server 2019, los números de acceso telefónico que ha creado en Skype empresarial Server 2019 se comportan de forma similar a los números de acceso telefónico que crea en la instalación heredada, tal como se describe en esta sección.
ms.openlocfilehash: 0df71debe8a6d5c686d8bce17b837f32a4ca2bab
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752702"
---
# <a name="migrate-dial-in-access-numbers"></a>Migrar los números de acceso telefónico

La migración de números de acceso telefónico local a Skype empresarial Server 2019 requiere la ejecución del cmdlet **Move-CsApplicationEndpoint** para migrar los objetos de contacto. Durante la instalación heredada y el período de coexistencia de Skype empresarial Server 2019, los números de acceso telefónico que ha creado en Skype empresarial Server 2019 se comportan de forma similar a los números de acceso telefónico que crea en la instalación heredada, tal como se describe en esta sección. 

Los números de acceso telefónico que ha creado en la instalación antigua, pero que se han movido a Skype empresarial Server 2019, o que ha creado en Skype empresarial Server 2019 antes, durante o después de la migración tienen las siguientes características:

- No aparecen en las invitaciones a reuniones de Office Communications Server 2007 R2, ni en la página del número de acceso telefónico.

- Aparecen en las invitaciones de reunión heredadas y en la página de números de acceso telefónico local.

- Aparecen en las invitaciones a reuniones de Skype empresarial Server 2019 y la página de número de acceso telefónico.

- No se pueden ver ni modificar en la herramienta administrativa de Office Communications Server 2007 R2.

- Se pueden ver y modificar en el panel de control de instalación heredada y en el shell de administración de instalación heredada.

- Se pueden ver y modificar en el panel de control de Skype empresarial Server 2019 y en el shell de administración de Skype empresarial Server 2019.

- Se pueden volver a secuenciar en la región con el cmdlet Set-CsDialinConferencingAccessNumber con el parámetro Priority.

Debe terminar de migrar los números de acceso telefónico que apuntan al grupo de instalación heredado antes de retirar el grupo de instalación heredado. Si no completa la migración de los números de acceso telefónico como se describe en el siguiente procedimiento, no se podrán realizar las llamadas entrantes a los números de acceso.

> [!IMPORTANT]
> Debe realizar este procedimiento antes de retirar el grupo de instalación heredado. 

> [!NOTE]
> Se recomienda que mueva los números de acceso telefónico cuando el uso de la red sea bajo, en caso de que se produzca una breve interrupción del servicio. 

## <a name="to-identify-and-move-dial-in-access-numbers"></a>Para identificar y mover números de acceso telefónico

1. Inicie el shell de administración de Skype empresarial Server: haga clic en **Inicio**, **todos los programas**, **Microsoft Skype empresarial Server 2019**y, a continuación, haga clic en **Shell de administración de Skype empresarial Server**.

2. Para mover cada número de acceso telefónico a un grupo hospedado en Skype empresarial Server 2019, en la línea de comandos, ejecute: 

   ```PowerShell
   Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>
   ```

3. Abra el panel de control de Skype empresarial Server.

4. En la barra de navegación izquierda, haga clic en **Conferencia**.

5. Haga clic en la pestaña **Número de acceso telefónico**. 

6. Compruebe que no quedan números de acceso telefónico para el grupo de instalación heredado desde el que va a migrar.

    > [!NOTE]
    > Cuando todos los números de acceso telefónico local señalan al grupo de servidores de Skype empresarial Server 2019, puede retirar el grupo de instalación heredado. 

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-control-panel"></a>Comprobar la migración del número de acceso telefónico local mediante el panel de control de Skype empresarial Server

1. Desde una cuenta de usuario asignada al rol **CsUserAdministrator** o al rol **CsAdministrator**, inicie sesión en cualquier PC de su implementación interna. 

2. Abra el panel de control de Skype empresarial Server.

3. En la barra de navegación izquierda, haga clic en **Conferencia**.

4. Haga clic en la pestaña **Número de acceso telefónico**. 

5. Compruebe que todos los números de acceso telefónico local se han migrado al grupo de servidores hospedado en Skype empresarial Server 2019.

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-management-shell"></a>Comprobar la migración del número de acceso telefónico local mediante el shell de administración de Skype empresarial Server

1. Abra el shell de administración de Skype empresarial Server.

2. Para devolver todos los números de acceso de conferencias de acceso telefónico migrados, en la línea de comandos ejecute:

   ```PowerShell
   Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}
   ```

3. Compruebe que todos los números de acceso telefónico local se han migrado al grupo de servidores hospedado en Skype empresarial Server 2019.


