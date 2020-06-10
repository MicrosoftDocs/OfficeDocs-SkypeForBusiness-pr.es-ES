---
title: Administrar paquetes de directivas en Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: sekrantz, aaglick
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.policypackages.overview
- seo-marvel-apr2020
localization_priority: Normal
search.appverid: MET150
description: Aprenda a usar y administrar paquetes de directivas en Microsoft Teams para simplificar, simplificar y ayudar a proporcionar coherencia al administrar directivas para grupos de usuarios.
ms.openlocfilehash: 0fc612f4f04e0a57176ac985b40de029d42c5e9e
ms.sourcegitcommit: f586d2765195dbd5b7cf65615a03a1cb098c5466
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "44669417"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a>Administrar paquetes de directivas en Microsoft Teams

Un paquete de directivas de Microsoft Teams es una colección de directivas y opciones de directiva predefinidas que puede asignar a los usuarios que tienen roles similares en su organización. Hemos creado paquetes de directivas para simplificar, simplificar y ayudar a proporcionar coherencia al administrar directivas para grupos de usuarios de toda la organización.  

Cuando se asigna un paquete de directivas a los usuarios, se crean las directivas del paquete y, después, se puede personalizar la configuración de las directivas en el paquete para satisfacer las necesidades de la organización.

Los paquetes de directivas no están disponibles para organizaciones de la comunidad de la nube de Estados Unidos (GCC).

## <a name="what-is-a-policy-package"></a>¿Qué es un paquete de directivas?

Los paquetes de directivas le permiten controlar las características de teams que desea permitir o restringir a conjuntos de personas específicas de su organización. Cada paquete de directivas de Teams está diseñado según un rol de usuario e incluye directivas predefinidas y opciones de directiva que admiten las actividades de colaboración y comunicación típicas de ese rol.

Actualmente, Teams incluye los siguientes paquetes de directivas.

|**Nombre del paquete**  |**Descripción** |
|---------|---------|
|Educación (estudiante de educación superior)    |Crea un conjunto de directivas y opciones de directiva que se aplican a estudiantes de educación superior.|
|Educación (estudiante principal de la escuela)   |Crea un conjunto de directivas y opciones de directiva que se aplican a los alumnos principales.|
|Educación (estudiante secundario de la escuela)    |Crea un conjunto de directivas y opciones de directiva que se aplican a los alumnos secundarios.         |
|Educación (profesor)    |Crea un conjunto de directivas y configuraciones de directivas que se aplican a los profesores.      |
|Educación (principal profesor principal con aprendizaje remoto)    |Crea un conjunto de directivas que se aplican a los profesores de primaria para maximizar la seguridad y colaboración de los alumnos al usar la formación remota.      |
|Educación (estudiante principal de la escuela con aprendizaje remoto)    |Crea un conjunto de directivas que se aplican a los alumnos de primaria para maximizar la seguridad y colaboración de los alumnos al usar la formación remota.      |
|Trabajador clínico de sanidad  |Crea un conjunto de directivas y configuraciones de directivas que proporcionan a los trabajadores clínicos como enfermeras registradas, enfermeras, médicos y trabajadores sociales acceso completo a chats, llamadas, administración de turnos y reuniones. |
|Trabajador de información de asistencia sanitaria  |Crea un conjunto de directivas y opciones de directiva que ofrecen a trabajadores de la información como personal de ti, personal de informática, personal de finanzas y funcionarios de cumplimiento, acceso completo a chats, llamadas y reuniones.|
|Sala de pacientes sanitarios  |Crea un conjunto de directivas y parámetros de directivas que se aplican a las salas de pacientes de su organización de salud.|
|Usuarios de pequeñas y medianas empresas (voz empresarial) |Crea una directiva de configuración de aplicaciones que incluye las aplicaciones para una experiencia de voz de empresa.|
|Usuarios de pequeñas y medianas empresas (sin voz empresarial) |Crea una directiva de configuración de aplicaciones relevante para los usuarios de equipos empresariales pequeños y de tamaño mediano (experiencia de voz no empresarial).
|Funcionario de seguridad pública   |Crea un conjunto de directivas y parámetros de directivas que se aplican a los directores de seguridad pública de su organización.|

> [!NOTE]
> Agregaremos más paquetes de directivas en versiones futuras de Teams, así que vuelve a consultar la información más actualizada.  

A cada directiva individual se le da el nombre del paquete de directivas para que pueda identificar fácilmente las directivas vinculadas a un paquete de directivas.
Por ejemplo, al asignar el paquete de directivas Educación (profesor) a los profesores de su escuela, se crea una directiva denominada Education_Teacher para cada Directiva del paquete.

![Captura de pantalla del paquete de directivas Educación (profesor)](media/policy-packages-education_teacher.png)

