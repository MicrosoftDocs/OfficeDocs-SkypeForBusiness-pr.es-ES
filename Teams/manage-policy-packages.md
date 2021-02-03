---
title: Administrar paquetes de directivas en Microsoft Teams
author: cichur
ms.author: v-cichur
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
description: Obtenga información sobre cómo usar y administrar paquetes de directivas en Microsoft Teams para simplificar, simplificar y ayudar a proporcionar coherencia a la hora de administrar directivas para grupos de usuarios.
ms.openlocfilehash: 395b0f2c05278224bf024c1cf3e453a2f51bd725
ms.sourcegitcommit: de7d0807186a64dfe1cca15d34c39bdbad6af836
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2021
ms.locfileid: "50085183"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a>Administrar paquetes de directivas en Microsoft Teams

> [!NOTE]
> Una de las características analizadas en este artículo, los [paquetes](#custom-policy-packages)de directivas personalizadas, está actualmente en versión preliminar privada.

Un paquete de directivas en Microsoft Teams es una colección de directivas predefinidas y configuraciones de directiva que puede asignar a los usuarios que tienen roles similares en su organización. Hemos creado paquetes de directiva para simplificar, simplificar y ayudar a proporcionar coherencia a la hora de administrar directivas para grupos de usuarios de toda la organización.  

Puede usar los [paquetes de directiva incluidos en Teams](#policy-packages-included-in-teams) o crear [sus propios paquetes](#custom-policy-packages) de directiva personalizados (en versión preliminar privada).

:::image type="content" source="media/policy-packages-admin-center.png" alt-text="Captura de pantalla de la página Paquetes de directiva en el centro de administración":::

Puede personalizar la configuración de las directivas de un paquete de directivas para adaptarla a las necesidades de los usuarios. Al cambiar la configuración de directivas en un paquete, todos los usuarios asignados a ese paquete obtienen la configuración actualizada. Puede administrar paquetes de directivas mediante el Centro de administración de Microsoft Teams o PowerShell.

## <a name="what-is-a-policy-package"></a>¿Qué es un paquete de directivas?

Los paquetes de directiva le permiten controlar las características de Teams que quiere permitir o restringir para determinados conjuntos de usuarios en toda la organización. Cada paquete de directiva en Teams está diseñado en torno a un rol de usuario e incluye directivas predefinidas y configuraciones de directiva que admiten las actividades de colaboración y comunicación típicas para ese rol.

Los paquetes de directiva admiten los siguientes tipos de directiva de Teams:

- Directiva de mensajería
- Directiva de reuniones
- Directiva de configuración de aplicaciones
- Directiva de llamadas
- Directiva de eventos en directo

## <a name="policy-packages-included-in-teams"></a>Paquetes de directiva incluidos en Teams

Teams incluye actualmente los siguientes paquetes de directiva.

|**Nombre del paquete**  |**Descripción** |
|---------|---------|
|Educación (estudiante de educación superior)    |Crea un conjunto de directivas y configuraciones de directivas que se aplican a los estudiantes de educación superior.|
|Educación (estudiante de escuela primaria)   |Crea un conjunto de directivas y configuraciones de directiva que se aplican a los alumnos principales.|
|Educación (estudiante de secundaria)    |Crea un conjunto de directivas y configuraciones de directiva que se aplican a los alumnos secundarios.         |
|Educación (profesor)    |Crea un conjunto de directivas y configuraciones de directivas que se aplican a los profesores.      |
|Educación (profesor de educación primaria con aprendizaje remoto)    |Crea un conjunto de directivas que se aplican a los profesores de primaria para maximizar la seguridad y colaboración de los alumnos al usar la formación remota.      |
|Educación (estudiante de escuela primaria con aprendizaje remoto)    |Crea un conjunto de directivas que se aplican a los alumnos de primaria para maximizar la seguridad y colaboración de los alumnos al usar la formación remota.      |
|Administrador de frontline manager |Crea un conjunto de directivas y aplica esa configuración a los administradores de frontlines de su organización. |
|Trabajador de la primera línea |Crea un conjunto de directivas y aplica esa configuración a los trabajadores de la línea frontal de su organización. |
|Trabajador sanitario  |Crea un conjunto de directivas y configuraciones de directivas que proporciona a los trabajadores clínicos como enfermeras registradas, enfermeras responsables, médicos y trabajadores sociales acceso total a chat, llamadas, administración de turnos y reuniones. |
|Trabajador de la información sanitaria  |Crea un conjunto de directivas y configuraciones de directivas que proporciona a los trabajadores de la información, como el personal de IT, el personal de informática, el personal de finanzas y los responsables de cumplimiento normativo, acceso total a chats, llamadas y reuniones.|
|Sala de pacientes sanitarios  |Crea un conjunto de directivas y configuraciones de directivas que se aplican a las salas de pacientes de su organización sanitaria.|
|Usuario de una empresa pequeña y mediana (Business Voice) |Crea una directiva de configuración de aplicaciones que incluye las aplicaciones para una experiencia de voz empresarial.|
|Usuario de una empresa pequeña y mediana (sin Business Voice) |Crea una directiva de configuración de aplicación relevante para los usuarios de Teams para pequeñas y medianas empresas (experiencia que no sea de Voz empresarial).
|Responsable de seguridad pública   |Crea un conjunto de directivas y configuraciones de directivas que se aplican a los responsables de seguridad pública de su organización.|

> [!NOTE]
> Agregaremos más paquetes de directivas en futuras versiones de Teams, así que vuelve a comprobar la información más actualizada.  

A cada directiva individual se le da el nombre del paquete de directivas para que pueda identificar fácilmente las directivas vinculadas a un paquete de directivas.
Por ejemplo, al asignar el paquete de directivas educación (para profesores) a los profesores de su centro educativo, se crea una directiva denominada Education_Teacher para cada directiva del paquete.

![Captura de pantalla del paquete de directivas de Educación (para profesores)](media/policy-packages-education_teacher.png)

## <a name="custom-policy-packages"></a>Paquetes de directivas personalizadas

**Esta característica está en versión preliminar privada**

Los paquetes de directivas personalizadas te permiten agrupar tu propio conjunto de directivas para usuarios con roles similares en tu organización. Crea tus propios paquetes de directivas agregando los tipos de directiva y las directivas que necesites.

Para crear un nuevo paquete de directivas personalizado:

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, seleccione **Paquetes de directiva** y haga clic en **Agregar.**
    :::image type="content" source="media/policy-packages-add.png" alt-text="Captura de pantalla del botón Agregar en la página Paquetes de directivas del centro de administración":::
2. Escribe un nombre y una descripción para el paquete.
    :::image type="content" source="media/policy-packages-add-custom.png" alt-text="Captura de pantalla de adición de un nuevo paquete de directivas personalizado":::
3. Seleccione los tipos de directiva y nombres de directiva que desea incluir en el paquete.
4. Haga clic en **Guardar**.

## <a name="how-to-use-policy-packages"></a>Cómo usar paquetes de directiva

En los siguientes esquemas se describe cómo usar paquetes de directivas en tu organización.

![Información general sobre cómo usar paquetes de directivas](media/manage-policy-packages-overview.png)

- **[Ver:](#view-the-settings-of-a-policy-in-a-policy-package)** Ver las directivas de un paquete de directivas. A continuación, consulta la configuración de cada directiva en un paquete antes de asignar el paquete. Asegúrese de que comprende cada configuración. Decida si los valores predefinidos son adecuados para su organización o si necesita cambiarlos para que sean más restrictivos o restrictivos en función de las necesidades de su organización.

    Si se elimina una directiva, aún podrá ver la configuración, pero no podrá cambiar ninguna configuración. Una directiva eliminada se vuelve a crear con la configuración predefinida al asignar el paquete de directiva.

- **[Personalizar:](#customize-policies-in-a-policy-package)** personalice la configuración de directivas en el paquete de directivas para adaptarla a las necesidades de su organización.

- **[Asignar:](#assign-a-policy-package)** asigna el paquete de directiva a los usuarios.  

> [!NOTE]
> También puedes cambiar la configuración de directivas en un paquete de directiva después de asignar un paquete. Los cambios que realice en la configuración de directivas se aplican automáticamente a los usuarios a los que se les asigna el paquete.

Estos son los pasos para ver, asignar y personalizar paquetes de directiva en el Centro de administración de Microsoft Teams.

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a>Ver la configuración de una directiva en un paquete de directiva

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, seleccione Paquetes de directiva **y,** a continuación, seleccione un paquete de directiva haciendo clic a la izquierda del nombre del paquete.
2. Haga clic en la directiva que quiera ver.

### <a name="customize-policies-in-a-policy-package"></a>Personalizar directivas en un paquete de directiva

Puede editar la configuración de una directiva a través de la página **Paquetes** de directiva o directamente en la página de directivas del centro de administración de Microsoft Teams.

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, realice una de las siguientes acciones:
    - Haz **clic en Paquetes** de directiva y, a continuación, selecciona el paquete de directivas haciendo clic a la izquierda del nombre del paquete.
    - Haga clic en el tipo de directiva.  Por ejemplo, haga clic en **Directivas de mensajería.**
2. Seleccione la directiva que desea editar. Las directivas que están vinculadas a un paquete de directivas tienen el mismo nombre que el paquete de directivas.
3. Realice los cambios que desee y, a continuación, haga clic en **Guardar.**

### <a name="assign-a-policy-package"></a>Asignar un paquete de directiva 

#### <a name="assign-a-policy-package-to-one-user"></a>Asignar un paquete de directiva a un usuario

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Usuarios** y, después, haga clic en el usuario.
2. En la página del usuario, haga clic en **Directivas** y, a continuación, junto **a Paquete de directivas,** haga clic en **Editar.**
3. En el **panel Asignar paquete de** directivas, seleccione el paquete que desea asignar y, a continuación, haga clic en **Guardar.**

#### <a name="assign-a-policy-package-to-multiple-users"></a>Asignar un paquete de directiva a varios usuarios

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a Paquetes de directiva y, a continuación, seleccione el paquete de directiva que desea asignar haciendo clic a la izquierda del nombre del paquete.
2. Haga clic **en Administrar usuarios.**
3. En el panel **Administrar usuarios**, busque el usuario por nombre para mostrar o por nombre de usuario, seleccione el nombre y, después, haga clic en **Agregar**. Repita este paso por cada usuario que quiera agregar.
4. Cuando haya terminado de agregar usuarios, haga clic en **Guardar.**

#### <a name="assign-a-policy-package-to-a-group"></a>Asignar un paquete de directivas a un grupo

**Esta característica está en versión preliminar privada**

La opción de asignar un paquete de directiva a grupos le permite asignar múltiples directivas a un grupo de usuarios, como un grupo de seguridad o una lista de distribución. La asignación de directiva se extiende a los miembros del grupo en función de las reglas de prioridad. A medida que se agregan o se eliminan miembros de un grupo, sus asignaciones de directivas heredadas se actualizan correspondientemente. Este método es el recomendado para grupos de hasta 50 000 usuarios, pero también funciona con grupos más grandes.

Para obtener más información, consulte [Asignar un paquete de directivas a un grupo](assign-policies.md#assign-a-policy-package-to-a-group).

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a>Asignar un paquete de directivas a un conjunto amplio (un lote) de usuarios

Use la asignación de paquete de directiva por lotes para asignar un paquete de directivas a grandes grupos de usuarios de una sola vez. Use el cmdlet [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) para enviar un lote de usuarios y el paquete de directivas que quiera asignar. Las asignaciones se procesan como una operación de segundo plano y se genera un identificador de operación para cada lote.

Un lote puede contener hasta 5000 usuarios. Puede especificar los usuarios por su identificador de objeto, UPN, dirección SIP o dirección de correo electrónico. Para obtener más información, consulte [Asignar un paquete de directivas a un lote de usuarios](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).

## <a name="troubleshooting"></a>Solución de problemas

**Recibe un error al asignar un paquete de directivas**

Esto puede ocurrir si una o más directivas del paquete no se crearon o no se aplicaron correctamente. Reasigna el paquete de directivas a los usuarios. Normalmente, al volver a intentar la operación se soluciona este problema.

## <a name="related-topics"></a>Temas relacionados

[Asignar directivas a los usuarios en Teams](assign-policies.md)

[Paquetes de directivas de Teams para administradores de EDU](policy-packages-edu.md)

[Paquetes de directivas de Teams para atención sanitaria](policy-packages-healthcare.md)

[Paquetes de directivas de Teams para administración pública](policy-packages-gov.md)
