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
description: Su administrador de Teams o de TI puede configurar el acceso externo para otros dominios (federación) para permitir que los usuarios de esos dominios encuentren, llamen, chateen y configuren reuniones con los usuarios.
appliesto:
- Microsoft Teams
ms.localizationpriority: high
ms.openlocfilehash: 5a52e479b7dd813af786c33e494675fe7b8e9743
ms.sourcegitcommit: a969502c0a5237caf041d7726f4f1edefdd75b44
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2022
ms.locfileid: "61766613"
---
# <a name="manage-external-access-in-microsoft-teams"></a>Administrar el acceso externo en Microsoft Teams

El acceso externo facilita que los usuarios de Teams de fuera de su organización puedan encontrar, llamar, chatear y organizar reuniones con usted en Teams. También puede usar el acceso externo para comunicarse con los usuarios externos que todavía usen Skype Empresarial (en línea o local) o Skype (en la versión preliminar).

Si desea que personas de otras organizaciones tengan acceso a los equipos y canales, es mejor utilizar el acceso de invitados. Para obtener más información sobre las diferencias entre el acceso externo y el acceso de invitados, consulte [Comparación entre el acceso de invitado y el acceso externo](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access). 

Use el acceso externo si:
  
- Tiene usuarios de dominios externos que necesitan colaborar. Por ejemplo, Rob@contoso.com y Ann@northwindtraders.com están trabajando en un proyecto junto con otros usuarios de los dominios contoso.com y northwindtraders.com.

- Quiere que las personas de su organización usen Teams para ponerse en contacto con empresas específicas ajenas a la organización.

- Quiere que cualquier persona del mundo que use Teams pueda encontrarle y ponerse en contacto con usted por medio su dirección de correo electrónico. 

## <a name="plan-for-external-access"></a>Planificar el acceso externo

El acceso externo está activado en Teams de forma predeterminada, lo que significa que su organización puede comunicarse con todos los dominios externos. Si agrega dominios bloqueados, se permitirán todos los demás dominios. Si agrega dominios permitidos, se bloquearán todos los demás dominios. La excepción a esta regla es que se permitan participantes anónimos en las reuniones. Hay tres escenarios para configurar el acceso externo en el Centro de administración de Teams (**Usuarios** > **Acceso externo**):

> [!NOTE]
> Los usuarios de Teams puede añadir aplicaciones cuando organizan reuniones o chats con personas de otras organizaciones. También pueden usar aplicaciones compartidas con personas de otras organizaciones cuando organizan reuniones o chats con estas organizaciones. Se aplican las directivas de datos de la organización del usuario anfitrión, así como las prácticas de intercambio de datos de cualquier aplicación de terceros compartida por la organización del usuario.

> [!NOTE]
> Si desactiva el acceso externo en su organización, los usuarios externos aún podrán unirse a las reuniones mediante la participación anónima. Para más información, consulte [Administrar la configuración de las reuniones en Teams](meeting-settings-in-teams.md).

- **Permitir todos los dominios externos**: es la configuración predeterminada en Teams y facilita que los usuarios de la organización puedan hacer búsquedas, llamar, chatear y organizar reuniones con usuarios externos a la organización en cualquier dominio.

    En este escenario, los usuarios pueden comunicarse con todos los dominios externos que ejecutan Teams o Skype Empresarial o permiten todos los dominios externos o han agregado su dominio a su lista de permitidos.

- **Permitir solo dominios externos específicos**: al agregar dominios a una lista de dominios **permitidos**, solo se autoriza el acceso externo a los dominios permitidos. Una vez que se configura una lista de dominios permitidos, se bloquearán todos los demás dominios. Para permitir dominios específicos, haga clic en **Agregar un dominio**, agregue el nombre del dominio, haga clic en **Acción que se realizará en este dominio** y, después, seleccione **Permitido**.

- **Bloquear dominios específicos**: al agregar dominios a una lista de dominios **bloqueados**, se permite la comunicación con todos los dominios externos, *excepto* con aquellos que se han bloqueado. Para bloquear dominios específicos, haga clic en **Agregar un dominio**, agregue el nombre del dominio, haga clic en **Acción que se realizará en este dominio** y, después, seleccione **Bloqueado**. Una vez que haya configurado una lista de dominios bloqueados, se permitirán todos los demás dominios.

- **Bloquear todos los dominios externos**: impide que los usuarios de su organización encuentren, llamen, chateen y configuren reuniones con personas externas a su organización en cualquier dominio.

