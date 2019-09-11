---
title: Administrar el acceso externo (federación) en Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 07/12/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: vinbel
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.externalaccess.overview
description: Su administrador de ti puede configurar el acceso externo para otros dominios (Federación) para permitir que los usuarios de esos dominios participen en Teams.
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: dedda63d5ec97d914ba6bd1a70b7e5b3f1d9d7ee
ms.sourcegitcommit: dc151bf4454ddec20db5cd133a42a67599c08d64
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/11/2019
ms.locfileid: "36838117"
---
<a name="manage-external-access-in-microsoft-teams"></a>Administrar el acceso externo en Microsoft Teams
======================================================

Con el acceso externo de Microsoft Teams, los usuarios de Teams de otros dominios pueden participar en tus chats y llamadas. También puede permitir a otros usuarios externos que siguen usando Skype empresarial online, Skype empresarial local o incluso Skype a participar.

Siga los pasos de este artículo cuando:
  
- Tiene usuarios en diferentes dominios de su empresa: por ejemplo, Rob@contoso.com y Ann@northwindtraders.com.

- Quiere que las personas de su organización usen Teams para ponerse en contacto con personas de empresas específicas de fuera de su organización.

- Desea que cualquier persona del mundo que use Teams pueda encontrarse y ponerse en contacto con usted, usando su dirección de correo electrónico. Si usted y otro usuario habilitan el acceso externo y permiten los dominios de cada uno, esto funcionará. Si no funciona, el otro usuario debe asegurarse de que su configuración no esté bloqueando su dominio.

