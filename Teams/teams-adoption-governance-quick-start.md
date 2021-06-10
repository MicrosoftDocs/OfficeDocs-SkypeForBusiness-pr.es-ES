---
title: Comenzar el inicio rápido para Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: karuanag
localization_priority: Normal
search.appverid: MET150
description: Inicio rápido que cubre las decisiones clave que tendrá que tomar para la fase 2 de su plan Microsoft Teams adopción.
f1.keywords:
- CSH
ms.custom:
- Adopt
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_Adopt
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: cd54902e00e984de740b7bbf6d0fd96e37e88aa9
ms.sourcegitcommit: df1eca90090c29eaaf7fd79bd8cc84c556f12b1e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/12/2020
ms.locfileid: "48424560"
---
# <a name="governance-quick-start-for-microsoft-teams"></a>Comenzar el inicio rápido para Microsoft Teams

Las siguientes actividades se realizarán simultáneamente y pueden implicar a todos o a parte de su equipo clave. Como práctica recomendada, aplazar las conversaciones de gobierno y seguridad a gran escala para después de completar la experimentación inicial con Teams. Es importante comprender cómo las decisiones de gobierno pueden afectar a la experiencia del usuario final y simplificarán las decisiones que tendrá que tomar en esa fecha posterior. Para esta fase hay algunas decisiones que deben tomarse. Para realizarlas correctamente, primero tendrá que responder a las siguientes preguntas:

- ¿Qué partes interesadas de su evaluación anterior son un buen candidato para participar en esta incorporación empresarial limitada?
- ¿Este individuo (o grupo de individuos) ha sugerido casos de uso que serían buenos candidatos para esta fase?  
- ¿Tienen suficiente interés de los empleados de su organización para ser primeros en adoptar y darle comentarios significativos y regulares? 

Para obtener más información, lea [Planear el](plan-teams-governance.md) gobierno en Teams y Planear la administración del ciclo de vida en [Teams](plan-teams-lifecycle.md).

## <a name="an-icon-representing-a-decision-pointdecisions"></a>![Un icono que representa un punto de decisión](media/teams-adoption-decision-icon.png)Decisiones

Tome las siguientes decisiones (en este momento, estas decisiones solo se aplican a la fase 2):

### <a name="decision-1-who-can-create-teams"></a>Decisión 1: Quién crear equipos 

Para los fines de esta fase, puede restringir quién es capaz de crear equipos a la población adoptante temprana, además del equipo principal del proyecto. Esto permitirá a los primeros usuarios crear equipos adicionales si es necesario. Supervisar este comportamiento le dará información clave para su amplia implementación.

### <a name="decision-2-teams-naming-conventions"></a>Decisión 2: Teams convenciones de nomenclatura 

Es probable que desee implementar algunas convenciones de nomenclatura para su amplia implementación de Teams y buscar nombres duplicados. En la fase 2 le sugerimos que implemente una convención de nomenclatura manual solo para sus proyectos iniciales. La práctica recomendada para esto es realizar una incorporación interactiva con el equipo de proyecto de los primeros usuarios y permitirles seleccionar su propio nombre. Esto le dará información sobre cómo piensan los empleados sobre su trabajo y será esencial para crear una convención de nomenclatura a mayor escala más adelante. (Información adicional sobre los elementos de una incorporación interactiva aparecerá más adelante en esta guía).

### <a name="decision-3-guest-access"></a>Decisión 3: Acceso de invitado

Según el ámbito y el tipo de proyecto y la naturaleza de su sector, permitir una colaboración segura con socios o proveedores puede ser una capacidad esencial que desea probar. Puede limitar quién puede agregar invitados a los equipos mediante los controles de inquilino adecuados y limitar los equipos que están abiertos a los invitados mediante etiquetas de confidencialidad. Además, puede asegurarse de que los invitados cumplan los requisitos de seguridad de la organización, como el uso de autenticación multifactor (MFA).

### <a name="decision-4-approved-apps"></a>Decisión 4: Aplicaciones aprobadas

El mejor uso de Teams incluye la integración de otras aplicaciones en la experiencia. Como mínimo, el equipo técnico debe habilitar las aplicaciones de primer nivel y las características de su Teams usuario. Según el caso de uso y otras aplicaciones usadas en su organización, puede optar por incluir aplicaciones adicionales como parte de su experimento controlado. Asegúrese de investigar cualquier aplicación de terceros para asegurarse de que cumplen los requisitos de seguridad y cumplimiento de su organización.

### <a name="decision-5-are-meetings-included-in-your-test"></a>Decisión 5: ¿Se incluyen las reuniones en la prueba? 

La Teams de reunión es de alta calidad, admite el chat de vídeo y reúne a sus empleados para que sean más eficaces. Consulte con su equipo técnico para asegurarse de que su entorno está listo para incluir reuniones voIP sencillas. Habilitar servicios de audioconferencia o de voz normalmente se excluiría de esta fase de la experimentación; sin embargo, eso depende del equipo principal del proyecto, su preparación técnica y el estado de otros servicios de voz o reunión de su organización. La preparación técnica debe incluir aspectos como el equipamiento de la sala de reuniones, los dispositivos y accesorios del usuario final y la red. Se recomienda incluir chats de vídeo y reuniones VoIP en la experimentación para obtener más valor de su Teams implementación. 

### <a name="decision-6-content-management-and-structure"></a>Decisión 6: Administración y estructura de contenido
Teams funciona mejor cuando los usuarios trabajan de un extremo a otro dentro de la plataforma , en lugar de exigirles que vuelvan continuamente a los sistemas y servicios heredados, y ofrece nuevas formas de trabajo que difieren de la manera en que los usuarios están acostumbrados. Como parte del experimento, trabaje con los participantes para considerar las estructuras de equipo y los canales que adoptan las formas multimodales de colaborar dentro de Teams y evite simplemente replicar estructuras de almacenamiento y carpetas existentes. Además, tenga en cuenta los requisitos de cumplimiento para el contenido almacenado fuera de los sistemas compatibles existentes, como la administración de registros o los sistemas de copia de seguridad.

### <a name="decision-7--data-security"></a>Decisión 7: Seguridad de datos

En preparación para su amplia implementación, puede optar por usar etiquetas de seguridad para clasificar los tipos de equipos de su entorno. Para los fines de este experimento, le recomendamos que consulte Plan de gobernanza en [Teams](plan-teams-governance.md) y asegúrese de que se ha establecido una directiva de retención básica en los datos de Teams en su Microsoft 365. Es posible que tenga que coordinar este trabajo con su equipo técnico porque Microsoft 365 derechos de administrador necesarios para completar este trabajo.

### <a name="decision-8-length-of-your-experiment"></a>Decisión 8: Duración del experimento

Una implementación Teams se realiza a un ritmo adecuado para garantizar el impulso, el enfoque y los aprendizajes adecuados. Le recomendamos que esta fase del proyecto tenga una duración de 60 días para asegurarse de que sus primeros usuarios completen ciclos empresariales suficientes. Extender la experimentación durante un tiempo demasiado largo aumenta el riesgo de un programa de cambio fallido; sin embargo, este tiempo variará para cada organización.  

![Un icono que representa el siguiente paso ](media/teams-adoption-next-icon.png) Siguiente: [Definir escenarios de uso](teams-adoption-define-usage-scenarios.md)
