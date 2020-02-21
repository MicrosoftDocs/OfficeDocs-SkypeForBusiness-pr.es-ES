---
title: 'Lync Server 2013: establecer el PIN de conferencia de acceso telefónico local de un usuario'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set a user's dial-in conferencing PIN
ms:assetid: 4252b5a5-4267-4513-b18e-0253a8d66f72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520985(v=OCS.15)
ms:contentKeyID: 48183970
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ad28eb7214cb6762e8b0941f22da8b97966e9024
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200686"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="set-a-users-dial-in-conferencing-pin-in-lync-server-2013"></a>Establecer el PIN de conferencia de acceso telefónico local de un usuario en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-06-10_

Para unirse a una conferencia de acceso telefónico local como usuario autenticado, un usuario de Lync Server 2013 con credenciales de servicios de dominio de Active Directory (AD DS) requiere un número de identificación personal (PIN). Si un usuario olvida el PIN de conferencia de acceso telefónico local o no ha establecido el PIN con Lync Server, puede establecer el PIN del usuario desde el panel de control de Lync Server. Puede generar el PIN automáticamente o crear uno de forma manual.

<div>


> [!NOTE]  
> Las características específicas del PIN como, por ejemplo, su longitud mínima, pueden configurarse como una directiva. Además de la directiva global, puede configurar una directiva de PIN para sitios o usuarios individuales. Para obtener más información sobre cómo configurar una directiva de PIN, vea <A href="lync-server-2013-configure-dial-in-conferencing-personal-identification-number-pin-rules.md">configurar las reglas de número de identificación personal (PIN) de conferencia de acceso telefónico local en Lync Server 2013</A>.



</div>

<div>

## <a name="to-set-a-users-pin"></a>Para definir el PIN de un usuario

1.  Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Usuarios**.

4.  Utilice uno de los métodos siguientes para encontrar a un usuario:
    
      - En el cuadro **Buscar usuarios**, escriba la primera porción del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de la cuenta de usuario y, a continuación, haga clic en **Buscar**.
    
      - Si ha guardado una consulta, haga clic en el icono **Abrir consulta**, utilice el cuadro de diálogo **Abrir** para recuperar la consulta (un archivo .usf) y, a continuación, haga clic en **Buscar**.

5.  (Opcional) Especificar criterios de búsqueda adicionales para restringir los resultados:
    
    1.  Haga clic en **Agregar filtro**.
    
    2.  Especifique la propiedad de usuario; para ello, escríbala o haga clic en la flecha de la lista desplegable para seleccionar la propiedad.
    
    3.  En la lista desplegable **Igual a**, haga clic en el operador (por ejemplo, **Igual a** o **No igual a**).
    
    4.  En función de la propiedad de usuario que haya seleccionado, especifique los criterios que desee usar para filtrar los resultados de búsqueda escribiendo o haciendo clic en la flecha de la lista desplegable.
        
        <div>
        

        > [!TIP]  
        > Para agregar cláusulas de búsqueda adicionales a la consulta, haga clic en <STRONG>Agregar filtro</STRONG>.

        
        </div>
    
    5.  Haga clic en **Buscar**.
    
    <div>
    

    > [!NOTE]  
    > Si el PIN está bloqueado, debe desbloquearlo antes de definirlo. Para desbloquear el PIN, haga clic en el usuario, en <STRONG>Acción</STRONG> y en <STRONG>Desbloquear PIN</STRONG>.

    
    </div>

6.  Haga clic en un usuario en los resultados de búsqueda, haga clic en **Acción** y, a continuación, en **Establecer PIN**.

7.  En el cuadro de diálogo **Establecer PIN**, realice una de las siguientes acciones:
    
      - Para permitir que Lync Server 2013 genere el PIN del usuario, seleccione **generar automáticamente un PIN válido** (opción predeterminada).
    
      - Para crear su propio PIN, haga clic en **Introducir manualmente un PIN específico**, haga clic en el cuadro de texto y escriba un PIN que cumpla los requisitos de PIN especificados en la configuración de la directiva de PIN.

8.  Haga clic en **Aceptar**.

9.  En **Establecer PIN**, lleve a cabo uno de los procedimientos siguientes:
    
      - Active la casilla **Mostrar PIN** para ver el PIN y, a continuación, copie el PIN e informe del mismo al usuario mediante el método preferido en su organización.
    
      - Haga clic en **Abrir mi aplicación de correo electrónico para enviar el nuevo PIN al usuario** para enviar el PIN por correo electrónico. Si su cliente de correo electrónico es Microsoft Office Outlook, el PIN se copia automáticamente en un mensaje de correo electrónico nuevo. Si usa un cliente de correo electrónico diferente, active la casilla **Mostrar PIN** para ver el PIN y cópielo en el mensaje de correo electrónico.

10. Haga clic en **Cerrar**.

</div>

<div>

## <a name="assigning-a-user-pin-by-using-windows-powershell-cmdlets"></a>Asignación de un PIN de usuario mediante cmdlets de Windows PowerShell

Puede asignar números de PIN que también se pueden asignar mediante el cmdlet Set-CsClientPin. Puede ejecutar este cmdlet desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.

<div>

## <a name="to-auto-assign-a-pin-number-to-a-user"></a>Para asignar automáticamente un número de PIN a un usuario

  - El siguiente comando asigna a un número PIN al usuario Ken Myer. Debido a que no se incluye el parámetro PIN, Lync Server generará y asignará automáticamente el número PIN.
    
        Set-CsClientPin -Identity "Ken Myer" 

</div>

<div>

## <a name="to-assign-a-specific-pin-number-to-a-user"></a>Para asignar un número de PIN específico a un usuario

  - Este comando usa el parámetro PIN para asignar el número PIN 121989 al usuario Ken Myer.
    
        Set-CsClientPin -Identity "Ken Myer" -Pin 121989

</div>

Para obtener más información, consulte el tema de ayuda del cmdlet [set-CsClientPin](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPin) .

</div>

<div>

## <a name="see-also"></a>Consulta también


[Número de acceso telefónico local](https://technet.microsoft.com/library/gg133674\(v=ocs.15\))  


[Configurar reglas de número de identificación personal (PIN) de conferencia de acceso telefónico en Lync Server 2013](lync-server-2013-configure-dial-in-conferencing-personal-identification-number-pin-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

