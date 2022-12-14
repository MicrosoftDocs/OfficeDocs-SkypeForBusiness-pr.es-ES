---
title: Controlar quién puede omitir la sala de espera de la reunión en Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
ms.reviewer: rbronisevsky
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Aprenda a usar la sala de espera de la reunión en Microsoft Teams para permitir que solo determinados participantes puedan unirse a la reunión directamente.
ms.openlocfilehash: c9073209a329c0d97c7d1951c02194d9924eea76
ms.sourcegitcommit: 0d97dc6616b3d633564409e39c08311af1522705
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/14/2022
ms.locfileid: "69392736"
---
# <a name="control-who-can-bypass-the-meeting-lobby-in-microsoft-teams"></a>Controlar quién puede omitir la sala de espera de la reunión en Microsoft Teams

La sala de espera de la reunión de Teams es una forma de impedir que determinados tipos de participantes se unan a una reunión hasta que un organizador de la reunión, un co-organizador o un moderador los admita. Cuando un participante va a la sala de espera, se notifica a los organizadores, co-organizadores y moderadores y pueden optar por admitirlos o no en la reunión.

Con la configuración de la sala de espera del Centro de administración de Teams, puede crear valores predeterminados para qué tipos de participantes de la reunión pueden omitir la sala de espera y qué participantes deben esperar allí hasta que se les admita en la reunión. Puede controlar cómo interactúan los siguientes tipos de participantes con la sala de espera:

- Organizador y co-organizador de la reunión
- Personas en su organización
- Invitados
- Personas en organizaciones de confianza
- Participantes anónimos

Las identidades de las personas que se unen a las reuniones se comprueban Microsoft 365 a menos que el participante sea anónimo. No se puede verificar a los participantes anónimos.

## <a name="prerequisites-for-meeting-with-people-outside-your-organization"></a>Requisitos previos para reunirse con personas de fuera de su organización

Hay varias opciones de configuración en Teams que controlan si las personas de fuera de la organización pueden interactuar con Teams. Las siguientes opciones de configuración deben estar habilitadas para que personas de fuera de la organización puedan unirse a reuniones:

- [El acceso de invitado en Teams](guest-access.md) debe estar habilitado para que los invitados puedan unirse a las reuniones.
- [El acceso externo](manage-external-access.md) debe estar habilitado para que los usuarios de organizaciones de confianza puedan unirse a las reuniones. Debe configurarse una confianza mutua entre la organización y la organización externa, así como el organizador de la reunión de la organización, así como habilitar el acceso externo a todos los participantes de la organización externa.
- Los **usuarios anónimos pueden unirse a una** configuración de reunión (nivel de organización) y la directiva de reunión (para el organizador que crea la reunión) deben estar **activadas** para que los participantes anónimos puedan unirse a las reuniones.

Si cualquiera de estas opciones está desactivada, ese tipo de participante externo no podrá unirse a las reuniones independientemente de la configuración de la sala de espera.

## <a name="overview-of-lobby-settings-and-policies"></a>Información general sobre las directivas y la configuración de la sala de espera

En la tabla siguiente se muestran las directivas de reunión de Teams que afectan a la forma en que los participantes de la reunión interactúan con la sala de espera.

