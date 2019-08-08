---
title: Actualización Pro para Microsoft Teams | Recorrido
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
audience: admin
description: Use esta guía si se encuentra en una organización grande o si tiene una personalización de la implementación de Skype empresarial.
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3d34c111302c3e8de173b4c553589ab840495118
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36236042"
---
# <a name="upgrade-pro"></a>Actualizar Pro

Diseñado para organizaciones más grandes o para las implementaciones complejas de Skype empresarial (por ejemplo, implementaciones híbridas o de voz en la nube), actualice cuentas de Pro para un ciclo de vida de actualización más largo junto con diversos escenarios de actualización, entre los que se incluyen Microsoft Teams junto a Skype empresarial hasta que los equipos estén listos para su organización.

En tres fases, la actualización Pro cubre:

|**[Antes de la actualización](#pre-upgrade)** |**[Actualizar](#upgrade)** |**[Posterior a la actualización](#post-upgrade)** |
|---|---|---|
|Obtener el valor de Teams<ul><li>Listo su entorno</li><li>Adopción de equipos para la colaboración, las reuniones y/o las llamadas</li><li>Planear la actualización de Skype empresarial en Teams a lo largo del tiempo</li></ul> |Migrar usuarios de Skype empresarial<ul><li>Notificar y preparar a los usuarios</li><li>Mover usuarios al modo solo para equipos</li><li>Realizar un seguimiento del progreso de uso en función de objetivos</li></ul> | Amplifica tu ROI <ul><li>Supervisar la calidad o el estado de la red</li><li>Mantener la diversión de los usuarios</li><li>Planear la innovación de los equipos en curso</li></ul>|

> [!NOTE]
> Sabemos que su viaje a teams puede implicar el aprovechamiento de varios [modos](https://aka.ms/skypetoteams-coexist) y la actualización de grupos de usuarios en diferentes momentos, lo que le permitirá controlar la experiencia de actualización de usuario y mantener el impulso con Teams. <br><br>
Para ayudar a demostrar cómo puede desdoblar su viaje de actualización, hemos proporcionado un plan de muestra a continuación que define un recorrido pasando de Skype empresarial al modo **islas** y solo a teams. Además, el plan de ejemplo describe una organización que ha dividido a sus usuarios en cuatro grupos de actualización o _cohorts_. Con esta plantilla, personalice el plan para abarcar su viaje específico a Teams, incorporando los distintos [modos](https://aka.ms/skypetoteams-coexist) que va a usar y la cantidad de grupos de actualización a los que segmentar a los usuarios.

## <a name="pre-upgrade"></a>Antes de la actualización

**Prepare su organización para los equipos.** Para ayudar a garantizar una actualización correcta a Teams, es importante asignar tiempo adecuado para la preparación. Su organización no solo podrá empezar a alcanzar rápidamente el valor de Teams, sino que podrá acelerar la actualización de Skype empresarial tan pronto como se haya preparado el equipo para usted. Supervise la [Guía básica](https://aka.ms/O365Roadmap) de las mejoras previstas para los equipos. Esto le ayudará a identificar la escala de tiempo de actualización adecuada para su organización. Si ya ha habilitado Teams junto con Skype empresarial, use estas actividades previas a la actualización como punto de comprobación para validar la preparación de la organización antes de actualizar los usuarios a teams.

> [!Tip]
> Descargue el [Kit de actualización correcta](https://aka.ms/UpgradeSuccessKit) para los materiales de preparación de usuarios de plantillas, como las comunicaciones y las encuestas de usuarios, además de un plan de actualización de proyecto y un plan de pruebas piloto. Los elementos que están disponibles en el kit están marcados con un\*asterisco () en la lista de abajo.

### <a name="days-1ndash7-create-your-upgrade-plan-to-help-ensure-your-organization-is-set-up-for-long-term-success"></a>Días 1&ndash;7: crear un plan de actualización para asegurarse de que su organización está configurada para el éxito a largo plazo

|Paso||Resumen |Recursos |
|---|---|---|---|
|**1** |**Definir las partes interesadas** |Considere el alcance de su proyecto e identifique a las partes interesadas relevantes durante la preparación técnica y la preparación del usuario para impulsar la responsabilidad y el éxito. |[Dar de alta a los participantes](upgrade-enlist-stakeholders.md) |
|**2** |**Definir la visión del proyecto** |Su visión es el "panorama general" o el estado final eventual que responde a la pregunta "¿por qué estamos haciendo este proyecto?" Una visión ideal se dirige a los drivers empresariales de su organización y al valor de los usuarios, agregando perspectivas. |[Visión del proyecto](upgrade-define-project-scope.md#project-vision) |
|**3** |**Definir el ámbito del proyecto** |Es posible que su visión solo se pueda realizar a lo largo del tiempo, a través de varias fases. El ámbito del proyecto define el foco de su proyecto en este momento y sirve para mantener el equipo del proyecto centrado en sus tareas actuales, permitiéndole realizar su visión a largo plazo. |[Ámbito del proyecto](upgrade-define-project-scope.md#project-scope) |
|**4** |**Definir los objetivos del proyecto** |Sus objetivos definen el resultado deseado y le permiten medir el éxito del proyecto. Los objetivos se pueden definir como objetivos y resultados clave (OKRs), y las medidas de éxito del proyecto se pueden definir como indicadores clave de éxito (KSIs). Es esencial que obtenga una participación completa de las partes interesadas del proyecto al definir OKRs y KSIs, para garantizar que sienten una sensación de propiedad y a alinear estas medidas de éxito con las tareas del proyecto definidas. Los objetivos deben incluir una combinación de éxito técnico y centrado en el usuario. |[Objetivos del proyecto](upgrade-define-project-scope.md#project-goals) |
|**5** |**Identificar riesgos y planes de mitigación** |Es importante evaluar proactivamente posibles riesgos y definir un plan de mitigación para superar los problemas que puedan surgir, de modo que el proyecto pueda continuar con sus objetivos. Un registro de riesgos es una herramienta excelente para realizar un seguimiento de los riesgos del proyecto, junto con la probabilidad de que sean y su posible impacto, y la captura de su plan de mitigación. En la tabla siguiente se muestra un registro de riesgo de ejemplo. |[Riesgos y mitigación](upgrade-define-project-scope.md#risks-and-mitigation) |
|**6** |**Definir la escala de tiempo** |Establezca una escala de tiempo para hitos clave (por ejemplo, habilitar equipos junto a Skype empresarial para todos los usuarios o iniciar actualizaciones por fases de usuarios) además de la fecha de finalización. Una escala de tiempo definida ayuda a que el equipo del proyecto funcione a un estado final coherente e informa de la programación de trabajo de vuelta, lo que ayuda a garantizar el seguimiento del proyecto. Considere una escala de tiempo que no es demasiado acelerada (donde las tareas pueden estar en la lista). |[Escala](upgrade-define-project-scope.md#timeline)<br><br>[Paquete de actualización correcta](https://aka.ms/UpgradeSuccessKit)|
|**7** |**Definir la actualización adecuada de Skype empresarial y de equipos y la estrategia de coexistencia** |Como cliente existente de Skype empresarial, la transición completa a teams puede llevar algún tiempo. Sin embargo, puede empezar a obtener el valor de Teams hoy, lo que permite a los usuarios usar Teams junto con Skype empresarial. Dado que hay alguna funcionalidad superpuesta entre las dos aplicaciones, le recomendamos que revise los modos disponibles de coexistencia y actualización para determinar qué ruta de acceso es adecuada para su organización. Para obtener una experiencia óptima, pruebe su estrategia de coexistencia planificada antes de implementarla de manera generalizada para todos los usuarios. |[Comprender Microsoft Teams y la coexistencia e interoperabilidad de Skype empresarial](teams-and-skypeforbusiness-coexistence-and-interoperability.md)<br><br>[Elegir su recorrido de actualización](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)|

### <a name="days-8ndash15-evaluate-your-organizations-readiness-for-teams"></a>Días 8&ndash;15: evaluar la preparación de los equipos de su organización

|Paso | |Resumen |Recursos |
|---|---|---|---|
|**1** |**Evaluar el entorno existente para identificar los riesgos y requisitos** |Al evaluar su entorno, usted identifica los riesgos y los requisitos que influirán en la implementación general. Al identificar estos elementos de forma proactiva, puede ajustar su planificación para ayudar a garantizar el éxito. |[Evaluar el entorno antes de actualizar a teams](upgrade-plan-journey-evaluate-environment.md) |
|**2** |**Completar la incorporación técnica de Office 365 y Teams** |Aprovechamiento de listas de comprobación de incorporación existentes para identificar tareas y actividades para completar la preparación técnica de las capacidades de colaboración y voz con Teams. |[Preparar el servicio para la actualización a teams](upgrade-prepare-environment-prepare-service.md) |
|**3** |**Optimizar la red para equipos, especialmente para escenarios de medios en tiempo real** |Si está implementando audio, vídeo o reuniones, puede realizar algunos pasos adicionales para optimizar su red para esa funcionalidad. Teams usa tecnología de audio y vídeo (códecs) que puede&mdash;adaptarse y, por lo&mdash;tanto, funcionar mejor en la mayoría de las condiciones de la red. Para garantizar un rendimiento óptimo y coherente, debe preparar su red para los equipos. |[Preparar la red para actualizar a teams](upgrade-prepare-environment-prepare-network.md) |
|**4** |**Evaluar si la organización está preparada para el cambio** |Para obtener valor de Teams, los usuarios deben usarlo. Solo habilitar Teams no garantiza que logres tu objetivo. Los usuarios tienen diferentes casos de uso y distintos estilos de aprendizaje, y se adaptan a nuevas tecnologías a velocidades diferentes. Comprender su base de usuarios le permite preparar el nivel adecuado de educación para facilitar y acelerar la adopción de los usuarios. |[Preparación de los cambios de organización](upgrade-org-change-readiness.md#organizational-change-readiness) |
|**5** |**Preparar un plan de preparación de usuarios para definir cómo se comunicarán, entrenarán y proporcionarán soporte técnico a los usuarios** |Para garantizar la integración óptima de la nueva tecnología, use una combinación de mensajería de alcance amplio (con los casos de mensajería de visión/valor y de uso universal) y mensajería, formación y soporte adaptados a los roles y cohorts que haya definido y también a tu laggards, según corresponda. Este plan personalizado le ayudará a facilitar la adopción por parte de los usuarios al permitir que los usuarios se relacionen más rápidamente con los equipos, a la vez que demuestran sus necesidades. Se puede usar durante la fase piloto, la incorporación y la actualización a teams. |[Preparar un plan de preparación del usuario](upgrade-user-readiness.md)<br><br>[Paquete de actualización correcta](https://aka.ms/UpgradeSuccessKit)<br><br>[Aprendizaje en vídeo de Teams](https://support.office.com/article/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7?wt.mc_id=otc_home)<br><br>[Cambiar a Teams desde Skype Empresarial](https://support.office.com/article/Switch-to-Teams-from-Skype-for-Business-6295a0ae-4e8e-4bba-a100-64cc951cc964) |
|**6** |**Anunciar el lanzamiento pendiente de Microsoft Teams** |Comunicarse con los usuarios de forma anticipada ayuda a los usuarios a sentirse incluido, reduce la confusión genera un entusiasmo sobre Microsoft Teams, lo que ayuda a acelerar la actualización de Skype empresarial a lo largo del tiempo. | [Paquete de actualización correcta](https://aka.ms/UpgradeSuccessKit) |
|**7** |**Preparar el personal de TI para Teams** |Los administradores de inquilinos de Office 365, los clientes técnicos y el escritorio de soporte son responsables de conducir una experiencia de usuario de alta calidad. Esto incluye asegurarse de que su red está lista para admitir equipos, configurar equipos para los usuarios y ser capaz de solucionar y resolver los problemas que puedan surgir. |[Preparar el personal de TI para Microsoft Teams](https://docs.microsoft.com/microsoftteams/upgrade-prepare-it-pros)<br><br>[Paquete de actualización correcta](https://aka.ms/UpgradeSuccessKit) |

### <a name="days-16ndash60-run-a-pilot-to-confirm-that-your-organization-is-ready-and-inform-your-optimal-journey-to-teams"></a>Días 16&ndash;60: ejecutar un programa piloto para confirmar que su organización está preparada e informar a su óptimo viaje a los equipos

|Paso | |Resumen |Recursos |
|---|---|---|---|
|**1** |**Resumen de la logística piloto** |Una prueba piloto correcta define fechas de inicio y finalización, y objetivos claramente definidos para medir el éxito. Estos objetivos deberían alinearse con el ámbito de su proyecto más amplio y se usarán para informar a su camino hacia delante después de que el piloto haya finalizado. |[Resumen de la logística piloto](pilot-essentials.md#1-outline-pilot-logistics) |
|**2** |**Seleccionar los participantes de la prueba piloto y los escenarios de prueba** |Seleccione los participantes de la prueba piloto no basados únicamente en roles o personas, sino también en el proyecto y en el trabajo entre equipos. El programa piloto debe extenderse a las personas clave de ti, la formación y el Departamento de soporte técnico, de modo que pueda validar completamente la solución mientras optimiza los recursos de administración de proyectos. |[Seleccionar los participantes de la prueba piloto y los escenarios de prueba](pilot-essentials.md#2-select-your-pilot-participants-and-test-scenarios) |
|**3** |**Diseñar el plan de prueba y la encuesta de comentarios** |Identifique tareas claramente definidas para que los participantes los completen y una forma de compartir sus comentarios. Agrupe tareas en conjunto para ofrecer escenarios reales a sus usuarios, lo que muestra la relevancia para sus actividades diarias. |[Diseñar el plan de prueba y la encuesta de comentarios](pilot-essentials.md#3-design-your-test-plan-and-feedback-survey) |
|**4** |**Crear un plan de comunicaciones piloto** |Educar a los participantes de la fase piloto sobre lo que está ocurriendo, Cuándo y por qué se esperan. Para impulsar la diversión y la participación máxima, asegúrate de incluir la mensajería de valor de usuario además de vínculos a aprendizaje y asistencia donde los usuarios puedan obtener información adicional a medida que avanzan a través de la prueba piloto. |[Crear un plan de comunicaciones](pilot-essentials.md#4-create-your-communications-plan)<br><br>[Paquete de actualización correcta](https://aka.ms/UpgradeSuccessKit) |
|**5** |**Realizar la prueba piloto** |La realización de su piloto incluye comunicarse con sus usuarios, supervisar su red y uso para garantizar que el rendimiento de la red y la calidad de las llamadas permanezcan saludables, recopile comentarios de los participantes y revisando los vales del servicio de asistencia para preguntas relacionadas con Podrán. |[Realizar la prueba piloto](pilot-essentials.md#5-conduct-your-pilot) |
|**6** |**Evaluar aprendizajes y evaluar su plan de avance** |Reúna todas las encuestas de comentarios, las estadísticas de redes finales y las incidencias de soporte técnico para el análisis de sus objetivos y determine si va a implementar su plan de avance. |[Evaluar aprendizajes y evaluar su plan de avance](pilot-essentials.md#6-assess-learnings-and-evaluate-your-go-forward-plan) |

### <a name="day-60-until-upgrade-deploy-teams-in-coexistence-with-skype-for-business"></a>Día 60 hasta la actualización: implementar Teams en coexistencia con Skype empresarial

|Paso | |Resumen |Recursos |
|---|---|---|---|
|**1** |**Anunciar el lanzamiento oficial de Teams** |Comuníquese con sus usuarios sobre el inicio de su organización de Teams para garantizar el conocimiento y el valor de tierra y los beneficios de los usuarios. Considere la posibilidad de usar varias formas de comunicación, como un evento de lanzamiento y correo electrónico. |[Paquete de actualización correcta](https://aka.ms/UpgradeSuccessKit) |
|**2** |**Habilitar el modo de coexistencia adecuado para los usuarios** |Siga los pasos para establecer los modos de coexistencia correctos para su organización. |[Configurar su coexistencia y la configuración de actualización](setting-your-coexistence-and-upgrade-settings.md) |
|**3** |**Manténgase informado acerca de la guía básica de Teams** |Supervise la guía básica de Teams y evalúe continuamente la preparación de la organización para identificar el momento adecuado para que su organización se traslade a teams. |[Guía básica de Teams](https://aka.ms/teamsroadmap) |
|**4** |**Envía comunicaciones adicionales y contrata a los expertos de Teams para impulsar** la diversión y la adopción de equipos |Anime a la adopción por el usuario y mantenga la emoción de los equipos con comunicaciones y campeones continuos. |[Programa Microsoft 365 Champions](https://aka.ms/O365Champions) |

## <a name="upgrade"></a>Upgrade

**Haga que el funcionario se mueva a teams.** Cuando se actualizan los usuarios, se mueven al modo de coexistencia de **equipos** . Teams se convierte en la aplicación principal para conversaciones, reuniones, llamadas y colaboraciones, y el acceso a la aplicación de Skype empresarial está deshabilitado. Aunque los aspectos técnicos de esta fase son bastante sencillos, considere el efecto que el cambio puede tener en la experiencia del usuario y deje que los usuarios pasen oficialmente sus actividades de Skype empresarial a teams. Para reducir la necesidad de que los usuarios tengan experiencias diferentes con diferentes clientes, intenta limitar la ventana de actualización de un extremo a otro de 45 días.

### <a name="days-1ndash45-implement-your-upgrade-from-skype-for-business-to-teams"></a>Días 1&ndash;45: implementar la actualización de Skype empresarial en Teams

|Paso | |Resumen |Recursos |
|---|---|---|---|
|**1** |**Validar que ha completado las actividades anteriores a la actualización descritas anteriormente** |Asegúrese de que la actualización se realice correctamente al confirmar la finalización de todas las actividades de planificación y preparación. |Todas las anteriores |
|**2** |**Iniciar comunicaciones para los usuarios en el primer grupo de actualización** |Comience a ejecutar el plan de comunicación anterior, preliminar y posterior a la actualización para impulsar la detección, establecer expectativas y compartir la ventaja de los equipos con los usuarios con antelación a su actualización. |[Preparar un plan de preparación del usuario](upgrade-user-readiness.md)<br><br>[Paquete de actualización correcta](https://aka.ms/UpgradeSuccessKit)<br><br>[Aprendizaje en vídeo de Teams](https://support.office.com/article/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7?wt.mc_id=otc_home)<br><br>[Cambiar a Teams desde Skype Empresarial](https://support.office.com/article/Switch-to-Teams-from-Skype-for-Business-6295a0ae-4e8e-4bba-a100-64cc951cc964) |
|**3** |**Habilitar el modo de coexistencia para los equipos solo para los usuarios de su primer grupo de actualización** |Siga los pasos apropiados para su entorno de Skype empresarial para realizar la migración de usuarios técnicos. |[Actualización de Skype Empresarial Online a Microsoft Teams](upgrade-to-teams-execute-skypeforbusinessonline.md)<br><br>[Actualizar a teams desde una implementación híbrida de Skype empresarial](upgrade-to-teams-execute-skypeforbusinesshybrid.md)<br><br>[Actualizar desde una implementación local de Skype empresarial a teams](upgrade-to-teams-execute-skypeforbusinessonpremises.md) |
|**4** |**Repetir las actividades de actualización anteriores para los grupos de actualización restantes en un ciclo sucesivo** |Continúe con los planes de comunicaciones y actualice los grupos de usuarios en función de su plan. | |
|**5** |**Enviar encuestas posteriores a la actualización de comentarios a todos los usuarios** |Aproveche una encuesta de comentarios para recopilar comentarios y perspectivas de los usuarios. |[Paquete de actualización correcta](https://aka.ms/UpgradeSuccessKit) |

## <a name="post-upgrade"></a>Posterior a la actualización

**Maximice el valor para empresas con Teams.** Una vez que su organización se haya actualizado completamente a Teams, dedique un tiempo para evaluar el éxito con sus objetivos e implementar un plan para continuar el impulso.

### <a name="days-1ndash14-measure-the-success-of-your-upgrade"></a>Días 1&ndash;14: Mida el éxito de su actualización

|Paso | |Resumen |Recursos |
|---|---|---|---|
|**1** |**Evaluar la actualización inicial correcta** |Evaluar el progreso con respecto a los objetivos establecidos en la fase anterior a la actualización. |[Objetivos del proyecto](upgrade-define-project-scope.md#project-goals) |
|**2** |**Implemente un plan de mitigación para cualquier objetivo que no esté en el buen camino.** |Definir estrategias de corrección o de corrección de cursos para objetivos que no se cumplen. |[Objetivos del proyecto](upgrade-define-project-scope.md#project-goals) |

### <a name="ongoing"></a>Regulares

|Paso | |Resumen |Recursos |
|---|---|---|---|
|**1** |**Supervisar el estado y la calidad de la red** |Implementar un plan para supervisar y mitigar el estado de la red le ayudará a garantizar una experiencia de usuario positiva además de reducir las llamadas a su servicio de asistencia al cliente. |[Supervisar el estado y la calidad de la red](continue-journey.md#monitor-for-network-health-and-quality) |
|**2** |**Impulsar el impulso y la adopción de usuarios** |Anime a la adopción por el usuario y mantenga el entusiasmo de los equipos con un plan de adopción continua. |[Impulsar el impulso y la adopción de usuarios](continue-journey.md#drive-user-momentum-and-adoption) |
|**3** |**Prepararse para nuevas funcionalidades** |Establecer un ciclo de cambio en la organización le asegurará que está listo para administrar las mejoras de colaboración continuas y obtener el máximo valor. |[Prepararse para nuevas funcionalidades](continue-journey.md#prepare-for-new-functionality) |

> [!Note]
> Nuestro contenido de upgrade Pro está evolucionando continuamente. Asegúrese de consultar las instrucciones más recientes y lea el [blog](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog)de Teams.

> [!Important]
> Skype empresarial online se retirará el 31 de julio de 2021, después del cual ya no será accesible ni compatible. Para maximizar los beneficios y asegurarse de que su organización tenga el tiempo adecuado para implementar su actualización, le recomendamos que comience su viaje a Microsoft Teams hoy. Recuerde que una actualización correcta alinea la disposición de los usuarios y técnicos, así que asegúrese de aprovechar las instrucciones de este documento a medida que navega por Microsoft Teams.
