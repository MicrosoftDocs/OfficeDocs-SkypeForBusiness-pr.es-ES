---
title: 'Lync Server 2013: asignar una directiva de conferencia por usuario'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign a per-user conferencing policy
ms:assetid: 72f12c72-65f7-44fe-ab81-0f57cb2f87d1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521015(v=OCS.15)
ms:contentKeyID: 48184475
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9dbeb129ef58c6993d1cd919b03d7417d35b439a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842918"
---
# <a name="assign-a-per-user-conferencing-policy-in-lync-server-2013"></a>Asignar una directiva de conferencia por usuario en Lync Server 2013

 


La Directiva de conferencia es una de las configuraciones individuales de una cuenta de usuario que puede configurar en el panel de control de Lync Server.

La implementación de una o más directivas de conferencia por usuario es opcional. También puede implementar una directiva de conferencia de nivel internacional o una directiva de conferencia de nivel de sitio. Si implementa directivas por usuario, debe asignarlas explícitamente a usuarios, grupos o objetos de contacto. Los permisos y derechos de usuario de conferencia se especifican automáticamente de forma predeterminada para los definidos en la Directiva de conferencia global cuando no se ha asignado ninguna directiva específica de nivel de sitio o de usuario.

Después de crear al menos una directiva de conferencia por usuario, use los procedimientos de este tema para asignar la Directiva que especifica los permisos y derechos de usuario que desea que el servidor otorgue a las reuniones organizadas por un usuario en particular.

Para obtener una lista de todas las configuraciones de directiva de conferencia disponibles, consulte [referencia de configuración de directiva de conferencia para Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).

Para obtener más información sobre cómo crear directivas de conferencia, consulte [crear o modificar una directiva de conferencia en Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md).

## <a name="to-assign-a-per-user-conferencing-policy"></a>Para asignar una directiva de conferencia por usuario

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Usuarios**.

4.  Use uno de los métodos siguientes para encontrar a un usuario:
    
      - En el cuadro **Buscar usuarios**, escriba la primera porción del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de la cuenta de usuario y, a continuación, haga clic en **Buscar**.
    
      - Si ha guardado una consulta, haga clic en el icono **Abrir consulta**, use el cuadro de diálogo **Abrir** para recuperar la consulta (un archivo .usf) y, a continuación, haga clic en **Buscar**.

5.  (Opcional) Especificar criterios de búsqueda adicionales para restringir los resultados:
    
    1.  Haga clic en **Agregar filtro**.
    
    2.  Especifique la propiedad de usuario. Para ello, escríbala o haga clic en la flecha de la lista desplegable para seleccionar la propiedad.
    
    3.  En la lista desplegable **Igual a**, haga clic en el operador (por ejemplo, **Igual a** o **No igual a**).
    
    4.  En función de la propiedad de usuario que haya seleccionado, especifique los criterios que desee utilizar para filtrar los resultados de búsqueda escribiendo o haciendo clic en la flecha de la lista desplegable.
        

        > [!TIP]  
        > Para agregar cláusulas de búsqueda adicionales a la consulta, haga clic en <STRONG>Agregar filtro</STRONG>.

    
    5.  Haga clic en **Buscar**.

6.  Haga clic en un usuario en los resultados de búsqueda, haga clic en **Acción** y, a continuación, en **Asignar directivas**.
    

    > [!TIP]  
    > Si desea que la misma directiva de conferencia por usuario se aplique a varios usuarios, seleccione varios usuarios en los resultados de búsqueda, haga clic en <STRONG>acciones</STRONG>y, a continuación, haga clic en <STRONG>asignar directivas</STRONG>.



7.  En **asignar directivas**, en **Directiva de conferencia**, realice una de las siguientes acciones:
    

    > [!NOTE]  
    > Puesto que existen varias directivas que puede configurar en <STRONG>asignar directivas</STRONG>, <STRONG> &lt;mantener como está&gt; </STRONG> seleccionado de forma predeterminada para todas las directivas del cuadro de diálogo. Para seguir usando la directiva asignada anteriormente al usuario, no efectúe cambios en esta configuración.

    
      - Seleccione ** \<automático\> ** para permitir que Lync Server 2013 pueda elegir automáticamente la Directiva de nivel global o, si está definida, la Directiva de nivel de sitio.
    
      - Haga clic en el nombre de una directiva de conferencia por usuario que haya definido previamente en la página **Directiva de conferencia** .
        

        > [!TIP]  
        > Para ayudarle a decidir la directiva que desea asignar, tras hacer clic en el nombre de una directiva, haga clic en <STRONG>Ver</STRONG> para ver los derechos y permisos de usuario definidos en la directiva.



8.  Cuando haya terminado, haga clic en **Aceptar**.

## <a name="assigning-a-per-user-conferencing-policy-by-using-windows-powershell-cmdlets"></a>Asignar una directiva de conferencia por usuario mediante cmdlets de Windows PowerShell

Las directivas de conferencia por usuario se pueden asignar mediante Windows PowerShell y el cmdlet Grant-CsConferencingPolicy. Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.

## <a name="to-assign-a-per-user-conferencing-policy-to-a-single-user"></a>Para asignar una directiva de conferencia por usuario a un solo usuario

  - El comando siguiente asigna la Directiva de conferencia por usuario RedmondConferencingPolicy al usuario Ken Myer.
    
        Grant-CsConferencingPolicy -Identity "Ken Myer" -PolicyName "RedmondConferencingPolicy"

## <a name="to-assign-a-per-user-conferencing-policy-to-multiple-users"></a>Para asignar una directiva de conferencia por usuario a varios usuarios

  - Este comando asigna la Directiva de conferencia por usuario HRConferencingPolicy a todos los usuarios que trabajan para el Departamento de recursos humanos. Para obtener más información sobre el parámetro LdapFilter que se usa en este comando, consulte la documentación del cmdlet [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) .
    
        Get-CsUser -LdapFilter "Department=Human Resources" | Grant-CsConferencingPolicy -PolicyName "HRConferencingPolicy"

## <a name="to-unassign-a-per-user-conferencing-policy"></a>Para cancelar la asignación de una directiva de conferencia por usuario

  - El comando siguiente elimina la asignación de cualquier directiva de conferencia por usuario asignada previamente a Ken Myer. Después de quitar la asignación de la directiva por usuario, se usará automáticamente la directiva global o la directiva del sitio local, si existe, para administrar a Ken Myer. La directiva de sitio tiene prioridad sobre la directiva global.
    
        Grant-CsConferencingPolicy -Identity "Ken Myer" -PolicyName $Null

Para obtener más información, consulte el tema de ayuda para el cmdlet [Grant-CsConferencingPolicy](https://technet.microsoft.com/en-us/library/gg425937\(v=ocs.15\)) .

## <a name="see-also"></a>Vea también


[Crear o modificar una directiva de conferencia en Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md)  


[Asignación de directivas por usuario en Lync Server 2013](lync-server-2013-assigning-per-user-policies.md)

