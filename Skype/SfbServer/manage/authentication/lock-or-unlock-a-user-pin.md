---
title: Bloquear o desbloquear un PIN de usuario en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 3d293a8a-e182-4547-8b06-2603c3c77329
description: 'Resumen: bloquear o desbloquear el PIN de conferencia de acceso telefónico local de un usuario para Skype Empresarial Server.'
ms.openlocfilehash: 1ae1deea84b099852decd9acbc6315049484b0b3
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60848604"
---
# <a name="lock-or-unlock-a-user-pin-in-skype-for-business-server"></a>Bloquear o desbloquear un PIN de usuario en Skype Empresarial Server
 
**Resumen:** Bloquear o desbloquear el PIN de conferencia de acceso telefónico local de un usuario para Skype Empresarial Server.
  
Puedes bloquear o desbloquear el PIN de un usuario desde la **sección Usuarios** de Skype Empresarial Server Panel de control.
  
### <a name="to-lock-a-users-pin-in-skype-for-business-server-control-panel"></a>Para bloquear el PIN de un usuario en Skype Empresarial Server Panel de control

1. Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir Skype Empresarial Server Panel de control.  
    
3. En la barra de navegación izquierda, haga clic en **Usuarios**.
    
4. Utilice uno de los métodos siguientes para encontrar a un usuario:
    
    - En el cuadro **Buscar usuarios**, escriba la primera porción del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de la cuenta de usuario y, a continuación, haga clic en **Buscar**.
    
    - Si ha guardado una consulta, haga clic en el icono **Abrir consulta**, utilice el cuadro de diálogo **Abrir** para recuperar la consulta (un archivo .usf) y, a continuación, haga clic en **Buscar**.
    
5. (Opcional) Especificar criterios de búsqueda adicionales para restringir los resultados:
    
   a. Haga clic en **Agregar filtro**.
    
   b. Especifique la propiedad de usuario; para ello, escríbala o haga clic en la flecha de la lista desplegable para seleccionar la propiedad.
    
   c. En la lista desplegable **Igual a**, haga clic en el operador (por ejemplo, **Igual a** o **No igual a**).
    
   d. En función de la propiedad de usuario que haya seleccionado, especifique los criterios que desee usar para filtrar los resultados de búsqueda escribiendo o haciendo clic en la flecha de la lista desplegable.
    
    > [!TIP]
    > Para agregar cláusulas de búsqueda adicionales a la consulta, haga clic en **Agregar filtro**. 
  
   e. Haga clic en **Buscar**.
    
   f. Haga clic en el usuario, en **Acción** y, a continuación, haga clic en **Bloquear PIN**.
    
### <a name="to-unlock-a-users-pin-in-skype-for-business-server-control-panel"></a>Para desbloquear el PIN de un usuario en Skype Empresarial Server Panel de control

1. Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir Skype Empresarial Server Panel de control.  
    
3. En la barra de navegación izquierda, haga clic en **Usuarios**.
    
4. Utilice uno de los métodos siguientes para encontrar a un usuario:
    
   - En el cuadro **Buscar usuarios**, escriba la primera porción del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de la cuenta de usuario y, a continuación, haga clic en **Buscar**.
    
   - Si ha guardado una consulta, haga clic en el icono **Abrir consulta**, utilice el cuadro de diálogo **Abrir** para recuperar la consulta (un archivo .usf) y, a continuación, haga clic en **Buscar**.
    
5. (Opcional) Especificar criterios de búsqueda adicionales para restringir los resultados:
    
   a. Haga clic en **Agregar filtro**.
    
   b. Especifique la propiedad de usuario; para ello, escríbala o haga clic en la flecha de la lista desplegable para seleccionar la propiedad.
    
   c. En la lista desplegable **Igual a**, haga clic en el operador (por ejemplo, **Igual a** o **No igual a**).
    
   d. En función de la propiedad de usuario que haya seleccionado, especifique los criterios que desee usar para filtrar los resultados de búsqueda escribiendo o haciendo clic en la flecha de la lista desplegable.
    
    > [!TIP]
    > Para agregar cláusulas de búsqueda adicionales a la consulta, haga clic en **Agregar filtro**. 
  
   e. Haga clic en **Buscar**.
    
   f. Haga clic en el usuario, en **Acción** y, a continuación, haga clic en **Desbloquear PIN**.
    
## <a name="locking-and-unlocking-user-pins-by-using-windows-powershell-cmdlets"></a>Bloqueo y desbloqueo de LOS PIN de usuario mediante Windows PowerShell cmdlets

Puede bloquear y desbloquear los PIN de usuario mediante Windows PowerShell y los cmdlets Lock-CsClientPin y Unlock-CsClientPin usuario. Puede ejecutar estos cmdlets desde el Shell Skype Empresarial Server administración o desde una sesión remota de Windows PowerShell. Para obtener más información acerca del uso de Windows PowerShell para conectarse a Skype Empresarial Server, vea [Administración remota de PowerShell de Microsoft Lync](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/). El proceso es el mismo en Skype Empresarial Server.
  
### <a name="to-lock-a-user-pin"></a>Para bloquear el PIN de un usuario

- Para bloquear el PIN de un usuario, use el cmdlet Lock-CsClientPin usuario. Por ejemplo:
    
  ```PowerShell
  Lock-CsClientPin -Identity "Ken Myer"
  ```

### <a name="to-unlock-a-user-pin"></a>Para desbloquear el PIN de un usuario

- Para desbloquear el PIN de un usuario, use el cmdlet Unlock-CsClientPin usuario. Por ejemplo:
    
  ```PowerShell
  Unlock-CsClientPin -Identity "Ken Myer"
  ```

Para obtener más información, vea el tema de ayuda para los [cmdlets Lock-CsClientPin](/powershell/module/skype/lock-csclientpin?view=skype-ps) y [Unlock-CsClientPin.](/powershell/module/skype/unlock-csclientpin?view=skype-ps)