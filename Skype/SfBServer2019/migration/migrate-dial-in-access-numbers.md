---
title: Migrar los números de acceso telefónico
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: La migración de números de acceso telefónico local a Skype empresarial Server 2019 requiere ejecutar el cmdlet Move-CsApplicationEndpoint para migrar los objetos de contacto. Durante la instalación heredada y el período de coexistencia de Skype empresarial 2019, los números de acceso telefónico local creados en Skype empresarial Server 2019 se comportan de forma similar a los números de acceso telefónico local que se crean en la instalación heredada, como se describe en este sección.
ms.openlocfilehash: 81f100979d009f4f9b48cf9a538ec92095a67ad8
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36238049"
---
# <a name="migrate-dial-in-access-numbers"></a>Migrar los números de acceso telefónico

La migración de números de acceso telefónico local a Skype empresarial Server 2019 requiere ejecutar el cmdlet **Move-CsApplicationEndpoint** para migrar los objetos de contacto. Durante la instalación heredada y el período de coexistencia de Skype empresarial 2019, los números de acceso telefónico local creados en Skype empresarial Server 2019 se comportan de forma similar a los números de acceso telefónico local que se crean en la instalación heredada, como se describe en este sección. 

Los números de acceso telefónico local que ha creado en la instalación heredada, pero que ha movido a Skype empresarial Server 2019, o que ha creado en Skype empresarial Server 2019 antes, durante o después de la migración, tienen las siguientes características:

- No aparecen en las invitaciones a reuniones de Office Communications Server 2007 R2 y la página de número de acceso telefónico local.

- Aparece en la página heredar las invitaciones a reuniones y el número de acceso telefónico local.

- Aparece en las invitaciones a reuniones de Skype empresarial Server 2019 y la página de número de acceso telefónico local.

- No se puede ver ni modificar en la herramienta administrativa de Office Communications Server 2007 R2.

- Se puede ver y modificar en el panel de control de instalación heredado y en el shell de administración de instalación heredado.

- Se puede ver y modificar en el panel de control de Skype empresarial Server 2019 y en el shell de administración de Skype empresarial Server 2019.

- Se puede volver a secuenciar dentro de la región mediante el cmdlet Set-CsDialinConferencingAccessNumber con el parámetro Priority.

Debe finalizar la migración de los números de acceso telefónico local que apunten al grupo de instalación heredado antes de retirar el grupo de instalación heredado. Si no completa la migración de números de acceso telefónico, como se describe en el siguiente procedimiento, se producirán errores en las llamadas entrantes a los números de acceso.

> [!IMPORTANT]
> Debe realizar este procedimiento antes de dar de baja al grupo de instalación heredado. 

> [!NOTE]
> Le recomendamos que mueva los números de acceso telefónico cuando el uso de la red sea bajo, en caso de que haya un breve período de tiempo de servicio. 

## <a name="to-identify-and-move-dial-in-access-numbers"></a>Para identificar y mover los números de acceso telefónico local

1. Inicie el shell de administración de Skype empresarial Server: haga clic en **Inicio**, haga clic en **todos los programas**, haga clic en **Microsoft Skype empresarial Server 2019**y, a continuación, haga clic en **consola de administración de Skype empresarial Server**.

2. Para mover cada número de acceso de acceso telefónico local a un grupo hospedado en Skype empresarial Server 2019, ejecute: 

   ```
   Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>
   ```

3. Abra el panel de control de Skype empresarial Server.

4. En la barra de navegación izquierda, haga clic en **Conferencia**.

5. Haga clic en la pestaña **número de acceso telefónico local** . 

6. Compruebe que no quedan números de acceso telefónico local para el grupo de instalación heredado desde el que va a migrar.

    > [!NOTE]
    > Cuando todos los números de acceso telefónico local señalan al grupo de servidores de Skype empresarial 2019, puede desactivar el grupo de instalación heredado. 

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-control-panel"></a>Comprobar la migración de números de acceso telefónico local con el panel de control de Skype empresarial Server

1. Desde una cuenta de usuario que tenga asignada la función **CsUserAdministrator** o el rol **CsAdministrator** , inicie sesión en cualquier equipo de su implementación interna. 

2. Abra el panel de control de Skype empresarial Server.

3. En la barra de navegación izquierda, haga clic en **Conferencia**.

4. Haga clic en la pestaña **número de acceso telefónico local** . 

5. Compruebe que todos los números de acceso telefónico local se migran al grupo hospedado en Skype empresarial Server 2019.

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-management-shell"></a>Comprobar la migración de números de acceso telefónico local con el shell de administración de Skype empresarial Server

1. Abra el shell de administración de Skype empresarial Server.

2. Para devolver todos los números de acceso de la Conferencia de acceso telefónico local migrados, desde la línea de comandos ejecute:

   ```
   Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}
   ```

3. Compruebe que todos los números de acceso telefónico local se migran al grupo hospedado en Skype empresarial Server 2019.


