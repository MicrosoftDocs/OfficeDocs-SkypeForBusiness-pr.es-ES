---
title: Ver la información del PIN del usuario en Skype Empresarial Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 59e38117-8112-4851-82ac-a746ffa0f89d
description: 'Resumen: Ver información del NIP de usuario de Skype para Business Server 2015.'
ms.openlocfilehash: 2521c9edba0b16eda6ea799b6b968a8c57bba245
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="view-user-pin-information-in-skype-for-business-server-2015"></a>Ver la información del PIN del usuario en Skype Empresarial Server 2015
 
**Resumen:** Vista de usuario información del NIP de Skype de Business Server 2015.
  
Para unirse a una conferencia de acceso telefónico como un usuario autenticado, un Skype para Business Server 2015 usuario con credenciales de servicios de dominio de Active Directory (AD DS) requiere un número de identificación personal (PIN). Puede ver información del NIP de un usuario de Skype para el Panel de Control de servidor empresarial.
  
> [!NOTE]
> Puede ver información de estado del PIN como, por ejemplo, si se ha establecido el PIN o cuándo se modificó el PIN, pero no puede ver el PIN actual viendo su estado. Si un usuario ha perdido su NIP, puede restablecerla mediante los procedimientos en el [conjunto de acceso telefónico conferencias de un usuario de PIN en Skype para Business Server 2015](set-a-user-s-dial-in-conferencing-pin.md)
  
### <a name="to-view-a-users-pin-in-skype-for-business-server-control-panel"></a>Para ver el NIP de un usuario en Skype para Panel de Control de servidor empresarial

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
    
    > [!NOTE]
    > Si el PIN está bloqueado, debe desbloquearlo antes de definirlo. Para desbloquear el PIN, haga clic en el usuario, en **Acción**y en **Desbloquear PIN**. 
  
6. Haga clic en un usuario en los resultados de búsqueda, haga clic en **Acción** y luego en **Ver estado de PIN**.
    
## <a name="viewing-user-pin-information-by-using-windows-powershell-cmdlets"></a>Ver información del NIP de usuario mediante cmdlets de Windows PowerShell utilizando

Puede ver la información del PIN del usuario con el cmdlet Get-CsClientPinInfo. Este cmdlet se puede ejecutar desde el Skype para el Shell de administración de servidor empresarial o desde una sesión remota de Windows PowerShell. Para obtener más información acerca del uso de Windows PowerShell remoto para conectar con Skype para Business Server, consulte el artículo de blog ["rápido inicio: administración de Microsoft Lync Server 2010 utilizando remoto PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876). El proceso es el mismo en Skype para Business Server.
  
### <a name="to-view-user-pin-information"></a>Para ver la información del PIN del usuario

Para ver información del NIP de un usuario, escriba un comando similar al siguiente en el Skype para negocios de Shell de administración de servidor y, a continuación, presione ENTRAR:
    
  ```
  Get-CsClientPinInfo -Identity "Ken Myer"
  ```

Devolverá información similar a la siguiente:

  ```
  Identity          : sip:kenmyer@litwareinc.com
IsPinSet          : False
IsLockedOut       : False
LastPinChangeTime : 9/25/2012 1:35:03 PM
PinExpirationTime :
  ```

Para obtener más información, vea el tema de ayuda para el cmdlet [Get-CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/get-csconferencedisclaimer?view=skype-ps) .
  
## <a name="see-also"></a>Vea también

#### 

[Establecer conferencias en el marcado de un usuario PIN en Skype para Business Server 2015](set-a-user-s-dial-in-conferencing-pin.md)
  
[Bloquear o desbloquear un PIN en Skype usuario Business Server 2015](lock-or-unlock-a-user-pin.md)

