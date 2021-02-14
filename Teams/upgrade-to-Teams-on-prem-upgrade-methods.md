---
title: 'Actualizar a Teams desde una implementación local de Skype Empresarial: Microsoft Teams'
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Actualización de Skype Empresarial a Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2dc8afc48db6264cef5c5ad959f33dd7e738e116
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515797"
---
# <a name="upgrade-methods-mdash-for-it-administrators"></a>Métodos de &mdash; actualización para administradores de TI

En este artículo se describen los métodos de actualización para migrar a Teams. Este artículo es el segundo de varios que describen los conceptos de actualización y la implementación para los administradores de TI.  

- [Información general](upgrade-to-teams-on-prem-overview.md)
- **Métodos de** actualización (en este artículo)
- [Herramientas para administrar la actualización](upgrade-to-teams-on-prem-tools.md)
- [Consideraciones adicionales para las organizaciones con Skype Empresarial local](upgrade-to-teams-on-prem-considerations.md)
- [Implementación de la actualización](upgrade-to-teams-on-prem-implement.md)
- [Consideraciones de la red telefónica conmutada (RTC)](upgrade-to-teams-on-prem-pstn-considerations.md)

Además, en los artículos siguientes se describen conceptos importantes de actualización y comportamientos de coexistencia:

- [Coexistencia de Teams y Skype Empresarial](upgrade-to-teams-on-prem-coexistence.md)
- [Modos de coexistencia - Referencia](migration-interop-guidance-for-teams-with-skype.md)
- [Experiencia del cliente de Teams y cumplimiento con los modos de coexistencia](teams-client-experience-and-conformance-to-coexistence-modes.md)


## <a name="upgrade-methods"></a>Métodos de actualización

Hay dos métodos para actualizar una organización existente con Skype Empresarial (ya sea en línea o local) a Teams: método de funcionalidad superpuesta y el método de seleccionar capacidades. Este artículo le ayudará a elegir el método adecuado para su organización describiendo ambos métodos y presentando las ventajas y desventajas de cada uno. 

