---
title: 'Aplicación De auditoría de pacientes para administradores de TI y cumplimiento de Teams '
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
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
ms.reviewer: anach
description: Obtener información sobre cómo auditar la aplicación Pacientes para administradores de Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 3cf850b8ae7312fa6c43f879baefb617f48d30b3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096194"
---
# <a name="audit-logs-for-patients-app"></a>Registros de auditoría de la aplicación Pacientes

> [!NOTE]
> Desde el 30 de octubre de 2020, la aplicación Pacientes se retiró y se reemplazó por la aplicación [Listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) en Teams. Los datos de la aplicación Pacientes se almacenan en el buzón de correo del grupo de Office 365 que respalda al equipo. Todos los datos asociados con la aplicación Pacientes se conservan en este grupo, pero ya no se puede acceder a ellos a través de la interfaz de usuario. Los usuarios pueden volver a crear sus listas mediante la [aplicación Listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).
>
>Con Listas, los equipos del cuidado de la salud de su organización sanitaria pueden crear listas de pacientes para escenarios que van desde guardias y reuniones interdisciplinarias de equipo, hasta el seguimiento general de pacientes. Consulte la plantilla Pacientes en Listas para comenzar. Para obtener más información sobre cómo administrar la aplicación Listas en su organización, consulte [Administrar la aplicación Listas](../../manage-lists-app.md).

Un registro de auditoría para la actividad de la aplicación Pacientes permite a los equipos de respuesta después del incidente revisar los cambios en los registros médicos electrónicos (EMR) o en la información de salud del paciente (PHI) de un paciente y determinar si se necesitan cambios o mejoras en la directiva o el procedimiento para el acceso a PHI en las herramientas de productividad. Los eventos del registro de auditoría abarcan las acciones realizadas a través de la interfaz de usuario de la aplicación Pacientes.

## <a name="meet-hipaa-requirements"></a>Cumplir los requisitos de HIPAA

De acuerdo con las directrices de HIPAA, los proveedores de servicios de salud deben mantener registros de todo el acceso a la PHI, de modo que los cambios se puedan auditar. Microsoft está comprometido con sus clientes empresariales que usan Microsoft Teams y para ayudarles a cumplir los requisitos y controles hipaa. Se realiza un seguimiento completo del acceso a la PHI a través de la aplicación Pacientes y los registros están disponibles en el Centro de cumplimiento de Microsoft 365, tal y como se describe en el artículo de funcionalidad Búsqueda de registros [de](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance) auditoría.

> [!IMPORTANT]
> La carga de mantener la privacidad de los pacientes se coloca en el proveedor de atención sanitaria por ley. La ley da derecho a los pacientes a la privacidad y requiere que un administrador de TI o un controlador HIPAA puedan determinar fácilmente a qué enfermera, médico o trabajador social se les ha accedido o modificado los registros de pacientes. Uno de los ejemplos más comunes de una infracción de acceso a LA PHI es el acceso a los pacientes VIP. La funcionalidad del registro de auditoría es necesaria para llevar a cabo investigaciones de cualquier infracción de acceso a PHI y para cumplir los requisitos hipaa.

<!-- add an image from the security and compliance center audit log search page showing an event, Ansuman please let me know whether we need to copy an existing screen shot (and which one) or grab a new one -->

## <a name="enable-audit-logs-for-the-patients-app"></a>Habilitar registros de auditoría para la aplicación Pacientes

Una auditoría depende de varias configuraciones anteriores:

