---
title: Administrar el acceso externo (federación) en Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: vinbel
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.externalaccess.overview
description: Su equipo o administrador de ti puede configurar el acceso externo para otros dominios (Federación) para permitir que los usuarios de esos dominios participen en Teams.
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 071bb1523a0840a798edfe030a1dd52362695df2
ms.sourcegitcommit: 09e719ead5c02b3cfa96828841c4905748d192a3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2019
ms.locfileid: "37753535"
---
<a name="manage-external-access-in-microsoft-teams"></a>Administrar el acceso externo en Microsoft Teams
======================================================

El acceso externo es una forma para que los usuarios externos de equipos externos puedan buscar, llamar, chatear y configurar reuniones con usted en Teams. También puede usar el acceso externo para comunicarse con usuarios externos que siguen usando Skype empresarial (en línea y local) y Skype (próximamente 2020).

Si quiere que los usuarios externos tengan acceso a los equipos y los canales, el acceso de invitados puede ser una mejor manera de hacerlo. Para obtener más información sobre las diferencias entre el acceso externo y el acceso de invitados, consulte [comparar el acceso externo y](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access)el de invitado. 

Use acceso externo cuando:
  
- Tiene usuarios en diferentes dominios que necesitan colaborar. Por ejemplo, Rob@contoso.com y Ann@northwindtraders.com trabajan en un proyecto junto con algunos otros en los dominios contoso.com y northwindtraders.com.

- Quiere que las personas de su organización usen Teams para ponerse en contacto con personas de empresas específicas de fuera de su organización.

- Desea que cualquier persona del mundo que use Teams pueda encontrarse y ponerse en contacto con usted, usando su dirección de correo electrónico. 




