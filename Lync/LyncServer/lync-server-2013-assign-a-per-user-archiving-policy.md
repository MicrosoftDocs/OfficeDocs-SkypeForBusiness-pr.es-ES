---
title: Asignación de una directiva de archivado por usuario
TOCTitle: Asignación de una directiva de archivado por usuario
ms:assetid: a12ca483-b235-460f-b3fe-130fb3087264
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg182560(v=OCS.15)
ms:contentKeyID: 48276167
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Asignación de una directiva de archivado por usuario

 

_**Última modificación del tema:** 2013-02-22_

La directiva de archivado es uno de los valores de configuración individuales de una cuenta de usuario que puede configurar en Panel de control de Lync Server 2013.

La implementación de una o más directivas de archivado por usuario es opcional. Asimismo, puede implementar solamente una directiva de archivado a nivel global o a nivel de sitio. Si no implementa directivas por usuario, es preciso que las asigne explícitamente a un objeto de usuario, grupo o contacto. Los requisitos de archivado toman automáticamente los valores predeterminados de aquellos definidos en la directiva de conferencia cuando no se asigna una directiva a nivel de sitio o por usuario específica.

Tras crear al menos una directiva de archivado por usuario, use los procedimientos en este tema para asignar la directiva que especifique adecuadamente si el servidor archivará las comunicaciones internas y externas de un usuario, o ambas.

Para obtener información detallada sobre la creación de directivas de archivado por usuario, consulte [Crear una directiva de archivado para habilitar o deshabilitar el archivado de las comunicaciones internas o externas para sitios o usuarios específicos](lync-server-2013-creating-an-archiving-policy-to-enable-or-disable-archiving-of-internal-or-external-communications-for-specific-sites-or-users.md).

## Para asignar una directiva de archivado por usuario

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y después introduzca la dirección URL de administración para abrir el panel de control de Lync Server. Para más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Abrir las herramientas administrativas de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Usuarios**.

4.  Utilice uno de los métodos siguientes para encontrar a un usuario:
    
      - En el cuadro **Buscar usuarios**, escriba la primera porción del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de la cuenta de usuario y, a continuación, haga clic en **Buscar**.
    
      - Si ha guardado una consulta, haga clic en el icono **Abrir consulta**, utilice el cuadro de diálogo **Abrir** para recuperar la consulta (un archivo .usf) y, a continuación, haga clic en **Buscar**.

5.  (Opcional) Especificar criterios de búsqueda adicionales para restringir los resultados:
    
    1.  Haga clic en **Agregar filtro**.
    
    2.  Especifique la propiedad de usuario; para ello, escríbala o haga clic en la flecha de la lista desplegable para seleccionar la propiedad.
    
    3.  En la lista desplegable **Igual a**, haga clic en el operador (por ejemplo, **Igual a** o **No igual a**).
    
    4.  En función de la propiedad de usuario que haya seleccionado, especifique los criterios que desee utilizar para filtrar los resultados de búsqueda escribiendo o haciendo clic en la flecha de la lista desplegable.
        
        > [!TIP]  
        > Para agregar cláusulas de búsqueda adicionales a la consulta, haga clic en <strong>Agregar filtro</strong>.
        
    
    5.  Haga clic en **Buscar**.

6.  Haga clic en un usuario en los resultados de búsqueda, haga clic en **Acción** y, a continuación, en **Asignar directivas**.
    
    > [!TIP]  
    > Si desea que se aplique la misma directiva de archivado por usuario a múltiples usuarios, seleccione varios usuarios en los resultados de la búsqueda, a continuación, haga clic en <strong>Acciones</strong> y en <strong>Asignar directivas</strong>.
    


7.  En **Asignar directivas**, en **Directiva de archivado**, realice uno de los procedimientos siguientes:
    

    > [!NOTE]
    > Debido a que existen numerosas directivas que puede configurar mediante el cuadro de diálogo <STRONG>Asignar directivas</STRONG>, se selecciona <STRONG>&lt;Dejar tal cual&gt;</STRONG> de forma predeterminada para cada directiva del cuadro de diálogo. Para seguir utilizando la directiva asignada anteriormente al usuario, no efectúe cambios en esta configuración.

    
      - Permita que Lync Server 2013 elija automáticamente la directiva de nivel global o la directiva de nivel de sitio, si se hubiera definido.
    
      - Haga clic en el nombre de una directiva de archivado por usuario que haya definido anteriormente en la página **Directiva de archivado**.
        
        > [!TIP]  
        > Para ayudarle a decidir la directiva que desea asignar, tras hacer clic en el nombre de una directiva, haga clic en <strong>Ver</strong> para ver los derechos y permisos de usuarios definidos en la directiva.
        


8.  Cuando haya terminado, haga clic en **Aceptar**.

## Asignar una directiva de archivado por usuario mediante cmdlets de Windows PowerShell

Las directivas de archivado por usuario también pueden asignarse mediante Windows PowerShell y el cmdlet **Grant-CsArchivingPolicy**. Este cmdlet puede ejecutarse bien desde el Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Asignar una directiva de archivado por usuario a un solo usuario

  - El siguiente comando permite asignar la directiva de archivado por usuario RedmondArchivingPolicy al usuario Ken Myer.
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"

## Asignar una directiva de archivado por usuario a varios usuarios

  - Este comando asigna la directiva de archivado por usuario RedmondArchivingPolicy a todos los usuarios que tengan cuentas alojadas en el grupo de registradores en atl-cs-001.litwareinc.com. Para más información sobre el parámetro Filtro usado en este comando, consulte la documentación del cmdlet [Get-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser).
    
        Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"

## Desasignar una directiva de archivado por usuario

  - Este comando desasigna cualquier directiva de archivado por usuario previamente asignada a Ken Myer. Una vez desasignada la directiva por usuario, Ken Myer pasará automáticamente a ser administrado mediante la directiva global (o, de existir, por la directiva de su sitio local). Las directivas de sitio tienen prioridad sobre la directiva global.
    
        Grant-CsarchivingPolicy -Identity "Ken Myer" -PolicyName $Null

Para obtener más información, consulte el tema de ayuda correspondiente al cmdlet [Grant-CsArchivingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsArchivingPolicy).

## Vea también

#### Tareas

[Crear una directiva de archivado para habilitar o deshabilitar el archivado de las comunicaciones internas o externas para sitios o usuarios específicos](lync-server-2013-creating-an-archiving-policy-to-enable-or-disable-archiving-of-internal-or-external-communications-for-specific-sites-or-users.md)  

#### Otros recursos

[Asignación de directivas por usuario](lync-server-2013-assigning-per-user-policies.md)

