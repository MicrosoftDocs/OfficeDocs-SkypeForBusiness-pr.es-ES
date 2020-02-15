---
title: 'Lync Server 2013: importación de casos de prueba de enrutamiento de voz'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Import voice routing test cases
ms:assetid: 6546e24c-9ad2-428b-92b2-63948ed0f884
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398460(v=OCS.15)
ms:contentKeyID: 48184325
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 742bb5d8e8f29edf0397c9bb9fa12592087ea517
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038722"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="import-voice-routing-test-cases-in-lync-server-2013"></a>Importar casos de prueba de enrutamiento de voz en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-21_

Los casos de prueba proporcionan una forma de probar las rutas de voz en su organización: puede definir aspectos como el número que se va a marcar y el plan de marcado y la Directiva de voz que se van a usar, y Lync Server 2013 puede comprobar que, según esas condiciones, el número proporcionado puede Succes sfully se enrutará a la red RTC.

Los casos de prueba, que se pueden crear mediante el panel de control de Lync Server, normalmente solo se guardan en el servidor donde se creó y ejecutó originalmente el caso. Sin embargo, estos casos de prueba pueden exportarse como archivos XML (con la extensión .vtest) y luego importarse en otros servidores. Esto le permite ejecutar las mismas pruebas en diferentes equipos ubicados en diferentes puntos de la topología.

<div>

## <a name="to-import-a-voice-routing-test-case"></a>Para importar un caso de prueba de enrutamiento de voz

1.  Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro de la función CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para obtener más información, consulte [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Enrutamiento de voz**.

4.  En el menú **acciones** , haga clic en **importar casos de prueba**.

5.  Busque el archivo de caso de prueba (. vtest) que desea importar y, a continuación, haga clic en **abrir**.

6.  Haga clic en **Confirmar** y, a continuación, en **Confirmar todo**.
    
    <div>
    

    > [!NOTE]  
    > Cuando importe un archivo. vtest, debe ejecutar el comando <STRONG>confirmar todo</STRONG> para publicar el caso de prueba. Para obtener más información, consulte <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish Pending changes to the Voice Routing Configuration en Lync Server 2013</A> en la documentación de operaciones.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Vea también


[Exportar casos de prueba de enrutamiento de voz en Lync Server 2013](lync-server-2013-export-voice-routing-test-cases.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

