---
title: 'Lync Server 2013: administración de cambios'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Change management
ms:assetid: 73c774f5-c12f-4c72-be73-e07dc745b994
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720336(v=OCS.15)
ms:contentKeyID: 63969618
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7de514dee1b9e185e880660be656b493ae520340
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151100"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="change-management-in-lync-server-2013"></a>Administración de cambios en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-08-18_

Los cambios en el entorno de TI son inevitables. Los cambios incluyen nuevas tecnologías, sistemas, aplicaciones, hardware, herramientas, procesos y cambios en funciones y responsabilidades. Un sistema de administración de cambios eficaz le permite introducir cambios en el entorno de ti rápidamente y con una interrupción mínima del servicio. Un sistema de administración de cambios reúne a todos los equipos que participan en el cambio de un sistema. Por ejemplo, decidirse por sacar partido de Office Web Apps. Se trata de una aplicación de servicio de Lync integrada que permite a los usuarios leer y editar documentos en un explorador. La implementación de este servicio, después de haber pasado a producción, requiere la implicación de varios equipos:

  - **Equipo de prueba**   este grupo comprueba la carga de Office Web Apps en un servidor de prueba, en el proceso que proporciona información sobre los patrones de uso esperados y el rendimiento esperado de los servidores de producción.

  - **Administradores de Lync**   este equipo determina la estrategia de implementación y los scripts de la instalación donde fue posible. El equipo es responsable de garantizar que el cambio se implemente en el entorno de producción y es responsable de la administración posteriormente. El equipo debe comprender el efecto de los cambios e incorporarlos a los procedimientos antes de que los cambios se pongan en producción.

  - **Equipo de red**   este equipo es responsable de los cambios en las reglas del firewall que permiten el acceso desde Internet a los servidores internos del grupo de Lync. El equipo también es responsable de trabajar con los administradores de Lync para asegurarse de que el ancho de banda disponible puede admitir la carga adicional.

  - **Equipo de seguridad**   este equipo evalúa la seguridad y minimiza los riesgos. El equipo de seguridad debe revisar las vulnerabilidades conocidas y ayudar a garantizar que los riesgos de seguridad se minimizan.

  - **Equipo de aceptación del usuario**   este equipo está formado por usuarios que están dispuestos a probar el sistema y ofrecer comentarios para mejoras.

El proceso de administración de cambios define las responsabilidades de cada equipo y programa el trabajo que se va a realizar, incorporando comprobaciones y pruebas en las que son necesarias. Los controles de cambios variarán en función de la complejidad y del efecto esperado de un cambio. Pueden variar desde la aprobación automática de cambios menores, para cambiar las reuniones de revisión, a revisiones de nivel de proyecto completas. Para explicar esto mejor, los grupos de cambios se describen en esta sección.

  - **Cambios**   importantes los cambios importantes tienen un efecto global en el sistema y pueden requerir la entrada de varios equipos. Un ejemplo de esto es la actualización a Lync Server 2013. Los cambios principales afectan a muchos equipos y quizás a diferentes sistemas. El proceso de administración de cambios probablemente incluirá una o más reuniones de revisión de cambios para informar a los equipos que participarán en el cambio o que se verán afectados por el cambio.

  - **Cambios significativos los**   cambios significativos requieren recursos significativos para planear, crear e implementar. Deben introducirse controles de cambio apropiados para garantizar que se comprenda el efecto del cambio, que se prueban los procedimientos de implementación y que los planes de reversión y contingencia están listos. Un ejemplo de cambio importante es la implementación de una nueva actualización acumulativa.

  - **Cambios**   menores los cambios menores no afectan significativamente al entorno de ti, por ejemplo, al cambiar ciertas directivas de Lync a través del panel de control de Microsoft Lync Server 2013.

  - **Cambios estándar los**   cambios estándar se realizan regularmente y se entienden y documentan correctamente. El proceso de administración de cambios debe revisar todos los cambios realizados en los procedimientos. No debería ser necesario para cambios rutinarios como la creación de una base de datos de contenido o la adición de un usuario.

El siguiente ejemplo de administración de cambios examina cómo interactúan diferentes equipos y las acciones que se realizan cuando se implementa un nuevo Service Pack. Estas acciones están organizadas y administradas por el proceso de administración de cambios.

  - **Generar una solicitud**   de cambio el equipo de seguridad ha evaluado el último Service Pack y confirmado que resuelve una posible vulnerabilidad en el sistema de producción. El equipo genera una solicitud de cambio para que la nueva actualización acumulativa se aplique a todos los servidores que ejecutan Lync Server.

  - **Notas de la versión del Service Pack Revise**   el equipo de administrador de Lync revisa las notas de la versión del Service Pack para identificar el efecto en el sistema.

  - **Se realiza**   una serie de pruebas de laboratorio el equipo de administrador de Lync debe realizar las actualizaciones de prueba en un servidor en un entorno de prueba para decidir si el Service Pack se puede aplicar correctamente sin afectar a ninguna de las aplicaciones y los sistemas de servidor instalados. Si hay aplicaciones de terceros o creadas internamente que se encuentran en la interfaz con Lync Server en un entorno de producción, también deben probarse. Estas pruebas también se pueden usar para estimar el tiempo necesario para realizar las actualizaciones.

  - **Se informa a los usuarios de la interrupción**   que el equipo de administrador de Lync, el equipo de comunicaciones o el servicio de asistencia al usuario informe a todos los usuarios afectados sobre el ciclo de mantenimiento planeado y el tiempo que el servicio no estará disponible.

  - **Se realiza una copia de seguridad completa de Lync antes de la actualización**   el equipo de administrador de Lync debe comprobar que hay una copia de seguridad válida que se puede usar para volver al estado original del sistema si se produce un error en la instalación del Service Pack. Le recomendamos que se restaure la copia de seguridad en un servidor en espera para que este sistema esté disponible fácilmente si hay problemas.

  - **Se ha implementado**   la actualización acumulativa el equipo de administrador de Lync realiza la instalación durante el ciclo de mantenimiento planeado.

<div>

## <a name="managing-the-timing-of-changes"></a>Administración del tiempo de los cambios

Le recomendamos que implemente un procedimiento para programar cambios para evitar interrupciones en secciones superpuestas del trabajo. Por ejemplo, es posible que dos equipos tengan que planear un cambio menor en un sistema. Un equipo puede estar aplicando una actualización acumulativa en un grupo mientras otro equipo está migrando usuarios heredados a ese grupo. Ningún equipo se ve afectado por los cambios que el otro equipo está planeando, y es posible que cada equipo no reconozca necesariamente los cambios que el otro equipo está planeando. Si se produjeron ambos cambios al mismo tiempo, es posible que haya problemas para implementar los cambios. Además, si hay problemas después de que se aplicaron los cambios, por ejemplo, si se produce un error en la migración del usuario, puede ser difícil decidir qué cambio se debe deshacer. Debe haber períodos de mantenimiento regulares configurados entre ti y la administración para probar los cambios y aceptarlos.

</div>

</div>

<span> </span>

</div>

</div>

</div>

