---
title: 'Lync Server 2013: asignar una directiva de ubicación por usuario'
description: 'Lync Server 2013: asignar una directiva de ubicación por usuario.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user location policy
ms:assetid: 343f2de3-a0ae-4403-8456-6e520b579d32
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520974(v=OCS.15)
ms:contentKeyID: 48183794
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 81631740e0a6c908c392ccacb6b37d7033d9224c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559886"
---
# <a name="assign-a-per-user-location-policy-in-lync-server-2013"></a>Asignar una directiva de ubicación por usuario en Lync Server 2013

 


La Directiva de ubicación es una de las configuraciones individuales de una cuenta de usuario que se puede configurar en el panel de control de Lync Server.

La implementación de una o varias directivas de ubicación por usuario es opcional. También puede implementar solamente una directiva de ubicación de nivel global o una directiva de ubicación de nivel de subred. Si no implementa directivas por usuario, es preciso que las asigne explícitamente a un objeto de usuario, grupo o contacto. La configuración de Enhanced 9-1-1 (E9-1-1) establece automáticamente como predeterminada la definida en la directiva de ubicación de nivel global, en el caso de que no se haya asignado una directiva específica a nivel de subred o por usuario.

Tras crear al menos una directiva de ubicación por usuario, emplee los procedimientos de este tema para asignar a la directiva que especifique la configuración que desea que aplique el servidor para las llamadas de emergencia realizadas por parte de un usuario particular.

Para obtener una lista de todas las opciones de configuración de directivas de ubicación disponibles, consulte [Defining The location Policy for Lync Server 2013](lync-server-2013-defining-the-location-policy.md).

Para obtener información detallada sobre cómo crear directivas de ubicación, consulte [Create Location policies in Lync Server 2013](lync-server-2013-create-location-policies.md).

## <a name="to-assign-a-per-user-location-policy-with-the-lync-server-control-panel"></a>Para asignar una directiva de ubicación por usuario con el panel de control de Lync Server

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
    > Si desea aplicar la misma directiva de ubicación por usuario a varios usuarios, seleccione los distintos usuarios en los resultados de la búsqueda, haga clic en <STRONG>Acciones</STRONG> y, a continuación, en <STRONG>Asignar directivas</STRONG>.



7.  En **Asignar directivas**, en **Directiva de ubicación**, lleve a cabo uno de los procedimientos siguientes:
    

    > [!NOTE]  
    > Debido a que hay varias directivas que puede configurar mediante el cuadro de diálogo <STRONG>asignar directivas</STRONG> , se selecciona la opción <STRONG> &lt; mantener como está &gt; </STRONG> seleccionada de forma predeterminada para cada Directiva del cuadro de diálogo. Para seguir utilizando la directiva asignada anteriormente al usuario, no efectúe cambios en esta configuración.

    
      - Permita que Lync Server 2013 elija automáticamente la Directiva de nivel global o, si está definida, la Directiva de nivel de subred.
    
      - Haga clic en el nombre de una directiva de ubicación por usuario que haya definido anteriormente con el cmdlet **New-CsLocationPolicy**.
        

        > [!TIP]  
        > Para ayudarle a decidir la directiva que desea asignar, tras hacer clic en el nombre de una directiva, haga clic en <STRONG>Ver</STRONG> para ver los derechos y permisos de usuarios definidos en la directiva.



8.  Cuando haya terminado, haga clic en **Aceptar**.

## <a name="assigning-a-per-user-location-policy-by-using-lync-server-management-shell-cmdlets"></a>Asignación de una directiva de ubicación de Per-User mediante el uso de cmdlets del shell de administración de Lync Server

Puede asignar directivas de ubicación por usuario con el cmdlet Grant-CsLocationPolicy. Puede ejecutar este cmdlet desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server 2010 mediante PowerShell remoto" en [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

## <a name="to-assign-a-per-user-location-policy-to-a-single-user"></a>Para asignar una directiva de ubicación por usuario a un único usuario

  - El comando siguiente permite asignar la directiva de ubicación por usuario RedmondLocationPolicy al usuario Ken Myer.
    
        Grant-CsLocationPolicy -Identity "Ken Myer" -PolicyName "RedmondLocationPolicy"

## <a name="to-assign-a-per-user-location-policy-to-multiple-users"></a>Para asignar una directiva de ubicación por usuario a varios usuarios

  - Este comando permite asignar la directiva de ubicación por usuario AccountingDepartmentLocationPolicy a todos los usuarios que trabajen en el departamento de Contabilidad. Para obtener más información sobre el parámetro LdapFilter usado en este comando, consulte la documentación del cmdlet [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) .
    
        Get-CsUser -LdapFilter "Department=Accounting" | Grant-CsLocationPolicy -PolicyName "AccountingDepartmentLocationPolicy"

## <a name="to-unassign-a-per-user-location-policy"></a>Para cancelar la asignación de una directiva de ubicación por usuario

  - El comando que se describe a continuación permite cancelar la asignación de directiva de ubicación por usuario previamente asignada a Ken Myer. Una vez cancelada la asignación de la directiva por usuario, la administración del usuario Ken Myer se realizará de forma automática mediante la directiva global o, en caso de que exista, mediante la directiva de sitio local. Las directivas de sitios prevalecen sobre las directivas globales.
    
        Grant-CsLocationPolicy -Identity "Ken Myer" -PolicyName $Null

Para obtener más información, consulte el tema de ayuda para el cmdlet [Grant-CsLocationPolicy](https://technet.microsoft.com/library/gg413049\(v=ocs.15\)) .

