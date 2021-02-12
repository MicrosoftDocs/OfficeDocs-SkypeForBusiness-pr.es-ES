---
title: Elegir el viaje de actualización de Skype Empresarial a Microsoft Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: landerl, bjwhalen
description: Detalles de las opciones de coexistencia de Skype Empresarial y Microsoft Teams, así como de los posibles viajes de actualización a Teams, con escenarios de ejemplo.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- ms.teamsadmincenter.orgwidesettings.teamsfeatures.upgradetoteamsarticle
- ms.teamsadmincenter.upgradeoverride.learnmore
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 23a71a075730f1447259d6e3a4a3dd21f650bfd7
ms.sourcegitcommit: 1e16c6c7112bdde03209c12468b5705ddd116a62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "49578163"
---
# <a name="choose-your-upgrade-journey-from-skype-for-business-to-teams"></a>Elegir la vía de actualización de Skype Empresarial a Teams

![Diagrama de itinerario de actualización, énfasis en la fase de definición del proyecto](media/upgrade-banner-project-definition.png "Fases del itinerario de la actualización, con énfasis en la fase de definición del proyecto")

Este artículo forma parte de la fase de definición de proyecto de su vía de actualización. Antes de continuar, confirma que has completado las siguientes actividades:

- [Ha incorporado a las partes interesadas del proyecto](upgrade-enlist-stakeholders.md)
- [Ha definido el ámbito del proyecto](https://aka.ms/SkypetoTeams-Scope)
- [Ha comprendido la coexistencia y la interoperabilidad de Skype Empresarial y Teams](https://aka.ms/SkypeToTeams-Coexist)

Como cliente existente de Skype Empresarial, la transición completa a Teams puede llevar cierto tiempo. Sin embargo, puede empezar hoy mismo a comprender el valor de Teams habilitando a sus usuarios para utilizar Teams junto con Skype Empresarial. Dado que hay algunas funciones superpuestas entre las dos aplicaciones, le recomendamos que revise los modos de coexistencia y actualización disponibles para ayudar a determinar qué ruta es la adecuada para su organización. Por ejemplo, es posible que decida permitir todas las cargas de trabajo en ambas soluciones sin interoperabilidad. O bien, puede decidir administrar la experiencia de usuario, ya sea mediante la introducción gradual de las funciones de Teams o seleccionando grupos de usuarios para ciertas funciones, hasta que la organización esté preparada para actualizar a todos sus miembros a Teams. Use el resultado de la prueba piloto para evaluar la vía adecuada para la actualización de su organización.

> [!IMPORTANT]
> Skype Empresarial Online se retirará el 31 de julio de 2021, momento a partir del cual ya no será posible obtener acceso a este soporte. Para aprovechar al máximo las ventajas y asegurarse de que su organización dispone del tiempo adecuado para implementar la actualización, le recomendamos que comience ahora su viaje hacia Microsoft Teams.

Este artículo describe los distintos modos que le permiten administrar las modalidades de Skype Empresarial y de Teams que estarán disponibles para los usuarios. Al igual que con cualquier implementación, le recomendamos encarecidamente que [pilote el plan previsto](pilot-essentials.md) con un grupo seleccionado de usuarios antes de actualizar toda la organización a Teams. Recuerde que la introducción de nuevas tecnologías puede suponer molestias para los usuarios. Tómese el tiempo para evaluar el nivel de preparación de los usuarios e implementar un plan de comunicación y capacitación antes de implementar cualquiera de los modos descritos en este documento.

> [!TIP]
> Únase a nosotros para realizar talleres interactivos y en directo en los que compartiremos instrucciones, procedimientos recomendados y recursos diseñados para iniciar la planeación e implementación de actualizaciones.
>
>Para empezar, únase en primer lugar a la sesión [Planificar la actualización](https://aka.ms/SkypeToTeamsPlanning).


## <a name="upgrade-journey-building-blocks"></a>Bloques de construcción de la vía de actualización

A fin de preparar formalmente la organización para que pase a Teams, debe empezar a planificar los escenarios de actualización que finalmente permitirán a la organización adoptar plenamente Teams como única solución de colaboración y comunicación.

Para recibir orientación sobre el proceso de toma de decisiones, familiarícese con los distintos modos, conceptos y terminología relevantes para actualizar de Skype Empresarial a Teams. Para obtener más información, consulte Coexistencia e interoperabilidad de Microsoft Teams y [Skype Empresarial.](https://aka.ms/SkypeToTeams-Coexist)

> [!NOTE]
> También necesitará tener en cuenta sus escenarios de migración de voz. Sistema telefónico es la tecnología de Microsoft para habilitar el control de llamadas y las capacidades de central de conmutación (PBX) en la nube de Microsoft 365 u Office 365. Para conectar Sistema telefónico a la red telefónica conmutada (RTC) para que los usuarios puedan realizar llamadas telefónicas en todo el mundo, tiene opciones en función de sus necesidades empresariales. Para obtener más información sobre las opciones de conectividad de Sistema telefónico y RTC, vea [Voz: Sistema telefónico y Conectividad con RTC.](cloud-voice-landing-page.md)

Un usuario que ha migrado a Teams ya no usa un cliente de Skype Empresarial, salvo para incorporarse a una reunión mantenida en Skype Empresarial. Todos los chats y llamadas entrantes se fijon en el cliente de Teams del usuario, independientemente de si el remitente usa Teams o Skype Empresarial. Todas las reuniones nuevas organizadas por el usuario actualizado se programarán como reuniones de Teams. Si el usuario intenta usar el cliente de Skype Empresarial, se bloqueará el inicio de chats y llamadas<sup>1</sup>. Sin embargo, el usuario puede (y debe) seguir usando el cliente de Skype Empresarial para incorporarse a las reuniones a las que sea invitado.

Los administradores gestionan la transición a Teams aplicando el concepto de [modo](migration-interop-guidance-for-teams-with-skype.md), que es una propiedad de [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps). Un usuario que se ha migrado a Teams como se describe anteriormente se encuentra en el modo "TeamsOnly". En el caso de una organización que va a migrar a Teams, el objetivo final es pasar a todos los usuarios al modo TeamsOnly.

Hay dos métodos para migrar una organización existente con Skype Empresarial (tanto en línea como local) a Teams:

- El **método de funciones superpuestas** (con el modo Islas): se presenta Teams a los usuarios de una organización existente con Skype Empresarial para que puedan usar ambos clientes en paralelo durante una fase transitoria. Durante este período, la mayoría de las funciones de Teams (pero no todas) están disponibles para ellos. El modo de esta configuración se conoce como Islas y este es el modo predeterminado para cualquier organización existente con Skype Empresarial. Una vez que la organización está preparada, el administrador pasa a los usuarios al modo TeamsOnly.

- Método de **funciones seleccionadas** (con uno o varios modos de Skype Empresarial): el administrador gestiona la transición (de Skype Empresarial a Teams) para las funcionalidades de chat, llamadas y programación de reuniones para los usuarios de su organización. Cada una de estas funciones está disponible en Skype Empresarial o en Teams, pero no en ambas aplicaciones. Los administradores usan TeamsUpgradePolicy para controlar cuándo una funcionalidad pasa a Teams para los usuarios. Los usuarios que todavía no están en el modo TeamsOnly continúan usando Skype Empresarial para chat y llamadas, y los dos conjuntos de usuarios pueden comunicar entre sí mediante la funcionalidad de interoperabilidad. Los administradores gestionan la transición mediante la migración progresiva de más usuarios al modo TeamsOnly.

<sup>1 Los</sup> clientes antiguos de Skype Empresarial que se enviaron antes de 2017 no respetan TeamsUpgradePolicy. Asegúrese de que utiliza el cliente más reciente de Skype Empresarial disponible en su canal de Office.

A continuación se muestran los factores clave para ayudarle a decidir cuál es la ruta de acceso adecuada para su organización. 

## <a name="overlapping-capabilities-method-using-islands-mode"></a>Método de funciones superpuestas (con el modo Islas)

Con el método de funciones superpuestas, los usuarios pueden usar tanto equipos como clientes de Skype Empresarial para chat, llamadas VoIP y reuniones. En este método, el chat y las llamadas de VoIP en Teams son prioritarios dentro de la organización, mientras que Skype Empresarial permite chat y llamadas VOIP/RTC con organizaciones externas (si se ha configurado). Es posible programar y asistir a reuniones en ambos productos.

Al usar el método de funciones superpuestas, el tráfico de comunicación para Skype Empresarial y Teams permanece separado (incluso para el mismo usuario) y los dos diferentes clientes nunca se comunican entre sí (para los usuarios de la misma organización). Las experiencias de usuario se basan en la configuración del destinatario. Por ejemplo, supongamos que el destinatario Usuario A utiliza este método de actualización:

- La comunicación iniciada desde el cliente de Skype Empresarial de otro usuario siempre llegará al cliente de Skype Empresarial del usuario A.

- La comunicación iniciada desde el cliente de Teams de un usuario de la *misma* organización siempre llegará al cliente de Teams del usuario A.

- La comunicación iniciada desde el cliente de Teams *de* un usuario de una organización externa siempre llegará al cliente de Skype Empresarial del usuario A.

Si ha asignado una licencia de Microsoft 365 u Office 365 a los usuarios, esta será la experiencia de actualización predeterminada para su organización. Al asignar una licencia de Microsoft 365 u Office 365, se asignan tanto las licencias de Teams como de Skype Empresarial Online de forma predeterminada. <sup>2</sup>

Para que este método funcione de forma eficaz, todos los usuarios deben ejecutar simultáneamente ambos clientes. Los chats y llamadas entrantes desde la organización a un usuario en el modo Islas pueden llegar al cliente de Skype Empresarial o al de Teams, circunstancia esta que no está bajo el control del destinatario. Depende del cliente que el remitente use para iniciar la comunicación. Si el remitente y el destinatario están en distintas organizaciones, las llamadas entrantes y chats a un usuario en modo Islas siempre se encuentran en el cliente de Skype Empresarial.

Por ejemplo, si el destinatario en modo Islas inicia sesión en Skype Empresarial, pero no en Teams y alguien le envía un mensaje desde Teams, el destinatario en modo Islas no verá el mensaje (en lugar de ello recibirá un correo electrónico en el que se le indicará que se ha recibido un mensaje en Teams). De manera similar, si un usuario está ejecutando Teams pero no es Skype Empresarial y alguien le envía un mensaje desde Skype Empresarial, el usuario no verá este chat. El comportamiento en cada uno de estos casos es similar para las llamadas. Si los usuarios no ejecutan ambos clientes, se pueden producir situaciones frustrantes.

La presencia también funciona de forma independiente entre Teams y Skype Empresarial con este método de actualización. Esto significa que los otros usuarios pueden ver diferentes estados de presencia para el Usuario A en función del cliente que utilicen. Para obtener más información, consulte [Presencia](upgrade-to-Teams-on-prem-coexistence.md#presence).

- Otros usuarios, al usar Teams, verán la presencia en función de la actividad del usuario A en Teams.

- Otros usuarios, al usar Skype Empresarial, verán la presencia en función de la actividad del usuario A en Skype Empresarial.

Una vez que esté listo para actualizar usuarios al modo TeamsOnly, puede actualizar los usuarios de forma individual o bien puede actualizar toda la organización a la vez mediante el uso de la directiva de ámbito empresarial<sup>3</sup>. Una vez que un usuario se actualiza al modo TeamsOnly, este recibe todas las conversaciones y llamadas entrantes en Teams.

Sin embargo, los destinatarios no actualizados en modo Islas pueden seguir recibiendo chats y llamadas de un usuario TeamsOnly en los clientes de Skype Empresarial o de Teams. Para las conversaciones existentes, el usuario en TeamsOnly responderá al cliente desde el cual el remitente haya iniciado el chat o la llamada. 

Para las nuevas conversaciones desde el punto de vista del usuario de TeamsOnly, el chat o la llamada siempre irán a los usuarios del modo Islas del cliente teams. Esto se debe a que el cliente de Teams mantiene hilos de conversación independientes para las comunicaciones Teams-Teams y Teams-Skype Empresarial, incluso para el mismo usuario. Para obtener más información, consulte [Conversaciones de Teams: interoperabilidad frente a hilos nativos](upgrade-to-teams-on-prem-coexistence.md#teams-conversations---interop-versus-native-threads).

En la tabla siguiente se resume la experiencia de Teams para los modos Islas y TeamsOnly:

| Experiencia de Teams | En modo Islas | En modo TeamsOnly |
|:------------------ | :------------------- | :------------------ |
| Chats y llamadas entrantes recibidos en:|  Teams o Skype Empresarial | Teams |
| Llamadas RTC recibidas en: | Skype Empresarial <br>(El uso de la función RTC en equipos no es compatible con el modo Islas).     | Teams |   
 |Presencia    | La presencia en Skype Empresarial y en Teams es independiente. Los usuarios pueden ver diferentes estados para el mismo usuario en modo Islas en función del cliente que utilicen. | La presencia se basa únicamente en la actividad del usuario en Teams. El resto de usuarios, independientemente del cliente que usen, verán esta presencia. | 
 | Programación de reuniones    | Los usuarios pueden programar reuniones en Teams o en Skype Empresarial. De forma predeterminada, verán ambos complementos en Outlook. Puede establecer una directiva de reunión de Teams para controlar si los usuarios solo pueden usar el complemento de reunión de Teams o los complementos de reunión de Teams y skype empresarial. Para obtener más información, [consulte Establecer el proveedor de reuniones para los usuarios en el modo Islas.](meeting-policies-in-teams.md#meeting-policy-settings---meeting-provider-for-islands-mode) |     Los usuarios solo pueden programar reuniones en Teams. En Outlook, solo está disponible el complemento Teams. | 

En la tabla siguiente se resumen las ventajas e inconvenientes de usar el método de funciones superpuestas para migrar su organización a Teams.

| Ventajas     |       Inconvenientes |
| :------------------ | :---------------- |
| Permite una rápida adopción en la organización.| Existe un potencial de confusión para el usuario final debido a que existen dos clientes con funcionalidades similares pero interfaces de usuario diferentes. Además, no tienen control sobre el cliente al que llegan los mensajes de chat o llamadas entrantes. |
| Permite a los usuarios aprender y familiarizarse con Teams y seguir teniendo acceso completo a Skype Empresarial. | Existe un potencial de insatisfacción para el usuario final debido a la pérdida de mensajes si el usuario no ejecuta los dos clientes.|
| Mínimo esfuerzo de administración para empezar a trabajar en Teams. | Puede resultar difícil salir de las islas y pasar al modo TeamsOnly si los usuarios y aquellos con los que se comunican regularmente no usan Teams de forma activa.|
|Permite a los usuarios aprovechar funciones para mejorar el trabajo en equipo que no están disponibles en Skype Empresarial.| Un usuario que utiliza Skype Empresarial en local y Teams no podrá comunicarse desde Teams con otros usuarios que usen Skype Empresarial en local pero no dispongan de Teams.  |

<sup>2 Esto</sup> es así incluso si el usuario está en local en Skype Empresarial Server. Tanto si el usuario está en local como si está en línea, deje la licencia de Skype Empresarial Online habilitada, dado que actualmente es necesaria para la plena funcionalidad de Teams.

<sup>3 Tenga</sup> en cuenta que la migración de reuniones de Skype Empresarial a reuniones de Teams solo se activa al aplicar TeamsUpgradePolicy a usuarios individuales, no de forma individual por espacio empresarial. Para obtener más información, consulte [Migración de reuniones](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).

## <a name="select-capabilities-method-using-skype-for-business-modes"></a>Seleccionar el método de funcionalidades (con modos de Skype Empresarial)

Es posible que algunas organizaciones prefieran ofrecer a los usuarios finales una experiencia más predecible a medida que su organización pasa de Skype Empresarial a Teams. En este modelo, los administradores de TI usan uno de los modos de Skype Empresarial en TeamsUpgradePolicy para designar explícitamente las funciones que permanecen en Skype Empresarial antes de migrar al modo TeamsOnly. Una vez que los usuarios están listos para cambiar las funcionalidades seleccionadas al modo TeamsOnly, el administrador actualiza el modo para estos usuarios a TeamsOnly. Durante esta transición:

- Los administradores tienen opciones para habilitar algunas de las funcionalidades de Teams para los usuarios a la vez que mantienen las funcionalidades de chat y llamadas en Skype Empresarial antes de que los usuarios pasen a la experiencia TeamsOnly. La administración puede habilitar funcionalidades de colaboración de Teams o reuniones de Teams + funcionalidades de colaboración.

- Los usuarios que aún están en Skype Empresarial reciben todos los chats y llamadas entrantes en su cliente de Skype Empresarial, independientemente de si la comunicación se ha originado en el cliente de Teams o Skype Empresarial del otro usuario. Además, para estos usuarios de Skype Empresarial, las funciones de llamadas y chat en el cliente de Teams están deshabilitadas para evitar confusiones de los usuarios finales y asegurar un enrutamiento y una presencia adecuados.

- Los usuarios en el modo TeamsOnly reciben todos los chats y llamadas entrantes en su cliente de Teams, y Teams indica la presencia, independientemente de dónde se originó la comunicación: Teams, Skype empresarial o cualquier tipo de usuario federado.

A diferencia del método de funcionalidades superpuestas, en el método de seleccionar funcionalidades los usuarios que usan Skype Empresarial pueden comunicarse con los usuarios que se encuentran en TeamsOnly. La comunicación entre un usuario de Skype Empresarial y un usuario de Teams se denomina [interoperabilidad](upgrade-to-Teams-on-prem-coexistence.md#interoperability) o "interoperabilidad". La comunicación de interoperabilidad es posible a un nivel uno a uno para chats y llamadas entre usuarios en Skype Empresarial y otros usuarios en Teams. Además, los usuarios invitados siempre pueden unirse a una reunión de Skype Empresarial o de Teams, pero deben usar un cliente que se corresponda con el tipo de reunión. Para obtener más información, consulte [Reuniones](upgrade-to-Teams-on-prem-coexistence.md#meetings).

Para los usuarios del método de selección de funcionalidades, la presencia de un usuario es coherente, independientemente del cliente que use el otro usuario. Si el usuario se encuentra en uno de los modos de Skype Empresarial, todos los demás usuarios verán la presencia en función de la actividad de ese usuario en Skype Empresarial. De forma similar, si un usuario se encuentra en el modo TeamsOnly, todos los demás usuarios verán la presencia en función de la actividad de ese usuario en Teams. Para obtener más información, consulte [Presencia](upgrade-to-Teams-on-prem-coexistence.md#presence).

En el caso de una organización que haya elegido seguir el método de seleccionar funcionalidades, el administrador debe cambiar el modo de todo el espacio empresarial desde Islas al modo adecuado de coexistencia de Skype Empresarial (SfbWithTeamsCollab o SfBWithTeamsCollabAndMeetings).  

La experiencia de los usuarios invitados se ajustará al modo de coexistencia asignado en el ámbito empresarial. Si establece un modo de Skype Empresarial a nivel empresarial, los invitados no podrán chatear, llamar o mostrar su presencia. Para obtener más información, consulte [Acceso de invitado a Teams](guest-access.md).

Cuando el modo cambia de Islas a SfbWithTeamsCollab, un usuario que nunca haya usado Teams no verá ninguna diferencia en cómo usar Skype Empresarial. Sin embargo, si el usuario empieza a usar Teams, solo estará expuesto a funcionalidades como Teams, canales y archivos. El chat, las llamadas y la programación de reuniones no estarán disponibles en Teams, puesto que el administrador ha designado (por ahora) Skype Empresarial como el cliente deseado para estas funciones.

> [!NOTE]
> Cuando el usuario A cambia de Islas a uno de los modos de Skype Empresarial, el cliente de Teams de cualquier otro usuario que se comunique con el Usuario A necesita saber que el modo del Usuario A ha cambiado para que pueda enrutar la comunicación al cliente adecuado para el Usuario A. Para cualquier usuario que ya haya establecido chats nativos de Teams a Teams con el usuario A, puede llevar tiempo que los clientes de Teams de estos otros usuarios sean conscientes del cambio de modo de Islas a cualquier modo de Skype Empresarial. Cuando los administradores estén listos, pueden cambiar el chat, las llamadas y la programación de reuniones de un usuario determinado a Teams a la vez actualizando el modo del usuario a TeamsOnly.

Como alternativa, el administrador de puede mover primero la programación de reuniones a Teams, dejando que el chat y las llamadas funcionen en Skype Empresarial mediante el modo SfBWithTeamsCollabAndMeetings. Este modo permite a las organizaciones pasar a Teams para reuniones, si los usuarios aún no están listos para pasar al modo TeamsOnly (por ejemplo, aún no está listo para migrar la funcionalidad RTC existente). Este escenario transitorio se denomina [Reuniones primero](meetings-first.md).


|Experiencia de Teams  |En el modo SfBWithTeamsCollab |En el modo SfBWithTeamsCollabAndMeetings |En modo TeamsOnly  |
|---------|---------|---------|---------|
|Chats y llamadas VoIP entrantes procedentes de los usuarios de su organización recibidos en:     | Skype Empresarial        | Skype Empresarial       | Teams        |
|Llamadas RTC recibidas en:     | Skype Empresarial        |Skype Empresarial         | Teams        |
|Presencia     | Skype Empresarial        |Skype Empresarial         | Teams        |
|Programación de reuniones     | Skype Empresarial         | Teams        | Teams        |


En la tabla siguiente se resumen las ventajas e inconvenientes de usar los modos de Skype Empresarial como paso transitorio hacia el modo TeamsOnly.

| Ventajas     |       Inconvenientes |
| :------------------ | :---------------- |
| Direccionamiento predecible para el usuario final. Todas las llamadas y chats llegan a Skype Empresarial o a Teams (pero no a ambos), en función de la selección del administrador.|Las conversaciones de interoperabilidad no son compatibles con el texto enriquecido, el uso compartido de archivos y el uso compartido de pantalla. Esto puede solucionarse aprovechando la funcionalidad Reunirse ahora para iniciar una reunión. |
|Puede reducir la confusión de usuarios finales, ya que una función determinada solo está disponible en un único cliente. | Los usuarios no tienen acceso a Teams para las actividades comunes que se realizan en Skype Empresarial, como el chat y las llamadas con antelación a la actualización a TeamsOnly.|
|El administrador tiene mayor control sobre el conjunto de funcionalidades disponibles para los usuarios mientras se realiza la transición desde Skype Empresarial a Teams. | |
| Permite a una organización usar Teams para reuniones, incluso si todavía no está lista para cambiar plenamente al modo TeamsOnly.||
|La presencia de un usuario determinado es la que ven el resto de usuarios, independientemente del cliente que utilicen.||

## <a name="summary-of-upgrade-methods"></a>Resumen de los métodos de actualización
En la tabla siguiente se resumen los métodos de actualización:


|Funciones superpuestas (con el modo Islas)  |Funcionalidades seleccionadas (con modos de Skype Empresarial)  |
|---------|---------|
|Antes de actualizar a TeamsOnly, los usuarios deben ejecutar ambos clientes de forma simultánea, ya que los chats y llamadas entrantes pueden dirigirse a cualquiera de los dos clientes.     | Los chats y llamadas solo se reciben en un cliente, según el modo del destinatario. Los usuarios no actualizados pueden ejecutar ambos clientes, pero no hay ningún solapamiento funcional (las llamadas y el chat no están disponibles en Teams).         |
|Permite a los administradores incluir una función superpuesta (chat, reuniones, llamadas de VoIP) para los usuarios finales, tanto en Skype Empresarial como en Teams, así como para nuevas funcionalidades (equipos y canales) en Teams.     | Permite a los administradores presentar funcionalidades seleccionadas de Teams a los usuarios finales (equipos y canales), sin ofrecer la misma funcionalidad que también existe en Skype Empresarial.        |
|La interoperabilidad entre Skype Empresarial y Teams no existe mientras ambos usuarios se encuentren en modo Islas.      |La interoperabilidad es necesaria para la comunicación entre los usuarios de Skype Empresarial y Teams.         |

> [!NOTE]
> Si no puede seguir los métodos admitidos para migrar sus usuarios desde Skype Empresarial Server a Teams, es posible realizar la transición de los usuarios a Teams quitando Skype Empresarial Server y todos los atributos de usuario relacionados en Active Directory. Una vez que los atributos de Azure Active Directory de los usuarios se han borrado de los atributos de Skype Empresarial Server y los registros DNS se han vuelto a apuntar a Microsoft 365 u Office 365, sería posible licenciar a los usuarios en Microsoft 365 u Office 365 y actualizarlos a Teams. 

> [!IMPORTANT]
> Con la migración total, los datos de contactos y reuniones no se migrarán del entorno local a Microsoft Teams.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/>Punto de decisión</td><td><ul> ¿Qué itinerario de actualización es el adecuado para los requisitos empresariales de su organización?<br><br></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next step"/><br/>Paso siguiente</td><td><ul> Identificar el modelo de implementación actual, los escenarios de casos de uso y las consideraciones clave para su organización informarán sobre el camino a Teams más adecuado para su organización.<br><br></ul></td></tr>
</table>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/>Punto de decisión</td><td><ul> ¿Qué escenario de actualización es aplicable a su organización?<br><br></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Siguientes pasos</td><td><ul> Decida la escala de tiempo del itinerario de actualización de su organización en función de la mensajería, las reuniones y los requisitos empresariales de llamadas.<br><br> Decida el trabajo adicional que necesita para completar el itinerario de la actualización.<br><br></ul></td></tr>
</table>

Después de elegir el mejor viaje de actualización para su organización, [realice la actualización a Teams.](https://aka.ms/SkypeToTeams-Upgrade)
