---
title: "Configuración de clientes de Lync Server 2013 para su uso con Office Web Apps Server"
TOCTitle: Configuración de clientes para su uso con Office Web Apps Server
ms:assetid: e5eaead7-0b32-42fb-97eb-ca203af59a9d
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205339(v=OCS.15)
ms:contentKeyID: 48276983
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuración de clientes de Lync Server 2013 para su uso con Office Web Apps Server

 

_**Última modificación del tema:** 2013-02-25_

Si quiere que los usuarios experimenten todas las capacidades de Office Web App Server, actualícelos a Microsoft Lync 2013. Solo los usuarios de Lync 2013 podrán hacer tareas como desplazarse por diapositivas de PowerPoint independientemente de la presentación real de PowerPoint. (Es decir, estos usuarios podrán mirar cualquier diapositiva de la presentación en cualquier momento, sin interferir de ningún modo en la presentación real.) Los usuarios que no usen Lync 2013 seguirán pudiendo unirse a conferencias en línea y ver la presentación de PowerPoint. No obstante, no podrán desplazarse independientemente por las diapositivas, ni podrán ver las transiciones entre diapositivas, ni ver los vídeos incrustados..

Estas capacidades estarán siempre disponibles para los usuarios de Lync 2013. Y esto es cierto aunque el moderador de PowerPoint ejecute Microsoft Lync 2010. Si una presentación de PowerPoint está hospedada por un usuario que ejecuta Lync 2010, Lync Server 2013 se coordinará con Office Web Apps Server para garantizar que los usuarios de Lync 2013 vean la versión Office Web Apps Server de la presentación. Office Web Apps Server no proporciona servicios de PowerPoint a los usuarios que ejecuten clientes que no sean Lync 2013. En su lugar, estos usuarios se conectan al servicio del servidor de conferencia y ven las presentaciones de PowerPoint igual que lo hacían en Microsoft Lync Server 2010. Esto también significa que estos usuarios solo tendrán acceso a las capacidades más limitadas ofrecidas por Lync Server 2010.

Aunque no se necesita ninguna configuración cliente para Office Web Apps Server (salvo actualizar los usuarios a Lync 2013), recomendamos que los asistentes a la conferencia se actualicen a Internet Explorer 9. Aunque se puede obtener acceso a las conferencias con Internet Explorer 8, existen algunas limitaciones al uso del explorador web. Por ejemplo, los usuarios de Internet Explorer 8 no podrán cambiar el tamaño de la región de PowerPoint por un tamaño personalizado. En su lugar, tendrán que limitarse a usar uno de los tamaños de región predefinidos. Igualmente, los usuarios de Internet Explorer 8 no podrán reproducir archivos multimedia.

