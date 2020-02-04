---
title: 'Lync Server 2013: asignar una directiva de archivado por usuario'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user archiving policy
ms:assetid: a12ca483-b235-460f-b3fe-130fb3087264
ms:mtpsurl: https://technet.microsoft.com/library/Gg182560(v=OCS.15)
ms:contentKeyID: 48185014
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e633521b00277dcc5f0e7dec96ab0250a8934574
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738400"
---
# <a name="assign-a-per-user-archiving-policy-in-lync-server-2013"></a>Asignar una directiva de archivado por usuario en Lync Server 2013

 


La Directiva de archivado es una de las configuraciones individuales de una cuenta de usuario que puede configurar en el panel de control de Lync Server 2013.

La implementación de una o más directivas de archivado por usuario es opcional. También puede implementar una directiva de archivado de nivel global o una directiva de archivado de nivel de sitio. Si implementa directivas por usuario, es preciso que las asigne explícitamente a un objeto de usuario, grupo o contacto. Los requisitos de archivado se especifican de forma automática predeterminada para los definidos en la Directiva de conferencia global cuando no se ha asignado ninguna directiva específica de nivel de sitio o de usuario.

Después de crear al menos una directiva de archivado por usuario, use los procedimientos de este tema para asignar la Directiva que especifica correctamente si el servidor archivará las comunicaciones internas, las comunicaciones externas o ambas de un usuario en particular.

Para obtener más información sobre la creación de directivas de archivado por usuario, consulte [crear una directiva de archivado en Lync Server 2013 para habilitar o deshabilitar el archivado de las comunicaciones internas o externas para determinados sitios o usuarios](lync-server-2013-create-archiving-policy-sites-users.md).

## <a name="to-assign-a-per-user-archiving-policy"></a>Para asignar una directiva de archivado por usuario

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
    > Si desea aplicar la misma directiva de archivado por usuario a varios usuarios, seleccione varios usuarios en los resultados de búsqueda, haga clic en <STRONG>acciones</STRONG>y, a continuación, haga clic en <STRONG>asignar directivas</STRONG>.



7.  En **asignar directivas**, en **Directiva de archivado**, siga uno de estos procedimientos:
    

    > [!NOTE]  
    > Puesto que existen varias directivas que puede configurar mediante el cuadro de diálogo <STRONG>asignar directivas</STRONG> , <STRONG> &lt;&gt; </STRONG> la opción mantener está seleccionada de forma predeterminada para todas las directivas del cuadro de diálogo. Para seguir usando la directiva asignada anteriormente al usuario, no efectúe cambios en esta configuración.

    
      - Permita Lync Server 2013 para elegir automáticamente la Directiva de nivel global o, si se ha definido, la Directiva de nivel de sitio.
    
      - Haga clic en el nombre de una directiva de archivado por usuario que haya definido previamente en la página **Directiva de archivado** .
        

        > [!TIP]  
        > Para ayudarle a decidir la Directiva que desea asignar, después de hacer clic en un nombre de Directiva, haga clic en <STRONG>Ver</STRONG> para ver los derechos de usuario y permisos definidos en la Directiva.



8.  Cuando haya terminado, haga clic en **Aceptar**.

## <a name="assigning-a-per-user-archiving-policy-by-using-windows-powershell-cmdlets"></a>Asignar una directiva de archivado por usuario mediante cmdlets de Windows PowerShell

Puede asignar directivas de archivado por usuario mediante Windows PowerShell y el cmdlet **Grant-CsArchivingPolicy** . Puede ejecutar este cmdlet desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.

## <a name="to-assign-a-per-user-archiving-policy-to-a-single-user"></a>Para asignar una directiva de archivado por usuario a un solo usuario

  - El siguiente comando permite asignar la directiva de archivado por usuario RedmondArchivingPolicy al usuario Ken Myer.
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"

## <a name="to-assign-a-per-user-archiving-policy-to-multiple-users"></a>Para asignar una directiva de archivado por usuario a varios usuarios

  - Este comando asigna el RedmondArchivingPolicy de directiva de archivado por usuario a todos los usuarios que tienen cuentas alojadas en el registro de la agrupación de atl-cs-001.litwareinc.com. Para obtener más información sobre el parámetro de filtro usado en este comando, consulte la documentación del cmdlet [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) .
    
        Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"

## <a name="to-unassign-a-per-user-archiving-policy"></a>Para cancelar la asignación de una directiva de archivado por usuario

  - El comando siguiente elimina la asignación de cualquier directiva de archivado por usuario previamente asignada a Ken Myer. Después de quitar la asignación de la directiva por usuario, se usará automáticamente la directiva global o la directiva del sitio local, si existe, para administrar a Ken Myer. La directiva de sitio tiene prioridad sobre la directiva global.
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null

Para obtener más información, consulte el tema de ayuda para el cmdlet [Grant-CsArchivingPolicy](https://technet.microsoft.com/library/gg398475\(v=ocs.15\)) .

## <a name="see-also"></a>Vea también


[Crear una directiva de archivado en Lync Server 2013 para habilitar o deshabilitar el archivado de las comunicaciones internas o externas para usuarios o sitios específicos](lync-server-2013-create-archiving-policy-sites-users.md)  


[Asignación de directivas por usuario en Lync Server 2013](lync-server-2013-assigning-per-user-policies.md)

