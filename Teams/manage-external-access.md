---
title: Administrar el acceso externo (Federación)
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: vinbel
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.externalaccess.overview
- seo-marvel-mar2020
description: El administrador de Teams o de TI puede configurar el acceso externo de otros dominios (federación) para permitir que los usuarios de esos dominios participen en Teams.
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 0aa8cd2ac27bac7bf5159512801670270791f903
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583869"
---
<a name="manage-external-access-in-microsoft-teams"></a>Administrar el acceso externo en Microsoft Teams
======================================================

El acceso externo es una forma para que los usuarios de los equipos de un dominio externo puedan buscar, llamar, chatear y configurar reuniones con usted en Teams. También puede usar el acceso externo para comunicarse con usuarios externos que siguen usando Skype empresarial (en línea y local) y Skype (en versión preliminar).

Si quiere que los usuarios externos tengan acceso a los equipos y canales, la opción de acceso de invitado puede ser la más aconsejable. Para obtener más información sobre las diferencias entre el acceso externo y el acceso de invitados, consulte [Comparación entre el acceso de invitado y el acceso externo](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access). 

Use el acceso externo si:
  
- Tiene usuarios de distintos dominios que necesitan colaborar. Por ejemplo, Rob@contoso.com y Ann@northwindtraders.com están trabajando en un proyecto junto con otros usuarios de los dominios contoso.com y northwindtraders.com.

- Quiere que las personas de su organización usen Teams para ponerse en contacto con empresas específicas ajenas a la organización.

- Quiere que cualquier persona del mundo que use Teams pueda encontrarle y ponerse en contacto con usted por medio su dirección de correo electrónico. 