El acceso externo permite a los usuarios externos buscar, llamar y enviar mensajes instantáneos, así como configurar reuniones con usted. Sin embargo, si quiere que los usuarios externos tengan acceso a los equipos y los canales, el acceso de invitados puede ser una mejor manera de hacerlo. Para obtener más información sobre las diferencias entre el acceso externo y el acceso de invitados, vea acceso [externo frente a acceso de invitados](#external-access-vs-guest-access), a continuación. Para activar el acceso de invitados, consulte [activar el acceso de invitados](set-up-guests.md) para que los usuarios puedan comunicarse.

> [!IMPORTANT]
> En la actualidad, para federar dentro de la aplicación Microsoft Teams a un usuario externo fuera de su organización que no es actualmente invitado de su Azure Active Directory (Azure AD) o de inquilino, debe estar correctamente configurado para un híbrido y pasarse a Skype empresarial online. A partir de 2/25/2019, Teams no admite la Federación nativa sin que el usuario del perfil SIP se haya alojado en Skype empresarial online. Para obtener más información sobre cómo configurar su cuenta para una implementación híbrida y después a los equipos, consulte [actualizar la implementación híbrida de Skype empresarial a teams](https://docs.microsoft.com/en-us/microsoftteams/upgrade-to-teams-execute-skypeforbusinesshybrid).

> [!IMPORTANT]
> Los usuarios invitados siguen la configuración de toda la organización para el modo de coexistencia. Esto no se puede modificar.

## <a name="external-access-vs-guest-access"></a>Acceso externo frente a acceso de invitados

El acceso externo (Federación) y el acceso de invitados son diferentes:

- Acceso de invitado concede permiso de acceso a una persona. Acceso externo concede permiso de acceso a un dominio completo.

- El acceso de invitados, una vez otorgado por el propietario de un equipo, permite que un invitado [tenga acceso a recursos](guest-experience.md), como archivos y debates de canales, para un equipo específico y conversa con otros usuarios del equipo al que han sido invitados. Con el acceso externo (chat federado), los participantes del chat externo no tienen acceso a los equipos de la organización o a los recursos del equipo. Solo pueden participar en un chat federado. Los administradores de inquilinos pueden elegir entre las dos opciones de comunicación dependiendo del nivel de colaboración que sea deseable con la parte externa. Los administradores pueden elegir entre dos enfoques o ambos, según las necesidades de la organización, pero recomendamos habilitar el acceso de invitados para disfrutar de una experiencia de Teams más completa. 

Consulte la tabla siguiente para obtener una comparación de las características de acceso externo e invitado.

| Característica | Usuarios de acceso externo | Usuarios de acceso de invitado |
|---------|-----------------------|--------------------|
| El usuario puede chatear con alguien de otra empresa | Sí |Sí |
| El usuario puede llamar a alguien de otra empresa | Sí | Sí |
| El usuario puede ver si alguien de otra empresa está disponible para realizar llamadas o chats | Sí | Sí<sup>1</sup> |
| El usuario puede buscar usuarios en espacios empresariales externos | Sí<sup>2</sup> | No |
| El usuario puede compartir archivos | No | Sí |
| El usuario puede acceder a los recursos de Teams | No | Sí |
| Se puede Agregar un usuario a un chat grupal | No | Sí |
| Se puede Agregar un usuario a una reunión | Sí | Sí |
| Se pueden agregar usuarios adicionales a un chat con un usuario externo | No<sup>3</sup> | N/D |
| El usuario se identifica como una fiesta externa | Sí | Sí |
| Se muestra la presencia | Sí | Sí |
| Se muestra un mensaje de fuera de la oficina | No | Sí |
| Usuario individual puede bloquearse | No | Sí |
| @mentions son compatibles | No | Sí |
| Hacer llamadas privadas | Sí | Sí |
| Permitir video IP | Sí | Sí |
| Modo de uso compartido de pantalla | No | Sí |
| Permitir reunirse ahora | No | Sí |
| Editar mensajes enviados | No | Sí |
| Puede eliminar mensajes enviados | No | Sí |
| Usar Giphy en la conversación | No | Sí |
| Usar memes en una conversación | No | Sí |
| Usar adhesivos en la conversación | No | Sí |
||||

<sup>1</sup> siempre que el usuario se haya agregado como invitado y haya iniciado sesión como invitado para el inquilino invitado.<br>
<sup>2</sup> solo por correo electrónico o dirección de protocolo de inicio de sesión (SIP).<br>
<sup>3</sup> el chat externo (federado) solo es 1:1.

Para obtener más información sobre las características de invitado y la experiencia de invitado, vea [activar o desactivar el acceso de invitado a Microsoft Teams](https://docs.microsoft.com/microsoftteams/set-up-guests) y [Cómo es la experiencia de invitado](https://docs.microsoft.com/microsoftteams/guest-experience).

Para obtener más información sobre la versión gratuita de Teams y sobre cómo funciona con las características de acceso externo, consulte [diferencias entre Microsoft Teams y Microsoft Teams](https://support.office.com/article/differences-between-microsoft-teams-and-microsoft-teams-free-0b69cf39-eb52-49af-b255-60d46fdf8a9c?ui=en-US&rs=en-US&ad=US).

## <a name="quick-steps-for-scenarios"></a>Pasos rápidos para escenarios

|**Desea....**  |**Pasos rápidos**  |
|---------|-----------------------|
|Desea permitir que **los usuarios de Teams** de la organización se comuniquen con **los usuarios de Teams** en otra organización (externa).|En acceso externo, agregue el dominio externo a la lista de permitidos o use abrir Federación. <p>A continuación, haga lo mismo el administrador de la organización de otros equipos.      |
|Desea permitir que **los usuarios de Teams** de la organización se comuniquen con **usuarios de Skype empresarial online** en la misma organización.  |Habilite el modo de coexistencia o elija el modo de actualización de islas para admitir los usuarios de Skype empresarial de su organización.   |
|Desea permitir que **los usuarios de Teams** de la organización se comuniquen con **los usuarios de Skype empresarial online** en otra organización (externa).      |En acceso externo, agregue el dominio externo a la lista de permitidos o use abrir Federación.  <p>Activar **los usuarios pueden comunicarse con Skype empresarial y los usuarios de Teams** en acceso externo. <p>A continuación, haga lo mismo el administrador de la organización de otros equipos. <p>**Nota**: el dominio externo con usuarios de Skype empresarial debe habilitar el modo de coexistencia o elegir el modo de actualización de islas para admitir los usuarios de Skype empresarial de esa organización.|
|Desea permitir que **los usuarios de Teams** de la organización se comuniquen con usuarios de **Skype** desde dentro o fuera de su organización.   | No se admite un escenario en este momento. <p>**Importante**: los usuarios de Teams no podrán comunicarse con usuarios de Skype, pero los usuarios de Skype empresarial de su organización podrán comunicarse con usuarios de Skype dentro o fuera de su organización si se cumplen estos dos requisitos: <p>1) activar **los usuarios pueden comunicarse con los usuarios de Skype empresarial y de Teams** y los **usuarios de Skype empresarial pueden comunicarse con** la configuración de usuarios de Skype en acceso externo. <p> 2) su organización se ejecuta en modo de coexistencia. |
|Desea permitir que los **usuarios** de su equipo se comuniquen con **usuarios de Skype empresarial online** desde una organización local y con **usuarios de Skype**.   |En acceso externo, agregue el dominio externo a la lista de permitidos o use abrir Federación. . <p>Activar **los usuarios pueden comunicarse con Skype empresarial y los usuarios de Teams** en acceso externo. <p>Activar **Skype empresarial los usuarios pueden comunicarse con los usuarios de Skype** en acceso externo. <p> A continuación, haga lo mismo el administrador de la organización local.<p>**Importante** En este escenario, los usuarios de su equipo no podrán comunicarse con los usuarios de Skype, pero los usuarios de Skype empresarial de su organización podrán comunicarse con los usuarios de Skype dentro o fuera de su organización si activa la opción **para que los usuarios puedan comunicarse con Skype empresarial. y los usuarios de equipos** y los usuarios de **Skype empresarial pueden comunicarse con** la configuración de usuarios de Skype en acceso externo.|
|Desea permitir que los **usuarios de Skype empresarial online** se comuniquen con **los usuarios** de un equipo de otra organización de Office 365.|Habilite el modo de coexistencia o elija el modo de actualización de islas para admitir los usuarios de Skype empresarial de su organización. <p>En acceso externo, agregue el dominio externo a la lista de permitidos o use abrir Federación.  <p> Activar **los usuarios pueden comunicarse con Skype empresarial y los usuarios de Teams** en acceso externo. <p>A continuación, haga que el administrador de la organización de otros equipos realice las mismas acciones. |
|Desea permitir que los **usuarios de Skype empresarial online** se comuniquen con los **usuarios de Skype empresarial online** de otra organización de Office 365.    | Habilite el modo de coexistencia o elija el modo de actualización de islas para admitir los usuarios de Skype empresarial de su organización. <p>En acceso externo, agregue el dominio externo a la lista de permitidos o use abrir Federación. <p> Activar **los usuarios pueden comunicarse con Skype empresarial y los usuarios de Teams** en acceso externo.<p>A continuación, el administrador de la organización de otros equipos realiza todas las mismas acciones. |
|Desea permitir que los **usuarios de Skype empresarial online** se comuniquen con los **usuarios de Skype empresarial online** desde una organización local.     |Habilite el modo de coexistencia o elija el modo de actualización de islas para admitir los usuarios de Skype empresarial de su organización. <p>En acceso externo, agregue el dominio externo a la lista de permitidos o use abrir Federación.  <p>Activar **los usuarios pueden comunicarse con Skype empresarial y los usuarios de Teams** en acceso externo.  <p> Luego, hacer que el administrador de la organización local realice las mismas acciones. |
|Desea permitir que los **usuarios de Skype empresarial online** se comuniquen con **los usuarios de Skype** (dentro o fuera de su organización).   |Habilite el modo de coexistencia o elija el modo de actualización de islas para admitir los usuarios de Skype empresarial de su organización. <p>Activar los **usuarios de Skype empresarial pueden comunicarse con los usuarios de Skype** en acceso externo.         |
|Desea permitir que los **usuarios de Skype empresarial online** se comuniquen con **usuarios de Skype empresarial online** de otra organización y **usuarios de Skype** de dentro o fuera de su organización.    |Habilite el modo de coexistencia o elija el modo de actualización de islas para admitir los usuarios de Skype empresarial de su organización. <p>En acceso externo, agregue el dominio externo a la lista de permitidos o use abrir Federación.  <p> Activar **los usuarios pueden comunicarse con los usuarios de Skype empresarial y Teams** y los **usuarios de Skype empresarial pueden comunicarse con los** usuarios de Skype en acceso externo. <p>A continuación, haga que el administrador de la organización de otros equipos realice las mismas acciones.       <p> **Nota**: el administrador del otro dominio externo no tiene que activar **Skype empresarial los usuarios pueden comunicarse con los usuarios de Skype** en acceso externo.|

> [!IMPORTANT]
> No tiene que agregar ningún **"dominio de Skype"** como dominios permitidos para permitir que los usuarios de Teams o Skype empresarial online se comuniquen con usuarios de Skype dentro o fuera de su organización. Todos los **dominios de Skype** se muestran en la lista, lo que significa que se consideran permitidos todos estos dominios.

## <a name="let-your-teams-users-chat-and-communicate-with-users-in-another-organization"></a>Permitir a los usuarios de su equipo conversar y comunicarse con los usuarios de otra organización

El acceso externo permite a los usuarios de Skype empresarial comunicarse con otros usuarios ajenos a su organización. De forma predeterminada, su organización puede comunicarse con todos los dominios externos. Si agrega dominios bloqueados, todos los demás dominios estarán permitidos, pero si agrega dominios permitidos, todos los demás dominios se bloquearán. Puede configurar fácilmente el acceso externo para su organización. Hay tres escenarios para configurarlo:

- **Escenario 1** : puede usar la **Federación abierta**. Esta es la configuración predeterminada y permite a los usuarios de la organización buscar, llamar y enviar mensajes instantáneos y chats, así como configurar reuniones con personas externas a su organización.

    Cuando use esta configuración, los usuarios podrán comunicarse con todos los dominios externos que ejecutan Teams o Skype empresarial y están usando la Federación abierta o han agregado su dominio a la lista de permitidos.

- **Escenario 2** : puede Agregar un dominio o dominios a la lista de **permitidos** . Para ello, haga clic en **Agregar un dominio**, agregue el nombre de dominio, haga clic en **acción para realizar en este dominio**y, a continuación, seleccione **permitido**. Es importante saber que, si lo haces, **bloqueará** el resto de los dominios.

- **Escenario 3** : puede Agregar un dominio o dominios a la lista de **bloqueados** . Para ello, haga clic en **Agregar un dominio**, agregue el nombre de dominio, haga clic en **acción para realizar en este dominio**y, a continuación, seleccione **bloqueado**. Es importante saber que si lo haces, **permitirás** el resto de los dominios.

Siga estos pasos para permitir o bloquear dominios.

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

## <a name="communicate-with-users-in-a-skype-for-business-online-organization"></a>Comunicarse con los usuarios en una organización de Skype empresarial online

Si está configurando un acceso externo para permitir que los usuarios de su equipo encuentren y se pongan en contacto con usuarios que están en una organización de Skype empresarial y que limitan quién puede comunicarse con sus usuarios, siga los pasos para configurar el acceso externo desde su dominio al dominio de la otra organización. Después, solicite al administrador de la otra organización que siga los pasos a continuación para configurar el acceso externo para Skype empresarial online.

![Un icono que muestra el logotipo](media/sfb-logo-30x30.png) de Skype empresarial **con el centro de administración de Skype empresarial**

Haga que el administrador de la organización Realice estos pasos:

1. En el centro de administración de Microsoft 365, vaya a los **centros** > de administración**Teams &** > **portal heredado**de Skype.
  
2. En el **centro de administración de Skype empresarial**, elija**comunicaciones externas**de la **organización** > .

3. Para configurar la comunicación con una empresa específica o con usuarios de otro dominio, en el cuadro desplegable, elija **activado solo para los dominios permitidos**.

    O, si desea permitir la comunicación con cualquier persona del mundo que tenga abiertas las directivas de Skype empresarial, elija **activado excepto para los dominios bloqueados**. Esta es la configuración que se aplica normalmente.

4. En **dominios bloqueados o permitidos**, elija **+** y, a continuación, agregue el nombre del dominio que desea permitir.

## <a name="related-topics"></a>Temas relacionados

Para obtener información sobre el acceso de invitados en Microsoft Teams, consulte [administrar el acceso de invitado en Microsoft Teams](manage-guests.md).
