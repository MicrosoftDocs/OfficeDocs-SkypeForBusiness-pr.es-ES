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
ms.openlocfilehash: 34c774411fd825dd01595ef1e51ffa9c65c6eb8f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007399"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validating-the-configuration-of-office-web-apps-server-in-lync-server-2013"></a>Validación de la configuración de Office Web Apps Server en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-04-22_

Después de que se haya agregado Office Web Apps Server a la topología y después de que se haya publicado la topología, verá dos nuevos eventos de registro de eventos en el registro de eventos de Lync Server. En primer lugar, se debe agregar un evento LS Data MCU (identificador de evento 41034); Este evento informará de que se ha descubierto el servidor de Office Web Apps:

**Se ha descubierto el servidor de conferencia Web de Office Web Apps Server, se ha habilitado el contenido de PowerPoint.**

Además, debe ver otro evento LS Data MCU (Id. de evento 41032) que informa sobre las direcciones URL de Office Web Apps Server. Por ejemplo:

**Servidor de conferencia web la detección del servidor de Office Web Apps se ha realizado correctamente.**

**Página de moderadores internos de Office Web Apps Server:https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed=**

**Página de asistentes internos de Office Web Apps Server:https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&=**

**Página de moderadores externos de Office Web Apps Server:https://atl-officewebapps-001.litwareinc.com/m/Presenter.aspx?a=0\&embed**

**Página de asistentes internos de Office Web Apps Server:https://atl-officewebapps-001.litwareinc.com/m/ParticipantFrame.aspx?a=0\&embed=true&**

Si ve un evento LS Data MCU con el Id. de evento 41033, indicará un error en la detección de Office Web Apps Server. En ese caso, Microsoft Lync Server 2013 probará tantas veces como sea necesario para descubrir el servidor de Office Web Apps recién configurado. Si el proceso de detección falla repetidas veces, deberá quitar Office Web Apps Server del documento de la topología, publicar la topología actualizada y, a continuación, cuando los problemas de conectividad estén resueltos, agregar de nuevo Office Web Apps Server a la topología.

Si Office Web Apps Server parece estar configurado correctamente y el proceso de detección lo ha reconocido, puede comprobar que Office Web Apps Server funciona como se esperaba compartiendo una presentación de PowerPoint entre un par de clientes de Microsoft Lync 2013. Si el usuario A puede cargar y visualizar la presentación de PowerPoint y el usuario B puede unirse a la reunión y ver esa presentación, significa que Office Web Apps Server funciona.

Aún cuando parezca que Office Web Apps Server está correctamente configurado, podría recibir el mensaje de error "Algunas características de uso compartido no están disponibles debido a problemas de conectividad del servidor” cuando intente compartir una presentación de PowerPoint.Si recibe ese mensaje de error, reinicie el servidor (o servidores) front-end asociado al nuevo servidor Office Web Apps Server.

</div>

<span> </span>

</div>

</div>

</div>

