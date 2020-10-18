---
title: 'Lync Server 2013: crear o modificar una nueva Directiva de versión de cliente'
description: 'Lync Server 2013: cree o modifique una nueva Directiva de versión de cliente.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a new client version policy
ms:assetid: 4be6e449-aa82-4b46-abb1-d31281573a72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898476(v=OCS.15)
ms:contentKeyID: 50873756
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d4d100e21591a27646784161614ff6c248dc6ae6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574616"
---
# <a name="create-or-modify-a-new-client-version-policy-in-lync-server-2013"></a>Crear o modificar una nueva Directiva de versión de cliente en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-23_

Puede usar las directivas de versión de cliente para especificar las versiones de clientes que son compatibles con su entorno. El uso del control de versiones de cliente puede ayudar a reducir los costos asociados a la compatibilidad con varias versiones de cliente. También puede mejorar la experiencia general del usuario, ya que cuando interactúan versiones anteriores y posteriores de los clientes, las características disponibles pueden estar limitadas por la versión anterior del cliente. Puede crear o modificar directivas de versión de cliente desde el panel de control de Lync Server 2013 o el shell de administración de Lync Server 2013.

<div>

## <a name="to-create-or-modify-client-version-policies-by-using-lync-server-control-panel"></a>Para crear o modificar directivas de versión de cliente mediante el panel de control de Lync Server

1.  Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Clientes**.
    
    <div>
    

    > [!NOTE]  
    > La pestaña <STRONG>Directiva de versión de cliente</STRONG> está seleccionada de forma predeterminada.

    
    </div>

4.  En la página **Directiva de versión de cliente** , realice una de las siguientes acciones:
    
      - Para crear una directiva de versión de cliente, haga clic en **nuevo**, seleccione Directiva de **sitio**, **Directiva de grupo**de servidores o Directiva de **usuario**y, a continuación, haga clic en **Aceptar**.
    
      - Para modificar la directiva global u otra directiva de versión de cliente existente, seleccione la Directiva, haga clic en **Editar**y, a continuación, haga clic en **Mostrar detalles**.

5.  En la página **Editar Directiva de versión de cliente** , cree o modifique reglas tal y como se describe en [Create or Modify a New Client version Policy Rule in Lync Server 2013](lync-server-2013-create-or-modify-a-new-client-version-policy-rule.md).

</div>

<div>

## <a name="creating-or-modifying-client-version-policies-by-using-windows-powershell-cmdlets"></a>Creación o modificación de directivas de versión de cliente mediante cmdlets de Windows PowerShell

Puede crear directivas de versión de cliente con el cmdlet **New-CsClientVersionPolicy** y modificarlas con el cmdlet **set-CsClientVersionPolicy** . Estos cmdlets se pueden ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server 2010 mediante PowerShell remoto" en [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-create-a-new-site-scoped-client-version-policy"></a>Para crear una nueva Directiva de versión de cliente con ámbito en el sitio

  - El siguiente comando crea una nueva Directiva de versión de cliente que se aplica al sitio Redmond. Como no se especifican parámetros adicionales, la nueva Directiva usará la configuración de versión de cliente predeterminada.
    
        New-CsClientVersionPolicy -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-new-per-user-client-version-policy"></a>Para crear una nueva Directiva de versión de cliente por usuario

  - Para crear una directiva por usuario, use un comando similar al siguiente:
    
        New-CsClientVersionPolicy -Identity "RedmondClientVersionPolicy"

</div>

Para obtener más información, consulte los temas de ayuda del cmdlet [New-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientVersionPolicy) y el cmdlet [set-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionPolicy) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

