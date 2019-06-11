---
title: 'Lync Server 2013: Exportar casos de prueba de enrutamiento de voz'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Export voice routing test cases
ms:assetid: 489ac472-1a35-4755-b390-48f7cdf31e94
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425957(v=OCS.15)
ms:contentKeyID: 48184050
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d6e47158d9ea3da6f04a1424026c7edb73c1d482
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835184"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="export-voice-routing-test-cases-in-lync-server-2013"></a>Exportar casos de prueba de enrutamiento de voz en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-11-01_

Los casos de prueba proporcionan una manera de probar las rutas de voz de su organización: puede definir elementos como el número que se marcará y el plan de marcado y la Directiva de voz que se utilizará, y Lync Server puede comprobar que, dadas las condiciones, el número suministrado puede se enrutó correctamente a la red PSTN.

Los casos de prueba, que se pueden crear con el panel de control de Lync Server, normalmente solo se guardan en el servidor en el que se creó y ejecutó originalmente el caso. Sin embargo, estos casos de prueba se pueden exportar como archivos XML (con la extensión. vtest) y, a continuación, importarse en otros servidores. Esto le permite ejecutar las mismas pruebas en diferentes equipos que se encuentran en diferentes puntos de su topología.

<div>

## <a name="to-export-a-voice-routing-test-case"></a>Para exportar un caso de prueba de enrutamiento de voz

1.  En el panel de control de Lync Server, haga clic en **enrutamiento de voz** y en **probar enrutamiento de voz**.

2.  En la pestaña **probar el enrutamiento de voz** , seleccione el caso de prueba (o casos de prueba) que se va a exportar. Para seleccionar varios casos de prueba, haga clic en el primer caso que se va a exportar y, a continuación, mantenga presionada la tecla Ctrl y seleccione los casos adicionales que se van a exportar.

3.  Haga clic en **acción**y, a continuación, en **exportar casos de prueba**.

4.  En el cuadro de diálogo **Guardar como** , seleccione una carpeta para almacenar los casos de prueba exportados y escriba un nombre para el archivo XML resultante en el cuadro **nombre de archivo** . Tenga en cuenta que si va a exportar varias pruebas, todos estos casos de prueba se guardarán en un único archivo XML.

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

