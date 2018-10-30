---
title: Asignación de una directiva de PIN por usuario
TOCTitle: Asignación de una directiva de PIN por usuario
ms:assetid: d8211c64-0b63-4193-a074-673da7d14287
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg182594(v=OCS.15)
ms:contentKeyID: 48276843
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Asignación de una directiva de PIN por usuario

 

_**Última modificación del tema:** 2013-02-22_

La directiva de número de identificación personal (PIN) de conferencia de acceso telefónico local es una de las configuraciones individuales de una cuenta de usuario que se puede establecer en el Panel de control de Lync Server 2013.

La implementación de una o más directivas de PIN por usuario es opcional. Asimismo, puede implementar solamente una directiva de PIN a nivel global o a nivel de sitio. Si implementa directivas por usuario, es preciso que las asigne explícitamente a un objeto de usuario, grupo o contacto. Los derechos y permisos de usuario para el uso de PIN de conferencia de acceso telefónico local pasan a ser, de forma predeterminada, los definidos en la directiva de PIN de nivel global cuando no se haya asignado una directiva específica de nivel de sitio o por usuario.

Tras crear al menos una directiva de PIN por usuario, emplee los procedimientos de este tema para asignar la directiva que especifique las restricciones que desee que imponga el servidor en los PIN que haya creado y usado un usuario en particular.

Para obtener información detallada sobre las directivas de PIN por usuario para conferencias de acceso telefónico local, consulte [Crear o modificar la configuración de PIN de conferencia de acceso telefónico local para un sitio o grupo de usuarios en Lync Server 2013](lync-server-2013-create-or-modify-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md).

## Para asignar una directiva de PIN por usuario

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Usuarios**.

4.  Utilice uno de los métodos siguientes para encontrar a un usuario:
    
      - En el cuadro **Buscar usuarios**, escriba la primera porción del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de la cuenta de usuario y, a continuación, haga clic en **Buscar**.
    
      - Si ha guardado una consulta, haga clic en el icono **Abrir consulta**, utilice el cuadro de diálogo **Abrir** para recuperar la consulta (un archivo .usf) y después haga clic en **Buscar**.

5.  (Opcional) Especifique criterios de búsqueda adicionales para restringir los resultados:
    
    1.  Haga clic en **Agregar filtro**.
    
    2.  Especifique la propiedad de usuario. Escríbala o haga clic en la flecha de la lista desplegable para seleccionar la propiedad.
    
    3.  En la lista desplegable **Igual a**, haga clic en el operador (por ejemplo, **Igual a** o **No igual a**).
    
    4.  En función de la propiedad de usuario que haya seleccionado, especifique los criterios que desee usar para filtrar los resultados de la búsqueda escribiendo o haciendo clic en la flecha de la lista desplegable.
        
        > [!TIP]  
        > Para agregar cláusulas de búsqueda adicionales a la consulta, haga clic en <strong>Agregar filtro</strong>.
        
    
    5.  Haga clic en **Buscar**.

6.  Haga clic en un usuario en los resultados de búsqueda, haga clic en **Acción** y, a continuación, en **Asignar directivas**.
    
    > [!TIP]  
    > Si desea aplicar la misma directiva de PIN por usuario a varios usuarios, seleccione los distintos usuarios en los resultados de la búsqueda, haga clic en <strong>Acciones</strong> y después en <strong>Asignar directivas</strong>.
    


7.  En **Asignar directivas**, en **Directiva de PIN**, realice uno de los procedimientos siguientes:
    

    > [!NOTE]
    > Debido a que se pueden configurar numerosas directivas mediante el cuadro de diálogo <STRONG>Asignar directivas</STRONG>, se selecciona <STRONG>&lt;Mantener tal cual&gt;</STRONG> de forma predeterminada para cada directiva del cuadro de diálogo. Para seguir utilizando la directiva asignada anteriormente al usuario, no efectúe cambios en esta configuración.

    
      - Permita que Lync Server 2013 elija automáticamente la directiva de nivel global o la directiva de nivel de sitio, si se hubiera definido.
    
      - Haga clic en el nombre de una directiva de PIN por usuario que haya definido anteriormente en la página **Directiva de PIN**.
        
        > [!TIP]  
        > Para que le sea más fácil decidir la directiva que desea asignar, tras hacer clic en el nombre de una directiva, haga clic en <strong>Ver</strong> para ver los derechos y permisos de usuario definidos en la directiva.
        


8.  Cuando haya terminado, haga clic en **Aceptar**.

## Asignar una directiva PIN por usuario con los cmdlets del Shell de administración de Lync Server

Puede asignar directivas de PIN por usuario usando el Shell de administración de Lync Server y el cmdlet **Grant-CsPinPolicy**. Ejecute este cmdlet desde el Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Asignar una directiva de PIN por usuario a un único usuario

  - El comando siguiente asigna la directiva de PIN por usuario RedmondPinPolicy al usuario Ken Myer.
    
        Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName "RedmondPinPolicy"

## Asignar una directiva de PIN por usuario a varios usuarios

  - El comando siguiente asigna la directiva de PIN por usuario RedmondUsersPinPolicy a todos los usuarios que trabajan en la ciudad de Redmond. Para más información sobre el parámetro LdapFilter usado en este comando, consulte [Get-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser).
    
        Get-CsUser -LdapFilter "l=Redmond" | Grant-CsPinPolicy -PolicyName "RedmondUsersPinPolicy"

## Quitar la asignación de una directiva de PIN por usuario

  - El comando siguiente quita la asignación de las directivas de PIN por usuario asignadas previamente a Ken Myer. Después de quitar la asignación de la directiva por usuario, se usará automáticamente la directiva global o la directiva del sitio local, si existe, para administrar a Ken Myer. La directiva de sitio tiene prioridad sobre la directiva global.
    
        Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName $Null

Para más información, consulte [Grant-CsPinPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsPinPolicy).

## Vea también

#### Tareas

[Crear una directiva de PIN nueva](lync-server-2013-create-a-new-pin-policy.md)  

#### Otros recursos

[Asignación de directivas por usuario](lync-server-2013-assigning-per-user-policies.md)

