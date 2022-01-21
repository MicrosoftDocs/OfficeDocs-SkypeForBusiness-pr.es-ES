---
title: Barreras de información en Microsoft Teams
description: En este artículo se explican qué son las barreras de información Microsoft Teams y cómo pueden afectar a Teams.
author: robmazz
ms.author: robmazz
manager: laurawi
ms.reviewer: vikramju
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 247f8e1d735bfe331c914da1ec89863b755cf373
ms.sourcegitcommit: 11061890a64da88d92db3fa43f1bf320b216c355
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/21/2022
ms.locfileid: "62163551"
---
# <a name="information-barriers-in-microsoft-teams"></a>Barreras de información en Microsoft Teams

Las barreras de información (IB) son directivas que un administrador puede configurar para evitar que individuos o grupos se comuniquen entre sí. Los IB son útiles si, por ejemplo, un departamento administra información que no debería compartirse con otros departamentos. Los IB también son útiles cuando es necesario aislar un grupo o impedir que se comunique con cualquier persona que no sea de ese grupo.

Por Microsoft Teams, las barreras de información pueden determinar y evitar los siguientes tipos de colaboraciones no autorizadas:

- Agregar un usuario a un equipo o canal
- Acceso de usuario al contenido del equipo o del canal
- Acceso de usuario a chats grupales y 1:1
- Acceso de usuario a reuniones
- Impide las búsquedas y la detección, los usuarios no estarán visibles en el selector de personas.

