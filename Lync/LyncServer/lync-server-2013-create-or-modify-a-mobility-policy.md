---
title: 'Lync Server 2013: crear o modificar una directiva de movilidad'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a mobility policy
ms:assetid: fc2dfea0-2215-440d-9f4b-7c985da29211
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721946(v=OCS.15)
ms:contentKeyID: 49733884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a240c55b4478c5cf5f67a4f0774b1979e884b3b0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208006"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-mobility-policy-in-lync-server-2013"></a>Crear o modificar una directiva de movilidad en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-23_

Puede crear o modificar directivas de movilidad para permitir a los usuarios de móviles utilizar los dispositivos móviles compatibles para las funcionalidades de Lync, como la mensajería instantánea (MI), presencia y contactos. Puede crear o modificar directivas de movilidad desde el panel de control de Lync Server 2013 o el shell de administración de Lync Server 2013

<div>

## <a name="to-create-a-mobility-policy-with-lync-server-control-panel"></a>Para crear una directiva de movilidad con el panel de control de Lync Server

1.  Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Clientes** y, a continuación, en el botón de navegación **Directiva de movilidad**.

4.  En la página **Directiva de movilidad** , haga clic en **nuevo**y realice una de las siguientes acciones:
    
    1.  Para crear una directiva de movilidad de sitio, haga clic en **Directiva de sitio**, haga clic en un sitio y en **Aceptar**. Reviste la configuración predeterminada y realice los cambios que desee.
    
    2.  Para crear una directiva de movilidad, haga clic en **Directiva de usuario**, escriba un nombre, revise la configuración predeterminada y realice los cambios que desee.

5.  Haga clic en **Confirmar**.

</div>

<div>

## <a name="to-modify-a-mobility-policy-with-lync-server-control-panel"></a>Para modificar una directiva de movilidad con el panel de control de Lync Server

1.  Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Clientes** y, a continuación, en el botón de navegación **Directiva de movilidad**.

4.  En la página **Directiva de movilidad** , haga clic en una de las directivas de movilidad existentes.

5.  En el menú **Editar **, haga clic en **Mostrar detalles **.

6.  Edite cualquiera de las opciones.

7.  Haga clic en **Confirmar **.

</div>

<div>

## <a name="creating-external-access-policies-by-using-windows-powershell-cmdlets"></a>Creación de directivas de acceso externo mediante cmdlets de Windows PowerShell

Puede crear directivas de movilidad (en el ámbito del sitio o en el ámbito por usuario) mediante Windows PowerShell y el cmdlet **New-CsMobilityPolicy** . Además, puede utilizar el cmdlet **Set-CsMobilityPolicy** para modificar cualquiera de las directivas existentes, incluida la directiva global. Estos cmdlets se pueden ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.

<div>

## <a name="to-create-a-mobility-policy-at-the-site-scope"></a>Para crear una directiva de movilidad en el ámbito de sitio

  - Este comando crea una directiva de movilidad nueva para el sitio Redmond:
    
        New-CsMobilityPolicy -Identity "site:Redmond"
    
    Como no se han especificado parámetros (aparte del parámetro obligatorio Identity) en el comando anterior, las directivas utilizarán los valores predeterminados en todas sus propiedades.

</div>

<div>

## <a name="to-create-a-mobility-policy-at-the-per-user-scope"></a>Para crear una directiva de movilidad en el ámbito por usuario

  - Para crear una directiva de movilidad en el ámbito de usuario, especifique una identidad única para la directiva:
    
        New-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-a-mobility-policy"></a>Para cambiar un valor de propiedad único al crear una directiva de movilidad

  - Para crear directivas que utilicen diferentes valores de propiedad, incluya el parámetro adecuado y el valor de parámetro. Por ejemplo, este comando crea una directiva de movilidad que deshabilita las llamadas vía trabajo:
    
        New-CsMobilityPolicy -Identity "site:Redmond" -EnableOutsideVoice $False

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-a-mobility-policy"></a>Para cambiar varios valores de propiedad al crear una directiva de movilidad

  - Se pueden modificar varios valores de propiedad incluyendo varios parámetros. Por ejemplo, este comando crea una directiva que deshabilita tanto la movilidad como la llamada vía trabajo:
    
        New-CsMobilityPolicy "site:Redmond" -EnableMobility $False -EnableOutsideVoice $False

</div>

Para obtener más información, consulte el tema de ayuda relativo a los cmdlets [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy) y [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy).

</div>

<div>

## <a name="see-also"></a>Consulta también


[Configuración de la Directiva de movilidad en Lync Server 2013](lync-server-2013-configuring-mobility-policy.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

