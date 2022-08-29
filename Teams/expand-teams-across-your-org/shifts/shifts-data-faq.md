---
title: Preguntas más frecuentes sobre los datos de Turnos
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
description: Obtenga respuestas a las preguntas más frecuentes sobre los datos de Turnos, incluido dónde se almacenan los datos de Turnos, la retención, la recuperación y el cifrado de datos.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- microsoftcloud-healthcare
- m365-frontline
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: f7132f79936616ba66565cd133e5ab8616541254
ms.sourcegitcommit: 46dbff43eec9631863b74b2b49c9a29c6497d8e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/20/2022
ms.locfileid: "67396861"
---
# <a name="shifts-data-faq"></a>Preguntas más frecuentes sobre los datos de Turnos

Este artículo trata las preguntas más frecuentes sobre los datos de Turnos, incluido dónde se almacenan los datos de Turnos, la retención, la recuperación y el cifrado de datos.

## <a name="where-is-shifts-data-stored"></a>¿Dónde se almacenan los datos de Turnos?

Los datos de turnos se almacenan en una de las tres zonas geográficas: Asia Pacífico (APAC), la Unión Europea (UE) o la Estados Unidos. Cada geo almacena datos en al menos dos regiones de centros de datos de Azure para alta disponibilidad (HA) y recuperación ante desastres (DR). En la actualidad, la geo Estados Unidos/Norteamérica usa centros de datos en las Estados Unidos Norte Central y Central Sur. Para obtener más información, consulta [Dónde se almacenan los datos de clientes de Microsoft 365](/microsoft-365/enterprise/o365-data-locations).

Actualmente, Shifts ofrece residencia de datos en Australia, Canadá, Francia, Japón y el Reino Unido. Estamos trabajando activamente para ampliar la compatibilidad a más ubicaciones.

## <a name="can-i-choose-where-shifts-data-is-stored"></a>¿Puedo elegir dónde se almacenan los datos de Turnos?

Al configurar Teams por primera vez, elige un país o región, que se establece en el nivel de suscripción. Turnos respeta esta selección y usa la configuración regional y la región que se establece en Teams si se admite esa región. Si aún no estamos en esa región, almacenamos datos en una región cercana que admitimos. En el futuro, tenemos previsto migrar los datos existentes, si se almacenan en una región cercana, a la región aprovisionada en Teams.

## <a name="can-i-access-and-export-or-delete-a-users-personal-data-in-shifts"></a>¿Puedo acceder a los datos personales de un usuario y exportarlos o eliminarlos en Turnos?

Turnos cumple con el Reglamento general de protección de datos (RGPD). Una solicitud formal por parte de una persona (conocida como interesado) para realizar una acción sobre sus datos personales se denomina solicitud del interesado (DSR). Puede buscar datos personales y actuar en ellos en Turnos en respuesta a una DSR.

Puede usar la herramienta de exhibición de documentos electrónicos de búsqueda de contenido en la portal de cumplimiento Microsoft Purview para buscar y exportar datos de reloj de tiempo y programación a Excel. Para todos los demás datos de Turnos, puede realizar capturas de pantalla de los datos.

Para obtener más información, consulte [Office 365 solicitudes del interesado para el RGPD y la CCPA](/microsoft-365/compliance/gdpr-dsr-office365).

## <a name="what-happens-to-shifts-data-if-i-turn-off-shifts-for-my-organization"></a>¿Qué sucede con los datos de Turnos si desactivo turnos para mi organización?

Si desactiva Turnos en su organización *, no se* eliminarán los datos. Si desactiva Turnos y después activa Turnos, los datos de turnos seguirán estando disponibles.

Si elimina el inquilino, todos los datos de Turnos se eliminan cuando finaliza el período de retención.

No hay ninguna opción para eliminar solo los datos de Turnos. Si elimina un equipo en Teams, los turnos programan datos asociados a ese equipo se eliminan cuando termina el período de retención. Para obtener más información, consulta [Retención, eliminación y destrucción de datos en Microsoft 365](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview).

## <a name="can-i-recover-a-shifts-schedule-that-was-deleted"></a>¿Puedo recuperar una programación de Turnos que se eliminó?

Puede recuperar una programación eliminada si se restaura el grupo de Microsoft 365 que la respalda (o el equipo de Teams).

De forma predeterminada, un grupo eliminado de Microsoft 365 se conserva durante 30 días. Este período de 30 días se denomina "eliminación temporal" porque todavía puede restaurar el grupo. Para obtener más información, consulta [Restaurar un grupo de Microsoft 365 eliminado](/microsoft-365/admin/create-groups/restore-deleted-group?tabs=admin-center).

