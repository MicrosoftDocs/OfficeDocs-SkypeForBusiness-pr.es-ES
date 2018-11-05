---
title: 'Lync Server 2013: Información general de la aplicación de anuncio'
TOCTitle: Información general de la aplicación de anuncio
ms:assetid: 2abee804-2599-48bb-90b2-15df0bae5e20
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204757(v=OCS.15)
ms:contentKeyID: 48274757
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Información general de la aplicación de anuncio en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-13_

Cuando implemente la Aplicación de anuncio, deberá configurar una tabla de números no asignados que determine qué acción tomar cuando alguien marca un número no asignado. La tabla de números no asignados contiene intervalos de números de teléfono que son válidos para la organización y especifica qué Aplicación de anuncio administra cada intervalo. Cuando el autor de una llamada marque un número de teléfono que sea válido para la organización pero que no esté asignado a nadie, Lync Server buscará el número en la tabla de enrutamiento de números no asignados, identificará en qué intervalo se incluye al número y enrutará la llamada a la Aplicación de anuncio que se haya especificado para ese intervalo. La Aplicación de anuncio responde la llamada y reproduce un mensaje de audio (si se ha configurado así) y, a continuación, desconecta la llamada o la transfiere a un destino predeterminado, como, por ejemplo, un operador. Puede usar cmdlets del Shell de administración de Lync Server para configurar varios mensajes de audio o para transferir destinos.

La forma en que configure la tabla de números sin asignar depende de cómo desee usarla. Si dispone de números específicos que ya no están en uso y desea reproducir mensajes personalizados para cada uno de los números, puede introducir esos números específicos en la tabla de números no asignados. Por ejemplo, si ha cambiado el número del departamento de soporte interno, puede introducir el número antiguo de este departamento y asignarlo a un anuncio que comunique el número nuevo. Si desea reproducir un mensaje general para todas las personas que llamen a un número no asignado como, por ejemplo, a empleados que ya no pertenecen a la organización, puede introducir intervalos para todas las extensiones válidas de la organización. Se invoca a la tabla de números no asignados siempre que el autor de la llamada marque un número que no esté asignado actualmente.

En Lync Server 2013, la Aplicación de anuncio se instala automáticamente con el Aplicación de grupo de respuesta. Las aplicaciones de Anuncio y Grupo de respuesta son componentes estándar de una implementación de Telefonía IP empresarial: al implementar Telefonía IP empresarial, se implementan ambas aplicaciones automáticamente.