> [!NOTE]
> Los dominios permitidos o bloqueados solo se aplican a las reuniones si el acceso anónimo a las reuniones está "desactivado".

## <a name="allow-or-block-domains"></a>Permitir o bloquear dominios

  **Usar el Centro de administración de Microsoft Teams**

Para permitir dominios específicos

1. En el Centro de administración de Teams, vaya a **Usuarios** > **Acceso externo**.

2. En **Elegir a qué dominios tienen acceso los usuarios**, elija **Permitir solo dominios externos específicos**.

3. Seleccione **Permitir dominios**.

4. En el cuadro **Dominio,** escriba el dominio que desea permitir y, a continuación, haga clic en **Listo**.

5. Si desea permitir otro dominio, haga clic en **Agregar un dominio**.

6. Haga clic en **Guardar**.

Para bloquear dominios específicos

1. En el Centro de administración de Teams, vaya a **Usuarios** > **Acceso externo**.

2. En **Elegir a qué dominios tienen acceso los usuarios**, elija **Bloquear solo dominios externos específicos**.

3. Seleccione **Bloquear dominios**.

4. En el cuadro **Dominio,** escriba el dominio que desea permitir y, a continuación, haga clic en **Listo**.

5. Si desea bloquear otro dominio, haga clic en **Agregar un dominio**.

6. Haga clic en **Guardar**.

Asegúrese de que el administrador de la otra organización de Teams complete estos mismos pasos. Por ejemplo, si la otra organización limita las organizaciones que pueden comunicarse con sus usuarios, el administrador de esa organización debe incluir en su lista de **dominios permitidos** el dominio de la empresa a la que usted pertenece.

## <a name="communicate-with-skype-users-preview"></a>Comunicarse con usuarios de Skype (versión preliminar)

Siga los pasos que se indican a continuación para que los usuarios de Teams de su organización puedan llamar a usuarios de Skype y chatear con ellos. Los usuarios de Teams pueden buscar usuarios de Skype y, a continuación, iniciar con ellos una conversación privada de solo texto o una llamada de audio o vídeo, y viceversa.

  **Usar el Centro de administración de Microsoft Teams**

1. En el panel de navegación izquierdo, vaya a **Usuarios** > **Acceso externo**.

2. Active la configuración **Permitir que los usuarios de mi organización se comuniquen con usuarios de Skype**.

Para obtener más información sobre las formas en las que pueden comunicarse los usuarios de Teams y Skype, incluidas las limitaciones que se aplican, consulte [Interoperabilidad de Teams y Skype](teams-skype-interop.md).

## <a name="block-unsolicited-contact-with-external-unmanaged-teams-users"></a>Bloquear el contacto no solicitado con usuarios externos de Teams no administrados

Siga estos pasos para evitar que los usuarios de Teams de su organización entren en contacto no solicitado con usuarios externos de Teams cuyas cuentas no estén administradas por una organización.

  **Usar el Centro de administración de Microsoft Teams**

1. En el panel de navegación izquierdo, vaya a **Usuarios** > **Acceso externo**.

2. Siga uno de estos pasos:

    - Para impedir que los usuarios de Teams de su organización se comuniquen con usuarios externos de Teams cuyas cuentas no están administradas por una organización, desactive la configuración **Los usuarios de mi organización pueden comunicarse con usuarios de Teams cuyas cuentas no estén administradas por una organización** y desactive la casilla **Los usuarios externos con cuentas de Teams no administradas por una organización pueden ponerse en contacto con usuarios de mi organización**.

    - Para permitir que los usuarios de Teams de su organización se comuniquen con usuarios externos de Teams cuyas cuentas no están administradas por una organización si sus usuarios de Teams han iniciado el contacto, active la configuración **Los usuarios de mi organización pueden comunicarse con usuarios de Teams cuyas cuentas no estén administradas por una organización** y desactive la casilla **Los usuarios externos con cuentas de Teams no administradas por una organización pueden ponerse en contacto con usuarios de mi organización**.

    - Para permitir que los usuarios de Teams de su organización se comuniquen con usuarios externos de Teams cuyas cuentas no estén administradas por una organización y reciban solicitudes para comunicarse con esos usuarios externos de Teams, active la configuración **Los usuarios de mi organización pueden comunicarse con usuarios de Teams cuyas cuentas no estén administradas por una organización** y seleccione la casilla **Los usuarios externos con cuentas de Teams no administradas por una organización pueden ponerse en contacto con los usuarios en mi organización**.

## <a name="test-access"></a>Probar el acceso

