---
title: Asignación de una directiva de versión por usuario
TOCTitle: Asignación de una directiva de versión por usuario
ms:assetid: f7e8ba2f-62dc-4e7d-8b63-682986f10240
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg182607(v=OCS.15)
ms:contentKeyID: 48277208
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Asignación de una directiva de versión por usuario

 

_**Última modificación del tema:** 2013-02-22_

La directiva de versión de cliente es una de las configuraciones individuales de una cuenta de usuario que puede configurar en el Panel de control de Lync Server.

La implementación de una o varias directivas de versión de cliente por usuario es opcional. También puede implementar solamente una directiva de versión de cliente en el nivel global, o directivas de versión de cliente en el nivel de sitio o en el nivel de grupo de servidores. Si no implementa directivas por usuario, es preciso que las asigne explícitamente a un objeto de usuario, grupo o contacto. Cuando no se asigna ninguna directiva específica en el nivel de sitio, en el nivel de grupo de servidores o por usuario, los clientes predeterminados que tienen permiso para registrarse con Lync Server 2013 son los definidos en la directiva de versión de cliente del nivel global.

Después de crear, al menos, una directiva de versión de cliente por usuario, use los procedimientos de este tema para asignar la directiva que especifique las versiones de cliente que desea registrar con Lync Server.

Para ver más detalles acerca de la creación de directivas de versión de cliente por usuario, consulte [Especificación de las aplicaciones cliente que se pueden usar para iniciar sesión en Lync Server 2013](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md).

## Para asignar una directiva de versión de cliente por usuario

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
    
    4.  En función de la propiedad de usuario que haya seleccionado, especifique los criterios que desee utilizar para filtrar los resultados de búsqueda escribiendo o haciendo clic en la flecha de la lista desplegable.
        
        > [!TIP]  
        > Para agregar cláusulas de búsqueda adicionales a la consulta, haga clic en <strong>Agregar filtro</strong>.
        
    
    5.  Haga clic en **Buscar**.

6.  Haga clic en un usuario en los resultados de búsqueda, haga clic en **Acción** y, a continuación, en **Asignar directivas**.
    
    > [!TIP]  
    > Si desea que se aplique la misma directiva de versión de cliente por usuario a varios usuarios, seleccione varios usuarios en los resultados de búsqueda y, a continuación, haga clic en <strong>Acciones</strong> y <strong>Asignar directivas</strong>.
    


7.  En **Asignar directivas**, en **Directiva de versión de cliente**, realice una de las siguientes acciones:
    

    > [!NOTE]
    > Debido a que existen numerosas directivas que puede configurar mediante el cuadro de diálogo <STRONG>Asignar directivas</STRONG>, se selecciona <STRONG>&lt;Dejar tal cual&gt;</STRONG> de forma predeterminada para cada directiva del cuadro de diálogo. Para seguir utilizando la directiva asignada anteriormente al usuario, no efectúe cambios en esta configuración.

    
      - Permita que Lync Server elija automáticamente la directiva de nivel global o la directiva de nivel de sitio o de nivel de grupo de servidores, si se hubiera definido.
    
      - Haga clic en el nombre de una directiva de versión de cliente por usuario que haya definido previamente en la página **Directiva de versión de cliente**.
        
        > [!TIP]  
        > Para ayudarle a decidir la directiva que desea asignar, tras hacer clic en el nombre de una directiva, haga clic en <strong>Ver</strong> para ver los derechos y permisos de usuario definidos en la directiva.
        


8.  Cuando haya terminado, haga clic en **Aceptar**.

## Para asignar una directiva de versión por usuario usando cmdlets de Shell de administración de Lync Server.

Puede asignar directivas de versión por usuario usando el cmdlet Grant-CsClientVersionPolicy. Este cmdlet se puede ejecutar desde el Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Para asignar una directiva de versión por usuario a un solo usuario

  - El comando siguiente asigna la directiva de versión de cliente por usuario RedmondClientVersionPolicy al usuario Ken Myer.
    
        Grant-CsClientVersionPolicy -Identity "Ken Myer" -PolicyName "RedmondClientVersionPolicy"

## Para asignar una directiva de versión de cliente por usuario a varios usuarios

  - Este comando asigna la directiva de versión de cliente por usuario RedmondClientVersionPolicy a todos los usuarios que tienen actualmente asignada la directiva de voz RedmondVoicePolicy. Si desea más información sobre el parámetro Filter que se usa en este comando, consulte la documentación del cmdlet [Get-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser).
    
        Get-CsUser -Filter {VoicePolicy -eq "RedmondVoicePolicy"} | Grant-CsClientVersionPolicy -PolicyName "RedmondClientVersionPolicy"

## Para cancelar la asignación de una directiva de versión de cliente por usuario

  - El comando siguiente cancela la asignación de la directiva de versión de cliente por usuario que hemos asignado anteriormente a Ken Myer. Una vez cancelada, Ken Myer será administrado automáticamente usando la directiva global, su directiva de sitio local (si existe) o la directiva de ámbito de servicio asignada a su Registrador. La directiva de ámbito de servicio tiene prioridad sobre cualquier directiva de sitio y una directiva de sitio tiene prioridad sobre la directiva global.
    
        Grant-CsClientVersionPolicy -Identity "Ken Myer" -PolicyName $Null

Si desea más información, consulte el tema de ayuda relativo al cmdlet [Grant-CsClientVersionPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsClientVersionPolicy).

## Vea también

#### Otros recursos

[Asignación de directivas por usuario](lync-server-2013-assigning-per-user-policies.md)  
[Administrar dispositivos, teléfonos y aplicaciones cliente en Lync Server 2013](lync-server-2013-managing-devices-phones-and-client-applications.md)

