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
description: En este artículo se explican qué son las barreras de información en Microsoft Teams y cómo pueden afectar a Teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 87e282673d1fabec5b751b0a3722515585e5e404
ms.sourcegitcommit: 360c78c66386fe00afe535681f51254eda886edf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/17/2021
ms.locfileid: "50837017"
---
# <a name="information-barriers-in-microsoft-teams"></a>Barreras de información en Microsoft Teams

Las barreras de información (IB) son directivas que un administrador puede configurar para evitar que individuos o grupos se comuniquen entre sí. Los IB son útiles si, por ejemplo, un departamento administra información que no debería compartirse con otros departamentos. Los IB también son útiles cuando es necesario aislar un grupo o impedir que se comunique con cualquier persona que no sea de ese grupo.

> [!NOTE]
> - Los grupos de barreras de información (IB) no se pueden crear entre inquilinos.
> - La versión 1 no admite el uso de bots, aplicaciones de Azure Active Directory (Azure AD) y algunas API para agregar usuarios.
> - Los canales privados son compatibles con las directivas del IB que configure.
> - Nuevo: Para obtener información sobre la compatibilidad con barreras para sitios de SharePoint conectados a Teams, vea Segmentos [asociados a sitios de Microsoft Teams.](https://docs.microsoft.com/sharepoint/information-barriers#segments-associated-with-microsoft-teams-sites)

Las directivas del IB también impiden las búsquedas y la detección. Si intenta comunicarse con alguien con quien no debería comunicarse, no encontrará ese usuario en el selector de personas.

## <a name="background"></a>Información general

El controlador principal de los IB proviene del sector de servicios financieros. La Autoridad reguladora del sector financiero[(FINRA)]( https://www.finra.org)revisa los IB y los conflictos de interés dentro de las empresas miembros y proporciona instrucciones sobre la administración de dichos conflictos (FINRA 2241, Aviso normativo de investigación de deuda [15-31.](https://www.finra.org/sites/default/files/Regulatory-Notice-15-31_0.pdf)


Sin embargo, desde la introducción de los IB, muchas otras áreas han encontrado que son útiles. Otros escenarios comunes incluyen:

- Educación: Los alumnos de una escuela no pueden buscar detalles de contacto para los alumnos de otras escuelas.

- Legal: Mantener la confidencialidad de los datos obtenidos por el abogado de un cliente e impedir que un abogado de la misma empresa que representa a un cliente diferente pueda acceder a ellos.

- Gobierno: el acceso a la información y el control están limitados entre departamentos y grupos.

- Servicios profesionales: un grupo de personas de una empresa solo puede chatear con un cliente o con un cliente específico a través del acceso de invitado durante una interacción con el cliente.

Por ejemplo, Enrico pertenece al segmento bancario y Pradeep pertenece al segmento asesor financiero. Enrico y Pradeep no pueden comunicarse entre sí porque la directiva del IB de la organización bloquea la comunicación y la colaboración entre estos dos segmentos. Sin embargo, Enrico y Pradeep pueden comunicarse con Lee en RECURSOS HUMANOS.

![Ejemplo que muestra barreras de información que impiden la comunicación entre segmentos](media/information-barriers-example.png)

## <a name="when-to-use-information-barriers"></a>Cuándo usar barreras de información

Es posible que desee usar los IB en situaciones como estas:

- Se debe impedir que un equipo comunique o comparta datos con un equipo específico.
- Un equipo no debe comunicarse ni compartir datos con nadie fuera del equipo.

El servicio de evaluación de directivas de barrera de información determina si una comunicación cumple con las directivas del IB.

## <a name="managing-information-barrier-policies"></a>Administrar directivas de barreras de información

Las directivas del IB se administran en el Centro de cumplimiento de Microsoft 365 (SCC) con cmdlets de PowerShell. Para obtener más información, vea [Definir directivas para barreras de información.](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies)

> [!IMPORTANT]
> Antes de configurar o definir directivas, debe habilitar la búsqueda de directorios con ámbito en Microsoft Teams. Espere al menos unas horas después de habilitar la búsqueda de directorios de ámbito antes de configurar o definir directivas para barreras de información. Para obtener más información, vea [Definir directivas de barreras de información.](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies#prerequisites)

## <a name="information-barriers-administrator-role"></a>Rol de administrador de barreras de información

El rol de administración de cumplimiento del IB es responsable de administrar las directivas del IB. Para obtener más información sobre este rol, vea Permisos en el Centro de cumplimiento de [Microsoft 365.](https://docs.microsoft.com/office365/securitycompliance/permissions-in-the-security-and-compliance-center)

## <a name="information-barrier-triggers"></a>Desencadenadores de barrera de información

Las directivas del IB se activan cuando se llevan a cabo los siguientes eventos de Teams:

- **Los miembros se agregan a** un equipo: siempre que agregue un usuario a un equipo, la directiva del usuario debe evaluarse con las directivas del IB de otros miembros del equipo. Después de agregar correctamente al usuario, el usuario puede realizar todas las funciones del equipo sin más comprobaciones. Si la directiva del usuario impide que se le agregó al equipo, el usuario no se mostrará en la búsqueda.

    ![Captura de pantalla de búsqueda de un nuevo miembro para agregar a un equipo y no encontrar coincidencias](media/information-barriers-add-members.png)

- Se solicita un **nuevo chat:** cada vez que un usuario solicita un nuevo chat con uno o varios usuarios, el chat se evalúa para asegurarse de que no infringe ninguna política del IB. Si la conversación infringe una directiva del IB, la conversación no se inicia.

    Este es un ejemplo de un chat 1:1.

    > [!div class="mx-imgBorder"]
    > ![Captura de pantalla que muestra la comunicación bloqueada en el chat 1:1](media/information-barriers-one-one-chat.png)

    Este es un ejemplo de un chat grupal.

    > [!div class="mx-imgBorder"]
    > ![Captura de pantalla que muestra el chat grupal](media/information-barriers-group-chat.png)

- Se invita a un usuario a unirse **a** una reunión: cuando se invita a un usuario a unirse a una reunión, la directiva del IB que se aplica al usuario se evalúa con las directivas del IB que se aplican a los demás miembros del equipo. Si hay una infracción, el usuario no podrá unirse a la reunión.

    ![Captura de pantalla que muestra el usuario bloqueado de la reunión](media/information-barriers-meeting.png)

- **Una pantalla** se comparte entre dos o más usuarios: cuando un usuario comparte una pantalla con otros usuarios, el uso compartido debe evaluarse para asegurarse de que no infringe las directivas del IB de otros usuarios. Si se infringe una directiva del IB, no se permitirá el uso compartido de pantalla. 
 
    Este es un ejemplo de uso compartido de pantalla antes de aplicar la directiva. 

    > [!div class="mx-imgBorder"]
    > ![Captura de pantalla que muestra un chat de usuario](media/ib-before-screen-share-policy.png)

    Este es un ejemplo de uso compartido de pantalla después de aplicar la directiva. Los iconos de pantalla y de llamada no son visibles.

    > [!div class="mx-imgBorder"]
    > ![Captura de pantalla que muestra el carácter de usuario con la configuración bloqueada](media/ib-after-screen-share-policy.png)

- Un usuario realiza una llamada de teléfono en **Teams:** siempre que un usuario inicia una llamada de voz (a través de VOIP) a otro usuario o grupo de usuarios, la llamada se evalúa para asegurarse de que no infringe las directivas del IB de otros miembros del equipo. Si hay alguna infracción, la llamada de voz está bloqueada.

- **Los invitados de Teams:** las directivas del IB también se aplican a los invitados de Teams. Si los invitados necesitan ser reconocibles en la lista global de direcciones de su organización, vea Administrar el acceso de invitado [en Grupos de Microsoft 365.](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-guest-access-in-groups) Una vez que los invitados se puedan descubrir, puede [definir las directivas del IB.](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies)

## <a name="how-policy-changes-impact-existing-chats"></a>Cómo afectan los cambios de directiva a los chats existentes

Cuando el administrador de directivas del IB realiza cambios en una directiva o cuando se activa un cambio de directiva debido a un cambio en el perfil de un usuario (por ejemplo, para un cambio de trabajo), el Servicio de evaluación de directivas de barrera de información busca automáticamente a los miembros para asegurarse de que su pertenencia al equipo no infringe ninguna directiva.

Si hay un chat existente u otra comunicación entre los usuarios, y se establece una nueva directiva o se cambia una directiva existente, el servicio evalúa las comunicaciones existentes para asegurarse de que las comunicaciones siguen estando permitidas. 

- **Chat 1:1:** si ya no se permite la comunicación entre dos usuarios (debido a la aplicación a uno o ambos usuarios de una directiva que bloquea la comunicación), se bloquea la comunicación adicional. Sus conversaciones de chat existentes se convierten en de solo lectura. 

    Este es un ejemplo que muestra que el chat está visible.

    > [!div class="mx-imgBorder"]
    > ![Captura de pantalla que muestra que el chat de usuario está disponible](media/ib-before-1-1chat-policy.png)

    Este es un ejemplo que muestra que el chat está deshabilitado.

    > [!div class="mx-imgBorder"]
    > ![Captura de pantalla que muestra que el chat de usuario está deshabilitado](media/ib-after-1-1chat-policy.png)

- Chat **grupal:** si ya no se permite la comunicación de un usuario a un grupo (por ejemplo, porque un usuario cambió los trabajos), el usuario, junto con los demás usuarios cuya participación infringe la directiva, puede quitarse del chat grupal y no se permitirá una comunicación adicional con el grupo. El usuario todavía puede ver conversaciones antiguas, pero no podrá ver ni participar en nuevas conversaciones con el grupo. Si la directiva nueva o modificada que impide la comunicación se aplica a más de un usuario, es posible que los usuarios afectados por la directiva se quiten del chat grupal. Todavía pueden ver conversaciones antiguas.

  En este ejemplo, Enrico se mueve a otro departamento de la organización y se quita del chat grupal.

  ![Captura de pantalla de un chat grupal del que se ha quitado un usuario](media/information-barriers-user-changes-job.png)

  Enrico ya no puede enviar mensajes al chat grupal.

  ![Captura de pantalla de no poder enviar mensajes al chat grupal porque el usuario se quitó del grupo](media/information-barriers-user-changes-job-2.png)

- **Equipo:** todos los usuarios que se han quitado del grupo se quitan del equipo y no podrán ver ni participar en conversaciones existentes o nuevas.

## <a name="scenario-a-user-in-an-existing-chat-becomes-blocked"></a>Escenario: Un usuario de un chat existente se bloquea

Actualmente, los usuarios experimentan los siguientes escenarios si una directiva del IB bloquea a otro usuario:

- **Pestaña Personas:** un usuario no puede ver usuarios bloqueados en la **pestaña** Personas.

- **Selector de personas:** los usuarios bloqueados no estarán visibles en el selector de personas.

    ![Captura de pantalla de Teams que alerta al usuario de que la directiva impide mostrar la información de otro usuario](media/information-barriers-people-picker.png)
    
- **Pestaña Actividad:** si un usuario visita **la** pestaña Actividad de un usuario bloqueado, no aparecerá ninguna publicación. (La **pestaña Actividad** solo muestra publicaciones de canal y no habría canales comunes entre los dos usuarios).

    Este es un ejemplo de la vista de pestaña actividad que está bloqueada.

    > [!div class="mx-imgBorder"]
    > ![Captura de pantalla que muestra la pestaña actividad que está bloqueada](media/ib-after-activity-tab-policy.png)


- **Organigramas:** si un usuario accede a un organigrama en el que aparece un usuario bloqueado, el usuario bloqueado no aparecerá en el organigrama. En su lugar, aparecerá un mensaje de error.

- **Tarjeta Personas:** si un usuario participa en una conversación y el usuario se bloquea más tarde, otros usuarios verán un mensaje de error en lugar de la tarjeta de personas cuando pase el puntero sobre el nombre del usuario bloqueado. Las acciones enumeradas en la tarjeta (como llamadas y chats) no estarán disponibles.

- **Contactos sugeridos:** los usuarios bloqueados no aparecen en la lista de contactos sugeridos (la lista de contactos inicial que aparece para los nuevos usuarios).

- **Contactos de chat:** un usuario puede ver usuarios bloqueados en la lista de contactos de chats, pero los usuarios bloqueados se identificarán. La única acción que el usuario puede realizar en los usuarios bloqueados es eliminarlos. El usuario también puede hacer clic en ellos para ver su conversación anterior.

- **Contactos de llamadas:** un usuario puede ver usuarios bloqueados en la lista de contactos de llamadas, pero se identificarán los usuarios bloqueados. La única acción que el usuario puede realizar en el bloque de usuarios es eliminarlos.

    Este es un ejemplo de un usuario bloqueado en la lista de contactos de llamadas.

    > [!div class="mx-imgBorder"]
    > ![Captura de pantalla que muestra el chat de usuario](media/ib-before-chat-contacts-policy.png)

    Este es un ejemplo de que el chat está deshabilitado para un usuario en la lista de contenido de llamadas.

    > [!div class="mx-imgBorder"]
    > ![Captura de pantalla que muestra el usuario bloqueado del chat](media/ib-after-chat-contacts-policy.png)

- **Migración de Skype** a Teams: durante una migración de Skype Empresarial a Teams, todos los usuarios, incluso aquellos usuarios bloqueados por directivas del IB, se migrarán a Teams. A continuación, esos usuarios se administran como se describe anteriormente.

## <a name="teams-policies-and-sharepoint-sites"></a>Directivas de Teams y sitios de SharePoint

Cuando se crea un equipo, se aprovisiona un sitio de SharePoint y se asocia con Microsoft Teams para la experiencia de archivos. Las directivas del IB no se respetan en este sitio de SharePoint ni en los archivos de forma predeterminada. Para habilitar las directivas del IB, el administrador ya ha rellenado un formulario solicitando que las directivas del IB se habiliten en SharePoint y OneDrive (consulte la sección *Requisitos previos* en Barreras de [información).](https://docs.microsoft.com/sharepoint/information-barriers#prerequisites) Si la directiva del IB está activada en SharePoint y OneDrive, las directivas del IB funcionarán en sitios de SharePoint que se aprovisionan cuando se crea un equipo con Microsoft Teams.

Ejemplo de directivas del IB en un sitio de **SharePoint** de un equipo: en Contoso Bank corporation, el usuario "Sesha@contosobank.onmicrosoft.com" pertenece al segmento de banca de inversión y el usuario "Nikita@contosobank.onmicrosoft.com" pertenece al segmento Asesor. La directiva IB de la organización bloquea la comunicación y la colaboración entre estos dos segmentos.
Cuando el usuario Sesha crea un equipo para el segmento banca de inversión, el equipo y el sitio de SharePoint que lo afiance solo serán accesibles para los usuarios de banca de inversión. El usuario Nikita no puede acceder a ese sitio incluso si tiene el vínculo del sitio.

Para obtener más información, vea [Usar barreras de información con SharePoint.](https://docs.microsoft.com/sharepoint/information-barriers#segments-associated-with-microsoft-teams-sites)

## <a name="required-licenses-and-permissions"></a>Licencias y permisos necesarios

Para obtener más información sobre licencias y permisos, incluidos los planes y los precios, vea Instrucciones de licencias de [Microsoft 365](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)para el cumplimiento de & seguridad.

## <a name="known-issues"></a>Problemas conocidos
- Los usuarios no pueden unirse a reuniones ad hoc: si las directivas del IB están **habilitadas,** los usuarios no pueden unirse a reuniones si el tamaño de la lista de reuniones es mayor que los límites de asistencia a la [reunión.](limits-specifications-teams.md) La causa principal es que las comprobaciones del IB dependen de si los usuarios se pueden agregar a una lista de chat de reunión y solo cuando se pueden agregar a la lista se les permite unirse a la reunión. Un usuario que se une a una reunión una vez agrega ese usuario a la lista; por lo tanto, para las reuniones periódicas, la lista puede rellenarse rápidamente. Una vez que la lista de chat alcanza los límites [de](limits-specifications-teams.md)asistencia a la reunión, no se permite agregar usuarios adicionales a la reunión. Si IB está habilitado para el inquilino y la lista de chats está completa para una reunión, los usuarios nuevos (aquellos usuarios que aún no están en la lista) no podrán unirse a la reunión. Pero si ELI no está habilitado para el inquilino y la lista de chats de la reunión está completa, los nuevos usuarios (aquellos usuarios que aún no están en la lista) pueden unirse a la reunión, aunque no verán la opción de chat en la reunión. Una solución a corto plazo es quitar miembros inactivos de la lista de chats de la reunión para crear espacio para los nuevos usuarios. Sin embargo, aumentaremos el tamaño de las listas de chat de reunión más adelante.

- Los usuarios no pueden unirse a las reuniones del canal: si las directivas del IB están **habilitadas,** los usuarios no pueden unirse a las reuniones del canal si no son miembros del equipo. La causa principal es que las comprobaciones del IB dependen de si los usuarios se pueden agregar a una lista de chat de reunión y solo cuando se pueden agregar a la lista se les permite unirse a la reunión. El hilo de chat de una reunión de canal solo está disponible para los miembros del equipo o del canal, y los que no son miembros no pueden ver ni acceder a la conversación de chat. Si IB está habilitado para el inquilino y un miembro que no es del equipo intenta unirse a una reunión del canal, ese usuario no puede unirse a la reunión. Sin embargo,  si ib no está habilitado para el inquilino y un miembro que no es del equipo intenta unirse a una reunión del canal, el usuario puede unirse a la reunión, pero no verá la opción de chat en la reunión.

- Los propietarios de equipos no se quitan: si se aplica una nueva directiva del IB que da como resultado dos o más segmentos en conflicto presentes en un canal de Teams, los segmentos con propietarios de equipos tienen una preferencia más alta y se quitan otros usuarios del segmento. Además, en este momento, los propietarios de equipos no se quitan, incluso si están en conflicto con otros propietarios o usuarios. Los administradores de inquilinos y otros propietarios de canales tendrán que quitar los propietarios en conflicto manualmente. Estamos trabajando en una corrección.

## <a name="more-information"></a>Más información

- Para obtener más información sobre los IB, vea [Barreras de información.](https://docs.microsoft.com/office365/securitycompliance/information-barriers)

- Para configurar directivas del IB, vea [Definir directivas para barreras de información.](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies)

- Para editar o quitar directivas del IB, vea [Editar (o quitar) directivas de](https://docs.microsoft.com/microsoft-365/compliance/information-barriers-edit-segments-policies)barrera de información.

## <a name="availability"></a>Disponibilidad
- La característica está disponible en nuestra nube pública; en enero de 2021, hemos lanzado Barreras de información en la nube de GCC.
- La característica aún no está disponible en las nubes GCCH y DOD.