## <a name="can-i-use-custom-retention-policies-for-shifts-data"></a>¿Puedo usar directivas de retención personalizadas para los datos de Turnos?

Actualmente, Turnos no admite directivas de retención personalizadas.

Para obtener más información sobre las directivas de retención en Teams, vea [Obtener más información sobre la retención de Teams](/microsoft-365/compliance/retention-policies-teams) y [Administrar directivas de retención para Teams](../../retention-policies.md).

## <a name="can-i-retrieve-shifts-data-for-a-user-whose-license-was-revoked"></a>¿Puedo recuperar los datos de Turnos de un usuario cuya licencia se ha revocado?

Hoy en día, no ofrecemos la capacidad de recuperar datos de un usuario cuya licencia se ha revocado. Estamos trabajando para que esta funcionalidad sea algo en lo que estamos trabajando.

## <a name="what-type-of-encryption-does-shifts-use-for-data-at-rest-and-in-transit"></a>¿Qué tipo de cifrado usan los Turnos para los datos en reposo y en tránsito?

Azure Cosmos DB y Azure Storage cifran los datos de turnos en reposo. Para obtener más información, consulte [Cifrado de datos de Azure en reposo](/azure/security/fundamentals/encryption-atrest) y [Cifrado de datos en Azure Cosmos DB](/azure/cosmos-db/database-encryption-at-rest).

Turnos sigue las directrices de Microsoft 365 para el cifrado de datos en tránsito. Para obtener más información, consulte [Cifrado de datos en tránsito](/compliance/assurance/assurance-encryption-in-transit).

El cifrado de turnos de datos en reposo y en tránsito se verifica anualmente mediante la auditoría de cumplimiento de SOC2.

## <a name="can-i-access-immutable-copies-of-shifts-data"></a>¿Puedo acceder a copias inmutables de datos de Turnos?

No almacenamos copias inmutables de datos de Turnos. Por ejemplo, un administrador puede realizar cambios en una programación, como agregar notas, cambiar los tiempos de los turnos, asignar tareas, etc.

## <a name="can-shifts-data-be-edited"></a>¿Se pueden editar los datos de Turnos?

Hay ciertos aspectos de los turnos que no se pueden cambiar y determinados aspectos que se pueden cambiar. Por ejemplo, los detalles de los turnos, como las notas y los colores, se pueden editar de forma similar a cómo se pueden cambiar en la aplicación Turnos. Las solicitudes de turno no se pueden editar a menos que se retire la solicitud.

Para ver qué campos se han cambiado, puede buscar eventos de Turnos en el registro de auditoría de Microsoft 365. Para obtener más información sobre los eventos que se registran para las actividades de Turnos en el registro de auditoría de Microsoft 365, vea [Turnos en las actividades de Teams](../../audit-log-events.md#shifts-in-teams-activities).

## <a name="my-organization-uses-a-workforce-management-system-for-scheduling-can-we-integrate-with-and-access-shifts-data"></a>Mi organización usa un sistema de administración de la fuerza de trabajo para la programación. ¿Podemos integrar con datos de Turnos y acceder a ellos?

Las API de Shifts Graph le permiten integrar datos de Shifts con sistemas externos de administración de la fuerza de trabajo (WFM). Para obtener más información, consulte [Turnos API de Graph](/graph/api/resources/shift).

También ofrecemos conectores Turnos administrados. Con estos conectores, puede integrar su sistema de WFM directamente con Turnos. Para obtener más información sobre los conectores de Mayús y los sistemas de WFM [admitidos, vea Conectores de Turnos](/microsoft-365/frontline/shifts-connectors).

## <a name="can-shifts-data-be-deleted-permanently-after-a-specified-period-of-time"></a>¿Los datos de Turnos se pueden eliminar permanentemente después de un período de tiempo especificado?

Hoy en día, no eliminamos los datos de turnos. Con [las API de Shifts Graph](/graph/api/resources/shift), es posible [crear una aplicación con Power Apps](/powerapps/maker/) para conservar datos durante un período de tiempo especificado. Sin embargo, no se admite de forma nativa.

## <a name="can-shifts-data-be-moved-in-a-tenant-to-tenant-migration"></a>¿Se pueden mover los datos de Turnos en una migración de espacio empresarial a inquilino?

Los datos de turnos se pueden migrar de un inquilino a otro inquilino a petición específica. Tenga en cuenta que la migración de espacio empresarial a inquilino no se admite de forma rápida, pero se puede plantear como una solicitud de cliente.

## <a name="related-articles"></a>Artículos relacionados

- [Turnos para Teams](../shifts-for-teams-landing-page.md)
- [Administrar la aplicación Turnos](manage-the-shifts-app-for-your-organization-in-teams.md)
