---
title: 'Lync Server 2013: usar la llamada con un teléfono habilitado para Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using Call Me At with a Lync-enabled phone
ms:assetid: 975a1df8-a159-4aa4-a991-5972a535998e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn383570(v=OCS.15)
ms:contentKeyID: 56470326
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cc89ac5038d367a57b791546c287e515bfd3c7bf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850207"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-call-me-at-with-a-lync-enabled-phone-and-lync-server-2013"></a>Usar llamarme en con un teléfono habilitado para Lync y Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-08-09_

La característica llamarme a en Lync permite a los usuarios unirse a la parte de audio de una conferencia con un teléfono móvil, "Land Line" u otro dispositivo conectado a la red de telefonía pública conmutada (RTC). Cuando intente unirse a una reunión mediante Lync, normalmente se le presentará el cuadro de diálogo **unirse al audio** de la reunión:

![Captura de pantalla de la ventana unirse al audio de la reunión de Lync] (images/Dn383570.e28f17f0-9f17-44ef-b893-f4ef132f47ac(OCS.15).png "Captura de pantalla de la ventana unirse al audio de la reunión de Lync")

Si selecciona **llamarme al**, puede seleccionar un número de teléfono de la lista desplegable. Lync Server 2013 colocará una llamada telefónica al número seleccionado y podrá usar ese teléfono para participar en la parte de audio de la Conferencia.

La lista desplegable se rellena con los números de teléfono (para teléfono móvil, teléfono de casa u otro teléfono) que ha introducido en la ficha **teléfonos** en el cuadro de diálogo **Lync: opciones** :

![Captura de pantalla de opciones de configuración de teléfonos de Lync] (images/Dn383570.03d2f25d-49e2-47b4-b1e9-b1614fc0c11c(OCS.15).png "Captura de pantalla de opciones de configuración de teléfonos de Lync")

Si no ha introducido ningún número de teléfono en la ficha **teléfonos** , no tendrá ningún número disponible en el cuadro de lista desplegable. Sin embargo, siempre puede hacer clic en **nuevo número** y hacer que Lync Server llame a cualquier número de teléfono que quiera:

Captura de pantalla de la ![ventana llamada de audio de reunión de Lync] Captura de pantalla de la (images/Dn383570.27f2ac7a-cc1c-465c-b145-202ad03af4f2(OCS.15).png "ventana llamada de audio de reunión de Lync")

La característica llamarme al funciona muy bien, siempre y cuando lo haya hecho de la manera prevista: haciendo que Lync Server llame a un número de teléfono RTC. Sin embargo, puede tener una experiencia menos adecuada si pide a Lync Server que le llame en un extremo habilitado para Lync (por ejemplo, un teléfono en una sala de conferencias). A continuación se indica el problema que puede llevar a cabo, así como dos maneras de solucionar el problema.

Para empezar, esto es lo que sucede al proporcionar la característica llamarme a con el número de teléfono de un teléfono con Lync habilitado. Supongamos que Ken Myer intenta unirse a una reunión haciendo que Lync Server le llame en 1-206-555-1219, un número de teléfono habilitado para Lync Server. Ken se conectará inicialmente a la reunión, pero después de unos segundos Lync mostrará que el mensaje **no se completó o finalizó**, y parecerá que Ken se ha eliminado de la reunión:

![Captura de pantalla de la ventana de conferencia de llamada de Lync] (images/Dn383570.c2a81727-8751-41b5-946a-03a1b75b9d95(OCS.15).png "Captura de pantalla de la ventana de conferencia de llamada de Lync")

Observe, sin embargo, que hay una discrepancia en la ventana de conversación de Lync. Ken Myer es el único nombre que aparece en el encabezado de los **participantes** . Sin embargo, si miras la barra de título de la ventana, verás que la Conferencia contiene un total de 4 participantes.

Del mismo modo, si busca en la ventana de conversación de cualquiera de los otros participantes de la Conferencia, no verá Ken Myer en la lista:

Captura de pantalla de la ![ventana Lista de participantes de Lync] Captura de pantalla de la (images/Dn383570.fa5990cf-2694-402c-ac06-946aa66b6837(OCS.15).png "ventana Lista de participantes de Lync")

Y, al mismo tiempo, Ken Myer podrá participar en la parte de audio de la llamada con su teléfono habilitado para Lync. La característica llamarme a ha funcionado realmente, pero la experiencia del usuario es inferior a la óptima.

Hay al menos dos maneras de solucionar este problema. Si ya se ha unido a una conferencia de esta forma (como Ken Myer ha sido), normalmente puede resolver el problema si participa en un modo diferente. Por ejemplo, si envías un mensaje instantáneo, la ventana de conversación ahora mostrará a todos los participantes de la Conferencia, incluidos los siguientes:

![Captura de pantalla de conversación y lista de participantes de Lync] (images/Dn383570.9b5ff6d6-9f73-467c-99a7-ef3aa8bd7e7a(OCS.15).png "Captura de pantalla de conversación y lista de participantes de Lync")

En este momento, podrás participar en la reunión de la manera esperada.

Como alternativa, puede evitar el problema por completo cambiando la forma en que se une a la reunión. Si necesita que Lync Server llame a un teléfono habilitado para Lync Server, debe empezar a unirse a la reunión sin una conexión de audio. Para ello, seleccione no unirse al audio al presentarse con el cuadro de diálogo unirse al audio de la reunión:

![Captura de pantalla de Lync no unirse a la ventana audio] de la reunión (images/Dn383570.280a148d-cce5-4b02-87f9-9f78f17a81c1(OCS.15).png "Captura de pantalla de Lync no unirse a la ventana audio") de la reunión

Una vez que se haya conectado correctamente a la reunión, ahora podrá "invitar" al teléfono habilitado para Lync Server a unirse también a la reunión. Para ello, coloque el mouse sobre el icono de personas y, a continuación, haga clic en invitar a **más personas**:

Captura de pantalla de invitar a ![más participantes en Lync] Captura de pantalla de invitar a (images/Dn383570.69b81b29-d1d2-4ed3-acb6-e37dd18e3d86(OCS.15).png "más participantes en Lync")

De esta forma, se abrirá el cuadro de diálogo **Enviar un mensaje instantáneo** . Omita el título del cuadro de diálogo (no está enviando un mensaje instantáneo) y escriba el número de teléfono del teléfono habilitado para Lync:

![Captura de pantalla del cuadro de diálogo Enviar un mensaje instantáneo] (images/Dn383570.cd67a3f0-06d8-41ba-a808-c067f64bec9f(OCS.15).png "Captura de pantalla del cuadro de diálogo Enviar un mensaje instantáneo")

Después de hacer clic en **Aceptar**, Lync Server llamará al número especificado en el cuadro de diálogo. Cuando se establece la conexión, tendrá capacidades de audio completas a través del teléfono habilitado para Lync y podrá ver la lista completa de la Conferencia e interactuar con ella.

</div>

<span> </span>

</div>

</div>

</div>

