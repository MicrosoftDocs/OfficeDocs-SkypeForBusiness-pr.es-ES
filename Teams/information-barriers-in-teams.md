---
title: Barreras de información en la versión preliminar de Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 05/14/2019
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
search.appverid: MET150
ms.reviewer: vikramju
description: Obtenga información sobre las barreras de información y cómo afectan a los equipos.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5cf9891e44df3e656255da90dc495d8f0bda8c72
ms.sourcegitcommit: 9a99be1365df439f9443f31240aa5311782458df
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2019
ms.locfileid: "33993924"
---
# <a name="information-barriers-in-microsoft-teams-preview"></a>Barreras de información en la versión preliminar de Microsoft Teams

> [!INCLUDE [Preview feature](includes/preview-feature.md)]

Las barreras de información son las directivas que un administrador puede configurar para evitar que los individuos o grupos comunicarse entre sí. Esto es útil si, por ejemplo, un departamento encarga de información que no debe compartir con otros departamentos o un grupo debe ser no se les permita comunicarse con cualquiera fuera de los contactos.

> [!NOTE]
> - No se puede crear grupos de barrera de información a través de los inquilinos.
> - No se admite el uso de bots para agregar los usuarios en la versión 1.
> - Versión de las barreras de información 1 no incluye compatibilidad con SharePoint y OneDrive para la empresa. Estamos trabajando acerca de cómo habilitar la característica en SharePoint y se va a comunicar una vez está disponible.

Directivas de barrera de información también evitar que las búsquedas y detección. Esto significa que si se intenta comunicarse con alguien que no se comunica con, no encontrará que el usuario en el selector de personas.

## <a name="background"></a>Información general