Para probar la configuración, necesitará un usuario de Teams que no se encuentre detrás del firewall. 
  
1. Una vez que tanto usted como el administrador de la otra organización hayan cambiado la configuración de **Acceso externo**, todo debería estar listo para empezar.

2. En la aplicación de Teams, busque a ese usuario por su dirección de correo electrónico y envíe una solicitud para chatear.

3. Pida a su contacto de Teams que le envíe una solicitud para chatear. Si no recibe la solicitud, quiere decir que el problema se encuentra en la configuración de su firewall (siempre que haya confirmado que la configuración de su firewall es correcta).

4. Otro método para comprobar si el problema es del firewall consiste en ir a un lugar que tenga una conexión WiFi que no esté bloqueada por este, como una cafetería, y utilizar Teams para enviar una solicitud para chatear a su contrato. Si el mensaje se envía a través de la ubicación WIFI, pero no sucede lo mismo cuando está en el trabajo, quiere decir que el problema está en el firewall.

> [!NOTE]
> Eso funcionará si usted y el otro usuario activan el acceso externo y permiten los respectivos dominios. Si eso no funciona, el otro usuario debería asegurarse de que la configuración de su organización no está bloqueando el dominio de la de usted.

## <a name="limit-external-access-to-specific-people"></a>Limitar el acceso externo a personas específicas

Si ha habilitado **los usuarios de mi organización pueden comunicarse con usuarios de Teams cuyas cuentas no están administradas por una organización**, puede limitar el acceso externo a personas específicas mediante PowerShell.

Puede usar el script de ejemplo siguiente, sustituyendo *policyName* por el nombre que desea asignar a la directiva y *userName* por cada usuario que desee que pueda usar el acceso externo.

Asegúrese de que ha instalado el [módulo Microsoft Teams PowerShell](/microsoftteams/teams-powershell-install) antes de ejecutar el script.

```PowerShell
Connect-MicrosoftTeams

# Disable external access globally
Set-CsExternalAccessPolicy -EnableTeamsConsumerAccess $false

# Create a new external access policy
New-CsExternalAccessPolicy -Identity <PolicyName> -EnableTeamsConsumerAccess $true

# Assign users to the policy
$users_ids = @("<UserName1>", "<UserName2>")
New-CsBatchPolicyAssignmentOperation -PolicyType ExternalAccessPolicy -PolicyName "<PolicyName>" -Identity $users_ids

```

Por ejemplo:

```PowerShell
Connect-MicrosoftTeams

Set-CsExternalAccessPolicy -EnableTeamsConsumerAccess $false

New-CsExternalAccessPolicy -Identity ContosoExternalAccess -EnableTeamsConsumerAccess $true

$users_ids = @("MeganB@contoso.com", "AlexW@contoso.com")
New-CsBatchPolicyAssignmentOperation -PolicyType ExternalAccessPolicy -PolicyName "ContosoExternalAccess" -Identity $users_ids

```

Vea [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) para obtener ejemplos adicionales de cómo compilar una lista de usuarios.

Puede ver la nueva directiva ejecutando `Get-CsExternalAccessPolicy`.


Vea también [New-CsExternalAccessPolicy](/powershell/module/skype/new-csexternalaccesspolicy) y [Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy).

## <a name="common-external-access-scenarios"></a>Escenarios comunes de acceso externo

En las siguientes secciones se describe cómo habilitar la federación para escenarios de acceso externo comunes y cómo TeamsUpgradePolicy determina la entrega de llamadas y chats entrantes.

### <a name="enable-federation"></a>Habilitar la federación:

Para permitir que los usuarios de la organización se comuniquen con usuarios de otra organización, ambas organizaciones deben habilitar la federación. Los pasos para habilitar la federación para una organización determinada dependen de si la organización está exclusivamente en línea, es híbrida o si es exclusivamente local.

