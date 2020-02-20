---
title: Paquetes de directivas de Microsoft Teams para administradores de EDU
author: dstrome
ms.author: dstrome
manager: serdars
ms.reviewer: prkuch
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.policypackages.overview
localization_priority: Normal
search.appverid: MET150
description: Obtenga información sobre cómo usar y administrar paquetes de directivas en Microsoft Teams.
ms.openlocfilehash: d4a11952ea65a5380abb3ba284e13bab6d5d4e90
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42155052"
---
# <a name="microsoft-teams-policy-packages-for-edu-admins"></a>Paquetes de directivas de Microsoft Teams para administradores de EDU

Un paquete de directivas de Microsoft Teams recopila las directivas predefinidas y la configuración de directivas que puede asignar a los usuarios que tengan roles similares en su institución. Los paquetes de directivas simplifican, optimizan y ayudan a proporcionar coherencia al administrar las directivas. En la práctica normal, asigne a cada uno de los usuarios un paquete de directivas y, según sea necesario, redefina las directivas de cada paquete para satisfacer las necesidades de ese grupo de usuarios. Al actualizar la configuración de un paquete, todos los usuarios asignados a ese paquete se cambian como una actualización masiva.

En general, las instituciones educativas tienen muchos tipos de usuarios con necesidades exclusivas, en función de la edad y el vencimiento de los alumnos. Por ejemplo, es posible que desee conceder a los formadores y al personal acceso completo a Microsoft Teams, pero quiere limitar las capacidades de Microsoft Teams para que los alumnos favorezcan un entorno de aprendizaje seguro y centrado. Puede usar paquetes de directivas para personalizar la configuración en función de las necesidades de los diferentes cohorts de su comunidad de la escuela.

## <a name="what-is-a-policy-package"></a>¿Qué es un paquete de directivas?

Los paquetes de directivas le permiten controlar las funciones de Microsoft teams que permiten o restringen el uso de Microsoft Teams para conjuntos específicos de personas de su organización. Cada paquete de directivas está diseñado según un rol de usuario e incluye directivas predefinidas y opciones de directiva que admiten actividades típicas de ese rol.

Directivas de predefinición de paquetes de directivas para:
- Mensajería 
- Reuniones
- Configuración de la aplicación
- Llamadas
- Eventos en directo

Microsoft Teams actualmente incluye los siguientes paquetes de directivas:

|Nombre del paquete que aparece en el centro de administración de Microsoft Teams |Es la mejor opción para  |Descripción |
|:--- |:--- |:--- |
|Education_Teacher| Educadores y personal| Use este conjunto de directivas y configuración de directivas para conceder a los formadores y el personal de su organización acceso completo a chats, llamadas y reuniones a través de Microsoft Teams. |
|Education_PrimaryStudent | Estudiantes principales de la escuela  | Los más jóvenes, los estudiantes de la escuela principal de su institución pueden necesitar más límites dentro de Microsoft Teams. Use este conjunto de directivas y de configuración de directivas para limitar capacidades como la creación y administración de reuniones, la administración de chats y las llamadas privadas. |
|Education_SecondaryStudent| Estudiantes mayores de la escuela secundaria | Escuela secundaria los estudiantes antiguos de su institución pueden necesitar más límites dentro de Microsoft Teams. Use este conjunto de directivas y de configuración de directivas para limitar capacidades como la creación y administración de reuniones, la administración de chats y las llamadas privadas. |
|Education_HigherEducationStudent | Estudiantes de educación superior | Los estudiantes de educación superior de su Intuition pueden necesitar menos límites que los estudiantes de los jóvenes, pero se recomiendan algunas limitaciones. Puede usar este conjunto de directivas y opciones de directiva para dar acceso a chats, llamadas y reuniones dentro de su organización, pero limite la forma en que los alumnos usan Microsoft Teams con participantes externos. |
|||

A cada directiva individual se le da el nombre del paquete de directivas para que pueda identificar fácilmente las directivas vinculadas a un paquete de directivas. Por ejemplo, al asignar el paquete de directivas Education_Teacher a los profesores de su escuela, se crea una directiva llamada Education_Teacher para cada Directiva del paquete.

![Captura de pantalla del paquete de directivas de Education_Teacher](media/policy-packages-education_teacher.png)

> [!NOTE]
> Si decide que los profesores y el personal de soporte administrativo necesitan directivas diferentes, puede reasignar un paquete existente: identifique un paquete que no esté usando actualmente y cambie la configuración para que sea la adecuada para ese grupo. Es posible que tenga que hacer una nota para usted mismo qué grupo tiene qué paquete, pero este es el único obstáculo para reasignar un paquete.

## <a name="why-use-policy-packages"></a>¿Por qué usar paquetes de directivas?

Si su institución tiene cientos o incluso miles de usuarios, es posible que se pregunte: "¿por qué tomarse el tiempo para asignar un paquete u otro a todos esos usuarios?"

Asignar paquetes a cientos de usuarios es una inversión en tiempo administrativo, sin ninguna pregunta. Un aspecto importante de las inversiones es que se pagan a lo largo del tiempo, en lugar de hacerlo de inmediato.

En un entorno educativo, hay muchos usuarios con roles iguales o similares. Dedica menos esfuerzo a lo largo del tiempo cuando administra la experiencia del usuario de la misma manera. Grupo paquetes un conjunto de directivas específicas para las distintas funciones de la institución. Los usuarios con la misma licencia, pero diferentes roles, pueden tener las directivas pertinentes asignadas según su rol, que es más eficaz que el ajuste de directivas para usuarios individuales.

Una vez que todos los usuarios de la institución estén clasificados en grupos y tengan paquetes aplicados, administrarlos desde entonces es una cuestión de cambiar la configuración del paquete una vez para todos los usuarios asignados al paquete. Puede elegir ajustar las directivas de un paquete antes o después de asignar usuarios al paquete.

Consulte [administrar paquetes de directivas en Microsoft Teams](manage-policy-packages.md) para obtener instrucciones paso a paso para asignar usuarios individuales a un paquete, asignar paquetes de forma masiva a hasta 20 usuarios, y administrar y actualizar las directivas vinculadas a cada paquete.