|Setting|Descripción|
|:------|:----------|
|**Los usuarios anónimos y los autores de llamadas de acceso telefónico local pueden iniciar una reunión**|Esta es una directiva por organizador que permite reuniones sin coordinadores. Esta configuración controla si los participantes anónimos y los usuarios de acceso telefónico local pueden unirse a la reunión sin un participante verificado en la asistencia. Esta configuración solo se aplica cuando **quién puede omitir la sala de espera** se establece en **Todos**. Si la opción **Usuarios anónimos puede unirse a una reunión** o a una organización de la reunión está **desactivada**, esta configuración solo se aplica a los autores de llamadas de acceso telefónico local. De forma predeterminada, esta configuración está desactivada para evitar posibles abusos de los vínculos de reuniones por parte de usuarios anónimos. <br><br> Mientras **esté desactivado**, los participantes anónimos y los usuarios de acceso telefónico local esperarán en la sala de espera hasta que un participante verificado (incluido un organizador de acceso telefónico local) se una a la reunión, momento en el que se admitirá automáticamente. Una vez iniciada la reunión, los participantes anónimos y los usuarios de acceso telefónico local se unirán a la llamada automáticamente, incluso si el organizador se va. <br><br> Si esta configuración está **activada**, los participantes anónimos y de acceso telefónico local pueden iniciar la reunión y unirse a ella sin un participante verificado presente.|
|**Personas marcación puede omitir la sala de espera**|Esta es una directiva por organizador. Esta configuración controla si las personas que llaman por teléfono se unen a la reunión directamente o esperan en la sala de espera. Cuando esta configuración está **desactivada**, los usuarios de acceso telefónico local esperarán en la sala de espera hasta que un organizador, co-organizador o moderador se una a la reunión y los admita. Cuando esta configuración está **activada**, los usuarios de acceso telefónico local se unirán automáticamente a la reunión sin tener que pasar por la sala de espera. (Si **los usuarios anónimos y los autores de llamadas de acceso telefónico local pueden iniciar una reunión** está **desactivado**, esperarán en la sala de espera hasta que se inicie la reunión).|
|**Quién puede omitir la sala de espera**|Esta es una directiva por organizador. Esta configuración controla qué tipos de participantes (excepto aquellos que llaman por teléfono) se unen a una reunión directamente y qué tipos de participantes esperan en la sala de espera hasta que un organizador, un co-organizador o un moderador los admita.|

En la tabla siguiente se muestra cómo afecta cada opción de **la directiva Quién puede omitir la sala de espera** a cada *tipo de participante de la reunión*.

|Valor de la directiva:|Todos|Usuarios de mi organización y de organizaciones de confianza e invitados|Usuarios en mi organización e invitados|Usuarios en mi organización|Solo las personas invitadas|Solo los organizadores y co-organizadores|
|:--------|:------|:-----|:-----|:------|:-------|:---------------|
|*Organizador y co-organizador*|Bypass|Bypass|Bypass|Bypass|Bypass|Bypass|
|*Personas en la organización*|Bypass|Bypass|Bypass|Bypass|Personas que se enviaron o reenviaron una invitación se omitirán; otras personas esperan en la sala de espera|Vestíbulo|
|*Invitados*|Bypass|Bypass|Bypass|Vestíbulo|Personas que se enviaron o reenviaron una invitación se omitirán; otras personas esperan en la sala de espera|Vestíbulo|
|*Personas en organizaciones de confianza*|Bypass|Bypass|Vestíbulo|Vestíbulo|Personas que se enviaron o reenviaron una invitación se omitirán; otras personas esperan en la sala de espera|Vestíbulo|
|*Participantes anónimos*|Bypass|Vestíbulo|Vestíbulo|Vestíbulo|Vestíbulo|Vestíbulo|

**Solo las personas invitadas** se aplican solo a los participantes verificados a los que se envió una invitación o a los que se reenvió una invitación. Los usuarios agregados como parte de un grupo de distribución esperarán en la sala de espera.

## <a name="choose-who-can-bypass-the-lobby-in-meetings-hosted-by-your-organization"></a>Elegir quién puede omitir la sala de espera en reuniones hospedadas por su organización

Puede configurar las opciones y directivas descritas anteriormente en el Centro de administración de Teams. Consulte las secciones siguientes para obtener instrucciones sobre qué configuración elegir para diferentes circunstancias. Para obtener información sobre cómo funcionan las directivas de reunión, vea [Administrar directivas de reunión en Microsoft Teams](/microsoftteams/meeting-policies-overview).

> [!Important]
> Los organizadores de la reunión pueden cambiar los valores predeterminados que elija para el **Personas marcar puede omitir la sala de espera** y **Quién puede omitir la configuración de la sala de espera**. Si necesita aplicar esta configuración a un valor determinado, puede usar una plantilla de reunión o una etiqueta de confidencialidad (se requiere Teams Premium).  Para obtener más información, vea [Configurar la sala de espera de reunión de Microsoft Teams para reuniones confidenciales](configure-lobby-sensitive-meetings.md).

