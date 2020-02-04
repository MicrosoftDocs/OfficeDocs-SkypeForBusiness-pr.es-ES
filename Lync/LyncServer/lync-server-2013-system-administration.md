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
ms.openlocfilehash: 8e10f0d340ec0d291d0b184b8649f8f132683e08
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764286"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="system-administration-in-lync-server-2013"></a>Administración del sistema en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-08-18_

La administración del sistema incluye las tareas administrativas cotidianas, tanto planificadas como a petición, que se requieren para mantener el funcionamiento correcto de un sistema de ti. Normalmente, las tareas de administración del sistema se cubren mediante procedimientos escritos. Estos procedimientos ayudan a garantizar que todos los empleados de soporte utilicen las mismas herramientas y métodos estándar.

En un entorno de Lync, las tareas típicas de administración del sistema incluyen la realización de copias de seguridad y el archivado de grupos, la supervisión de registros, la creación y administración de usuarios y la actualización de software antivirus.

<div>

## <a name="system-troubleshooting"></a>Solución de problemas del sistema

Una organización debe estar preparada para tratar problemas inesperados y debe tener un procedimiento para administrar los problemas desde el punto en el que se les informa hasta su resolución. Información sobre cómo el personal de soporte diagnosticó un problema se debe grabar y usar en el futuro para evitar la repetición del trabajo completado de forma innecesaria.

</div>

<div>

## <a name="system-troubleshooting-process"></a>Proceso de solución de problemas del sistema

En el siguiente diagrama se muestra el proceso de solución de problemas del sistema y las interacciones con otros roles de operaciones.

**Diagrama de flujo de solución de problemas del sistema**

![Diagrama de flujo de solución de problemas del sistema](images/Dn720318.869d0b89-6473-4b1f-9d90-59604b4b8e98(OCS.15).jpg "Diagrama de flujo de solución de problemas del sistema")

  - **Clasificar y priorizar**   esta tarea normalmente la realiza el servicio de asistencia al cliente. Por ejemplo, un problema puede estar agrupado como un problema de software o un problema de hardware. El problema se redirige al equipo de soporte técnico adecuado para que lo investigue. Las reglas para determinar la prioridad de un problema, junto con el tiempo para responder y el momento de la resolución, se definen normalmente en el SLA.

  - **Investigue y diagnostique**   el equipo de soporte técnico adecuado para diagnosticar el problema y proponer cambios para resolver el problema. Si la solución es sencilla y no requiere control de cambios, la solución se puede aplicar de inmediato. Si la solución no es sencilla, se debe elevar una solicitud de cambio y el proceso de administración de cambios debe administrar el trabajo propuesto, con frecuencia en un procedimiento de "seguimiento rápido". Los cambios que se realicen deben registrarse con el proceso de administración de la configuración.

  - **Cerrar y grabar**   después de probar la resolución, debe cerrarse el problema. Si hay clases que aprender del problema, debe crearse una entrada en la base de conocimientos.

  - **Revisión y análisis**   de tendencias se deben realizar revisiones periódicas de problemas recientes para identificar tendencias de problemas. Por ejemplo, si los usuarios experimentan problemas frecuentes con los inicios de sesión lentos en sus sitios de Lync, pueden producirse problemas de ancho de banda de red. Deben revisarse las horas de resolución de problemas y el efecto de las interrupciones en la disponibilidad del sistema y compararlas con el SLA. La persona que liaises al cliente sobre problemas del servicio, como un administrador de cuentas, debe estar informada de cualquier problema importante.

</div>

<div>

## <a name="issue-management-tools"></a>Herramientas de administración de problemas

Las herramientas de servicio de asistencia al cliente permiten a los empleados registrar, clasificar y priorizar nuevos problemas. Las herramientas proporcionarán los procesos de flujo de trabajo para administrar la solicitud de servicio de problemas mediante investigación y diagnóstico, a menudo por más de un equipo de soporte técnico. Las herramientas, que a menudo proporcionarán informes sobre los tiempos de resolución y las tendencias históricas, también pueden incluir una base de datos de Knowledge base, que se puede usar para buscar problemas anteriores.

Microsoft Knowledge base es un registro útil de los problemas de soporte técnico que ha encontrado Microsoft. Para obtener más información, consulte el sitio web de<http://go.microsoft.com/fwlink/?linkid=14898>soporte técnico de Microsoft ().

El software de terceros suele requerir personalización para satisfacer las necesidades de la organización, como la organización de los equipos, los requisitos de informes y las medidas que necesita el SLA.

</div>

<div>

## <a name="centralized-vs-decentralized-administration"></a>Administración centralizada y descentralizada

Los roles y las responsabilidades para realizar las tareas de administración del sistema dependen de si la organización sigue un modelo centralizado, un modelo descentralizado o una combinación de ambos.

  - **Modelo centralizado**   en un modelo centralizado, uno o varios grupos administrativos mantienen un control total de todo el entorno de Lync Server. Este modelo administrativo se asemeja a un centro de datos en el que todas las tareas de administración las realiza un único grupo de tecnología de la información. Las funciones y responsabilidades dentro del equipo deben definirse en función de la experiencia y la experiencia.

  - **Modelo descentralizado**   las organizaciones descentralizadas se encuentran en varias ubicaciones geográficas y tienen servidores de Lync Server y equipos de administradores en diferentes ubicaciones. Por ejemplo, es posible que haya personal de administración local y uno o más servidores que ejecuten Lync Server 2013 para cada país o región. O bien, puede haber un grupo de servidores que ejecuten Lync Server 2013 y un equipo administrativo para Norteamérica y otro para Europa. En ocasiones, es posible que desee que los administradores sean responsables de su propio área geográfica y restringir los permisos para administrar los recursos de otras áreas.

Lync Server también le permite delegar tareas administrativas específicas a personas o grupos específicos mediante el control de acceso basado en roles (RBAC). RBAC permite que los administradores deleguen permisos y derechos de usuario específicos a otros administradores para realizar un subconjunto de las tareas administrativas posibles. Al usar RBAC, la capacidad del usuario para realizar tareas administrativas específicas depende de los roles RBAC que se asignan al usuario. RBAC proporciona una lista de cmdlets que el usuario puede ejecutar en función de los roles RBAC de los que es miembro el usuario.

</div>

</div>

<span> </span>

</div>

</div>

</div>