- [Método de funciones superpuestas (con el modo Islas)](#overlapping-capabilities-method-using-islands-mode)

   Los usuarios de una organización existente de Skype Empresarial están introducidos en Teams para que puedan usar ambos clientes durante una fase de transición. Durante este período, la mayoría de las funciones de Teams (pero no todas) están disponibles para ellos. El modo de esta configuración se conoce como Islas y este es el modo predeterminado para cualquier organización existente con Skype Empresarial. Cuando la organización esté lista, el administrador moverá los usuarios al modo TeamsOnly.

- [Seleccionar el método de funcionalidad (usando uno o varios de los modos de Skype Empresarial)](#select-capabilities-method-using-skype-for-business-modes)

   El administrador administra la transición (de Skype Empresarial a Teams) de las funciones de chat, llamadas y programación de reuniones para los usuarios de su organización.  Cada una de estas funciones está disponible en Skype Empresarial o en Teams, pero no en ambas aplicaciones. Los administradores usan TeamsUpgradePolicy para controlar cuándo una funcionalidad pasa a Teams para los usuarios. Los usuarios que todavía no están en el modo TeamsOnly continúan usando Skype Empresarial para chat y llamadas, y los dos conjuntos de usuarios pueden comunicar entre sí mediante la funcionalidad de interoperabilidad. Los administradores gestionan la transición mediante la migración progresiva de más usuarios al modo TeamsOnly.  

Después de comprender y elegir el método de actualización, puede obtener información sobre las herramientas para administrar la actualización de su organización [a Teams.](upgrade-to-teams-on-prem-tools.md)

## <a name="overlapping-capabilities-method-using-islands-mode"></a>Método de funciones superpuestas (con el modo Islas)

Con el método de funciones superpuestas, los usuarios pueden usar tanto equipos como clientes de Skype Empresarial para chat, llamadas VoIP y reuniones. Este estado se conoce como modo "Islas" porque el tráfico de comunicación para Skype Empresarial y Teams sigue siendo independiente (incluso para el mismo usuario) y los dos clientes distintos nunca se comunican entre ellos (para los usuarios de la misma organización). Por ejemplo, supongamos que el usuario destinatario A está en el modo Islas:

- La comunicación iniciada desde el cliente de Skype Empresarial de otro usuario siempre llegará al cliente de Skype Empresarial del Usuario A.

- La comunicación iniciada desde el cliente de Teams de otro usuario siempre llegará al cliente de Teams del usuario A, si el otro usuario se *encuentra en la misma organización.* 

- La comunicación iniciada desde el cliente de Teams de otro usuario siempre llegará al cliente de Skype Empresarial del usuario A, si el otro usuario se encuentra *en una organización federada.*

El modo islas es el modo predeterminado de TeamsUpgradePolicy para cualquier organización existente que aún no se haya actualizado a TeamsOnly. Al asignar una licencia de Microsoft 365 u Office 365, se asignan tanto las licencias de Teams como de Skype Empresarial Online de forma predeterminada. (Esto se cumple incluso si el usuario está en local en Skype Empresarial Server. Tanto si el usuario se encuentra en local como en línea, deje habilitada la licencia de Skype Empresarial Online, ya que actualmente se necesita para la funcionalidad completa de Teams). De hecho, si no ha realizado ningún paso para cambiar la configuración predeterminada, es posible que ya tenga un uso significativo de Teams en su organización.  Esta es una de las ventajas del enfoque de funciones superpuestas. Permite una adopción rápida y controlada por el usuario final dentro de una organización.

Para que este método funcione correctamente, requiere que todos los usuarios ejecuten ambos clientes simultáneamente. Los chats y llamadas entrantes desde la organización a un usuario en el modo Islas pueden llegar al cliente de Skype Empresarial o al de Teams, circunstancia esta que no está bajo el control del destinatario. Si el remitente y el destinatario se encuentran en la misma organización, depende del cliente que use el remitente para iniciar la comunicación. Si el remitente y el destinatario están en distintas organizaciones, las llamadas entrantes y chats a un usuario en modo Islas siempre se encuentran en el cliente de Skype Empresarial.  

Por ejemplo, si un destinatario del modo Islas ejecuta Skype Empresarial pero no Teams y alguien de la misma organización le envía un mensaje desde Teams, el destinatario del modo Islas no verá el mensaje (pero finalmente recibirá un correo electrónico en el que se le indica que no ha recibido un mensaje en Teams). De manera similar, si un usuario está ejecutando Teams pero no es Skype Empresarial y alguien le envía un mensaje desde Skype Empresarial, el usuario no verá este chat.  Recibirán un correo electrónico que indica que se ha perdido un mensaje. El comportamiento en cada uno de estos casos es similar para las llamadas. Si los usuarios no ejecutan ambos clientes, se pueden producir situaciones frustrantes.

Cuando el usuario A está en modo de Islas, la presencia del Usuario A como la ven otros usuarios en Teams y en Skype Empresarial es independiente:

- Los otros usuarios que utilicen Teams verán la presencia en función de la actividad del Usuario A en Teams. 
- Los otros usuarios que utilicen Skype Empresarial verán la presencia en función de la actividad del Usuario A en Skype Empresarial. 

Esto significa que los otros usuarios pueden ver diferentes estados de presencia para el Usuario A en función del cliente que utilicen. Para obtener más información, vea [Presencia.](upgrade-to-teams-on-prem-coexistence.md#presence)

Cuando esté listo para actualizar los usuarios al modo TeamsOnly, puede actualizar a los usuarios individualmente o puede actualizar todo el espacio empresarial a la vez con la directiva de todo el inquilino. Una vez que un usuario se actualiza al modo TeamsOnly, este recibe todas las conversaciones y llamadas entrantes en Teams. (Tenga en cuenta que la migración de reuniones de Skype Empresarial a las reuniones de Teams solo se activa al aplicar TeamsUpgradePolicy a usuarios individuales, no de forma individual por espacio empresarial. Vea [la migración de reuniones](upgrade-to-teams-on-prem-tools.md#meeting-migration) para obtener detalles).

Sin embargo, los destinatarios no actualizados en modo Islas pueden seguir recibiendo chats y llamadas de un usuario TeamsOnly en los clientes de Skype Empresarial o de Teams.  Esto se debe a que el cliente de Teams mantiene hilos de conversación independientes para las comunicaciones Teams-Teams y Teams-Skype Empresarial, incluso para el mismo usuario.  (Consulte [Conversaciones de Teams - Interoperabilidad frente a hilos nativos).](upgrade-to-teams-on-prem-coexistence.md#teams-conversations---interop-versus-native-threads)  Por ejemplo, supongamos que el usuario de las Islas A usa Teams para enviar un mensaje al usuario B de Teams. Cuando el usuario B responda a ese chat, la comunicación se mostrará en el cliente de Teams del usuario A. Ahora supongamos que el usuario A usa el cliente de Skype Empresarial para enviar un mensaje al usuario B de Teams. El usuario B recibirá el chat en Teams, pero será una conversación independiente en el cliente de Teams del usuario B en comparación con la otra conversación. Si el usuario B responde a esta conversación con el Usuario A, llegará al cliente de Skype Empresarial del usuario A. 

En la tabla siguiente se resume la experiencia de Teams para los modos Islas y TeamsOnly:  

| Experiencia de Teams | En modo Islas | En modo TeamsOnly |
|:------------------ | :------------------- | :------------------ |
| Chats y llamadas entrantes recibidos en:|  Teams o Skype Empresarial | Teams |
| Llamadas RTC recibidas en: | Skype Empresarial <br>(El uso de la función RTC en equipos no es compatible con el modo Islas).    | Teams |   
 |Presencia  | La presencia en Skype Empresarial y en Teams es independiente. Los usuarios pueden ver diferentes estados para el mismo usuario en modo Islas en función del cliente que utilicen. | La presencia está basada únicamente en la actividad del usuario en Teams. El resto de usuarios, independientemente del cliente que usen, verán esta presencia. | 
 | Programación de reuniones   | De forma predeterminada, los usuarios pueden programar reuniones en Teams o Skype Empresarial. Se mostrarán ambos complementos en Outlook. |   Los usuarios solo pueden programar reuniones en Teams. En Outlook, solo está disponible el complemento Teams. | 

En la tabla siguiente se resumen las ventajas e inconvenientes de usar el método de funciones superpuestas para migrar su organización a Teams.

| Ventajas     |       Inconvenientes |
| :------------------ | :---------------- |
| Permite una rápida adopción en la organización.| Posible confusión al usuario final porque hay dos clientes con funciones similares, pero interfaces de usuario diferentes. Además, no tienen control sobre el cliente al que llegan los mensajes de chat o llamadas entrantes. |
| Permite a los usuarios aprender y familiarizarse con Teams y seguir teniendo acceso completo a Skype Empresarial. | Potencial de insatisfecho para el usuario final debido a mensajes perdidos si el usuario no ejecuta ambos clientes. Es posible que los usuarios se quejan de que no reciben mensajes.|
| Mínimo esfuerzo de administración para empezar a trabajar en Teams. | Puede resultar difícil salir del modo de "salir de las islas" y pasar al modo TeamsOnly si no todas las personas de la organización usan Teams, especialmente si no todos los usuarios están activos en Teams. Por ejemplo, una vez que un subconjunto de usuarios se actualiza al modo TeamsOnly, esos usuarios solo se enviarán en Teams. Para el resto de la población en el modo De las Islas, esos mensajes siempre llegarán a Teams. Pero si parte de esa población no ejecuta Teams, percibirá que esos mensajes se pierden. |
|  | Al usar Teams, los usuarios que tienen una cuenta local en Skype Empresarial Server no tienen compatibilidad de interoperabilidad o federación.  Esto puede crear confusión si tiene una mezcla de usuarios de las Islas, algunos de los que están en Skype Empresarial Online y otros en Skype Empresarial local.   |

## <a name="select-capabilities-method-using-skype-for-business-modes"></a>Seleccionar el método de funcionalidades (con modos de Skype Empresarial)

Es posible que algunas organizaciones prefieran proporcionar a sus usuarios finales una experiencia más predecible y sencilla a medida que su organización pasa de Skype Empresarial a Teams. En este modelo, los administradores de TI usan uno de los modos de Skype Empresarial en TeamsUpgradePolicy para designar explícitamente qué usuarios permanecen en Skype Empresarial antes de migrar al modo TeamsOnly. Cuando estén listos para cambiar los usuarios seleccionados al modo TeamsOnly, el administrador actualiza el modo para esos usuarios a TeamsOnly. A medida que avanza la implementación, cada vez más usuarios pasa de Skype Empresarial al modo TeamsOnly.  Durante esta transición:

- Los usuarios que siguen en Skype Empresarial reciben todas las conversaciones y llamadas entrantes en el cliente de Skype Empresarial, independientemente de si la comunicación proviene del cliente de Teams o de Skype Empresarial del otro usuario. Además, para estos usuarios de Skype Empresarial, las llamadas y las funciones de chat en el cliente de Teams se deshabilitan para ayudar a evitar la confusión de los usuarios finales y garantizar un enrutamiento adecuado. 

- Los usuarios en el modo TeamsOnly reciben todos los chats y llamadas entrantes en su cliente de Teams, independientemente de la ubicación de origen de la comunicación: Teams, Skype Empresarial o cualquier tipo de usuario federado. 

A diferencia del método de las Islas, en el método de capacidades de selección, los usuarios de Skype Empresarial y los usuarios de TeamsOnly pueden comunicarse entre sí. La comunicación entre un usuario de Skype Empresarial y un usuario de Teams se conoce como interoperabilidad (o «interop»). La comunicación de interoperabilidad es posible en uno a uno para los chats y llamadas entre un usuario en Skype Empresarial y otro usuario en Teams; sin embargo, es posible que algunas funciones avanzadas no estén disponibles. (Consulte [Interoperabilidad).](upgrade-to-teams-on-prem-coexistence.md#interoperability) Además, los usuarios invitados siempre pueden unirse a una reunión de Skype Empresarial o de Teams, pero deben usar un cliente que se corresponda con el tipo de reunión. Para obtener más información, consulte [Reuniones](upgrade-to-teams-on-prem-coexistence.md#meetings).

Como la transición de los usuarios de una funcionalidad de selección normalmente no se encuentra en modo de islas, la presencia de un usuario es coherente independientemente del cliente que utilice el otro usuario. Si el usuario está en uno de los modos de Skype Empresarial, el resto de usuarios verán la presencia en función de la actividad de este usuario en Skype Empresarial. De forma similar, si un usuario está en modo TeamsOnly, el resto de usuarios verán la presencia en función de la actividad de este usuario en Teams. Para obtener más información, consulte [Presencia](upgrade-to-teams-on-prem-coexistence.md#presence).

Para las organizaciones que aún no han empezado a usar Teams, el administrador debe cambiar el modo de todo el espacio empresarial de Islas a SfbWithTeamsCollab. (En el caso de organizaciones que ya tienen parte del uso de Teams, el administrador debe "único" usuarios que ya están activos en Teams para asegurarse de que este cambio no se aplica a ellos. Para obtener más información, consulte Un método de capacidades de selección [para una organización que ya usa Teams en modo de islas).](upgrade-to-teams-on-prem-implement.md#a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode)

Cuando el modo cambia de Islas a SfbWithTeamsCollab, un usuario que nunca ha usado Teams no verá ninguna diferencia en cómo usa Skype Empresarial. Sin embargo, si el usuario empieza a usar Teams, solo estará expuesto a funcionalidades como Teams, canales y archivos. El chat, las llamadas y la programación de reuniones no estarán disponibles en Teams, puesto que el administrador ha designado (por ahora) Skype Empresarial como el cliente deseado para estas funciones.  

Nota: Cuando el usuario A cambia de Islas a uno de los modos de Skype Empresarial, el cliente de Teams de cualquier otro usuario que se comunique con el Usuario A debe saber que el modo del Usuario A ha cambiado para que pueda enrutar la comunicación al cliente adecuado para el Usuario A.  Para cualquier usuario que ya haya establecido chats nativos de Teams a Teams con el usuario A, pueden tardar hasta 36 horas hasta que los clientes de Teams de estos otros usuarios sean conscientes del cambio de modo de Islas a cualquier modo de Skype Empresarial.   En cambio, otros clientes descubren los cambios de un usuario existente en el modo TeamsOnly en un plazo de 2 horas.

Cuando los administradores estén listos, podrán pasar de una vez el chat, las llamadas y la programación de reuniones de un usuario determinado a Teams actualizando el modo del usuario a TeamsOnly.  

Como alternativa, el administrador de puede mover primero la programación de reuniones a Teams, dejando que el chat y las llamadas funcionen en Skype Empresarial mediante el modo SfBWithTeamsCollabAndMeetings. Este modo permite a las organizaciones pasar a Teams para reuniones si los usuarios aún no están listos para pasar al modo TeamsOnly (normalmente porque podría ser necesario más tiempo para migrar la funcionalidad RTC existente). Este escenario transitorio se denomina [Reuniones primero](meetings-first.md).

En la tabla siguiente se resumen las ventajas e inconvenientes de usar los modos de Skype Empresarial como paso transitorio hacia el modo TeamsOnly.


| Ventajas     |       Inconvenientes |
| :------------------ | :---------------- |
| Direccionamiento predecible para el usuario final.  Todas las llamadas y chats llegan a Skype Empresarial o a Teams (pero no a ambos), en función de la selección del administrador.  | Las conversaciones de interoperabilidad no son compatibles con el texto enriquecido, el uso compartido de archivos y el uso compartido de pantalla.  Esto se puede trabajar con reuniones a petición, pero esto no es tan fácil.  |
| Elimine la confusión del usuario final porque una funcionalidad determinada solo está disponible en un cliente.  | Los usuarios no pueden probar ambos clientes en paralelo para el mismo conjunto de funciones. Esto puede ser especialmente un factor si los usuarios perciben el cambio de Skype Empresarial a Teams como un importante cambio en el paradigma. |
| Permite la introducción incremental de Teams.  |  | |
| El administrador tiene control total de la transición de Skype Empresarial a Teams. |  | | 
| Permite a una organización usar Teams para reuniones, incluso si todavía no está lista para cambiar plenamente al modo TeamsOnly. |  | |
| La presencia de un usuario determinado es la que ven el resto de usuarios, independientemente del cliente que utilicen.  |  | |

## <a name="summary-of-upgrade-methods"></a>Resumen de los métodos de actualización

En la tabla siguiente se resumen los métodos de actualización:

| Funciones superpuestas (con el modo Islas)     |      Seleccionar funcionalidades (usando los modos de Skype Empresarial) |
| :------------------ | :---------------- |
| Antes de actualizar a TeamsOnly, los usuarios deben ejecutar ambos clientes de forma simultánea, ya que los chats y llamadas entrantes pueden dirigirse a cualquiera de los dos clientes.   | El chat y las llamadas llegan a un solo cliente, en función del modo del destinatario. Los usuarios no actualizados pueden ejecutar ambos clientes, pero no hay ningún solapamiento funcional (las llamadas y el chat no están disponibles en Teams).  Los administradores también pueden controlar si los usuarios programan reuniones en Teams o Skype Empresarial.   |
| Los usuarios pueden usar Skype Empresarial y Teams en paralelo para la misma funcionalidad.   | Permite a los administradores introducir nuevas funciones netas de Teams para los usuarios finales (equipos y canales), sin proporcionar la misma funcionalidad que también existe en Skype Empresarial.   |
|La interoperabilidad entre Skype Empresarial y Teams no existe mientras ambos usuarios se encuentren en modo Islas. Una vez que algunos usuarios se actualizan a TeamsOnly, la conversación de interoperabilidad puede producirse entre esos usuarios y otros usuarios que todavía están en el modo de Islas. Sin embargo, el usuario de las Islas podría elegir usar Teams y evitar la conversación interoperabilidad. | La interoperabilidad es necesaria para la comunicación entre los usuarios de Skype Empresarial y Teams.   |


## <a name="related-links"></a>Vínculos relacionados

[Guía de migración e interoperabilidad para organizaciones que usan Teams y Skype Empresarial](migration-interop-guidance-for-teams-with-skype.md) 

[Configurar la conectividad híbrida entre Skype Empresarial Server y Microsoft 365 u Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Mover usuarios entre la implementación local y la nube](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Configurar su coexistencia y la configuración de actualización](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Usar el servicio de migración de reuniones (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

