---
title: Configuración de números de teléfono sin asignar
TOCTitle: Configuración de números de teléfono sin asignar
ms:assetid: a0650659-dce7-455f-8977-02454bbfa400
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg182559(v=OCS.15)
ms:contentKeyID: 48276162
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuración de números de teléfono sin asignar

 

_**Última modificación del tema:** 2012-11-01_

Lync Server le permite especificar cómo se van a tratar las llamadas entrantes a los números de teléfono válidos para su organización pero que no están asignados a un usuario o teléfono. Para definir cómo se tratan dichas llamadas, deberá configurar una tabla de números no asignados. Puede usar la tabla para enrutar las llamadas a una Aplicación de anuncio o a un servidor de Mensajería unificada de Exchange.

La forma en que configure la tabla de números sin asignar depende de cómo desee usarla. Puede configurar la tabla con todas las extensiones válidas para la organización, con únicamente extensiones sin asignar o bien, con una combinación de ambos tipos de números. La tabla de números sin asignar puede incluir tanto números asignados como sin asignar, pero solamente se invoca cuando un autor de llamadas marca un número que no está asignado en esos momentos. Si incluye todas las extensiones válidas en la tabla de números sin asignar, puede especificar la acción que va a tener lugar siempre que alguien abandone la organización, sin necesidad de volver a configurar la tabla. Si incluye extensiones sin asignar en la tabla, puede personalizar la acción que va a tener lugar respecto a números específicos. Por ejemplo, si cambia la extensión del departamento de soporte interno, puede incluir el número antiguo de este departamento en la tabla y asignarlo a un anuncio que comunique el número nuevo.

> [!IMPORTANT]  
> Antes de configurar la tabla de números sin asignar, debe haber definido uno o más anuncios o haber establecido un operador automático de Mensajería unificada de Exchange. Para obtener información detallada sobre cómo crear anuncios, consulte <a href="lync-server-2013-create-an-announcement.md">Crear un anuncio en Lync Server 2013</a>. Para ver si ha establecido la configuración de Mensajería unificada de Exchange, ejecute el cmdlet <strong>Get-CsExUmContact</strong>. Para obtener información detallada, consulte <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsExUmContact">Get-CsExUmContact</a>.



## En esta sección

  - [Crear o modificar un intervalo numérico sin asignar en Lync Server 2013](lync-server-2013-create-or-modify-an-unassigned-number-range.md)

  - [Eliminar un intervalo numérico sin asignar en Lync Server 2013](lync-server-2013-delete-an-unassigned-number-range.md)