> [!IMPORTANT]
> Actualmente, para poder federar en la aplicación Microsoft Teams un usuario externo ajeno a la organización que no sea un invitado de su Azure Active Directory (Azure AD) o inquilino, debe configurar correctamente un entorno híbrido y migrar a Skype Empresarial Online. Desde el 25 de febrero de 2019, Teams no admite la federación nativa si el usuario del perfil de SIP no está hospedado en Skype Empresarial Online. Para obtener más información sobre cómo configurar su cuenta para entornos híbridos y migrar después a Teams, consulte [Actualizar a Teams desde una implementación híbrida de Skype Empresarial](https://docs.microsoft.com/microsoftteams/upgrade-to-teams-execute-skypeforbusinesshybrid).

## <a name="plan-for-external-access"></a>Planificar el acceso externo

El acceso externo está activado en Teams de forma predeterminada, lo que significa que su organización puede comunicarse con todos los dominios externos. Si agrega dominios bloqueados, se permitirán todos los demás dominios. Si agrega dominios permitidos, se bloquearán todos los demás dominios. Hay tres escenarios en los que se configura el acceso externo en el Centro de administración de Microsoft Teams (**Configuración para toda la organización** > **Acceso externo**):

- **Federación abierta**: es la configuración predeterminada en Teams y facilita que los usuarios de la organización puedan hacer búsquedas, llamar, chatear y organizar reuniones con usuarios externos a la organización en cualquier dominio.

    En este escenario, los usuarios pueden comunicarse con todos los dominios externos que ejecuten Teams o Skype Empresarial y usen la federación abierta o hayan agregado el dominio a su lista de dominios permitidos.

- **Permitir dominios específicos**: al agregar dominios a una lista de dominios **permitidos**, solo se permite el acceso externo a los dominios permitidos. Una vez que se configura una lista de dominios permitidos, se bloquearán todos los demás dominios. Para permitir dominios específicos, haga clic en **Agregar un dominio**, agregue el nombre del dominio, haga clic en **Acción que se realizará en este dominio** y, después, seleccione **Permitido**.

- **Bloquear dominios específicos**: al agregar dominios a una lista de dominios **bloqueados**, se permite la comunicación con todos los dominios externos, *excepto* con aquellos que se han bloqueado. Para bloquear dominios específicos, haga clic en **Agregar un dominio**, agregue el nombre del dominio, haga clic en **Acción que se realizará en este dominio** y, después, seleccione **Bloqueado**. Una vez que haya configurado una lista de dominios bloqueados, se permitirán todos los demás dominios.

## <a name="allow-or-block-domains"></a>Permitir o bloquear dominios

### <a name="step-1---enable-your-organization-to-communicate-with-another-teams-organization"></a>Paso 1: Permitir que la organización se comunique con otra organización de Teams

![Icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png)  **Usar el Centro de administración de Microsoft Teams**

1. En el panel de navegación izquierdo, vaya a **Configuración para toda la organización** > **Acceso externo**.

2. Active la opción **Los usuarios pueden comunicarse con otros usuarios de Skype Empresarial y Teams**.

     ![Captura de pantalla que muestra activada la opción Los usuarios pueden comunicarse con otros usuarios de Skype Empresarial y Teams.](media/manage-external-access-2.png).

3. Si quiere que todas las organizaciones de Teams puedan comunicarse con los usuarios de su organización, vaya al paso 5.

4. Si quiere limitar las organizaciones que pueden comunicarse con los usuarios de su organización, puede permitir todos los dominios excepto algunos, o bien puede permitir únicamente dominios específicos. 

    - Para permitir todos los dominios excepto algunos, haga clic en **Agregar un dominio** para agregar los dominios que quiere bloquear. En el panel **Agregar un dominio**, escriba el nombre del dominio, haga clic en **Bloqueado** y, después, haga clic en **Listo**. 
    - Para permitir las comunicaciones únicamente con organizaciones específicas, agregue esos dominios a la lista con el estado **Permitido**. Una vez que haya agregado un dominio a la lista de permitidos, solo se permitirán las comunicaciones con aquellas organizaciones cuyos dominios estén en la lista de permitidos. 

5. Haga clic en **Guardar **.

6. Asegúrese de que el administrador de la otra organización de Teams complete los mismos pasos. Por ejemplo, si la otra organización limita las organizaciones que pueden comunicarse con sus usuarios, el administrador de esa organización debe incluir en su lista de **dominios permitidos** el dominio de la empresa a la que usted pertenece.

### <a name="step-2---test-it"></a>Paso 2: Probarlo

Para probar la configuración, necesitará un usuario de Teams que no se encuentre detrás del firewall. 
  
1. Una vez que tanto usted como el administrador de la otra organización hayan cambiado la configuración de **Acceso externo**, todo debería estar listo para empezar.

2. En la aplicación de Teams, busque a ese usuario por su dirección de correo electrónico y envíe una solicitud para chatear.

3. Pida a su contacto de Teams que le envíe una solicitud para chatear. Si no recibe la solicitud de su contacto, el problema está en la configuración del firewall (suponiendo que la otra organización ya ha confirmado que tienen una configuración de firewall correcta).

4. Otro modo de comprobar si el problema está en el firewall es ir a una ubicación wifi que no se encuentre detrás del firewall, como, por ejemplo, una cafetería, y enviar a través de Teams una solicitud al contacto para chatear. Si el mensaje se envía a través de la ubicación wifi, pero no sucede lo mismo cuando está en el trabajo, quiere decir que el problema está en el firewall.

> [!NOTE]
> Eso funcionará si usted y el otro usuario activan el acceso externo y permiten los respectivos dominios. Si eso no funciona, el otro usuario debería asegurarse de que la configuración de su organización no está bloqueando el dominio de la de usted.

## <a name="communicate-with-users-in-a-skype-for-business-online-organization"></a>Comunicarse con los usuarios de una organización de Skype Empresarial Online

Si va a configurar el acceso externo para que sus usuarios de Teams puedan buscar y ponerse en contacto con los usuarios de una organización de Skype Empresarial que limita quién puede comunicarse con sus usuarios, sigua los pasos para configurar el acceso externo desde su dominio al dominio de la otra organización. Después, pida al administrador de la otra organización que siga los pasos que se indican a continuación para configurar el acceso externo para Skype Empresarial Online.

Para obtener instrucciones específicas sobre los escenarios comunes de Skype Empresarial Online, vea [Escenarios comunes de acceso externo](#common-external-access-scenarios) a continuación.

![Icono que muestra el logotipo de Skype Empresarial](media/sfb-logo-30x30.png) **Usar el Centro de administración de Skype Empresarial**

Haga que el administrador de la otra organización siga los siguientes pasos:

1. En el Centro de administración de Microsoft 365, vaya a **Centros de administración** > **Teams y Skype** > **Portal heredado**.
  
2. En el **Centro de administración de Skype Empresarial**, seleccione **Organización** > **Comunicaciones externas**.

3. Para configurar la comunicación con empresas específicas o con usuarios de otros dominios, seleccione en el cuadro desplegable **Activado solo para dominios permitidos**.

    O bien, si desea habilitar la comunicación con todos aquellos que tengan directivas de Skype Empresarial abiertas, seleccione **Activado excepto para los dominios bloqueados**. Esta configuración es la predeterminada.

4. En **Dominios bloqueados o permitidos**, seleccione **+** y agregue el nombre del dominio que desea permitir.

## <a name="communicate-with-skype-users-in-preview"></a>Comunicarse con usuarios de Skype (en la versión preliminar)

Siga los pasos que se indican a continuación para que los usuarios de Teams de su organización puedan llamar a usuarios de Skype y chatear con ellos. Los usuarios de Teams pueden buscar usuarios de Skype y, a continuación, iniciar con ellos una conversación privada de solo texto o una llamada de audio o vídeo, y viceversa.

![Icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png)  **Usar el Centro de administración de Microsoft Teams**

1. En el panel de navegación izquierdo, vaya a **Configuración para toda la organización** > **Acceso externo**.

2. Active la opción **Los usuarios pueden comunicarse con usuarios de Skype**.

    ![Captura de pantalla que muestra activada la opción Los usuarios pueden comunicarse con usuarios de Skype](media/manage-external-access-5.png).

Para obtener más información sobre las formas en las que pueden comunicarse los usuarios de Teams y Skype, incluidas las limitaciones que se aplican, consulte [Interoperabilidad de Teams y Skype](teams-skype-interop.md).

## <a name="common-external-access-scenarios"></a>Escenarios comunes de acceso externo

|**Si desea...**  |**Haga lo siguiente**  |
|---------|-----------------------|
|Permitir que los usuarios de **Teams** de su organización se comuniquen con los **usuarios de Teams** de otra organización (externa).|En Acceso externo, agregue el dominio externo a la lista de permitidos o use la federación abierta. Después, haga que el administrador de la otra organización de Teams haga lo mismo.      |
|Permitir que los **usuarios de Teams** de su organización se comuniquen con **usuarios de Skype Empresarial Online** de la misma organización.  |Habilite el modo de coexistencia o elija el modo de actualización de aplicaciones aisladas para admitir usuarios de Skype Empresarial de su organización.   |
|Permitir que los **usuarios de Teams** de su organización se comuniquen con **usuarios de Skype Empresarial Online** de otra organización (externa).      |En Acceso externo, agregue el dominio externo a la lista de permitidos o use la federación abierta. <br><br>En Acceso externo, active la opción **Los usuarios pueden comunicarse con otros usuarios de Skype Empresarial y Teams**. Después, haga que el administrador de la otra organización de Teams haga lo mismo. <br><br>**NOTA**: El dominio externo con los usuarios de Skype Empresarial debe habilitar el modo de coexistencia o elegir el modo de actualización de aplicaciones aisladas para admitir usuarios de Skype Empresarial de esa organización.|
|Permitir que los **usuarios de Teams** de su organización se comuniquen con usuarios de **Skype**.<br> (en la versión preliminar)  |En Acceso externo, active la opción **Los usuarios pueden comunicarse con usuarios de Skype**. |
|Permita que los **usuarios de Skype empresarial online** se comuniquen con **los usuarios de Teams** en otro Microsoft 365 u Office 365.| Los usuarios de Skype Empresarial Online podrán comunicarse con los usuarios de Teams de otra organización si los primeros se encuentran en uno de los siguientes modos de actualización: aplicaciones aisladas, SfBOnly, SfBWIthTeamsCollab, SfBWithTeamsCollabAndMeetings; y los usuarios de Teams de la otra organización se encuentran en el modo TeamsOnly. <br><br>En Acceso externo, active la opción **Los usuarios pueden comunicarse con otros usuarios de Skype Empresarial y Teams**. Después, haga que el administrador de la otra organización de Teams haga lo mismo.|
|Permita que los **usuarios de Skype empresarial online** se comuniquen con **usuarios de Skype empresarial online** desde otro Microsoft 365 u Office 365.    | Los usuarios de Skype Empresarial Online podrán comunicarse con los usuarios de Skype Empresarial Online de otra organización si los primeros se encuentran en uno de los siguientes modos de actualización: aplicaciones aisladas, SfBOnly, SfBWIthTeamsCollab, SfBWithTeamsCollabAndMeetings; y los usuarios de Skype Empresarial Online de la otra organización se encuentran en los siguientes modos de actualización: aplicaciones aisladas, SfBOnly, SfBWIthTeamsCollab, SfBWithTeamsCollabAndMeetings.<br><br>En Acceso externo, active la opción **Los usuarios pueden comunicarse con otros usuarios de Skype Empresarial y Teams**. Después, haga que el administrador de la otra organización de Teams haga lo mismo.|
|Permitir que sus **usuarios de Skype Empresarial Online** se comuniquen con **usuarios de Skype Empresarial** de una organización local.     |Los usuarios de Skype Empresarial Online podrán comunicarse con los usuarios de Skype Empresarial de una organización local si los primeros se encuentran en uno de los siguientes modos de actualización: aplicaciones aisladas, SfBOnly, SfBWIthTeamsCollab, SfBWithTeamsCollabAndMeetings; y los usuarios de Skype Empresarial Online de la otra organización se encuentran en los siguientes modos de actualización: aplicaciones aisladas, SfBOnly, SfBWIthTeamsCollab, SfBWithTeamsCollabAndMeetings.<br><br>En Acceso externo, active la opción **Los usuarios pueden comunicarse con otros usuarios de Skype Empresarial y Teams**. Después, haga que el administrador de la otra organización de Teams haga lo mismo.|
|Permitir que sus **usuarios de Skype Empresarial Online** se comuniquen con **usuarios de Skype** (de dentro o de fuera de su organización).   |En Acceso externo, active la opción **Los usuarios pueden comunicarse con usuarios de Skype**.|

> [!IMPORTANT]
> No es necesario que agregue ningún **dominio de Skype** como dominio permitido para permitir que los usuarios de Teams o Skype Empresarial Online se comuniquen con usuarios de Skype de dentro o de fuera de su organización. Todos los **dominios de Skype** están en la lista blanca, lo que significa que todos ellos pueden considerarse como PERMITIDOS.

## <a name="how-does-external-access-compare-with-guest-access"></a>¿En qué se diferencia el acceso externo del acceso de invitados?

Para obtener más información sobre la diferencia entre el acceso externo y el acceso de invitados, lea [Comunicación con usuarios de otras organizaciones](communicate-with-users-from-other-organizations.md).

## <a name="related-topics"></a>Temas relacionados

- [Experiencia de chat nativa para usuarios externos (federados)](native-chat-for-external-users.md)
