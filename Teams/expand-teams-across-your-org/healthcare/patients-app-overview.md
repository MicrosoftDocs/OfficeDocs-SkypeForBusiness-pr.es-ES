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
description: Más información sobre la aplicación Pacientes para administradores de Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 92bc7581610abf1dc8baab17d2e9d23abb6c6fd3
ms.sourcegitcommit: beaaee10019f4eda746f348888a4a3c2aaa6f196
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2020
ms.locfileid: "48803508"
---
# <a name="patients-app-overview"></a>Información general de la aplicación Pacientes

> [!NOTE]
> A partir del 30 de octubre de 2020, la aplicación Pacientes se ha retirado y reemplazado por la [aplicación Listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) en Teams. Los datos de la aplicación Pacientes se almacenan en el buzón de grupo del grupo de Office 365 que copia de seguridad del equipo. Todos los datos asociados a la aplicación Pacientes se conservan en este grupo, pero ya no se puede acceder a ellos a través de la interfaz de usuario. Los usuarios pueden volver a crear sus listas con la [aplicación Listas.](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)
>
>Con Listas, los equipos de cuidado de su organización sanitaria pueden crear listas de pacientes para situaciones que van desde rounds y reuniones de equipo interdisciplinarias hasta la supervisión general del paciente. Consulte la plantilla Pacientes en Listas para empezar. Para obtener más información sobre cómo administrar la aplicación Listas en su organización, vea [Administrar la aplicación Listas.](../../manage-lists-app.md)

La aplicación Pacientes es una aplicación de la tienda de Microsoft Teams disponible para todos los usuarios de Teams. La aplicación permite a los equipos de salud del paciente consisten en trabajadores clínicos (por ejemplo, enfermeras, médicos y trabajadores sociales) puede organizar y revisar listas de pacientes para situaciones que van desde las reuniones interdisciplinarias y las reuniones del equipo hasta la supervisión general del paciente.

La aplicación tiene dos modos:

- El modo conectado DESP que se conecta a EMR a través de FLC. La aplicación de modo conectado DE LAN se mantiene en versión preliminar privada y los clientes o administradores interesados pueden solicitar acceso a la aplicación soltándolos en un correo electrónico a [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com) con información sobre su organización de Microsoft 365.
- El modo manual que permite que los equipos de salud agreguen o agreguen información del paciente manualmente. La aplicación está disponible en la tienda de aplicaciones de Teams para que los usuarios finales la descarguen en una vista previa privada. La aplicación puede restringirse a determinadas secciones de usuarios mediante las directivas de [configuración de aplicaciones](../../teams-app-setup-policies.md) en Teams. Para obtener acceso a la aplicación, su inquilino debe formar parte de la Programa de adopción de tecnología (TAP) (TAP). Envíanos un correo electrónico a [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com) para iniciar el proceso y solicitar acceso.

## <a name="usage-example"></a>Ejemplo de uso

Durante las sesiones de redondeo en cada turno de los centros médicos, los médicos se reúnen en el centro de enfermería para discutir sobre las últimas actualizaciones sobre el progreso con los pacientes del centro.  Resaltan las métricas críticas clave (no necesariamente médicas o que son explícitas en los registros médicos del paciente) y se aseguran de que el paciente está en la ruta correcta para la descarga en función de su diagnóstico. Para redondear estos pacientes, la enfermera responsable configura la aplicación para el paciente en un equipo en el que se agregan todos los médicos y se agregan pacientes a una lista de pacientes. Durante las asistencias, las enfermeras y los otros cuidadores del paciente pueden acceder a Microsoft Teams y a la aplicación Pacientes en sus dispositivos móviles, así como actualizar la información relevante del paciente en sus dispositivos para que el resto del equipo pueda ver esas actualizaciones y notas, y mantenerse sincronizado. Dos veces al día, al comienzo y al final de un turno, también tienen varias reuniones de equipo para rebanarse la lista de pacientes y usar la aplicación Pacientes para base y compartir información sobre cada paciente con la aplicación Pacientes en una pantalla de gran tamaño. A menudo, ciertos médicos también pueden marcar para un acceso remoto a estas reuniones de Teams y seguir formando parte de la discusión.

## <a name="configure-patients-app"></a>Aplicación Configurar pacientes

Para obtener información sobre cómo preparar su entorno para usar la aplicación pacientes en modo DESC, consulte Integración de registros sanitarios [electrónicos en Microsoft Teams.](patients-app.md) También debe ver Administrar directivas de configuración de aplicaciones [en Microsoft Teams para](../../teams-app-setup-policies.md) habilitar la aplicación Pacientes para su organización.

Para obtener información sobre cómo los usuarios finales pueden acceder a la aplicación Pacientes e instalarla en un equipo de su propiedad o administrador, consulte Introducción a [Pacientes de Microsoft Teams.](https://support.office.com/article/get-started-with-microsoft-teams-patients-aa7daebe-706a-4a65-8ce9-b9b79233f393)

<!-- add link out to client doc, doesn't seem to be available yet, Grant is finalizing -->

## <a name="frequently-asked-questions-faq"></a>Preguntas más frecuentes (P+F)

**¿Dónde se almacenan los datos de la aplicación Pacientes?**

Todos los datos introducidos por los usuarios finales en la aplicación Pacientes, incluido el esquema de columna o campo, los datos reales introducidos en la lista y los elementos de lista (es decir, pacientes) se almacenan en la infraestructura segura y compatible de Exchange Online. Todos los datos se almacenan en el buzón de grupo que está asociado con el equipo. Esta arquitectura permite a la aplicación Pacientes cumplir fácilmente la residencia de datos, el soporte en la nube de la administración pública (próximamente) y otras características de protección de la información y cumplimiento, como el soporte de exhibición de documentos electrónicos. La aplicación Pacientes funciona en un ámbito de equipo. Tendrá que instalar una instancia de la aplicación por equipo.

<!-- add link to eDiscovery article for the Patients app, Mark Johnson will finalize soon -->

**¿Desde dónde puedo adquirir la aplicación Pacientes?**

Si el administrador de la aplicación Pacientes está habilitada para su organización, cualquier usuario final puede ir a la tienda de aplicaciones de Teams y agregar la aplicación Pacientes a un equipo del que es miembro. Para obtener más información, vea [Administrar directivas de configuración de aplicaciones en Microsoft Teams.](../../teams-app-setup-policies.md)

**¿Puedo tener varias instancias de la aplicación Pacientes en un equipo porque así es como funciona mi sala de estar/unidad?**

Actualmente, solo puede instalar una instancia de la aplicación Pacientes para un equipo determinado, y solo en el canal general. Sin embargo, dentro de la aplicación, se pueden crear varias listas para dirigirse a escenarios de separación o de aislamiento o multicanal. De forma predeterminada, todos los miembros del equipo tendrán acceso a la pestaña Pacientes en el canal general. 

**¿Puedo exportar todos los datos desde la aplicación Pacientes?**
En este momento no, pero esta característica estará disponible próximamente. 

**Puesto que esta aplicación se aplica a la fi, ¿hay auditorías para evitar el acceso o el cumplimiento no autorizados de las normativas?**

Sí. Cada acción de la interfaz de usuario realizada por un usuario de Microsoft Teams en la aplicación Pacientes se audita y está disponible en el centro de seguridad y cumplimiento. Los detalles se explican en los registros [de auditoría de la aplicación Pacientes.](patients-audit.md)

## <a name="related-topics"></a>Temas relacionados

[Integración de registros sanitarios electrónicos en Microsoft Teams](patients-app.md)
