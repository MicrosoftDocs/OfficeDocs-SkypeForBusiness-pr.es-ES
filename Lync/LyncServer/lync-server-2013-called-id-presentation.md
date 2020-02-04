---
title: 'Lync Server 2013: presentación del identificador denominado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Called ID presentation
ms:assetid: cf6c6af5-3418-411e-a50b-7a9cf8e100d4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721892(v=OCS.15)
ms:contentKeyID: 49733826
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8dc22438a688239618fc7a73cf3aa30ec614568d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742950"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="called-id-presentation-in-lync-server-2013"></a>Llamada presentación de identificación en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-21_

Con Lync Server 2010, el número de teléfono de la persona que se llama (es decir, el número de teléfono llamado) se puede traducir desde el formato E. 164 al formato de marcado local requerido por el interlocutor troncal (es decir, la puerta de enlace asociada, la central de conmutación (PBX) o el tronco del SIP). Para ello, defina una o varias reglas de traslación para traducir la URI de la solicitud antes de redirigirla al tronco de mismo nivel.

<div>


> [!IMPORTANT]  
> La capacidad de asociar una o más reglas de traducción con una configuración de telefonía IP empresarial está pensada para su uso como <EM>alternativa</EM> a la configuración de reglas de traducción en el punto de conexión del mismo nivel. No asociar reglas de traducción con una configuración de telefonía IP empresarial si ha configurado reglas de traducción en el punto de conexión del mismo nivel porque las dos reglas podrían entrar en conflicto.



</div>

Puede usar cualquiera de los siguientes métodos para crear o modificar una regla de traducción:

  - Use la herramienta **generar una regla de traducción** para especificar valores para los dígitos de inicio, la longitud, los dígitos que se van a quitar y los dígitos que se van a agregar y, a continuación, permita que el panel de control de Lync Server genere el patrón correspondiente y la regla de traducción correspondiente.

  - Escriba de forma manual expresiones regulares para definir el patrón de coincidencia y la regla de traducción.

<div>


> [!NOTE]  
> Para obtener información sobre cómo escribir expresiones regulares, vea "expresiones regulares de .NET Framework" <A href="http://go.microsoft.com/fwlink/p/?linkid=140927">http://go.microsoft.com/fwlink/p/?linkId=140927</A>en.



</div>

<div>

## <a name="in-this-section"></a>En esta sección

  - [Crear o modificar una regla de traducción con la herramienta generar una regla de traducción de Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)

  - [Crear o modificar una regla de traducción de forma manual en Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-manually.md)

</div>

<div>

## <a name="see-also"></a>Vea también


[Presentación de la identificación de llamadas en Lync Server 2013](lync-server-2013-caller-id-presentation.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

