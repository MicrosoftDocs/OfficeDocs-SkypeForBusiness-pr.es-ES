---
title: Visualización de información del PIN de usuario
TOCTitle: Visualización de información del PIN de usuario
ms:assetid: 59e38117-8112-4851-82ac-a746ffa0f89d
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ688067(v=OCS.15)
ms:contentKeyID: 49889197
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Visualización de información del PIN de usuario

 

_**Última modificación del tema:** 2013-02-23_

Para unirse a una conferencia de acceso telefónico como usuario autenticado, un usuario de Lync Server 2013 con credenciales de Servicios de dominio de Active Directory (AD DS) necesita un número de identificación personal (PIN). Puede ver información del PIN de un usuario en el Panel de control de Lync Server 2013.


> [!NOTE]
> Puede ver información de estado del PIN como, por ejemplo, si se ha establecido el PIN o cuándo se modificó el PIN, pero no puede ver el PIN actual viendo su estado. Si un usuario ha perdido su PIN, puede restablecerlo siguiendo los procedimientos de <A href="lync-server-2013-set-a-user-s-dial-in-conferencing-pin.md">Establecer el PIN de conferencia de acceso telefónico local para un usuario en Lync Server 2013</A>



## Para ver el PIN de un usuario en Panel de control de Lync Server

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Usuarios**.

4.  Use uno de los métodos siguientes para encontrar a un usuario:
    
      - En el cuadro **Buscar usuarios** , escriba la primera porción del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de la cuenta de usuario y, a continuación, haga clic en **Buscar** .
    
      - Si ha guardado una consulta, haga clic en el icono **Abrir consulta** , utilice el cuadro de diálogo **Abrir** para recuperar la consulta (un archivo .usf) y, a continuación, haga clic en **Buscar** .

5.  (Opcional) Especifique criterios de búsqueda adicionales para restringir los resultados:
    
    1.  Haga clic en **Agregar filtro** .
    
    2.  Especifique la propiedad de usuario; para ello, escríbala o haga clic en la flecha de la lista desplegable para seleccionar la propiedad.
    
    3.  En la lista desplegable **Igual a** , haga clic en el operador (por ejemplo, **Igual a** o **No igual a** ).
    
    4.  En función de la propiedad de usuario que haya seleccionado, especifique los criterios que desee usar para filtrar los resultados de búsqueda escribiendo o haciendo clic en la flecha de la lista desplegable.
        
        > [!TIP]  
        > Para agregar cláusulas de búsqueda adicionales a la consulta, haga clic en <strong>Agregar filtro</strong> .
        
    
    5.  Haga clic en **Buscar** .
    

    > [!NOTE]
    > Si el PIN está bloqueado, debe desbloquearlo antes de definirlo. Para desbloquear el PIN, haga clic en el usuario, en <STRONG>Acción</STRONG> y en <STRONG>Desbloquear PIN</STRONG>.



6.  Haga clic en un usuario en los resultados de búsqueda, haga clic en **Acción** y luego en **Ver estado de PIN** .

## Para ver la información del PIN del usuario con los cmdlets de Shell de administración de Lync Server

Puede ver la información del PIN del usuario con el cmdlet Get-CsClientPinInfo. Este cmdlet se puede ejecutar desde el Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Para ver la información del PIN del usuario

  - Para ver la información del PIN de un usuario, escriba un comando similar al siguiente Shell de administración de Lync Server y luego presione ENTRAR:
    
        Get-CsClientPinInfo -Identity "Ken Myer"
    
    Eso devolverá información similar a esta:
    
        Identity          : sip:kenmyer@litwareinc.com
        IsPinSet          : False
        IsLockedOut       : False
        LastPinChangeTime : 9/25/2012 1:35:03 PM
        PinExpirationTime :

Para más información, vea el tema de ayuda del cmdlet [Get-CsConferenceDisclaimer](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsConferenceDisclaimer).

## Vea también

#### Tareas

[Establecer el PIN de conferencia de acceso telefónico local para un usuario en Lync Server 2013](lync-server-2013-set-a-user-s-dial-in-conferencing-pin.md)  
[Bloquear o desbloquear un PIN de usuario](lync-server-2013-lock-or-unlock-a-user-pin.md)