> [!IMPORTANT]
> En la actualidad, para federar dentro de la aplicación Microsoft Teams a un usuario externo fuera de su organización que no es actualmente invitado de su Azure Active Directory (Azure AD) o de inquilino, debe estar correctamente configurado para un híbrido y pasarse a Skype empresarial online. A partir del 25 de febrero de 2019, Teams no admite la Federación nativa sin que el usuario del perfil SIP se haya alojado en Skype empresarial online. Para obtener más información sobre cómo configurar su cuenta para una implementación híbrida y después a los equipos, consulte [actualizar la implementación híbrida de Skype empresarial a teams](https://docs.microsoft.com/microsoftteams/upgrade-to-teams-execute-skypeforbusinesshybrid).






## <a name="plan-for-external-access"></a>Planear el acceso externo

De forma predeterminada, el acceso externo está activado en Teams, lo que significa que su organización puede comunicarse con todos los dominios externos. Si agrega dominios bloqueados, todos los demás dominios estarán permitidos; y, si agrega dominios permitidos, todos los demás dominios se bloquearán. Hay tres escenarios para configurar el acceso externo en el centro de administración de equipos (configuración > de**acceso externo a****toda la organización**):

- **Abrir Federación**: esta es la configuración predeterminada en Teams y permite a los usuarios de la organización buscar, llamar, chatear y configurar reuniones con personas externas a su organización en cualquier dominio.

    En este escenario, los usuarios pueden comunicarse con todos los dominios externos que ejecutan Teams o Skype empresarial y están usando la Federación abierta o han agregado su dominio a su lista de permitidos.

- **Permitir dominios específicos**: al agregar dominios a una lista de **permitidos** , limitará el acceso externo solo a los dominios permitidos. Una vez que haya configurado una lista de dominios permitidos, todos los demás dominios se bloquearán. Para permitir dominios específicos, haga clic en **Agregar un dominio**, agregue el nombre de dominio, haga clic en **acción para realizar en este dominio**y, a continuación, seleccione **permitido**.

- **Bloquear dominios específicos** : al agregar dominios a una lista de **bloqueados** , puedes comunicarte con todos los dominios externos *excepto* los que hayas bloqueado. Para bloquear dominios específicos, haga clic en **Agregar un dominio**, agregue el nombre de dominio, haga clic en **acción para realizar en este dominio**y, a continuación, seleccione **bloqueado**. Una vez que haya configurado una lista de dominios bloqueados, todos los demás dominios estarán permitidos.

## <a name="allow-or-block-domains"></a>Permitir o bloquear dominios

### <a name="step-1---enable-your-organization-to-communicate-with-another-teams-organization"></a>Paso 1: permitir que su organización se comunique con otra organización de Teams

![Un icono que muestra el logotipo](media/teams-logo-30x30.png)de Microsoft Teams**con el centro de administración de Microsoft Teams**  

1. En el navegación de la izquierda, vaya a **configuración** > de**acceso externo**de la organización.

2. Activar o desactivar los **usuarios pueden comunicarse con Skype empresarial y los usuarios de Teams** cambien a **activado**.

     ![Captura de pantalla del interruptor de acceso externo activado](media/manage-external-access-2.png).

3. Si desea permitir que todas las organizaciones de Teams se comuniquen con los usuarios de su organización, vaya al paso 5.

4. Si desea limitar las organizaciones que pueden comunicarse con los usuarios de su organización, puede permitir todos los dominios excepto algunos, o bien puede permitir solo dominios específicos. 

    - Para permitir todos los dominios excepto algunos, agregue los dominios que desea bloquear haciendo clic en **Agregar dominio**. En el panel **Agregar un dominio** , escriba el nombre de dominio, haga clic en **bloqueado**y, a continuación, haga clic en **listo**. 
    - Para limitar las comunicaciones a organizaciones específicas, agregue esos dominios a la lista con el estado **permitido**. Una vez que haya agregado cualquier dominio a la lista de permitidos, las comunicaciones con otras organizaciones se limitarán únicamente a las organizaciones cuyos dominios estén en la lista de permitidos. 

5. Haga clic en **Guardar **.

6. Asegúrese de que el administrador de la organización de otros equipos completa estos mismos pasos. Por ejemplo, en su lista de **dominios permitidos** , su administrador debe especificar el dominio de su empresa si limita las organizaciones que pueden comunicarse con sus usuarios.

### <a name="step-2---test-it"></a>Paso 2: pruébelo

Para probar la configuración, necesita un usuario de teams que no esté detrás de su firewall.
  
1. Después de que usted y el administrador de la organización hayan cambiado la configuración de **acceso externo** , debe estar listo.

2. En la aplicación de Teams, busque la persona por dirección de correo electrónico y envíe una solicitud a una conversación.

3. Pídale al contacto de su equipo que le envíe una solicitud para chatear. Si no recibe la solicitud, quiere decir que el problema se encuentra en la configuración de su firewall (siempre que haya confirmado que la configuración de su firewall es correcta).

4. Otra forma de comprobar si el problema es el Firewall es ir a una ubicación WiFi que no esté detrás de su firewall. como una cafetería, y usar Teams para enviar una solicitud a su contacto para chatear. Si el mensaje pasa por la ubicación WiFi pero no cuando está en el trabajo, significa que el problema es su firewall.

> [!NOTE]
> Si usted y otro usuario activan el acceso externo y permiten los dominios de los demás, esto funcionará. Si no funciona, el otro usuario debe asegurarse de que su configuración no esté bloqueando su dominio.

## <a name="communicate-with-users-in-a-skype-for-business-online-organization"></a>Comunicarse con los usuarios en una organización de Skype empresarial online

Si está configurando un acceso externo para permitir que los usuarios de su equipo encuentren y se pongan en contacto con usuarios de una organización de Skype empresarial que limite quién puede comunicarse con sus usuarios, siga los pasos para configurar el acceso externo desde su dominio al dominio de la otra organización. Después, solicite al administrador de la otra organización que siga los pasos a continuación para configurar el acceso externo para Skype empresarial online. 

Para obtener instrucciones específicas sobre escenarios comunes de Skype empresarial online, consulte [escenarios comunes de acceso externo](#common-external-access-scenarios) a continuación.

![Un icono que muestra el logotipo](media/sfb-logo-30x30.png) de Skype empresarial **con el centro de administración de Skype empresarial**

Haga que el administrador de la organización Realice estos pasos:

1. En el centro de administración de Microsoft 365, vaya a los **centros** > de administración**Teams &** > **portal heredado**de Skype.
  
2. En el **centro de administración de Skype empresarial**, elija**comunicaciones externas**de la **organización** > .

3. Para configurar la comunicación con una empresa específica o con usuarios de otro dominio, en el cuadro desplegable, elija **activado solo para los dominios permitidos**.

    O, si desea permitir la comunicación con cualquier persona del mundo que tenga abiertas las directivas de Skype empresarial, elija **activado excepto para los dominios bloqueados**. Esta es la configuración que se aplica normalmente.

4. En **dominios bloqueados o permitidos**, elija **+** y, a continuación, agregue el nombre del dominio que desea permitir.

## <a name="common-external-access-scenarios"></a>Escenarios comunes de acceso externo

|**Si quiere....**  |**Haga esto**  |
|---------|-----------------------|
|Permita que **los usuarios de Teams** de la organización se comuniquen con **los usuarios de Teams** en otra organización (externa).|En acceso externo, agregue el dominio externo a la lista de permitidos o use abrir Federación. A continuación, haga lo mismo el administrador de la organización de otros equipos.      |
|Permita que **los usuarios de Teams** de la organización se comuniquen con **usuarios de Skype empresarial online** en la misma organización.  |Habilite el modo de coexistencia o elija el modo de actualización de islas para admitir los usuarios de Skype empresarial de su organización.   |
|Permita que **los usuarios de Teams** de la organización se comuniquen con **usuarios de Skype empresarial online** en otra organización (externa).      |En acceso externo, agregue el dominio externo a la lista de permitidos o use abrir Federación. <br><br>Activar **los usuarios pueden comunicarse con Skype empresarial y los usuarios de Teams** en acceso externo. A continuación, haga lo mismo el administrador de la organización de otros equipos. <br><br>**Nota**: el dominio externo con usuarios de Skype empresarial debe habilitar el modo de coexistencia o elegir el modo de actualización de islas para admitir los usuarios de Skype empresarial de esa organización.|
|Permita que **los usuarios de Teams** de la organización se comuniquen con usuarios de **Skype** desde dentro o fuera de su organización.   | Este escenario estará disponible próximamente. <br><br>**Importante**: los usuarios de Teams aún no pueden comunicarse con usuarios de Skype, pero sus usuarios de Skype empresarial pueden continuar comunicándose con usuarios de Skype dentro o fuera de su organización. Activar los **usuarios pueden comunicarse con los usuarios de Skype empresarial y de Teams** y los **usuarios de Skype empresarial pueden comunicarse con** la configuración de usuarios de Skype en acceso externo. |
|Permita que los **usuarios de Skype empresarial online** se comuniquen con **los usuarios de Teams** en otra organización de 365 de Office.| Los usuarios de Skype empresarial online pueden comunicarse con los usuarios de un equipo de otra organización si los usuarios tienen uno de los siguientes modos de actualización: Islas, SfBOnly, SfBWIthTeamsCollab, SfBWithTeamsCollabAndMeetings; y los usuarios de Teams de la otra organización están en el modo TeamsOnly. <br><br>Active la opción los **usuarios pueden comunicarse con Skype empresarial y los usuarios de Teams** en acceso externo. A continuación, haga que el administrador de la organización de otros equipos realice las mismas acciones.|
|Permita que los **usuarios de Skype empresarial online** se comuniquen con **usuarios de Skype empresarial online** de otra organización de Office 365.    | Los usuarios de Skype empresarial online pueden comunicarse con los usuarios de Skype empresarial online de otra organización si los usuarios tienen uno de los siguientes modos de actualización: Islas, SfBOnly, SfBWIthTeamsCollab, SfBWithTeamsCollabAndMeetings; y los usuarios de Skype empresarial online de la otra organización se encuentran en uno de los siguientes modos de actualización: Islas, SfBOnly, SfBWIthTeamsCollab, SfBWithTeamsCollabAndMeetings.<br><br>Active la opción los **usuarios pueden comunicarse con Skype empresarial y los usuarios de Teams** en acceso externo. A continuación, haga que el administrador de la organización de otros equipos realice las mismas acciones.|
|Permita que los **usuarios de Skype empresarial online** se comuniquen con **usuarios de Skype empresarial** desde una organización local.     |Los usuarios de Skype empresarial online pueden comunicarse con usuarios de Skype empresarial desde una organización local si los usuarios tienen uno de los siguientes modos de actualización: Islas, SfBOnly, SfBWIthTeamsCollab, SfBWithTeamsCollabAndMeetings; y los usuarios de Skype empresarial online de la otra organización se encuentran en uno de los siguientes modos de actualización: Islas, SfBOnly, SfBWIthTeamsCollab, SfBWithTeamsCollabAndMeetings.<br><br>Active la opción los **usuarios pueden comunicarse con Skype empresarial y los usuarios de Teams** en acceso externo. A continuación, haga que el administrador de la organización de otros equipos realice las mismas acciones.|
|Permita que los **usuarios de Skype empresarial online** se comuniquen con **usuarios de Skype** (dentro o fuera de su organización).   |Activar los **usuarios de Skype empresarial pueden comunicarse con los usuarios de Skype** en acceso externo.|
|Permita que **los usuarios de Teams** de la organización se comuniquen con **los usuarios de equipos** de fuera de su organización. | Para obtener información sobre cómo funciona la versión gratuita de Teams con acceso externo, consulte [diferencias entre Microsoft Teams y Microsoft Teams](https://support.office.com/article/differences-between-microsoft-teams-and-microsoft-teams-free-0b69cf39-eb52-49af-b255-60d46fdf8a9c).|

> [!IMPORTANT]
> No es necesario agregar dominios de **Skype** como dominios permitidos para permitir que los usuarios de Teams o Skype empresarial online se comuniquen con usuarios de Skype dentro o fuera de su organización. Todos los **dominios de Skype** están en la lista blanca, lo que significa que todos estos dominios se consideran permitidos.



## <a name="how-does-external-access-compare-with-guest-access"></a>¿Cómo se compara el acceso externo con el acceso de invitado?

Para obtener más información sobre la diferencia entre el acceso externo y el acceso de invitados, lea [comunicarse con los usuarios de otras organizaciones](communicate-with-users-from-other-organizations.md).

## <a name="related-topics"></a>Temas relacionados

[Experiencia de chat nativa para usuarios externos (federados)](native-chat-for-external-users.md)