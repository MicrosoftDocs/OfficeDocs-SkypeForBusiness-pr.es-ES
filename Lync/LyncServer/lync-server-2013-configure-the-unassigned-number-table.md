---
title: 'Lync Server 2013: Configurar la tabla de números sin asignar'
TOCTitle: Configurar la tabla de números sin asignar
ms:assetid: eaa01986-e92f-4328-acf6-4e46c4306a04
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg399053(v=OCS.15)
ms:contentKeyID: 48277056
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar la tabla de números sin asignar en Lync Server 2013

 

_**Última modificación del tema:** 2012-10-30_

En Lync Server 2013, puede especificar cómo se van a tratar las llamadas entrantes a los números de teléfono válidos para la organización pero que no están asignados a un usuario o teléfono. El autor de la llamada puede oír un mensaje o ser enrutado a otro destino, o bien ambas opciones.

La forma en que configure la tabla de números sin asignar depende de cómo desee usarla. Puede configurar la tabla con todas las extensiones válidas para la organización, con únicamente extensiones sin asignar o bien con una combinación de ambos tipos de números. La tabla de números sin asignar puede incluir tanto números asignados como sin asignar, pero solamente se invoca cuando un autor de llamadas marca un número que no está asignado en esos momentos. Si incluye todas las extensiones válidas en la tabla de números sin asignar, puede especificar la acción que va a tener lugar siempre que alguien abandone la organización, sin necesidad de volver a configurar la tabla. Si incluye extensiones sin asignar en la tabla, puede personalizar la acción que va a tener lugar respecto a números específicos. Por ejemplo, si cambia la extensión del departamento de soporte interno, puede incluir el número antiguo de este departamento en la tabla y asignarlo a un anuncio que comunique el número nuevo.

> [!IMPORTANT]  
> Antes de configurar la tabla de números sin asignar, el sistema debe tener anuncios definidos o un operador automático de Mensajería unificada de Exchange (UM) configurado.



> [!TIP]  
> Cuando alguien llama a un número sin asignar, Lync Server busca en la tabla de números sin asignar de arriba a abajo y usa el primer intervalo coincidente. Por tanto, si quiere que una determinada acción se realice como último recurso, deberá especificarla para el último intervalo en la tabla.



## En esta sección

[Crear o modificar un intervalo numérico sin asignar en Lync Server 2013](lync-server-2013-create-or-modify-an-unassigned-number-range.md) [Crear un anuncio en Lync Server 2013](lync-server-2013-create-an-announcement.md)

