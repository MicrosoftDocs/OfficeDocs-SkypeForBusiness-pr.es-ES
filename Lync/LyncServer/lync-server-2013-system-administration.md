---
title: 'Lync Server 2013: administración del sistema'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: System administration
ms:assetid: 063eb962-b96a-4699-8579-bb7125112df4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720318(v=OCS.15)
ms:contentKeyID: 63969577
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 61285a73ba7fd3689842f15967286c4393b8e927
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030794"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="system-administration-in-lync-server-2013"></a>Administración del sistema en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-08-18_

La administración del sistema incluye las tareas administrativas diarias, tanto planificadas como a petición, que son necesarias para mantener un sistema de ti funcionando sin problemas. Normalmente, las tareas de administración del sistema se cubren mediante procedimientos escritos. Estos procedimientos ayudan a garantizar que todos los miembros del personal de soporte usan las mismas herramientas y métodos estándar.

En un entorno de Lync, las tareas típicas de administración del sistema incluyen la copia de seguridad y archivado de los grupos, los registros de supervisión, la creación y administración de usuarios y la actualización del software antivirus.

<div>

## <a name="system-troubleshooting"></a>Solución de problemas del sistema

Una organización debe estar preparada para tratar problemas inesperados y debe tener un procedimiento para administrar los problemas desde el punto en el que se informa hasta su resolución. La información acerca de cómo el personal de soporte ha diagnosticado un problema debe registrarse y usarse en el futuro para evitar la repetición del trabajo completado innecesariamente.

</div>

<div>

## <a name="system-troubleshooting-process"></a>Proceso de solución de problemas del sistema

En el siguiente diagrama se muestra el proceso de solución de problemas del sistema y las interacciones con otros roles de operaciones.

**Diagrama de solución de problemas del sistema**

![Diagrama de solución de problemas del sistema](images/Dn720318.869d0b89-6473-4b1f-9d90-59604b4b8e98(OCS.15).jpg "Diagrama de solución de problemas del sistema")

  - **Clasificar y priorizar**   esta tarea suele realizarla el servicio de asistencia al cliente. Por ejemplo, un problema se puede agrupar como un problema de software o un problema de hardware. A continuación, el problema se enruta al equipo de soporte técnico adecuado para su investigación. Las reglas para determinar la prioridad de un problema, junto con el tiempo para responder y la hora de resolución, se suelen definir en el SLA.

  - **Investigue y diagnostique**   el equipo de soporte técnico adecuado para diagnosticar el problema y propone cambios para resolver el problema. Si la solución es sencilla y no requiere control de cambios, la solución puede aplicarse de inmediato. Si la solución no es sencilla, debe producirse una solicitud de cambio y el proceso de administración de cambios debe administrar el trabajo propuesto, con frecuencia en un procedimiento de "rápido seguimiento". Los cambios que se realicen deben registrarse mediante el proceso de administración de la configuración.

  - **Cerrar y grabar**   después de probar la solución, debe cerrarse el problema. Si hay lecciones que hay que aprender a partir del problema, debe crearse una entrada en la base de conocimientos.

  - **Revisión y análisis**   de tendencias se deben realizar revisiones periódicas de los problemas recientes para identificar las tendencias de problemas. Por ejemplo, si los usuarios experimentan problemas frecuentes con inicios de sesión lentos en sus sitios de Lync, los problemas de ancho de banda de red podrían ser la causa. Los tiempos de resolución del problema y el efecto de las interrupciones en la disponibilidad del sistema deben revisarse y compararse con el SLA. La persona que relacionarse con el cliente sobre problemas del servicio, como un administrador de cuentas, debe ser informada de problemas importantes.

</div>

<div>

## <a name="issue-management-tools"></a>Herramientas de administración de problemas

Las herramientas del servicio de asistencia al cliente permiten que el personal registre, clasifique y priorice los nuevos problemas. A continuación, las herramientas proporcionan los procesos de flujo de trabajo para administrar la solicitud del servicio Issue a través de investigación y diagnóstico, a menudo por más de un equipo de soporte técnico. Las herramientas, que a menudo proporcionarán informes sobre los tiempos de resolución y las tendencias históricas, también pueden incluir una base de datos de Knowledge base, que se puede usar para buscar en problemas anteriores.

Microsoft Knowledge base es un registro útil de los problemas de soporte técnico que ha encontrado Microsoft. Para obtener más información, vea el sitio web de<http://go.microsoft.com/fwlink/?linkid=14898>soporte técnico de Microsoft ().

El software de terceros suele requerir personalización para satisfacer las necesidades de la organización, como la organización de los equipos, los requisitos de informes y las medidas que requiere el SLA.

</div>

<div>

## <a name="centralized-vs-decentralized-administration"></a>Administración centralizada frente a la administración descentralizada

Los roles y las responsabilidades para realizar tareas de administración de sistemas dependen de si la organización sigue un modelo centralizado, un modelo descentralizado o una combinación de ambos.

  - **Modelo centralizado**   en un modelo centralizado, uno o varios grupos administrativos mantienen un control completo de todo el entorno de Lync Server. Este modelo administrativo se asemeja a un centro de datos en el que todas las tareas de administración las realiza un solo grupo de tecnología de la información. Las funciones y las responsabilidades del equipo se deben definir en función de la experiencia y los conocimientos.

  - **Modelo**   descentralizado las organizaciones descentralizadas se encuentran en varias ubicaciones geográficas y tienen servidores de Lync Server y equipos de administradores en distintas ubicaciones. Por ejemplo, puede que haya personal de administración local y uno o más servidores que ejecuten Lync Server 2013 para cada país o región. O bien, puede haber un grupo de servidores que ejecuten Lync Server 2013 y un equipo administrativo para Norteamérica y otro para Europa. A veces, es posible que desee que los administradores se encarguen solo en su propio área geográfica y restrinjan los permisos para administrar los recursos en otras áreas.

Lync Server también le permite delegar tareas administrativas específicas a personas o grupos específicos mediante el control de acceso basado en roles (RBAC). RBAC permite a los administradores delegar derechos de usuario y permisos específicos a otros administradores para que realicen un subconjunto de las tareas administrativas posibles. Mediante RBAC, la capacidad del usuario para realizar tareas administrativas específicas depende de los roles RBAC asignados al usuario. RBAC proporciona una lista de cmdlets que el usuario puede ejecutar en función de los roles RBAC de los que el usuario es miembro.

</div>

</div>

<span> </span>

</div>

</div>

</div>

