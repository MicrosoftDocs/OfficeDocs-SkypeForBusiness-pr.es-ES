---
title: Administrar paquetes de directivas en Microsoft Teams
author: SerdarSoysal
ms.author: serdars
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
ms.localizationpriority: medium
search.appverid: MET150
description: Obtenga información sobre cómo usar y administrar paquetes de directivas en Microsoft Teams para simplificar, simplificar y ayudar a proporcionar coherencia al administrar directivas para grupos de usuarios.
ms.openlocfilehash: d38384889e48e7d666036675b1a52ae194ea9582
ms.sourcegitcommit: 836926a4914eb33fc3e0d8d6c84cee886cb1a5a7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/29/2022
ms.locfileid: "65145038"
---
# <a name="manage-policy-packages-for-microsoft-teams"></a>Administrar paquetes de directivas para Microsoft Teams

Un paquete de directivas en Microsoft Teams es una colección de directivas y configuraciones de directiva predefinidas que puede asignar a los usuarios que tienen roles similares en la organización. Hemos creado paquetes de directivas para simplificar, simplificar y ayudar a proporcionar coherencia al administrar directivas para grupos de usuarios de toda la organización.  

Puedes usar los [paquetes de directivas incluidos en Teams](#policy-packages-included-in-teams) o [crear tus propios paquetes de directivas personalizados](#custom-policy-packages).

:::image type="content" source="media/policy-packages-admin-center.png" alt-text="Captura de pantalla de la página Paquetes de directivas en el centro de administración.":::

Puede personalizar la configuración de las directivas de un paquete de directivas para adaptarla a las necesidades de los usuarios. Al cambiar la configuración de las directivas de un paquete, todos los usuarios asignados a ese paquete obtienen la configuración actualizada. Puede administrar paquetes de directivas mediante el centro de administración de Microsoft Teams o PowerShell.

> [!NOTE]
> Esta característica está disponible temporalmente en la versión preliminar pública para todos los clientes de Microsoft Teams. Para obtener esta característica después de la vista previa, cada usuario necesitará la licencia del complemento Comunicaciones avanzadas. Para más información, consulte [Complemento de Comunicaciones avanzadas para Microsoft Teams](/microsoftteams/teams-add-on-licensing/advanced-communications).

## <a name="what-is-a-policy-package"></a>¿Qué es un paquete de directivas?

Los paquetes de directivas te permiten controlar Teams características que quieres permitir o restringir para conjuntos específicos de personas de la organización. Cada paquete de directivas de Teams está diseñado en torno a un rol de usuario e incluye directivas predefinidas y configuraciones de directiva que admiten las actividades de colaboración y comunicación típicas de ese rol.

Los paquetes de directivas admiten los siguientes tipos de directiva de Teams:

- Directiva de mensajería
- Directiva de reuniones
- Directiva de configuración de aplicaciones
- Directiva de llamadas
- Directiva de eventos en directo

## <a name="policy-packages-included-in-teams"></a>Paquetes de directivas incluidos en Teams

Teams incluye actualmente los siguientes paquetes de directivas.

| Nombre del paquete | Descripción |
|---------|---------|
|Educación (estudiante de educación superior)    |Crea un conjunto de directivas y configuraciones de directiva que se aplican a los estudiantes de educación superior.|
|Educación (estudiante de la escuela primaria)   |Crea un conjunto de directivas y configuraciones de directiva que se aplican a los alumnos principales.|
|Educación (estudiante de secundaria)    |Crea un conjunto de directivas y configuraciones de directiva que se aplican a los alumnos secundarios.         |
|Educación (profesor)    |Crea un conjunto de directivas y configuraciones de directiva que se aplican a los profesores.      |
|Educación (profesor de escuela primaria usando el aprendizaje remoto)    |Crea un conjunto de directivas que se aplican a los profesores de primaria para maximizar la seguridad y colaboración de los alumnos al usar la formación remota.      |
|Educación (estudiantes de educación primaria usando el aprendizaje remoto)    |Crea un conjunto de directivas que se aplican a los alumnos de primaria para maximizar la seguridad y colaboración de los alumnos al usar la formación remota.      |
|Administrador de frontline |Crea un conjunto de directivas y aplica esta configuración a los administradores de primera línea de su organización. |
|Trabajador de primera línea |Crea un conjunto de directivas y aplica esta configuración a los trabajadores de primera línea de su organización. |
|Trabajador clínico de la sanidad  |Crea un conjunto de directivas y configuraciones de directivas que proporciona a los trabajadores clínicos como los profesionales clínicos registrados, las enfermeras de cargo, los médico y los trabajadores sociales acceso completo al chat, a las llamadas, a la administración de turnos y a las reuniones. |
|Trabajador de la información sanitaria  |Crea un conjunto de directivas y configuraciones de directivas que dan a los trabajadores de la información como el personal de TI, el personal informático, el personal del departamento financiero y los responsables de cumplimiento normativo, acceso completo a chat, llamadas y reuniones.|
|Sala de pacientes de cuidado de la salud  |Crea un conjunto de directivas y configuraciones de directivas que se aplican a las salas de pacientes de su organización de cuidados de la salud.|
|Usuario de pequeñas y medianas empresas (Teams Sistema telefónico con paquete de plan de llamadas) |Crea una directiva de configuración de aplicaciones que incluye las aplicaciones de un Teams Sistema telefónico con la experiencia del paquete Plan de llamadas.|
|Usuario de pequeña y mediana empresa (sin Teams Sistema telefónico con paquete plan de llamadas) |Crea una directiva de configuración de aplicaciones relevante para una pequeña y mediana empresa Teams usuarios (sin Teams Sistema telefónico con la experiencia de conjunto de paquetes del plan de llamadas).
|Oficial de seguridad pública   |Crea un conjunto de directivas y configuraciones de directiva que se aplican a los oficiales de seguridad pública de su organización.|

> [!NOTE]
> Agregaremos más paquetes de directivas en futuras versiones de Teams, por lo que deberás volver a comprobar la información más actualizada.  

Cada directiva individual se indica con el nombre del paquete de directivas para que pueda identificar fácilmente las directivas vinculadas a un paquete de directivas.
Por ejemplo, al asignar el paquete de directivas Educación (profesor) a profesores de su centro educativo, se crea una directiva denominada Education_Teacher para cada directiva del paquete.

![Captura de pantalla del paquete de directivas educación (profesor).](media/policy-packages-education_teacher.png)

## <a name="custom-policy-packages"></a>Paquetes de directivas personalizadas

Los paquetes de directivas personalizadas le permiten agrupar su propio conjunto de directivas para los usuarios con roles similares en su organización. Cree sus propios paquetes de directivas agregando los tipos de directiva y las directivas que necesita.

Para crear un nuevo paquete de directivas personalizado:

1. En el panel izquierdo del Microsoft Teams centro de administración, selecciona **Paquetes de directivas** y, a continuación, haz clic en **Agregar**.

    :::image type="content" source="media/policy-packages-add.png" alt-text="Captura de pantalla del botón Agregar en la página Paquetes de directivas del centro de administración.":::

2. Escribe un nombre y una descripción para el paquete.

    :::image type="content" source="media/policy-packages-add-custom.png" alt-text="Captura de pantalla que muestra cómo agregar un nuevo paquete de directivas personalizado.":::

3. Selecciona los tipos de directiva y nombres de directiva que se incluirán en el paquete.

4. Seleccione **Guardar**.

## <a name="how-to-use-policy-packages"></a>Cómo usar paquetes de directivas

En los siguientes esquemas se describe cómo usar paquetes de directivas en su organización.

![Información general sobre cómo usar paquetes de directivas.](media/manage-policy-packages-overview.png)

- **[Vista](#view-the-settings-of-a-policy-in-a-policy-package)**: Vea las directivas de un paquete de directivas. A continuación, consulta la configuración de cada directiva en un paquete antes de asignar el paquete. Asegúrate de que comprendes cada opción de configuración. Decida si los valores predefinidos son adecuados para su organización o si necesita cambiarlos para que sean más restrictivos o indulgentes en función de las necesidades de su organización.

    Si se elimina una directiva, puede seguir viendo la configuración, pero no podrá cambiar ninguna configuración. Al asignar el paquete de directivas, se vuelve a crear una directiva eliminada con la configuración predefinida.

- **[Personalizar](#customize-policies-in-a-policy-package)**: personalice la configuración de las directivas en el paquete de directivas para adaptarla a las necesidades de su organización.

- **[Asignar](#assign-a-policy-package)**: asigne el paquete de directivas a los usuarios.  

> [!NOTE]
> También puede cambiar la configuración de las directivas de un paquete de directivas después de asignar un paquete. Los cambios que realice en la configuración de directivas se aplican automáticamente a los usuarios a los que se les asigna el paquete.

Estos son los pasos para ver, asignar y personalizar paquetes de directivas en el Centro de administración de Microsoft Teams.

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a>Ver la configuración de una directiva en un paquete de directivas

1. En el panel izquierdo del Microsoft Teams centro de administración, selecciona **Paquetes** de directivas y, a continuación, selecciona un paquete de directiva haciendo clic a la izquierda del nombre del paquete.

2. Seleccione la directiva que quiera ver.

### <a name="customize-policies-in-a-policy-package"></a>Personalizar directivas en un paquete de directivas

Puedes editar la configuración de una directiva a través de la página **Paquetes de** directivas o yendo directamente a la página de directiva del centro de administración de Microsoft Teams.

1. En el panel izquierdo del Microsoft Teams centro de administración, siga uno de estos procedimientos:
    - Selecciona **Paquetes de** directivas y, a continuación, selecciona el paquete de directivas haciendo clic a la izquierda del nombre del paquete.
    - Seleccione el tipo de directiva.  Por ejemplo, haga clic en **Directivas de mensajería**.

2. Seleccione la directiva que desea editar. Las directivas vinculadas a un paquete de directivas tienen el mismo nombre que el paquete de directivas.

3. Realice los cambios que desee y, a continuación, haga clic en **Guardar**.

### <a name="assign-a-policy-package"></a>Asignar un paquete de directivas

Puede asignar un paquete de directivas a un usuario individual, un grupo o un lote de usuarios. Para obtener más información sobre cómo asignar paquetes de directivas, consulta [Asignar paquetes de directiva a usuarios y grupos](assign-policy-packages.md).

## <a name="related-topics"></a>Temas relacionados

- [Asignar paquetes de directivas](assign-policy-packages.md)
- [paquetes de directivas de Teams para administradores educativos](policy-packages-edu.md)
- [Paquetes de directivas de Teams para sanidad](policy-packages-healthcare.md)
- [paquetes de directivas de Teams para la administración pública](policy-packages-gov.md)
