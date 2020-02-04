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
ms.openlocfilehash: 3f64e74b389b268027e06b2f4103b0c828c5be6f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758054"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-mobility-policy-in-lync-server-2013"></a>Crear o modificar una directiva de movilidad en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-23_

Puede crear o modificar la Directiva de movilidad para permitir a los usuarios móviles usar dispositivos móviles compatibles para las características de Lync, como la mensajería instantánea (mi), la presencia y los contactos. Puede crear o modificar directivas de movilidad desde el panel de control de Lync Server 2013 o del shell de administración de Lync Server 2013

<div>

## <a name="to-create-a-mobility-policy-with-lync-server-control-panel"></a>Para crear una directiva de movilidad con el panel de control de Lync Server

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **clientes**y luego en el botón de navegación de la **Directiva de movilidad** .

4.  En la página **Directiva de movilidad** , haga clic en **nuevo**y realice una de las siguientes acciones:
    
    1.  Para crear una directiva de movilidad de sitio, haga clic en **Directiva del sitio**, haga clic en un sitio, haga clic en **Aceptar**, revise la configuración predeterminada y, si lo desea, realice los cambios.
    
    2.  Para crear una directiva de movilidad de usuario, haga clic en **Directiva de usuario**, escriba un nombre, revise la configuración predeterminada y, si lo desea, realice los cambios.

5.  Haga clic en **Confirmar**.

</div>

<div>

## <a name="to-modify-a-mobility-policy-with-lync-server-control-panel"></a>Para modificar una directiva de movilidad con el panel de control de Lync Server

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **clientes**y luego en el botón de navegación de la **Directiva de movilidad** .

4.  En la página **Directiva de movilidad** , haga clic en una de las directivas de movilidad existentes.

5.  En el menú **Editar**, haga clic en **Mostrar detalles**.

6.  Edite cualquiera de los valores de configuración.

7.  Haga clic en **Confirmar**.

</div>

<div>

## <a name="creating-external-access-policies-by-using-windows-powershell-cmdlets"></a>Crear directivas de acceso externas mediante cmdlets de Windows PowerShell

Puede crear directivas de movilidad (en el ámbito del sitio o en el ámbito por usuario) mediante Windows PowerShell y el cmdlet **New-CsMobilityPolicy** . Además, puede usar el cmdlet **set-CsMobilityPolicy** para modificar cualquiera de las directivas existentes, incluida la directiva global. Estos cmdlets se pueden ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.

<div>

## <a name="to-create-a-mobility-policy-at-the-site-scope"></a>Para crear una directiva de movilidad en el ámbito del sitio

  - Este comando crea una nueva Directiva de movilidad para el sitio de Redmond:
    
        New-CsMobilityPolicy -Identity "site:Redmond"
    
    Dado que no se especificó ningún parámetro (excepto el parámetro de identidad obligatorio) en el comando anterior, las directivas usarán los valores predeterminados para todas sus propiedades.

</div>

<div>

## <a name="to-create-a-mobility-policy-at-the-per-user-scope"></a>Para crear una directiva de movilidad en el ámbito de cada usuario

  - Para crear una directiva de movilidad en el ámbito de cada usuario, especifique una identidad única para la Directiva:
    
        New-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-a-mobility-policy"></a>Para cambiar un único valor de propiedad al crear una directiva de movilidad

  - Para crear directivas que usen valores de propiedad diferentes, incluya el parámetro adecuado y el valor de parámetro. Por ejemplo, este comando crea una directiva de movilidad que deshabilita la llamada a través del trabajo:
    
        New-CsMobilityPolicy -Identity "site:Redmond" -EnableOutsideVoice $False

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-a-mobility-policy"></a>Para cambiar varios valores de propiedad al crear una directiva de movilidad

  - Puede incluir varios parámetros para modificar varios valores de propiedad. Por ejemplo, este comando crea una directiva que deshabilita la movilidad y la llamada a través del trabajo:
    
        New-CsMobilityPolicy "site:Redmond" -EnableMobility $False -EnableOutsideVoice $False

</div>

Para obtener más información, vea el tema de ayuda sobre los cmdlets [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy) y [set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy) .

</div>

<div>

## <a name="see-also"></a>Vea también


[Configuración de la directiva de movilidad en Lync Server 2013](lync-server-2013-configuring-mobility-policy.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

