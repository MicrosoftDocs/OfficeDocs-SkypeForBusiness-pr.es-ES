---
title: Actualizar a teams desde una implementación local de Skype empresarial-Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 10/22/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Actualización de Skype Empresarial a Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6a864828ce925ea289f27de1b3340a50770b4e88
ms.sourcegitcommit: f586d2765195dbd5b7cf65615a03a1cb098c5466
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "44665272"
---
# <a name="upgrade-from-skype-for-business-to-teams-mdash-for-it-administrators"></a>Actualizar de Skype empresarial a teams &mdash; para administradores de ti

## <a name="overview"></a>Información general

Al actualizar de Skype empresarial a Teams, algunas organizaciones necesitan un lanzamiento progresivo planificado y administrado por sus departamentos de ti. Este artículo está dirigido principalmente a administradores de TI en grandes organizaciones locales, pero también puede aplicarse a algunas organizaciones de Skype empresarial online.  Antes de leer este artículo, asegúrese de leer Introducción [a la actualización de Teams](upgrade-start-here.md) y [acerca del marco de actualización](upgrade-framework.md).

>[!NOTE]
>En este artículo se usan los términos Skype empresarial online, Skype empresarial local y Skype empresarial.  El último término se refiere a versiones locales y en línea.

Un usuario que ha migrado a Teams ya no usa un cliente de Skype Empresarial, salvo para incorporarse a una reunión mantenida en Skype Empresarial.  Todos los chats y llamadas pasan al cliente de Teams del usuario, independientemente de si el remitente utiliza Teams o Skype Empresarial. Todas las reuniones nuevas organizadas por el usuario migrado se programarán como reuniones de Teams. Si el usuario intenta usar el cliente de Skype empresarial, la iniciación de chats y llamadas estará bloqueada.  Sin embargo, el usuario puede (y debe) seguir usando el cliente de Skype Empresarial para incorporarse a las reuniones a las que sea invitado. (Los antiguos clientes de Skype empresarial que se entregaron antes 2017 no son compatibles con TeamsUpgradePolicy. Asegúrese de estar usando el último cliente de Skype empresarial.)
 