El controlador principal para las barreras de información proviene de la industria de servicios financieros. La autoridad de las normativas del sector financiero ([FINRA]( http://www.finra.org/)) revisa las barreras de información y los conflictos de intereses dentro de las empresas asociadas y se proporcionan instrucciones sobre cómo administrar este tipo de conflictos (FINRA 2241, [Obligaciones de investigación legales aviso 15 31](http://www.finra.org/sites/default/files/Regulatory-Notice-15-31_0.pdf).  

## <a name="when-should-i-use-information-barriers"></a>¿Cuándo debo usar las barreras de información?

Es posible que desee utilizar las barreras de información en situaciones como las siguientes:

- Un equipo debe ser no se les permita comunicarse o uso compartido de datos con una determinada otro equipo.
- Un equipo no debe comunicarse o compartir datos con cualquier persona fuera del equipo.

El servicio de evaluación de directiva de información barrera determina si una comunicación cumple con las directivas de barrera de información. 

## <a name="managing-information-barrier-policies"></a>Administración de directivas de la barrera de información

Las directivas de barrera de información se administran con seguridad & los cmdlets de PowerShell de centro de cumplimiento (SCC). Para obtener más información acerca del uso de estos cmdlets, [Regístrese aquí](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR1UzUQTEgHVPtD9W5uih2OlUMEwwUzhJSktIMUw2SDJJOE5FT1lTVzVTSS4u).

> [!IMPORTANT]
> Antes de configurar o definir directivas, **debe habilitar la búsqueda en el directorio con ámbito en los equipos de Microsoft**. Espere al menos 24 horas después de habilitar la búsqueda en el directorio con ámbito antes de configurar o definir directivas para las barreras de información.

## <a name="information-barriers-administrator-role"></a>Rol de administrador de las barreras de información

La función de administrador de las barreras de información es responsable de administrar las directivas de barrera de información. Para obtener más información acerca de esta función y participar en la vista previa, [Regístrese aquí](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR1UzUQTEgHVPtD9W5uih2OlUMEwwUzhJSktIMUw2SDJJOE5FT1lTVzVTSS4u).

## <a name="when-are-information-barrier-policies-checked"></a>¿Cuándo se deben comprobar las directivas de barrera de información?

Directivas de barrera de información se comprueban cuando los siguientes eventos de los equipos tienen lugar:

- Se deben evaluar **los miembros se agregan a un equipo** - siempre que se agrega un usuario a un equipo, la directiva del usuario con las directivas de la barrera de información de otros integrantes del grupo. Después de que el usuario se haya agregado correctamente, el usuario puede realizar todas las funciones en el equipo sin más comprobaciones. Si la directiva del usuario bloquea ellos desde que se agrega al equipo, el usuario no se mostrará en la búsqueda.
- **Se solicita un nuevo chat** - cada vez que se solicita un nuevo chat entre dos o más usuarios, se evalúa el chat para asegurarse de que no se infringen las directivas de la barrera de información. Si la conversación infringe una directiva de barrera de información, a continuación, no se inició la conversación y aparece un mensaje de error.
- **Un usuario recibe una invitación para unirse a una reunión** - cuando un usuario recibe una invitación para unirse a una reunión, se evalúa la directiva del usuario con las directivas de otros miembros del equipo y, si hay una infracción, el usuario no podrán unirse a la reunión y verá un mensaje de error.
- **Que una pantalla se comparte entre dos o más usuarios** - cualquier momento una pantalla se comparte entre dos o más usuarios, se debe evaluar el recurso compartido de la pantalla para asegurarse de que lo no infringe las directivas de la barrera de información de otros usuarios. Si se infringe una directiva de barrera de información, no se pueden compartir de la pantalla y aparecerá un mensaje de error.
- **Un usuario realiza una llamada de teléfono (IP VOIP) en los equipos** - cualquier momento se inicia una llamada de voz por un usuario a otro usuario o grupo de usuarios, la llamada se evalúa para asegurarse de que lo no infringe las directivas de barrera de información de los miembros del equipo oher. Si hay cualquier infracción, se bloquea la llamada de voz.

## <a name="what-happens-to-existing-chat-threads-when-a-policy-is-changed"></a>¿Lo que ocurre con los subprocesos de chat existentes cuando se modifica una directiva?

Cuando la administración de directiva de información barrera realiza cambios en la directiva o un cambio de directiva se inicia en vigor debido a cambio de trabajo de un usuario o un motivo similar, el servicio de evaluación de directiva de información barrera automáticamente busca los miembros para asegurarse de que miembros del equipo no infringe ninguna directiva. 

Si hay una conversación existente o en otros tipos de comunicación entre los usuarios y se establece una nueva directiva o se cambia una directiva existente, el servicio se evalúa como las comunicaciones existentes para asegurarse de que no se "dañados" (ya no permitido): 

- **chat de 1:1** - si ya no se permite la comunicación entre los dos usuarios (si se aplica una directiva de bloqueo de comunicación a los usuarios de uno o ambos), aún más se bloquea la comunicación y la conversación de chat se convertirán en solo lectura.
- **Conversaciones en grupo** - si ya no se permite la comunicación de un usuario al grupo (por ejemplo, si un usuario cambia los trabajos), puede quitar el usuario junto con los demás usuarios que infringir la directiva de conversaciones en grupo y no será más comunicación con el grupo permitido. El usuario todavía puede ver conversaciones antiguas (que serán de solo lectura), pero no podrá ver o participar en las conversaciones con el grupo nuevo. Si la directiva de nueva o modificada impidiendo la comunicación se aplica a más de un usuario, los usuarios que se ven afectados por la directiva pueden quitarse de conversaciones en grupo. Pueden ver las conversaciones anteriores. 
- **Equipo** - los usuarios que se han quitado del grupo se quitan del equipo de y no podrán ver o participar en conversaciones de nuevas o existentes.

## <a name="required-licenses-and-permissions"></a>Permisos y licencias necesarias

Actualmente, las características de la barrera de información se encuentran en versión preliminar pública. Cuando estas características están disponibles por lo general, que debe incluirse en suscripciones, tales como:

- Microsoft 365 E5
- Office 365 E5
- Office 365 avanzada de cumplimiento
- Cumplimiento de normas de Microsoft 365 E5

Para obtener más información, incluidos los planes y precios, vea [Las soluciones de cumplimiento de normas](https://products.office.com/business/security-and-compliance/compliance-solutions?rtc=1).
