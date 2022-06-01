---
title: Realizar una prueba piloto de usuario para evaluar y probar cómo funcionará Microsoft Teams en su organización
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: Instrucciones para iniciar un Microsoft Teams piloto para explorar todo lo que Teams pueden ofrecer a su organización, mientras sigue usando Skype Empresarial
ms.localizationpriority: medium
ms.custom: Teams-upgrade-guidance
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ae69bab918a9c8bd542e5ec70a95df7544677d8d
ms.sourcegitcommit: 2b1290b763c73f64c84c7568b16962e4ae48acf6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/01/2022
ms.locfileid: "65823229"
---
# <a name="conduct-a-user-pilot"></a>Llevar a cabo un piloto del usuario

![Diagrama de recorrido de la actualización, que resalta Implementación e implementación.](media/upgrade-banner-deployment.png "Fases del recorrido de la actualización, con énfasis en la fase de implementación e implementación")

Este artículo forma parte de la fase de implementación e implementación del recorrido de la actualización y comparte información para ejecutar una prueba piloto eficaz. Antes de continuar, confirma que has completado las siguientes actividades:

- [Ha incorporado a las partes interesadas del proyecto](upgrade-enlist-stakeholders.md)
- [Ha definido el ámbito del proyecto](./upgrade-define-project-scope.md)
- [Ha comprendido la coexistencia y la interoperabilidad de Skype Empresarial y Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Elige tu viaje de actualización](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Preparado para su entorno](./upgrade-prepare-environment.md)
- [Preparado para su organización](./upgrade-prepare-organization.md)

Mediante la implementación de nuevas tecnologías, su organización puede obtener valor empresarial, como ahorros en costes, cumplimiento de seguridad, satisfacción de los empleados y eficiencias operativas, pero también puede afectar a la productividad de los usuarios y a la infraestructura organizativa (su red). Antes de habilitar la nueva tecnología en toda la organización, realice un piloto formal de usuario. Al igual que pintaría un pequeño parche de color en una pared antes de pintar toda la sala, probaría una amplia implementación a menor escala realizando un piloto para validar la preparación técnica y de usuario, identificar y mitigar problemas, y ayudar a garantizar una implementación exitosa para toda la organización.

Para lograr los resultados más realistas, el programa piloto debe implicar a los usuarios reales, imitar la forma en que se comunican y colaborar, y comprobar las experiencias técnicas y de usuario. Si su organización está pensando en ejecutar Skype Empresarial y Teams en paralelo, actualizar a Teams en el futuro o implementar nuevas funciones, como llamadas o conferencias, un piloto puede ayudar a identificar el camino correcto para su organización. A veces se considera la fase 1 de una implementación, la prueba piloto ideal aprovecha la preparación que ya ha iniciado e implementa el plan definido con un grupo de usuarios dirigido.

|&nbsp; | &nbsp;|
|---|---|
| ![Un icono que representa un punto de decisión.](media/audio_conferencing_image7.png) <br/>Punto de decisión|<ul><li>¿Cómo usará un piloto para informar la dirección del proyecto?</li></ul> |
| ![Un icono que representa el paso siguiente.](media/audio_conferencing_image9.png)<br/>Paso siguiente|<ul><li>Use las siguientes instrucciones para diseñar y ejecutar el piloto formal.</li></ul>|

