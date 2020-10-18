---
title: 'Lync Server 2013: configurar las opciones de la cuenta de usuario'
description: 'Lync Server 2013: configurar las opciones de la cuenta de usuario.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure user account settings
ms:assetid: b7c74ecc-b924-4efc-8a56-3a5f94a9ef13
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412896(v=OCS.15)
ms:contentKeyID: 48185200
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e6ab4c57ba3d3e8c084314e1093736334312d0c1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577516"
---
# <a name="configure-user-account-settings-in-lync-server-2013"></a>Configurar las opciones de cuenta de usuario en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-05_

Los usuarios de acceso telefónico escriben su número de teléfono o extensión y un PIN para participar en conferencias como usuarios autenticados. El URI de **línea** de telefonía especificado en las cuentas de usuario de Lync Server es necesario para la autenticación.

En el procedimiento de este tema se explica cómo asignar un **URI de línea** para una sola cuenta de usuario. Si desea asignar un **URI de línea** para varias cuentas de usuario, puede crear un script que use el cmdlet **Set-CsUser**. Para obtener información detallada sobre cómo usar un script de ejemplo para asignar un **URI de línea** a varias cuentas de usuario, consulte "asignar URI de línea a varios usuarios" en [https://go.microsoft.com/fwlink/p/?linkId=196945](https://go.microsoft.com/fwlink/p/?linkid=196945) .

<div>

## <a name="to-configure-user-account-settings"></a>Para configurar las opciones de cuenta de usuario

1.  Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins, o bien como miembro del rol **Cs-ServerAdministrator** o **CsAdministrator**.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Usuarios**.

4.  En el campo de búsqueda, escriba el nombre del usuario que desea configurar para las conferencias de acceso telefónico local o haga clic en **Agregar filtro** para especificar campos de búsqueda y, a continuación, haga clic en **Buscar**.

5.  Haga doble clic en el nombre de usuario para abrir el cuadro de diálogo **Editar usuario de Lync Server** .

6.  En **Telefonía**, en el campo **URI de línea**, escriba un número de teléfono único y normalizado (por ejemplo, tel:+14255550200).
    
    <div>
    

    > [!NOTE]  
    > Puede especificar el <STRONG>URI de línea</STRONG> solo si la <STRONG>telefonía</STRONG> está establecida en <STRONG>solo de PC a PC</STRONG>, telefonía <STRONG>IP empresarial</STRONG>, <STRONG>control remoto de llamadas</STRONG> o <STRONG>control remoto de llamadas</STRONG>.

    
    </div>

7.  Haga clic en **Confirmar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

