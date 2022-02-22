---
title: Preguntas más frecuentes sobre los datos de turnos
author: lanachin
ms.author: v-lanachin
ms.reviewer: aaku
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
description: Obtenga respuestas a las preguntas más frecuentes sobre los datos de Turnos, como dónde se almacenan los datos de Turnos, retención de datos, recuperación y cifrado.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 2df5c465c9115dce47ee9e80ea649768606c338f
ms.sourcegitcommit: 10bee789272e648ea1e93d7d7c27ec645d0a8bdd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/22/2022
ms.locfileid: "62918962"
---
# <a name="shifts-data-faq"></a>Preguntas más frecuentes sobre los datos de turnos

En este artículo se tratan las preguntas más frecuentes sobre los datos de Turnos, como dónde se almacenan los datos de Turnos, la retención de datos, la recuperación y el cifrado.

## <a name="where-is-shifts-data-stored"></a>¿Dónde se almacenan los datos de Turnos?

Los datos de turnos se almacenan en una de las tres geografías (geos): Asia Pacífico (APAC), la Unión Europea (UE) o Estados Unidos. Cada geo almacena datos en al menos dos regiones del centro de datos de Azure para alta disponibilidad (HA) y recuperación ante desastres (DR). Hoy en día, el geo de Estados Unidos/Norteamérica usa centros de datos en Centro Norte y Centro y Sur de Estados Unidos. Para obtener más información, vea [Dónde Microsoft 365 datos de clientes almacenados](/microsoft-365/enterprise/o365-data-locations).

Actualmente, Shifts ofrece residencia de datos en Australia, Canadá, Francia, Japón y el Reino Unido. Estamos trabajando activamente para expandir el soporte técnico a más ubicaciones.

## <a name="can-i-choose-where-shifts-data-is-stored"></a>¿Puedo elegir dónde se almacenan los datos de Turnos?

La primera vez que configure Teams, elija un país o región, que se establece en el nivel de suscripción. Turnos respeta esta selección y usa la configuración regional y la región que se establece en Teams si se admite esa región. Si aún no estamos en esa región, almacenamos datos en una región cercana compatible. En el futuro, planeamos migrar datos existentes, si se almacenan en una región cercana, a la región que se aprovisiona en Teams.

## <a name="can-i-access-and-export-or-delete-a-users-personal-data-in-shifts"></a>¿Puedo acceder y exportar o eliminar los datos personales de un usuario en Turnos?

Los turnos cumplen con el Reglamento general de protección de datos (RGPD).Una solicitud formal de una persona (conocida como interesado) para realizar una acción sobre sus datos personales se denomina solicitud de interesado (DSR). Puede buscar y actuar en función de los datos personales en Turnos en respuesta a un DSR.

Puede usar la herramienta de exhibición de documentos electrónicos de búsqueda de contenido en el Centro de cumplimiento de Microsoft 365 para buscar y exportar datos de programación y reloj de hora a Excel. Para todos los demás datos de Turnos, puede realizar capturas de pantalla de los datos.

Para obtener más información, [vea Office 365 solicitudes del interesado para el RGPD y el CCPA](/microsoft-365/compliance/gdpr-dsr-office365).

## <a name="what-happens-to-shifts-data-if-i-turn-off-shifts-for-my-organization"></a>¿Qué ocurre con los datos de Turnos si despegar turnos de mi organización?

Desactivar Turnos en su organización *no elimina* los datos. Si desactiva Turnos y luego activa Turnos, los datos de Turnos seguirán estando disponibles.

Si elimina el espacio empresarial, todos los datos de Turnos se eliminan después de que finalice el período de retención.

No hay ninguna opción para eliminar solo los datos de Turnos. Si elimina un equipo en Teams, los datos de programación de Turnos asociados a ese equipo se eliminan una vez que finalice el período de retención. Para obtener más información, vea [Retención, eliminación](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview) y eliminación de datos en Microsoft 365.

## <a name="can-i-recover-a-shifts-schedule-that-was-deleted"></a>¿Puedo recuperar una programación de Turnos que se eliminó?

Puede recuperar una programación eliminada si se restaura Microsoft 365 grupo que la copia de seguridad (o el equipo de Teams).

De forma predeterminada, un grupo eliminado de Microsoft 365 se conserva durante 30 días. Este período de 30 días se denomina "eliminación suave" porque todavía puede restaurar el grupo. Para obtener más información, vea [Restaurar un grupo Microsoft 365 eliminado.](/microsoft-365/admin/create-groups/restore-deleted-group?view=o365-worldwide&tabs=admin-center)

## <a name="can-i-use-custom-retention-policies-for-shifts-data"></a>¿Puedo usar directivas de retención personalizadas para los datos de Turnos?