Para establecer las directivas para unirse a la reunión y la sala de espera
1. En el Centro de administración de Teams, expanda **Reuniones** y, después, seleccione **Directivas de reunión**.
1. Seleccione la directiva que desea actualizar.
1. En las secciones **Participante & invitados** , actualice la configuración que desea cambiar:
   - **Permitir que personas anónimas se unan a una reunión**
   - **Permitir que los usuarios anónimos inicien una reunión**
   - **Admitir automáticamente a personas** (quién puede omitir la sala de espera)
   - **Los usuarios de acceso telefónico local pueden omitir la sala de espera**

    ![Captura de pantalla que muestra la directiva para unirse a la reunión y la sala de espera en el Centro de administración de Teams.](media/meeting-join-and-lobby-tac-settings.png)
1. Seleccione **Guardar**.

Tenga en cuenta que los cambios pueden tardar hasta veinticuatro horas en surtir efecto.

Si desea permitir el acceso anónimo a la reunión, asegúrese de que la opción **Los usuarios anónimos pueden unirse a una reunión** también está activada.

Para establecer la configuración de reunión para toda la organización para unirse a una reunión anónima
1. En el Centro de administración de Teams, expanda **Reuniones** y, después, seleccione **Configuración de la reunión**.
1. En la sección **Participantes** , establezca **Que los usuarios anónimos puedan unirse a una reunión** **en Activado** o **Desactivado**.
    ![Captura de pantalla que muestra la configuración de unirse a la reunión y la sala de espera en el Centro de administración de Teams.](media/anonymous-users-can-join-meetings-org-setting.png)
1. Seleccione **Guardar**.

## <a name="control-access-to-meetings-by-anonymous-participants"></a>Controlar el acceso a las reuniones por parte de participantes anónimos

Los participantes anónimos son anónimos porque no han iniciado sesión en una cuenta que se puede comprobar con Microsoft 365. Esto podría incluir:

- Personas que no hayan iniciado sesión en Microsoft 365 con una cuenta profesional o educativa 
- Personas de organizaciones no de confianza (configuradas en [acceso externo](manage-external-access.md)).
- Personas de organizaciones en las que confía pero que no confían en su organización

Si quiere evitar que participantes anónimos se unan a la reunión por completo, puede desactivar la configuración **Los usuarios anónimos pueden unirse a una reunión** de toda la organización. También puede deshabilitar la unión anónima para organizadores de reuniones específicos mediante la directiva **Usuarios anónimos que pueden unirse a una reunión** .

Si quiere que los usuarios que se unan de forma anónima esperen en la sala de espera, puede establecer la configuración **Quién puede omitir la** directiva de la reunión de la sala de espera en cualquier opción excepto **Todos**. (Esta configuración no afecta a las personas que marcan por teléfono).

De forma predeterminada, los **usuarios anónimos y los autores de llamadas de acceso telefónico local pueden iniciar una directiva de reunión** están **desactivados**. Esto significa que los participantes anónimos y las personas que llaman por teléfono siempre esperarán en la sala de espera si un participante verificado aún no ha iniciado la reunión. Aunque puede activar esta configuración si hay circunstancias en las que desea permitir que participantes anónimos y personas que llaman por teléfono inicien reuniones, le recomendamos que lo deje desactivado.  Cuando la configuración está activada, las personas con cuentas no verificadas pueden iniciar reuniones, incluido el uso del vínculo de la reunión para tener reuniones a horas no programadas.

## <a name="control-access-to-meetings-by-people-dialing-in-by-phone"></a>Controlar el acceso a las reuniones por parte de personas que llaman por teléfono

De forma predeterminada, el **Personas marcación puede omitir la** directiva de sala de espera está **desactivada**, pero los organizadores de la reunión pueden cambiar esto al configurar la reunión. Puede cambiar el valor predeterminado actualizando el **Personas marcación puede omitir la** directiva de sala de espera o puede exigir un valor determinado mediante una plantilla de reunión.

## <a name="control-access-to-meetings-by-guests-and-people-from-trusted-organizations"></a>Controlar el acceso a las reuniones por parte de invitados y personas de organizaciones de confianza

