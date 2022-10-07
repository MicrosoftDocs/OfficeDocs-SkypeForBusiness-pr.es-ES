---
title: Conectar Microsoft Teams Essentials (identidad de AAD) a un sistema de correo electrónico existente con el calendario
ms.author: mikeplum
author: MikePlumleyMSFT
ms.reviewer: jimmyw
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
searchScope:
- Microsoft Teams
search.appverid: MET150
description: Obtenga información sobre cómo conectar Microsoft Teams Essentials (identidad de AAD) a un sistema de correo electrónico existente con calendario como Google Workspace
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: acdd613044e5e7f0ac7db857ca734f276522c919
ms.sourcegitcommit: 6e85f3f70f8488ab827ac352c0f324b6dfd4b856
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2022
ms.locfileid: "68377598"
---
# <a name="connect-microsoft-teams-essentials-aad-identity-to-an-existing-email-system-with-calendar"></a>Conectar Microsoft Teams Essentials (identidad de AAD) a un sistema de correo electrónico existente con el calendario

En esta guía se proporcionan pasos de configuración para conectar Microsoft Teams Essentials (identidad AAD) a un sistema de correo electrónico existente con el calendario.

Microsoft Teams Essentials (identidad de AAD) reúne lo mejor de Teams con reuniones, chat, llamadas y colaboración. Teams Essentials (identidad de AAD) puede conectarse a su sistema de correo electrónico existente para proporcionar una experiencia integrada, como tener todas las notificaciones de Teams en una bandeja de entrada de correo electrónico existente, todos los eventos del calendario en Teams y la posibilidad de iniciar sesión en Teams con su dirección de correo electrónico existente.

Una vez conectado, puede ver respuestas a reuniones programadas e invitaciones para colaborar en su buzón y en Microsoft Teams. También puede ver e interactuar con reuniones entrantes desde su calendario mediante Teams y el software de reuniones de terceros como Google Workspace.

## <a name="prerequisites"></a>Requisitos previos

Los pasos de configuración de este artículo implican el proceso de reenvío automático de elementos desde Exchange Online. De forma predeterminada, el reenvío automático está deshabilitado por la directiva de salida contra correo no deseado. Esta directiva debe estar habilitada para conectar Teams Essentials a un sistema de calendario y buzón existente.

Para habilitar el reenvío automático:

1. Vaya al portal de Microsoft 365 Defender en<https://security.microsoft.com/>
2. En el menú de navegación izquierdo, vaya a Email &**directivas de** **colaboración** >  & reglas  > **Directivas** > **de amenazas Contra correo no deseado** en la sección Directivas
3. En la página **Directivas contra correo no deseado** , seleccione **Directiva de salida contra correo no deseado (predeterminado)** en la lista
4. En el control flotante de detalles de la directiva que aparece, seleccione **Editar configuración de protección** para modificar la regla de autoforwarding.
5. En **Reglas de reenvío**, cambie la condición de reenvío automático a **Activado: el reenvío está habilitado** y guarde los cambios.

:::image type="content" source="media/essentials-antispam.png" alt-text="Imagen que muestra el control flotante de directiva de salida contra correo no deseado del Portal de Microsoft Defender con la condición Activado, reenvío está habilitado en Reglas de reenvío." :::

Para obtener más información sobre cómo configurar directivas de correo no deseado saliente, visite [Configurar el filtrado de correo no deseado saliente Office 365 | Microsoft Docs](/microsoft-365/security/office-365-security/configure-the-outbound-spam-policy?view=o365-worldwide&preserve-view=true).

## <a name="connect-teams-essentials-to-exchange-online-with-exchange-on-premises"></a>Conectar Teams Essentials a Exchange Online con Exchange local

Puede disfrutar de todo lo que Teams Essentials (AAD) ofrece mediante un enfoque híbrido para configurar la conexión entre Microsoft Teams y Exchange Online con Exchange local.

