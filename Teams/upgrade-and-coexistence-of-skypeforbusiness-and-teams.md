---
title: Viaje de actualización y coexistencia de Skype para empresas y Teams de Microsoft
author: arachmanGitHub
ms.author: MyAdvisor
manager: serdars
ms.date: 04/04/2018
ms.topic: article
ms.service: msteams
ms.reviewer: lehewe
description: Detalles de Skype para trayectos de actualización a los equipos de Skype para empresas con escenarios de ejemplo y modos y opciones de coexistencia de negocios y Teams de Microsoft.
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 46967004ec571e593ea3f73e213c3d0e5b801f86
ms.sourcegitcommit: ffca287cf70db2cab14cc1a6cb7cea68317bedd1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/05/2018
---
# <a name="upgrade-journey-and-coexistence-of-skype-for-business-and-microsoft-teams"></a>Viaje de actualización y coexistencia de Skype para empresas y Teams de Microsoft

Como un Skype existente para clientes de negocios, la transición completa a equipos podría tardar algún tiempo. Sin embargo, puede empezar a concretar el valor de los equipos en la actualidad, al permitir que los usuarios utilicen equipos junto con Skype para el negocio. Dado que hay algunas funciones superpuestas entre las dos aplicaciones, se recomienda que revise los modos de actualización disponibles para ayudar a determinar qué ruta de acceso es adecuado para su organización. Por ejemplo, podría optar por habilitar todas las cargas de trabajo en ambas soluciones sin interoperabilidad. O bien, si decide administrar la experiencia del usuario, introduciendo gradualmente capacidades de equipos o dirigidos a grupos de usuarios para seleccionadas funciones, hasta que su organización está preparada actualizar todos los equipos.

Al igual que con cualquier implementación, recomendamos encarecidamente realizar una [prueba piloto de su plan previsto](pilot-essentials.md) con un grupo seleccionado de usuarios antes de distribuir los equipos a su organización más amplia. Recuerde que la introducción de nueva tecnología puede ser disruptiva para los usuarios. Tómese tiempo para evaluar la preparación del usuario e implementar un plan de formación para mantener a los usuarios que saben y acelerar su aceptación de los equipos y comunicación. 

> [!IMPORTANT]
> Skype para el negocio a equipos de viaje actualización rápida evolución. Este artículo le ayudará a comprender la próxima actualización de los equipos, pero no incluye instrucciones de upgrade end-to-end. Una correcta actualización de Skype para empresas incluirá las actividades centradas en preparación técnica y del usuario. Estamos trabajando en esta guía ahora y se podrá ser publicarlo pronto.
 
## <a name="upgrade-and-coexistence-modes-defined"></a>Actualización y coexistencia de los modos definidos
Como ayuda para guiar el proceso de toma de decisiones, familiarícese con los distintos modos, conceptos y terminología relevante para la actualización de Skype para el negocio a los equipos.

### <a name="skype-for-business-with-teams-collaborationndashonly-mode"></a>Skype para empresas con la colaboración de equipos&ndash;modo sólo

En este modo, equipos está configurado para admitir equipos y basada en canales, conversaciones con charlas privadas, llamada y reuniones deshabilitadas.

Este modo es una excelente manera de presentar los equipos en su entorno mientras sigue Aproveche su inversión existente en Skype para empresas. 

### <a name="skype-for-business-with-teams-collaboration-and-meetings-mode"></a>Skype para empresas con la colaboración de equipos y modo de reuniones
Junto con el uso de los equipos para los equipos y conversaciones de canales en este modo, los usuarios empiezan a utilizar equipos para programar y llevar a cabo sus reuniones. Charlas privadas y voz y vídeo llamada permanecen en Skype para el negocio.

Si su organización necesita las funciones que proporciona equipos para reuniones, pero el negocio requiera mantener capacidades de voz de empresa en Skype para empresas, puede configurar los equipos para ofrecer Skype para empresas con la colaboración de equipos y reuniones capacidades para toda la organización (o algunas partes del mismo).

### <a name="islands-mode"></a>Modo de islas
Este es el modo predeterminado. Se utilizar para implementar equipos independientemente de Skype para el negocio. 

En este modo, los usuarios de equipos pueden utilizar inmediatamente equipos con todas sus capacidades con otros usuarios de equipos, mientras que otros usuarios puedan seguir utilizando Skype para el negocio y seguir siendo productivos sin ningún impacto en cómo usan Skype para los negocios hoy en día.

