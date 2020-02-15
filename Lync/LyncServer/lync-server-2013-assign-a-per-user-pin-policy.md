---
title: 'Lync Server 2013: asignar una directiva de PIN por usuario'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user PIN policy
ms:assetid: d8211c64-0b63-4193-a074-673da7d14287
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182594(v=OCS.15)
ms:contentKeyID: 48185475
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9523794808ca3b689cf1f3213c1f4ad657c83c25
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030123"
---
# <a name="assign-a-per-user-pin-policy-in-lync-server-2013"></a>Asignar una directiva de PIN por usuario en Lync Server 2013

 


La Directiva de número de identificación personal (PIN) de conferencia de acceso telefónico local es una de las configuraciones individuales de una cuenta de usuario que se puede configurar en el panel de control de Lync Server 2013.

La implementación de una o más directivas de PIN por usuario es opcional. Asimismo, puede implementar solamente una directiva de PIN a nivel global o a nivel de sitio. Si implementa directivas por usuario, es preciso que las asigne explícitamente a un objeto de usuario, grupo o contacto. Los derechos y permisos de usuario para el uso de PIN de conferencia de acceso telefónico local pasan a ser, de forma predeterminada, los definidos en la directiva de PIN de nivel global cuando no se haya asignado una directiva específica de nivel de sitio o por usuario.

Tras crear al menos una directiva de PIN por usuario, emplee los procedimientos de este tema para asignar la directiva que especifique las restricciones que desee que imponga el servidor en los PIN que haya creado y usado un usuario en particular.

Para obtener información detallada sobre cómo crear directivas de PIN de conferencia de acceso telefónico local por usuario, vea [crear o modificar la configuración de PIN de conferencia de acceso telefónico local en Lync Server 2013 para un sitio o grupo de usuarios](lync-server-2013-create-or-modify-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md).

## <a name="to-assign-a-per-user-pin-policy"></a>Para asignar una directiva de PIN por usuario

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
    > Si desea aplicar la misma directiva de PIN por usuario a varios usuarios, seleccione los distintos usuarios en los resultados de la búsqueda, haga clic en <STRONG>Acciones</STRONG> y después en <STRONG>Asignar directivas</STRONG>.



7.  En **Asignar directivas**, en **Directiva de PIN**, realice uno de los procedimientos siguientes:
    

    > [!NOTE]  
    > Debido a que hay varias directivas que puede configurar mediante el cuadro de diálogo <STRONG>asignar directivas</STRONG> , <STRONG> &lt;se selecciona la&gt; opción mantener como está</STRONG> seleccionada de forma predeterminada para cada Directiva del cuadro de diálogo. Para seguir utilizando la directiva asignada anteriormente al usuario, no efectúe cambios en esta configuración.

    
      - Permita que Lync Server 2013 elija automáticamente la Directiva de nivel global o, si está definida, la Directiva de nivel de sitio.
    
      - Haga clic en el nombre de una directiva de PIN por usuario que haya definido anteriormente en la página **Directiva de PIN**.
        

        > [!TIP]  
        > Para que le sea más fácil decidir la directiva que desea asignar, tras hacer clic en el nombre de una directiva, haga clic en <STRONG>Ver</STRONG> para ver los derechos y permisos de usuario definidos en la directiva.



8.  Cuando haya terminado, haga clic en **Aceptar**.

## <a name="assigning-a-per-user-pin-policy-by-using-windows-powershell-cmdlets"></a>Asignar una directiva de PIN por usuario mediante cmdlets de Windows PowerShell

Puede asignar directivas de PIN por usuario con Windows PowerShell y el cmdlet **Grant-CsPinPolicy** . Puede ejecutar este cmdlet desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.

## <a name="to-assign-a-per-user-pin-policy-to-a-single-user"></a>Asignar una directiva de PIN por usuario a un único usuario

  - El comando siguiente asigna la directiva de PIN por usuario RedmondPinPolicy al usuario Ken Myer.
    
        Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName "RedmondPinPolicy"

## <a name="to-assign-a-per-user-pin-policy-to-multiple-users"></a>Asignar una directiva de PIN por usuario a varios usuarios

  - El comando siguiente asigna la directiva de PIN por usuario RedmondUsersPinPolicy a todos los usuarios que trabajan en la ciudad de Redmond. Para obtener más información sobre el parámetro LdapFilter usado en este comando, consulte [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)).
    
        Get-CsUser -LdapFilter "l=Redmond" | Grant-CsPinPolicy -PolicyName "RedmondUsersPinPolicy"

## <a name="to-unassign-a-per-user-pin-policy"></a>Quitar la asignación de una directiva de PIN por usuario

  - El comando siguiente quita la asignación de las directivas de PIN por usuario asignadas previamente a Ken Myer. Después de quitar la asignación de la directiva por usuario, se usará automáticamente la directiva global o la directiva del sitio local, si existe, para administrar a Ken Myer. La directiva de sitio tiene prioridad sobre la directiva global.
    
        Grant-CsPinPolicy -Identity "Ken Myer" -PolicyName $Null

Para obtener más información, consulte [Grant-CsPinPolicy](https://technet.microsoft.com/library/gg398871\(v=ocs.15\)).

## <a name="see-also"></a>Vea también


[Crear una directiva de PIN nueva en Lync Server 2013](lync-server-2013-create-a-new-pin-policy.md)  


[Asignación de directivas por usuario en Lync Server 2013](lync-server-2013-assigning-per-user-policies.md)

