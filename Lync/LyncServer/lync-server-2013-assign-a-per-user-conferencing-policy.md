---
title: Asignación de una directiva de conferencia por usuario
TOCTitle: Asignación de una directiva de conferencia por usuario
ms:assetid: 72f12c72-65f7-44fe-ab81-0f57cb2f87d1
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg521015(v=OCS.15)
ms:contentKeyID: 48275643
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Asignación de una directiva de conferencia por usuario

 

_**Última modificación del tema:** 2013-02-22_

La directiva de conferencia es uno de los parámetros individuales de una cuenta de usuario que se pueden configurar en el Panel de control de Lync Server.

La implementación de una o varias directivas de conferencia por usuario es opcional. También puede implementar solamente una directiva de conferencia de nivel global o una directiva de conferencia de nivel de sitio. Si no implementa directivas por usuario, es preciso que las asigne explícitamente a objetos de usuario, grupo o contacto. En el caso de que no se haya asignado una directiva específica de nivel de sitio o por usuario, los derechos y permisos de conferencia se predeterminan automáticamente de acuerdo con los definidos en la directiva de conferencia de nivel global.

Después de crear al menos una directiva de conferencia por usuario, use los procedimientos de este tema para asignar la directiva que especifica los permisos y derechos de usuario que desea que aplique el servidor a las reuniones organizadas por un usuario determinado.

Para obtener una lista de las configuraciones de directivas de conferencia disponibles, consulte [Referencia de configuración de directivas de conferencias en Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).

Para ver información detallada sobre cómo crear directivas de conferencia, consulte [Creación o modificación de una directiva de conferencia en Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md).

## Asignación de una directiva de conferencia por usuario

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
    > Si desea aplicar la misma directiva de conferencia por usuario a varios usuarios, seleccione los distintos usuarios en los resultados de la búsqueda, haga clic en <strong>Acciones</strong> y, a continuación, en <strong>Asignar directivas</strong>.
    


7.  En **Asignar directivas**, en **Directiva de conferencia**, lleve a cabo uno de los siguientes procedimientos:
    

    > [!NOTE]
    > Debido a que existen numerosas directivas que puede configurar en <STRONG>Asignar directivas</STRONG>, se selecciona <STRONG>&lt;Dejar tal cual&gt;</STRONG> de forma predeterminada para cada directiva del cuadro de diálogo. Para seguir utilizando la directiva asignada anteriormente al usuario, no efectúe cambios en esta configuración.

    
      - Seleccione **\<Automático\>** para permitir que Lync Server 2013 elija automáticamente la directiva de nivel global o la directiva de nivel de sitio, si se hubiera definido.
    
      - Haga clic en el nombre de una directiva de conferencia por usuario que haya definido anteriormente en la página **Directiva de conferencia**.
        
        > [!TIP]  
        > Para ayudarle a decidir la directiva que desea asignar, tras hacer clic en el nombre de una directiva, haga clic en <strong>Ver</strong> para ver los derechos y permisos de usuario definidos en la directiva.
        


8.  Cuando haya terminado, haga clic en **Aceptar**.

## Asignación de una directiva de conferencia por usuario con los cmdlets de Lync Server PowerShell

Las directivas de conferencia por usuario también se pueden asignar con Lync Server PowerShell y el cmdlet Grant-CsConferencingPolicy. Puede ejecutar el cmdlet desde el Shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para más información sobre el uso de una conexión remota de Windows PowerShell a Lync Server, consulte el artículo del blog sobre Windows PowerShell de Lync Server "Inicio rápido: Administración de Microsoft Lync Server 2010 con PowerShell remoto" en [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).

## Asignación de una directiva de conferencia por usuario a un solo usuario

  - El comando siguiente asigna la directiva de conferencia por usuario RedmondConferencingPolicy al usuario Ken Myer.
    
        Grant-CsConferencingPolicy -Identity "Ken Myer" -PolicyName "RedmondConferencingPolicy"

## Asignación de una directiva de conferencia por usuario a varios usuarios

  - Este comando asigna la directiva de conferencia por usuario HRConferencingPolicy a todos los usuarios que trabajan en el departamento de recursos humanos. Para más información sobre el parámetro LdapFilter utilizado en este comando, consulte la información sobre el cmdlet [Get-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser).
    
        Get-CsUser -LdapFilter "Department=Human Resources" | Grant-CsConferencingPolicy -PolicyName "HRConferencingPolicy"

## Anulación de la asignación de una directiva de conferencia por usuario

  - El comando siguiente anula la asignación de una directiva de conferencia por usuario que se había asignado a Ken Myer. Una vez anulada la asignación, el usuario Ken Myer será administrado por la directiva global o, si la hay, por su directiva de sitio local. Las directivas de sitio tienen preferencia sobre la directiva global.
    
        Grant-CsConferencingPolicy -Identity "Ken Myer" -PolicyName $Null

Para más información, vea el tema de ayuda sobre el cmdlet [Grant-CsConferencingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsConferencingPolicy).

## Vea también

#### Tareas

[Creación o modificación de una directiva de conferencia en Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md)  

#### Otros recursos

[Asignación de directivas por usuario](lync-server-2013-assigning-per-user-policies.md)

