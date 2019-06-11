---
title: 'Lync Server 2013: administración de cambios'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Change management
ms:assetid: 73c774f5-c12f-4c72-be73-e07dc745b994
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720336(v=OCS.15)
ms:contentKeyID: 63969618
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 13eb521ea6b4be5f8d701885df65a3e1672b2eaa
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842621"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="change-management-in-lync-server-2013"></a>Administración de cambios en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-08-18_

Los cambios en el entorno de TI son inevitables. Los cambios incluyen nuevas tecnologías, sistemas, aplicaciones, hardware, herramientas, procesos y cambios en roles y responsabilidades. Un sistema de administración de cambios eficaz le permite introducir cambios en el entorno de ti rápidamente y con interrupciones mínimas en el servicio. Un sistema de administración de cambios reúne los equipos implicados en el cambio de sistema. Por ejemplo, decidir sacar partido de Office Web Apps. Esta es una aplicación de servicio de Lync integrada que permite a los usuarios leer y editar documentos en un explorador. La implementación de este servicio, después de haber ido a producción, requiere la participación de varios equipos:

  - **Equipo de pruebas**   esta carga de equipo: prueba las aplicaciones Web de Office en un servidor de prueba, en el proceso que proporciona información sobre los patrones de uso esperados y el rendimiento esperado de los servidores de producción.

  - **Administradores de Lync**   este equipo determina la estrategia de implementación y las secuencias de comandos de la instalación donde fue posible. El equipo es responsable de asegurarse de que el cambio se implementa en el entorno de producción, y es responsable de la administración más adelante. El equipo debe comprender el efecto de los cambios e incorporarlos en procedimientos antes de que los cambios se pongan en producción.

  - **Equipo de red**   este equipo es responsable de los cambios en las reglas de firewall que permiten el acceso desde Internet a los servidores internos del grupo de servidores de Lync. El equipo también es responsable de trabajar con los administradores de Lync para asegurarse de que el ancho de banda disponible puede admitir la carga adicional.

  - **Equipo de seguridad**   este equipo evalúa la seguridad y minimiza los riesgos. El equipo de seguridad debe revisar las vulnerabilidades conocidas y ayudar a garantizar que se minimicen los riesgos de seguridad.

  - **Equipo de aceptación de usuario**   este equipo está compuesto de usuarios que están dispuestos a probar el sistema y ofrecer comentarios para mejoras.

El proceso de administración de cambios define las responsabilidades de cada equipo y programa el trabajo que se va a realizar, con la incorporación de comprobaciones y pruebas cuando sea necesario. Los controles de cambio variarán en función de la complejidad y del efecto esperado de un cambio. Pueden variar desde la aprobación automática de cambios menores, para cambiar las reuniones de revisión, a revisiones de nivel de proyecto completas. Para explicar esto mejor, los grupos de cambios se tratan en esta sección.

  - **Cambios**   importantes los cambios importantes tienen un efecto global en el sistema y pueden requerir la entrada de varios equipos. Un ejemplo de esto es la actualización a Lync Server 2013. Los cambios importantes afectan a muchos equipos y quizás a diferentes sistemas. El proceso de administración de cambios probablemente incluirá una o varias reuniones de revisión de cambios para informar a los equipos que participarán en el cambio o que se verán afectados por el cambio.

  - **Cambios importantes los**   cambios significativos requieren recursos importantes para planear, crear e implementar. Deben introducirse controles de cambio apropiados para ayudar a garantizar que el efecto del cambio se entienda, los procedimientos de implementación se prueban y los planes de reversión y de contingencia están listos. Un ejemplo de un cambio significativo es implementar una nueva actualización acumulativa.

  - ****   Los cambios menores los cambios menores no afectan significativamente al entorno de ti, por ejemplo, al cambio de determinadas directivas de Lync a través del panel de control de Microsoft Lync Server 2013.

  - **Cambios**   estándar los cambios estándar se realizan regularmente y se han entendido y documentado correctamente. El proceso de administración de cambios debe revisar todos los cambios realizados en los procedimientos. No debería ser necesario para cambios rutinarios como la creación de una base de datos de contenido o la adición de un usuario.

El siguiente ejemplo de administración de cambios examina cómo interactúan diferentes equipos y las acciones que se realizan cuando se implementa un nuevo Service Pack. Estas acciones están organizadas y administradas por el proceso de administración de cambios.

  - **Iniciar una solicitud**   de cambio el equipo de seguridad ha evaluado el último Service Pack y confirmado que resuelve una posible vulnerabilidad en el sistema de producción. El equipo genera una solicitud de cambio para que la nueva actualización acumulativa se aplique a todos los servidores que ejecutan Lync Server.

  - **Notas de la versión del Service Pack Revise**   el equipo del administrador de Lync revisa las notas de la versión del Service Pack para identificar el efecto en el sistema.

  - **Se realiza**   una serie de pruebas de laboratorio el equipo de administrador de Lync debe realizar actualizaciones de prueba en un servidor en un entorno de prueba para decidir si el Service Pack se puede aplicar correctamente sin afectar a ninguna de las aplicaciones y servidores instalados. redes. Si hay aplicaciones de terceros o creadas internamente con la interfaz de Lync Server en un entorno de producción, también se deben probar. Estas pruebas también se pueden usar para estimar el tiempo necesario para realizar las actualizaciones.

  - **Se informa a los usuarios de la interrupción**   : el equipo de administrador de Lync, el equipo de comunicaciones o el servicio de asistencia al usuario informa a todos los usuarios afectados sobre el ciclo de mantenimiento planeado y el tiempo durante el cual el servicio no estará disponible.

  - **Se realiza una copia de seguridad completa de Lync antes de la actualización**   el equipo del administrador de Lync debe comprobar que hay una copia de seguridad válida que se puede usar para volver al estado original del sistema si se produce un error en la instalación del Service Pack. Le recomendamos que se restaure la copia de seguridad en un servidor de reserva para que este sistema esté disponible si hay problemas.

  - **La actualización acumulativa se ha implementado**   el equipo de administrador de Lync realiza la instalación durante el ciclo de mantenimiento planeado.

<div>

## <a name="managing-the-timing-of-changes"></a>Administrar los intervalos de cambios

Le recomendamos que implemente un procedimiento de programación de cambios para evitar interrupciones en secciones superpuestas de su trabajo. Por ejemplo, dos equipos pueden estar planeando un cambio menor en un sistema. Un equipo puede estar aplicando una actualización acumulativa en un grupo mientras otro equipo está migrando usuarios heredados a ese grupo. Ningún equipo se ve afectado por los cambios que el otro equipo está planeando, y es posible que cada equipo no sepa necesariamente los cambios que el otro equipo está planeando. Si los dos cambios se produjeron al mismo tiempo, es posible que haya problemas para implementar los cambios. Además, si hay problemas después de la aplicación de los cambios, por ejemplo, si se produce un error en la migración de usuario, puede ser difícil decidir qué cambio se debe revertir. Deben configurarse períodos de mantenimiento regulares entre ti y la administración para probar los cambios y aceptarlos.

</div>

</div>

<span> </span>

</div>

</div>

</div>

