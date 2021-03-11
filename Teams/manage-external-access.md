---
title: Administrar el acceso externo (federación)
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
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
localization_priority: Priority
ms.openlocfilehash: c41b051f7c11d27417885c9ada22d9337d50dfdb
ms.sourcegitcommit: c477aa1a7da0b6b9bea1f5d10f1395eef418bfdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/10/2021
ms.locfileid: "50711777"
---
# <a name="manage-external-access-in-microsoft-teams"></a>Administrar el acceso externo en Microsoft Teams

El acceso externo facilita que los usuarios externos de Teams de todo un dominio puedan hacer búsquedas, llamar, chatear y organizar reuniones con usted en Teams. También puede usar el acceso externo para comunicarse con los usuarios externos que todavía usen Skype Empresarial (en línea o local) o Skype (en la versión preliminar).

Si desea que personas de otras organizaciones tengan acceso a los equipos y canales, el acceso de invitados podría ser la mejor forma de lograrlo. Para obtener más información sobre las diferencias entre el acceso externo y el acceso de invitados, consulte [Comparación entre el acceso de invitado y el acceso externo](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access). 

Use el acceso externo si:
  
- Tiene usuarios de distintos dominios que necesitan colaborar. Por ejemplo, Rob@contoso.com y Ann@northwindtraders.com están trabajando en un proyecto junto con otros usuarios de los dominios contoso.com y northwindtraders.com.

- Quiere que las personas de su organización usen Teams para ponerse en contacto con empresas específicas ajenas a la organización.

- Quiere que cualquier persona del mundo que use Teams pueda encontrarle y ponerse en contacto con usted por medio su dirección de correo electrónico. 

> [!IMPORTANT]
> Para comunicarse con un usuario externo usando el cliente de Teams (tanto si ese usuario usa Teams como Skype Empresarial), el usuario de Teams debe estar alojado en Skype Empresarial Online.

## <a name="plan-for-external-access"></a>Planificar el acceso externo

El acceso externo está activado en Teams de forma predeterminada, lo que significa que su organización puede comunicarse con todos los dominios externos. Si agrega dominios bloqueados, se permitirán todos los demás dominios. Si agrega dominios permitidos, se bloquearán todos los demás dominios. La excepción a esta regla es que se permitan participantes anónimos en las reuniones. Hay tres escenarios para configurar el acceso externo en el Centro de administración de Teams (**Configuración de toda la organización** > **Acceso externo**):