> [!NOTE]
> Modo de islas incluye interoperabilidad temporal unidireccional que permite la interoperabilidad de charla desde equipos a Skype para el negocio cuando se cumplen las condiciones siguientes:
> - El usuario de los equipos es alojado en y habilitado para Skype para los negocios en línea.
> - El Skype para usuarios de empresa no ha utilizado nunca los equipos (o no tiene licencia para equipos).
>
> Este modo es útil cuando desea que los usuarios que utilizan principalmente equipos para conectarse con otros usuarios de la organización que todavía utilizan Skype para empresas sólo.
>
> Después de que los usuarios que previamente utilizan Skype sólo para negocios empiecen a utilizar los equipos, todas sus conversaciones de otros usuarios de equipos llegarán en equipos. Estos usuarios se cambia al modo de islas. Desde ese punto, se deben mantener ejecutando equipos para garantizar que permanecen conectados con los demás usuarios de los equipos de la organización.

### <a name="teams-only-mode"></a>Modo de sólo equipos
En este modo actualizado, el Skype para Business client ya no proporciona mensajería instantánea básica, indicadores de presencia, chat, llamada o capacidades de reunión. Los usuarios que trabajan en modo actualizado deben utilizar equipos como su herramienta principal de comunicaciones y colaboración.

Los usuarios que están preparados para utilizar equipos como su herramienta principal de comunicaciones y colaboración pueden actualizarse como sólo los equipos de los usuarios.

Un usuario actualizado sólo puede utilizar el Skype para Business client para unir Skype existente para reuniones de negocios o reuniones en Skype para empresas organizados por usuarios no actualizada o partes externas. Un usuario actualizado puedan continuar comunicándose con otros usuarios de la organización que aún utilizan Skype para el negocio mediante las capacidades de interoperabilidad entre los equipos y Skype para el negocio.

### <a name="skype-for-businessndashonly-mode"></a>Skype para empresas&ndash;modo sólo
Los usuarios que deban permanecer en Skype para negocios pueden configurarse como Skype para empresas&ndash;sólo a los usuarios. Los usuarios configurados en este modo se podrán utilizar los equipos y podrán comunicarse con sólo los equipos de los usuarios mediante las capacidades de interoperabilidad entre los equipos y Skype para el negocio.

## <a name="upgrade-and-coexistence-building-blocks"></a>Bloques de creación de actualización y coexistencia
Para preparar formalmente la organización de su viaje a los equipos, debe empezar a planear para los escenarios de actualización que eventualmente permitirá a su organización Aceptar completamente los equipos como solución de colaboración y comunicaciones únicos.

Cuando algunos de los usuarios están listos utilizar sólo equipos para sus comunicaciones diarias y la colaboración necesita, puede empezar a actualizar estos usuarios a equipos habilitando el modo sólo equipos para ellos.

Si no es viable para mover a los equipos de toda la organización, puede iniciar adoptando totalmente los equipos como una solución de colaboración del grupo primero manteniendo Skype para empresas como soluciones de comunicaciones unificadas de su organización. Otra opción es empezar a pasar las reuniones a los equipos además de incorporar capacidades de colaboración del grupo de equipos, mientras que el resto de las capacidades de comunicaciones unificadas en Skype para el negocio.

![Una captura de pantalla de actualización de bloques de creación de Skype para el negocio a equipos, formada por Skype para empresas con la colaboración de equipos&ndash;modo único, Skype para empresas con la colaboración de equipos y modo de reuniones, modo de islas, modo sólo equipos y Skype para Business&ndash;sólo modo.](media/upgrade_and_coexistence_building_block.png)

La tabla siguiente compara los modos de actualización y coexistencia.