Para que el acceso al calendario funcione para sus buzones locales, siga las instrucciones que se proporcionan en[Configurar el acceso del calendario de Teams para buzones locales de Exchange Microsoft Tech Community](https://techcommunity.microsoft.com/t5/exchange-team-blog/configuring-teams-calendar-access-for-exchange-on-premises/ba-p/1484009)

Para implementar Salas de Microsoft Teams en un entorno híbrido con Exchange local, visite [Implementar Salas de Microsoft Teams con Exchange local: Microsoft Teams | Microsoft Docs](rooms/with-exchange-on-premises.md)

## <a name="connect-teams-essentials-to-third-party-email-systems-with-calendar"></a>Conectar Teams Essentials a sistemas de correo electrónico de terceros con el calendario

Si no tiene previsto cambiar el buzón de correo de su organización a Microsoft 365, puede conectar Teams Essentials a un sistema de calendario y correo electrónico de terceros existente. Esta conexión le permite recibir notificaciones de Teams en su sistema de correo electrónico existente mientras visualiza invitaciones a reuniones y eventos del calendario existentes en Microsoft Teams.

### <a name="connect-teams-essentials-to-third-party-email-using-vanity-domain-google-workspace-example"></a>Conectar Teams Essentials al correo electrónico de terceros mediante un dominio de vanidad (ejemplo de Google Workspace)

En la siguiente sección se muestra cómo conectar Microsoft Teams a un sistema de correo electrónico existente con calendario, como Google Workspace. Para lograr esta conexión, dejará intacto el sistema de correo electrónico actual, reenviará todo el correo electrónico a Exchange Online y filtrará todo excepto los correos electrónicos del tipo de calendario. Al hacerlo, los correos electrónicos de calendario aparecen automáticamente en el calendario de Teams aceptado como correos electrónicos provisionales y de tipo no calendario se eliminan.

Todo el correo electrónico generado en Microsoft 365 se reenvía a Google Workspace para que los usuarios reciban avisos y notificaciones de Teams. Las identidades de usuario, como el correo electrónico principal del usuario, se pueden duplicar. El inicio de sesión único también es posible, pero no es necesario. Los usuarios deben poder unirse a las reuniones de Teams desde el calendario de terceros o el calendario de Teams. Otras características de Teams funcionarán según lo esperado.

:::image type="content" source="media/essentials-googleworkspace.png" alt-text="Imagen que representa un diagrama del flujo de correo entre EXO y Gmail":::

Estos ejemplos se basan en el commandlet de PowerShell [Connect-ExchangeOnline](/powershell/module/exchange/connect-exchangeonline) que forma parte del [módulo Exchange Online PowerShell V2](/powershell/exchange/exchange-online-powershell-v2?preserve-view=true&view=exchange-ps). Si recibe un error al ejecutar Connect-ExchangeOnline, asegúrese de que ha seguido las instrucciones recomendadas para instalar el módulo mediante [Instalar el módulo EXO V2](/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-EXO-v2-module). Cuando Connect-ExchangeOnline solicite credenciales, asegúrese de usar una cuenta de administrador de inquilinos.

#### <a name="step-one-set-up-a-new-microsoft-365-tenant-domain"></a>Paso 1: Configurar un nuevo dominio de inquilino de Microsoft 365

1. Vaya al centro de administración en <https://admin.microsoft.com>.

2. Vaya a **Configurar** > **dominios**  y seleccione **Agregar dominio** para agregar el dominio existente. Si no agrega un dominio, los usuarios de su organización usarán el dominio onmicrosoft.com para sus direcciones de correo electrónico hasta que lo haga. Asegúrese de agregar el dominio antes de agregar usuarios, para que no tenga que configurarlos dos veces.

3. Compruebe el dominio con un registro TXT siguiendo los pasos de [Comprobar con un registro TXT](/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider?view=o365-worldwide&preserve-view=true).

4. Cuando se te solicite, selecciona **No permitir que Microsoft 365 configure DNS**.

5. Cuando se le solicite, deje los registros MX existentes en su lugar sin modificarlos.

6. Actualice el registro TXT de SPF existente para que incluya Microsoft 365.

7. Configure DomainKeys Identified Mail (DKIM) para Microsoft 365 siguiendo estos pasos para [configurar DKIM](/microsoft-365/security/office-365-security/use-dkim-to-validate-outbound-email?view=o365-worldwide&preserve-view=true) manualmente.

8. Vuelva a iniciar sesión en la Centro de administración de Microsoft 365 en <https://admin.microsoft.com/AdminPortal/> para habilitar DKIM

9. En el panel de navegación de la izquierda, seleccione **Configuración de** > **dominios**

10. Con la casilla, seleccione su dominio existente que no sea de Microsoft (por ejemplo, TomislavK@thephone-company.com) de las listas de dominios actuales.

11. Selecciona el botón con **tres puntos verticales** para abrir un menú.

12. En el menú, selecciona **Establecer como predeterminado**

13. **Confirme establecer como predeterminado** en la ventana que aparece para establecer el dominio existente como predeterminado.
    :::image type="content" source="media/essentials-internalrelay2.png" alt-text="Imagen del cuadro de diálogo de confirmación para configurar el dominio como predeterminado":::

    Para obtener más información sobre cómo agregar un dominio a Microsoft 365, siga los pasos descritos en [Agregar un dominio a Microsoft 365](https://support.office.com/article/add-a-domain-to-office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611?ui=en-US&rs=en-US&ad=US).

#### <a name="step-two-add-users-and-assign-teams-essentials-licenses"></a>Paso 2: Agregar usuarios y asignar licencias de Teams Essentials

1. Ir al centro de administración en <https://admin.microsoft.com> para agregar un usuario individual

2. Vaya a **Usuarios** > **activos** y seleccione **Agregar un usuario**

3. En el panel **Configurar los conceptos básicos** , rellene la información básica del usuario y, después, seleccione **Siguiente**.
    - **Nombre:** Rellene el nombre y los apellidos, el nombre para mostrar y el nombre de usuario.
    - **Dominio:** Elija el dominio de la cuenta del usuario. Por ejemplo, si el nombre de usuario del usuario es Jakob y el dominio está contoso.com, inicie sesión con jakob@contoso.com.
    - **Configuración de contraseña:** Elija si desea usar la contraseña generada automáticamente o crear su propia contraseña segura para el usuario.  Determine si desea enviar la contraseña en un correo electrónico cuando se agrega el usuario.

4. En el panel **Asignar licencias de producto** , seleccione la ubicación y la licencia apropiada para el usuario. Si no tiene ninguna licencia disponible, puede agregar un usuario y comprar más licencias. Seleccione Siguiente.

5. En el panel **Configuración opcional** , expanda **Roles** si desea convertir a este usuario en administrador. Expanda **Información de perfil** para agregar información adicional sobre el usuario.

6. Seleccione **Siguiente**, revise la configuración del nuevo usuario, realice cualquier otro cambio si es necesario, seleccione **Finalizar la adición** y cierre.

Para agregar varios usuarios al mismo tiempo, siga los pasos recomendados en [Agregar usuarios y asignar licencias: Administración de Microsoft 365 | Microsoft Docs](/microsoft-365/admin/add-users/add-users?view=o365-worldwide&preserve-view=true)

#### <a name="step-three-configure-google-workspace"></a>Paso 3: Configurar Google Workspace

***Configure la entrega dual de correo electrónico a Microsoft 365 y quite los datos adjuntos:***

1. Siga los pasos de Google para configurar la entrega dual: <https://support.google.com/a/answer/9228551?hl=en>

2. Agregar ruta para Office 365

    - Ve a la consola de Google Administración en <https://admin.google.com>)
    - Vaya a Aplicaciones > Google Workspace > Hosts de > de Gmail.
    - Escriba un nombre de ruta. (Por ejemplo, Microsoft 365)
    - Elija "Host único" y escriba el registro MX especificado para el dominio en Microsoft 365 (por ejemplo: ContosoLandscaping2-m365master-com.mail.protection.outlook.com)

    **Método de host inteligente para resolver el código de respuesta ATTR35 cuando se envía correo a Exchange local/Exchange Online:**
    - Elija "Host único" y escriba el registro MX para el dominio inicial del inquilino como host inteligente. El dominio inicial tiene el formato GUID.onmicrosoft.com. Un GUID es un valor único que se proporciona a cada organización como parte de su inscripción en el servicio. Un GUID es un entero de 128 bits (16 bytes) que se puede usar en todos los equipos y redes siempre que se necesite un identificador único.
    - Puede usar la línea de comandos: nslookup -type MX GUID.onmicrosoft.com para resolver el registro MX (Por ejemplo: contosolandscaping2.mail.protection.outlook.com)
    - Elija **Puerto:25**
    - Continuar con las opciones recomendadas

3. Configurar la ruta a Office 365

    - Abre la **consola de google Administración** en<https://admin.google.com>

    - Ir al **enrutamiento** de  > **Gmail** > **de Aplicaciones de Google Workspace** > 

    - En la pestaña **Enrutamiento** , seleccione **Configurar**

    - Escriba **El nombre** de la regla. (Por ejemplo, Gmail a Office 365)

    - Para **que los mensajes de correo electrónico afecten**, seleccione **entrantes** y  **recepción interna**

    - En **Para los tipos de mensajes anteriores**, seleccione **Modificar mensaje**

    - En **Entregar también a**, seleccione **Agregar más destinatarios** y, a continuación, seleccione **Agregar para agregar la ruta de correo secundaria.**

    - En **Destinatarios**, seleccione la flecha abajo "" y seleccione **Avanzadas.**

    - Selecciona **Cambiar ruta.**

    - En la lista, seleccione la ruta de correo secundaria que creó anteriormente

    - En **Datos adjuntos**, seleccione **Quitar datos adjuntos del mensaje**

    - Desplázate hacia abajo y selecciona **Guardar**.

***Agregue su subdominio en Google Workspace para recibir correo electrónico de Microsoft 365.***

  A continuación, creará reglas de reenvío en los buzones de Microsoft 365 al subdominio. Elija un subdominio que se usará en Google Workspace para recibir correo electrónico de Microsoft 365 (por ejemplo, g.contosolandscaping2.m365master.com)

1. Iniciar en la **consola de Google Administración** (en admin.google.com)

2. Vaya a **Dominios** >  **de cuenta** > **Administrar dominios**

3. Seleccione **Agregar un dominio**

4. Escriba el nombre de dominio que seleccionó

5. Seleccionar **dominio de alias de usuario**

6. Seleccione **Agregar dominio & iniciar verificación**

7. Esperar a que la verificación se complete y actualice la página

8. Seleccione **Activar Gmail**

9. Elija **Omitir la configuración de registros MX** y, a continuación, seleccione **SIGUIENTE**

10. En el cuadro de diálogo **Redirigir correo a otro servidor** , anote el servidor al que redirigir el correo (por ejemplo, aspmx.l.google.com) y seleccione **Usar otro servidor de correo**

***Permitir que el correo electrónico de Microsoft 365 omita el filtro de correo no deseado***

1. Busque un encabezado adecuado del espacio empresarial de Microsoft 365 enviando un correo electrónico a un usuario en Google Workspace.

2. Abre el mensaje y selecciona **Mostrar original**

3. Elija un encabezado de correo electrónico que identifique exclusivamente el correo procedente de su inquilino de Microsoft 365. (Por ejemplo, X-MS-Exchange-CrossTenant-id: 92f60fc7-eab3-403b-9d7d-9d683bf0a4b5)

4. Ve a **la consola de Google Administración** en<https://admin.google.com>

5. Ir **a** > **Cumplimiento** de **Gmail** > **de Aplicaciones de Google Workspace** > 

6. Vaya a **Cumplimiento de contenido** y seleccione **Configurar**

7. Asigne un nombre a la configuración. Por ejemplo, lista de permitidos correo electrónico de Microsoft 365.

8. En **mensajes de correo electrónico para afectar a** la comprobación entrante

9. En **Agregar expresiones que describan el contenido que desea buscar en cada mensaje** , seleccione **si CUALQUIERA de los siguientes elementos coincide con el mensaje**

10. En **Expresiones**, seleccione **Agregar** xi. En **Agregar configuración**, elija **Coincidencia de contenido avanzada**

11. En **Ubicación** , elija **Encabezados completos**

12. En **Tipo de coincidencia** , elija **Texto completo**

13. En Contenido, escriba el encabezado de correo electrónico que identifica exclusivamente el correo electrónico procedente de su espacio empresarial de Microsoft 365 (Por ejemplo, X-MS-Exchange-CrossTenant-id: 92f60fc7-eab3-403b-9d7d-9d683bf0a4b5)

14. Selecciona **Guardar**

15. En el campo **Si las expresiones anteriores coinciden, haga lo siguiente** > **Modificar mensaje** y active **Omitir filtro de correo no deseado para este mensaje** en **Correo no deseado**.

16. Selecciona **Guardar**

#### <a name="step-four-configure-microsoft-365-settings-for-the-integration"></a>Paso 4: Configurar las opciones de Integración de Microsoft 365

*Configure el conector para redirigir el correo de Microsoft 365 a Gmail:*

1. Ve al **Centro de Administración de Microsoft** en<https://admin.microsoft.com/AdminPortal>

2. Seleccione **Mostrar todo** en el menú de navegación izquierdo.

3. En **centros de Administración**, seleccione **Exchange** para abrir el Centro de administración de Exchange en una pestaña nueva.

4. En el menú de navegación izquierdo del **Centro de administración de Exchange**, seleccione **Conectores** de flujo  >  de **correo**, abra el menú de desbordamiento (...) y seleccione Agregar un conector.

5. En **Conexión desde** en la ventana del conector nuevo, seleccione **Office 365**

6. En **Conexión para seleccionar el** servidor de correo electrónico de su organización, seleccione **Siguiente**

7. Escriba un **Nombre** para el nuevo conector (por ejemplo, Para Gmail) y continúe con **Siguiente**

8. En la sección **Uso del conector** , seleccione **Solo cuando tenga configurada una regla de transporte que redirija mensajes a este conector** y seleccione **Siguiente**.

9. En la sección Enrutamiento, escriba el host de correo inteligente adecuado (por ejemplo, aspmx.l.google.com), seleccione **+** y, a continuación, continúe con **Siguiente**.

10. En la sección **Restricciones de seguridad** , acepta la configuración predeterminada seleccionando **Siguiente**

11. En la **sección Correo electrónico de validación**, escribe una dirección de correo electrónico válida para el sistema Gmail (por ejemplo, johannal@g.contosolandscaping2.m365master.com), selecciona el **signo más (+)** y, a continuación, selecciona **Validar**

12. Espere a que finalice la validación y, si es correcto, presione Siguiente

13. En **Revisar conector**, compruebe que la configuración es correcta y presione Crear conector

14. Cuando vea la notificación de conector creado, presione **Listo**

*Reenvíe el correo de los buzones de Microsoft 365 a Gmail:*

1. Use el **Centro de Administración de Microsoft 365** para actualizar cada buzón o puede usar un script de **PowerShell**, como el siguiente:

    ```powershell
    $forwardingDomain = "g.contosolandscaping2.m365master.com"
    Connect-ExchangeOnline
    $Mailboxes = Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"}
    Foreach ($mbx in $mailboxes) {

    Set-Mailbox $mbx.Identity -DeliverToMailboxAndForward $true -ForwardingSMTPAddress $($mbx.Alias,$forwardingDomain -join "@")
    }
    ```

    **Solución de problemas de Connect-ExchangeOnline:**

    ¿Está experimentando un error al ejecutar Connect-ExchangeOnline? Esto podría ser el resultado de la regla de reenvío automático de correo electrónico de su organización. De forma predeterminada, el reenvío automático está deshabilitado. Para conectar Teams Essentials a Google Workspace, la regla debe estar habilitada.

    Escriba el siguiente script:

   ```powershell
    Set-ExecutionPolicy Unrestricted
     ```

    Después, ejecute los siguientes comandos:

    ```powershell
    Enable-OrganizationCustomization
    Get-HostOutboundSpamFilterPolicy | set-HostedOutboundSpamFilterPolicy -AutoForwardingMode On
    ```

*Configurar Exchange Online regla de transporte directa a calendario:*

1. Si configura esta configuración, se aceptarán automáticamente invitaciones de calendario para que aparezcan en el calendario de Teams sin requerir que los usuarios interactúen con la invitación en Outlook Web App.

2. Se puede usar el script siguiente para crear las reglas de transporte:

    ```powershell
    Connect-ExchangeOnline
    New-TransportRule -Name "Direct to Calendar" -MessageTypeMatches Calendaring -SetHeaderName "X-MS-Exchange-Organization-CalendarBooking-Response" -SetHeaderValue Tentative
    New-TransportRule -Name "Direct to Calendar triage action" -MessageTypeMatches Calendaring -SetHeaderName "X-MS-Exchange-Organization-CalendarBooking-TriageAction" -SetHeaderValue MoveToDeletedItems

    ```

*Deshabilite Outlook en la Web para los buzones:*

1. Siga las instrucciones de [Habilitar o deshabilitar Outlook en la Web para un buzón en Exchange Online](/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-outlook-web-app) deshabilitar Outlook en la Web para los buzones.

2. Puede deshabilitar Outlook en la Web con el **Centro de Administración de Exchange** o **PowerShell**. Puede usar el siguiente ejemplo de PowerShell para deshabilitar Outlook en la Web para todos los buzones:

    ```powershell
    Connect-ExchangeOnline
    $Mailboxes = Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"}
    Foreach ($mbx in $mailboxes) {
    Set-CASMailbox $mbx.Identity -OWAEnabled $false
    }
    ```

#### <a name="step-five-configure-exchange-online-domain-for-internal-relay"></a>Paso 5: Configurar Exchange Online dominio para retransmisión interna

Este paso garantiza que el correo electrónico se envía al sistema de terceros para su resolución final.

1. Ve al **Centro de Administración de Microsoft** en<https://admin.microsoft.com/AdminPortal>

2. En el panel de navegación izquierdo, seleccione **Mostrar todo**

3. En **Centros de Administración**, seleccione **Exchange** para abrir el Centro de administración de Exchange en una pestaña nueva.

4. En **el Centro de administración de Exchange**, seleccione **Flujo de correo** en el menú de navegación izquierdo y, después, seleccione **Dominios aceptados**

5. Pulse en el nombre de dominio configurado en el sistema de terceros (por ejemplo, contosoLandscaping2.m365master.com)

    :::image type="content" source="media/essentials-internalrelay1.png" alt-text="Imagen que muestra la configuración del Centro de administración de Exchange para Flujo de correo. ":::

6. Seleccione **Retransmisión interna** y, a continuación, haga clic en **Guardar**

    :::image type="content" source="media/essentials-internalrelay2.png" alt-text="Imagen que muestra el acto de guardar la configuración de retransmisión interna.":::

#### <a name="step-six-create-a-rule-to-delete-all-inbound-mail-to-exchange-online-except-for-calendaring"></a>Paso 6: Crear una regla para eliminar todo el correo entrante a Exchange Online excepto calendario

1. Puede configurar esta regla en el **Centro de Administración de Exchange** o **PowerShell**. Puede usar el siguiente ejemplo **de PowerShell** para crear la regla:

    ```powershell
    Connect-ExchangeOnline
    New-TransportRule -Name "Delete all except Calendaring" -ExceptIfMessageTypeMatches Calendaring -FromScope NotInOrganization -DeleteMessage:$true
    ```

### <a name="connect-teams-essentials-to-third-party-email-not-using-vanity-domain-gmail-example"></a>Conectar Teams Essentials al correo electrónico de terceros que no usa el dominio vanity (ejemplo de Gmail)

Puede programar y unirse a una reunión de Teams directamente desde Google Workspace conectando una cuenta de Gmail del consumidor a Teams Essentials con la dependencia principal del [complemento de Teams G Suite](https://support.microsoft.com/office/install-the-teams-meeting-add-on-for-google-workspace-bba2dfbe-0b2b-4ee7-be10-261ad80ddb60). Esto le ofrece la oportunidad de programar videoconferencias y audioconferencias con pantalla compartida, chat de reuniones, pizarras digitales y mucho más.

Configurará Gmail para extraer correo electrónico de Exchange Online para asegurarse de que el correo generado en Microsoft 365 y Teams llegue correctamente a Gmail. Es posible que deba deshabilitar los valores predeterminados de seguridad para lograr esta conexión, lo que hace que sea esencial usar una contraseña única segura. No es necesario un dominio personalizado para este escenario, pero puede configurarse en Microsoft 365 para su uso en Gmail si desea usar uno.

:::image type="content" source="media/essentials-gmail.png" alt-text="Imagen que hace sospechar el flujo de correo entre Teams Essentials y Gmail":::

#### <a name="1-ensure-that-you-have-a-gmail-account-set-up"></a>1. Asegúrese de que tiene una cuenta de Gmail configurada

Si ya tiene una cuenta existente, puede continuar con el paso siguiente. Si no es así, visite [Crear nueva cuenta de Google](https://accounts.google.com/SignUp?hl=en) para configurar una nueva cuenta de Gmail.

#### <a name="2-set-up-your-microsoft-365-tenant"></a>2. Configurar el espacio empresarial de Microsoft 365

*Configurar usuarios de AAD de Teams:*

1. Siga las instrucciones de[Agregar usuarios y asignar licencias](/microsoft-365/admin/add-users/add-users?view=o365-worldwide&preserve-view=true) para agregar varios usuarios

*Configurar la protección de identidad:*

1. Deshabilitar los valores predeterminados de seguridad si están activos.

2. Configurar la autenticación multifactor para los usuarios

3. Si usa el acceso condicional, asegúrese de hacer una excepción para el acceso POP al buzón.

*Agregar dominio al Centro de Administración de Microsoft 365 (opcional):*

1. En navegación, selecciona Configuración > dominio y, a continuación, Agregar dominio

2. Escriba su nombre de dominio en el campo correspondiente

3. Siga las instrucciones en pantalla para comprobar el dominio con registro TXT

4. Cuando se le solicite, permita que Microsoft configure DNS

5. Complete las instrucciones para comprobar la ruta del registro MX a Microsoft 365

6. Configurar el registro TXT de SPF para que incluya Microsoft 365

7. Complete las instrucciones para configurar registros TXT DKIM para Microsoft 365

8. Comprueba que DKIM esté habilitado cerrando sesión y volviendo a iniciar sesión en el centro de Administración

#### <a name="3-configure-gmail"></a>3. Configurar Gmail

1. Configurar Gmail para extraer Exchange Online correo en su sistema

2. Configurar el complemento Calendario de Teams

3. Habilitar Gmail para usar un dominio empresarial (opcional)
