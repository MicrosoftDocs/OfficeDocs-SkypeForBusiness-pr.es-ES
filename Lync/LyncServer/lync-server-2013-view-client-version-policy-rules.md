---
title: 'Lync Server 2013: ver reglas de directiva de versión de cliente'
description: 'Lync Server 2013: ver reglas de directiva de versión de cliente.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View client version policy rules
ms:assetid: f3a0215f-f72f-4e9b-a07b-25858dc4203a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ923060(v=OCS.15)
ms:contentKeyID: 50675350
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e04075f136d53fe149c6b0655699324a99e0a52
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572486"
---
# <a name="view-client-version-policy-rules-in-lync-server-2013"></a>Ver reglas de directiva de versión de cliente en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-23_

Una directiva de versión de cliente se compone de un conjunto de reglas de directiva de versión de cliente. Estas reglas definen las acciones que se deben realizar cuando los usuarios intentan iniciar sesión con clientes y versiones de clientes específicos. Puede ver las reglas de directiva de versión de cliente desde el panel de control de Lync Server 2013 o el shell de administración de Lync Server 2013.

<div>

## <a name="to-view-client-version-policy-rules-by-using-lync-server-control-panel"></a>Para ver las reglas de directiva de versión de cliente mediante el panel de control de Lync Server

1.  Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **clientes**y, a continuación, haga clic en el botón de navegación **Directiva de versión de cliente** .

4.  En la página **Directiva de versión de cliente** , haga doble clic en la Directiva de versión de cliente que desea ver.

5.  Las reglas aparecen en la página **Editar Directiva de versión de cliente** . Para ver los detalles de una regla, seleccione la regla y, a continuación, haga clic en **Mostrar detalles**.

</div>

<div>

## <a name="viewing-client-version-policy-rules-by-using-windows-powershell-cmdlets"></a>Visualización de reglas de directiva de versión de cliente mediante cmdlets de Windows PowerShell

Puede ver las reglas de directiva de versión de cliente mediante el shell de administración de Lync Server y el cmdlet **Get-CsClientVersionPolicyRule** . Este cmdlet se puede ejecutar desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server 2010 mediante PowerShell remoto" en [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-view-client-version-policy-rules"></a>Para ver las reglas de directiva de versión de cliente

  - Para ver las reglas de directiva de versión de cliente, escriba el siguiente comando en el shell de administración de Lync Server y, a continuación, presione ENTRAR:
    
        Get-CsClientVersionPolicyRule
    
    Se devolverá información similar a la siguiente para cada regla configurada:
    
        Identity          : Global/2336c611-a243-4c5d-994b-eea8a524d0e4
        Priority          : 0
        RuleId            : 2336c611-a243-4c5d-994b-eea8a524d0e4
        Description       :
        Action            : Block
        ActionUrl         :
        MajorVersion      : 1
        MinorVersion      : 3
        BuildNumber       :
        QfeNumber         :
        UserAgent         : RTC
        UserAgentFullName :
        Enabled           : True
        CompareOp         : LEQ

</div>

Para obtener más información, consulte el tema de ayuda del cmdlet [Get-CsClientVersionPolicyRule](https://docs.microsoft.com/powershell/module/skype/Get-CsClientVersionPolicyRule) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

