---
title: "Establecer el PIN de conferencia de acceso telefónico local para un usuario"
TOCTitle: Establecer el PIN de conferencia de acceso telefónico local para un usuario
ms:assetid: 4252b5a5-4267-4513-b18e-0253a8d66f72
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg520985(v=OCS.15)
ms:contentKeyID: 48275104
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Establecer el PIN de conferencia de acceso telefónico local para un usuario en Lync Server 2013

 

_**Última modificación del tema:** 2014-06-10_

Para unirse a una conferencia de acceso telefónico como usuario autenticado, un usuario de Lync Server 2013 con credenciales de Servicios de dominio de Active Directory (AD DS) necesita un número de identificación personal (PIN). Si un usuario olvida el PIN de conferencia de acceso telefónico local o no ha definido el PIN con Lync Server, puede definir el PIN del usuario desde Panel de control de Lync Server. Puede generar el PIN automáticamente o crear uno de forma manual.


> [!NOTE]
> Las características específicas del PIN como, por ejemplo, su longitud mínima, pueden configurarse como una directiva. Además de la directiva global, puede configurar una directiva de PIN para sitios o usuarios individuales. Para más información sobre cómo configurar una directiva de PIN, consulte <A href="lync-server-2013-configure-dial-in-conferencing-personal-identification-number-pin-rules.md">Configurar reglas del número de identificación personal (PIN) de la conferencia de acceso telefónico local en Lync Server 2013</A>.



## Para definir el PIN de un usuario

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Usuarios**.

4.  Utilice uno de los métodos siguientes para encontrar a un usuario:
    
      - En el cuadro **Buscar usuarios**, escriba la primera porción del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de la cuenta de usuario y, a continuación, haga clic en **Buscar**.
    
      - Si ha guardado una consulta, haga clic en el icono **Abrir consulta**, utilice el cuadro de diálogo **Abrir** para recuperar la consulta (un archivo .usf) y, a continuación, haga clic en **Buscar**.

5.  (Opcional) Especificar criterios de búsqueda adicionales para restringir los resultados:
    
    1.  Haga clic en **Agregar filtro**.
    
    2.  Especifique la propiedad de usuario. Para ello, escríbala o haga clic en la flecha de la lista desplegable para seleccionar la propiedad.
    
    3.  En la lista desplegable **Igual a**, haga clic en el operador (por ejemplo, **Igual a** o **No igual a**).
    
    4.  En función de la propiedad de usuario que haya seleccionado, especifique los criterios que desee usar para filtrar los resultados de búsqueda escribiendo o haciendo clic en la flecha de la lista desplegable.
        
        > [!TIP]  
        > Para agregar cláusulas de búsqueda adicionales a la consulta, haga clic en <strong>Agregar filtro</strong>.
        
    
    5.  Haga clic en **Buscar**.
    

    > [!NOTE]
    > Si el PIN está bloqueado, debe desbloquearlo antes de definirlo. Para desbloquear el PIN, haga clic en el usuario, en <STRONG>Acción</STRONG> y en <STRONG>Desbloquear PIN</STRONG>.



6.  Haga clic en un usuario en los resultados de búsqueda, haga clic en **Acción** y, a continuación, en **Establecer PIN**.

7.  En el cuadro de diálogo **Establecer PIN**, realice una de las siguientes acciones:
    
      - Para permitir que Lync Server 2013 genere el PIN del usuario, seleccione **Generar automáticamente un PIN válido** (opción predeterminada).
    
      - Para crear su propio PIN, haga clic en **Introducir manualmente un PIN específico**, haga clic en el cuadro de texto y escriba un PIN que cumpla los requisitos de PIN especificados en la configuración de la directiva de PIN.

8.  Haga clic en **Aceptar**.

9.  En **Establecer PIN**, lleve a cabo uno de los procedimientos siguientes:
    
      - Active la casilla **Mostrar PIN** para ver el PIN y, a continuación, copie el PIN e informe del mismo al usuario mediante el método preferido en su organización.
    
      - Haga clic en **Abrir mi aplicación de correo electrónico para enviar el nuevo PIN al usuario** para enviar el PIN por correo electrónico. Si su cliente de correo electrónico es Microsoft Office Outlook, el PIN se copia automáticamente en un mensaje de correo electrónico nuevo. Si usa un cliente de correo electrónico diferente, active la casilla **Mostrar PIN** para ver el PIN y cópielo en el mensaje de correo electrónico.

10. Haga clic en **Cerrar**.

## Asignación de un PIN de usuario con los cmdlets de Windows PowerShell

Puede asignar números de PIN con el cmdlet Set-CsClientPin. Puede ejecutar este cmdlet desde Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Para asignar automáticamente un número de PIN a un usuario

  - El siguiente comando asigna a un número PIN al usuario Ken Myer. Ya que el parámetro PIN no está incluido, Lync Server generará y asignará automáticamente el número de PIN.
    
        Set-CsClientPin -Identity "Ken Myer" 

## Para asignar automáticamente un número de PIN específico a un usuario

  - Este comando usa el parámetro PIN para asignar el número PIN 121989 al usuario Ken Myer.
    
        Set-CsClientPin -Identity "Ken Myer" -Pin 121989

Si desea más información, consulte el tema de ayuda relativo al cmdlet [Set-CsClientPin](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClientPin).

## Vea también

#### Conceptos

[Número de acceso telefónico local](https://technet.microsoft.com/es-es/library/gg133674\(v=ocs.15\))  

#### Otros recursos

[Configurar reglas del número de identificación personal (PIN) de la conferencia de acceso telefónico local en Lync Server 2013](lync-server-2013-configure-dial-in-conferencing-personal-identification-number-pin-rules.md)

