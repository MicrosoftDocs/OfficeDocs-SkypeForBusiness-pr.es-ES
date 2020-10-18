---
title: 'Lync Server 2013: usar Call me en con un teléfono habilitado para Lync'
description: 'Lync Server 2013: usar Call me en con un teléfono habilitado para Lync.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Call Me At with a Lync-enabled phone
ms:assetid: 975a1df8-a159-4aa4-a991-5972a535998e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn383570(v=OCS.15)
ms:contentKeyID: 56470326
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7fd7855e45132b133c78230e7f8769bdab897140
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580426"
---
# <a name="using-call-me-at-with-a-lync-enabled-phone-and-lync-server-2013"></a>Usar la llamada me en con un teléfono habilitado para Lync y Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-08-09_

La característica llamarme a en Lync permite a los usuarios unirse a la parte de audio de una conferencia mediante un teléfono móvil, "Land Line" u otro dispositivo conectado a la red telefónica conmutada (RTC). Al intentar unirse a una reunión con Lync, normalmente se le presentará el cuadro de diálogo **unirse al audio** de la reunión:

![Pantalla de uso de Lync para unirse a la reunión de audio](images/Dn383570.e28f17f0-9f17-44ef-b893-f4ef132f47ac(OCS.15).png "Pantalla de uso de Lync para unirse a la reunión de audio")

Si selecciona **llamarme al**, puede elegir un número de teléfono en la lista desplegable. Lync Server 2013 realizará una llamada telefónica al número seleccionado y podrá usar ese teléfono para participar en la parte de audio de la Conferencia.

La lista desplegable se rellena con los números de teléfono (para teléfonos móviles, teléfonos domésticos u otros teléfonos) que escribió en la pestaña **teléfonos** del cuadro de diálogo **Lync – opciones** :

![Captura de pantalla de opciones de configuración de teléfonos de Lync](images/Dn383570.03d2f25d-49e2-47b4-b1e9-b1614fc0c11c(OCS.15).png "Captura de pantalla de opciones de configuración de teléfonos de Lync")

Si no ha especificado ningún número de teléfono en la pestaña **teléfonos** , no tendrá ningún número disponible en el cuadro desplegable. Sin embargo, siempre puede hacer clic en **nuevo número** y hacer que Lync Server llame a cualquier número de teléfono que quiera:

![Captura de pantalla de llamada de audio de reunión de Lync unirse](images/Dn383570.27f2ac7a-cc1c-465c-b145-202ad03af4f2(OCS.15).png "Captura de pantalla de llamada de audio de reunión de Lync unirse")

La característica llamarme cuando funciona muy bien, siempre que la use como estaba previsto: haciendo que Lync Server llame a un número de teléfono RTC. Sin embargo, puede tener una experiencia menor que-óptima si solicita a Lync Server que le llame en un punto de conexión habilitado para Lync (por ejemplo, un teléfono en una sala de conferencias). A continuación se indica el problema en el que se puede ejecutar, así como dos maneras de solucionar el problema.

Para empezar, esto es lo que sucede cuando se proporciona la característica llamarme al con el número de teléfono de un teléfono habilitado para Lync. Supongamos que Ken Myer intenta unirse a una reunión haciendo que Lync Server le llame al 1-206-555-1219, un número de teléfono habilitado para Lync Server. Ken se conectará inicialmente a la reunión, pero después de unos segundos Lync mostrará que la llamada al mensaje **no se completó o ha finalizado**, y parece que Ken se ha quitado de la reunión:

![Captura de pantalla de la ventana de conferencia de llamadas de Lync](images/Dn383570.c2a81727-8751-41b5-946a-03a1b75b9d95(OCS.15).png "Captura de pantalla de la ventana de conferencia de llamadas de Lync")

Sin embargo, tenga en cuenta que hay una discrepancia dentro de la ventana de conversación de Lync. Ken Myer es el único nombre que aparece en el encabezado de los **participantes** . Sin embargo, si mira en la barra de título de la ventana, verá que la Conferencia contiene un total de 4 participantes.

Del mismo modo, si mira en la ventana de conversación de cualquiera de los otros participantes de la Conferencia, no verá Ken Myer enumerado en cualquier lugar:

![Captura de pantalla de la ventana Lista de participantes de Lync](images/Dn383570.fa5990cf-2694-402c-ac06-946aa66b6837(OCS.15).png "Captura de pantalla de la ventana Lista de participantes de Lync")

Y, sin embargo, al mismo tiempo, Ken Myer podrá participar en la parte de audio de la llamada mediante su teléfono habilitado para Lync. La característica llamarme a en ha trabajado realmente, pero la experiencia del usuario es inferior a la óptima.

Hay al menos dos maneras de solucionar este problema. Si ya se ha unido a una conferencia de este modo (como Ken Myer funcionó), normalmente puede resolver el problema realizando una modalidad diferente. Por ejemplo, si envía un mensaje instantáneo, ahora la ventana conversación mostrará todos los participantes de la Conferencia, incluidos usted:

![Captura de pantalla de conversación y lista de participantes de Lync](images/Dn383570.9b5ff6d6-9f73-467c-99a7-ef3aa8bd7e7a(OCS.15).png "Captura de pantalla de conversación y lista de participantes de Lync")

En este momento, podrá participar en la reunión de la manera prevista.

Como alternativa, puede evitar todo este problema cambiando la forma de unirse a la reunión. Si necesita que Lync Server llame a un teléfono habilitado para Lync Server, debe empezar a unirse a la reunión sin una conexión de audio. Para ello, seleccione no unirse al audio cuando aparezca el cuadro de diálogo unirse al audio de la reunión:

![Pantalla de Lync no unirse a la ventana audio de la reunión](images/Dn383570.280a148d-cce5-4b02-87f9-9f78f17a81c1(OCS.15).png "Pantalla de Lync no unirse a la ventana audio de la reunión")

Una vez que se haya conectado correctamente a la reunión, ahora puede "invitar" al teléfono habilitado para Lync Server a unirse también a la reunión. Para ello, ponga el mouse sobre el icono contactos y, a continuación, haga clic en **invitar a más personas**:

![Captura de pantalla de la ventana invita más participantes en Lync](images/Dn383570.69b81b29-d1d2-4ed3-acb6-e37dd18e3d86(OCS.15).png "Captura de pantalla de la ventana invita más participantes en Lync")

Se abrirá el cuadro de diálogo **Enviar un mensaje instantáneo** . Ignore el título del cuadro de diálogo (en realidad, no está enviando un mensaje instantáneo) y escriba el número de teléfono del teléfono habilitado para Lync:

![Captura de pantalla del cuadro de diálogo enviar mi](images/Dn383570.cd67a3f0-06d8-41ba-a808-c067f64bec9f(OCS.15).png "Captura de pantalla del cuadro de diálogo enviar mi")

Después de hacer clic en **Aceptar**, Lync Server llamará al número escrito en el cuadro de diálogo. Una vez realizada la conexión, dispondrá de capacidades de audio completas a través del teléfono habilitado para Lync y podrá ver e interactuar con la lista de conferencias completa.

</div>

<span> </span>

</div>

</div>

</div>