|Modo de  |Situación  |Objetivos a corto plazo  |Ventajas  |Advertencias  |
|---------|---------|---------|---------|---------|
|Skype para empresas con la colaboración de equipos sólo |Skype para la implementación de negocios con requisitos que aún no están cumplidos por equipos (por ejemplo, cumplimiento de normas avanzada)<br><br>Necesidad de largo plazo o compromiso de Skype para empresas|Inicio adopción de equipos rápidamente, centrándose en primer lugar en la colaboración en grupo<br><br> Desea mantener todas las cargas de trabajo de comunicaciones unificadas en Skype para el negocio por ahora|Sin capacidades superpuestas entre equipos y Skype para empresas<br><br>Charla y mensajería instantánea, residirá en Skype para empresas (ligado a llamar)<br><br>|
|Skype para empresas con la colaboración de equipos y reuniones |Skype para la implementación de negocios con un uso considerable de enterprise voice y requisitos que aún no se cumplen mediante una llamada a los equipos<br><br>Necesidad de largo plazo o compromiso de Skype para empresas<br><br>Que esté utilizando un servicio de reunión de terceros|Iniciar rápidamente, adopción de equipos va más allá de la colaboración en grupo<br><br>Mejorar la experiencia de las reuniones de los usuarios|Sin capacidades superpuestas<br><br>Reuniones de gran valor en equipos (WebRTC, grabaciones de la reunión de nube etc.)|Charla y mensajería instantánea, residirá en Skype para empresas (ligado a llamar)|
|Islas |Skype más pequeño o más sencilla para la implementación en la empresa<br><br>Capacidad y la voluntad para administrar cierta complejidad a corto plazo para moverse más rápido a los equipos |Ir a la experiencia completa de equipos lo más rápidamente posible<br><br>Realizar una prueba de concepto (PoC) de los equipos |Fácil de no utilizar, ninguna interoperabilidad<br><br>Mejor experiencia de los equipos por adelantado todas las funcionalidades |Requiere usuario buena comunicación para evitar confusiones y al uso de unidades hacia equipos<br><br>Estrategia de salida requiere que los usuarios totalmente han adoptado los equipos por el tiempo de Skype para el negocio es baja|
|Sólo los equipos |Algunos usuarios necesitan permanecer en Skype para empresas<br><br>Está actualizando su Skype para usuarios de negocios en línea a los equipos mientras mantiene Skype para empresas locales los usuarios de Skype para Business Server<br><br>Podrían haber implementado usuarios en modo de islas y están listos para retirar Skype para empresas para grupos de usuarios |Reducir los costes variables de Skype para empresas (operaciones de servidor local, el contrato de subcontratación etc.)<br><br>Ir a la experiencia completa de equipos lo más rápidamente posible, al menos, algunos usuarios|Limita la confusión de los usuarios proporcionando a trabajar con un único cliente|Interoperabilidad sólo es compatible con chat básico y llamada entre equipos y Skype para empresas|
|Skype para empresas sólo |Algunos usuarios necesitan permanecer en Skype para empresas<br><br>|Limita la confusión de los usuarios proporcionando a trabajar con un único cliente|Seguir cumpliendo los requerimientos del negocio que actualmente sólo pueden cumplirse por Skype para empresas|Interoperabilidad sólo es compatible con chat básico y llamada entre equipos y Skype para empresas|

> [!NOTE]
> Ayuda para habilitar cada uno de los modos descritos anteriormente, publicaremos a un tutorial acerca de cómo ejecutar su viaje desde Skype para el negocio a los equipos cuando las directivas están disponibles en un momento posterior. ¡Esté atento!

## <a name="upgrade-journeys"></a>Viajes de actualización
Puede tomar varios enfoques a la actualización de Skype para el negocio, ya sea en línea o locales, a los equipos:
- En el camino de upgrade simple, primero implementar equipos de Skype para empresas con la colaboración de equipos&ndash;sólo modo como parte de la evaluación y adopción temprana y, a continuación, implementar equipos sólo con el objetivo de retirar eventualmente Skype para el negocio de la entorno para todos los usuarios de la organización.
- Un viaje de actualización gradual ofrece un modo de actualización específico a un grupo específico de usuarios (también llamado un *grupo de edad*), dependiendo de sus requerimientos de colaboración y comunicaciones. Con el tiempo, toda la organización puede converger en únicamente por medio de equipos y eventualmente reemplazar Skype para empresas. Sin embargo, si la organización tiene razones de negocio atractivas para mantener Skype para el negocio, como una dependencia de una solución basada en Unified Communications Managed UCMA de API que se integra con aplicaciones de línea de negocio, o una solución de ética actualmente disponible para Skype para empresas sólo, puede actualizar una mayoría de los usuarios al modo de sólo equipos manteniendo Skype para usuarios profesionales de uno de lo Skype para los modos de negocio de una parte de la población de usuarios.

