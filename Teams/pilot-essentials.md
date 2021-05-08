---
title: Realizar un piloto de usuario para evaluar y probar cómo Microsoft Teams funcionará en su organización
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: Instrucciones para iniciar un Microsoft Teams piloto para explorar todo lo que Teams ofrecer a su organización, mientras sigue usando Skype Empresarial
localization_priority: Normal
ms.custom: Teams-upgrade-guidance
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: fe1cf351bb5d3d4a950b818505a8e5d93fa7ab27
ms.sourcegitcommit: 32e3bb588abcbeded2d885483384c06706b280eb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2021
ms.locfileid: "52282097"
---
# <a name="conduct-a-user-pilot"></a>Llevar a cabo un piloto del usuario

![Diagrama de viaje de actualización, que resalta Implementación e implementación](media/upgrade-banner-deployment.png "Fases del viaje de actualización, con énfasis en la fase implementación e implementación")

Este artículo forma parte de la fase de implementación e implementación de su viaje de actualización y comparte información para ejecutar un piloto eficaz. Antes de continuar, confirme que ha completado las siguientes actividades:

- [Ha incorporado a las partes interesadas del proyecto](upgrade-enlist-stakeholders.md)
- [Ha definido el ámbito del proyecto](./upgrade-define-project-scope.md)
- [Ha comprendido la coexistencia y la interoperabilidad de Skype Empresarial y Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Elegido el viaje de actualización](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Preparado el entorno](./upgrade-prepare-environment.md)
- [Preparar la organización](./upgrade-prepare-organization.md)

Al implementar nuevas tecnologías, su organización puede obtener un valor empresarial como el ahorro de costos, el cumplimiento de la seguridad, la satisfacción de los empleados y la eficiencia operativa, pero también puede afectar a la productividad de los usuarios y a la infraestructura organizativa (su red). Antes de habilitar nuevas tecnologías en toda la organización, realice un piloto de usuario formal. Al igual que pintaría un pequeño parche de color en una pared antes de pintar toda la sala, probaría una implementación amplia a menor escala realizando un piloto para validar la preparación técnica y del usuario, identificar y mitigar problemas y ayudar a garantizar una implementación exitosa en toda la organización.

Para lograr los resultados más realistas, el piloto debe implicar a usuarios reales, imitar cómo se comunican y colaborar, y comprobar las experiencias técnicas y de usuario. Tanto si su organización está pensando en ejecutar Skype Empresarial y Teams en paralelo, actualizar Teams a Teams en el futuro o implementar nuevas funciones como llamadas o conferencias, un piloto puede ayudar a identificar la ruta de acceso correcta para su organización. A veces se considera fase 1 de una implementación, el piloto ideal aprovecha la preparación que ya ha iniciado e implementa su plan definido con un grupo de usuarios dirigido.

| | |
|---|---|
| ![Un icono que representa un punto de decisión](media/audio_conferencing_image7.png) <br/>Punto de decisión|<ul><li>¿Cómo usará un piloto para informar sobre la dirección del proyecto?</li></ul> |
| ![Un icono que representa el siguiente paso](media/audio_conferencing_image9.png)<br/>Paso siguiente|<ul><li>Use las instrucciones siguientes para diseñar y ejecutar el piloto formal.</li></ul>|