Los administradores gestionan la transición a Teams aplicando el concepto de [modo](migration-interop-guidance-for-teams-with-skype.md#coexistence-modes), que es una propiedad de [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps). Un usuario que ha migrado a Teams según se ha descrito arriba se encuentra en modo "TeamsOnly".  En el caso de una organización que va a migrar a Teams, el objetivo final es pasar a todos los usuarios al modo TeamsOnly.

Hay dos métodos para migrar una organización existente con Skype Empresarial (tanto en línea como local) a Teams:

- **Método de funciones superpuesta** (con el modo Islas): los usuarios de una organización existente de Skype empresarial se presentan a Teams para que puedan usar ambos clientes durante una fase transitoria. Durante este período, la mayoría de las funciones de Teams (pero no todas) están disponibles para ellos. El modo de esta configuración se conoce como Islas y este es el modo predeterminado para cualquier organización existente con Skype Empresarial. Una vez que la organización está preparada, el administrador pasa a los usuarios al modo TeamsOnly.

- Método de **funciones seleccionadas** (con uno o varios modos de Skype Empresarial): el administrador gestiona la transición (de Skype Empresarial a Teams) para las funcionalidades de chat, llamadas y programación de reuniones para los usuarios de su organización.  Cada una de estas funciones está disponible en Skype Empresarial o en Teams, pero no en ambas aplicaciones. Los administradores usan TeamsUpgradePolicy para controlar cuándo una funcionalidad pasa a Teams para los usuarios. Los usuarios que todavía no están en el modo TeamsOnly continúan usando Skype Empresarial para chat y llamadas, y los dos conjuntos de usuarios pueden comunicar entre sí mediante la funcionalidad de interoperabilidad. Los administradores gestionan la transición mediante la migración progresiva de más usuarios al modo TeamsOnly.  

Este artículo le ayuda a elegir el método adecuado para su organización, ya que describe ambos métodos y presenta los pros y los inconvenientes de cada uno. 

## <a name="overlapping-capabilities-method-using-islands-mode"></a>Método de funciones superpuestas (con el modo Islas)

Con el método de funciones superpuestas, los usuarios pueden usar tanto equipos como clientes de Skype Empresarial para chat, llamadas VoIP y reuniones. Este estado se denomina "islas" porque el tráfico de comunicaciones de Skype empresarial y Teams sigue siendo independiente (incluso para el mismo usuario) y los dos clientes diferentes nunca se comunican entre sí (para los usuarios de la misma organización). Por ejemplo, supongamos que el usuario del destinatario A está en modo islas:

- La comunicación iniciada desde el cliente de Skype Empresarial de otro usuario siempre llegará al cliente de Skype Empresarial del Usuario A.
- La comunicación iniciada desde el cliente de Teams de otro usuario siempre se pondrá al cliente de equipos del usuario A, *si el otro usuario se encuentra en la misma organización*. 
- La comunicación iniciada desde el cliente de Teams de otro usuario siempre estará en el cliente de Skype empresarial del usuario A, *si el otro usuario se encuentra en una organización federada*.

El modo islas es el modo predeterminado de TeamsUpgradePolicy para cualquier organización existente que aún no TeamsOnly. Cuando asigna una licencia de Microsoft 365 o de Office 365, se asignan licencias de equipo y de Skype empresarial online de forma predeterminada. (Esto es cierto incluso si el usuario está alojado en local en Skype empresarial Server. Si el usuario se ha alojado en local o en línea, deje habilitada la licencia de Skype empresarial online, porque actualmente es necesaria para la funcionalidad de Teams completa. De hecho, si no ha tomado ningún paso para cambiar la configuración predeterminada, es posible que ya tenga un uso significativo de los equipos de su organización.  Este es uno de los beneficios del enfoque de funcionalidades superpuestas. Permite una adopción rápida y controlada por el usuario final dentro de una organización.

Para que este método funcione de forma eficaz, es necesario que todos los usuarios ejecuten ambos clientes al mismo tiempo. Los chats y llamadas entrantes desde la organización a un usuario en el modo Islas pueden llegar al cliente de Skype Empresarial o al de Teams, circunstancia esta que no está bajo el control del destinatario. Depende del cliente que el remitente use para iniciar la comunicación. Si el remitente y el destinatario están en distintas organizaciones, las llamadas entrantes y chats a un usuario en modo Islas siempre se encuentran en el cliente de Skype Empresarial.  

Por ejemplo, si un destinatario de modo de islas ejecuta Skype empresarial pero no equipos, y alguien lo envía mensajes de Teams, el destinatario del modo islas no verá el mensaje (pero al final recibirá un mensaje de correo electrónico que indica que ha perdido un mensaje en Teams). De manera similar, si un usuario está ejecutando Teams pero no es Skype Empresarial y alguien le envía un mensaje desde Skype Empresarial, el usuario no verá este chat.  Recibirán un mensaje de correo electrónico en el que se indica que había un mensaje perdido. El comportamiento en cada uno de estos casos es similar para las llamadas. Si los usuarios no ejecutan ambos clientes, se pueden producir situaciones frustrantes.

Cuando el usuario A está en modo islas, la presencia del usuario A tal y como lo ven otros usuarios en Teams y en Skype empresarial es independiente:

- Los otros usuarios que utilicen Teams verán la presencia en función de la actividad del Usuario A en Teams. 
- Los otros usuarios que utilicen Skype Empresarial verán la presencia en función de la actividad del Usuario A en Skype Empresarial. 

Esto significa que los otros usuarios pueden ver diferentes estados de presencia para el Usuario A en función del cliente que utilicen. Para obtener más información, consulte [Presencia](#presence).

Una vez que esté listo para actualizar a los usuarios al modo TeamsOnly, puede actualizar los usuarios de forma individual o puede actualizar todo el inquilino a la vez con la Directiva para todo el inquilino. Una vez que un usuario se actualiza al modo TeamsOnly, este recibe todas las conversaciones y llamadas entrantes en Teams. (Tenga en cuenta que la migración de reuniones de Skype empresarial a reuniones de Teams solo se desencadena cuando se aplica TeamsUpgradePolicy a usuarios individuales, no por espacio empresarial. Consulte [migración de reuniones](#meeting-migration) para obtener más información.)

Sin embargo, los destinatarios no actualizados en modo Islas pueden seguir recibiendo chats y llamadas de un usuario TeamsOnly en los clientes de Skype Empresarial o de Teams.  Esto se debe a que el cliente de Teams mantiene hilos de conversación independientes para las comunicaciones Teams-Teams y Teams-Skype Empresarial, incluso para el mismo usuario.  (Consulte [conversaciones de Teams: interoperabilidad frente a subprocesos nativos](#teams-conversations---interop-versus-native-threads)).  Por ejemplo, supongamos que el usuario A de las islas usa Teams para enviar un mensaje a TeamsOnly usuario B. Cuando el usuario B responda a esa conversación, la comunicación se situará en el cliente de equipos del usuario A. Supongamos que el usuario A usa su cliente de Skype empresarial para enviar un mensaje a TeamsOnly usuario B. el usuario B recibirá la conversación en Teams, pero será una conversación independiente en el cliente de equipos del usuario B en comparación con la otra conversación. Si el usuario B responde a esta conversación con el usuario A, se colocará en el cliente de Skype empresarial del usuario A. 

En la tabla siguiente se resume la experiencia de Teams para los modos Islas y TeamsOnly:  

| Experiencia de Teams | En modo Islas | En modo TeamsOnly |
|:------------------ | :------------------- | :------------------ |
| Chats y llamadas entrantes recibidos en:|  Teams o Skype Empresarial | Teams |
| Llamadas RTC recibidas en: | Skype Empresarial <br>(El uso de la función RTC en equipos no es compatible con el modo Islas).    | Teams |   
 |Presencia  | La presencia en Skype Empresarial y en Teams es independiente. Los usuarios pueden ver diferentes estados para el mismo usuario en modo Islas en función del cliente que utilicen. | La presencia está basada únicamente en la actividad del usuario en Teams. El resto de usuarios, independientemente del cliente que usen, verán esta presencia. | 
 | Programación de reuniones   | Los usuarios pueden programar reuniones en Teams o en Skype Empresarial. Se mostrarán ambos complementos en Outlook. |   Los usuarios solo pueden programar reuniones en Teams. En Outlook, solo está disponible el complemento Teams. | 

En la tabla siguiente se resumen las ventajas e inconvenientes de usar el método de funciones superpuestas para migrar su organización a Teams.

| Ventajas     |       Inconvenientes |
| :------------------ | :---------------- |
| Permite una rápida adopción en la organización.| Existe un potencial de confusión para el usuario final debido a que existen dos clientes con funcionalidades similares pero interfaces de usuario diferentes. Además, no tienen control sobre el cliente al que llegan los mensajes de chat o llamadas entrantes. |
| Permite a los usuarios aprender y familiarizarse con Teams y seguir teniendo acceso completo a Skype Empresarial. | Existe un potencial de insatisfacción para el usuario final debido a la pérdida de mensajes si el usuario no ejecuta los dos clientes. Los usuarios pueden quejarse de que no reciben mensajes.|
| Mínimo esfuerzo de administración para empezar a trabajar en Teams. | Puede ser desafiante "salir del modo islas" y pasar al modo TeamsOnly si no todos los miembros de la organización usan equipos, especialmente si no todos los usuarios están activos en Teams. Por ejemplo, una vez que un subconjunto de usuarios se actualiza al modo TeamsOnly, los usuarios solo se enviarán en Teams. Para el resto de la población en el modo islas, esos mensajes siempre estarán en el equipo. Pero si algunos de esos rellenados no se ejecutan en Teams, percibirán estos mensajes como perdidos. |
|  | Cuando se usan equipos, los usuarios que tienen una cuenta local en Skype empresarial Server no admiten la compatibilidad con la interoperabilidad o la Federación.  Esto puede crear confusión si tiene una combinación de usuarios de islas, algunas personas que se encuentran en Skype empresarial online y otras en Skype empresarial local.   |

## <a name="select-capabilities-method-using-skype-for-business-modes"></a>Seleccionar el método de funcionalidades (con modos de Skype Empresarial)

Es posible que algunas organizaciones prefieran proporcionar a los usuarios finales una experiencia más predecible y sencilla a medida que su organización pase de Skype empresarial a equipos. En este modelo, los administradores de ti usan uno de los modos de Skype empresarial en TeamsUpgradePolicy para designar de forma explícita qué usuarios permanecen en Skype empresarial antes de migrar al modo TeamsOnly. Puesto que están listos para desplazar a los usuarios seleccionados al modo TeamsOnly, el administrador actualiza el modo de que esos usuarios TeamsOnly. A medida que progresa la implementación, se transfieren cada vez más usuarios de Skype empresarial a modo TeamsOnly.  Durante esta transición:

- Los usuarios que siguen en Skype Empresarial reciben todas las conversaciones y llamadas entrantes en el cliente de Skype Empresarial, independientemente de si la comunicación proviene del cliente de Teams o de Skype Empresarial del otro usuario. Además, para estos usuarios de Skype empresarial, la funcionalidad de llamadas y chats en el cliente de equipos están deshabilitadas para ayudar a evitar la confusión del usuario final y garantizar el enrutamiento adecuado. 

- Los usuarios en modo TeamsOnly reciben todas las conversaciones y las llamadas entrantes en el cliente de su equipo, independientemente de dónde se originó la comunicación: Teams, Skype empresarial o cualquier tipo de usuario federado. 

A diferencia del método islas, en el método de selección de funciones, los usuarios de Skype empresarial y de TeamsOnly pueden comunicarse entre sí. La comunicación entre un usuario de Skype Empresarial y un usuario de Teams se conoce como interoperabilidad (o «interop»). (Consulte [interoperabilidad](#interoperability)). La comunicación interoperativa es posible en una base de uno a uno para conversaciones y llamadas entre usuarios de Skype empresarial y otros usuarios de Teams. Además, los usuarios invitados siempre pueden unirse a una reunión de Skype Empresarial o de Teams, pero deben usar un cliente que se corresponda con el tipo de reunión. Para obtener más información, consulte [Reuniones](#meetings).

Como los usuarios de una transición de funciones de selección no suelen estar en modo islas, la presencia de un usuario es coherente, independientemente del cliente que use el otro usuario. Si el usuario está en uno de los modos de Skype Empresarial, el resto de usuarios verán la presencia en función de la actividad de este usuario en Skype Empresarial. De forma similar, si un usuario está en modo TeamsOnly, el resto de usuarios verán la presencia en función de la actividad de este usuario en Teams. Para obtener más información, consulte [Presencia](#presence).

Para una organización que aún no ha empezado a usar Teams, el administrador debe cambiar el modo de todo el inquilino de islas a SfbWithTeamsCollab. (En el caso de organizaciones que ya tienen algunos usos de Teams, el administrador debe tener a los usuarios "abuelo" activos en Teams para asegurarse de que este cambio no se aplique a ellos. Para obtener más información, vea [una actualización de funciones seleccionadas para una organización que ya está usando el modo islas](#a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode).)

Cuando el modo cambia de islas a SfbWithTeamsCollab, los usuarios que nunca hayan usado Teams no verán ninguna diferencia en el modo en que usan Skype empresarial. Sin embargo, si el usuario empieza a usar Teams, solo estará expuesto a funcionalidades como Teams, canales y archivos. El chat, las llamadas y la programación de reuniones no estarán disponibles en Teams, puesto que el administrador ha designado (por ahora) Skype Empresarial como el cliente deseado para estas funciones.  

Nota: cuando el usuario A cambia de islas a uno de los modos de Skype empresarial, el cliente de Teams de cualquier otro usuario que se comunique con el usuario A debe saber que el modo del usuario a ha cambiado para que pueda enrutar la comunicación al cliente a adecuado para el usuario A.  Para los usuarios que ya hayan establecido chats nativos entre equipos con el usuario A, pueden tardar hasta 36 horas en que los clientes de los equipos de estos otros usuarios sean conscientes del cambio de modo de islas a cualquier modo de Skype empresarial.   Por el contrario, otros clientes detectan cambios en el modo de TeamsOnly de un usuario existente en un plazo de 2 horas.

Cuando los administradores estén listos, podrán pasar de una vez el chat, las llamadas y la programación de reuniones de un usuario determinado a Teams actualizando el modo del usuario a TeamsOnly.  

Como alternativa, el administrador de puede mover primero la programación de reuniones a Teams, dejando que el chat y las llamadas funcionen en Skype Empresarial mediante el modo SfBWithTeamsCollabAndMeetings. Este modo permite que las organizaciones pasen a los equipos de las reuniones, si aún no están listos para pasar al modo TeamsOnly (normalmente porque es posible que se necesite más tiempo para migrar la funcionalidad de RTC existentes). Este escenario transitorio se denomina [Reuniones primero](meetings-first.md).


En la tabla siguiente se resumen las ventajas e inconvenientes de usar los modos de Skype Empresarial como paso transitorio hacia el modo TeamsOnly.


| Ventajas     |       Inconvenientes |
| :------------------ | :---------------- |
| Direccionamiento predecible para el usuario final.  Todas las llamadas y chats llegan a Skype Empresarial o a Teams (pero no a ambos), en función de la selección del administrador.  | Las conversaciones de interoperabilidad no son compatibles con el texto enriquecido, el uso compartido de archivos y el uso compartido de pantalla.  Esto se puede llevar a cabo con las reuniones a petición, pero no es tan fácil.  |
| Elimine la confusión entre usuarios finales porque una determinada función solo está disponible en un cliente.  | Los usuarios no pueden probar ambos clientes en paralelo para el mismo conjunto de funciones. Esto puede ser especialmente un factor si los usuarios perciben que el cambio de Skype empresarial a teams es un cambio de paradigma importante. |
| Permite una introducción incremental de Teams.  |  | |
| El administrador tiene el control total de la transición de Skype empresarial a teams. |  | | 
| Permite a una organización usar Teams para reuniones, incluso si todavía no está lista para cambiar plenamente al modo TeamsOnly. |  | |
| La presencia de un usuario determinado es la que ven el resto de usuarios, independientemente del cliente que utilicen.  |  | |

## <a name="summary-of-upgrade-methods"></a>Resumen de los métodos de actualización

En la tabla siguiente se resumen los métodos de actualización:

| Funciones superpuestas (con el modo Islas)     |      Seleccionar capacidades (con los modos de Skype empresarial) |
| :------------------ | :---------------- |
| Antes de actualizar a TeamsOnly, los usuarios deben ejecutar ambos clientes de forma simultánea, ya que los chats y llamadas entrantes pueden dirigirse a cualquiera de los dos clientes.   | El chat y las llamadas llegan a un solo cliente, en función del modo del destinatario. Los usuarios no actualizados pueden ejecutar ambos clientes, pero no hay ningún solapamiento funcional (las llamadas y el chat no están disponibles en Teams).  Los administradores también pueden controlar si los usuarios programan reuniones en Teams o Skype empresarial.   |
| Los usuarios pueden usar Skype empresarial y Teams en paralelo para obtener la misma funcionalidad.   | Permite a los administradores introducir una nueva funcionalidad de Teams para los usuarios finales (equipos y canales), sin proporcionar la misma funcionalidad que también existe en Skype empresarial.   |
|La interoperabilidad entre Skype Empresarial y Teams no existe mientras ambos usuarios se encuentren en modo Islas. Una vez que se actualizan algunos usuarios a TeamsOnly, es posible que se produzca una conversación interoperativa entre los usuarios y otros usuarios que aún se encuentren en modo islas. Sin embargo, el usuario de las islas podría optar por usar Teams y evitar la conversación de interoperabilidad. | La interoperabilidad es necesaria para la comunicación entre los usuarios de Skype Empresarial y Teams.   |

## <a name="tools-for-managing-the-upgrade"></a>Herramientas para administrar la actualización

Para cualquiera de los métodos descritos anteriormente, los administradores administran la transición a TeamsOnly con [TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps), que controla el modo de coexistencia de un usuario. Para obtener más información sobre cada uno de los modos, vea [modos de coexistencia](migration-interop-guidance-for-teams-with-skype.md#coexistence-modes).

Si el administrador realiza una transición de funciones seleccionadas con los modos de Skype empresarial o simplemente actualiza al modo TeamsOnly desde la configuración de islas predeterminadas, TeamsUpgradePolicy es la herramienta principal.  Como cualquier otra directiva de Teams, TeamsUpgradePolicy se puede asignar directamente a un usuario, y también se puede establecer como el valor predeterminado para todo el inquilino. Cualquier asignación a un usuario tiene prioridad sobre la configuración predeterminada de inquilino.  Se puede administrar en la consola de administración de Teams y en PowerShell.

Los administradores pueden asignar cualquier modo de TeamsUpgradePolicy a los usuarios si el usuario se aloja en Skype empresarial online o en el entorno local, excepto que el modo TeamsOnly solo se puede asignar a un usuario que ya esté alojado en Skype empresarial online. Esto se debe a que la interoperabilidad con usuarios y la Federación de Skype empresarial solo es posible si el usuario se ha alojado en Skype empresarial online.

Los usuarios con cuentas de Skype empresarial domésticas locales [deben moverse por Internet](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) (ya sea a Skype empresarial online o directamente a teams) mediante Move-CsUser en el conjunto de herramientas de Skype empresarial local. Estos usuarios se pueden mover a TeamsOnly en 1 o 2 pasos:

-   1 paso: especificar el modificador-MoveToTeams en Move-CsUser. Para ello, necesita Skype empresarial Server 2019 o Skype empresarial Server 2015 con CU8.

-   2 pasos: después de ejecutar Move-CsUser, conceda el modo TeamsOnly al usuario mediante TeamsUpgradePolicy.

A diferencia de otras directivas, no es posible crear nuevas instancias de TeamsUpgradePolicy en Microsoft 365 u Office 365. Todas las instancias existentes están integradas en el servicio.  (Tenga en cuenta que el modo es una propiedad dentro de TeamsUpgradePolicy, en lugar del nombre de una instancia de directiva). En algunos, pero no en todos los casos, el nombre de la instancia de directiva es el mismo que el modo. En concreto, para asignar el modo de TeamsOnly a un usuario, conceda la instancia "UpgradeToTeams" de TeamsUpgradePolicy a ese usuario. Para ver una lista de todas las instancias, puede ejecutar el siguiente comando:

```PowerShell
Get-CsTeamsUpgradePolicy|ft Identity, Mode, NotifySfbUsers
```

Para actualizar un usuario en línea al modo TeamsOnly, asigne la instancia "UpgradeToTeams": 

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $user 
```

Para actualizar un usuario local de Skype empresarial al modo TeamsOnly, use Move-CsUser en el conjunto de herramientas local:

```PowerShell
Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred
```

Para cambiar el modo para todos los usuarios del espacio empresarial, excepto aquellos que tienen una concesión de conceder por usuario explícita (que tiene prioridad), ejecute el siguiente comando:

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
```


>[!NOTE]
>Si tiene usuarios con cuentas de Skype empresarial en el nivel local, no debe asignar el modo de TeamsOnly en el nivel del espacio empresarial, a menos que asigne de forma explícita algún otro modo a todos los usuarios con cuentas locales de Skype empresarial.


### <a name="using-notifications-in-skype-for-business-clients"></a>Uso de notificaciones en clientes de Skype empresarial

Los administradores tienen la opción de proporcionar notificaciones de usuario final en el cliente de Skype empresarial para informar a los usuarios de que pronto se actualizarán a Teams, tal y como se muestra en el siguiente diagrama. Por ejemplo, una semana antes de que el administrador planea actualizar un grupo de usuarios al modo TeamsOnly, es posible que el administrador desee activar estas notificaciones para ese grupo de usuarios. Estas notificaciones se habilitan mediante una instancia de TeamsUpgradePolicy con NotifySfbUsers = true.  Para todos los modos distintos de TeamsOnly, en realidad existen dos instancias por modo, que corresponden a los dos valores de NotifySfbUsers.  Para todos los modos distintos de TeamsOnly, en realidad existen dos instancias por modo, que corresponden a los dos valores de NotifySfbUsers. 

![Diagrama que muestra las notificaciones](media/teams-upgrade-sfb-with-notifications.png)

Si los usuarios están alojados en Skype empresarial online, simplemente asigne la instancia de directiva que tiene el mismo modo que el usuario, pero con NotifySfbUsers = true. 

Si los usuarios están alojados en Skype empresarial Server local, tendrá que usar el conjunto de herramientas local y necesitará Skype empresarial Server 2019 o CU8 para Skype empresarial Server 2015... En la ventana de PowerShell local, cree una nueva instancia de TeamsUpgradePolicy con NotifySfbUsers = true:

```PowerShell
New-CsTeamsUpgradePolicy -Identity EnableNotification -NotifySfbUsers $true
```

Después, con la misma ventana de PowerShell local, asigne esa nueva Directiva a los usuarios que desee:

```PowerShell
Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName EnableNotification
```

### <a name="meeting-migration"></a>Migración de reuniones

Cuando se migra un usuario al modo TeamsOnly, las reuniones de Skype empresarial existentes que organizó se convertirán en Teams de forma predeterminada. Si lo desea, puede deshabilitar el comportamiento predeterminado al asignar el modo de TeamsOnly a un usuario. Al mover usuarios de forma local, las reuniones se deben migrar a la nube para que funcione con la cuenta de usuario en línea, pero si no especifica-MoveToTeams, las reuniones se migrarán como reuniones de Skype empresarial, en lugar de convertirlas a teams. 

Al asignar el modo de TeamsOnly en el nivel de espacio empresarial, la migración de reuniones no se desencadena para ningún usuario. Si desea asignar el modo de TeamsOnly en el nivel de inquilino y migrar reuniones, puede usar PowerShell para obtener una lista de los usuarios en el espacio empresarial (por ejemplo, usar Get-CsOnlineUser con los filtros necesarios) y, a continuación, recorra cada uno de estos usuarios para desencadenar la migración de reuniones con Start-CsExMeetingMigration. Para obtener más información, vea [usar el servicio de migración de reuniones (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).


### <a name="additional-considerations-for-organizations-with-skype-for-business-server-on-premises"></a>Consideraciones adicionales para las organizaciones con Skype empresarial Server local

- La configuración del entorno híbrido de Skype empresarial es un requisito previo para migrar al modo TeamsOnly. Aunque es posible usar equipos en el modo islas sin entornos híbridos, no se puede realizar la transición al modo TeamsOnly hasta que el usuario pase de Skype empresarial local a Skype empresarial online (mediante [Move-CsUser](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)). Para obtener más información, vea [configurar la conectividad híbrida](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-hybrid-connectivity).

- Los usuarios de equipos que tienen una cuenta de Skype empresarial local (es decir, que aún no se han movido a la nube mediante Move-CsUser) no pueden interoperar con ningún usuario de Skype empresarial ni pueden federarse a usuarios externos. Esta función solo está disponible cuando los usuarios se mueven a la nube (ya sea en modo islas o como usuarios de TeamsOnly). 

- Si tiene usuarios con cuentas de Skype empresarial en el nivel local, no debe asignar el modo de TeamsOnly en el nivel del espacio empresarial, a menos que asigne de forma explícita algún otro modo a todos los usuarios con cuentas locales de Skype empresarial. 

- Debe asegurarse de que los usuarios estén sincronizados correctamente en Azure AD con los atributos correctos de Skype empresarial. Estos atributos son todos los prefijos con "msRTCSIP-". Si los usuarios no se sincronizan correctamente con Azure AD, las herramientas de administración de Teams no podrán administrar estos usuarios. Para obtener más información, vea [configurar Azure ad Connect para Teams y Skype empresarial](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-azure-ad-connect).

- Para crear un nuevo usuario de TeamsOnly o de Skype empresarial online en una organización híbrida, *primero debe habilitar el usuario en Skype empresarial Server local*y, después, mover el usuario de local a la nube con Move-CsUser.  La creación del usuario en local primero garantiza que todos los demás usuarios locales de Skype empresarial podrán enrutar al usuario recién creado. Una vez que todos los usuarios se han movido a Internet, ya no es necesario que habilite primero los usuarios en local.

- Cuando un usuario se mueve de local a la nube, las reuniones organizadas por ese usuario se migran a Skype empresarial online o Teams, en función de si se especifica o no el modificador-MoveToTeams.

- Si desea mostrar las notificaciones en el cliente de Skype empresarial para los usuarios locales, debe usar TeamsUpgradePolicy en el conjunto de herramientas local. Solo el parámetro NotifySfbUsers es relevante para los usuarios locales.  Los usuarios locales obtienen su modo de las instancias en línea de TeamsUpgradePolicy. Consulte las notas en [Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps). 

>[!NOTE]
> Los nuevos inquilinos creados después del 3 de septiembre de 2019 se crean como inquilinos de TeamsOnly, a menos que la organización ya tenga una implementación local de Skype empresarial Server. Microsoft usa los registros DNS para identificar las organizaciones locales de Skype empresarial Server. Si su organización tiene Skype empresarial Server local sin entradas DNS públicas, tendrá que llamar al servicio de soporte técnico de Microsoft para descalificar el nuevo inquilino. 


## <a name="perform-the-upgrade-for-your-organization"></a>Realizar la actualización de su organización

En esta sección se describen las siguientes opciones de actualización:

- Actualización de capacidades superpuestas (con el modo Islas)
- Una actualización de las funciones seleccionadas para una organización que aún no ha empezado a usar Teams
- Una actualización de las funciones seleccionadas para una organización que ya usa equipos en el modo islas

### <a name="overlapping-capabilities-upgrade-using-islands-mode"></a>Actualización de capacidades superpuestas (con el modo Islas)

Para la opción de actualización capacidades superpuestas:

- Considere esta opción si puede realizar una actualización rápida para su organización general.  Dado que hay riesgo potencial de confusión con la ejecución de ambos clientes, es mejor si puede minimizar este período de tiempo. Debe asegurarse de que los usuarios sepan ejecutar ambos clientes.

- Esta opción es el modelo que no está en el equipo y no requiere ninguna acción de administrador para comenzar a usar Teams excepto para asignar la licencia de Microsoft 365 o de Office 365. Si los usuarios ya tienen Skype empresarial online, es posible que ya esté en este modelo.

- Puede resultar difícil sacar provecho del modo de funciones superpuestas y pasar a TeamsOnly. Como los usuarios actualizados solo se comunican a través de Teams, cualquier otro usuario de la organización que se comunique con ese usuario debe estar usando Teams.  Si tiene usuarios que no han empezado a usar Teams, se mostrarán a los mensajes que faltan. Además, no verán los usuarios de TeamsOnly en línea en Skype empresarial. Algunas organizaciones eligen realizar una actualización para todos los inquilinos con la directiva global de inquilino para evitar esto, pero requieren la espera hasta que todos los usuarios estén listos para su actualización.


### <a name="a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams"></a>Una actualización de las funciones seleccionadas para una organización que aún no ha empezado a usar Teams

Si su organización aún no tiene ningún usuario activo en Teams, el primer paso es establecer la directiva predeterminada para el inquilino para TeamsUpgradePolicy en uno de los modos de Skype empresarial, por ejemplo, SfbWithTeamsCollab.  Los usuarios que aún no hayan comenzado a usar Teams no apreciarán ninguna diferencia en el comportamiento. Sin embargo, la configuración de esta directiva en el nivel de espacio empresarial permite empezar a actualizar usuarios al modo TeamsOnly y garantiza que los usuarios actualizados puedan seguir comunicándose con usuarios no actualizados.  Una vez que hayas identificado a los usuarios de la prueba piloto, puedes actualizarlos a TeamsOnly.  Si son locales, usa Move-CsUser. Si están conectados, simplemente asígnelos a TeamsOnly Mode con TeamsUpgradePolicy.  De forma predeterminada, cualquier reunión de Skype empresarial programada por estos usuarios se migrará a teams.

A continuación se muestran los comandos clave:

1. Establezca el valor predeterminado para el inquilino en modo SfbWithTeamsCollab de la siguiente manera:

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
   ```

2. Actualice el usuario a TeamsOnly como se indica a continuación:

   - Si el usuario ya está conectado:

     ```PowerShell
     Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $username 
     ```

   - Si el usuario es local:

     ```PowerShell
     Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
     ```

Notas
 
- En lugar de establecer la Directiva de todo el inquilino en SfbWithTeamsCollab, puede establecerla en SfbWithTeamsCollabAndMeetings. Esto hace que todos los usuarios programen todas las reuniones nuevas en Teams.
- Move-CsUser es un cmdlet en las herramientas locales. El conmutador MoveToTeams requiere Skype empresarial Server 2019 o Skype empresarial Server 2015 con CU8. Si está usando una versión anterior, puede mover primero el usuario a Skype empresarial online y, a continuación, conceder el modo TeamsOnly a ese usuario.
- De forma predeterminada, las reuniones de Skype empresarial se migran a teams al actualizar al modo TeamsOnly o al asignar el modo SfbWithTeamsCollabAndMeetings.  

El diagrama siguiente muestra las fases conceptuales de actualización de las funciones seleccionadas para una organización sin un uso previo de Teams. El alto de las barras representa el número de usuarios. Durante cualquier fase de la actualización, todos los usuarios pueden comunicarse entre sí.  Los usuarios de Skype empresarial se comunican con usuarios de TeamsOnly usando interoperabilidad y viceversa.

![Diagrama que muestra la selección de funciones de selección sin un uso previo de Teams](media/teams-upgrade-1.png)


### <a name="a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode"></a>Una actualización de las funciones seleccionadas para una organización que ya usa equipos en el modo islas

Si algunos usuarios de su organización usan activamente equipos en modo islas, es probable que no desee quitar la funcionalidad de los usuarios existentes. Por lo tanto, es necesario un paso adicional antes de cambiar la Directiva de todo el inquilino. La solución es "abuelo", es decir, los usuarios existentes de equipos activos en modo islas, antes de establecer la política de todos los inquilinos en SfbWithTeamsCollab.  Una vez que lo haya hecho, puede proceder con la implementación como se indica anteriormente, pero tendrá dos grupos de usuarios que se están moviendo a TeamsOnly: los usuarios que estuvieron activos en Teams estarán en modo islas y el resto de usuarios estarán en el modo SfbWithTeamsCollab. Puede mover estos usuarios progresivamente al modo TeamsOnly.

1. Busque usuarios que estén activos en Teams de la siguiente manera:

   1. En el centro de administración de Microsoft 365, en la barra de navegación de la izquierda, vaya a informes y, después, uso. 
   2. En la lista desplegable "seleccionar un informe", elija Microsoft Teams y, a continuación, actividad del usuario. Esto proporcionará una tabla exportable de usuarios que han estado activos en Teams. 
   3. Haga clic en exportar, abrir Excel y filtro para mostrar solo los usuarios que están activos en Teams.

2. Para cada usuario de equipos activos que se encuentra en el paso 1, asigne el modo islas en el PowerShell remoto. Esto le permite ir al paso siguiente y se asegura de que no cambie la experiencia del usuario.  

   ```PowerShell
   $users=get-content “C:\MyPath\users.txt” 
    foreach ($user in $users){ 
    Grant-CsTeamsUpgradePolicy -identity $user -PolicyName Islands} 
   ```

3. Establezca la Directiva de todo el inquilino en SfbWithTeamsCollab:

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Global -PolicyName SfbWithTeamsCollab 
   ```

4. Actualice los usuarios seleccionados al modo TeamsOnly. Puede optar por actualizar los usuarios en el modo islas o SfbWithTeamsCollab, aunque es posible que desee dar prioridad a la actualización de los usuarios en el modo islas en primer lugar para minimizar la posibilidad de confusión que puede producirse cuando los usuarios están en modo islas.   

   Para usuarios alojados en Skype empresarial online:  

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams 
   ```

   Para los usuarios alojados en Skype empresarial Server local:  

   ```PowerShell
   Move-CsUser -Identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
   ```

El diagrama siguiente muestra las fases conceptuales de una transición de selección de funciones en la que hay usuarios de islas activas al principio. El alto de las barras representa el número de usuarios. Durante cualquier fase de la actualización, todos los usuarios pueden comunicarse entre sí.  Los usuarios de Skype empresarial se comunican con usuarios de TeamsOnly usando interoperabilidad y viceversa.


![Diagrama que muestra las funciones de selección actualizar con usuarios activos en modo islas](media/teams-upgrade-2.png)

   

## <a name="considerations-for-pstn-calling"></a>Consideraciones para las llamadas RTC

Si se trata de una función de llamadas RTC, existen cuatro escenarios posibles para pasar al modo TeamsOnly:

- *Un usuario de Skype empresarial online con un plan de llamadas de Microsoft*. Después de la actualización, este usuario seguirá teniendo un plan de llamadas de Microsoft.

- *Un usuario de Skype empresarial online con funcionalidad de voz local* a través de Skype empresarial local o Cloud Connector Edition. La actualización del usuario a teams debe coordinarse con la migración del usuario al enrutamiento directo para garantizar que el usuario de TeamsOnly tiene la funcionalidad de RTC.

- *Un usuario de Skype empresarial local con telefonía IP empresarial, que se va a migrar a en línea y mantener la conectividad RTC local*.  Migrar este usuario a teams requiere mover la cuenta de Skype empresarial local del usuario a la nube y coordinar ese movimiento con la migración del usuario al enrutamiento directo. 

- *Un usuario de Skype empresarial local con telefonía IP empresarial*, que se va a migrar a en línea y usar un plan de llamadas de Microsoft.  Migrar este usuario a teams requiere mover la cuenta de Skype empresarial local del usuario a la nube y coordinar el movimiento con una o A una) el puerto del número de ese usuario a un plan de llamadas de Microsoft o B asignar un nuevo número de suscriptor de las regiones disponibles.

Este artículo proporciona una descripción general de alto nivel únicamente. Para obtener más información, consulte [planes de llamadas](calling-plan-landing-page.md)y [enrutamiento directo de sistema telefónico](direct-routing-landing-page.md) . Además, tenga en cuenta que el uso de sistema telefónico con Teams solo se admite cuando el usuario está en modo TeamsOnly.  Si el usuario está en modo islas, el sistema telefónico solo es compatible con Skype empresarial. 

### <a name="from-skype-for-business-online-with-microsoft-calling-plans"></a>Desde Skype empresarial online con planes de llamadas de Microsoft 

Este es el escenario de actualización más sencillo que implica voz. 

1. Asegúrese de que los usuarios tienen asignada una licencia de Teams. De forma predeterminada, cuando asigna una licencia de Microsoft 365 o de Office 365, Teams está habilitado, por lo que, a menos que previamente haya deshabilitado la licencia de Teams, no es necesario realizar ninguna acción.

2.  Si los usuarios ya tienen un plan de llamadas de Microsoft con un número de teléfono, el único cambio necesario es asignar el modo de TeamsOnly de usuario en TeamsUpgradePolicy.  Antes de asignar el modo de TeamsOnly, las llamadas RTC entrantes estarán en el cliente de Skype empresarial del usuario. Después de la actualización a modo TeamsOnly, las llamadas RTC entrantes estarán en el cliente de equipos del usuario.  

### <a name="from-skype-for-business-online-with-on-premises-voice"></a>Desde Skype empresarial online con voz local

En este escenario, el usuario ya está en Skype empresarial online, pero su conectividad RTC es local, ya sea usando Skype empresarial Server en modo híbrido o en la edición de la nube. Migrar a estos usuarios al modo de TeamsOnly con la funcionalidad de RTC significa habilitarlos para el enrutamiento directo, en el que los troncos RTC se conectan directamente al servicio de enrutamiento directo en la nube, a través del controlador de borde de sesión (SBC) local.

A continuación se enumeran los pasos básicos.  Los pasos 1-4 se enumeran en la secuencia sugerida, pero se pueden realizar en cualquier orden. La clave es que todas estas opciones deben completarse antes del paso 5.

1. Si va a establecer la Directiva de todo el inquilino en uno de los modos de Skype empresarial, asegúrese de que los usuarios de las islas actuales les asignen expresamente el modo islas, tal como se ha descrito anteriormente.

2. Configure el inquilino para el enrutamiento directo. Consulte [Resumen de la configuración por inquilino de enrutamiento directo](#summary-of-per-tenant-configuration-of-direct-routing).

3. Si lo desea, configure varias directivas de Teams para estos usuarios (por ejemplo, TeamsMessagingPolicy, TeamsMeetingPolicy, etc.). Esto se puede hacer en cualquier momento, pero si desea asegurarse de que los usuarios tengan la configuración correcta cuando se actualicen, es mejor hacerlo antes de que el usuario se actualice al modo TeamsOnly.

4. Preparar usuarios para la migración de voz: 
   - Si es necesario, asigne la licencia de Teams.  Suponiendo que el usuario ya es funcional en la voz local de Skype empresarial online, el usuario ya tiene Skype empresarial plan 2 y Microsoft Phone System. Deje ambos planes habilitados, incluyendo la licencia de Skype empresarial online plan 2.  
   - Asigne el OnlineVoiceRoutingPolicy deseado. 

5. Actualice el usuario: estos pasos deben ser coordinados. 

   - En Microsoft 365 u Office 365, actualice el usuario al modo TeamsOnly (Grant-CsTeamsUpgradePolicy).
   - En la SBC, configure el enrutamiento de voz para habilitar las llamadas entrantes enviando llamadas al enrutamiento directo en lugar de al servidor de mediación local.


### <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing"></a>Desde Skype empresarial Server local, con telefonía IP empresarial, para dirigir el enrutamiento

En este escenario, el usuario aún se ha alojado en Skype empresarial local y su conectividad RTC también es local. Migrar a estos usuarios a modo TeamsOnly con la funcionalidad de RTC significa habilitarlos para el enrutamiento directo y, después, mover el usuario a la nube. 
 
A continuación se enumeran los pasos básicos.  Los pasos 1-5 se enumeran en la secuencia sugerida, pero se pueden realizar en cualquier orden. La clave es que todas estas opciones deben completarse antes del paso 6.

1. Si va a establecer la Directiva de todo el inquilino en uno de los modos de Skype empresarial, asegúrese de que los usuarios de las islas existentes les asignan expresamente el modo islas, tal como se ha descrito anteriormente.

2. Si aún no lo ha hecho, [Configure la organización para la implementación híbrida de Skype empresarial](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity).

3. Configure el inquilino para el enrutamiento directo. Consulte [Resumen de la configuración por inquilino de enrutamiento directo](#summary-of-per-tenant-configuration-of-direct-routing).

4. Si lo desea, configure varias directivas de Teams para estos usuarios (por ejemplo, TeamsMessagingPolicy, TeamsMeetingPolicy, etc.). Esto se puede hacer en cualquier momento, pero si desea asegurarse de que los usuarios tengan la configuración correcta cuando se actualicen, es mejor hacerlo antes de que el usuario se actualice a TeamsOnly.

5. Asigne las licencias de Microsoft 365 u Office 365 si es necesario.  El usuario debe tener tanto equipos como Skype empresarial online plan 2, así como un sistema telefónico. Si el plan 2 de Skype empresarial online está deshabilitado, vuelva a habilitarlo.  

6. Actualice el usuario: estos pasos deben ser coordinados. 

   - Con las herramientas locales de Skype empresarial, ejecute Move-CsUser with-MoveToTeams switch. Si está usando una versión de Skype empresarial Server que no admite el modificador-MoveToTeams, ejecute primero Move-CsUser y, a continuación, asigne el modo TeamsOnly en PowerShell Remote de inquilino o en la consola de administración de Teams.

   - En la SBC, configure el enrutamiento de voz para habilitar las llamadas entrantes enviando llamadas al enrutamiento directo en lugar de al servidor de mediación local. 

   - En Microsoft 365 u Office 365: asigne el OnlineVoiceRoutingPolicy relevante para habilitar las llamadas salientes. 


### <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan"></a>Desde Skype empresarial Server local, con telefonía IP empresarial, plan de llamadas de Microsoft

En este escenario, el usuario aún se ha alojado en Skype empresarial local y su conectividad RTC también es local. Migrar a estos usuarios a modo TeamsOnly con la funcionalidad de RTC significa mover el usuario a la nube y migrar su número desde el antiguo operador a un plan de llamadas de Microsoft o asignar un número nuevo al usuario. 

A continuación se enumeran los pasos básicos.Los pasos 1-5 se enumeran en la secuencia sugerida, pero se pueden realizar en cualquier orden. La clave es que todas estas opciones deben completarse antes del paso 6. 

1. Si va a establecer la Directiva de todo el inquilino en uno de los modos de Skype empresarial, asegúrese de que los usuarios de las islas existentes les asignan expresamente el modo islas, tal como se ha descrito anteriormente. 

2. Si aún no lo ha hecho, [Configure la organización para la implementación híbrida de Skype empresarial](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity). 

3. Si lo desea, configure varias directivas de Teams para estos usuarios (por ejemplo, TeamsMessagingPolicy, TeamsMeetingPolicy, etc.). Esto se puede hacer en cualquier momento, pero si desea asegurarse de que los usuarios tengan la configuración correcta cuando se actualicen, es mejor hacerlo antes de que el usuario se actualice a TeamsOnly. 

4. Asigne las licencias de Microsoft 365 u Office 365 si es necesario.El usuario debe tener tanto equipos como Skype empresarial online plan 2, así como un sistema telefónico. Si el plan 2 de Skype empresarial online está deshabilitado, vuelva a habilitarlo.  

5. Obtener números de teléfono para los usuarios. (Para obtener información detallada, consulte [administrar números de teléfono de su organización](https://docs.microsoft.com/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)).

   - Si va a volver a usar los números, envíe una solicitud de portabilidad a su operador.  
   - También puede adquirir números nuevos directamente desde Microsoft. 

6. Actualice el usuario. Con las herramientas locales de Skype empresarial, ejecute Move-CsUser con el modificador-MoveToTeams.  

    - Si va a trasladar números a Microsoft, debe coordinar los intervalos de esta operación para que se produzcan cuando se produzca el puerto. 

    - Si está usando números nuevos de Microsoft, tendrá que cambiar el LineUri para el usuario.Esto debe hacerse en las herramientas locales y, a continuación, sincronizarse con la nube a través de Azure AD Connect. Si Azure AD Connect sincroniza el cambio, debe usar la operación de movimiento y CsUser para estar al día. 

### <a name="summary-of-per-tenant-configuration-of-direct-routing"></a>Resumen de la configuración por inquilino de enrutamiento directo 

1. Para asegurarse de que el controlador de borde de sesión (SBC) es compatible con el enrutamiento directo, revisamos [esta lista](direct-routing-border-controllers.md). También debe asegurarse de que tiene la versión correcta del firmware.  

2. Empareje su SBC local con el servicio de enrutamiento directo de Teams. Para obtener más información, consulte [emparejar la SBC al servicio de enrutamiento directo del sistema telefónico](direct-routing-configure.md). 

3. Esta configuración es esencialmente un reflejo de la configuración local. La configuración electrónica consiste en: 
   - OnlineVoiceRoutingPolicy (basado en la VoiceRoutingPolicy local si migra usuarios de Skype empresarial online y se basa en VoicePolicy Si migra usuarios de local con Enterprise Voice).
   - Objetos OnlinePSTNUsage (basados en el uso local de RTC). 
   - Objetos OnlineVoiceRoute (basados en VoiceRoute locales). 

Para obtener más información, vea [configurar el enrutamiento directo](direct-routing-configure.md). 

### <a name="manage-enterprisevoiceenabled-property-during-migration"></a>Administrar la propiedad EnterpriseVoiceEnabled durante la migración 

Si usa enrutamiento directo o un plan de llamadas de Microsoft, un usuario debe tener EnterpriseVoiceEnabled = true en Azure AD para que el usuario tenga la funcionalidad RTC.  EnterpriseVoiceEnabled ("EV-Enabled") es una propiedad (no una directiva) que existe en un directorio local y en la nube. El valor en la nube es lo que importa a teams.  La lógica exacta de cómo se establece la función EV-Enabled en true depende del siguiente escenario: 

- Si el usuario está habilitado para EV en el servidor local de Skype empresarial y se asigna una licencia de sistema telefónico al usuario antes de mover el usuario a la nube con Move-CsUser, se aprovisionará al usuario en línea con EV-Enabled = true. 

- Si un TeamsOnly existente o un usuario de Skype empresarial online tiene asignada una licencia de sistema telefónico, la función EV-Enabled no se establece en true de forma predeterminada.  Esto también sucede si un usuario local se mueve a la nube antes de asignar la licencia de sistema telefónico. En cualquiera de los casos, el administrador debe especificar el siguiente cmdlet: 

  ```PowerShell
  Set-CsUser -EnterpriseVoiceEnabled $True 
  ```

## <a name="coexistence-of-teams-with-skype-for-business"></a>Coexistencia de equipos con Skype empresarial

En esta sección se resume el comportamiento que se puede producir al ejecutar tanto los equipos como los clientes de Skype empresarial en la misma organización, independientemente del modo y el método de actualización que se use:

- [Reuniones](#meetings)
- [Interoperabilidad](#interoperability)
- [Conversaciones de Teams: interoperabilidad frente a subprocesos nativos](#teams-conversations---interop-versus-native-threads)
- [Presence](#presence)
- [Federación](#federation)
- [Contactos](#contacts)

### <a name="meetings"></a>Reuniones

Independientemente de su modo, los usuarios siempre pueden unirse a cualquier tipo de reunión a la que se les invite, ya sea Skype empresarial o Teams.  Sin embargo, los usuarios deben unirse a la reunión con un cliente correspondiente que coincida con el tipo de reunión:

- Si la reunión es una reunión de Teams, todos los participantes (ya sean TeamsOnly, Islas o usuarios de Skype empresarial) usan el cliente de Teams para unirse a la reunión. Si Teams no está instalado, se dirigirá al usuario a la web, al intentar unirse a una reunión.

- Si la reunión es una reunión de Skype empresarial, todos los participantes (ya sean TeamsOnly, Islas o usuarios de Skype empresarial) usan el cliente de Skype empresarial para unirse a la reunión. Si el cliente de Skype empresarial no está instalado, se dirigirá al usuario a la web para unirse a través de la aplicación de reunión de Skype.

Al organizar reuniones, el tipo de reunión que se programa se basa en el modo de organizador, como se muestra en la tabla siguiente:

| Modo del organizador    |      Comportamiento |
| :------------------ | :---------------- |
| TeamsOnly, SfbWithTeamsCollabAndMeetings |    Todas las reuniones programadas en Teams. El complemento de Skype empresarial no está disponible en Outlook. | 
| SfbWithTeamsCollab, SfbOnly   | Todas las reuniones programadas en Skype empresarial. El complemento de Teams no está disponible en Outlook. | 
| Aplicaciones aisladas |     Las reuniones se pueden programar en Skype empresarial o en Teams. Ambos complementos están disponibles en Outlook. | 


### <a name="interoperability"></a>Interoperabilidad

Teams es compatible con la interoperabilidad ("interoperabilidad") con Skype empresarial en algunos escenarios. La comunicación interoperativa hace referencia a una conversación o una llamada entre un usuario de Skype empresarial y un usuario de Teams.  La comunicación de interoperabilidad solo es posible entre dos usuarios; no es posible hacer llamadas y chats de varios participantes ni agregar usuarios adicionales.

Se crea un chat o una llamada entre dos usuarios cuando se cumple cada una de las siguientes condiciones:

- Un usuario está usando Teams y el otro está usando Skype empresarial.

- El modo del receptor de la comunicación inicial no es islas (de lo contrario, la comunicación se situaría en el mismo cliente) si ambos usuarios están en la misma organización. En los escenarios federados, el usuario que envía está usando Teams y el destinatario no está en modo TeamsOnly. 

- El usuario de los equipos no tiene una cuenta de Skype empresarial doméstica local. 

Dentro de la comunicación de interoperabilidad, chat solo es texto sin formato. Además, el uso compartido de archivos y la pantalla compartida no son posibles *en el chat de interoperabilidad propiamente*dicho. Sin embargo, los usuarios de una conversación de interoperabilidad pueden lograr fácilmente el uso compartido de archivos y/o pantalla mediante la creación de una reunión a petición, desde dentro de la conversación interoperativa, como se describe a continuación:

- Si el usuario de Teams intenta compartir su pantalla, se crea automáticamente una reunión de equipos a petición y se envía un vínculo de invitación a la reunión al cliente del usuario de Skype empresarial. Al hacer clic en el vínculo, el usuario de Skype empresarial abrirá Teams y se unirá a la reunión. Ambos usuarios están ahora en una reunión de Teams y pueden compartir según sea necesario.

- Si el usuario de Skype empresarial está usando un cliente de 2018 o posterior e intenta compartir cualquier contenido, se crea automáticamente una reunión a petición de Skype empresarial y se envía un vínculo de invitación a la reunión al cliente del usuario de Teams. Al hacer clic en el vínculo, el usuario de Teams intentará unirse a la reunión de Skype empresarial. Si el usuario de Teams tiene instalado el cliente de Skype empresarial, se abrirá y se solicitará que el usuario inicie sesión (si aún no lo ha hecho).  Si el usuario de Teams no tiene instalado el cliente de Skype empresarial, se le pedirá que use la versión Web. Una vez que los dos usuarios han iniciado sesión, están en una reunión de Skype empresarial y pueden compartirlo según sea necesario.

### <a name="teams-conversations---interop-versus-native-threads"></a>Conversaciones de Teams: interoperabilidad frente a subprocesos nativos

Dado que las comunicaciones interoperativas no admiten todas las características de la conversación de equipos nativos, el cliente de Teams mantiene hilos de conversaciones independientes para la comunicación entre equipos y equipos entre usuarios de Skype empresarial. Estas conversaciones se representan de forma diferente en la interfaz de usuario: los subprocesos de interoperabilidad se pueden diferenciar de un subproceso de equipo nativo normal por:

- Ausencia de controles para texto enriquecido, uso compartido de archivos/pantallas, incapacidad para agregar usuarios.
- Una modificación en el icono del usuario de destino, en la que se muestra una "S" para Skype empresarial.

Estas diferencias se muestran en las siguientes capturas de pantallas:

Una conversación de equipos nativos a equipos con la prueba G3 de usuario

![Diagrama que muestra una conversación entre equipos nativo](media/teams-upgrade-native-thread.png)

Una conversación de interoperabilidad con la misma prueba G3 de usuario

![Diagrama que muestra una conversación interoperativa entre equipos](media/teams-upgrade-interop-thread.png)

Una vez que se crea una conversación, su tipo nunca cambia. Una vez creado, un subproceso de interoperabilidad de Teams siempre se enrutará al cliente de Skype empresarial del usuario de destino. Un subproceso nativo siempre se enrutará al cliente de equipos del usuario de destino.  Si cambia el modo de un usuario de un destinatario, los subprocesos existentes de Teams a ese usuario dejarán de funcionar y aparecerá una nota en la conversación con un vínculo para iniciar una nueva conversación nativa, tal y como se muestra en la siguiente captura de pantalla. Para obtener más información, consulta [chats y llamadas de subprocesos ya existentes](coexistence-chat-calls-presence.md#chats-and-calls-from-pre-existing-threads).


![Diagrama que muestra una conversación con un usuario de Skype empresarial actualizado](media/teams-upgrade-chat-with-upgraded-sfb-user.png)

### <a name="presence"></a>Presence

La presencia de un usuario determinado se basa en la actividad del usuario en el servicio a través del cliente. A continuación, se publica la presencia de otros usuarios para verlo.  Skype empresarial y Teams son servicios independientes con clientes independientes, de modo que cada servicio tiene su propio estado de presencia para un usuario.   También existe una sincronización entre los servicios de presencia en Teams y Skype empresarial online.  Esto permite que un servicio publique potencialmente la presencia del usuario desde el otro servicio, si es necesario. 

El comportamiento de la publicación de presencia se basa en el modo del usuario. Hay tres casos básicos:

- Si un usuario está en modo TeamsOnly, todos los demás usuarios verán la presencia de Teams para ese usuario, independientemente del cliente que usen.

- Si un usuario se encuentra en cualquiera de los modos de Skype empresarial, todos los demás usuarios verán la presencia de Skype empresarial para ese usuario, independientemente del cliente que usen.

- Si un usuario está en modo islas, la presencia Publicada en Skype empresarial y Teams es independiente, por lo que la presencia que se muestra a los usuarios dentro de la misma organización dependerá del cliente del otro usuario. Los usuarios de organizaciones federadas verán la presencia de ese usuario en función de su actividad de Skype empresarial, ya que el tráfico federado hacia un usuario del modo islas aterriza en Skype empresarial.

Por ejemplo, supongamos que el usuario A está en modo islas. Si el usuario A está activo en Teams pero no ha iniciado sesión en Skype empresarial, otros usuarios verían el usuario A como activo en el cliente de su equipo, pero en su cliente de Skype empresarial, verían el usuario A como desconectado. Esto se debe a su diseño, ya que no se puede comunicar con el usuario A si no ejecuta el cliente. 

Para obtener más información, consulte [presencia](coexistence-chat-calls-presence.md#presence).

### <a name="federation"></a>Federación

La Federación de equipos a otro usuario con Skype empresarial requiere que el usuario de Teams se conecte en línea en Skype empresarial. TeamsUpgradePolicy controla el enrutamiento de las llamadas y chats federados entrantes. El comportamiento de enrutamiento federado es el mismo que para los escenarios de espacio empresarial, excepto en el modo "aplicaciones aisladas". Cuando los destinatarios están en modo Aplicaciones aisladas:

- Chats y llamadas iniciadas desde la tierra de un equipo en Skype empresarial si el destinatario se encuentra en un inquilino federado.
- Chats y llamadas iniciadas desde Teams llegan a Teams si el destinatario está en el mismo espacio empresarial.
- Los chats y las llamadas iniciadas desde Skype empresarial siempre se encuentran en Skype empresarial.

Un chat federado entre un usuario de Teams y un Skype empresarial es un subproceso de interoperabilidad, por lo que no es posible el texto enriquecido y el uso compartido. La interfaz de usuario expone los chats federados de manera similar a los mismos subprocesos de interoperabilidad de inquilino, excepto que hay una nota que indica que el usuario es externo.

Cuando Teams presentó por primera vez la Federación, un chat federado entre dos usuarios de Teams también era un subproceso de interoperabilidad, pero en el futuro, se introducirá la Federación de equipos nativos, que proporciona una funcionalidad completa para las conversaciones entre usuarios que están en modo TeamsOnly. . 

Para obtener más información, consulta [enrutamiento federado para nuevos chats o llamadas](coexistence-chat-calls-presence.md#federated-routing-for-new-chats-or-calls).

### <a name="contacts"></a>Contactos

Teams y Skype empresarial tienen listas distintas de contactos. Esto significa que las adiciones, la eliminación y las modificaciones de los contactos realizados en un sistema no se sincronizan con el otro sistema. Sin embargo, los contactos de Skype empresarial se copian automáticamente en Teams cuando se produce una de las dos sucesos específicos: 

- Para cualquier usuario de Skype empresarial online, la primera vez que inicie sesión en Teams, los contactos de Skype empresarial se copiarán en Teams.  Este comportamiento no está disponible para los usuarios con una cuenta local en Skype empresarial Server.  

- Después de que un usuario se actualice a TeamsOnly (mediante la asignación de TeamsUpgradePolicy o a través de Move-CsUser-MoveToTeams), la próxima vez que un usuario inicie sesión en Teams, los contactos existentes en Skype empresarial se combinarán con los contactos existentes que ya están en Teams. Este comportamiento se produce si la cuenta de Skype empresarial del usuario está hospedada en local o en línea. 

En ambos casos, la transferencia de contactos de Skype empresarial a teams es asincrónica, por lo que puede transcurrir unos minutos antes de que los contactos aparezcan en Teams. Los dos eventos anteriores son lo que desencadena la copia.  

## <a name="related-links"></a>Vínculos relacionados

[Guía de migración e interoperabilidad para organizaciones que usan Teams y Skype Empresarial](migration-interop-guidance-for-teams-with-skype.md) 

[Configurar la conectividad híbrida entre Skype empresarial Server y Microsoft 365 u Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Mover usuarios entre la implementación local y la nube](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Configurar su coexistencia y la configuración de actualización](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Usar el servicio de migración de reuniones (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

