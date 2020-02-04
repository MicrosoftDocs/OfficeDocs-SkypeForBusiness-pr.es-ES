---
title: 'Lync Server 2013: validar la configuración de Office Web Apps Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating the configuration of Office Web Apps Server
ms:assetid: f6e8ecbf-305d-4a13-92d0-b61dbd82b0ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205393(v=OCS.15)
ms:contentKeyID: 48185859
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 541929233eff5e401b3998aa84e463e2640378c0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763574"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validating-the-configuration-of-office-web-apps-server-in-lync-server-2013"></a>Validar la configuración de Office Web Apps Server en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-04-22_

Después de agregar Office Web Apps Server a la topología y después de que se haya publicado la topología, debe ver dos nuevos eventos de registro de eventos en el registro de eventos de Lync Server. En primer lugar, se debe agregar un evento LS Data MCU (identificador de evento 41034). Este evento notificará que se ha descubierto el servidor de Office Web Apps:

**Se ha detectado el servidor de conferencia web Office Web Apps Server, se ha habilitado el contenido de PowerPoint.**

Además, debe ver otro evento LS Data MCU (Id. de evento 41032) que informa sobre las direcciones URL de Office Web Apps Server. Por ejemplo:

**Se ha detectado correctamente el servidor de conferencia web de Office Web Apps Server.**

**Página del moderador interno de Office Web Apps Server:https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed=**

**Página de asistente interno de Office Web Apps Server:https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&=**

**Página de moderador externo de Office Web Apps Server:https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed**

**Página de asistente interno de Office Web Apps Server:https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&**

Si ve un evento LS Data MCU con el identificador de evento de 41033, significa que se ha producido un error en la detección de Office Web Apps Server. En ese caso, Microsoft Lync Server 2013 probará tantas veces como sea necesario para descubrir el servidor de Office Web Apps recién configurado. Si el proceso de detección falla varias veces, debería quitar Office Web Apps Server del documento de topología, publicar la topología actualizada y, a continuación, intentar volver a agregar Office Web Apps Server a la topología después de haber resuelto los problemas de conectividad.

Si el servidor de Office Web Apps parece estar configurado correctamente y ha sido reconocido por el proceso de detección, puede comprobar que Office Web Apps Server funciona como se espera compartiendo una presentación de PowerPoint entre un par de clientes de Microsoft Lync 2013. Si el usuario A puede cargar y mostrar la presentación de PowerPoint y si el usuario B se puede unir a la reunión y ver la presentación, Office Web Apps Server está funcionando.

Incluso si Office Web Apps Server parece estar configurado correctamente, es posible que reciba el mensaje de error "algunas características de uso compartido no están disponibles debido a problemas de Conectividad del servidor" al intentar compartir una presentación de PowerPoint. Si recibe este mensaje de error, debe reiniciar el servidor front-end (o servidores) asociado con el nuevo servidor de Office Web Apps.

</div>

<span> </span>

</div>

</div>

</div>

