---
title: 'Lync Server 2013: exportar casos de prueba de enrutamiento de voz'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Export voice routing test cases
ms:assetid: 489ac472-1a35-4755-b390-48f7cdf31e94
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425957(v=OCS.15)
ms:contentKeyID: 48184050
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fcca6e09be8c3a5607e7888a35c14f125f3475fc
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137329"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="export-voice-routing-test-cases-in-lync-server-2013"></a>Exportar casos de prueba de enrutamiento de voz en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

Los casos de prueba proporcionan una forma de probar rutas de voz en su organización: puede definir aspectos como el número que se va a marcar y el plan de marcado y la Directiva de voz que se van a usar, y Lync Server puede comprobar que, dadas las condiciones, el número proporcionado puede se enrutó correctamente a la red RTC.

Los casos de prueba, que se pueden crear mediante el panel de control de Lync Server, normalmente solo se guardan en el servidor donde se creó y ejecutó originalmente el caso. Sin embargo, estos casos de prueba pueden exportarse como archivos XML (con la extensión .vtest) y luego importarse en otros servidores. Esto le permite ejecutar las mismas pruebas en diferentes equipos ubicados en diferentes puntos de la topología.

<div>

## <a name="to-export-a-voice-routing-test-case"></a>Para exportar un caso de prueba de enrutamiento de voz

1.  En el panel de control de Lync Server, haga clic en **enrutamiento de voz** y en **probar enrutamiento de voz**.

2.  En la pestaña **Probar enrutamiento de voz**, Seleccione el caso de prueba (o los casos de prueba) que va a exportar. Para seleccionar varios casos de prueba, haga clic en el primer caso que se va a exportar, luego mantenga presionada la tecla Ctrl y seleccione los casos adicionales.

3.  Haga clic en **Acciones** y luego en **Exportar casos de prueba**.

4.  En el cuadro de diálogo **Guardar como**, seleccione una carpeta para almacenar los casos de prueba exportados y escriba un nombre para el archivo XML resultante en el cuadro **Nombre de archivo**. Tenga en cuenta que si va a exportar varios casos de prueba, todos ellos se guardarán en un fichero XML.

5.  Para guardar los casos de prueba, haga clic en **Guardar**.

</div>

<div>

## <a name="see-also"></a>Vea también


[Importar casos de prueba de enrutamiento de voz en Lync Server 2013](lync-server-2013-import-voice-routing-test-cases.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

