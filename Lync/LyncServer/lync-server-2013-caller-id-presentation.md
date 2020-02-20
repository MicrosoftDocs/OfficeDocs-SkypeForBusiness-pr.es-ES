---
title: 'Lync Server 2013: presentación del identificador de llamada'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Caller ID presentation
ms:assetid: 6a643961-a0a1-41d1-96ba-6c428a89d82e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204980(v=OCS.15)
ms:contentKeyID: 48184425
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 880adaa1a01a79e5d28ed79e756847fe0518d3a9
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151320"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="caller-id-presentation-in-lync-server-2013"></a>Presentación del identificador de llamada en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-22_

Con Lync Server 2010, el número de teléfono de la persona que ha llamado (es decir, el número de teléfono llamado) se puede traducir del formato E. 164 al formato de marcado local necesario para el tronco del mismo nivel (es decir, la puerta de enlace asociada, la central de conmutación (PBX) o el tronco SIP). Para ello, defina una o varias reglas de traslación para traducir la URI de la solicitud antes de redirigirla al tronco de mismo nivel.

Lync Server 2013 presenta la opción de traducir el número de teléfono de la persona que llama (es decir, el número de teléfono al que llama el autor de la llamada) desde el formato E. 164 al formato de marcado local necesario para el tronco del mismo nivel. Por ejemplo, puede escribir una regla de conversión para quitar el prefijo +34 del principio de una cadena de llamada y sustituirlo por 0134.

<div id="sectionSection0" class="section">

**Para configurar el identificador de llamada mediante el panel de control de Lync Server**

1.  Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro de la función CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para obtener más información, consulte [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Enrutamiento de voz** y, después, en **Configuración de tronco**.

4.  En la página **Configuración de tronco**, haga doble clic en el tronco existente (por ejemplo, **Global**) para abrir el cuadro de diálogo **Editar configuración de tronco**.

5.  Para configurar la presentación del identificador de llamada:
    
      - Para elegir una o más reglas en una lista de reglas de conversión disponible en la implementación de Telefonía IP empresarial, haga clic en **Seleccionar**. En **Reglas de conversión del número que llama**, haga clic en las reglas que quiera asociar al tronco y, después, haga clic en **Aceptar**.
    
      - Para definir una regla de conversión nueva y asociarla al tronco, haga clic en **Nueva**. Para obtener más información sobre cómo definir una regla nueva, consulte [Defining Translation Rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) en la documentación sobre implementación.
    
      - Para editar una regla de conversión que ya esté asociada al tronco, haga clic en el nombre de la regla y, a continuación, en **Mostrar detalles**. Para obtener más información, consulte [Defining Translation Rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md) en la documentación sobre implementación.
    
      - Para copiar una regla de conversión existente con el fin de utilizarla como punto de partida en la definición de una regla nueva, haga clic en el nombre de la regla, en **Copiar**y, a continuación, en **Pegar**. Para obtener más información, consulte [Defining Translation Rules in Lync Server 2013](lync-server-2013-defining-translation-rules.md).
    
      - Para quitar una regla de conversión de un tronco, resalte el nombre de la regla y en **Quitar**.
    
    <div>
    

    > [!WARNING]  
    > No asocie reglas de conversión a un tronco si ha configurado reglas de conversión en la entidad del mismo nivel que el tronco asociado, porque es posible que ambas reglas puedan entrar en conflicto.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

