---
title: Barreras de información en Microsoft Teams
author: chrfox
ms.author: chrfox
manager: laurawi
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
ms.reviewer: vikramju
f1.keywords:
- NOCSH
description: Este artículo explica qué son las barreras de información en Microsoft Teams y cómo pueden afectar a Teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 94e0117e1f0956d8e3e9ae8e6bafc7feabcdf237
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196464"
---
# <a name="information-barriers-in-microsoft-teams"></a>Barreras de información en Microsoft Teams

Las barreras de información (IB) son directivas que un administrador puede configurar para evitar que los individuos o grupos se comuniquen entre sí. Los IB son útiles si, por ejemplo, un departamento está controlando información que no se debe compartir con otros departamentos. Los IB también son útiles cuando es necesario aislar o impedir que un grupo se comunique con cualquier persona que no forme parte de ese grupo.

> [!NOTE]
> - Los grupos de barreras de información (IB) no se pueden crear entre inquilinos.
> - En la versión 1 no se admite el uso de bots, aplicaciones de Azure Active Directory (Azure AD) y algunas API para agregar usuarios.
> - Los canales privados cumplen las directivas IB que configure.
> - Nuevo: Para obtener información sobre el soporte técnico para los sitios de SharePoint que están conectados a Teams, vea [Segmentos asociados con los sitios de Microsoft Teams.](https://docs.microsoft.com/sharepoint/information-barriers#segments-associated-with-microsoft-teams-sites)

Las directivas DEL IB también impiden las búsquedas y el descubrimiento. Si intenta comunicarse con alguien con quien no debe comunicarse, no encontrará ese usuario en el Selector de personas.

## <a name="background"></a>Información general

El controlador principal para los IB proviene de la industria de servicios financieros. La Autoridad Reguladora de la Industria Financiera[(FINRA)]( https://www.finra.org)revisa los IB y los conflictos de interés dentro de las empresas miembros y proporciona orientación sobre la administración de este tipo de conflictos (FINRA 2241, Aviso reglamentario de investigación de deuda [15-31).](https://www.finra.org/sites/default/files/Regulatory-Notice-15-31_0.pdf)


Sin embargo, desde la introducción a los IB, muchas otras áreas las han encontrado útiles. Otros escenarios comunes son:

- Educación: Los alumnos de una escuela no pueden buscar información de contacto para los alumnos de otras escuelas.

- Legal: Mantener la confidencialidad de los datos que se obtienen por la red de un cliente y evitar que un único cliente pueda acceder a ellos por una sola empresa que representa a un cliente diferente.

- Administración pública: el acceso y el control de la información están limitados a todos los departamentos y grupos.

- Servicios profesionales: un grupo de personas de una empresa solo puede chatear con un cliente o con un cliente específico a través del acceso de invitado durante una interacción con el cliente.

Por ejemplo, Enrico pertenece al segmento Bancario y Pradeep pertenece al segmento de asesores financieros. Enrico y Pradeep no pueden comunicarse entre sí porque la directiva IB de la organización bloquea la comunicación y la colaboración entre estos dos segmentos. Sin embargo, Enrico y Pradeep pueden comunicarse con Lee en RR. UU.

![Ejemplo que muestra barreras de información que impiden la comunicación entre segmentos](media/information-barriers-example.png)

## <a name="when-to-use-information-barriers"></a>Cuándo usar barreras de información

Es posible que desee usar los IB en situaciones como esta:

- Es necesario impedir que un equipo comunique o comparta datos con un equipo específico.
- Un equipo no debe comunicarse ni compartir datos con personas fuera del equipo.

El Servicio de evaluación de la política de barreras de la información determina si una comunicación cumple con las directivas IB.

## <a name="managing-information-barrier-policies"></a>Administrar directivas de barreras de información

Las directivas IB se administran en el Centro de cumplimiento de Microsoft 365 (SCC) con cmdlets de PowerShell. Para obtener más información, [vea Definir directivas para las barreras de información.](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies)

> [!IMPORTANT]
> Antes de configurar o definir directivas, debe habilitar la búsqueda en el directorio de ámbito en Microsoft Teams. Espere al menos unas horas después de habilitar la búsqueda en el directorio con ámbito antes de configurar o definir directivas para las barreras de información. Para obtener más información, vea [Definir directivas de barreras de información.](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies#prerequisites)

## <a name="information-barriers-administrator-role"></a>Rol de administrador de barreras de información

El rol de Administración del cumplimiento de la IB es el responsable de administrar las directivas del IB. Para obtener más información sobre este rol, vea [Permisos del Centro de cumplimiento de Microsoft 365.](https://docs.microsoft.com/office365/securitycompliance/permissions-in-the-security-and-compliance-center)

## <a name="information-barrier-triggers"></a>Desencadenadores de la barrera de información

Las directivas IB se activan cuando se llevan a cabo los siguientes eventos de Teams:

- **Se agregan miembros a** un equipo: siempre que agregue un usuario a un equipo, la directiva del usuario debe evaluarse según las directivas del IB de otros miembros del equipo. Una vez que el usuario se haya agregado correctamente, podrá realizar todas las funciones del equipo sin realizar más comprobaciones. Si la directiva del usuario bloquea su agregó al equipo, el usuario no se mostrará en la búsqueda.

    ![Captura de pantalla de la búsqueda de un nuevo miembro para agregarlo a un equipo y no encontrar ninguna coincidencia](media/information-barriers-add-members.png)

- Se solicita un **nuevo chat:** cada vez que un usuario solicita un nuevo chat con uno o más usuarios, el chat se evalúa para asegurarse de que no infringe ninguna política del IB. Si la conversación infringe una directiva de la IB, la conversación no se inicia.

    Este es un ejemplo de un chat 1:1.

    > [!div class="mx-imgBorder"]
    > ![Captura de pantalla que muestra la comunicación bloqueada en un chat 1:1](media/information-barriers-one-one-chat.png)

    Este es un ejemplo de un chat grupal.

    > [!div class="mx-imgBorder"]
    > ![Captura de pantalla que muestra el chat grupal](media/information-barriers-group-chat.png)

- Se invita a un usuario a unirse a una reunión: cuando se invita **a** un usuario a unirse a una reunión, la directiva del IB que se aplica al usuario se evalúa según las directivas del IB que se aplican a los demás miembros del equipo. Si hay una infracción, el usuario no podrá unirse a la reunión.

    ![Captura de pantalla que muestra que el usuario está bloqueado de una reunión](media/information-barriers-meeting.png)

- **Se** comparte una pantalla entre dos o más usuarios: cuando un usuario comparte una pantalla con otros usuarios, es necesario evaluar el uso compartido para asegurarse de que no infringe las directivas DEL SISTEMA IB de otros usuarios. Si se infringe una directiva IB, no se permitirá el uso compartido de pantalla. 
 
    Este es un ejemplo de uso compartido de pantalla antes de aplicar la directiva. 

    > [!div class="mx-imgBorder"]
    > ![Captura de pantalla que muestra un chat de usuario](media/ib-before-screen-share-policy.png)

    Este es un ejemplo de uso compartido de pantalla después de aplicar la directiva. Los iconos de pantalla compartido e llamada no están visibles.

    > [!div class="mx-imgBorder"]
    > ![Captura de pantalla que muestra el carácter de usuario con configuración bloqueada](media/ib-after-screen-share-policy.png)

- Un usuario realiza una llamada telefónica en **Teams:** siempre que un usuario inicia una llamada de voz (a través de VOIP) a otro usuario o grupo de usuarios, la llamada se evalúa para asegurarse de que no infringe las directivas IB de otros miembros del equipo. Si se trata de alguna infracción, la llamada de voz se bloquea.

- **Los invitados en Teams:** las directivas de la IB también se aplican a los invitados en Teams. Si los invitados deben poder ser reconocibles en la lista global de direcciones de su organización, vea Administrar el acceso de invitados en grupos de [Microsoft 365.](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-guest-access-in-groups) Una vez que los invitados se puedan detectar, puede [definir directivas IB.](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies)

## <a name="how-policy-changes-impact-existing-chats"></a>Cómo afectan los cambios de directiva a los chats existentes

Cuando el administrador de la directiva IB realiza cambios en una directiva, o cuando se activa un cambio de directiva debido a un cambio en el perfil de un usuario (por ejemplo, para un cambio de trabajo), el Servicio de evaluación de directivas de barrera de información busca automáticamente a los miembros para asegurarse de que su pertenencia al equipo no infringe ninguna directiva.

Si hay un chat existente u otra comunicación entre los usuarios, y se establece una nueva directiva o se cambia una directiva existente, el servicio evalúa las comunicaciones existentes para asegurarse de que las comunicaciones pueden seguir teniendo lugar. 

- **Chat 1:1:** si ya no se permite la comunicación entre dos usuarios (debido a la aplicación a uno o a ambos usuarios de una directiva que bloquea la comunicación), se bloquea la comunicación posterior. Sus conversaciones de chat existentes se convierten en de solo lectura. 

    Este es un ejemplo que muestra que el chat está visible.

    > [!div class="mx-imgBorder"]
    > ![Captura de pantalla que muestra que el chat de usuario está disponible](media/ib-before-1-1chat-policy.png)

    Este es un ejemplo que muestra que el chat está deshabilitado.

    > [!div class="mx-imgBorder"]
    > ![Captura de pantalla que muestra que el chat del usuario está deshabilitado](media/ib-after-1-1chat-policy.png)

- **Chat grupal:** si ya no se permite la comunicación de un usuario a un grupo (por ejemplo, porque un usuario cambió los trabajos), el usuario (junto con los demás usuarios cuya participación infringe la directiva) puede quitarse del chat grupal y no se permitirá una mayor comunicación con el grupo. El usuario todavía puede ver conversaciones antiguas, pero no podrá ver ni participar en nuevas conversaciones con el grupo. Si la directiva nueva o cambiada que impide la comunicación se aplica a más de un usuario, los usuarios afectados por la directiva pueden quitarse del chat de grupo. Seguirán teniendo conversaciones antiguas.

  En este ejemplo, Enrico se ha movido a otro departamento de la organización y se quita del chat grupal.

  ![Captura de pantalla de un chat grupal del que se ha quitado un usuario](media/information-barriers-user-changes-job.png)

  Enrico ya no puede enviar mensajes al chat grupal.

  ![Captura de pantalla que indica que no se pueden enviar mensajes a un chat grupal porque el usuario se ha quitado del grupo](media/information-barriers-user-changes-job-2.png)

- **Equipo:** todos los usuarios que se han quitado del grupo se quitan del equipo y no podrán ver ni participar en conversaciones existentes o nuevas.

## <a name="scenario-a-user-in-an-existing-chat-becomes-blocked"></a>Escenario: Un usuario de un chat existente queda bloqueado

Actualmente, los usuarios experimentan los siguientes escenarios si una directiva IB bloquea a otro usuario:

- **Pestaña Personas:** un usuario no puede ver los usuarios bloqueados en la **pestaña** Personas.

- **Selector de personas:** los usuarios bloqueados no estarán visibles en el Selector de personas.

    ![Captura de pantalla de Teams que alerta al usuario de que la directiva impide que se muestre la información de otro usuario](media/information-barriers-people-picker.png)
    
- **Pestaña Actividad:** si un usuario visita la **pestaña** Actividad de un usuario bloqueado, no aparecerán publicaciones. (La **pestaña Actividad** solo muestra las publicaciones de los canales y no hay canales comunes entre los dos usuarios).

    Este es un ejemplo de la vista de la pestaña actividad que está bloqueada.

    > [!div class="mx-imgBorder"]
    > ![Captura de pantalla que muestra la pestaña actividad que está bloqueada](media/ib-after-activity-tab-policy.png)


- **Organigramas:** si un usuario tiene acceso a un organigrama en el que aparece un usuario bloqueado, el usuario bloqueado no aparecerá en el organigrama. En su lugar, aparecerá un mensaje de error.

- **Tarjeta personas:** si un usuario participa en una conversación y este se bloquea posteriormente, otros usuarios verán un mensaje de error en lugar de la tarjeta de personas cuando pasen el cursor sobre el nombre del usuario bloqueado. Las acciones enumeradas en la tarjeta (como llamadas y chats) no estarán disponibles.

- **Contactos sugeridos:** los usuarios bloqueados no aparecen en la lista de contactos sugeridos (la lista de contactos inicial que aparece para los nuevos usuarios).

- **Contactos de chat:** un usuario puede ver los usuarios bloqueados en la lista de contactos de chats, pero se identificarán los usuarios bloqueados. La única acción que el usuario puede realizar en los usuarios bloqueados es eliminarlos. El usuario también puede hacer clic en él para ver su conversación pasada.

- **Llamadas a contactos:** un usuario puede ver los usuarios bloqueados en la lista de contactos de llamadas, pero se identificarán los usuarios bloqueados. La única acción que el usuario puede realizar en el bloque de usuarios es eliminarlos.

    Este es un ejemplo de un usuario bloqueado en la lista de contactos de llamadas.

    > [!div class="mx-imgBorder"]
    > ![Captura de pantalla que muestra el chat de usuario](media/ib-before-chat-contacts-policy.png)

    Este es un ejemplo del chat que se ha deshabilitado para un usuario en la lista de contenido de llamadas.

    > [!div class="mx-imgBorder"]
    > ![Captura de pantalla que muestra que el usuario está bloqueado del chat](media/ib-after-chat-contacts-policy.png)

- **Migración de Skype** a Teams: durante una migración de Skype Empresarial a Teams, todos los usuarios, incluso aquellos usuarios bloqueados por las directivas IB, se migrarán a Teams. Esos usuarios se administran como se describió anteriormente.

## <a name="teams-policies-and-sharepoint-sites"></a>Directivas de Teams y sitios de SharePoint

Cuando se crea un equipo, se aprovisiona un sitio de SharePoint y se asocia a Microsoft Teams para la experiencia de archivos. Las directivas DEL IB no se respetan en este sitio de SharePoint y los archivos de forma predeterminada. Para habilitar las directivas IB, el administrador ya ha rellenado un formulario solicitando que se habiliten las directivas del IBI en SharePoint y OneDrive (consulte la sección *Requisitos previos* en Barreras de [información).](https://docs.microsoft.com/sharepoint/information-barriers#prerequisites) Si la directiva del IB está activada en SharePoint y OneDrive, las directivas del IB funcionarán en los sitios de SharePoint aprovisionados cuando se cree un equipo con Microsoft Teams.

Ejemplo de directivas IB en el sitio de **SharePoint** de un equipo: En Contoso Bank Corporation, el usuario 'Sesha@contosobank.onmicrosoft.com' pertenece al segmento De banca de inversiones y el usuario 'Nikita@contosobank.onmicrosoft.com' pertenece al segmento de asesoramiento. La directiva IB de la organización bloquea la comunicación y la colaboración entre estos dos segmentos.
Cuando el usuario Sesha crea un equipo para el segmento de banca de inversiones, el equipo y el sitio de SharePoint que lo copia de seguridad serán accesibles solo para los usuarios de Banca de inversiones. El usuario Nikita no puede acceder a ese sitio aunque tenga el vínculo del sitio.

Para obtener más información, [vea Usar barreras de información con SharePoint.](https://docs.microsoft.com/sharepoint/information-barriers#segments-associated-with-microsoft-teams-sites)

## <a name="required-licenses-and-permissions"></a>Licencias y permisos necesarios

Para obtener más información sobre licencias y permisos, incluidos los planes y los precios, consulte la guía de licencias de [Microsoft 365](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)para la seguridad y & cumplimiento.

## <a name="known-issues"></a>Problemas conocidos
- Los usuarios no pueden unirse a reuniones **ad-hoc:** si se habilitan las directivas IB, los usuarios no podrán unirse a las reuniones si el tamaño de la lista de reuniones es superior a los límites de asistencia a [reuniones.](limits-specifications-teams.md) La causa principal es que los controles ib dependen de si los usuarios se pueden agregar a una lista de chat de la reunión y solo cuando se pueden agregar a la lista pueden unirse a la reunión. Un usuario que se une a una reunión una vez lo agrega a la lista; por lo tanto, para reuniones periódicas, la lista puede llenarse rápidamente. Una vez que la lista de chat alcanza [los](limits-specifications-teams.md)límites de asistencia a la reunión, no se permite agregar usuarios adicionales a la reunión. Si IB está habilitado para el inquilino y la lista de chat está llena para una reunión, los nuevos usuarios (aquellos que aún no están en la lista) no podrán unirse a la reunión. Sin embargo, si IB no está habilitado para el inquilino y la lista de chat de la reunión está llena, se permite a los nuevos usuarios (aquellos que aún no están en la lista) unirse a la reunión, aunque no verán la opción de chat en la reunión. Una solución a corto plazo es quitar miembros inactivos de la lista del chat de la reunión para hacer espacio a los nuevos usuarios. Sin embargo, aumentaremos el tamaño de las listas de chat de la reunión más adelante.

- **Los usuarios no pueden** unirse a las reuniones del canal: si se habilitan las directivas IB, los usuarios no podrán unirse a las reuniones del canal si no son miembros del equipo. La causa principal es que los controles ib dependen de si los usuarios se pueden agregar a una lista de chat de la reunión y solo cuando se pueden agregar a la lista pueden unirse a la reunión. La conversación de chat de una reunión de canal solo está disponible para los miembros del equipo o del canal y los usuarios que no son miembros no pueden ver ni tener acceso a la conversación de chat. Si IB está habilitado para el inquilino y un miembro que no es del equipo intenta unirse a una reunión del canal, ese usuario no puede unirse a la reunión. Sin embargo,  si IB no está habilitado para el inquilino y un miembro que no es del equipo intenta unirse a una reunión del canal, el usuario puede unirse a la reunión, pero no verá la opción de chat en la reunión.

## <a name="more-information"></a>Más información

- Para obtener más información sobre los IB, vea [Barreras de información.](https://docs.microsoft.com/office365/securitycompliance/information-barriers)

- Para configurar directivas IB, vea [Definir directivas para las barreras de información.](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies)

- Para editar o quitar directivas DE LAC, vea [Editar (o quitar) las directivas de barreras de información.](https://docs.microsoft.com/microsoft-365/compliance/information-barriers-edit-segments-policies)

## <a name="availability"></a>Disponibilidad
- La característica está disponible en la nube pública; en enero de 2021, se lanzó Information Barriers en la nube GCC.
- La característica aún no está disponible en las nubes GCCH y DOD.
