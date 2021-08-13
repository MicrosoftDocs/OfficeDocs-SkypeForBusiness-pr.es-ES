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
description: La migración de números de acceso telefónico a Skype Empresarial Server 2019 requiere ejecutar el cmdlet Move-CsApplicationEndpoint para migrar los objetos de contacto. Durante el período de coexistencia de la instalación heredada y Skype Empresarial Server 2019, los números de acceso telefónico local que creó en Skype Empresarial Server 2019 se comportan de forma similar a los números de acceso telefónico local que cree en la instalación heredada, como se describe en esta sección.
ms.openlocfilehash: a65f0252dd4899ef196701d282a1b14673c5c22b7851029b35a15c4685c2b28d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54318055"
---
# <a name="migrate-dial-in-access-numbers"></a>Migrar los números de acceso telefónico

La migración de números de acceso telefónico a Skype Empresarial Server 2019 requiere ejecutar el cmdlet **Move-CsApplicationEndpoint** para migrar los objetos de contacto. Durante el período de coexistencia de la instalación heredada y Skype Empresarial Server 2019, los números de acceso telefónico local que creó en Skype Empresarial Server 2019 se comportan de forma similar a los números de acceso telefónico local que cree en la instalación heredada, como se describe en esta sección. 

Los números de acceso telefónico que creó en la instalación heredada pero que se movieron a Skype Empresarial Server 2019, o que creó en Skype Empresarial Server 2019 antes, durante o después de la migración, tienen las siguientes características:

- No aparecen en las invitaciones a reuniones de Office Communications Server 2007 R2, ni en la página del número de acceso telefónico.

- Aparecerá en las invitaciones a la reunión de instalación heredada y en la página de número de acceso telefónico.

- Aparecerá en Skype Empresarial Server convocatorias de reunión de 2019 y en la página de número de acceso telefónico.

- No se pueden ver ni modificar en la herramienta administrativa de Office Communications Server 2007 R2.

- Se puede ver y modificar en el Panel de control de instalación heredado y en el Shell de administración de instalación heredado.

- Se puede ver y modificar en el Panel de control Skype Empresarial Server 2019 y en Skype Empresarial Server Shell de administración de 2019.

- Se pueden volver a secuenciar en la región con el cmdlet Set-CsDialinConferencingAccessNumber con el parámetro Priority.

Debe finalizar la migración de números de acceso telefónico que apunten al grupo de instalación heredado antes de retirar el grupo de instalación heredado. Si no completa la migración de los números de acceso telefónico como se describe en el siguiente procedimiento, no se podrán realizar las llamadas entrantes a los números de acceso.

> [!IMPORTANT]
> Debe realizar este procedimiento antes de retirar el grupo de instalación heredado. 

> [!NOTE]
> Se recomienda que mueva los números de acceso telefónico cuando el uso de la red sea bajo, en caso de que se produzca una breve interrupción del servicio. 

## <a name="to-identify-and-move-dial-in-access-numbers"></a>Para identificar y mover números de acceso telefónico

1. Inicie el Shell Skype Empresarial Server administración: haga clic en Inicio **,** en Todos los **programas,** en **Microsoft Skype Empresarial Server 2019** y, a continuación, haga clic en **Skype Empresarial Server Shell de administración**.

2. Para mover cada número de acceso telefónico a un grupo hospedado en Skype Empresarial Server 2019, desde la línea de comandos: 

   ```PowerShell
   Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>
   ```

3. Abra Skype Empresarial Server Panel de control.

4. En la barra de navegación izquierda, haga clic en **Conferencia**.

5. Haga clic en la pestaña **Número de acceso telefónico**. 

6. Compruebe que no quedan números de acceso telefónico para el grupo de instalación heredado desde el que está migrando.

    > [!NOTE]
    > Cuando todos los números de acceso telefónico telefónico apunten al grupo de servidores Skype Empresarial Server 2019, puede retirar el grupo de instalación heredado. 

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-control-panel"></a>Comprobar la migración de números de acceso telefónico mediante Skype Empresarial Server Panel de control

1. Desde una cuenta de usuario asignada al rol **CsUserAdministrator** o al rol **CsAdministrator**, inicie sesión en cualquier PC de su implementación interna. 

2. Abra Skype Empresarial Server Panel de control.

3. En la barra de navegación izquierda, haga clic en **Conferencia**.

4. Haga clic en la pestaña **Número de acceso telefónico**. 

5. Compruebe que todos los números de acceso telefónico se migran al grupo hospedado en Skype Empresarial Server 2019.

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-management-shell"></a>Comprobar la migración del número de acceso telefónico mediante Skype Empresarial Server Shell de administración

1. Abra Skype Empresarial Server Shell de administración.

2. Para devolver todos los números de acceso de conferencias de acceso telefónico migrados, en la línea de comandos ejecute:

   ```PowerShell
   Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}
   ```

3. Compruebe que todos los números de acceso telefónico se migran al grupo hospedado en Skype Empresarial Server 2019.


