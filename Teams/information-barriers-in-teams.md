---
title: Barreras de la información en Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.date: 07/08/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection: Teams_ITAdmin_Help
search.appverid: MET150
ms.reviewer: vikramju
description: Obtenga más información sobre las barreras de información y cómo afectan a teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1238e0e4d015a9216523c96e981e3f37ad54c131
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36245368"
---
# <a name="information-barriers-in-microsoft-teams"></a>Barreras de la información en Microsoft Teams

Las barreras de información son directivas que un administrador puede configurar para evitar que los usuarios o grupos se comuniquen entre sí. Esto es útil si, por ejemplo, un departamento está manejando información que no debe compartir con otros departamentos o que un grupo necesita impedir, o aislar, comunicarse con cualquier persona fuera de ese grupo.

> [!NOTE]
> - Los grupos de barrera de información no se pueden crear en todos los inquilinos.
> - En la versión 1, no se admite el uso de bots para agregar usuarios.
> - Barreras de información la versión 1 no incluye compatibilidad con SharePoint y OneDrive para la empresa. Estamos trabajando para habilitar la característica en SharePoint y se comunicará una vez que esté disponible.

Las directivas de barrera de información también evitan búsquedas y descubrimiento. Esto significa que si intentas comunicarte con alguien con quien no deberías comunicarte, no encontrarás ese usuario en el selector de personas.

## <a name="background"></a>Información general

