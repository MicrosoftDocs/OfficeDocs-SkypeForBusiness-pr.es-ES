---
title: Configurar el PIN de conferencias de acceso telefónico local de un usuario en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 4252b5a5-4267-4513-b18e-0253a8d66f72
description: 'Resumen: establezca el PIN de conferencias de acceso telefónico local de un usuario para Skype empresarial Server.'
ms.openlocfilehash: 83d1aae54d6e8be4f31b5bd27b6a568d6d88db1e
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992287"
---
# <a name="set-a-users-dial-in-conferencing-pin-in-skype-for-business-server"></a>Configurar el PIN de conferencias de acceso telefónico local de un usuario en Skype empresarial Server
 
**Resumen:** Establezca el PIN de conferencias de acceso telefónico local de un usuario para Skype empresarial Server.
  
Para unirse a una conferencia de acceso telefónico local como usuario autenticado, un usuario de Skype empresarial Server con credenciales de servicios de dominio de Active Directory (AD DS) necesita un número de identificación personal (PIN). Si un usuario olvida el PIN de conferencias de acceso telefónico local o no ha establecido el PIN con Skype empresarial Server, puede establecer el PIN del usuario desde el panel de control de Skype empresarial Server. Puede generar el PIN automáticamente o crear uno de forma manual.
  
> [!NOTE]
> Las características específicas del PIN como, por ejemplo, su longitud mínima, pueden configurarse como una directiva. Además de la directiva global, puede configurar una directiva de PIN para sitios o usuarios individuales. 
  
### <a name="to-set-a-users-pin"></a>Para establecer el PIN de un usuario

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
    > Si el PIN está bloqueado, debe desbloquearlo antes de definirlo. Para desbloquear el PIN, haga clic en el usuario, en **Acción** y en **Desbloquear PIN**. 
  
6. Haga clic en un usuario en los resultados de búsqueda, haga clic en **Acción** y, a continuación, en **Establecer PIN**.
    
7. En el cuadro de diálogo **Establecer PIN**, realice una de las siguientes acciones:
    
   - Para permitir que Skype empresarial Server genere el PIN del usuario, seleccione **generar automáticamente un PIN válido** (opción predeterminada).
    
   - Para crear su propio PIN, haga clic en **Escribir manualmente un PIN específico**, haga clic en el cuadro de texto y escriba un PIN que cumpla los requisitos de PIN especificados en la configuración de la directiva de PIN.
    
8. Haga clic en **Aceptar**.
    
9. En **Establecer PIN**, lleve a cabo uno de los procedimientos siguientes: 
    
   - Active la casilla **Mostrar PIN** para ver el PIN y, a continuación, copie el PIN e informe del mismo al usuario mediante el método preferido en su organización.
    
   - Haga clic en **Abrir mi aplicación de correo electrónico para enviar el nuevo PIN al usuario** para enviar el PIN por correo electrónico. Si su cliente de correo electrónico es Microsoft Office Outlook, el PIN se copia automáticamente en un mensaje de correo electrónico nuevo. Si usa un cliente de correo electrónico diferente, active la casilla **Mostrar PIN** para ver el PIN y cópielo en el mensaje de correo electrónico.
    
10. Haga clic en **Cerrar**.
    
## <a name="assigning-a-user-pin-by-using-windows-powershell-cmdlets"></a>Asignación de un PIN de usuario mediante cmdlets de Windows PowerShell

Puede asignar números de PIN con el cmdlet Set-CsClientPin. Puede ejecutar este cmdlet desde el shell de administración de Skype empresarial Server o desde una sesión remota de Windows PowerShell. Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Skype empresarial Server, consulte el artículo del blog ["Inicio rápido: administración de Microsoft Lync Server 2010 mediante PowerShell remoto"](https://go.microsoft.com/fwlink/p/?linkId=255876). El proceso es el mismo en Skype empresarial Server. 
  
### <a name="to-auto-assign-a-pin-number-to-a-user"></a>Para asignar automáticamente un número de PIN a un usuario

El siguiente comando asigna un número PIN al usuario a Ken Myer. Puesto que el parámetro PIN no está incluido, Skype empresarial Server generará y asignará el número PIN automáticamente.
    
  ```PowerShell
  Set-CsClientPin -Identity "Ken Myer" 
  ```

### <a name="to-assign-a-specific-pin-number-to-a-user"></a>Para asignar automáticamente un número de PIN específico a un usuario

Este comando usa el parámetro PIN para asignar el número PIN 121989 al usuario Ken Myer.
    
  ```PowerShell
  Set-CsClientPin -Identity "Ken Myer" -Pin 121989
  ```

Para obtener más información, consulte el tema de ayuda para el cmdlet [set-CsClientPin](https://docs.microsoft.com/powershell/module/skype/set-csclientpin?view=skype-ps) .
  

