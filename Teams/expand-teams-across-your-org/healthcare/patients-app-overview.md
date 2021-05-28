---
title: 'Aplicación Pacientes para administradores de Teams '
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: Obtenga información sobre la aplicación Pacientes para administradores de Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 2302f117564e1dd00a6f238ca23a8e36c63ae554
ms.sourcegitcommit: e6e6a2a85ff376f97a3af3548e13d1273fa84a52
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/28/2021
ms.locfileid: "52697847"
---
# <a name="patients-app-overview"></a>Información general de la aplicación Pacientes

> [!NOTE]
> Desde el 30 de octubre de 2020, la aplicación Pacientes se retiró y se reemplazó por la aplicación [Listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) en Teams. Los datos de la aplicación Pacientes se almacenan en el buzón de correo del grupo de Office 365 que respalda al equipo. Todos los datos asociados con la aplicación Pacientes se conservan en este grupo, pero ya no se puede acceder a ellos a través de la interfaz de usuario. Los usuarios pueden volver a crear sus listas mediante la [aplicación Listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).
>
>Con Listas, los equipos del cuidado de la salud de su organización sanitaria pueden crear listas de pacientes para escenarios que van desde guardias y reuniones interdisciplinarias de equipo, hasta el seguimiento general de pacientes. Consulte la plantilla Pacientes en Listas para comenzar. Para obtener más información sobre cómo administrar la aplicación Listas en su organización, consulte [Administrar la aplicación Listas](../../manage-lists-app.md).

La aplicación Pacientes es una aplicación de la tienda de Microsoft Teams disponible para todos los usuarios de Teams. La aplicación permite que los equipos de salud de pacientes que constan de trabajadores clínicos (por ejemplo, enfermeras, médicos o trabajadores sociales), puedan seleccionar y revisar listas de pacientes en escenarios que van desde rondas y reuniones de equipos interdisciplinares, hasta el monitoreo general de pacientes.

La aplicación tiene dos modalidades:

- El modo Conectado EMR, que conecta a los EMR a través de FHIR. La aplicación de modo Conectado EMR permanece en vista previa privada y los clientes o administradores interesados pueden solicitar acceso a la misma enviando a Microsoft un correo electrónico a [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com) con información sobre su organización de Microsoft 365.
- El modo manual, que permite a los equipos de salud agregar o traer información del paciente de forma manual. La aplicación está disponible en la tienda de aplicaciones de Teams para que los usuarios finales la descarguen en una versión preliminar privada. La aplicación se puede restringir a determinadas secciones de usuarios que utilizan [directivas de configuración de aplicaciones](../../teams-app-setup-policies.md) en Teams. Para obtener acceso a la aplicación, el espacio empresarial debe ser parte del Programa de adopción de tecnología (TAP). Envíenos un correo electrónico a [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com) para iniciar el proceso de solicitud de acceso.

## <a name="usage-example"></a>Ejemplo de uso

Durante las sesiones clínicas de cada turno de las salas médicas, los médicos se reúnen en la estación de enfermería para discutir los últimos acontecimientos sobre el progreso de los pacientes en la sala.  Destacan las métricas críticas clave (no necesariamente médicas o que estén explícitas en los registros médicos de los pacientes) y se aseguran de que el paciente esté en el camino correcto hacia el alta en función del diagnóstico. Para valorar a estos pacientes, la enfermera a cargo configura la aplicación Paciente en un equipo al que se agrega a todos los médicos y a los pacientes de una lista de pacientes. Durante las valoraciones, las enfermeras y los demás cuidadores del paciente acceden a Microsoft Teams y la aplicación Pacientes en sus dispositivos móviles y actualizan la información relevante del paciente en su dispositivo, tras lo cual, todos los demás miembros del equipo de salud pueden ver esas actualizaciones y notas y permanecer sincronizados. Dos veces al día, al comienzo y al final de un turno, también tienen reuniones de equipo multidisciplinares para revisar la lista de pacientes y usar la aplicación Pacientes para establecer conexión y compartir información sobre cada paciente gracias a la aplicación en una pantalla grande. A menudo, algunos médicos también pueden conectarse a estas reuniones de Teams de forma remota y seguir formando parte de la discusión.

## <a name="configure-patients-app"></a>Configurar la aplicación Pacientes

Vea [Administrar directivas de configuración de aplicaciones en Microsoft Teams](../../teams-app-setup-policies.md) para habilitar la aplicación Pacientes para su organización.

Para obtener información sobre cómo los usuarios finales pueden acceder a la aplicación Pacientes e instalarla en un equipo que poseen o administran, consulte [Introducción a Microsoft Teams Pacientes](https://support.office.com/article/get-started-with-microsoft-teams-patients-aa7daebe-706a-4a65-8ce9-b9b79233f393).

<!-- add link out to client doc, doesn't seem to be available yet, Grant is finalizing -->

## <a name="frequently-asked-questions-faq"></a>Preguntas más frecuentes (P+F)

**¿Dónde se almacenan los datos de la aplicación Pacientes?**

Todos los datos introducidos por los usuarios finales en la aplicación Pacientes, incluido el esquema de columna / campo, los datos reales ingresados en la lista y los elementos de la misma (es decir, los pacientes), se almacenan en la infraestructura compatible y segura de Exchange Online. Todos los datos se almacenan en el buzón de correo del grupo asociado con el equipo. Esta arquitectura permite que la aplicación Pacientes cumpla fácilmente con la residencia de datos, el soporte de gobierno en la nube (disponible en el futuro) y otras características de protección de la información o de cumplimiento, como el soporte de eDiscovery. La aplicación Pacientes opera en un entorno de equipo. Deberá instalar una instancia de la aplicación por equipo.

<!-- add link to eDiscovery article for the Patients app, Mark Johnson will finalize soon -->

**¿Dónde puedo adquirir la aplicación Pacientes?**

Si el administrador habilita la aplicación Pacientes para la organización, cualquier usuario final puede ir a la tienda de aplicaciones de Teams y agregar la aplicación Pacientes a un equipo del que sea miembro. Para más información, consulte [Administrar directivas de configuración de aplicaciones en Microsoft Teams](../../teams-app-setup-policies.md).

**¿Puedo tener varias instancias de la aplicación Pacientes en un equipo si así es como funciona mi sala / unidad?**

Actualmente, solo puede instalar una instancia de la aplicación Pacientes en un equipo determinado, y solo en el canal general. Sin embargo, dentro de la aplicación se pueden crear varias listas para abordar escenarios multicanales o de aislamiento / separación. De forma predeterminada, todos los miembros del equipo tendrán acceso a la pestaña Pacientes en el canal general. 

**¿Puedo exportar todos los datos de la aplicación Pacientes?**
No en este momento, aunque esta función estará disponible pronto. 

**Dado que esta aplicación se adapta a la PHI, ¿existe una auditoría para evitar el acceso no autorizado o el cumplimiento de las regulaciones?**

Sí, existe. Cada acción de IU realizada por un usuario de Microsoft Teams en la aplicación Pacientes se audita y está disponible en el centro de seguridad y cumplimiento. Los detalles se explican en los [Registros de auditoría para la aplicación Pacientes](patients-audit.md).

