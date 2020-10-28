---
title: 'Auditar la aplicación de pacientes para los administradores de ti y cumplimiento de los equipos '
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
description: Obtener información sobre cómo auditar la aplicación para pacientes para administradores de equipos
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 042d3308e70f2b6275360dfd0137bdc9ed94b7c8
ms.sourcegitcommit: 18b5e3487ba1350c5d2e6d676a4ab582b5b638d4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "48772281"
---
# <a name="audit-logs-for-patients-app"></a>Registros de auditoría de la aplicación Pacientes

> [!NOTE]
> Desde el 30 de octubre de 2020, la aplicación de pacientes se ha retirado y se ha sustituido por la [aplicación listas](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) en Teams. Con las listas, los equipos de cuidados de la organización de la salud pueden crear listas de pacientes para escenarios que abarcan desde rondas y reuniones interdisciplinarias hasta supervisión general de pacientes. Consulte la plantilla patients en listas para comenzar. Para obtener más información sobre cómo administrar la aplicación listas de su organización, vea [administrar la aplicación listas](../../manage-lists-app.md).

Un registro de auditoría para la actividad de la aplicación pacientes permite a los equipos de respuesta tras incidente revisar los cambios realizados en los registros médicos electrónicos (EMR) o la información sanitaria de pacientes (PHI) del paciente y determinar si necesitan cambios o mejoras en la política o el procedimiento para el acceso a la PHI en herramientas de productividad. Los eventos de registro de auditoría cubren las acciones que se realizan a través de la interfaz de usuario de la aplicación pacientes.

## <a name="meet-hipaa-requirements"></a>Cumplir con los requisitos de HIPAA

Según las normas de HIPAA, los proveedores de asistencia sanitaria deben mantener registros de todo el acceso a la PHI, de modo que sea posible auditar los cambios. Microsoft se compromete a los clientes empresariales que usan Microsoft Teams y les ayuda a cumplir con los requisitos y controles de HIPAA. El acceso a la PHI a través de la aplicación de pacientes está completamente registrado y los registros están disponibles en el centro de cumplimiento de Microsoft 365, según se describe en el artículo [funcionalidad de búsqueda de registro de auditoría](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance) .

> [!IMPORTANT]
> La responsabilidad de mantener la privacidad del paciente se coloca en el proveedor de asistencia sanitaria por ley. La ley da derecho a la privacidad de pacientes y requiere que el administrador de ti o el controlador HIPAA pueda determinar fácilmente qué enfermera, médico o trabajador social ha acaquí o modificado registros de pacientes. Uno de los ejemplos más comunes de infracción de acceso a la PHI es el acceso a los pacientes VIP. La funcionalidad de registro de auditoría es necesaria para realizar investigaciones de cualquier violación de acceso de PHI y para cumplir con los requisitos de HIPAA.

<!-- add an image from the security and compliance center audit log search page showing an event, Ansuman please let me know whether we need to copy an existing screen shot (and which one) or grab a new one -->

## <a name="enable-audit-logs-for-the-patients-app"></a>Habilitar registros de auditoría para la aplicación de pacientes

Una auditoría depende de varias configuraciones anteriores:

1. El administrador tendría que trabajar con su proveedor de servicios de FHIR para tener EMR en un formato usado por la aplicación de pacientes. Consulte [integración de registros de asistencia electrónica en Microsoft Teams](patients-app.md).
2. Un administrador de proveedores de asistencia médica tendría que habilitar la aplicación de pacientes en el centro de administración de Teams. Para obtener más información, vea [Administrar directivas de configuración de aplicaciones en Microsoft Teams](../../teams-app-setup-policies.md) y artículos relacionados.
3. El administrador tendría que habilitar las auditorías de actividades, de la misma forma en que habilitan cualquier auditoría del registro de actividades, como se describe en [antes de comenzar](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance#before-you-begin) y [activar o desactivar la búsqueda de registros de auditoría](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off#turn-on-audit-log-search). Si el registro de auditoría ya está activado, no se necesita nada especial para la aplicación de pacientes. Cada vez que un proveedor de cuidado de la salud instala y ejecuta la aplicación dentro de un equipo, los registros de auditoría graban su actividad de PHI.
4. El administrador tendría que anunciar la disponibilidad de la aplicación de pacientes, y los trabajadores de la asistencia sanitaria tendrían que empezar a generar actividad para que se incluyera en una auditoría.

<!-- add link out to client doc when available -->

## <a name="run-an-audit"></a>Ejecutar una auditoría

Para obtener instrucciones sobre cómo ejecutar una búsqueda en el registro de actividades, consulte [Buscar en el registro de auditoría](https://docs.microsoft.com/office365/securitycompliance/search-the-audit-log-in-security-and-compliance#search-the-audit-log).

## <a name="logged-activities-for-patients-app"></a>Actividades registradas para la aplicación pacientes

La aplicación de pacientes tiene sus propias actividades registradas, que se enumeran en la tabla siguiente:

|Nombre descriptivo |Operación|Descripción|
|:---|:---|:---|
| Lista de pacientes visitada | PatientListView | Un usuario vio una lista de pacientes.|
| Lista eliminada de pacientes | PatientListDelete | Un usuario ha eliminado una lista de pacientes.|
| Se agregó a la lista de pacientes | PatientListAddPatient | Se agregó un paciente a una lista de pacientes. |
| Se ha agregado una nota para el paciente | PatientNoteAdd | Se agregó una nota al registro del paciente. |
| Esquema de pacientes creado | PatientSchemaCreate | Se creó un conjunto de columnas usadas en el registro del paciente. |
| El usuario inició una exportación | ExportInitiation | Los datos del paciente se exportaron desde la aplicación de pacientes a un archivo de Excel. El archivo se guardará en el sitio de SharePoint de grupo. |
| Lista de pacientes creados | PatientListCreate | Un usuario creó una lista de pacientes.|
| Establecer lista predeterminada de pacientes| PatientListDefaultSet| Un usuario define una lista determinada como la lista predeterminada.|
| Se ha quitado al paciente de la lista| PatientListRemovePatient | Se ha eliminado un paciente de una lista de pacientes. |
| Paciente buscado | PatientSearch | Buscó un registro del paciente en el servicio HCI. |
| Esquema del paciente actualizado | PatientSchemaUpdate  | Se ha actualizado un conjunto existente de columnas que se usan en el registro del paciente. |<!-- | Ha movido el paciente a una lista diferente| PatientMoved | El registro del paciente se movió de una lista a otra. |-->
| Lista de pacientes con el nombre cambiado | PatientListRename | Se cambió el nombre de una lista de pacientes. |
| Columnas modificadas en la lista de pacientes | PatientListEditColumns | Se editó una columna en una lista de pacientes (agregada o eliminada). |
| Detalles de pacientes vistos | PatientView | Un usuario vio un registro de paciente.|
| Detalles de pacientes editados | PatientDetailsEdit | Se modificó un detalle en un registro de paciente. |
| Establecer conexión de HCI | EHRConnectionSet | Establece la dirección URL que se usa para conectar con la conexión de servicio FHIR de EHR. Ejemplo: https://<span>API-V8-dstu2.hspconsortium.org/ContosoHospital/Open</span>  |
||||

Puede personalizar la auditoría según sea necesario para buscar o filtrar en cualquiera de estas actividades registradas.

Las actividades registradas de Microsoft Teams en general se describen en [actividades de Microsoft Teams](https://docs.microsoft.com/office365/securitycompliance/search-the-audit-log-in-security-and-compliance#microsoft-teams-activities).

## <a name="related-topics"></a>Temas relacionados

[Buscar en el registro de auditoría](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)

[Integración de registros sanitarios electrónicos en Microsoft Teams](patients-app.md)