| Si su organización es | Habilitar la federación como se muestra a continuación |
|:---------|:-----------------------|
|En línea sin Skype Empresarial local. Esto incluye a las organizaciones que tienen usuarios de TeamsOnly o usuarios de Skype Empresarial Online.| Si usa el Centro de administración de Teams: <br>- Asegúrese de que los dominios con los que desea comunicarse estén permitidos en Acceso externo.<br><br>Con PowerShell:<br>- Asegúrese de que la cuenta empresarial esté habilitada para la federación: `Get-CsTenantFederationConfiguration` debe mostrar `AllowFederatedUsers=true`. <br>- Asegúrese de que el valor vigente del usuario de `CsExternalAccessPolicy` tenga `EnableFederationAccess=true`.<br>- Si no usa una federación abierta, asegúrese de que el dominio de destino se muestre en `AllowedDomains` de `CsTenantFederationConfiguration`. |
|Exclusivamente local | En las herramientas locales: <br>- Asegúrese de que la federación esté habilitada en `CsAccessEdgeConfiguration`.<br>- Asegúrese de que la federación para el usuario esté habilitada a través de `ExternalAccessPolicy` (ya sea por la directiva global, la directiva del sitio o la directiva asignada por el usuario). <br> - Si no usa una federación abierta, asegúrese de que el dominio de destino se muestre en `AllowedDomains`. |
|Híbrido con algunos usuarios en línea (en Skype Empresarial o Teams) y algunos usuarios locales. | Siga los pasos anteriores para organizaciones en línea y locales. |

### <a name="delivery-of-incoming-chats-and-calls"></a>Entrega de chats y llamadas entrantes 

Los chats y las llamadas entrantes de una organización de la federación llegarán al cliente de Teams o de Skype Empresarial del usuario en función del modo del usuario destinatario en TeamsUpgradePolicy.

| Si desea | Haga lo siguiente: |
|:---------|:-----------------------|
| Asegúrese de que las llamadas y los chats federados entrantes lleguen al cliente de Teams del usuario: | Configure los usuarios para que sean TeamsOnly.
| Asegúrese de que los chats federados entrantes y las llamadas lleguen al cliente de Skype Empresarial del usuario | Configure a los usuarios para que se estén en cualquier modo distinto de TeamsOnly. |


### <a name="enable-federation-between-users-in-your-organization-and-consumer-users-of-skype"></a>Habilitar la federación entre los usuarios de su organización y los usuarios consumidores de Skype

Para habilitar la federación entre los usuarios de su organización y los usuarios consumidores de Skype:

| Si su organización es | Habilitar la federación de consumidores como se muestra a continuación |
|:---------|:-----------------------|
| Exclusivamente en línea sin Skype Empresarial local.  Esto incluye a las organizaciones que tienen usuarios de TeamsOnly o usuarios de Skype Empresarial Online. | Si usa el Centro de administración de Teams: <br>- Asegúrese de que **Permitir que los usuarios de mi organización se comuniquen con usuarios de Skype** está habilitado en Acceso externo.<br><br>Con PowerShell: <br>- Asegúrese de que la cuenta empresarial esté habilitada para la federación: `Get-CsTenantFederationConfiguration` debe mostrar `AllowPublicUsers=true`. <br> - Asegúrese de que el valor vigente del usuario de `CsExternalAccessPolicy` tenga `EnablePublicCloudAccess=true`. |
| Exclusivamente local | En las herramientas locales: <br> - Asegúrese de que Skype está habilitado como asociado federado. <br> - Asegúrese de `EnablePublicCloudAccess=true` para el usuario a través de `ExternalAccessPolicy` (ya sea mediante la directiva global, la directiva del sitio o la directiva asignada por el usuario).|
| Híbrido con algunos usuarios en línea (en Skype Empresarial o Teams) y algunos usuarios locales.| Siga los pasos anteriores para organizaciones en línea y locales.


> [!IMPORTANT]
> No es necesario que agregue ningún **dominio de Skype** como dominio permitido para permitir que los usuarios de Teams o Skype Empresarial Online se comuniquen con usuarios de Skype de dentro o de fuera de su organización. Se permiten todos los **dominios de Skype**.

## <a name="federation-diagnostic-tool"></a>Herramienta de diagnóstico de federación

Si es administrador, puede usar la siguiente herramienta de diagnóstico para validar que un usuario de Teams pueda comunicarse con un usuario de Teams federado:

1. Seleccione **Ejecutar pruebas** a continuación, lo cual rellenará el diagnóstico en el Centro de administración de Microsoft 365. 

   > [!div class="nextstepaction"]
   > [Ejecutar pruebas: federación de Teams](https://aka.ms/TeamsFederationDiag)

2. En el panel Ejecutar diagnóstico, escriba la **Dirección de Protocolo de inicio de sesión (SIP)** y el **nombre de dominio del espacio empresarial federado** y, a continuación, seleccione **Ejecutar pruebas**.

3. Las pruebas indicarán los mejores pasos a seguir para abordar cualquier configuración de espacio empresarial o directiva que impida la comunicación con el usuario federado.


## <a name="related-topics"></a>Temas relacionados

- [Experiencia de chat nativa para usuarios externos (federados)](native-chat-for-external-users.md)
