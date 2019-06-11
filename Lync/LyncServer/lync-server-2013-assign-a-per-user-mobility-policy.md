---
title: 'Lync Server 2013: asignar una directiva de movilidad por usuario'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign a per-user mobility policy
ms:assetid: d8bf997f-4bc7-48d3-973b-323505f55e9d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721902(v=OCS.15)
ms:contentKeyID: 49733836
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e79a9b76ac4774bbbac7772bef19902d6d70f15a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850705"
---
# <a name="assign-a-per-user-mobility-policy-in-lync-server-2013"></a>Asignar una directiva de movilidad por usuario en Lync Server 2013

 


La Directiva de movilidad es una de las opciones de configuración individuales de una cuenta de usuario que puede configurar en el panel de control de Lync Server o en el shell de administración de Lync Server.

## <a name="to-assign-a-per-user-mobility-policy-with-lync-server-control-panel"></a>Para asignar una directiva de movilidad por usuario con el panel de control de Lync Server

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
    > Si quiere que la misma directiva de movilidad por usuario se aplique a varios usuarios, seleccione varios usuarios en los resultados de búsqueda, haga clic en <STRONG>acciones</STRONG>y, a continuación, haga clic en <STRONG>asignar directivas</STRONG>.



7.  En **asignar directivas**, en **Directiva de movilidad**, realice una de las siguientes acciones:
    

    > [!NOTE]  
    > Puesto que existen varias directivas que puede configurar en <STRONG>asignar directivas</STRONG>, <STRONG> &lt;mantener como está&gt; </STRONG> seleccionado de forma predeterminada para todas las directivas del cuadro de diálogo. Para seguir usando la directiva asignada anteriormente al usuario, no efectúe cambios en esta configuración.

    
      - Seleccione ** \<automático\> ** para permitir que Lync Server 2013 pueda elegir automáticamente la Directiva de nivel global o, si está definida, la Directiva de nivel de sitio.
    
      - Haga clic en el nombre de una directiva de movilidad por usuario que haya definido previamente en la página **Directiva de movilidad** .
        

        > [!TIP]  
        > Para ayudarle a decidir la directiva que desea asignar, tras hacer clic en el nombre de una directiva, haga clic en <STRONG>Ver</STRONG> para ver los derechos y permisos de usuario definidos en la directiva.



8.  Cuando haya terminado, haga clic en **Aceptar**.

## <a name="assigning-a-per-user-mobility-policy-by-using-windows-powershell-cmdlets"></a>Asignar una directiva de movilidad por usuario mediante cmdlets de Windows PowerShell

Puede asignar directivas de movilidad por usuario mediante Windows PowerShell y el cmdlet **Grant-CsMobilityPolicy** . Puede ejecutar este cmdlet desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.

## <a name="to-assign-a-per-user-mobility-policy-to-a-single-user"></a>Para asignar una directiva de movilidad por usuario a un solo usuario

  - El comando siguiente asigna la Directiva de movilidad por usuario RedmondMobilityPolicy al usuario Ken Myer.
    
        Grant-CsMobilityPolicy -Identity "Ken Myer" -PolicyName "RedmondMobilityPolicy"

## <a name="to-assign-a-per-user-mobility-policy-to-multiple-users"></a>Para asignar una directiva de movilidad por usuario a varios usuarios

  - El comando siguiente asigna la Directiva de movilidad por usuario RedmondMobilityPolicy a todos los usuarios que actualmente tienen asignada la Directiva NorthAmericaMobilityPolicy. Para obtener más información sobre el parámetro de filtro usado en este comando, vea [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)).
    
        Get-CsUser -Filter {MobilityPolicy -eq "NorthAmericaMobilityPolicy"} | Grant-CsMobilityPolicy -PolicyName "RedmondMobilityPolicy"

## <a name="to-unassign-a-per-user-mobility-policy"></a>Para cancelar la asignación de una directiva de movilidad por usuario

  - El comando siguiente elimina la asignación de cualquier directiva de movilidad por usuario asignada previamente a Ken Myer. Después de quitar la asignación de la directiva por usuario, se usará automáticamente la directiva global o la directiva del sitio local, si existe, para administrar a Ken Myer. La directiva de sitio tiene prioridad sobre la directiva global.
    
        Grant-CsMobilityPolicy -Identity "Ken Myer" -PolicyName $Null

Para obtener más información, consulte [Grant-CsMobilityPolicy](https://technet.microsoft.com/en-us/library/hh690038\(v=ocs.15\)).

## <a name="see-also"></a>Vea también


[Configuración de la directiva de movilidad en Lync Server 2013](lync-server-2013-configuring-mobility-policy.md)

