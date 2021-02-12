---
title: Realizar un piloto de usuario para evaluar y probar cómo funcionará Microsoft Teams en su organización
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: Guía para iniciar un piloto de Microsoft Teams para explorar todo lo que Teams puede ofrecer a su organización mientras sigue usando Skype Empresarial
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
ms.openlocfilehash: 4f74b3d59c226c3445fb317c22c29c67682d8107
ms.sourcegitcommit: 1e16c6c7112bdde03209c12468b5705ddd116a62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "49578323"
---
# <a name="conduct-a-user-pilot"></a>Llevar a cabo un piloto del usuario

![Diagrama de viaje de actualización, en el que se resalta implementación e implementación](media/upgrade-banner-deployment.png "Fases del viaje de actualización, con énfasis en la fase Implementación e Implementación")

Este artículo forma parte de la fase de implementación e implementación del viaje de actualización y comparte información para ejecutar una prueba piloto eficaz. Antes de continuar, confirma que has completado las siguientes actividades:

- [Ha incorporado a las partes interesadas del proyecto](upgrade-enlist-stakeholders.md)
- [Ha definido el ámbito del proyecto](https://aka.ms/SkypetoTeams-Scope)
- [Ha comprendido la coexistencia y la interoperabilidad de Skype Empresarial y Teams](https://aka.ms/SkypeToTeams-Coexist)
- [Ha elegido el viaje de actualización](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Preparado tu entorno](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [Ha preparado tu organización](https://aka.ms/SkypeToTeams-UserReadiness)

Mediante la implementación de nuevas tecnologías, su organización puede lograr valores empresariales como ahorros en costes, cumplimiento de seguridad, satisfacción de los empleados y eficiencia operativa, pero también puede afectar a la productividad de los usuarios y a la infraestructura organizativa (su red). Antes de habilitar la nueva tecnología en toda la organización, realice una prueba piloto de usuario formal. Al igual que pintaría un pequeño parche de color en una pared antes de pintar toda la sala, probaría una amplia implementación a menor escala realizando un piloto para validar la preparación técnica y del usuario, identificar y mitigar problemas, y ayudar a garantizar una implementación correcta a nivel de toda la organización.

Para lograr los resultados más realistas, el piloto debe involucrar a los usuarios reales, imitar cómo se comunican y colaborar, y comprobar las experiencias técnicas y de usuario. Tanto si su organización está pensando en ejecutar Skype Empresarial y Teams en paralelo, actualizar a Teams en el futuro o implementar nuevas funciones, como llamadas o conferencias, un piloto puede ayudar a identificar el camino correcto para su organización. A veces considerado la fase 1 de una implementación, el piloto ideal aprovecha la preparación que ya ha iniciado e implementa su plan definido con un grupo de usuarios específico.

| | |
|---|---|
| ![Un icono que representa un punto de decisión](media/audio_conferencing_image7.png) <br/>Punto de decisión|<ul><li>¿Cómo se usará un piloto para informar sobre la dirección del proyecto?</li></ul> |
| ![Un icono que representa el siguiente paso](media/audio_conferencing_image9.png)<br/>Paso siguiente|<ul><li>Use las siguientes instrucciones para diseñar y ejecutar un programa piloto formal.</li></ul>|

> [!Tip]
> Use los recursos [piloto de ejemplo](https://aka.ms/UpgradeSuccessKit) para ayudar a diseñar las comunicaciones, el plan de pruebas y la encuesta de comentarios.

## <a name="1-outline-pilot-logistics"></a>1. Esquema de logística piloto

Un piloto exitoso ha definido las fechas de inicio y finalización, y [objetivos claramente definidos](upgrade-define-project-scope.md#project-goals) para medir el éxito. Estos objetivos deben alinearse con el ámbito del proyecto más amplio, como documentó cuando definió el ámbito del [proyecto,](upgrade-define-project-scope.md)y se usarán para informar su ruta hacia adelante cuando el piloto haya terminado. También debe asegurarse de que ha incluido a las partes interesadas correctas durante todo el proyecto. Le recomendamos que deje tiempo suficiente para ejecutar el piloto y evalúe su impacto: recomendamos un mínimo de 30 días.

Empiece con poco y agregue a su programa piloto según corresponda, ya sea agregando cargas de trabajo o características, o con usuarios adicionales, con lo que necesita tiempo para evaluar los resultados y ajustar la prueba piloto mientras se itera. Incluso es posible que opte por ejecutar las pruebas piloto siguientes, ya que las nuevas características de Teams se lanzan según la hoja de ruta.

## <a name="2-select-your-pilot-participants-and-test-scenarios"></a>2. Seleccionar los participantes piloto y escenarios de prueba

Una de las tareas más importantes a la hora de planificar el programa piloto es hacer una selección meditada de los participantes. Recuerde que Teams está optimizado para el trabajo en equipo, por lo que debe asegurarse de seleccionar a los participantes piloto no solo en función de los roles o personas, sino también en función del trabajo entre equipos y el proyecto. Un buen punto de empezar es pedir a las partes interesadas y a los jefes de departamento proyectos reales que puede validar en Teams. Un ejemplo de proyecto basado en roles podría ser usar Teams con su organización de ventas para asegurarse de que los representantes de campo pueden obtener acceso fácilmente a los recursos que necesitan y compartir información con otros miembros del campo. Un ejemplo de trabajo basado en proyectos puede coordinar un evento de lanzamiento de producto con los equipos de marketing, formación, relaciones públicas y planificación de eventos. Independientemente de los escenarios que seleccione, el programa piloto debería ampliarse a personas clave en TI, formación y su departamento de soporte técnico, para que pueda validar cuidadosamente la solución al tiempo que optimiza completamente los recursos de administración de proyectos.

> [!Tip]
> Al seleccionar los participantes del grupo piloto de Teams, asegúrese de incluir a los usuarios principales de Skype Empresarial. Consulte a esos usuarios para comprender cómo usan Skype Empresarial hoy y, a continuación, cree un plan de pruebas para comprobar que Teams puede satisfacer sus necesidades actuales.

## <a name="3-design-your-test-plan-and-feedback-survey"></a>3. Diseñar el plan de pruebas y la encuesta de comentarios

Para obtener una experiencia piloto satisfactoria, dé a los participantes tareas definidas claramente para que las completen junto con una forma de compartir sus comentarios. Agrupar tareas para ofrecer escenarios reales a los usuarios y demostrar su relevancia a sus actividades diarias. Deje que los casos de uso definidos en Evaluar la disponibilidad [de cambios organizativos](https://aka.ms/OrgReadiness) guíen su plan de pruebas.

Su organización puede optar por pilotar todas las funciones a la vez o utilizar un enfoque gradual, por ejemplo, la colaboración piloto primero, luego las reuniones, después el chat y las llamadas. Asegúrese de que tiene un canal de comentarios abierto para realizar un seguimiento del progreso y medir los resultados. Use una encuesta predefinida como una forma sencilla de capturar y evaluar los resultados piloto; el diseño de la encuesta debe basarse en los escenarios y características de su plan de pruebas.

## <a name="4-create-your-communications-plan"></a>4. Crear su plan de comunicaciones

Es crucial para el éxito del programa piloto que enseñe a los participantes piloto sobre lo que está sucediendo, cuándo y por qué, y lo que se espera de ellos. Para impulsar la emoción y la máxima participación, asegúrese de incluir la mensajería de valor de usuario además de vínculos de aprendizaje y soporte técnico en los que los usuarios pueden obtener información adicional a medida que avanzan en el programa piloto. Estos son algunos recursos de ejemplo para empezar a trabajar con su plan piloto de comunicaciones:

- [Recursos piloto, incluidas plantillas](https://aka.ms/UpgradeSuccessKit)de correo electrónico y preguntas de encuesta de comentarios de ejemplo
- [Cambiar a Teams desde Skype Empresarial,](https://support.office.com/article/Switch-to-Teams-from-Skype-for-Business-6295a0ae-4e8e-4bba-a100-64cc951cc964)una guía de inicio rápido diseñada para ayudar a los usuarios de Skype Empresarial a empezar a usar Teams

## <a name="5-conduct-your-pilot"></a>5. Realizar la prueba piloto

Con toda la logística ya preparada, ya está listo para comenzar el piloto. Dirigir el programa piloto incluye comunicarse con los usuarios, supervisar su red y su uso para garantizar que el rendimiento de la red y la calidad de las llamadas permanecen en buen estado, recopilar comentarios de los participantes y revisar las solicitudes del departamento de soporte técnico para preguntas relacionadas con Teams.

### <a name="tips-for-pilot-success"></a>Sugerencias para el éxito de un piloto

Las siguientes sugerencias pueden ayudar a garantizar el éxito de la prueba piloto:

- Antes de comenzar el piloto, confirme que todos los participantes piloto están habilitados para el [modo de coexistencia] adecuado.
- (desea https://aka.ms/SkypeToTeams-SetCoexistence) validar.
- Semanalmente, durante el piloto, reúnase con las partes interesadas del proyecto para revisar los comentarios de los usuarios, los datos de uso, los datos de red y los vales del departamento de soporte técnico para garantizar que la prueba piloto se ejecute sin problemas. Realice los ajustes necesarios.

### <a name="suggested-timeline"></a>Escala de tiempo sugerida

A continuación se sugiere una escala de tiempo para un proyecto piloto de 30 días:

- Una semana antes del lanzamiento piloto: Enviar la comunicación inicial a los usuarios piloto.
- Día 1: Enviar comunicación de inicio a los usuarios piloto.
- Día 7: Mantenga la primera reunión semanal de control del equipo del proyecto.
- Día 14: Envíe una comunicación de punto medio a los usuarios piloto, mantenga una reunión semanal de control del equipo del proyecto.
- Día 21: Mantenga una reunión semanal de control del equipo del proyecto.
- Día 30: Enviar la comunicación final a los usuarios piloto.
- Días 31-45: Evaluar los resultados piloto y planear los pasos siguientes.

## <a name="6-assess-learnings-and-evaluate-your-go-forward-plan"></a>6. Evaluar los aprendizajes y su plan de desarrollo

Una vez completado el piloto, es el momento de recopilar todas las encuestas de comentarios, las estadísticas finales de red y las vales de soporte técnico para analizar sus objetivos y determinar si implementará su plan de futuro. Es posible que descubra que su organización está lista para una implementación amplia, o desea ampliar el piloto a más usuarios, o desea volver a visitar el piloto en una fecha posterior después de que cualquier preocupación que ha identificado se haya atenido. Recuerde que el programa piloto es una buena manera de predecir resultados técnicos y de usuario en un _entorno_ controlado; tenga cuidado al avanzar demasiado rápido.

Si los resultados indican:

- Se han alcanzado sus objetivos piloto **(por ejemplo,** la satisfacción del usuario y la calidad de la red), debe estar listo para continuar con la siguiente fase del lanzamiento. Dependiendo de los objetivos del proyecto, este podría ser uno de los siguientes:
  - Extender el piloto a otros participantes
  - [Habilitar Teams junto con Skype Empresarial (modo **islas)** para algunas o todas las organizaciones](https://aka.ms/SkypeToTeams-SetCoexistence)
  - [Actualizar usuarios de Skype Empresarial a Teams (modo **Solo** equipos) para algunas o todas las organizaciones](https://aka.ms/SkypeToTeams-SetCoexistence)
- El piloto no ha logrado los resultados que deseaba **(por ejemplo,** la satisfacción del usuario y la calidad de la red), dedifique el tiempo necesario para realizar los ajustes adecuados a su plan y vuelva a ver el piloto.

> [!Tip]
> Ensalce a sus participantes piloto como compañeros de campeones para ayudar a evangeliste e incorporar nuevos usuarios a Teams. Los colegas campeones pueden relacionarse fácilmente con otros usuarios, compartir sus propias experiencias y aprendizajes, y ofrecer soporte técnico y orientación a sus compañeros. Obtenga más información [sobre los campeones](https://go.microsoft.com/fwlink/?linkid=859068) y cómo puede usarlos en su propia implementación.