> [!Tip]
> Use los recursos [piloto de ejemplo](https://aka.ms/UpgradeSuccessKit) para ayudar a diseñar las comunicaciones, el plan de pruebas y la encuesta de comentarios.

## <a name="1-outline-pilot-logistics"></a>1. Esquema de logística piloto

Un piloto exitoso ha definido fechas de inicio y finalización, y objetivos [claramente](upgrade-define-project-scope.md#project-goals) definidos para medir el éxito. Estos objetivos deben alinearse con el ámbito de su proyecto más amplio, como documentó cuando definió el ámbito del [proyecto,](upgrade-define-project-scope.md)y se usarán para informar sobre la ruta de acceso después de que el piloto haya terminado. También debe asegurarse de que ha incluido a las partes interesadas correctas durante la duración del proyecto. Le recomendamos que deje tiempo suficiente para ejecutar el piloto y evalúe su impacto: le recomendamos un mínimo de 30 días.

Empiece pequeño y agregue a su piloto según corresponda, ya sea agregando cargas de trabajo o características, o usuarios adicionales, haciendo tiempo para evaluar los resultados y ajustar el piloto a medida que se itera. Incluso puede optar por ejecutar pilotos posteriores a medida que se Teams nuevas características de la hoja de ruta.

## <a name="2-select-your-pilot-participants-and-test-scenarios"></a>2. Seleccione los participantes piloto y escenarios de prueba

Una de las tareas más importantes a la hora de planificar el programa piloto es hacer una selección meditada de los participantes. Recuerde que Teams está optimizado para el trabajo en equipo, así que asegúrese de seleccionar participantes piloto no solo basados en roles o personas, sino también en función de su proyecto y trabajo entre equipos. Un buen lugar para empezar es pedir a las partes interesadas y a los jefes de departamento proyectos reales que puede validar en Teams. Un ejemplo de un proyecto basado en roles podría ser usar Teams con su organización de ventas para asegurarse de que los representantes de campo puedan acceder fácilmente a los recursos que necesitan y compartir información con otros miembros del campo. Un ejemplo de trabajo basado en proyectos podría ser coordinar un evento de lanzamiento de producto con los equipos de marketing, formación, relaciones públicas y planificación de eventos. Independientemente de los escenarios que seleccione, el piloto debe extenderse a personas clave de TI, aprendizaje y su departamento de soporte técnico, para que pueda validar la solución a la vez que optimiza por completo los recursos de administración de proyectos.

> [!Tip]
> Al seleccionar los participantes Teams grupo piloto, asegúrese de incluir los usuarios principales de Skype Empresarial. Consulte a esos usuarios para comprender cómo usan Skype Empresarial hoy y, a continuación, cree un plan de prueba para comprobar que Teams puede satisfacer sus necesidades actuales.

## <a name="3-design-your-test-plan-and-feedback-survey"></a>3. Diseñar el plan de prueba y la encuesta de comentarios

Para una experiencia piloto correcta, dé a los participantes tareas claramente definidas para que las completen junto con una forma de compartir sus comentarios. Agrupar tareas para ofrecer escenarios reales a los usuarios, lo que demuestra la relevancia de sus actividades diarias. Deje que los casos de uso definidos en [Evaluar preparación para cambios organizativos](./upgrade-org-change-readiness.md) guíen su plan de pruebas.

Es posible que su organización elija pilotar todas las funciones a la vez o usar un enfoque gradual, por ejemplo, la colaboración piloto primero, después las reuniones y, después, el chat y las llamadas. Asegúrese de que tiene un canal de comentarios abierto para realizar un seguimiento del progreso y medir los resultados. Use una encuesta predefinida como una forma sencilla de capturar y evaluar los resultados piloto; el diseño de la encuesta debe basarse en los escenarios y características del plan de prueba.

## <a name="4-create-your-communications-plan"></a>4. Crear un plan de comunicaciones

Es crucial para el éxito del piloto que eduque a los participantes piloto sobre lo que está sucediendo, cuándo y por qué, y lo que se espera de ellos. Para impulsar la emoción y la máxima participación, asegúrese de incluir mensajes de valor de usuario, además de vínculos a aprendizaje y soporte técnico, donde los usuarios pueden obtener información adicional a medida que avanzan por el piloto. Estos son algunos recursos de ejemplo para empezar a usar su plan piloto de comunicaciones:

- [Recursos piloto,](https://aka.ms/UpgradeSuccessKit)incluidas plantillas de correo electrónico y preguntas de encuesta de comentarios de ejemplo
- [Cambiar a Teams desde Skype Empresarial](https://support.office.com/article/Switch-to-Teams-from-Skype-for-Business-6295a0ae-4e8e-4bba-a100-64cc951cc964), una guía de inicio rápido diseñada para ayudar a Skype Empresarial usuarios empezar a usar Teams

## <a name="5-conduct-your-pilot"></a>5. Realizar el piloto

Con toda la logística en su lugar, ya está listo para comenzar el piloto. Llevar a cabo el piloto incluye comunicarse con los usuarios, supervisar la red y el uso para garantizar que el rendimiento de la red y la calidad de las llamadas permanezcan en buen estado, recopilar comentarios de los participantes y revisar los vales del departamento de soporte técnico para preguntas relacionadas con Teams.

### <a name="tips-for-pilot-success"></a>Sugerencias éxito piloto

Las siguientes sugerencias pueden ayudar a garantizar el éxito del piloto:

- Antes de comenzar el piloto, confirme que todos los participantes piloto están habilitados para el [modo coexistencia] adecuado.
- ( https://aka.ms/SkypeToTeams-SetCoexistence) desea validar.
- Semanalmente, durante todo el piloto, reúnase con las partes interesadas del proyecto para revisar los comentarios de los usuarios, los datos de uso, los datos de red y los vales del departamento de soporte técnico para asegurarse de que el piloto se ejecuta sin problemas. Realice los ajustes necesarios.

### <a name="suggested-timeline"></a>Escala de tiempo sugerida

A continuación se sugiere una escala de tiempo para un proyecto piloto de 30 días:

- Una semana antes del lanzamiento piloto: Envíe la comunicación inicial a los usuarios piloto.
- Día 1: Enviar comunicación de inicio a los usuarios piloto.
- Día 7: Celebrar la primera reunión semanal de punto de comprobación del equipo del proyecto.
- Día 14: Envíe una comunicación de punto medio a los usuarios piloto y mantenga una reunión semanal de punto de comprobación del equipo del proyecto.
- Día 21: Celebrar una reunión semanal de punto de comprobación del equipo del proyecto.
- Día 30: Enviar comunicación final a los usuarios piloto.
- Días 31-45: Evalúe los resultados piloto y planee los pasos siguientes.

## <a name="6-assess-learnings-and-evaluate-your-go-forward-plan"></a>6. Evaluar aprendizajes y evaluar su plan de avance

Una vez completada la prueba piloto, es el momento de recopilar todas las encuestas de comentarios, estadísticas finales de la red y vales de soporte técnico para analizar sus objetivos y determinar si implementará su plan de avance. Es posible que encuentre que su organización está lista para una implementación amplia, o que desea extender el piloto a más usuarios, o desea volver a visitar el piloto más adelante después de mitigar cualquier preocupación que haya identificado. Recuerde que el piloto es una buena manera de predecir los resultados técnicos y de usuario en un _entorno_ controlado; tenga cuidado al avanzar demasiado rápido.

Si los resultados indican:

- Se han alcanzado los objetivos piloto **(por ejemplo,** la satisfacción del usuario y la calidad de la red), debe estar listo para continuar con la siguiente fase de la implementación. Según los objetivos del proyecto, este podría ser uno de los siguientes:
  - Extender el piloto a participantes adicionales
  - [Habilitar Teams junto Skype Empresarial (**modo Islas)** para parte o toda la organización](./setting-your-coexistence-and-upgrade-settings.md)
  - [Actualizar usuarios de Skype Empresarial a Teams **(solo Teams)** para parte o toda la organización](./setting-your-coexistence-and-upgrade-settings.md)
- El piloto no obtuvo los resultados que quería **(por ejemplo,** la satisfacción del usuario y la calidad de la red), dedó un tiempo para realizar los ajustes adecuados a su plan y volver a visitar el piloto.

> [!Tip]
> Alista a los participantes piloto como compañeros de prueba para ayudar a evangelizar e incorporar nuevos usuarios a Teams. Los defensores de los pares pueden relacionarse fácilmente con otros usuarios, compartir sus propias experiencias y aprendizajes, así como ofrecer soporte y orientación a sus compañeros. Obtenga más información sobre [los campeones](https://go.microsoft.com/fwlink/?linkid=859068) y cómo puede usarlos dentro de su propia implementación.