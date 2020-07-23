---
title: Métodos recomendados y procedimientos recomendados para crear equipos de clase
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: lakuan
description: Obtenga información acerca de los métodos recomendados y los procedimientos recomendados para crear equipos de clase en su escuela.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 3e8b8e8605b5e4f916389109cb611996aa90a895
ms.sourcegitcommit: 34a30c2c9a8e32bfcb382c3e6e7237f277ec361d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/22/2020
ms.locfileid: "45206774"
---
# <a name="recommended-methods-and-best-practices-for-creating-class-teams"></a>Métodos recomendados y procedimientos recomendados para crear equipos de clase

Microsoft Teams para el ámbito educativo ofrece   [tipos de equipo específicos](https://support.office.com/article/choose-a-team-type-to-collaborate-in-microsoft-teams-0a971053-d640-4555-9fd7-f785c2b99e67)  de uso educativo. El [tipo de equipo de clase](https://support.office.com/article/create-a-class-team-in-microsoft-teams-fae422eb-58b7-4431-9ff2-a4b9b6ae7c5b) está diseñado para aulas y tiene características específicas que prestan apoyo a las necesidades del aula, como:  

- Tareas
- Notas
- Bloc de notas de clase de OneNote  
- [Carpeta de materiales de clase](https://support.office.com/article/Use-folders-to-create-read-only-files-for-students-or-other-team-members-0e7791d7-8c9c-4749-9bca-984289477988)  para proteger el contenido de solo lectura para los alumnos
- [Acceso anticipado para profesores](https://support.microsoft.com/article/activate-early-access-class-teams-created-with-school-data-sync-0d154696-66ab-4fcf-b22f-c3d9a82aaf78) para configurar la clase antes de agregar alumnos 
- Capacidad de silenciar a alumnos desobedientes y otros permisos especiales  

Hay varias maneras de crear equipos de clase. Teams para el ámbito educativo tiene un conjunto único de herramientas de implementación que facilitan su puesta en marcha. Repasaremos varias opciones para ayudarle a elegir la ruta de acceso de implementación adecuada que se ajuste mejor a sus necesidades.  

## <a name="automatic-team-creation-using-sds"></a>Creación automática de equipos con SDS

**Esta característica estará disponible próximamente a finales de julio de 2020.**

La automatización de la creación del equipo ahorra tiempo tanto de los administradores de TI como de los profesores. Asegura que los profesores tengan todos los equipos de clase creados y listos para la configuración tras iniciar sesión. [School Data Sync (SDS)](https://docs.microsoft.com/SchoolDataSync) es una herramienta gratuita de Office 365 Educación que lee los datos del sistema de registro de la institución educativa, como un sistema de información de estudiantes (SIS) o un sistema de administración del aprendizaje (LMS). SDS usa los datos para enriquecer la configuración de Office 365 de muchas maneras, como pueden ser crear equipos de clase de modo masivo y mantener la sincronización con el sistema de información para que las suscripciones de los profesores y los alumnos estén actualizadas a medida que cambia la inscripción. SDS puede importar datos desde cualquier sistema de registro y dispone de conectores integrados para muchos de los actuales [proveedores de SIS ](https://docs.microsoft.com/schooldatasync/what-sis-and-mis-vendors-does-school-data-sync-support) del mundo. Se recomienda encarecidamente usar SDS, ya que ofrece las siguientes ventajas.  

### <a name="benefits"></a>Ventajas

- Creación y mantenimiento automáticos de equipos de clase: los profesores podrán iniciar sesión en Teams y empezar a enseñar inmediatamente.
- Sincronización de la suscripción con SIS/LMS para guardar los cambios de suscripción de alumnos.
- Equipo de satisfacción del cliente educativo disponible para ayudar de forma gratuita con la implementación.
- [Acceso anticipado para profesores](https://support.office.com/article/activate-early-access-class-teams-created-with-school-data-sync-0d154696-66ab-4fcf-b22f-c3d9a82aaf78): los formadores tienen tiempo para preparar el equipo antes de que los alumnos lo usen.  
- De forma opcional, crea usuarios y adjudica licencias de Office 365.
- Crea grupos de seguridad que se usarán en Office 365, incluida la directiva de Teams.
- Crea unidades administrativas para la delegación administrativa limitada y el [restablecimiento de la contraseña del profesor](https://docs.microsoft.com/schooldatasync/how-to-enable-teacher-password-reset). 
- Control integrado de reintentos y errores, límite de interrupciones y estabilidad de la sesión para el procesamiento a gran escala a fin de reducir el trabajo de los administradores.  
- Capacidades integradas de limpieza para cambiar el nombre y archivar grupos y equipos cuando queden obsoletos.
- [Sincronización de calificaciones](https://docs.microsoft.com/schooldatasync/grade-sync): los profesores pueden completar todas las calificaciones en Teams y hacer que escriba de forma automática las calificaciones de Teams en el libro de calificaciones de SIS. 
- [Protección de datos de alumnos](https://docs.microsoft.com/schooldatasync/protecting-student-personal-data): evite que los alumnos usen aplicaciones ajenas a Microsoft y realice un seguimiento y administre el consentimiento parental. 
- Se usan datos importados para enriquecer la información educativa con roles de usuario, organizaciones (escuelas) y otros datos importantes.  

### <a name="considerations"></a>Consideraciones

SDS crea equipos en dos pasos. El primer paso consiste en crear un grupo de Microsoft 365 en Azure Active Directory (Azure AD); en el segundo paso, el grupo se convierte automáticamente en un equipo. El segundo paso de creación de equipos es opcional en SDS. Es posible que un administrador no quiera crear automáticamente equipos en función del tiempo de implementación y el número de equipos sin usar que puedan resultar. Se recomiendan que las instituciones con 500 000 equipos o más desactiven la creación automática de equipos en SDS y usen el [método de creación de equipos dirigida por el profesor](#teacher-led-team-creation-from-office-365-class-groups).  

### <a name="get-started"></a>Introducción

Para empezar, vaya a [School Data Sync (SDS)](https://docs.microsoft.com/SchoolDataSync) y contacte con asistencia de implementación [https://aka.ms/sdssupport](https://aka.ms/sdssupport).  

## <a name="teacher-led-team-creation-from-office-365-class-groups"></a>Creación de equipos dirigida por el profesor de grupos de clase de Office 365

**Esta característica estará disponible próximamente a mediados de agosto de 2020.**

La creación de equipos dirigida por el profesor es una buena opción de implementación si quiere que los profesores creen rápidamente las clases que necesitan. También recomendamos que las instituciones que tengan más de 500 000 equipos usen este método para minimizar el número de equipos creados de forma superflua.  

Esta estrategia híbrida le permite usar SDS para crear grupos para cada clase (recomendado) o usar la [API de Graph](https://docs.microsoft.com/graph/api/educationroot-post-classes) para crearlos por su cuenta. Una vez preparados los grupos de clases, los formadores pueden convertir los grupos en equipos mediante el icono de **clases sugeridas**.

:::image type="content" source="media/class-teams-edu-suggested-classes.png" alt-text="Captura de pantalla que muestra el icono de clases sugeridas":::

### <a name="benefits"></a>Ventajas

- [Acceso anticipado para profesores](https://support.office.com/article/activate-early-access-class-teams-created-with-school-data-sync-0d154696-66ab-4fcf-b22f-c3d9a82aaf78): los formadores tienen tiempo para preparar el equipo antes de que los alumnos lo usen.  
- Reduce el número de equipos sin usar e innecesarios. Las clases se preparan y sugieren, pero no se crean, a menos que el profesor tenga intención de usarlas. Se recomienda esta opción para grandes instituciones que tienen más de 500 000 equipos con objeto de reducir el desorden.
- SDS
    - Sincronización de la suscripción con SIS/LMS para guardar los cambios de suscripción de alumnos.
    - Equipo de satisfacción del cliente educativo disponible para ayudar de forma gratuita con la implementación.
    - De forma opcional, crea usuarios y adjudica licencias de Office 365.
    - Crea grupos de seguridad que se usarán en Office 365, incluida la directiva de Teams.
    - Crea unidades administrativas para la delegación administrativa limitada y el [restablecimiento de la contraseña del profesor](https://docs.microsoft.com/schooldatasync/how-to-enable-teacher-password-reset).
    - Control integrado de reintentos y errores, límite de interrupciones y estabilidad de la sesión para el procesamiento a gran escala a fin de reducir el trabajo de los administradores. 
    - Capacidades integradas de limpieza para cambiar el nombre y archivar grupos y equipos cuando queden obsoletos. 
    - [Sincronización de calificaciones](https://docs.microsoft.com/schooldatasync/grade-sync): los profesores pueden completar todas las calificaciones en Teams y hacer que escriba de forma automática las calificaciones de Teams en el libro de calificaciones de SIS. 
    - [Protección de datos de alumnos](https://docs.microsoft.com/schooldatasync/protecting-student-personal-data): evite que los alumnos usen aplicaciones ajenas a Microsoft y realice un seguimiento y administre el consentimiento parental. 
    - Se usan datos importados para enriquecer la información educativa con roles de usuario, organizaciones (escuelas) y otros datos importantes.
- API de Graph
    - Mayor flexibilidad y control.
    - No requiere integración con SDS.

### <a name="considerations"></a>Consideraciones

- No es completamente automática y requiere algunas acciones de los profesores.
- Los profesores que no tienen permiso para crear equipos aún podrán crear equipos a partir de grupos existentes, tal y como se muestra [aquí](https://support.office.com/article/create-a-class-team-in-microsoft-teams-preview-fae422eb-58b7-4431-9ff2-a4b9b6ae7c5b).
- La API de Graph requiere un alto nivel de conocimiento técnico y tiempo para crear y ejecutar el script y solucionar los problemas al crear grupos de clase.

### <a name="get-started"></a>Introducción

Para empezar con el método SDS, vaya a [School Data Sync (SDS)](https://docs.microsoft.com/SchoolDataSync) y contacte con asistencia de implementación [https://aka.ms/sdssupport](https://aka.ms/sdssupport). 

Para usar el método de la API de Graph, consulte [API de Graph](https://docs.microsoft.com/graph/api/educationroot-post-classes?view=graph-rest-1.0&tabs=http) y [Crear un equipo de clase](https://docs.microsoft.com/graph/api/educationroot-post-classes?view=graph-rest-beta&tabs=http).  

> [!NOTE]
> Para usar este método con SDS, tendrá que desactivar la opción de creación automática de equipos en su perfil de SDS. También puede usar una combinación de creación de equipos automática y dirigida por el profesor para los equipos de clase necesarios y opcionales mediante dos perfiles de SDS.

## <a name="powershell-script-using-graph-apis"></a>Script de PowerShell con la API de Graph

Con PowerShell, puede escribir un script para crear equipos, canales y configurar opciones automáticamente. Para ello, el administrador debe crear el grupo en primer lugar, agregar profesores y alumnos y, a continuación, crear el equipo como se indica [aquí](https://docs.microsoft.com/graph/teams-create-group-and-team). También puede usar la API de Microsoft Graph para crear, configurar, clonar y archivar equipos. Para obtener más información, consulte [Usar la API de Microsoft Graph para trabajar con Microsoft Teams](https://developer.microsoft.com/graph/docs/api-reference/beta/resources/teams_api_overview), [PowerShell de Microsoft Teams](https://docs.microsoft.com/powershell/module/teams) y [Crear un equipo de clase](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta&tabs=http#example-6-create-a-team-with-a-non-standard-base-template-type). El uso de las API de Graph es una buena forma de obtener más control y flexibilidad, sin embargo, exige un alto nivel de conocimientos técnicos y más tiempo para la configuración inicial.  

### <a name="benefits"></a>Ventajas

- Mayor flexibilidad y control.
- Opción de crear equipos con acceso anticipado para profesores o acceso inmediato de los alumnos a los equipos.  
- Si [crea equipos a partir de grupos](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta&tabs=http#example-4-create-a-team-from-group), los profesores tendrán acceso anticipado y se sincronizarán los cambios en las suscripciones de los alumnos para el grupo de Azure AD.

### <a name="considerations"></a>Consideraciones

- Requiere un alto nivel de conocimiento técnico y tiempo para crear y ejecutar el script y solucionar los problemas al crear grupos de clase.
- Sin control integrado de errores ni lógica de reintentos.
- Los cambios de suscripción no se sincronizan con SIS. 

> [!NOTE]
> Los equipos de clase requieren suscripción al grupo oculta para que solo los profesores y los alumnos de la clase pueden ver a los miembros de esa clase. Para crear un grupo de clase de Office 365, consulte [Crear un equipo de clase](https://docs.microsoft.com/graph/api/educationroot-post-classes?view=graph-rest-beta&tabs=http) para cumplir los mismos requisitos de privacidad.

## <a name="manual-team-creation"></a>Creación de equipos manual

Los alumnos y los formadores podrán sacar el máximo partido a Teams cuando puedan usarlo con barreras mínimas y dispongan de la flexibilidad para adaptarlo a sus necesidades. Una forma en que los usuarios pueden adaptar su experiencia de Teams consiste en contar con la capacidad de crear equipos. Los formadores configuran su propio equipo de clase e invitan a alumnos como se muestra [aquí](https://support.microsoft.com/article/create-a-class-team-in-microsoft-teams-fae422eb-58b7-4431-9ff2-a4b9b6ae7c5b#ID0EADAAA=Create_a_team_from_scratch). Los formadores pueden invitar a los alumnos[agregando alumnos al equipo](https://support.office.com/article/add-a-student-to-a-class-team-b88263bb-ace1-4702-8a48-f8a2cf4af954), [compartiendo un código de unión](https://support.office.com/article/Create-a-link-or-a-code-for-joining-a-team-11b0de3b-9288-4cb4-bc49-795e7028296f) o [compartiendo un vínculo al equipo](https://support.office.com/article/Create-a-link-or-a-code-for-joining-a-team-11b0de3b-9288-4cb4-bc49-795e7028296f). Si es posible, es mejor que los formadores agreguen a los alumnos al equipo para asegurarse de que los alumnos obtengan acceso y se les notifique que se les ha agregado a un equipo.

### <a name="benefits"></a>Ventajas

- Mayor flexibilidad y control para los profesores.
- Creación y acceso inmediato al equipo.  

### <a name="considerations"></a>Consideraciones

- Requiere acciones y tiempo del profesor.
- La suscripción de alumnos no se sincroniza con SIS y requiere administración manual.
- No proporciona a los profesores acceso anticipado a los equipos. Los alumnos obtendrán acceso inmediato.

## <a name="recommended-best-practices"></a>Procedimientos recomendados

- Implementación anticipada. Implementación anticipada para asegurarse de que todo funciona de forma segura y está listo el primer día de clase. Si usa SDS, no es necesario que tenga la suscripción completa de alumnos para poder iniciar la implementación de SDS. Sincronizará a los alumnos cuando esa información esté disponible en su SIS.
- Si tiene más de 500 000 equipos, le recomendamos que use el [método de creación de equipos dirigida por el profesor](#teacher-led-team-creation-from-office-365-class-groups). Reduce la cantidad de equipos sin usar y el desorden pues solo crea equipos relevantes y necesarios.  
- Si hay algún problema (por ejemplo, faltan clases) con la creación automática de equipos de SDS y los profesores los necesitan de forma inmediata, es posible usar el [método de creación de equipos dirigida por el profesor](#teacher-led-team-creation-from-office-365-class-groups) para intentarlo de nuevo. La [creación manual de equipos](#manual-team-creation) es otra solución, pero no actualizará la suscripción del equipo.  
- El límite de equipos del espacio empresarial es 500 000 equipos. Por lo tanto, los administradores deben intentar reducir el número de equipos sin usar de manera proactiva para evitar alcanzar esos límites y que se prolongue el tiempo de configuración. Para obtener más información sobre los límites, consulte [Límites y especificaciones de Microsoft Teams](limits-specifications-teams.md).  
