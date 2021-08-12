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
description: Aprenda a usar y administrar paquetes de directivas en Microsoft Teams simplificar, simplificar y ayudar a proporcionar coherencia al administrar directivas para grupos de usuarios.
ms.openlocfilehash: 2fd892bc440996c7c1f000402122ad268a402ebb6bf382672813efa296de819f
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54341795"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a>Administrar paquetes de directivas en Microsoft Teams

Un paquete de directivas en Microsoft Teams es una colección de directivas predefinidas y la configuración de directiva que puede asignar a usuarios que tienen roles similares en su organización. Hemos creado paquetes de directivas para simplificar, simplificar y ayudar a proporcionar coherencia al administrar directivas para grupos de usuarios en toda la organización.  

Puede usar los [paquetes de directiva incluidos en Teams](#policy-packages-included-in-teams) o [crear sus propios paquetes de directiva personalizados.](#custom-policy-packages)

:::image type="content" source="media/policy-packages-admin-center.png" alt-text="Captura de pantalla de la página Paquetes de directivas en el Centro de administración":::

Puede personalizar la configuración de las directivas de un paquete de directivas para que se adapte a las necesidades de los usuarios. Al cambiar la configuración de las directivas de un paquete, todos los usuarios que están asignados a ese paquete obtienen la configuración actualizada. Los paquetes de directivas se administran mediante el Microsoft Teams de administración o PowerShell.

> [!NOTE]
> Cada usuario necesitará el complemento comunicaciones avanzadas para recibir una asignación de paquete de directiva personalizada. Para obtener más información, [vea Advanced Communications add-on for Microsoft Teams](/microsoftteams/teams-add-on-licensing/advanced-communications).

## <a name="what-is-a-policy-package"></a>¿Qué es un paquete de directivas?

Los paquetes de directivas le permiten controlar Teams características que desea permitir o restringir para conjuntos específicos de personas en toda la organización. Cada paquete de directiva de Teams está diseñado en torno a un rol de usuario e incluye directivas predefinidas y configuraciones de directiva que admiten las actividades de colaboración y comunicación típicas de ese rol.

Los paquetes de directivas admiten los siguientes Teams de directivas:

- Directiva de mensajería
- Directiva de reunión
- Directiva de configuración de aplicaciones
- Directiva de llamadas
- Directiva de eventos en directo

## <a name="policy-packages-included-in-teams"></a>Paquetes de directivas incluidos en Teams

Teams incluye actualmente los siguientes paquetes de directivas.

| Nombre del paquete | Descripción |
|---------|---------|
|Educación (estudiante de educación superior)    |Crea un conjunto de directivas y configuraciones de directivas que se aplican a los estudiantes de educación superior.|
|Educación (estudiante de primaria)   |Crea un conjunto de directivas y configuraciones de directivas que se aplican a los alumnos de primaria.|
|Educación (estudiante de secundaria)    |Crea un conjunto de directivas y configuraciones de directivas que se aplican a los alumnos secundarios.         |
|Educación (profesor)    |Crea un conjunto de directivas y configuraciones de directivas que se aplican a los profesores.      |
|Educación (profesor de primaria con aprendizaje remoto)    |Crea un conjunto de directivas que se aplican a los profesores principales para maximizar la seguridad y colaboración de los alumnos al usar el aprendizaje remoto.      |
|Educación (estudiante de escuela primaria con aprendizaje remoto)    |Crea un conjunto de directivas que se aplican a los alumnos de primaria para maximizar la seguridad y colaboración de los alumnos al usar el aprendizaje remoto.      |
|Administrador de línea frontal |Crea un conjunto de directivas y aplica esa configuración a los administradores de front-line de la organización. |
|Trabajador en primera línea |Crea un conjunto de directivas y aplica esa configuración a los trabajadores de Frontline de la organización. |
|Trabajador clínico de la salud  |Crea un conjunto de directivas y configuraciones de directivas que dan a los trabajadores clínicos, como enfermeras registradas, enfermeras de cargo, médicos y trabajadores sociales acceso total a chat, llamadas, administración de turnos y reuniones. |
|Trabajador de información sanitaria  |Crea un conjunto de directivas y configuraciones de directivas que dan a los trabajadores de la información, como el personal de INFORMÁTICA, el personal de informática, el personal de finanzas y los responsables de cumplimiento, acceso total al chat, las llamadas y las reuniones.|
|Sala de pacientes de salud  |Crea un conjunto de directivas y configuraciones de directivas que se aplican a las salas de pacientes de la organización sanitaria.|
|Usuario de pequeña y mediana empresa (Business Voice) |Crea una directiva de configuración de aplicaciones que incluye las aplicaciones para una experiencia de voz empresarial.|
|Usuario de pequeñas y medianas empresas (sin Business Voice) |Crea una directiva de configuración de aplicaciones relevante para una pequeña y mediana empresa Teams usuarios (experiencia de voz no empresarial).
|Oficial de seguridad pública   |Crea un conjunto de directivas y configuraciones de directivas que se aplican a los responsables de seguridad pública de la organización.|

> [!NOTE]
> Agregaremos más paquetes de directiva en futuras versiones de Teams, así que vuelve a consultar la información más actualizada.  

Cada directiva individual tiene el nombre del paquete de directivas para que pueda identificar fácilmente las directivas vinculadas a un paquete de directivas.
Por ejemplo, cuando asigna el paquete de directiva Educación (profesor) a los profesores de la escuela, se crea una directiva denominada Education_Teacher para cada directiva del paquete.

![Captura de pantalla del paquete de directivas educación (profesor)](media/policy-packages-education_teacher.png)

## <a name="custom-policy-packages"></a>Paquetes de directivas personalizados

**Los paquetes de directivas personalizados aún no están disponibles para el Government Community Cloud (GCC)**

Los paquetes de directivas personalizados le permiten agrupar su propio conjunto de directivas para usuarios con roles similares en su organización. Cree sus propios paquetes de directivas agregando los tipos de directiva y las directivas que necesita.

Para crear un nuevo paquete de directiva personalizada:

1. En la navegación izquierda del centro de administración Microsoft Teams, seleccione **Paquetes de directivas** y, a continuación, haga clic en **Agregar**.

    :::image type="content" source="media/policy-packages-add.png" alt-text="Captura de pantalla del botón Agregar en la página Paquetes de directivas en el Centro de administración":::

2. Escriba un nombre y una descripción para el paquete.

    :::image type="content" source="media/policy-packages-add-custom.png" alt-text="Captura de pantalla de agregar un nuevo paquete de directiva personalizada":::

3. Seleccione los tipos de directiva y los nombres de directiva que se incluirán en el paquete.

4. Haga clic en **Guardar**.

## <a name="how-to-use-policy-packages"></a>Cómo usar paquetes de directivas

A continuación se describe cómo usar paquetes de directivas en la organización.

![Información general sobre cómo usar paquetes de directivas](media/manage-policy-packages-overview.png)

- **[Ver](#view-the-settings-of-a-policy-in-a-policy-package)**: Ver las directivas de un paquete de directivas. A continuación, vea la configuración de cada directiva de un paquete antes de asignar el paquete. Asegúrese de comprender cada configuración. Decida si los valores predefinidos son adecuados para su organización o si necesita cambiarlos para que sean más restrictivos o indulgentes en función de las necesidades de la organización.

    Si se elimina una directiva, aún puede ver la configuración, pero no podrá cambiar ninguna configuración. Una directiva eliminada se vuelve a crear con la configuración predefinida al asignar el paquete de directiva.

- **[Personalizar](#customize-policies-in-a-policy-package)**: personalizar la configuración de las directivas del paquete de directivas para que se ajuste a las necesidades de su organización.

- **[Asignar](#assign-a-policy-package)**: Asignar el paquete de directiva a los usuarios.  

> [!NOTE]
> También puede cambiar la configuración de directivas en un paquete de directivas después de asignar un paquete. Los cambios realizados en la configuración de directiva se aplican automáticamente a los usuarios a los que se asigna el paquete.

Estos son los pasos para ver, asignar y personalizar paquetes de directivas en el centro Microsoft Teams administración.

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a>Ver la configuración de una directiva en un paquete de directiva

1. En la navegación izquierda del Centro de administración de Microsoft Teams, seleccione Paquetes de directivas y, a continuación, seleccione un paquete de directiva haciendo clic a la izquierda del nombre del paquete.

2. Haga clic en la directiva que desea ver.

### <a name="customize-policies-in-a-policy-package"></a>Personalizar directivas en un paquete de directivas

Puede editar la configuración de  una directiva a través de la página Paquetes de directivas o yendo directamente a la página de directiva en el centro Microsoft Teams administración.

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, siga uno de estos procedimientos:
    - Haga **clic en Paquetes de** directiva y, a continuación, seleccione el paquete de directiva haciendo clic a la izquierda del nombre del paquete.
    - Haga clic en el tipo de directiva.  Por ejemplo, haga clic en **Directivas de mensajería.**

2. Seleccione la directiva que desee editar. Las directivas que están vinculadas a un paquete de directivas tienen el mismo nombre que el paquete de directivas.

3. Realice los cambios que desee y, a continuación, haga clic **en Guardar**.

### <a name="assign-a-policy-package"></a>Asignar un paquete de directivas

Puede asignar un paquete de directiva a un usuario individual, un grupo o un lote de usuarios. Para obtener más información sobre cómo asignar paquetes de directivas, vea [Asignar paquetes de directivas a usuarios y grupos.](assign-policy-packages.md)

## <a name="related-topics"></a>Temas relacionados

- [Asignar paquetes de directivas](assign-policy-packages.md)
- [Teams paquetes de directiva para administradores edu](policy-packages-edu.md)
- [Teams paquetes de directivas para la salud](policy-packages-healthcare.md)
- [Teams paquetes de directivas de administración pública](policy-packages-gov.md)
