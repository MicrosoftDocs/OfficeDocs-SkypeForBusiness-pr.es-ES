---
title: 'Lync Server 2013: asignar una directiva de ubicación por usuario'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign a per-user location policy
ms:assetid: 343f2de3-a0ae-4403-8456-6e520b579d32
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520974(v=OCS.15)
ms:contentKeyID: 48183794
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4a387d0f603addea31bd1e3ee6b591e06a26b2c4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850747"
---
# <a name="assign-a-per-user-location-policy-in-lync-server-2013"></a>Asignar una directiva de ubicación por usuario en Lync Server 2013

 


La Directiva de ubicación es una de las configuraciones individuales de una cuenta de usuario que puede configurar en el panel de control de Lync Server.

Implementar una o más directivas de ubicación para cada usuario es opcional. También puede implementar una directiva de ubicación global o una directiva de ubicación de nivel de subred. Si implementa directivas por usuario, es preciso que las asigne explícitamente a un objeto de usuario, grupo o contacto. La configuración mejorada de 9-1-1 (E9-1-1) se asigna de forma predeterminada a los valores definidos en la Directiva de ubicación global cuando no se ha asignado ninguna directiva específica de subred o de usuario.

Después de crear al menos una directiva de ubicación por usuario, use los procedimientos de este tema para asignar a la Directiva que especifica la configuración que quiere que el servidor aplique para las llamadas de emergencia realizadas por un usuario en particular.

Para obtener una lista de todas las opciones de configuración de la Directiva de ubicación disponibles, consulte [definir la Directiva de ubicación de Lync Server 2013](lync-server-2013-defining-the-location-policy.md).

Para obtener detalles sobre la creación de directivas de ubicación, consulte [crear directivas de ubicación en Lync Server 2013](lync-server-2013-create-location-policies.md).

## <a name="to-assign-a-per-user-location-policy-with-the-lync-server-control-panel"></a>Para asignar una directiva de ubicación por usuario con el panel de control de Lync Server

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
    > Si desea aplicar la misma directiva de ubicación por usuario a varios usuarios, seleccione varios usuarios en los resultados de búsqueda, haga clic en <STRONG>acciones</STRONG>y, a continuación, haga clic en <STRONG>asignar directivas</STRONG>.



7.  En **asignar directivas**, en **Directiva de ubicación**, realice una de las siguientes acciones:
    

    > [!NOTE]  
    > Puesto que existen varias directivas que puede configurar mediante el cuadro de diálogo <STRONG>asignar directivas</STRONG> , <STRONG> &lt;&gt; </STRONG> la opción mantener está seleccionada de forma predeterminada para todas las directivas del cuadro de diálogo. Para seguir usando la directiva asignada anteriormente al usuario, no efectúe cambios en esta configuración.

    
      - Permita Lync Server 2013 para elegir automáticamente la Directiva de nivel global o, si está definida, la Directiva de nivel de subred.
    
      - Haga clic en el nombre de una directiva de ubicación por usuario que haya definido previamente ejecutando el cmdlet **New-CsLocationPolicy** .
        

        > [!TIP]  
        > Para ayudarle a decidir la Directiva que desea asignar, después de hacer clic en un nombre de Directiva, haga clic en <STRONG>Ver</STRONG> para ver los derechos de usuario y permisos definidos en la Directiva.



8.  Cuando haya terminado, haga clic en **Aceptar**.

## <a name="assigning-a-per-user-location-policy-by-using-lync-server-management-shell-cmdlets"></a>Asignar una directiva de ubicación por usuario mediante los cmdlets del shell de administración de Lync Server

Puede asignar directivas de ubicación por usuario mediante el cmdlet Grant-CsLocationPolicy. Puede ejecutar este cmdlet desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.

## <a name="to-assign-a-per-user-location-policy-to-a-single-user"></a>Para asignar una directiva de ubicación por usuario a un solo usuario

  - El comando siguiente asigna la Directiva de ubicación por usuario RedmondLocationPolicy al usuario Ken Myer.
    
        Grant-CsLocationPolicy -Identity "Ken Myer" -PolicyName "RedmondLocationPolicy"

## <a name="to-assign-a-per-user-location-policy-to-multiple-users"></a>Para asignar una directiva de ubicación por usuario a varios usuarios

  - Este comando asigna la Directiva de ubicación por usuario AccountingDepartmentLocationPolicy a todos los usuarios que trabajan para el Departamento de contabilidad. Para obtener más información sobre el parámetro LdapFilter que se usa en este comando, consulte la documentación del cmdlet [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) .
    
        Get-CsUser -LdapFilter "Department=Accounting" | Grant-CsLocationPolicy -PolicyName "AccountingDepartmentLocationPolicy"

## <a name="to-unassign-a-per-user-location-policy"></a>Para cancelar la asignación de una directiva de ubicación por usuario

  - El comando siguiente elimina la asignación de cualquier directiva de ubicación por usuario asignada previamente a Ken Myer. Después de quitar la asignación de la directiva por usuario, se usará automáticamente la directiva global o la directiva del sitio local, si existe, para administrar a Ken Myer. La directiva de sitio tiene prioridad sobre la directiva global.
    
        Grant-CsLocationPolicy -Identity "Ken Myer" -PolicyName $Null

Para obtener más información, consulte el tema de ayuda para el cmdlet [Grant-CsLocationPolicy](https://technet.microsoft.com/en-us/library/gg413049\(v=ocs.15\)) .