El impulsor principal para las barreras de la información viene de la industria de servicios financieros. La autoridad legal del sector financiero ([FINRA]( http://www.finra.org)) revisa las barreras de la información y los conflictos de intereses en las empresas miembros y proporciona instrucciones sobre cómo administrar dichos conflictos (FINRA 2241, [aviso normativo de investigación de deudas 15-31](http://www.finra.org/sites/default/files/Regulatory-Notice-15-31_0.pdf).  

## <a name="when-should-i-use-information-barriers"></a>¿Cuándo debo usar las barreras de la información?

Es posible que desee usar barreras de información en situaciones como estas:

- Debe evitarse que un equipo pueda comunicarse o compartir datos con otro equipo específico.
- Un equipo no debe comunicarse ni compartir datos con nadie fuera del equipo.

El servicio de evaluación de directivas de Information barrera determina si una comunicación cumple con las directivas de la barrera de información. 

## <a name="managing-information-barrier-policies"></a>Administración de directivas de la barrera de información

Las directivas de barrera de información se administran en el centro de cumplimiento de & de seguridad de Office 365 (SCC) con los cmdlets de PowerShell. Para obtener más información, consulte [definir directivas para las barreras de la información](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies).

> [!IMPORTANT]
> Antes de configurar o definir directivas, **debe habilitar la búsqueda de directorio en Microsoft Teams**. Espere al menos 24 horas después de habilitar la búsqueda de directorio en el ámbito antes de configurar o definir directivas para barreras de información. [Más información sobre los requisitos previos para las barreras de la información](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies#prerequisites).

## <a name="information-barriers-administrator-role"></a>Función de administrador de barreras de información

El rol de administración de cumplimiento de IB es el responsable de administrar las políticas de la barrera de información. Para obtener más información sobre este rol, consulte [permisos en el centro de cumplimiento de la & de seguridad de Office 365](https://docs.microsoft.com/office365/securitycompliance/permissions-in-the-security-and-compliance-center).

## <a name="when-are-information-barrier-policies-checked"></a>¿Cuándo se verifican las directivas de barrera de información?

Las directivas de barrera de información se comprueban cuando se producen los siguientes eventos de Teams:

- **Se agregan miembros a un equipo** siempre que agregue un usuario a un equipo, la Directiva del usuario debe evaluarse contra las directivas de la barrera de información de otros miembros del equipo. Después de que el usuario se haya agregado correctamente, el usuario puede realizar todas las funciones del equipo sin más comprobaciones. Si la Directiva del usuario impide que se agreguen al equipo, el usuario no se mostrará en la búsqueda.
- **Se solicita una nueva conversación** : cada vez que se solicita una nueva conversación entre dos o más usuarios, se evalúa la conversación para asegurarse de que no infrinja ninguna política de barrera de la información. Si la conversación infringe una directiva de barrera de información, la conversación no se inicia.
- **Un usuario ha recibido una invitación para unirse a una reunión** : cuando un usuario está invitado a unirse a una reunión, la Directiva del usuario se evalúa según las directivas de otros miembros del equipo y, si se produce una infracción, el usuario no podrá unirse a la reunión.
- **Una pantalla se comparte entre dos o más usuarios** , siempre que una pantalla se comparta entre dos o más usuarios, se debe evaluar el uso compartido de pantalla para asegurarse de que no infrinja las directivas de la barrera de información de otros usuarios. Si se infringe una directiva de barrera de información, no se permitirá el uso compartido de pantalla.
- **Un usuario realiza una llamada de teléfono (VoIP) en Teams** , siempre que un usuario inicie una llamada de voz a otro usuario o grupo de usuarios, la llamada se evalúa para asegurarse de que no infrinja las directivas de la barrera de información de otros miembros del equipo. Si hay alguna infracción, la llamada se bloquea.

## <a name="what-happens-to-existing-chat-threads-when-a-policy-is-changed"></a>¿Qué pasa con los subprocesos de chat existentes cuando se cambia una directiva?

Cuando el administrador de la Directiva de la barrera de información realiza cambios en una directiva o se activa un cambio de directiva debido a un cambio en el perfil de un usuario (por ejemplo, un cambio en el trabajo o un motivo similar), el servicio de evaluación de la Directiva de información de la barrera automáticamente busca los miembros para asegurarse de que los miembros del equipo no infrinjan las directivas.

Si hay una conversación u otra comunicación entre usuarios, se establece una nueva Directiva o se modifica una directiva existente, el servicio evalúa las comunicaciones existentes para asegurarse de que se permitan las comunicaciones. 

- **1:1 chat** : Si ya no se permite la comunicación entre los dos usuarios (si se aplica una directiva que bloquea la comunicación a uno o ambos usuarios), se bloquea la comunicación adicional y la conversación de chat se convertirá en solo lectura.
- **Conversación grupal** : Si ya no se permite la comunicación de un usuario al grupo (por ejemplo, si un usuario cambia de trabajo), el usuario, junto con el resto de los usuarios que infrinjan la Directiva, se puede quitar de la conversación grupal y la comunicación posterior con el grupo no se tienen. El usuario puede seguir viendo conversaciones antiguas (que serán de solo lectura), pero no podrá ver ni participar en ninguna conversación nueva con el grupo. Si la directiva nueva o modificada que evita la comunicación se aplica a más de un usuario, los usuarios afectados por la Directiva se pueden quitar de la conversación grupal. Aún puede ver conversaciones antiguas. 
- **Equipo** : todos los usuarios que se han quitado del grupo se quitan del equipo y no podrán ver ni participar en conversaciones nuevas o existentes.

## <a name="what-will-users-experience-if-another-user-is-blocked"></a>¿Qué experimentarán los usuarios si otro usuario está bloqueado?

En la actualidad, los usuarios experimentan lo siguiente si una directiva de barrera de información bloquea a otro usuario:

- **Pestaña personas** : un usuario puede ver algunos usuarios bloqueados en la pestaña **contactos** . El usuario puede seleccionar a los usuarios bloqueados.
- **Ficha actividad** : Si un usuario visita la pestaña **actividad** de un usuario bloqueado, no aparecerá ninguna publicación. (La ficha **actividad** muestra solo las publicaciones de canal y no habría canales comunes entre los dos usuarios).
- **** Organigramas: Si un usuario obtiene acceso a un organigrama en el que aparece un usuario bloqueado, el usuario verá el usuario bloqueado en el gráfico y podrá hacer clic en acciones en el gráfico, pero las acciones (como la llamada) no se realizarán.
- **Tarjeta de contactos** : Si un usuario participa en una conversación y posteriormente se bloquea, otros usuarios pueden seguir viendo la tarjeta contactos para el usuario bloqueado. Todas las acciones que aparecen en la tarjeta (como llamadas y chats) estarán disponibles, pero no se realizarán las acciones.
- **Contactos sugeridos** : en la lista de contactos sugeridos (la lista de contactos inicial que aparece para los nuevos usuarios), los usuarios pueden ver todos los contactos sugeridos (incluidos los usuarios bloqueados). Sin embargo, si un usuario hace clic en el nombre de un usuario bloqueado para abrir el panel de chats, el mensaje se bloqueará.
- **Contactos de chat** : un usuario puede ver usuarios bloqueados en la lista de contactos de chat.
- **Llamadas contactos** : un usuario puede ver los usuarios bloqueados en la lista de contactos y se mostrarán acciones como llamadas y mensajes, pero cuando el usuario intente llamar o enviar un mensaje al usuario bloqueado, la llamada o el mensaje no se enviará.
- **Migración de Skype a teams** : durante una migración de Skype empresarial a Teams, todos los usuarios, incluso los que están bloqueados por las directivas de la barrera de información, se migrarán a teams y se administrarán según se describe anteriormente.

Próximamente: los usuarios experimentarán lo siguiente si una directiva de barrera de información bloquea a otro usuario:

- **Pestaña personas** : un usuario no puede ver usuarios bloqueados en la pestaña **contactos** .
- **Ficha actividad** : Si un usuario visita la pestaña **actividad** de un usuario bloqueado, no aparecerá ninguna publicación. (La ficha **actividad** muestra solo las publicaciones de canal y no habría canales comunes entre los dos usuarios).
- **** Organigramas: Si un usuario accede a un organigrama en el que aparece un usuario bloqueado, dicho usuario no aparecerá en el organigrama y aparecerá un mensaje de error.
- **Tarjeta de contactos** : Si un usuario participa en una conversación y el usuario se bloquea posteriormente, otros usuarios verán un mensaje de error en lugar de la tarjeta de contactos cuando pasen el mouse sobre el nombre del usuario bloqueado. Las acciones que aparecen en la tarjeta (como llamadas y conversaciones) no estarán disponibles.
- **Contactos sugeridos** : los usuarios bloqueados no aparecen en la lista de contactos sugeridos (la lista de contactos inicial que aparece para los nuevos usuarios).
- **Contactos de chat** : un usuario no puede ver usuarios bloqueados en la lista de contactos de chat.
- **Llama a contactos** : un usuario puede ver usuarios bloqueados en la lista de contactos de llamadas, pero los usuarios bloqueados se identificarán y la única acción que el usuario puede realizar es eliminarlos.
- **Migración de Skype a teams** : durante una migración de Skype empresarial a Teams, todos los usuarios, incluso los que están bloqueados por las directivas de la barrera de información, se migrarán a teams y se administrarán según se describe anteriormente.

## <a name="required-licenses-and-permissions"></a>Licencias y permisos necesarios

Las barreras de información se están publicando y se incluyen en las suscripciones, como por ejemplo:

- Microsoft 365 E5
- Office 365 E5
- Cumplimiento avanzado de Office 365
- Cumplimiento de Microsoft 365 E5

Para obtener más información, incluidos planes y precios, consulte [soluciones de cumplimiento](https://products.office.com/business/security-and-compliance/compliance-solutions?rtc=1).

## <a name="more-information"></a>Más información

- Para obtener más información sobre las barreras de la información, consulte barreras de la [información](https://docs.microsoft.com/office365/securitycompliance/information-barriers).

- Para configurar las políticas de la barrera de información, consulte [definir políticas para las barreras de información](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies)

- Para editar o quitar directivas de la barrera de la información, consulte [Editar o quitar directivas](https://docs.microsoft.com/office365/securitycompliance/information-barriers-edit-segments-policies.md) de la barrera de información