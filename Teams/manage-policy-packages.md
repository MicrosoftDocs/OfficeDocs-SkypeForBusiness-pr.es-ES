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
description: Obtenga información sobre cómo usar y administrar paquetes de directivas en Microsoft Teams para simplificar, simplificar y ayudar a proporcionar coherencia al administrar directivas para grupos de usuarios.
ms.openlocfilehash: 1b7e6e5c6311ebd51b0f00b86953291ed4ac63b3
ms.sourcegitcommit: b52b6aba289396c4fc10dd856817137eb1bc1f67
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/07/2021
ms.locfileid: "51634239"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a>Administrar paquetes de directivas en Microsoft Teams

Un paquete de directivas en Microsoft Teams es una colección de directivas y configuraciones de directiva predefinidas que puede asignar a los usuarios que tienen roles similares en la organización. Hemos creado paquetes de directivas para simplificar, simplificar y ayudar a proporcionar coherencia al administrar directivas para grupos de usuarios de toda la organización.  

Puede usar los [paquetes de directiva incluidos en Teams](#policy-packages-included-in-teams) o crear sus propios paquetes de directiva [personalizados](#custom-policy-packages) (en versión preliminar privada).

:::image type="content" source="media/policy-packages-admin-center.png" alt-text="Captura de pantalla de la página Paquetes de directivas en el Centro de administración":::

Puede personalizar la configuración de las directivas de un paquete de directivas para adaptarla a las necesidades de los usuarios. Al cambiar la configuración de directivas de un paquete, todos los usuarios que están asignados a ese paquete obtienen la configuración actualizada. Puede administrar paquetes de directivas mediante el Centro de administración de Microsoft Teams o PowerShell.

## <a name="what-is-a-policy-package"></a>¿Qué es un paquete de directivas?

Los paquetes de directivas le permiten controlar las características de Teams que desea permitir o restringir para conjuntos específicos de personas de toda la organización. Cada paquete de directivas de Teams está diseñado en torno a un rol de usuario e incluye directivas predefinidas y configuraciones de directiva que admiten las actividades de colaboración y comunicación que son típicas de ese rol.

Los paquetes de directiva admiten los siguientes tipos de directiva de Teams:

- Directiva de mensajería
- Directiva de reuniones
- Directiva de configuración de aplicaciones
- Directiva de llamadas
- Directiva de eventos en directo

## <a name="policy-packages-included-in-teams"></a>Paquetes de directivas incluidos en Teams

Teams incluye actualmente los siguientes paquetes de directivas.

| Nombre del paquete | Descripción |
|---------|---------|
|Educación (estudiante de educación superior)    |Crea un conjunto de directivas y configuraciones de directivas que se aplican a los estudiantes de educación superior.|
|Educación (alumno de la escuela primaria)   |Crea un conjunto de directivas y configuraciones de directiva que se aplican a los alumnos de primaria.|
|Educación (estudiante de secundaria)    |Crea un conjunto de directivas y configuraciones de directiva que se aplican a los alumnos secundarios.         |
|Educación (profesor)    |Crea un conjunto de directivas y configuraciones de directiva que se aplican a los profesores.      |
|Educación (profesor de escuela primaria que usa el aprendizaje remoto)    |Crea un conjunto de directivas que se aplican a los profesores de primaria para maximizar la seguridad y colaboración de los alumnos al usar la formación remota.      |
|Educación (alumno de la escuela primaria que usa el aprendizaje remoto)    |Crea un conjunto de directivas que se aplican a los alumnos de primaria para maximizar la seguridad y colaboración de los alumnos al usar la formación remota.      |
|Administrador de primera línea |Crea un conjunto de directivas y aplica esa configuración a los administradores de frontline de su organización. |
|Trabajador en primera línea |Crea un conjunto de directivas y aplica esa configuración a los trabajadores de Frontline de su organización. |
|Trabajador clínico de la sanidad  |Crea un conjunto de directivas y configuraciones de directivas que proporciona a los trabajadores clínicos como los profesionales clínicos registrados, las enfermeras de cargo, los médico y los trabajadores sociales acceso completo al chat, a las llamadas, a la administración de turnos y a las reuniones. |
|Trabajador de la información sanitaria  |Crea un conjunto de directivas y configuraciones de directivas que dan a los trabajadores de la información como el personal de TI, el personal informático, el personal del departamento financiero y los responsables de cumplimiento normativo, acceso completo a chat, llamadas y reuniones.|
|Sala de pacientes de cuidado de la salud  |Crea un conjunto de directivas y configuraciones de directivas que se aplican a las salas de pacientes de su organización de cuidados de la salud.|
|Usuario de pequeñas y medianas empresas (Business Voice) |Crea una directiva de configuración de aplicaciones que incluye las aplicaciones para una experiencia de voz empresarial.|
|Usuario de pequeñas y medianas empresas (sin Business Voice) |Crea una directiva de configuración de aplicaciones relevante para usuarios de Teams para pequeñas y medianas empresas (experiencia de voz no empresarial).
|Oficial de seguridad pública   |Crea un conjunto de directivas y configuraciones de directiva que se aplican a los responsables de seguridad pública de su organización.|

> [!NOTE]
> Agregaremos más paquetes de directiva en futuras versiones de Teams, así que vuelve a comprobar la información más actualizada.  

Cada directiva individual se indica con el nombre del paquete de directivas para que pueda identificar fácilmente las directivas vinculadas a un paquete de directivas.
Por ejemplo, cuando asigna el paquete de directivas Educación (profesor) a los profesores de su centro educativo, se crea una directiva denominada Education_Teacher para cada directiva del paquete.

![Captura de pantalla del paquete de directivas educación (profesor)](media/policy-packages-education_teacher.png)

## <a name="custom-policy-packages"></a>Paquetes de directivas personalizados

**Los paquetes de directivas personalizados aún no están disponibles para la nube de la comunidad gubernamental (GCC)**

Los paquetes de directivas personalizados le permiten agrupar su propio conjunto de directivas para usuarios con roles similares en su organización. Cree sus propios paquetes de directivas agregando los tipos de directiva y las directivas que necesita.

Para crear un nuevo paquete de directiva personalizada:

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, seleccione **Paquetes de directivas** y, a continuación, haga clic en **Agregar.**

    :::image type="content" source="media/policy-packages-add.png" alt-text="Captura de pantalla del botón Agregar en la página Paquetes de directiva en el Centro de administración":::

2. Escriba un nombre y una descripción para el paquete.

    :::image type="content" source="media/policy-packages-add-custom.png" alt-text="Captura de pantalla de agregar un nuevo paquete de directiva personalizada":::

3. Seleccione los tipos de directiva y los nombres de directiva que desea incluir en el paquete.

4. Haga clic en **Guardar**.

## <a name="how-to-use-policy-packages"></a>Cómo usar paquetes de directivas

A continuación se describe cómo usar paquetes de directivas en su organización.

![Información general sobre cómo usar paquetes de directivas](media/manage-policy-packages-overview.png)

- **[Ver:](#view-the-settings-of-a-policy-in-a-policy-package)** Ver las directivas de un paquete de directivas. Después, vea la configuración de cada directiva de un paquete antes de asignar el paquete. Asegúrese de que comprende cada configuración. Decida si los valores predefinidos son adecuados para su organización o si necesita cambiarlos para que sean más restrictivos o más indulgentes en función de las necesidades de su organización.

    Si se elimina una directiva, aún puede ver la configuración, pero no podrá cambiar ninguna configuración. Se vuelve a crear una directiva eliminada con la configuración predefinida al asignar el paquete de directiva.

- **[Personalizar:](#customize-policies-in-a-policy-package)** Personalice la configuración de directivas del paquete de directivas para que se ajuste a las necesidades de su organización.

- **[Asignar:](#assign-a-policy-package)** Asigne el paquete de directiva a los usuarios.  

> [!NOTE]
> También puede cambiar la configuración de directivas de un paquete de directiva después de asignar un paquete. Los cambios que realice en la configuración de directivas se aplican automáticamente a los usuarios a los que se les asigna el paquete.

Estos son los pasos para ver, asignar y personalizar paquetes de directivas en el Centro de administración de Microsoft Teams.

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a>Ver la configuración de una directiva en un paquete de directivas

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, seleccione Paquetes de directivas y, después, seleccione un paquete de directiva haciendo clic a la izquierda del nombre del paquete.

2. Haga clic en la directiva que desea ver.

### <a name="customize-policies-in-a-policy-package"></a>Personalizar directivas en un paquete de directivas

Puede editar la configuración de  una directiva a través de la página Paquetes de directivas o yendo directamente a la página de directivas en el Centro de administración de Microsoft Teams.

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, realice una de las siguientes acciones:
    - Haga **clic en Paquetes** de directiva y, a continuación, seleccione el paquete de directiva haciendo clic a la izquierda del nombre del paquete.
    - Haga clic en el tipo de directiva.  Por ejemplo, haga clic en **Directivas de mensajería.**

2. Seleccione la directiva que desea editar. Las directivas vinculadas a un paquete de directivas tienen el mismo nombre que el paquete de directivas.

3. Realice los cambios que desee y, a continuación, haga clic en **Guardar.**

### <a name="assign-a-policy-package"></a>Asignar un paquete de directivas

Puede asignar un paquete de directiva a un usuario individual, un grupo o un lote de usuarios. Para obtener más información sobre cómo asignar paquetes de directiva, vea [Asignar paquetes de directiva a usuarios y grupos.](assign-policy-packages.md)

## <a name="related-topics"></a>Temas relacionados

- [Asignar paquetes de directiva](assign-policy-packages.md)
- [Paquetes de directivas de Teams para administradores de EDU](policy-packages-edu.md)
- [Paquetes de directivas de Teams para sanidad](policy-packages-healthcare.md)
- [Paquetes de directivas de Teams para el gobierno](policy-packages-gov.md)
