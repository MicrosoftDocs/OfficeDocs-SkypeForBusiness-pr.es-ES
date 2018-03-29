---
title: Bloquear o desbloquear el PIN de un usuario en Skype Empresarial Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 3d293a8a-e182-4547-8b06-2603c3c77329
description: 'Resumen: Bloquear o desbloquear la conferencia acceso telefónico del usuario PIN de Skype Business Server 2015.'
ms.openlocfilehash: 5bd4a334f9c0b543d9b4cade8631f992a920dfb1
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="lock-or-unlock-a-user-pin-in-skype-for-business-server-2015"></a>Bloquear o desbloquear el PIN de un usuario en Skype Empresarial Server 2015
 
**Resumen:** Bloquear o desbloquear la conferencia acceso telefónico del usuario PIN de Skype para Business Server 2015.
  
Puede bloquear o desbloquear el NIP de un usuario desde la sección de **usuarios** de Skype para el Panel de Control de servidor empresarial.
  
### <a name="to-lock-a-users-pin-in-skype-for-business-server-control-panel"></a>Bloquear el NIP de un usuario en Skype para Panel de Control de servidor empresarial

1. Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin para abrir el Skype para Panel de Control de servidor empresarial.  
    
3. En la barra de navegación izquierda, haga clic en **Usuarios**.
    
4. Utilice uno de los métodos siguientes para encontrar a un usuario:
    
    - En el cuadro **Buscar usuarios**, escriba la primera porción del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de la cuenta de usuario y, a continuación, haga clic en **Buscar**.
    
    - Si ha guardado una consulta, haga clic en el icono **Abrir consulta**, utilice el cuadro de diálogo **Abrir** para recuperar la consulta (un archivo .usf) y, a continuación, haga clic en **Buscar**.
    
5. (Opcional) Especificar criterios de búsqueda adicionales para restringir los resultados:
    
   a. Haga clic en **Agregar filtro**.
    
   b. Especifique la propiedad de usuario. Para ello, escríbala o haga clic en la flecha de la lista desplegable para seleccionar la propiedad.
    
   c. En la lista desplegable **Igual a**, haga clic en el operador (por ejemplo, **Igual a** o **No igual a**).
    
   d. En función de la propiedad de usuario que haya seleccionado, especifique los criterios que desee usar para filtrar los resultados de búsqueda escribiendo o haciendo clic en la flecha de la lista desplegable.
    
    > [!TIP]
    > Para agregar cláusulas de búsqueda adicionales a la consulta, haga clic en **Agregar filtro**. 
  
   e. Haga clic en **Buscar**.
    
   f. Haga clic en el usuario, en **Acción** y, a continuación, haga clic en **Bloquear PIN**.
    
### <a name="to-unlock-a-users-pin-in-skype-for-business-server-control-panel"></a>Para desbloquear el NIP de un usuario en Skype de Panel de Control de servidor empresarial

1. Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de Admin para abrir el Skype para Panel de Control de servidor empresarial.  
    
3. En la barra de navegación izquierda, haga clic en **Usuarios**.
    
4. Utilice uno de los métodos siguientes para encontrar a un usuario:
    
   - En el cuadro **Buscar usuarios**, escriba la primera porción del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de la cuenta de usuario y, a continuación, haga clic en **Buscar**.
    
   - Si ha guardado una consulta, haga clic en el icono **Abrir consulta**, utilice el cuadro de diálogo **Abrir** para recuperar la consulta (un archivo .usf) y, a continuación, haga clic en **Buscar**.
    
5. (Opcional) Especificar criterios de búsqueda adicionales para restringir los resultados:
    
   a. Haga clic en **Agregar filtro**.
    
   b. Especifique la propiedad de usuario. Para ello, escríbala o haga clic en la flecha de la lista desplegable para seleccionar la propiedad.
    
   c. En la lista desplegable **Igual a**, haga clic en el operador (por ejemplo, **Igual a** o **No igual a**).
    
   d. En función de la propiedad de usuario que haya seleccionado, especifique los criterios que desee usar para filtrar los resultados de búsqueda escribiendo o haciendo clic en la flecha de la lista desplegable.
    
    > [!TIP]
    > Para agregar cláusulas de búsqueda adicionales a la consulta, haga clic en **Agregar filtro**. 
  
   e. Haga clic en **Buscar**.
    
   f. Haga clic en el usuario, en **Acción** y, a continuación, haga clic en **Desbloquear PIN**.
    
## <a name="locking-and-unlocking-user-pins-by-using-windows-powershell-cmdlets"></a>Bloqueo y desbloqueo NIP de los usuarios mediante Cmdlets de Windows PowerShell

Puede bloquear y desbloquear el PIN de usuario mediante Windows PowerShell y los cmdlets CsClientPin-Lock y Unlock CsClientPin. Estos cmdlets se puede ejecutar desde el Skype para el Shell de administración de servidor empresarial o desde una sesión remota de Windows PowerShell. Para obtener más información acerca del uso de Windows PowerShell remoto para conectar con Skype para Business Server, consulte el artículo de blog ["rápido inicio: administración de Microsoft Lync Server 2010 utilizando remoto PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). El proceso es el mismo en Skype para Business Server.
  
### <a name="to-lock-a-user-pin"></a>Para bloquear el PIN de un usuario

- Para bloquear el NIP de un usuario, utilice el cmdlet Lock-CsClientPin. Por ejemplo:
    
  ```
  Lock-CsClientPin -Identity "Ken Myer"
  ```

### <a name="to-unlock-a-user-pin"></a>Para desbloquear el PIN de un usuario

- Para desbloquear el NIP de un usuario, utilice el cmdlet Unlock-CsClientPin. Por ejemplo:
    
  ```
  Unlock-CsClientPin -Identity "Ken Myer"
  ```

Para obtener más información, vea el tema de Ayuda de los cmdlets [CsClientPin-Lock](https://docs.microsoft.com/powershell/module/skype/lock-csclientpin?view=skype-ps) y [Unlock-CsClientPin](https://docs.microsoft.com/powershell/module/skype/unlock-csclientpin?view=skype-ps) .