## <a name="how-to-use-policy-packages"></a>Cómo usar paquetes de directivas

A continuación se describe cómo usar paquetes de directivas en su organización.

![Información general sobre cómo usar paquetes de directivas](media/manage-policy-packages-overview.png)

- **[Ver](#view-the-settings-of-a-policy-in-a-policy-package)**: ver la configuración de cada directiva en un paquete de directivas antes de asignar un paquete. Asegúrese de comprender cada configuración y, a continuación, decida si los valores predefinidos son adecuados para su organización o si necesita cambiarlos de forma más restrictiva o flexible según las necesidades de su organización.

    Si se elimina una directiva, puede seguir viendo la configuración, pero no podrá cambiar la configuración. Una directiva eliminada se vuelve a crear con la configuración predefinida al asignar el paquete de directivas.

- **[Asignar](#assign-a-policy-package)**: asignar el paquete de directivas a los usuarios. Recuerde que las directivas de un paquete de directivas no se crean hasta que usted asigne el paquete, después de que puede cambiar la configuración de directivas individuales en el paquete.  

- **[Personalizar](#customize-policies-in-a-policy-package)**: personalizar la configuración de directivas en el paquete de directivas para satisfacer las necesidades de su organización. Los cambios que realice en la configuración de la Directiva se aplican automáticamente a los usuarios que tienen asignado el paquete.

Estos son los pasos para ver, asignar y personalizar paquetes de directivas en el centro de administración de Microsoft Teams.

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a>Ver la configuración de una directiva en un paquete de directivas

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, haga clic en **paquetes de directivas**y, a continuación, seleccione un paquete de directivas haciendo clic a la izquierda del nombre del paquete.
2. Haga clic en la Directiva que desea ver.

### <a name="assign-a-policy-package"></a>Asignar un paquete de directivas

#### <a name="assign-a-policy-package-to-one-user"></a>Asignar un paquete de directivas a un usuario

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Usuarios** y, después, haga clic en el usuario.
2. En la página del usuario, haga clic en **directivas**y, a continuación, junto a **paquete de directivas**, haga clic en **Editar**.
3. En el panel **asignar paquete de directivas** , seleccione el paquete que desea asignar y, a continuación, haga clic en **Guardar**.

#### <a name="assign-a-policy-package-to-multiple-users"></a>Asignar un paquete de directivas a varios usuarios

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **paquetes de directivas**y, a continuación, seleccione el paquete de directivas que desea asignar haciendo clic a la izquierda del nombre del paquete.
2. Haga clic en **administrar usuarios**.
3. En el panel **Administrar usuarios**, busque el usuario por nombre para mostrar o por nombre de usuario, seleccione el nombre y, después, haga clic en **Agregar**. Repita este paso por cada usuario que quiera agregar.
4. Cuando haya terminado de agregar usuarios, haga clic en **Guardar**.

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a>Asignar un paquete de directivas a un conjunto grande (lote) de usuarios

Use la asignación de paquetes de directivas por lotes para asignar un paquete de directivas a grandes conjuntos de usuarios a la vez. Use el cmdlet [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) para enviar un lote de usuarios y el paquete de directivas que desea asignar. Las asignaciones se procesan como una operación en segundo plano y se genera un identificador de operación para cada lote.

Un lote puede contener hasta 5.000 usuarios. Puede especificar los usuarios por su identificador de objeto, UPN, dirección SIP o dirección de correo electrónico. Para obtener más información, consulte [asignar un paquete de directivas a un lote de usuarios](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).

### <a name="customize-policies-in-a-policy-package"></a>Personalizar directivas en un paquete de directivas

Puede editar la configuración de una directiva a través de la página **paquetes de directivas** o yendo directamente a la página de directivas en el centro de administración de Microsoft Teams.

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, siga uno de estos procedimientos:
    - Haga clic en **paquetes de directivas**y, a continuación, seleccione el paquete de directivas haciendo clic a la izquierda del nombre del paquete.
    - Haga clic en el tipo de directiva.  Por ejemplo, haga clic en **directivas de mensajería**.
2. Haga clic en la Directiva que desea editar. Las directivas vinculadas a un paquete de directivas tienen el mismo nombre que el paquete de directivas.
3. Realice los cambios que desee y, a continuación, haga clic en **Guardar**.

## <a name="troubleshooting"></a>Solución de problemas

**Recibe un error cuando asigna un paquete de directivas**

Esto puede ocurrir si una o más directivas del paquete no se han creado o aplicado correctamente. Reasigne el paquete de directivas a los usuarios. El reintento de la operación normalmente soluciona este problema.

## <a name="related-topics"></a>Temas relacionados

[Paquetes de directivas de Microsoft Teams para administradores de EDU](policy-packages-edu.md)