> [!IMPORTANT]
> Para ambos tipos de viaje de actualización, si su organización es actualmente un Skype para implementación de local de negocio, debe iniciar planean implementar Skype para híbrido de negocio antes de actualizar a los usuarios al modo de sólo equipos. Esto también ayudará a facilitar la interoperabilidad con los equipos.
> Utilice [MyAdvisor](https://myadvisor.fasttrack.microsoft.com/) para guiar su Skype para implementación híbrida de negocio.

> [!NOTE]
> Modo de equipos sólo requiere que los usuarios que forman parte de las cohortes se aloja en Skype para los negocios en línea, y una relación híbrida entre su Skype para la implementación local de la empresa y su Skype para inquilinos de negocios en línea es necesaria para facilitar la actualización y interoperabilidad entre equipos y Skype para empresas. Debe realizarse el cambio a Skype para los negocios en línea para los usuarios que forman parte de las cohortes antes de que se está actualizado al modo de sólo equipos. Skype para Business Server 2019 y también en una futura actualización acumulativa de Skype para Business Server 2015, pretende simplificar la mecánica de actualización de usuarios locales a los equipos mediante la administración de la migración a Skype para los negocios en línea y actualizar a los usuarios a sólo los equipos modo en un solo paso.

Cualquier viaje que elija, Microsoft aquí es proporcionar soporte técnico a través del proceso de actualización. De requisitos técnicos a los recursos de disponibilidad del usuario, compartiremos la orientación y las mejores prácticas para ayudar a garantizar una transición exitosa de Skype para el negocio a equipos. Guía detallada sobre la actualización estar listo pronto, por lo que revise periódicamente para obtener más información.

### <a name="simple-upgrade-journey"></a>Viaje de actualización simple
El camino de upgrade simple se ilustra en el diagrama siguiente.

![Una captura de pantalla del viaje de actualización simple. Todos los usuarios inicialmente usan equipos en Skype para empresas con la colaboración de equipos&ndash;modo solamente, entonces transición al modo de sólo equipos, con el estado final del actualizado a los equipos de toda la organización.](media/upgrade_and_coexistence_simple_upgrade_journey.png)

Los equipos se ha implementado para todos los usuarios de la organización y configurado en Skype para empresas con la colaboración de equipos&ndash;sólo modo. Cuando la organización determina que los equipos está preparado para satisfacer todas sus necesidades de colaboración y comunicaciones, todos los usuarios se actualizan a modo de sólo equipos. En ese momento, el medio ambiente puede retirarse Skype para el negocio.

### <a name="gradual-upgrade-journey"></a>Viaje de actualización gradual
En el diagrama siguiente se muestra un ejemplo de un viaje de actualización gradual.

![En el trayecto de actualización gradual, las cohortes de usuarios utilizan inicialmente los equipos en una variedad de modos de actualización, junto con Skype para el negocio. Transición de algunas cohortes al modo de sólo equipos, mientras se mantiene un grupo de usuarios con Skype para empresas con la colaboración de equipos y modo de reuniones.](media/upgrade_and_coexistence_gradual_upgrade_journey.png)

Equipos se implementa en la organización mediante el uso de diferentes modos de actualización para los diferentes grupos de usuarios o las cohortes. Por ejemplo, un grupo de usuarios puede habilitarse para el modo de islas, otro habilitado para Skype para empresas con la colaboración de equipos y el modo de reuniones, mientras que un tercer grupo de usuarios podría estar habilitado inicialmente en Skype para empresas con la colaboración de equipos&ndash;sólo modo.

Con el tiempo, grupos de usuarios pueden actualizarse al modo de sólo equipos, seguido por el resto de la organización. Finalmente, estará lista para retirar Skype para el negocio y utilizar sólo equipos para comunicaciones y colaboración, toda la organización o, si los requisitos empresariales exigen que se conserven Skype para el negocio para un grupo específico, la mayoría de los usuarios en el organización sólo podrá utilizar los equipos. <br><br>
<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Puntos de decisión</td><td><ul> ¿Qué actualización viaje es adecuado para los requisitos empresariales de su organización?<br><br></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Pasos siguientes</td><td><ul> Identificación de su actual modelo de implementación, utilice situaciones y consideraciones clave para su organización informará el viaje a equipos que mejor se adapten a su organización.<br><br></ul></td></tr>
</table>

## <a name="upgrade-scenarios"></a>Escenarios de actualización
En función de los viajes de actualización descritos anteriormente en este artículo, los siguientes consejos preceptivos se proporcionan para Skype específico para los modelos de implementación de negocios que podría asignar a su modelo de implementación actual. 

|Modelo de implementación  |Punto de partida  |Consideraciones  |Viaje  |
|---------|---------|---------|---------|
|Skype para el negocio en línea, sólo con planes de llamada |Inquilinos de Office 365 con Azure Connect de AD, SharePoint Online, Exchange Online y Skype para los negocios en línea<br><br> Sistema de teléfono con una llamada a planes implementa mediante Skype para los negocios en línea para todos los usuarios |Todos los usuarios aprovechan certificadas auriculares<br><br> Las reuniones requieren a internos y anónimos participantes externos de VoIP<br><br> Mensajería incluye contactos internos y externos |**Guía básica de mensajería**: característica de federación destinado a la versión Q2 de 2018<br><br> **Plan de reuniones**: características desea que ya están disponibles<br><br> **Llamar a roadmap**: características desea que ya están disponibles<br><br> Bloques de creación:<ul><li> Skype para empresas con la colaboración de equipos&ndash;modo sólo</li><li> Modo de sólo equipos</li></ul>|
|Skype para negocios en línea con conector de nube Edition (CCE) |Inquilinos de Office 365 con Azure Connect de AD, SharePoint Online, Exchange Online y Skype para los negocios en línea<br><br> Sistema de teléfono con voz híbrida vía CCE implementado mediante Skype para el negocio en línea en varias ubicaciones<br><br> 1.000 usuarios están utilizando cargas de voz y mensajería sólo|el 80% de la población de usuarios aprovecha el sistema de teléfono con voz híbrida vía CCE<br><br> Todos los de mensajería está dentro de la empresa<br><br> Actualmente no se utilizan las reuniones, pero hay interés en habilitar conferencias de Audio en el futuro|**Guía básica de mensajería**: están disponibles características que desee<br><br> **Plan de reuniones**: pueden cumplirse los requisitos del futuro<br><br> **Llamar a roadmap**: enrutamiento en función de los equipos destinado a la versión Q2 de 2018 directo <br><br> Bloques de creación:<ul><li> Skype para empresas con la colaboración de equipos y modo de reuniones</li><li> Modo de sólo equipos</li></ul> |
|Skype para negocios híbrido |Inquilinos de Office 365 con Azure Connect de AD, SharePoint Online, Exchange Online y Skype para los negocios en línea<br><br> Skype para híbridos y Business Server 2015 implementado se configura con Skype para los negocios en línea|Un número de usuarios requiere la capacidad de grabar reuniones<br><br> Hay 10 salas de conferencias, aprovechando actualmente sistemas de salas de Skype v2<br><br> La organización desea aprovechar las ventajas de los equipos como una herramienta de colaboración lo más rápidamente posible|**Guía básica de mensajería**: están disponibles características que desee<br><br> **Plan de reuniones**: grabación de la reunión, reunión característica de sala dispositivos destinado a la versión Q2 de 2018 de nube<br><br> **Llamar a roadmap**: están disponibles características que desee<br><br> Bloques de creación:<ul><li>Skype para empresas con la colaboración de equipos&ndash;modo sólo</li><li> Skype para empresas con la colaboración de equipos y modo de reuniones</li><li>Modo de islas</li><li>Modo de sólo equipos</li></ul> |
|Skype para Business Server (local) |Inquilinos de Office 365 con Azure Connect de AD y Exchange Online<br><br> SharePoint y Skype para empresas están implementados en locales|Función de voz empresarial completa set (Skype para Business Server 2015) actualmente en uso<br><br> Centro de contacto implementado<br><br> Las reuniones se llevan a cabo con los usuarios federados internos y externos, mediante VoIP y conferencias de acceso telefónico<br><br> Mensajería con usuarios internos y externos|Implementar SharePoint en línea<br><br> Configurar Skype para híbrido de negocio (dominio de división)<br><br>**Guía básica de mensajería**: característica de federación destinado a la versión Q2 de 2018<br><br> **Plan de reuniones**: federado reunión unión, característica de lobby PSTN destinado a la versión Q2 de 2018<br><br> **Llamar a roadmap**: característica destinado a la liberación Q4 de 2018 y en adelante<br><br>Bloques de creación:<ul><li>Modo de islas (prueba piloto)</li><li>Skype para empresas con la colaboración de equipos&ndash;modo sólo</li><li>Skype para empresas con la colaboración de equipos y modo de reuniones</li><li>Modo de sólo equipos y Skype para empresas&ndash;modo sólo</li></ul><br>Investigar la actualización a Skype para Business Server 2019|

<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/>Puntos de decisión</td><td><ul> ¿El escenario de actualización es aplicable a su organización?<br><br></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/>Pasos siguientes</td><td><ul> Decidir la línea de tiempo del viaje de actualización de la organización basado en mensajes, reuniones y llamar a los requerimientos del negocio.<br><br> Decidir el trabajo adicional necesario para completar su viaje de actualización.<br><br></ul></td></tr>
</table>

## <a name="see-also"></a>Vea también
[Administrar equipos durante la transición al nuevo Teams de Microsoft y Skype para el centro de administración de negocios](manage-teams-skypeforbusiness-admin-center.md)