>[!NOTE]
>- Los grupos de barreras de información no se pueden crear entre inquilinos.
>- Con bots, Azure Active Directory (Azure AD), API para enviar notificaciones de fuente de actividades y algunas API para agregar usuarios no es compatible con la versión 1.
>- Los canales privados son compatibles con las directivas de barreras de información que configure.
>- Para obtener información sobre la compatibilidad con barreras SharePoint sitios conectados a Teams, vea Segmentos [asociados](/sharepoint/information-barriers#segments-associated-with-microsoft-teams-sites)a Microsoft Teams sitios .

## <a name="background"></a>Información general

El controlador principal de los IB proviene del sector de servicios financieros. La Autoridad reguladora del sector financiero[(FINRA)]( https://www.finra.org)revisa los IB y los conflictos de interés dentro de las empresas miembros y proporciona instrucciones sobre la administración de dichos conflictos (FINRA 2241, Aviso normativo de investigación de deuda [15-31.](https://www.finra.org/sites/default/files/Regulatory-Notice-15-31_0.pdf)

Sin embargo, desde la introducción de los IB, muchas otras áreas han encontrado que son útiles. Otros escenarios comunes incluyen:

- **Educación:** Los alumnos de una escuela no pueden buscar detalles de contacto para los alumnos de otras escuelas.
- **Legal:** Mantener la confidencialidad de los datos obtenidos por el abogado de un cliente e impedir que un abogado de la misma empresa que representa a un cliente diferente pueda acceder a ellos.
- **Gobierno:** el acceso a la información y el control están limitados entre departamentos y grupos.
- **Professional:** un grupo de personas de una empresa solo puede chatear con un cliente o con un cliente específico a través del acceso de invitado durante una participación del cliente.

Por ejemplo, Enrico pertenece al segmento bancario y Pradeep pertenece al segmento asesor financiero. Enrico y Pradeep no pueden comunicarse entre sí porque la directiva del IB de la organización bloquea la comunicación y la colaboración entre estos dos segmentos. Sin embargo, Enrico y Pradeep pueden comunicarse con Lee en RECURSOS HUMANOS.

![Ejemplo que muestra barreras de información que impiden la comunicación entre segmentos.](media/information-barriers-example.png)

## <a name="when-to-use-information-barriers"></a>Cuándo usar barreras de información

Es posible que desee usar los IB en situaciones como estas:

- Se debe impedir que un equipo comunique o comparta datos con un equipo específico.
- Un equipo no debe comunicarse ni compartir datos con nadie fuera del equipo.

El servicio de evaluación de directivas de barrera de información determina si una comunicación cumple con las directivas del IB.

## <a name="managing-information-barrier-policies"></a>Administrar directivas de barreras de información

Las directivas del IB se administran en Microsoft 365 de cumplimiento (SCC) con cmdlets de PowerShell. Para obtener más información, vea [Definir directivas para barreras de información.](/office365/securitycompliance/information-barriers-policies)

>[!IMPORTANT]
>Antes de configurar o definir directivas, debe habilitar la búsqueda de directorios de ámbito en Microsoft Teams. Espere al menos unas horas después de habilitar la búsqueda de directorios de ámbito antes de configurar o definir directivas para barreras de información. Para obtener más información, vea [Definir directivas de barreras de información.](/office365/securitycompliance/information-barriers-policies#prerequisites)

## <a name="information-barriers-administrator-role"></a>Rol de administrador de barreras de información

El rol de administración de cumplimiento del IB es responsable de administrar las directivas del IB. Para obtener más información sobre este rol, vea [Permisos en el Centro de Microsoft 365 cumplimiento.](/office365/securitycompliance/permissions-in-the-security-and-compliance-center)

## <a name="information-barrier-triggers"></a>Desencadenadores de barrera de información

Las directivas del IB se activan cuando se Teams eventos:

- **Los miembros se agregan a** un equipo: siempre que agregue un usuario a un equipo, la directiva del usuario debe evaluarse con las directivas del IB de otros miembros del equipo. Después de agregar correctamente al usuario, el usuario puede realizar todas las funciones del equipo sin más comprobaciones. Si la directiva del usuario impide que se le agregó al equipo, el usuario no se mostrará en la búsqueda.

    ![Captura de pantalla de búsqueda de un nuevo miembro para agregar a un equipo y no encontrar coincidencias.](media/information-barriers-add-members.png)

- Se solicita un **nuevo chat:** cada vez que un usuario solicita un nuevo chat con uno o varios usuarios, el chat se evalúa para asegurarse de que no infringe ninguna política del IB. Si la conversación infringe una directiva del IB, la conversación no se inicia.

    Este es un ejemplo de un chat 1:1.

    ![Captura de pantalla que muestra la comunicación bloqueada en un chat de 1:1.](media/information-barriers-one-one-chat.png)

    Este es un ejemplo de un chat grupal.

    ![Captura de pantalla que muestra el chat grupal.](media/information-barriers-group-chat.png)

- Se invita a un usuario a unirse **a** una reunión: cuando se invita a un usuario a unirse a una reunión, la directiva del IB que se aplica al usuario se evalúa con las directivas del IB que se aplican a los demás miembros del equipo. Si hay una infracción, el usuario no podrá unirse a la reunión.

    ![Captura de pantalla que muestra el usuario bloqueado de la reunión.](media/information-barriers-meeting.png)

- **Una pantalla** se comparte entre dos o más usuarios: cuando un usuario comparte una pantalla con otros usuarios, el uso compartido debe evaluarse para asegurarse de que no infringe las directivas del IB de otros usuarios. Si se infringe una directiva del IB, no se permitirá el uso compartido de pantalla.

    Este es un ejemplo de uso compartido de pantalla antes de aplicar la directiva.

    ![Captura de pantalla que muestra un chat de usuario.](media/ib-before-screen-share-policy.png)

    Este es un ejemplo de uso compartido de pantalla después de aplicar la directiva. Los iconos de pantalla y de llamada no son visibles.

    ![Captura de pantalla que muestra el carácter de usuario con la configuración bloqueada.](media/ib-after-screen-share-policy.png)

- Un usuario realiza una llamada de teléfono en **Teams:** Siempre que un usuario inicia una llamada de voz (a través de VOIP) a otro usuario o grupo de usuarios, la llamada se evalúa para asegurarse de que no infringe las directivas del IB de otros miembros del equipo. Si hay alguna infracción, la llamada de voz está bloqueada.

- **Invitados en Teams:** las condiciones del IB también se aplican a los Teams invitados. Si los invitados necesitan ser reconocibles en la lista global de direcciones de su organización, vea Administrar el acceso de invitado [en Microsoft 365 grupos.](/microsoft-365/admin/create-groups/manage-guest-access-in-groups) Una vez que los invitados se puedan descubrir, puede [definir las directivas del IB.](/office365/securitycompliance/information-barriers-policies)

## <a name="how-policy-changes-impact-existing-chats"></a>Cómo afectan los cambios de directiva a los chats existentes

Cuando el administrador de directivas del IB realiza cambios en una directiva o cuando se activa un cambio de directiva debido a un cambio en el perfil de un usuario (por ejemplo, para un cambio de trabajo), el Servicio de evaluación de directivas de barrera de información busca automáticamente a los miembros para asegurarse de que su pertenencia al equipo no infringe ninguna directiva.

Si hay un chat existente u otra comunicación entre los usuarios, y se establece una nueva directiva o se cambia una directiva existente, el servicio evalúa las comunicaciones existentes para asegurarse de que las comunicaciones siguen estando permitidas. 

- **Chat 1:1:** Si ya no se permite la comunicación entre dos usuarios (debido a la aplicación a uno o ambos usuarios de una directiva que bloquea la comunicación), se bloquea la comunicación adicional. Sus conversaciones de chat existentes se convierten en de solo lectura.

    Este es un ejemplo que muestra que el chat está visible.

    ![Captura de pantalla que muestra el chat de usuario está disponible.](media/ib-before-1-1chat-policy.png)

    Este es un ejemplo que muestra que el chat está deshabilitado.

    ![La captura de pantalla que muestra el chat de usuario está deshabilitada.](media/ib-after-1-1chat-policy.png)

- Chat **grupal:** si la comunicación de un usuario a un grupo ya no está permitida (por ejemplo, porque un usuario cambió los trabajos), el usuario, junto con los demás usuarios cuya participación infringe la directiva, puede quitarse del chat grupal y no se permitirá una comunicación adicional con el grupo. El usuario todavía puede ver conversaciones antiguas, pero no podrá ver ni participar en nuevas conversaciones con el grupo. Si la directiva nueva o modificada que impide la comunicación se aplica a más de un usuario, es posible que los usuarios afectados por la directiva se quiten del chat grupal. Todavía pueden ver conversaciones antiguas.

  En este ejemplo, Enrico se mueve a otro departamento de la organización y se quita del chat grupal.

  ![Captura de pantalla de un chat grupal del que se ha quitado un usuario.](media/information-barriers-user-changes-job.png)

  Enrico ya no puede enviar mensajes al chat grupal.

  ![Captura de pantalla de no poder enviar mensajes al chat grupal porque el usuario se quitó del grupo.](media/information-barriers-user-changes-job-2.png)

- **Equipo:** los usuarios que se han quitado del grupo se quitan del equipo y no podrán ver ni participar en conversaciones existentes o nuevas.

## <a name="scenario-a-user-in-an-existing-chat-becomes-blocked"></a>Escenario: Un usuario de un chat existente se bloquea

Actualmente, los usuarios experimentan los siguientes escenarios si una directiva del IB bloquea a otro usuario:

- **Pestaña Personas:** un usuario no puede ver usuarios bloqueados en la **pestaña** Personas.

- **Selector de personas:** los usuarios bloqueados no estarán visibles en el selector de personas.

    ![Captura de pantalla Teams alerta al usuario de que la directiva impide mostrar la información de otro usuario.](media/information-barriers-people-picker.png)

- **Pestaña Actividad:** si un usuario visita **la** pestaña Actividad de un usuario bloqueado, no aparecerá ninguna publicación. (La **pestaña Actividad** solo muestra publicaciones de canal y no habría canales comunes entre los dos usuarios).

    Este es un ejemplo de la vista de pestaña actividad que está bloqueada.

    ![Captura de pantalla que muestra la pestaña actividad que está bloqueada.](media/ib-after-activity-tab-policy.png)

- **Organigramas:** si un usuario accede a un organigrama en el que aparece un usuario bloqueado, el usuario bloqueado no aparecerá en el organigrama. En su lugar, aparecerá un mensaje de error.

- **Tarjeta personas:** si un usuario participa en una conversación y el usuario se bloquea más tarde, otros usuarios verán un mensaje de error en lugar de la tarjeta de personas cuando pase el puntero sobre el nombre del usuario bloqueado. Las acciones enumeradas en la tarjeta (como llamadas y chats) no estarán disponibles.

- **Contactos sugeridos:** los usuarios bloqueados no aparecen en la lista de contactos sugeridos (la lista de contactos inicial que aparece para los nuevos usuarios).

- **Contactos de chat:** un usuario puede ver usuarios bloqueados en la lista de contactos de chats, pero los usuarios bloqueados se identificarán. La única acción que el usuario puede realizar en los usuarios bloqueados es eliminarlos. El usuario también puede seleccionarlo para ver su conversación anterior.

- **Contactos de llamadas:** un usuario puede ver usuarios bloqueados en la lista de contactos de llamadas, pero los usuarios bloqueados se identificarán. La única acción que el usuario puede realizar en el bloque de usuarios es eliminarlos.

    Este es un ejemplo de un usuario bloqueado en la lista de contactos de llamadas.

    > [!div class="mx-imgBorder"]
    > ![Captura de pantalla que muestra el chat de usuario.](media/ib-before-chat-contacts-policy.png)

    Este es un ejemplo de que el chat está deshabilitado para un usuario en la lista de contenido de llamadas.

    > [!div class="mx-imgBorder"]
    > ![Captura de pantalla que muestra el usuario bloqueado del chat.](media/ib-after-chat-contacts-policy.png)

- Skype a **Teams:** durante una migración de Skype Empresarial a Teams, todos los usuarios, incluso aquellos que están bloqueados por directivas del IB, se migrarán a Teams. A continuación, esos usuarios se administran como se describe anteriormente.

## <a name="teams-policies-and-sharepoint-sites"></a>Teams directivas y SharePoint sitios

Cuando se crea un equipo, SharePoint sitio se aprovisiona y se asocia con Microsoft Teams para la experiencia de archivos. Las directivas de barrera de información no se respetan en SharePoint sitio y archivos de forma predeterminada. Para habilitar las barreras de información en SharePoint y OneDrive, siga las instrucciones y los pasos del artículo Usar [barreras](/sharepoint/information-barriers#enable-sharepoint-and-onedrive-information-barriers-in-your-organization) de información SharePoint información.

## <a name="information--barrier-modes-and-teams"></a>Modos de barrera de información y Teams

El modo barreras de información ayuda a fortalecer quién se puede agregar o quitar de un equipo. Al usar barreras de información con Teams, se admiten los siguientes modos de IB:

- **Abrir:** esta configuración es el modo IB predeterminado para todos los grupos existentes que se aprovisionaron antes de habilitar las barreras de información. En este modo, no hay directivas del IB aplicables.
- **Implícito:** esta configuración es el modo IB predeterminado cuando se aprovisiona un equipo después de habilitar las barreras de información. El modo implícito le permite agregar todos los usuarios compatibles en el grupo.
- **Propietario moderado (versión preliminar):** este modo se establece en un equipo cuando desea permitir la colaboración entre usuarios de segmento incompatibles moderados por el propietario. El propietario del equipo puede agregar nuevos miembros según su directiva del IB.

Teams antes de activar una directiva de barrera de información en el espacio empresarial se establecen automáticamente en *Modo* abierto de forma predeterminada. Una vez que haya activado las directivas del IB en el inquilino, es necesario que actualice el modo de los equipos existentes a *Implícito* para asegurarse de que los equipos existentes cumplen con ib.

Use el cmdlet [Set-UnifiedGroup](/powershell/module/exchange/set-unifiedgroup) con el parámetro *InformationBarrierMode* que corresponde al modo que desea usar para los segmentos. La lista de valores permitidos para el *parámetro InformationBarrierMode* son *Open*, *Implicit* y *Owner Moderated*.

Por ejemplo, para configurar el *modo* implícito para un grupo Microsoft 365, usará el siguiente comando de PowerShell:

```powershell
Set-UnifiedGroup -InformationBarrierMode Implicit
```

Para actualizar el modo de Abrir a Implícito para todos los equipos existentes, use este [script de PowerShell](information-barriers-mode-script.md).

Si cambia la configuración de modo abierto en grupos conectados Teams existentes para cumplir los requisitos de cumplimiento de su organización, tendrá que actualizar los modos [del IB](/sharepoint/information-barriers.md#view-and-manage-ib-modes-as-an-administrator-with-sharepoint-powershell) para los sitios SharePoint asociados conectados al equipo de Teams.

## <a name="required-licenses-and-permissions"></a>Licencias y permisos necesarios

Para obtener más información sobre licencias y permisos, planes y precios, consulte Microsoft 365 de licencias para el cumplimiento de & [seguridad.](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)

## <a name="known-issues"></a>Problemas conocidos

- Los usuarios no pueden unirse a reuniones ad hoc: si las directivas del IB están **habilitadas,** los usuarios no pueden unirse a reuniones si el tamaño de la lista de reuniones es mayor que los límites de asistencia a la [reunión.](limits-specifications-teams.md) La causa principal es que las comprobaciones del IB dependen de si los usuarios se pueden agregar a una lista de chat de reunión y solo cuando se pueden agregar a la lista se les permite unirse a la reunión. Un usuario que se une a una reunión una vez agrega ese usuario a la lista; por lo tanto, para las reuniones periódicas, la lista puede rellenarse rápidamente. Una vez que la lista de chat alcanza los límites [de](limits-specifications-teams.md)asistencia a la reunión, no se pueden agregar usuarios adicionales a la reunión. Si IB está habilitado para la organización y la lista de chats está completa para una reunión, los usuarios nuevos (aquellos usuarios que aún no están en la lista) no pueden unirse a la reunión. Pero si ELI no está habilitado para la organización y la lista de chats de la reunión está completa, los nuevos usuarios (aquellos usuarios que aún no están en la lista) pueden unirse a la reunión, aunque no verán la opción de chat en la reunión. Una solución a corto plazo es quitar miembros inactivos de la lista de chats de la reunión para crear espacio para los nuevos usuarios. Sin embargo, aumentaremos el tamaño de las listas de chat de reunión más adelante.
- Los usuarios no pueden unirse a las reuniones del canal: si las directivas del IB están **habilitadas,** los usuarios no pueden unirse a las reuniones del canal si no son miembros del equipo. La causa principal es que las comprobaciones del IB dependen de si los usuarios se pueden agregar a una lista de chat de reunión y solo cuando se pueden agregar a la lista se les permite unirse a la reunión. El hilo de chat de una reunión de canal solo está disponible para los miembros del equipo o del canal, y los que no son miembros no pueden ver ni acceder a la conversación de chat. Si ELI está habilitado para la organización y un miembro que no es del equipo intenta unirse a una reunión del canal, ese usuario no puede unirse a la reunión. Sin embargo,  si ib no está habilitado para la organización y un miembro que no es del equipo intenta unirse a una reunión del canal, el usuario puede unirse a la reunión, pero no verá la opción de chat en la reunión.
- **Número máximo de segmentos permitidos en** una organización: cada organización puede configurar hasta 100 segmentos al configurar directivas del IB. No hay ningún límite en el número de directivas que se pueden configurar.
- **Las directivas del IB** no funcionan para usuarios federados: si permite la federación con organizaciones externas, las directivas del IB no restringirán los usuarios de dichas organizaciones. Si los usuarios de su organización se unen a un chat o reunión organizado por usuarios federados externos, las directivas del IB tampoco restringirán la comunicación entre los usuarios de su organización.

## <a name="more-information"></a>Más información

- Para obtener más información sobre los IB, vea [Barreras de información.](/office365/securitycompliance/information-barriers)
- Para configurar directivas del IB, vea [Introducción a las barreras de información.](/office365/securitycompliance/information-barriers-policies)
- Para editar o quitar directivas del IB, vea [Administrar directivas de barreras de información.](/microsoft-365/compliance/information-barriers-edit-segments-policies)

## <a name="availability"></a>Disponibilidad

- La característica está disponible en nuestra nube pública; en enero de 2021, hemos lanzado barreras de información en la GCC nube.
- La característica aún no está disponible en el GCC: nubes altas y dod.
