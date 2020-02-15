---
title: 'Lync Server 2013: asignar una directiva de conferencia por usuario'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user conferencing policy
ms:assetid: 72f12c72-65f7-44fe-ab81-0f57cb2f87d1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521015(v=OCS.15)
ms:contentKeyID: 48184475
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c4fbef02553d4ba390dcf94f96f55936e2661b1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043322"
---
# <a name="assign-a-per-user-conferencing-policy-in-lync-server-2013"></a>Asignar una directiva de conferencia por usuario en Lync Server 2013

 


La Directiva de conferencia es una de las configuraciones individuales de una cuenta de usuario que se puede configurar en el panel de control de Lync Server.

La implementación de una o varias directivas de conferencia por usuario es opcional. También puede implementar solamente una directiva de conferencia de nivel global o una directiva de conferencia de nivel de sitio. Si no implementa directivas por usuario, es preciso que las asigne explícitamente a objetos de usuario, grupo o contacto. En el caso de que no se haya asignado una directiva específica de nivel de sitio o por usuario, los derechos y permisos de conferencia se predeterminan automáticamente de acuerdo con los definidos en la directiva de conferencia de nivel global.

Después de crear al menos una directiva de conferencia por usuario, use los procedimientos de este tema para asignar la directiva que especifica los permisos y derechos de usuario que desea que aplique el servidor a las reuniones organizadas por un usuario determinado.

Para obtener una lista de todas las opciones de configuración de directivas de conferencia disponibles, consulte [referencia de configuración de directivas de conferencia para Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).

Para obtener más información sobre cómo crear directivas de conferencia, consulte [Create or Modify a Conferencing Policy in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md).

## <a name="to-assign-a-per-user-conferencing-policy"></a>Asignación de una directiva de conferencia por usuario

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
    
    4.  En función de la propiedad de usuario que haya seleccionado, especifique los criterios que desee utilizar para filtrar los resultados de búsqueda escribiendo o haciendo clic en la flecha de la lista desplegable.
        

        > [!TIP]  
        > Para agregar cláusulas de búsqueda adicionales a la consulta, haga clic en <STRONG>Agregar filtro</STRONG>.

    
    5.  Haga clic en **Buscar**.

6.  Haga clic en un usuario en los resultados de búsqueda, haga clic en **Acción** y, a continuación, en **Asignar directivas**.
    

    > [!TIP]  
    > Si desea aplicar la misma directiva de conferencia por usuario a varios usuarios, seleccione los distintos usuarios en los resultados de la búsqueda, haga clic en <STRONG>Acciones</STRONG> y, a continuación, en <STRONG>Asignar directivas</STRONG>.



7.  En **Asignar directivas**, en **Directiva de conferencia**, lleve a cabo uno de los siguientes procedimientos:
    

    > [!NOTE]  
    > Debido a que hay varias directivas que puede configurar en <STRONG>asignar directivas</STRONG>, <STRONG> &lt;mantener como está&gt; </STRONG> seleccionada de forma predeterminada para cada directiva en el cuadro de diálogo. Para seguir utilizando la directiva asignada anteriormente al usuario, no efectúe cambios en esta configuración.

    
      - Seleccione ** \<automático\> ** para permitir que Lync Server 2013 elija automáticamente la Directiva de nivel global o, si está definida, la Directiva de nivel de sitio.
    
      - Haga clic en el nombre de una directiva de conferencia por usuario que haya definido anteriormente en la página **Directiva de conferencia**.
        

        > [!TIP]  
        > Para ayudarle a decidir la directiva que desea asignar, tras hacer clic en el nombre de una directiva, haga clic en <STRONG>Ver</STRONG> para ver los derechos y permisos de usuario definidos en la directiva.



8.  Cuando haya terminado, haga clic en **Aceptar**.

## <a name="assigning-a-per-user-conferencing-policy-by-using-windows-powershell-cmdlets"></a>Asignar una directiva de conferencia por usuario mediante cmdlets de Windows PowerShell

Las directivas de conferencia por usuario se pueden asignar mediante Windows PowerShell y el cmdlet Grant-CsConferencingPolicy. Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.

## <a name="to-assign-a-per-user-conferencing-policy-to-a-single-user"></a>Para asignar una directiva de conferencia por usuario a un solo usuario

  - El comando siguiente asigna la directiva de conferencia por usuario RedmondConferencingPolicy al usuario Ken Myer.
    
        Grant-CsConferencingPolicy -Identity "Ken Myer" -PolicyName "RedmondConferencingPolicy"

## <a name="to-assign-a-per-user-conferencing-policy-to-multiple-users"></a>Para asignar una directiva de conferencia por usuario a varios usuarios

  - Este comando asigna la directiva de conferencia por usuario HRConferencingPolicy a todos los usuarios que trabajan en el departamento de recursos humanos. Para obtener más información sobre el parámetro LdapFilter usado en este comando, consulte la documentación del cmdlet [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) .
    
        Get-CsUser -LdapFilter "Department=Human Resources" | Grant-CsConferencingPolicy -PolicyName "HRConferencingPolicy"

## <a name="to-unassign-a-per-user-conferencing-policy"></a>Para cancelar la asignación de una directiva de conferencia por usuario

  - El comando siguiente anula la asignación de una directiva de conferencia por usuario que se había asignado a Ken Myer. Una vez anulada la asignación, el usuario Ken Myer será administrado por la directiva global o, si la hay, por su directiva de sitio local. Las directivas de sitio tienen preferencia sobre la directiva global.
    
        Grant-CsConferencingPolicy -Identity "Ken Myer" -PolicyName $Null

Para obtener más información, consulte el tema de ayuda para el cmdlet [Grant-CsConferencingPolicy](https://technet.microsoft.com/library/gg425937\(v=ocs.15\)) .

## <a name="see-also"></a>Vea también


[Crear o modificar una directiva de conferencia en Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md)  


[Asignación de directivas por usuario en Lync Server 2013](lync-server-2013-assigning-per-user-policies.md)

