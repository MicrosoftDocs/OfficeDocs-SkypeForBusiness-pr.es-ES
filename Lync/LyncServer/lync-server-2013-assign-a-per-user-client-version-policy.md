---
title: 'Lync Server 2013: asignar una directiva de versión de cliente por usuario'
description: 'Lync Server 2013: asignar una directiva de versión de cliente por usuario.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user client version policy
ms:assetid: f7e8ba2f-62dc-4e7d-8b63-682986f10240
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182607(v=OCS.15)
ms:contentKeyID: 48185868
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ec2fcbf9c005806a97dfbdceb22095fe0ff8f33
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559986"
---
# <a name="assign-a-per-user-client-version-policy-in-lync-server-2013"></a>Asignar una directiva de versión de cliente por usuario en Lync Server 2013

 


La Directiva de versión de cliente es una de las configuraciones individuales de una cuenta de usuario que se puede configurar en el panel de control de Lync Server.

La implementación de una o varias directivas de versión de cliente por usuario es opcional. También puede implementar solamente una directiva de versión de cliente en el nivel global, o directivas de versión de cliente en el nivel de sitio o en el nivel de grupo de servidores. Si no implementa directivas por usuario, es preciso que las asigne explícitamente a un objeto de usuario, grupo o contacto. Cuando no se asigna ninguna directiva específica de nivel de sitio, nivel de grupo o por usuario, los clientes predeterminados que se pueden registrar con Lync Server 2013 son los que se definen en la Directiva de versión de cliente de nivel global.

Después de crear al menos una directiva de versión de cliente por usuario, use los procedimientos de este tema para asignar la Directiva que especifica las versiones de cliente que desea permitir para registrarse en Lync Server.

Para obtener información detallada sobre cómo crear directivas de versión de cliente por usuario, vea [especificar las aplicaciones cliente que se pueden usar para iniciar sesión en Lync Server 2013](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md).

## <a name="to-assign-a-per-user-client-version-policy"></a>Para asignar una directiva de versión de cliente por usuario

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
    > Si desea que se aplique la misma directiva de versión de cliente por usuario a varios usuarios, seleccione varios usuarios en los resultados de búsqueda y, a continuación, haga clic en <STRONG>Acciones</STRONG> y <STRONG>Asignar directivas</STRONG>.



7.  En **Asignar directivas**, en **Directiva de versión de cliente**, realice una de las siguientes acciones:
    

    > [!NOTE]  
    > Debido a que hay varias directivas que puede configurar mediante el cuadro de diálogo <STRONG>asignar directivas</STRONG> , se selecciona la opción <STRONG> &lt; mantener como está &gt; </STRONG> seleccionada de forma predeterminada para cada Directiva del cuadro de diálogo. Para seguir utilizando la directiva asignada anteriormente al usuario, no efectúe cambios en esta configuración.

    
      - Permita que Lync Server elija automáticamente la Directiva de nivel global o, si está definida, la Directiva de nivel de sitio o la Directiva de nivel de grupo.
    
      - Haga clic en el nombre de una directiva de versión de cliente por usuario que haya definido previamente en la página **Directiva de versión de cliente**.
        

        > [!TIP]  
        > Para ayudarle a decidir la directiva que desea asignar, tras hacer clic en el nombre de una directiva, haga clic en <STRONG>Ver</STRONG> para ver los derechos y permisos de usuario definidos en la directiva.



8.  Cuando haya terminado, haga clic en **Aceptar**.

## <a name="assigning-a-per-user-client-version-policy-by-using-windows-powershell-cmdlets"></a>Asignación de una directiva de versión de cliente de Per-User mediante cmdlets de Windows PowerShell

Puede asignar directivas de versión por usuario usando el cmdlet Grant-CsClientVersionPolicy. Puede ejecutar este cmdlet desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server 2010 mediante PowerShell remoto" en [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

## <a name="to-assign-a-per-user-client-version-policy-to-a-single-user"></a>Para asignar una directiva de versión por usuario a un solo usuario

  - El comando siguiente asigna la directiva de versión de cliente por usuario RedmondClientVersionPolicy al usuario Ken Myer.
    
        Grant-CsClientVersionPolicy -Identity "Ken Myer" -PolicyName "RedmondClientVersionPolicy"

## <a name="to-assign-a-per-user-client-version-policy-to-multiple-users"></a>Para asignar una directiva de versión de cliente por usuario a varios usuarios

  - Este comando asigna la directiva de versión de cliente por usuario RedmondClientVersionPolicy a todos los usuarios que tienen actualmente asignada la directiva de voz RedmondVoicePolicy. Para obtener más información sobre el parámetro filter usado en este comando, consulte la documentación del cmdlet [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) .
    
        Get-CsUser -Filter {VoicePolicy -eq "RedmondVoicePolicy"} | Grant-CsClientVersionPolicy -PolicyName "RedmondClientVersionPolicy"

## <a name="to-unassign-a-per-user-client-version-policy"></a>Para cancelar la asignación de una directiva de versión de cliente por usuario

  - El comando siguiente cancela la asignación de la directiva de versión de cliente por usuario que hemos asignado anteriormente a Ken Myer. Una vez cancelada, Ken Myer será administrado automáticamente usando la directiva global, su directiva de sitio local (si existe) o la directiva de ámbito de servicio asignada a su Registrador. La directiva de ámbito de servicio tiene prioridad sobre cualquier directiva de sitio y una directiva de sitio tiene prioridad sobre la directiva global.
    
        Grant-CsClientVersionPolicy -Identity "Ken Myer" -PolicyName $Null

Para obtener más información, consulte el tema de ayuda para el cmdlet [Grant-CsClientVersionPolicy](https://technet.microsoft.com/library/gg412903\(v=ocs.15\)) .

## <a name="see-also"></a>Consulte también


[Asignación de directivas por usuario en Lync Server 2013](lync-server-2013-assigning-per-user-policies.md)  
[Administración de dispositivos, teléfonos y aplicaciones cliente en Lync Server 2013](lync-server-2013-managing-devices-phones-and-client-applications.md)

