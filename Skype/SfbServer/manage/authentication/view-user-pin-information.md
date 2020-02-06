---
title: Ver información de PIN de usuario en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 59e38117-8112-4851-82ac-a746ffa0f89d
description: 'Resumen: vea la información del PIN de usuario en Skype empresarial Server.'
ms.openlocfilehash: 236148de5b100220731d723df3217205b258879e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818692"
---
# <a name="view-user-pin-information-in-skype-for-business-server"></a>Ver información de PIN de usuario en Skype empresarial Server
 
**Resumen:** Ver información de PIN de usuario en Skype empresarial Server.
  
Para unirse a una conferencia de acceso telefónico local como usuario autenticado, un usuario de Skype empresarial Server con credenciales de servicios de dominio de Active Directory (AD DS) necesita un número de identificación personal (PIN). Puede ver la información del PIN de un usuario desde el panel de control de Skype empresarial Server.
  
> [!NOTE]
> Puede ver información de estado del PIN como, por ejemplo, si se ha establecido el PIN o cuándo se modificó el PIN, pero no puede ver el PIN actual viendo su estado. Si un usuario ha perdido su PIN, puede restablecerlo siguiendo los procedimientos de establecer el [PIN de conferencias de acceso telefónico local de un usuario en Skype empresarial Server](set-a-user-s-dial-in-conferencing-pin.md)
  
### <a name="to-view-a-users-pin-in-skype-for-business-server-control-panel"></a>Para ver el PIN de un usuario en el panel de control de Skype empresarial Server

1. Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2. Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Skype empresarial Server.  
    
3. En la barra de navegación izquierda, haga clic en **Usuarios**.
    
4. Use uno de los métodos siguientes para encontrar a un usuario:
    
   - En el cuadro **Buscar usuarios**, escriba la primera porción del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de la cuenta de usuario y, a continuación, haga clic en **Buscar**.
    
   - Si ha guardado una consulta, haga clic en el icono **Abrir consulta**, use el cuadro de diálogo **Abrir** para recuperar la consulta (un archivo .usf) y, a continuación, haga clic en **Buscar**.
    
5. (Opcional) Especificar criterios de búsqueda adicionales para restringir los resultados:
    
   a. Haga clic en **Agregar filtro**.
    
   b. Especifique la propiedad de usuario. Para ello, escríbala o haga clic en la flecha de la lista desplegable para seleccionar la propiedad.
    
   c. En la lista desplegable **Igual a**, haga clic en el operador (por ejemplo, **Igual a** o **No igual a**).
    
   d. En función de la propiedad de usuario que haya seleccionado, especifique los criterios que desee usar para filtrar los resultados de búsqueda escribiendo o haciendo clic en la flecha de la lista desplegable.
    
    > [!TIP]
    > Para agregar cláusulas de búsqueda adicionales a la consulta, haga clic en **Agregar filtro**. 
  
   &. Haga clic en **Buscar**.
    
    > [!NOTE]
    > Si el PIN está bloqueado, debe desbloquearlo antes de definirlo. Para desbloquear el PIN, haga clic en el usuario, en **Acción**y en **Desbloquear PIN**. 
  
6. Haga clic en un usuario en los resultados de búsqueda, haga clic en **Acción** y luego en **Ver estado de PIN**.
    
## <a name="viewing-user-pin-information-by-using-windows-powershell-cmdlets"></a>Ver información de PIN de usuario mediante cmdlets de Windows PowerShell

Puede ver la información del PIN del usuario con el cmdlet Get-CsClientPinInfo. Este cmdlet se puede ejecutar desde el shell de administración de Skype empresarial Server o desde una sesión remota de Windows PowerShell. Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Skype empresarial Server, consulte el artículo del blog ["Inicio rápido: administración de Microsoft Lync Server 2010 mediante PowerShell remoto"](https://go.microsoft.com/fwlink/p/?linkId=255876). El proceso es el mismo en Skype empresarial Server.
  
### <a name="to-view-user-pin-information"></a>Para ver la información del PIN del usuario

Para ver la información de PIN de un usuario, escriba un comando similar al siguiente en el shell de administración de Skype empresarial Server y, a continuación, presione ENTRAR:
    
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

Para obtener más información, consulte el tema de ayuda para el cmdlet [Get-CsConferenceDisclaimer](https://docs.microsoft.com/powershell/module/skype/get-csconferencedisclaimer?view=skype-ps) .
  
## <a name="see-also"></a>Vea también

[Configurar el PIN de conferencias de acceso telefónico local de un usuario en Skype empresarial Server](set-a-user-s-dial-in-conferencing-pin.md)
  
[Bloquear o desbloquear un PIN de usuario en Skype empresarial Server](lock-or-unlock-a-user-pin.md)
