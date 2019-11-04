---
title: Actualización de Microsoft Teams desde Skype empresarial | Modos, coexistencia
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: dearbeen, bjwhalen
description: Detalles de Skype empresarial y Microsoft Teams opciones y modos de coexistencia, y actualización de los viajes a los equipos de Skype empresarial con escenarios de ejemplo.
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
f1keywords:
- ms.teamsadmincenter.orgwidesettings.teamsfeatures.upgradetoteamsarticle
- ms.teamsadmincenter.upgradeoverride.learnmore
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5de243402cd5694b2e4a498f7ff7650cd8f49f4a
ms.sourcegitcommit: 2e005b335b1566c99b93fc311498702838466324
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2019
ms.locfileid: "37931648"
---
![Actualizar el diagrama de viaje, enfatizando la fase de definición del proyecto](media/upgrade-banner-project-definition.png "Etapas del viaje de actualización, con énfasis en la fase de definición del proyecto")

Este artículo forma parte de la fase de definición de proyecto del viaje de actualización. Antes de continuar, confirme que ha completado las siguientes actividades:

- [Inventar a los participantes del proyecto](upgrade-enlist-stakeholders.md)
- [Definió el ámbito del proyecto](https://aka.ms/SkypetoTeams-Scope)
- [La coexistencia y la interoperabilidad de Skype para empresas y equipos](https://aka.ms/SkypeToTeams-Coexist)

# <a name="choose-your-upgrade-journey-from-skype-for-business-to-teams"></a>Elegir el viaje de actualización de Skype empresarial a teams

Como cliente existente de Skype empresarial, la transición completa a teams puede llevar algún tiempo. Sin embargo, puede empezar a obtener el valor de Teams hoy, lo que permite a los usuarios usar Teams junto con Skype empresarial. Dado que hay alguna funcionalidad superpuesta entre las dos aplicaciones, le recomendamos que revise los modos disponibles de coexistencia y actualización para determinar qué ruta de acceso es adecuada para su organización. Por ejemplo, puede optar por habilitar todas las cargas de trabajo en ambas soluciones sin interoperabilidad. O bien, puede decidir administrar la experiencia del usuario, ya sea mediante la presentación gradual de las capacidades de Teams o la segmentación de grupos de usuarios para capacidades de selección, hasta que su organización esté lista para actualizar a todos los equipos. Use el resultado de su prueba piloto para evaluar el camino adecuado para la actualización de su organización.

> [!IMPORTANT]
> Skype empresarial online se retirará el 31 de julio de 2021, después del cual ya no será accesible ni compatible. Para maximizar los beneficios y asegurarse de que su organización tenga el tiempo adecuado para implementar su actualización, le recomendamos que comience su viaje a Microsoft Teams hoy.

En este artículo se describen los distintos modos que le permiten administrar las modalidades de Skype empresarial y de los equipos disponibles para los usuarios. Al igual que con cualquier implementación, le recomendamos encarecidamente que [planee su plan previsto](pilot-essentials.md) con un grupo de usuarios seleccionado antes de actualizar su organización a teams. Recuerde que la presentación de nuevas tecnologías puede ser perjudicial para los usuarios. Tomarse el tiempo para evaluar la preparación de los usuarios e implementar un plan de comunicación y formación antes de implementar cualquiera de los modos descritos en el presente documento.

> [!TIP]
> Únase a los talleres interactivos y en vivo en los que compartimos orientación, procedimientos recomendados y recursos diseñados para la planificación e implementación de la actualización de lanzamiento.
>
>Únase primero a la [planificación de tu actualización](https://aka.ms/SkypeToTeamsPlanning) para comenzar.


## <a name="upgrade-journey-building-blocks"></a>Actualizar los bloques de creación del viaje

Para preparar formalmente su organización para su viaje a Teams, debe comenzar a planear los escenarios de actualización que le permitirán a su organización adoptar completamente equipos como una única solución de comunicaciones y colaboración.

Para ayudarle en el proceso de toma de decisiones, familiarícese con los distintos modos, conceptos y terminología relacionados con la actualización de Skype empresarial a teams. Para obtener más información, consulte [Microsoft Teams y la coexistencia e interoperabilidad de Skype empresarial](https://aka.ms/SkypeToTeams-Coexist)

Un usuario que se ha migrado a teams ya no usa un cliente de Skype empresarial, excepto para unirse a una reunión hospedada en Skype empresarial. Todas las conversaciones entrantes y llama en tierra en el cliente de equipos del usuario, independientemente de si el remitente usa Teams o Skype empresarial. Todas las reuniones nuevas organizadas por el usuario actualizado se programarán como reuniones de Teams. Si el usuario intenta usar el cliente de Skype empresarial, el inicio de los chats y las llamadas se bloquea<sup>1</sup>. Sin embargo, el usuario puede (y debe) seguir usando el cliente de Skype empresarial para unirse a las reuniones a las que está invitado.

Los administradores administran su transición a teams mediante el concepto de [modo](migration-interop-guidance-for-teams-with-skype.md#coexistence-modes), que es una propiedad de [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps). Un usuario que se ha migrado a Teams, como se describe anteriormente, está en modo "TeamsOnly". En el caso de una organización que está migrando a Teams, el último objetivo es mover todos los usuarios al modo TeamsOnly.

Existen dos métodos para migrar una organización existente con Skype empresarial (ya sea en línea o local) a teams:

- **Método de funciones superpuestas** (con el modo Islas): los usuarios de una organización existente de Skype empresarial se introducen en Teams para que puedan usar ambos clientes en paralelo durante una fase de transición. Durante este período, la mayoría de las funciones de Teams, pero no todas, están disponibles. El modo de esta configuración se denomina islas, y este es el modo predeterminado para cualquier organización existente con Skype empresarial. Una vez que la organización está lista, el administrador pasa a los usuarios al modo TeamsOnly.
- **Seleccione el método de capacidades** (con uno o varios de los modos de Skype empresarial): el administrador administra la transición (de Skype empresarial a teams) de las funciones de chat, llamadas y programación de reuniones para los usuarios de su organización. Cada una de estas funciones está disponible en Skype empresarial o en Teams, pero no en ambas. Los administradores usan TeamsUpgradePolicy para controlar cuándo se desplazan esta funcionalidad a los equipos de los usuarios. Los usuarios que aún no están en el modo de TeamsOnly siguen usando Skype empresarial para conversaciones y llamadas, y los dos conjuntos de usuarios pueden comunicarse a través de la funcionalidad de interoperabilidad. Los administradores administran la transición mediante la migración progresiva de más usuarios al modo TeamsOnly.

<sup>1</sup> Los antiguos clientes de Skype empresarial que se entregaron antes 2017 no son compatibles con TeamsUpgradePolicy. Asegúrese de que está usando el último cliente de Skype empresarial disponible en su canal de Office.

A continuación se muestran los factores clave para ayudarle a decidir cuál es la ruta de acceso adecuada para su organización. 

## <a name="overlapping-capabilities-method-using-islands-mode"></a>Método de funciones superpuestas (con el modo Islas)

Con el método de funciones superpuestas, los usuarios pueden usar tanto equipos como clientes de Skype empresarial para conversaciones de chat, llamadas de VoIP y reuniones. En este método, las llamadas de chat y VOIP en Teams son específicas de la organización, mientras que Skype empresarial habilita las llamadas de chat y de VOIP/RTC con organizaciones externas (si se han configurado). Las reuniones se pueden programar y tener una asistencia en ambos productos.

Al usar el método de funciones superpuestas, el tráfico de comunicación de Skype empresarial y Teams sigue siendo independiente (incluso para el mismo usuario) y los dos clientes diferentes nunca se comunican entre sí (para los usuarios de la misma organización). Las experiencias de usuario se basan en la configuración del destinatario. Por ejemplo, supongamos que el usuario A está usando este método de actualización:

- La comunicación iniciada desde el cliente de Skype empresarial de otro usuario siempre se ubicará en el cliente de Skype empresarial del usuario A.
- La comunicación iniciada desde el cliente de Teams desde un *usuario de la misma organización* siempre estará en el cliente de equipos del usuario a.
- La comunicación iniciada desde un cliente de equipos desde un *usuario de una organización externa* siempre estará en el cliente de Skype empresarial del usuario a.

Si ha asignado una licencia de Office 365 a los usuarios, esta será la experiencia de actualización predeterminada para su organización. Cuando asigna una licencia de Office 365, se asignan licencias de equipo y de Skype empresarial online de forma predeterminada. <sup>2</sup>

Para que este método funcione de forma eficaz, todos los usuarios deben ejecutar ambos clientes al mismo tiempo. Las conversaciones entrantes y las llamadas desde dentro de la organización a un usuario en modo islas pueden encontrarse en el cliente de Skype para empresas o Teams, y esto no está bajo el control del destinatario. Depende del cliente que use el remitente para iniciar la comunicación. Si el remitente y el destinatario están en distintas organizaciones, las llamadas entrantes y los chats a un usuario en el modo islas siempre estarán en el cliente de Skype empresarial.

Por ejemplo, si un destinatario de modo islas ha iniciado sesión en Skype empresarial pero no Teams, y alguien los envía a un equipo, el destinatario del modo islas no verá el mensaje (pero finalmente recibirá un mensaje de correo electrónico que indica que ha perdido un mensaje en Teams). Del mismo modo, si un usuario ejecuta Teams pero no Skype empresarial y alguien le envía un mensaje de usuario de Skype empresarial, el usuario no verá ese chat. El comportamiento en cada uno de estos casos es similar al de las llamadas. Si los usuarios no ejecutan ambos clientes, puede dar lugar a frustraciones fácilmente.

La presencia también funciona de forma independiente entre equipos y Skype empresarial usando este método de actualización. Esto significa que otros usuarios pueden ver diferentes Estados de presencia para el usuario A, dependiendo del cliente que usen. Para obtener más información, consulte [presencia](upgrade-to-Teams-on-prem-overview.md#presence).

- Otros usuarios, cuando usen Teams, verán la presencia en función de la actividad del usuario A en Teams.
- Otros usuarios, al usar Skype empresarial, verán la presencia basada en la actividad del usuario A en Skype empresarial.

Una vez que esté listo para actualizar a los usuarios al modo TeamsOnly, puede actualizar los usuarios de forma individual o puede actualizar todo el inquilino a la vez con la Directiva de ámbito empresarial<sup>3</sup>. Una vez que un usuario se actualiza al modo TeamsOnly, recibe todas las conversaciones y llamadas entrantes en Teams.

Sin embargo, es posible que los destinatarios no actualizados en modo islas sigan recibiendo chats y llamadas de un usuario TeamsOnly en sus clientes de Skype empresarial o de Teams. Para las conversaciones existentes, el usuario de TeamsOnly responderá al cliente en el que el remitente inició la conversación o la llamada. 

Para las conversaciones nuevas desde el punto de vista del usuario de TeamsOnly, la conversación o la llamada siempre irá al modo islas islas usuarios de Teams. Esto se debe a que el cliente de Teams mantiene subprocesos de conversación por separado para la comunicación entre equipos y entre equipos y entre usuarios de Skype para empresas, incluso para el mismo usuario. Para obtener más información, vea [conversaciones de Teams: interoperabilidad frente a subprocesos nativos](upgrade-to-Teams-on-prem-overview.md#teams-conversations---interop-versus-native-threads).

En la tabla siguiente se resume la experiencia de los equipos para el modo islas y TeamsOnly:

| Experiencia de Teams | En modo islas | En el modo TeamsOnly |
|:------------------ | :------------------- | :------------------ |
| Conversaciones y llamadas entrantes recibidas en:|  Teams o Skype empresarial | Teams |
| Llamadas RTC recibidas en: | Skype Empresarial <br>(El uso de la funcionalidad RTC en Teams no es compatible con el modo Islas).    | Teams |   
 |Presence  | La presencia en Skype empresarial y Teams es independiente. Los usuarios pueden ver diferentes Estados para el mismo usuario de islas, en función del cliente que usen. | La presencia se basa únicamente en la actividad del usuario en Teams. Todos los demás usuarios, independientemente del cliente que usen, verán esa presencia. | 
 | Programación de reuniones   | Los usuarios pueden programar reuniones en Teams o Skype empresarial. Verán ambos complementos en Outlook. |   Los usuarios solo programan reuniones en Teams. En Outlook solo está disponible el complemento de Teams. | 

En la siguiente tabla se resumen los pros y los inconvenientes de usar el método de funciones superpuestas para migrar su organización a teams.

| Profesionales ti     |       Conveniente |
| :------------------ | :---------------- |
| Permite una rápida adopción dentro de una organización.| Posibilidad de confusión entre usuarios finales, ya que existen dos clientes con una funcionalidad similar, pero distintas interfaces de usuario. Además, no tienen control sobre qué clientes entran y las llamadas entrantes. |
| Permite a los usuarios aprender y familiarizarse con Teams sin dejar de tener acceso completo a Skype empresarial. | Potencial de insatisfacción del usuario final debido a mensajes perdidos si el usuario no está ejecutando ambos clientes.|
| Esfuerzo mínimo de administración para empezar a trabajar en Teams. | Puede ser desafiante "salir del modo de islas" y pasar al modo TeamsOnly si los usuarios y aquellos con los que normalmente se comunican no usan activamente Teams.|
|Permite a los usuarios aprovechar las funciones para mejorar el trabajo en equipo que no está disponible en Skype empresarial.| Un usuario que está usando Skype empresarial en local y Teams no podrá comunicarse con otros usuarios que usen Skype empresarial local, pero que no tengan equipos de equipos.  |

<sup>2</sup> Esto es cierto incluso si el usuario está alojado en local en Skype empresarial Server. Independientemente de si el usuario se ha alojado en local o en línea, deje habilitada la licencia de Skype empresarial online, porque actualmente es necesaria para la funcionalidad de equipos completos.

<sup>3</sup> Tenga en cuenta que la migración de reuniones de Skype empresarial a reuniones de Teams solo se desencadena cuando se aplica TeamsUpgradePolicy a usuarios individuales, no por espacio empresarial. Consulte [migración de reuniones](upgrade-to-Teams-on-prem-overview.md#meeting-migration) para obtener más información.

## <a name="select-capabilities-method-using-skype-for-business-modes"></a>Método de selección de funciones (con los modos de Skype empresarial)

Es posible que algunas organizaciones prefieran proporcionar a los usuarios finales una experiencia más predecible a medida que su organización pase de Skype empresarial a equipos. En este modelo, los administradores de ti usan uno de los modos de Skype empresarial en TeamsUpgradePolicy para designar de forma explícita Qué funcionalidades permanecen en Skype empresarial antes de migrar al modo TeamsOnly. Puesto que están listos para desplazar las funcionalidades seleccionadas al modo TeamsOnly, el administrador actualiza el modo de que esos usuarios TeamsOnly. Durante esta transición:

- Los administradores tienen opciones para habilitar determinadas capacidades de Teams para los usuarios a la vez que mantienen las capacidades de chat y de llamadas en Skype empresarial antes de que los usuarios pasen a TeamsOnly. La administración puede habilitar las capacidades de colaboración de Teams o las reuniones y las características de colaboración.
- Los usuarios que todavía tienen Skype empresarial reciben todas las conversaciones y llamadas entrantes en el cliente de Skype empresarial, independientemente de si la comunicación proviene de los equipos de los demás usuarios o del cliente de Skype empresarial. Además, para estos usuarios de Skype empresarial, la funcionalidad de llamadas y chats en el cliente de equipos están deshabilitadas para ayudar a evitar la confusión del usuario final y garantizar el enrutamiento y la presencia adecuados.
- Los usuarios en modo TeamsOnly reciben todas las conversaciones y las llamadas entrantes en el cliente de su equipo y la presencia viene proporcionada por los equipos, independientemente de dónde se originó la comunicación: Teams, Skype empresarial o cualquier tipo de usuario federado.

A diferencia del método de capacidades superpuestas, en el método de seleccionar capacidades, los usuarios que usan Skype empresarial pueden comunicarse con los usuarios que están en TeamsOnly. La comunicación entre un usuario de Skype empresarial y un usuario de equipo se conoce como [interoperabilidad](upgrade-to-Teams-on-prem-overview.md#interoperability) o "interoperabilidad". La comunicación interoperativa es posible en una base de uno a uno para conversaciones y llamadas entre usuarios de Skype empresarial y otros usuarios de Teams. Además, los usuarios invitados siempre pueden unirse a una reunión de Skype empresarial o de Teams, pero deben usar un cliente que se corresponda con el tipo de reunión. Para obtener más información, vea [reuniones](upgrade-to-Teams-on-prem-overview.md#meetings).

Para los usuarios con un método de selección de funciones, la presencia de un usuario es coherente, independientemente del cliente que use el otro usuario. Si el usuario se encuentra en uno de los modos de Skype empresarial, todos los demás usuarios verán presencia basada en la actividad de ese usuario en Skype empresarial. De forma similar, si un usuario está en modo TeamsOnly, todos los demás usuarios verán la presencia basándose en la actividad de ese usuario en Teams. Para obtener más información, consulte [presencia](upgrade-to-Teams-on-prem-overview.md#presence).

Para una organización que ha elegido seguir el método de funciones SELECT, el administrador debe cambiar el modo de inquilino para todo el inquilino de islas al modo de coexistencia de Skype empresarial correspondiente (SfbWithTeamsCollab o SfBWithTeamsCollabAndMeetings).  

Las experiencias de los usuarios invitados se ajustarán al modo de coexistencia asignado al inquilino. Si estableces un modo de Skype empresarial en el nivel de espacio empresarial, los invitados no pueden conversar, llamar o mostrar su presencia. Para obtener más información, lea [acceso de invitado en Teams](guest-access.md).

Cuando el modo cambia de islas a SfbWithTeamsCollab, los usuarios que nunca hayan usado Teams no verán ninguna diferencia en el modo en que usan Skype empresarial. Sin embargo, si el usuario comienza a usar Teams, solo se verá expuesto a una funcionalidad como la de Teams & canal y archivos. La programación, las llamadas y las reuniones no estarán disponibles en Teams, ya que el administrador ha designado (por ahora) Skype empresarial como el cliente deseado para esas funciones.

> [!NOTE]
> Cuando el usuario A cambia de islas a uno de los modos de Skype empresarial, el cliente de Teams de cualquier otro usuario que se comunique con el usuario A debe saber que el modo del usuario a ha cambiado para que pueda enrutar la comunicación al cliente a correspondiente para el usuario A. Para todos los usuarios que ya hayan establecido chats nativos entre equipos con el usuario A, puede demorar el cambio de modo de los demás usuarios de los equipos de los usuarios de islas a cualquier modo de Skype empresarial. Cuando los administradores están listos, pueden desplazarse por las conversaciones de chat, llamadas y reuniones para un usuario determinado a teams todos a la vez actualizando el modo del usuario a TeamsOnly.

Como alternativa, el administrador puede desplazar solo la programación de reuniones a Teams, dejando las funciones de chat y de llamadas en Skype empresarial con el modo SfBWithTeamsCollabAndMeetings. Este modo permite que las organizaciones pasen a los equipos de las reuniones, si aún no están listos para pasar al modo TeamsOnly (por ejemplo, aún no está listo para migrar la funcionalidad RTC existente). Este escenario transitorio se conoce como [reuniones en primer lugar](meetings-first.md).


|Experiencia de Teams  |En el modo SfBWithTeamsCollab |En el modo SfBWithTeamsCollabAndMeetings |En el modo TeamsOnly  |
|---------|---------|---------|---------|
|Las conversaciones entrantes y las llamadas de VOIP de los usuarios de su organización se han recibido en:     | Skype Empresarial        | Skype Empresarial       | Teams        |
|Llamadas RTC recibidas en:     | Skype Empresarial        |Skype Empresarial         | Teams        |
|Presence     | Skype Empresarial        |Skype Empresarial         | Teams        |
|Programación de reuniones     | Skype Empresarial         | Teams        | Microsoft Teams        |


La siguiente tabla resume los pros y los inconvenientes de usar los modos de Skype empresarial como paso de transición hacia el modo TeamsOnly.

| Profesionales ti     |       Conveniente |
| :------------------ | :---------------- |
| Enrutamiento predecible para el usuario final. Todas las llamadas y chats se encuentran en Skype para empresas o en Teams (pero no en ambas), en función de la selección del administrador.|Las conversaciones de interoperabilidad carecen de compatibilidad con texto enriquecido, uso compartido de archivos y pantalla compartida. Esto se puede resolver aprovechando la funcionalidad reunirse ahora para iniciar una reunión. |
|Puede reducir la confusión del usuario final porque una determinada función solo está disponible en un cliente. | Los usuarios no tienen acceso a los equipos para actividades comunes realizadas en Skype empresarial, como chats y llamadas antes de la actualización a TeamsOnly.|
|El administrador ha aumentado el control sobre el conjunto de capacidades disponibles para los usuarios mientras se realiza la transición de Skype empresarial a teams. | |
| Permite a una organización usar Teams para reuniones, incluso si aún no está listo para moverse completamente al modo TeamsOnly.||
|La presencia de un usuario determinado según lo ven otras personas es la misma, independientemente del cliente que usen.||

## <a name="summary-of-upgrade-methods"></a>Resumen de los métodos de actualización
En la siguiente tabla se resumen los métodos de actualización:


|Funciones superpuestas (con el modo Islas)  |Capacidades seleccionadas (con los modos de Skype empresarial)  |
|---------|---------|
|Antes de actualizar a TeamsOnly, los usuarios deben ejecutar ambos clientes a la vez, ya que las conversaciones entrantes y las llamadas pueden situarse en cualquier cliente.     | Chatea y llama solamente a tierras de un cliente, en función del modo del destinatario. Los usuarios no actualizados pueden ejecutar ambos clientes, pero no hay ninguna superposición funcional (las llamadas y la conversación no están disponibles en Teams).         |
|Permite a los administradores introducir funcionalidades superpuestas (chat, reuniones, llamadas VOIP) tanto en Skype empresarial como en Teams para usuarios finales, así como nuevas capacidades (equipos y canales) en Teams.     | Permite a los administradores presentar la funcionalidad de selección de Teams a los usuarios finales (equipos y canales), sin proporcionar la misma funcionalidad que también existe en Skype empresarial.        |
|La interoperabilidad entre Skype empresarial y Teams no existe mientras ambos usuarios están en el modo islas.      |La interoperabilidad es necesaria para la comunicación entre los usuarios de Skype empresarial y de Teams.         |

> [!NOTE]
> Si no puede seguir los métodos admitidos para migrar los usuarios de Skype empresarial Server a Teams, sería posible realizar la transición de los usuarios a teams quitando Skype empresarial Server y todos los atributos de usuario relacionados en Active Directory. Una vez que los usuarios de los atributos de Azure Active Directory se hayan eliminado de los atributos de servidor de Skype empresarial y los registros de DNS hayan sido redirigidos a Office 365, entonces sería posible conceder licencias a los usuarios en Office 365 y actualizarlos a teams. 

> [!IMPORTANT]
> Con la migración total, los datos de contactos y reuniones no se migrarán del entorno local a Microsoft Teams.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/>Puntos de decisión</td><td><ul> ¿Qué viaje de actualización es adecuado para los requisitos empresariales de su organización?<br><br></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next step"/><br/>Paso siguiente</td><td><ul> Identificar el modelo de implementación actual, los escenarios de casos de uso y las consideraciones clave para su organización informarán al viaje a los equipos que mejor se adapten a su organización.<br><br></ul></td></tr>
</table>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/>Puntos de decisión</td><td><ul> ¿Qué escenario de actualización es aplicable a su organización?<br><br></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Siguientes pasos</td><td><ul> Decidir la escala de tiempo del viaje de actualización de su organización en función de la mensajería, las reuniones y los requisitos empresariales de llamadas.<br><br> Decida el trabajo adicional necesario para completar el viaje de actualización.<br><br></ul></td></tr>
</table>

Una vez que haya elegido el mejor viaje de actualización para su organización, [realice la actualización a teams](https://aka.ms/SkypeToTeams-Upgrade).