Actualmente, Turnos no admite directivas de retención personalizadas.

Para obtener más información sobre las directivas de retención en Teams, vea [](/microsoft-365/compliance/retention-policies-teams) Información sobre la retención para Teams y Administrar directivas de retención [para Teams](../../retention-policies.md).

## <a name="can-i-retrieve-shifts-data-for-a-user-whose-license-was-revoked"></a>¿Puedo recuperar datos de Turnos para un usuario cuya licencia se ha revocado?

Hoy en día, no ofrecemos la posibilidad de recuperar datos de un usuario cuya licencia se revocó. Esta capacidad es algo con lo que estamos trabajando.

## <a name="is-shifts-supported-in-government-cloud-community-gcc-environments"></a>¿Se admiten turnos en entornos de Community (GCC) gubernamentales?

Los turnos están disponibles en GCC, pero no en GCC altos o doD.

## <a name="what-type-of-encryption-does-shifts-use-for-data-at-rest-and-in-transit"></a>¿Qué tipo de cifrado usa Turnos para los datos en reposo y en tránsito?

Los datos de Turnos están cifrados en reposo por Azure Cosmos DB y Azure Storage. Para obtener más información, vea [Cifrado de datos de Azure en](/azure/security/fundamentals/encryption-atrest) reposo y Cifrado [de datos en Azure Cosmos DB](/azure/cosmos-db/database-encryption-at-rest).

Turnos sigue las Microsoft 365 para el cifrado de datos en tránsito. Para obtener más información, vea [Cifrado para datos en tránsito](/compliance/assurance/assurance-encryption-in-transit).

El cifrado de turnos de datos en reposo y en tránsito se comprueba  año tras año mediante la auditoría de cumplimiento de SOC2.

## <a name="can-i-access-immutable-copies-of-shifts-data"></a>¿Puedo acceder a copias inmutables de datos de Turnos?

No almacenamos copias inmutables de los datos de Turnos. Por ejemplo, un administrador puede realizar cambios en una programación, como agregar notas, cambiar los horarios de turno, asignar tareas, entre otros.

## <a name="can-shifts-data-be-edited"></a>¿Se pueden editar los datos de Turnos?

Hay ciertos aspectos de turnos que no se pueden cambiar y ciertos aspectos que se pueden cambiar. Por ejemplo, los detalles de turno, como notas y colores, se pueden modificar de forma similar a como se pueden cambiar en la aplicación Turnos. Las solicitudes de turno no se pueden editar a menos que se retire la solicitud.

Para ver qué campos se han cambiado, puede buscar en el Microsoft 365 de auditoría de eventos de Turnos. Para obtener más información sobre los eventos que se registran para las actividades de Turnos en el registro de auditoría de Microsoft 365, vea [Turnos en Teams actividades](../../audit-log-events.md#shifts-in-teams-activities).

## <a name="my-organization-uses-a-workforce-management-system-for-scheduling-can-we-integrate-with-and-access-shifts-data"></a>Mi organización usa un sistema de administración de la fuerza de trabajo para la programación. ¿Podemos integrar con datos de Turnos y acceder a ellos?

Los cambios Graph API le permiten integrar los datos de Turnos con sistemas de administración de fuerza de trabajo externos (WFM). Para obtener más información, vea [Turnos Graph API](/graph/api/resources/shift).

También ofrecemos conectores de turnos administrados y conectores de turnos de código abierto. Con estos conectores, puede integrar su sistema WFM directamente con Turnos. Para obtener más información sobre los conectores de Turnos y los sistemas WFM compatibles, vea [Conectores de turnos](shifts-connectors.md).

## <a name="can-shifts-data-be-deleted-permanently-after-a-specified-period-of-time"></a>¿Los datos de Turnos se pueden eliminar permanentemente después de un período de tiempo especificado?

Hoy en día, no eliminamos los datos de Turnos en absoluto. Con [Mayúss Graph API](/graph/api/resources/shift), es posible crear una aplicación con Power Apps conservar los [](/powerapps/maker/) datos durante un período de tiempo especificado. Sin embargo, no lo admitemos de forma nativa.

## <a name="can-shifts-data-be-moved-in-a-tenant-to-tenant-migration"></a>¿Los datos de Turnos se pueden mover en una migración de inquilino a inquilino?

Los datos de turnos se pueden migrar de un inquilino a otro inquilino a petición específica. Tenga en cuenta que la migración de inquilino a inquilino no es compatible desde el primer momento, pero se puede elevar como una solicitud de cliente.

## <a name="related-articles"></a>Artículos relacionados

- [Turnos para Teams](../shifts-for-teams-landing-page.md)
- [Administrar la aplicación Turnos](manage-the-shifts-app-for-your-organization-in-teams.md)
