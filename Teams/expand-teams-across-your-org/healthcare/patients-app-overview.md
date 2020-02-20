---
title: 'Aplicación de pacientes para administradores de equipos '
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
description: Aplicación de pacientes para administradores de equipos
ms.openlocfilehash: 4c4eaced1b7e3c328d589906ac50cfb8ac805ea3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153792"
---
# <a name="patients-app-overview"></a>Información general de la aplicación Pacientes

La aplicación patients es una aplicación de la tienda Microsoft teams que está disponible para todos los usuarios de Teams. La aplicación permite que los equipos de cuidados de pacientes compuestos por trabajadores clínicos (por ejemplo, enfermeras, médicos, trabajadores sociales) puedan ajustar y revisar las listas de pacientes para escenarios que abarcan desde rondas y reuniones de equipos interdisciplinarios hasta monitoreo general de pacientes.

La aplicación tiene dos modos:

- El modo conectado de EMR que se conecta a EMRs a través de FHIR. La aplicación modo conectado de EMR permanece en la vista previa privada y los clientes interesados o los administradores pueden solicitar acceso a la aplicación colocando Microsoft un correo electrónico en [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com) con información sobre su inquilino de Office 365.
- El modo manual que permite a los equipos de atención médica agregar o aportar manualmente la información del paciente. La aplicación está disponible en la tienda de aplicaciones de Teams para que los usuarios finales la descarguen en la versión preliminar privada. La aplicación se puede restringir a determinadas secciones de usuarios que usan [directivas de configuración de aplicaciones](../../teams-app-setup-policies.md) en Teams. Para obtener acceso a la aplicación, su espacio empresarial debe formar parte del programa de adopción de tecnología (TAP). Envíenos un mensaje de correo electrónico a [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com) para iniciar el proceso de solicitud de acceso.

## <a name="usage-example"></a>Ejemplo de uso

Durante las sesiones de redondeo de cada turno en el exterior, los clínicos se reúnen en la estación de enfermería para hablar de las últimas actualizaciones en el progreso con pacientes en el mismo día.  Resaltan las principales métricas fundamentales (no necesariamente médicas o que son explícitas en los registros médicos de los pacientes) y garantizan que el paciente está en la ruta de la alas derecha para descargar en función de su diagnóstico. Para redondear a estos pacientes, el enfermeros de enfermería configura la aplicación del paciente en un equipo en el que se agregan todos los médicos y agrega pacientes a la lista de pacientes. Durante los retrasos, las enfermeras y otros brindadores de cuidados para el acceso del paciente a Microsoft Teams y a la aplicación de pacientes en sus dispositivos móviles y actualizan la información relevante del paciente en su dispositivo y, a continuación, cualquier persona en el equipo de cuidados puede ver dichas actualizaciones y notas Mantente sincronizado. Dos veces por día, al principio y al final de un turno, también tienen reuniones de equipo multidisciplinarias para repasar la lista de pacientes y usar la aplicación de pacientes para protegerse y compartir información sobre cada paciente con la aplicación de pacientes en una pantalla grande. A menudo, determinados médicos también pueden llamar a estas reuniones de Teams de forma remota y seguir siendo parte de la discusión.

## <a name="configure-patients-app"></a>Configurar la aplicación para pacientes

Para obtener información sobre cómo preparar su entorno para usar la aplicación para pacientes de modo EMR, consulte [integración de registros de asistencia médica electrónica en Microsoft Teams](patients-app.md). También tendrá que ver [las directivas de configuración de administración de aplicaciones en Microsoft Teams](../../teams-app-setup-policies.md) para habilitar la aplicación para pacientes para su organización.

Para obtener información sobre cómo los usuarios finales pueden tener acceso e instalar la aplicación de pacientes en un equipo que sean propietarios o que administren, consulte Introducción [a los pacientes de Microsoft Teams](https://support.office.com/article/get-started-with-microsoft-teams-patients-aa7daebe-706a-4a65-8ce9-b9b79233f393) 

<!-- add link out to client doc, doesn't seem to be available yet, Grant is finalizing -->

## <a name="frequently-asked-questions-faq"></a>Preguntas más frecuentes (p + f)

**¿Dónde se almacenan los datos de la aplicación patients?**

Todos los datos introducidos por los usuarios finales en la aplicación pacientes, incluido el esquema de columna o campo, los datos reales introducidos en la lista y los elementos de la lista (es decir, los pacientes) se almacenan en la infraestructura de Exchange Online segura y compatible. Todos los datos se almacenan en el buzón de correo del grupo que está asociado con el equipo. Esta arquitectura permite que la aplicación de pacientes pueda llevar a cabo con facilidad la residencia de datos, compatibilidad con la nube de administración pública (próximamente) y otras características de protección/cumplimiento de la información, como la compatibilidad con eDiscovery. La aplicación de pacientes funciona en un ámbito de equipo. Tendrá que instalar una instancia de la aplicación por equipo.

<!-- add link to eDiscovery article for the Patients app, Mark Johnson will finalize soon -->

**¿Desde dónde puedo comprar la aplicación para pacientes?**

Si la aplicación de pacientes está habilitada para su organización por su administrador, cualquier usuario final puede ir a la tienda de aplicaciones de Teams y agregar la aplicación patients a un equipo del que sean miembros. Para obtener más información, vea [Administrar directivas de configuración de aplicaciones en Microsoft Teams](../../teams-app-setup-policies.md).

**¿Puedo tener varias instancias de la aplicación de pacientes en un equipo porque así funciona mi unidad o mi "?**

Actualmente, solo puede instalar una instancia de la aplicación de pacientes para un equipo dado y solo en el canal general. Sin embargo, dentro de la aplicación, se pueden crear varias listas para abordar escenarios de canal múltiple o de aislamiento o separación. De forma predeterminada, todos los miembros del equipo tendrán acceso a la pestaña pacientes en el canal general. 

**¿Puedo exportar todos los datos de la aplicación patients?**
Ahora mismo, esta característica estará disponible próximamente. 

**Debido a que esta aplicación se adapta a la PHI, ¿se está auditando para evitar el acceso no autorizado o el cumplimiento de reglamentaciones?**

Sí, hay. Todas las acciones de la interfaz de usuario que realiza un usuario de Microsoft Teams en la aplicación de pacientes se auditan y están disponibles en el centro de seguridad y cumplimiento. Los detalles se explican en el artículo [aquí](patients-audit.md)

## <a name="related-topics"></a>Temas relacionados

[Integración de registros sanitarios electrónicos en Microsoft Teams](patients-app.md)