> [!NOTE]
> Si desactiva el acceso externo en su organización, los usuarios externos aún podrán unirse a las reuniones mediante la participación anónima. Para más información, consulte [Administrar la configuración de las reuniones en Teams](https://docs.microsoft.com/microsoftteams/meeting-settings-in-teams).

- **Federación abierta**: es la configuración predeterminada en Teams y facilita que los usuarios de la organización puedan hacer búsquedas, llamar, chatear y organizar reuniones con usuarios externos a la organización en cualquier dominio.

    En este escenario, los usuarios pueden comunicarse con todos los dominios externos que ejecuten Teams o Skype Empresarial y usen la federación abierta o hayan agregado el dominio a su lista de dominios permitidos.

- **Permitir dominios específicos**: al agregar dominios a una lista de dominios **permitidos**, solo se permite el acceso externo a los dominios permitidos. Una vez que se configura una lista de dominios permitidos, se bloquearán todos los demás dominios. Para permitir dominios específicos, haga clic en **Agregar un dominio**, agregue el nombre del dominio, haga clic en **Acción que se realizará en este dominio** y, después, seleccione **Permitido**.

- **Bloquear dominios específicos**: al agregar dominios a una lista de dominios **bloqueados**, se permite la comunicación con todos los dominios externos, *excepto* con aquellos que se han bloqueado. Para bloquear dominios específicos, haga clic en **Agregar un dominio**, agregue el nombre del dominio, haga clic en **Acción que se realizará en este dominio** y, después, seleccione **Bloqueado**. Una vez que haya configurado una lista de dominios bloqueados, se permitirán todos los demás dominios.

> [!NOTE]
> Los dominios permitidos o bloqueados solo se aplican a las reuniones si el acceso anónimo a las reuniones está "desactivado".

## <a name="allow-or-block-domains"></a>Permitir o bloquear dominios

### <a name="step-1---enable-your-organization-to-communicate-with-another-teams-or-skype-for-business-organizations"></a>Paso 1: Permitir que su organización se comunique con otras organizaciones con Teams o con Skype Empresarial

![Icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png)  **Usar el Centro de administración de Microsoft Teams**

1. En el panel de navegación izquierdo, vaya a **Configuración para toda la organización** > **Acceso externo**.

2. Active la opción **Los usuarios pueden comunicarse con otros usuarios de Skype Empresarial y Teams**.

     ![Captura de pantalla que muestra activada la opción Los usuarios pueden comunicarse con otros usuarios de Skype Empresarial y Teams.](media/manage-external-access-2.png).

3. Si quiere que todas las organizaciones de Teams puedan comunicarse con los usuarios de su organización, vaya al paso 5.

4. Si quiere limitar las organizaciones que pueden comunicarse con los usuarios de su organización, puede permitir todos los dominios excepto algunos, o bien puede permitir únicamente dominios específicos. 

    - Para permitir todos los dominios excepto algunos, haga clic en **Agregar un dominio** para agregar los dominios que quiere bloquear. En el panel **Agregar un dominio**, escriba el nombre del dominio, haga clic en **Bloqueado** y, después, haga clic en **Listo**. 
    - Para permitir las comunicaciones únicamente con organizaciones específicas, agregue esos dominios a la lista con el estado **Permitido**. Una vez que haya agregado un dominio a la lista de permitidos, solo se permitirán las comunicaciones con aquellas organizaciones cuyos dominios estén en la lista de permitidos. 

5. Haga clic en **Guardar**.

6. Asegúrese de que el administrador de la otra organización de Teams complete los mismos pasos. Por ejemplo, si la otra organización limita las organizaciones que pueden comunicarse con sus usuarios, el administrador de esa organización debe incluir en su lista de **dominios permitidos** el dominio de la empresa a la que usted pertenece.

### <a name="step-2---test-it"></a>Paso 2: Probarlo

Para probar la configuración, necesitará un usuario de Teams que no se encuentre detrás del firewall. 
  
1. Una vez que tanto usted como el administrador de la otra organización hayan cambiado la configuración de **Acceso externo**, todo debería estar listo para empezar.

2. En la aplicación de Teams, busque a ese usuario por su dirección de correo electrónico y envíe una solicitud para chatear.

3. Pida a su contacto de Teams que le envíe una solicitud para chatear. Si no recibe la solicitud de su contacto, el problema está en la configuración del firewall (suponiendo que la otra organización ya ha confirmado que tienen una configuración de firewall correcta).

4. Otro modo de comprobar si el problema está en el firewall es ir a una ubicación wifi que no se encuentre detrás del firewall, como, por ejemplo, una cafetería, y enviar a través de Teams una solicitud al contacto para chatear. Si el mensaje se envía a través de la ubicación wifi, pero no sucede lo mismo cuando está en el trabajo, quiere decir que el problema está en el firewall.

> [!NOTE]
> Eso funcionará si usted y el otro usuario activan el acceso externo y permiten los respectivos dominios. Si eso no funciona, el otro usuario debería asegurarse de que la configuración de su organización no está bloqueando el dominio de la de usted.


## <a name="communicate-with-skype-users-in-preview"></a>Comunicarse con usuarios de Skype (en la versión preliminar)

Siga los pasos que se indican a continuación para que los usuarios de Teams de su organización puedan llamar a usuarios de Skype y chatear con ellos. Los usuarios de Teams pueden buscar usuarios de Skype y, a continuación, iniciar con ellos una conversación privada de solo texto o una llamada de audio o vídeo, y viceversa.

![Icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png)  **Usar el Centro de administración de Microsoft Teams**

1. En el panel de navegación izquierdo, vaya a **Configuración para toda la organización** > **Acceso externo**.

2. Active la opción **Los usuarios pueden comunicarse con usuarios de Skype**.

    ![Captura de pantalla que muestra activada la opción Los usuarios pueden comunicarse con usuarios de Skype](media/manage-external-access-5.png).

Para obtener más información sobre las formas en las que pueden comunicarse los usuarios de Teams y Skype, incluidas las limitaciones que se aplican, consulte [Interoperabilidad de Teams y Skype](teams-skype-interop.md).

## <a name="common-external-access-scenarios"></a>Escenarios comunes de acceso externo

En las siguientes secciones se describe cómo habilitar la federación para escenarios de acceso externo comunes y cómo TeamsUpgradePolicy determina la entrega de llamadas y chats entrantes.

### <a name="enable-federation"></a>Habilitar la federación:

Para permitir que los usuarios de la organización se comuniquen con usuarios de otra organización, ambas organizaciones deben habilitar la federación. Los pasos para habilitar la federación para una organización determinada dependen de si la organización está exclusivamente en línea, es híbrida o si es exclusivamente local.

|**Si su organización es** |**Habilitar la federación como se muestra a continuación**  |
|:---------|:-----------------------|
|En línea sin Skype Empresarial local. Esto incluye a las organizaciones que tienen usuarios de TeamsOnly o usuarios de Skype Empresarial Online.| Si usa el Centro de administración de Teams: <br>- En Acceso externo, active la opción **Los usuarios pueden comunicarse con otros usuarios de Skype Empresarial y Teams**.<br>- Si no usa una federación abierta (la cual permite federación con cualquier otro dominio), entonces agregue el dominio externo a la lista de Permitidos.<br><br>Con PowerShell:<br>- Asegúrese de que la cuenta empresarial esté habilitada para la federación: `Get-CsTenantFederationConfiguration` debe mostrar `AllowFederatedUsers=true`. <br>- Asegúrese de que el valor vigente del usuario de `CsExternalAccessPolicy` tenga `EnableFederationAccess=true`.<br>- Si no usa una federación abierta, asegúrese de que el dominio de destino se muestre en `AllowedDomains` de `CsTenantFederationConfiguration`. |
|Exclusivamente local | En las herramientas locales: <br>- Asegúrese de que la federación esté habilitada en `CsAccessEdgeConfiguration`.<br>- Asegúrese de que la federación para el usuario esté habilitada a través de `ExternalAccessPolicy` (ya sea por la directiva global, la directiva del sitio o la directiva asignada por el usuario). <br> - Si no usa una federación abierta, asegúrese de que el dominio de destino se muestre en `AllowedDomains`. |
|Híbrido con algunos usuarios en línea (en Skype Empresarial o Teams) y algunos usuarios locales. | Siga los pasos anteriores para organizaciones en línea y locales. |

### <a name="delivery-of-incoming-chats-and-calls"></a>Entrega de chats y llamadas entrantes 

Los chats y las llamadas entrantes de una organización de la federación llegarán al cliente de Teams o de Skype Empresarial del usuario en función del modo del usuario destinatario en TeamsUpgradePolicy.

|**Si quiere** |**Haga esto:**  |
|:---------|:-----------------------|
| Asegúrese de que las llamadas y los chats federados entrantes lleguen al cliente de Teams del usuario: | Configure los usuarios para que sean TeamsOnly.
| Asegúrese de que los chats federados entrantes y las llamadas lleguen al cliente de Skype Empresarial del usuario | Configure a los usuarios para que se estén en cualquier modo distinto de TeamsOnly. |


### <a name="enable-federation-between-users-in-your-organization-and-consumer-users-of-skype"></a>Habilitar la federación entre los usuarios de su organización y los usuarios consumidores de Skype

Para habilitar la federación entre los usuarios de su organización y los usuarios consumidores de Skype:

|**Si su organización es** |**Habilitar la federación de consumidores como se muestra a continuación**  |
|:---------|:-----------------------|
| Exclusivamente en línea sin Skype Empresarial local.  Esto incluye a las organizaciones que tienen usuarios de TeamsOnly o usuarios de Skype Empresarial Online. | Si usa el Centro de administración de Teams: <br>- Asegúrese de que la opción **Los usuarios se pueden comunicar con usuarios de Skype** esté habilitada en Acceso externo.<br><br>Con PowerShell: <br>- Asegúrese de que la cuenta empresarial esté habilitada para la federación: `Get-CsTenantFederationConfiguration` debe mostrar `AllowPublicUsers=true`. <br> - Asegúrese de que el valor vigente del usuario de `CsExternalAccessPolicy` tenga `EnablePublicCloudAccess=true`. |
| Exclusivamente local | En las herramientas locales: <br> - Asegúrese de que Skype está habilitado como asociado federado. <br> - Asegúrese de `EnablePublicCloudAccess=true` para el usuario a través de `ExternalAccessPolicy` (ya sea mediante la directiva global, la directiva del sitio o la directiva asignada por el usuario).|
| Híbrido con algunos usuarios en línea (en Skype Empresarial o Teams) y algunos usuarios locales.| Siga los pasos anteriores para organizaciones en línea y locales.


> [!IMPORTANT]
> No es necesario que agregue ningún **dominio de Skype** como dominio permitido para permitir que los usuarios de Teams o Skype Empresarial Online se comuniquen con usuarios de Skype de dentro o de fuera de su organización. Todos los **dominios de Skype** están permitidos.

## <a name="how-does-external-access-compare-with-guest-access"></a>¿En qué se diferencia el acceso externo del acceso de invitados?

Para obtener más información sobre la diferencia entre el acceso externo y el acceso de invitados, lea [Comunicación con usuarios de otras organizaciones](communicate-with-users-from-other-organizations.md).

## <a name="related-topics"></a>Temas relacionados

- [Experiencia de chat nativa para usuarios externos (federados)](native-chat-for-external-users.md)