> [!Tip]
> Use los [recursos piloto](https://aka.ms/UpgradeSuccessKit) de ejemplo para ayudar a diseñar las comunicaciones, el plan de pruebas y la encuesta de comentarios.

## <a name="1-outline-pilot-logistics"></a>1. Esquema de logística piloto

Un piloto exitoso ha definido fechas de inicio y finalización, y [objetivos claramente definidos](upgrade-define-project-scope.md#project-goals) para medir el éxito. Estos objetivos deben alinearse con el ámbito de su proyecto más amplio, como documentó cuando [definió el ámbito del proyecto](upgrade-define-project-scope.md) y se usarán para informar la ruta hacia adelante después de que el piloto haya terminado. También debe asegurarse de que ha incluido a las partes interesadas adecuadas durante todo el proyecto. Querrá asegurarse de permitir tiempo suficiente para ejecutar el piloto y evaluar su impacto: se recomienda un mínimo de 30 días.

Empiece de forma pequeña y agréguelo al piloto según corresponda, ya sea agregando cargas de trabajo o características, o usuarios adicionales, haciendo tiempo para evaluar los resultados y ajustar el piloto a medida que se itera. Incluso puede optar por ejecutar pilotos posteriores a medida que se publiquen nuevas características de Teams según la hoja de ruta.

## <a name="2-select-your-pilot-participants-and-test-scenarios"></a>2. Seleccionar los participantes piloto y los escenarios de prueba

Una de las tareas más importantes a la hora de planificar el programa piloto es hacer una selección meditada de los participantes. Recuerde que Teams está optimizado para el trabajo en equipo, así que asegúrese de seleccionar participantes piloto no solo basándose en roles o roles, sino también en función de su proyecto y trabajo entre equipos. Un buen punto de partida es pedirles a las partes interesadas y a los jefes de departamento proyectos reales que puede validar en Teams. Un ejemplo de un proyecto basado en roles podría ser usar Teams con su organización de ventas para asegurarse de que los representantes de campo puedan acceder fácilmente a los recursos que necesitan y compartir información con otros miembros del campo. Un ejemplo de trabajo basado en proyectos podría ser coordinar un evento de lanzamiento de producto con los equipos de marketing, formación, relaciones públicas y planificación de eventos. Sea cual sea el escenario que seleccione, el programa piloto debe extenderse a las personas clave de TI, aprendizaje y su departamento de soporte técnico, para que pueda validar la solución a la vez que optimiza completamente los recursos de administración de proyectos.

> [!Tip]
> Al seleccionar a los participantes del grupo piloto Teams, asegúrese de incluir los usuarios principales de Skype Empresarial. Póngase en contacto con esos usuarios para comprender cómo usan Skype Empresarial hoy y, a continuación, cree un plan de pruebas para comprobar que Teams pueden satisfacer sus necesidades actuales.

## <a name="3-design-your-test-plan-and-feedback-survey"></a>3. Diseñar el plan de pruebas y la encuesta de comentarios

Para una experiencia piloto exitosa, proporcione a los participantes tareas claramente definidas para completarlas junto con una forma de que compartan sus comentarios. Agrupe tareas para ofrecer escenarios del mundo real a los usuarios, lo que demuestra la relevancia de sus actividades diarias. Deje que los casos de uso que definió en [Evaluar la preparación del cambio organizativo guíen](./upgrade-org-change-readiness.md) el plan de pruebas.

La organización puede probar todas las funciones a la vez o usar un enfoque gradual, por ejemplo, la colaboración piloto en primer lugar, después las reuniones y, después, el chat y las llamadas. Asegúrese de que tiene un canal de comentarios abierto para realizar un seguimiento del progreso y medir los resultados. Use una encuesta predefinida como una forma sencilla de capturar y evaluar los resultados piloto; el diseño de la encuesta debe basarse en los escenarios y características de su plan de pruebas.

## <a name="4-create-your-communications-plan"></a>4. Crear su plan de comunicaciones

Es crucial para el éxito de su piloto que eduque a los participantes piloto sobre lo que está sucediendo, cuándo y por qué, y lo que se espera de ellos. Para fomentar la emoción y la máxima participación, asegúrese de incluir mensajes de valor del usuario, además de vínculos a formación y soporte técnico donde los usuarios pueden obtener información adicional a medida que progresan a través del piloto. Estos son algunos recursos de ejemplo para empezar a usar su plan piloto de comunicaciones:

- [Recursos piloto](https://aka.ms/UpgradeSuccessKit), incluidas plantillas de correo electrónico y ejemplos de preguntas de encuesta de comentarios
- [Cambiar a Teams desde Skype Empresarial](https://support.office.com/article/Switch-to-Teams-from-Skype-for-Business-6295a0ae-4e8e-4bba-a100-64cc951cc964), una guía de inicio rápido diseñada para ayudar a Skype Empresarial usuarios a empezar a usar Teams

## <a name="5-conduct-your-pilot"></a>5. Dirigir el piloto

Con toda la logística en su lugar, ya está listo para comenzar su piloto. Realizar el programa piloto incluye la comunicación con los usuarios, supervisar la red y el uso para garantizar que el rendimiento de la red y la calidad de las llamadas permanecen en buen estado, recopilar comentarios de los participantes y revisar las incidencias del departamento de soporte técnico para preguntas relacionadas con Teams.

### <a name="tips-for-pilot-success"></a>Sugerencias para el éxito piloto

Las siguientes sugerencias pueden ayudar a garantizar el éxito de la prueba piloto:

- Antes de comenzar el piloto, confirme que todos los participantes piloto están habilitados para el [modo de coexistencia] adecuado
- (https://aka.ms/SkypeToTeams-SetCoexistence) quieres validar.
- Semanalmente, en todo el programa piloto, reúnase con las partes interesadas del proyecto para revisar los comentarios de los usuarios, los datos de uso, los datos de red y las solicitudes del departamento de soporte técnico para asegurarse de que el piloto se ejecuta sin problemas. Realice los ajustes necesarios.

### <a name="suggested-timeline"></a>Escala de tiempo sugerida

A continuación se sugiere una escala de tiempo para un proyecto piloto de 30 días:

- Una semana antes del lanzamiento del piloto: envíe la comunicación inicial a los usuarios piloto.
- Día 1: Enviar comunicación de lanzamiento a los usuarios piloto.
- Día 7: Mantenga la primera reunión semanal de control del equipo del proyecto.
- Día 14: Envíe una comunicación de punto medio a los usuarios piloto y mantenga una reunión semanal de control del equipo del proyecto.
- Día 21: Mantenga una reunión semanal de control del equipo del proyecto.
- Día 30: Enviar la comunicación final a los usuarios piloto.
- Días 31 a 45: Evaluar los resultados piloto y planear los pasos siguientes.

## <a name="6-assess-learnings-and-evaluate-your-go-forward-plan"></a>6. Evaluar los aprendizajes y evaluar su plan de avance

Una vez completado el piloto, es el momento de recopilar todas las encuestas de comentarios, estadísticas de red finales y vales de apoyo para analizar sus objetivos y determinar si va a implementar su plan de avance. Es posible que descubra que su organización está lista para una implementación amplia, que desea ampliar el piloto a más usuarios, o que desea volver a ver el piloto en una fecha posterior después de que se hayan mitigado las inquietudes que ha identificado. Recuerde que el piloto es una excelente manera de predecir resultados técnicos y de usuario en un entorno _controlado_ ; piense en saltar hacia delante demasiado rápido.

Si los resultados indican:

- **Sus objetivos piloto (por ejemplo, la satisfacción del usuario y la calidad de la red) se han logrado**, debe estar listo para continuar con la siguiente fase de su implementación. Dependiendo de los objetivos del proyecto, este podría ser uno de los siguientes:
  - Extender el piloto a otros participantes
  - [Habilitar Teams junto con Skype Empresarial (modo **Islas**) para toda la organización o parte de ella](./setting-your-coexistence-and-upgrade-settings.md)
  - [Actualización de usuarios de Skype Empresarial a Teams (**modo solo Teams**) para toda la organización o parte de ella](./setting-your-coexistence-and-upgrade-settings.md)
- **El piloto no logró los resultados deseados (por ejemplo, satisfacción del usuario y calidad de la red),** tómese tiempo para realizar los ajustes adecuados a su plan y volver a ver el piloto.

> [!Tip]
> Incluya a los participantes piloto como expertos de compañeros para ayudar a evangelizar e incorporar nuevos usuarios a Teams. Los expertos de pares pueden relacionarse fácilmente con otros usuarios, compartir sus propias experiencias y aprendizajes y ofrecer soporte técnico y orientación a sus compañeros. Obtén más información sobre [los expertos](
https://adoption.microsoft.com/become-a-champion/) y cómo podrías usarlos en tu propio lanzamiento.