1. El administrador tendría que trabajar con su proveedor de servicios FHIR para tener EL.A.C. en un formato usado por la aplicación Pacientes. Consulte [Integración de registros electrónicos de atención sanitaria en Microsoft Teams.](patients-app.md)
2. Un administrador del proveedor de atención sanitaria tendría que habilitar la aplicación de pacientes en el Centro de administración de Teams. Vea [Administrar directivas de configuración de aplicaciones en Microsoft Teams](../../teams-app-setup-policies.md) y artículos relacionados para obtener más información.
3. El administrador tendría que habilitar las auditorías de actividad, del mismo [](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance#before-you-begin) modo que habilitan cualquier auditoría de registro de actividades, como se describe en Antes de empezar y activar o desactivar la búsqueda del registro [de auditoría.](/office365/securitycompliance/turn-audit-log-search-on-or-off#turn-on-audit-log-search) Si el registro de auditoría ya está habilitado, no se necesita nada especial para la aplicación Pacientes. Cada vez que un proveedor de atención sanitaria instala y ejecuta la aplicación dentro de un equipo, los registros de auditoría registran su actividad de PHI.
4. A continuación, el administrador tendría que anunciar la disponibilidad de la aplicación Pacientes y los trabajadores sanitarios tendrían que empezar a generar actividad para incluirla en una auditoría.

<!-- add link out to client doc when available -->

## <a name="run-an-audit"></a>Ejecutar una auditoría

Para obtener instrucciones sobre cómo ejecutar una búsqueda del registro de actividades, vea [Buscar en el registro de auditoría.](/office365/securitycompliance/search-the-audit-log-in-security-and-compliance#search-the-audit-log)

## <a name="logged-activities-for-patients-app"></a>Actividades registradas para la aplicación Pacientes

La aplicación Pacientes tiene sus propias actividades registradas, enumeradas en la tabla siguiente:

|Nombre descriptivo |Operación|Descripción|
|:---|:---|:---|
| Lista de pacientes vistas | PatientListView | Un usuario ha visto una lista de pacientes.|
| Lista de pacientes eliminados | PatientListDelete | Un usuario eliminó una lista de pacientes.|
| Se ha agregado paciente a la lista | PatientListAddPatient | Se agregó un paciente a una lista de pacientes. |
| Nota agregada para el paciente | PatientNoteAdd | Se agregó una nota a un registro de pacientes. |
| Esquema de paciente creado | PatientSchemaCreate | Se creó un conjunto de columnas usadas en el registro de pacientes. |
| El usuario inició una exportación | ExportInitiation | Los datos del paciente se exportaron desde la aplicación Pacientes a un archivo de Excel. El archivo se guardará en el sitio de sharepoint de grupo. |
| Lista de pacientes creada | PatientListCreate | Un usuario creó una lista de pacientes.|
| Establecer la lista de pacientes predeterminada| PatientListDefaultSet| Un usuario establece una lista determinada como lista predeterminada.|
| Eliminado el paciente de la lista| PatientListRemovePatient | Se quitó un paciente de una lista de pacientes. |
| Paciente buscado | PatientSearch | Se ha buscado un registro de pacientes en el servicio de EHR. |
| Esquema de paciente actualizado | PatientSchemaUpdate  | Se ha actualizado un conjunto de columnas existente que se usa en el registro de pacientes. |<!-- | Mover paciente a una lista diferente| PatientMoved | El registro del paciente se movió de una lista a otra. |-->
| Lista de pacientes con nombre cambiado | PatientListRename | Se cambió el nombre de una lista de pacientes. |
| Columnas editadas en la lista de pacientes | PatientListEditColumns | Se ha editado una columna de una lista de pacientes (se ha agregado o quitado). |
| Detalles del paciente vistos | PatientView | Un usuario ha visto un registro de paciente.|
| Detalles del paciente modificados | PatientDetailsEdit | Se ha editado un detalle de un registro de pacientes. |
| Establecer la conexión EHR | EHRConnectionSet | Establezca la dirección URL que se usa para conectarse a la conexión del servicio FHIR de EHR. Ejemplo: https://<span>api-v8-dstu2.hspconsortium.org/ContosoHospital/open</span>  |
||||

Puede personalizar la auditoría según sea necesario para buscar o filtrar cualquiera de estas actividades registradas.

Las actividades registradas para Microsoft Teams en general se describen en [actividades de Microsoft Teams.](/office365/securitycompliance/search-the-audit-log-in-security-and-compliance#microsoft-teams-activities)

## <a name="related-topics"></a>Temas relacionados

[Buscar en el registro de auditoría](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)

[Integración de los registros sanitarios electrónicos en Microsoft Teams](patients-app.md)