Hay dos tipos de personas de fuera de la organización que pueden unirse a las reuniones como participantes comprobados:

- Invitados: personas que tienen una [cuenta de colaboración B2B de Azure Active Directory (Azure AD)](/azure/active-directory/external-identities/what-is-b2b) en su organización
- Usuarios de acceso externo: personas que tienen cuentas de Azure AD en una organización de confianza definida en [el acceso externo](manage-external-access.md) de Teams

Si quiere que todos los participantes verificados de la reunión de fuera de la organización esperen en la sala de espera, puede establecer la directiva Quién puede omitir la sala de espera **en Personas en mi organización** o **Solo los organizadores y co-organizadores** (siempre que un invitado no sea el organizador o co-organizador). Si quiere que solo los usuarios de organizaciones de confianza (usuarios de acceso externo) esperen en la sala de espera, puede elegir **Personas de mi organización e invitados**.

## <a name="control-access-to-meetings-by-people-without-invitations"></a>Controlar el acceso a las reuniones por personas sin invitaciones

Si quiere permitir que solo las personas que tienen invitaciones se unan a reuniones directamente y que todos los demás participantes esperen en la sala de espera, establezca **Quién puede omitir la sala de espera** en **Solo las personas invitadas**. (Personas invitados a través de la lista de distribución no están incluidos).

La opción **Solo las personas invitadas** incluye los participantes verificados a los que se reenvió la invitación, no solo aquellos invitados directamente por el organizador. No incluye a las personas que tienen el vínculo para unirse a la reunión, pero no a la invitación en sí ni a los participantes no comprobados (anónimos). Deben esperar en la sala de espera.

Tenga en cuenta que los organizadores de la reunión pueden deshabilitar el reenvío de la invitación a la reunión si solo quieren que las personas invitadas directamente por ellos asistan a la reunión.

## <a name="control-access-to-meetings-by-non-organizers"></a>Controlar el acceso a las reuniones por parte de usuarios que no son organizadores

Si tiene reuniones en las que se comparte información confidencial o que están sujetas a requisitos normativos, es posible que quiera que todos los participantes esperen en la sala de espera hasta que un organizador o un co-organizador de la reunión los admita. En este caso, puede establecer **Quién puede omitir la sala de espera** en **Solo los organizadores y co-organizadores**.

Como **Quién puede omitir la sala de espera** solo establece un valor predeterminado que los organizadores de la reunión pueden cambiar, considere aplicar el valor con una etiqueta de confidencialidad o una plantilla de reunión si tiene requisitos de cumplimiento en esta área. Para obtener más información, vea [Configurar la sala de espera de reunión de Microsoft Teams para reuniones confidenciales](configure-lobby-sensitive-meetings.md).

## <a name="set-meeting-policies-by-using-powershell"></a>Establecer directivas de reunión con PowerShell

Puede establecer las directivas de reunión descritas en este artículo mediante el cmdlet de PowerShell [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) con los siguientes parámetros:

- [-AllowAnonymousUsersToJoinMeeting](/powershell/module/skype/set-csteamsmeetingpolicy?#-allowanonymoususerstojoinmeeting) para controlar si los usuarios anónimos pueden unirse a reuniones
- [-AllowPSTNUsersToBypassLobby](/powershell/module/skype/set-csteamsmeetingpolicy#-allowpstnuserstobypasslobby) para controlar si las personas que llaman por teléfono pueden omitir la sala de espera
- [-AutoAdmittedUsers](/powershell/module/skype/set-csteamsmeetingpolicy?#-autoadmittedusers) para controlar quién puede omitir la sala de espera

## <a name="related-topics"></a>Temas relacionados

[Unirse a una reunión sin una cuenta de Teams](https://support.microsoft.com/office/c6efc38f-4e03-4e79-b28f-e65a4c039508)

[Usar el Centro de administración de Microsoft Teams para configurar la directiva de toda la organización](meeting-settings-in-teams.md#allow-anonymous-users-to-join-meetings)

[Los participantes externos reciben "Iniciar sesión en Teams para unirse o ponerse en contacto con el organizador de la reunión"](/microsoftteams/troubleshoot/meetings/external-participants-join-meeting-blocked)
