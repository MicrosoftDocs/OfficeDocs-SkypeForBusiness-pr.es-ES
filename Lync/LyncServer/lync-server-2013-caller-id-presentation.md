---
title: 'Lync Server 2013: presentación de identificación de llamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Caller ID presentation
ms:assetid: 6a643961-a0a1-41d1-96ba-6c428a89d82e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204980(v=OCS.15)
ms:contentKeyID: 48184425
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 016913ad68865f7d93512cc7383f2cfb47497ebe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842694"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="caller-id-presentation-in-lync-server-2013"></a>Presentación de la identificación de llamadas en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-22_

Con Lync Server 2010, el número de teléfono de la persona que se llama (es decir, el número de teléfono llamado) se puede traducir desde el formato E. 164 al formato de marcado local requerido por el interlocutor troncal (es decir, la puerta de enlace asociada, la central de conmutación (PBX) o el tronco del SIP). Para ello, defina una o varias reglas de traslación para traducir la URI de la solicitud antes de redirigirla al tronco de mismo nivel.

Lync Server 2013 introduce la opción de traducir el número de teléfono de la persona que llama (es decir, el número de teléfono desde el que llama el autor de la llamada) desde E. 164 formato al formato de marcado local requerido por el interlocutor troncal. Por ejemplo, puede escribir una regla de conversión para quitar el prefijo +34 del principio de una cadena de llamada y sustituirlo por 0134.

<div id="sectionSection0" class="section">

**Para configurar la identificación de llamadas mediante el panel de control de Lync Server**

1.  Inicie sesión en el equipo como miembro del grupo RTCUniversalServerAdmins o como miembro del rol CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Para obtener más información, consulte [permisos de configuración de delegación en Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Enrutamiento de voz** y, a continuación, en **Configuración del tronco**.

4.  En la página **Configuración de tronco**, haga doble clic en el tronco existente (por ejemplo, **Global**) para abrir el cuadro de diálogo **Editar configuración de tronco**.

5.  Para configurar la presentación del identificador de llamada:
    
      - Para elegir una o más reglas de una lista de todas las reglas de traducción disponibles en la implementación de telefonía IP empresarial, haga clic en **seleccionar**. En **Reglas de traducción de números de llamada**, haga clic en las reglas que quiera asociar al tronco y, después, haga clic en **Aceptar**.
    
      - Para definir una regla de conversión nueva y asociarla con el tronco, haga clic en **Nueva**. Para obtener más información sobre cómo definir una nueva regla, vea [definir reglas de traducción en Lync Server 2013](lync-server-2013-defining-translation-rules.md) en la documentación de implementación.
    
      - Para editar una regla de conversión que ya esté asociada al tronco, haga clic en el nombre de la regla y, a continuación, haga clic en  **Mostrar detalles**. Para obtener información detallada, consulte [definición de reglas de traducción en Lync Server 2013](lync-server-2013-defining-translation-rules.md) en la documentación de implementación.
    
      - Para copiar una regla de conversión existente con el fin de usarla como punto de partida en la definición de una regla nueva, haga clic en el nombre de la regla, en **Copiar** y, a continuación, en  **Pegar**. Para obtener más información, consulte [definición de reglas de traducción en Lync Server 2013](lync-server-2013-defining-translation-rules.md).
    
      - Para quitar una regla de conversión del plan de marcado, resalte el nombre de la regla y haga clic en **Eliminar**.
    
    <div>
    

    > [!WARNING]  
    > No asocie reglas de conversión a un tronco si ha configurado reglas de conversión en la entidad del mismo nivel que el tronco asociado, ya que es posible que ambas reglas puedan entrar en conflicto.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

