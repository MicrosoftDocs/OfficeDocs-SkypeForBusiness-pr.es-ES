---
title: Ver información de PIN de usuario en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 59e38117-8112-4851-82ac-a746ffa0f89d
description: 'Resumen: ver información de PIN de usuario en Skype Empresarial Server.'
ms.openlocfilehash: c016e6edf258f63166b930be833542bf9e730f15
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51099226"
---
# <a name="view-user-pin-information-in-skype-for-business-server"></a>Ver información de PIN de usuario en Skype Empresarial Server
 
**Resumen:** Ver información de PIN de usuario en Skype Empresarial Server.
  
Para unirse a una conferencia de acceso telefónico local como usuario autenticado, un usuario de Skype Empresarial Server con credenciales de Servicios de dominio de Active Directory (AD DS) requiere un número de identificación personal (PIN). Puede ver la información de PIN de un usuario desde el Panel de control de Skype Empresarial Server.
  
> [!NOTE]
> Puede ver la información de estado del PIN, como si el PIN se ha establecido o cuándo se cambió por última vez, pero no puede ver el PIN actual mirando el estado del PIN. Si un usuario ha perdido su PIN, puede restablecerlo siguiendo los procedimientos descritos en [Set a user's dial-in conferencing PIN in Skype for Business Server](set-a-user-s-dial-in-conferencing-pin.md)
  
### <a name="to-view-a-users-pin-in-skype-for-business-server-control-panel"></a>Para ver el PIN de un usuario en el Panel de control de Skype Empresarial Server

1. Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL de administración para abrir el Panel de control de Skype Empresarial Server.  
    
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
    
    > [!NOTE]
    > Si el PIN está bloqueado, debe desbloquearlo antes de definirlo. Para desbloquear el PIN, haga clic en el usuario, en **Acción** y en **Desbloquear PIN**. 
  
6. Haga clic en un usuario en los resultados de búsqueda, haga clic **en Acción** y, a continuación, haga clic en Ver estado **de PIN**.
    
## <a name="viewing-user-pin-information-by-using-windows-powershell-cmdlets"></a>Visualización de información de PIN de usuario mediante Windows PowerShell cmdlets

Puede ver la información del PIN del usuario mediante el cmdlet Get-CsClientPinInfo usuario. Este cmdlet se puede ejecutar desde el Shell de administración de Skype Empresarial Server o desde una sesión remota de Windows PowerShell. Para obtener más información acerca del Windows PowerShell remoto para conectarse a Skype Empresarial Server, vea el artículo de blog "Inicio rápido: Administración de [Microsoft Lync Server 2010 mediante PowerShell remoto".](https://go.microsoft.com/fwlink/p/?linkId=255876) El proceso es el mismo en Skype Empresarial Server.
  
### <a name="to-view-user-pin-information"></a>Para ver información de PIN de usuario

Para ver información de PIN para un usuario, escriba un comando similar al siguiente en el Shell de administración de Skype Empresarial Server y, a continuación, presione ENTRAR:
    
  ```PowerShell
  Get-CsClientPinInfo -Identity "Ken Myer"
  ```

Devolverá información similar a la siguiente:

<pre>
Identity          : sip:kenmyer@litwareinc.com
IsPinSet          : False
IsLockedOut       : False
LastPinChangeTime : 9/25/2012 1:35:03 PM
PinExpirationTime :
</pre>

Para obtener más información, vea el tema de ayuda para el cmdlet [Get-CsConferenceDisclaimer.](/powershell/module/skype/get-csconferencedisclaimer?view=skype-ps)
  
## <a name="see-also"></a>Ver también

[Establecer el PIN de conferencia de acceso telefónico local de un usuario en Skype Empresarial Server](set-a-user-s-dial-in-conferencing-pin.md)
  
[Bloquear o desbloquear un PIN de usuario en Skype Empresarial Server](lock-or-unlock-a-user-pin.md)