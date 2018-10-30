---
title: Asignación de una directiva de chat persistente por usuario
TOCTitle: Asignación de una directiva de chat persistente por usuario
ms:assetid: e22168f2-fde1-4f0a-b194-1fc881436822
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ721908(v=OCS.15)
ms:contentKeyID: 49889766
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Asignación de una directiva de chat persistente por usuario

 

_**Última modificación del tema:** 2013-02-22_

Puede asignar una directiva de chat persistente en el Panel de control de Lync Server 2013 o en el Shell de administración de Lync Server 2013. Para más información sobre la creación de directivas de usuario para el Servidor de chat persistente, consulte [Crear una directiva de usuario para chat persistente en Lync Server 2013](lync-server-2013-create-a-user-policy-for-persistent-chat.md).

## Para asignar una directiva de chat persistente en el Panel de control de Lync Server

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Usuarios**.

4.  Utilice uno de los métodos siguientes para encontrar a un usuario:
    
      - En el cuadro **Buscar usuarios**, escriba la primera porción del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de la cuenta de usuario y después haga clic en **Buscar**.
    
      - Si ha guardado una consulta, haga clic en el icono **Abrir consulta**, utilice el cuadro de diálogo **Abrir** para recuperar la consulta (un archivo .usf) y después haga clic en **Buscar**.

5.  (Opcional) Especifique criterios de búsqueda adicionales para restringir los resultados:
    
    1.  Haga clic en **Agregar filtro**.
    
    2.  Especifique la propiedad de usuario. Escríbala o haga clic en la flecha de la lista desplegable para seleccionar la propiedad.
    
    3.  En la lista desplegable **Igual a**, haga clic en el operador (por ejemplo, **Igual a** o **No igual a**).
    
    4.  En función de la propiedad de usuario que haya seleccionado, especifique los criterios que desee usar para filtrar los resultados de la búsqueda escribiendo o haciendo clic en la flecha de la lista desplegable.
        
        > [!TIP]  
        > Para agregar cláusulas de búsqueda adicionales a la consulta, haga clic en <strong>Agregar filtro</strong>.
        
    
    5.  Haga clic en **Buscar**.

6.  Haga clic en un usuario en los resultados de búsqueda, haga clic en **Acción** y después en **Asignar directivas**.
    
    > [!TIP]  
    > Si desea aplicar la misma directiva persistente por usuario a varios usuarios, seleccione los distintos usuarios en los resultados de la búsqueda, haga clic en <strong>Acciones</strong> y después en <strong>Asignar directivas</strong>.
    


7.  En **Asignar directivas**, en **Directiva de chat persistente**, lleve a cabo uno de los procedimientos siguientes:
    

    > [!NOTE]
    > Debido a que se pueden configurar numerosas directivas mediante el cuadro de diálogo <STRONG>Asignar directivas</STRONG>, se selecciona <STRONG>&lt;Mantener tal cual&gt;</STRONG> de forma predeterminada para cada directiva del cuadro de diálogo. Para seguir utilizando la directiva asignada anteriormente al usuario, no efectúe cambios en esta configuración.

    
      - Seleccione **\<Automático\>** para permitir que Lync Server 2013 elija automáticamente la directiva de nivel global o la directiva de nivel de sitio, si se hubiera definido.
    
      - Haga clic en el nombre de una directiva de chat persistente por usuario que haya definido anteriormente en la página **Directiva de chat persistente**.
        
        > [!TIP]  
        > Para que le sea más fácil decidir la directiva que desea asignar, tras hacer clic en el nombre de una directiva, haga clic en <strong>Ver</strong> para ver los derechos y permisos de usuario definidos en la directiva.
        


8.  Cuando haya terminado, haga clic en **Aceptar**.

## Asignar una directiva de chat persistente por usuario con los cmdlets de Lync Server PowerShell

Las directivas de chat persistente por usuario se pueden asignar también con Lync Server PowerShell o con el cmdlet Grant-CsPersistentChatPolicy. Este cmdlet se ejecuta desde el Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Asignar una directiva de chat persistente por usuario a un único usuario

  - El comando siguiente asigna la directiva de chat persistente por usuario RedmondPersistentChatPolicy al usuario Ken Myer.
    
        Grant-CsPersistentChatPolicy -Identity "Ken Myer" -PolicyName "RedmondPersistentChatPolicy"

## Asignar una directiva de chat persistente por usuario a varios usuarios

  - Este comando asigna la directiva de chat persistente por usuario RedmondUsersPersistentChatPolicy a todos los usuarios que trabajan para el departamento de TI. Para más información sobre el parámetro LdapFilter usado en este comando, consulte la documentación del cmdlet [Get-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser).
    
        Get-CsUser -LdapFilter "Department=IT" | Grant-CsPersistentChatPolicy -PolicyName "RedmondUsersPersistentChatPolicy"

## Quitar la asignación de una directiva de chat persistente por usuario

  - El comando siguiente quita la asignación de las directivas de chat persistente por usuario asignadas previamente a Ken Myer. Después de quitar la asignación de la directiva por usuario, se usará automáticamente la directiva global o la directiva del sitio local, si existe, para administrar a Ken Myer. La directiva de sitio tiene prioridad sobre la directiva global.
    
        Grant-CsPersistentChatPolicy -Identity "Ken Myer" -PolicyName $Null

Para más información, consulte el tema de ayuda del cmdlet [Grant-CsPersistentChatPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsPersistentChatPolicy).

## Vea también

#### Conceptos

[Crear una directiva de usuario para chat persistente en Lync Server 2013](lync-server-2013-create-a-user-policy-for-persistent-chat.md)

