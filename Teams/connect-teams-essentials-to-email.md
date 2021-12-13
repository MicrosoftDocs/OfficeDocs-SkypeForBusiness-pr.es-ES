---
title: Conectar Microsoft Teams Essentials (AAD identidad) a un sistema de correo electrónico existente con calendario
author: adjoseph
ms.author: adjoseph
ms.reviewer: jimmyw
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
searchScope:
- Microsoft Teams
search.appverid: MET150
description: Obtenga información sobre cómo conectar Microsoft Teams Essentials (AAD identidad) a un sistema de correo electrónico existente con un calendario como Google Workspace
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 682f7bcd4e90e96534e954cd0e22c6f5952db08b
ms.sourcegitcommit: 563567ab140d5802756170c846dade3645d0b9e4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2021
ms.locfileid: "61284798"
---
# <a name="connect-microsoft-teams-essentials-aad-identity-to-an-existing-email-system-with-calendar"></a>Conectar Microsoft Teams Essentials (AAD identidad) a un sistema de correo electrónico existente con calendario

Esta guía proporciona pasos de configuración para conectar Microsoft Teams Essentials (AAD identidad) a un sistema de correo electrónico existente con el calendario.

Microsoft Teams Essentials (AAD identidad) reúne lo mejor de Teams con reuniones, chat, llamadas y colaboración. Teams Essentials (AAD Identity) puede conectarse a su sistema de correo electrónico existente para proporcionar una experiencia integrada como tener todas las notificaciones Teams en una bandeja de entrada de correo electrónico existente, todos los eventos del calendario en Teams y la capacidad de iniciar sesión en Teams con su dirección de correo electrónico existente.

Una vez conectado, puede ver respuestas a reuniones programadas e invitaciones para colaborar en su buzón y Microsoft Teams. También puede ver e interactuar con las reuniones entrantes desde el calendario con el software de reuniones Teams y de terceros como Google Workspace.

## <a name="prerequisites"></a>Requisitos previos

Los pasos de configuración de este artículo implican el proceso de reenviar automáticamente elementos de Exchange Online. De forma predeterminada, el reenvío automático está deshabilitado por la directiva de salida contra correo no deseado. Esta directiva debe estar habilitada para conectar Teams Essentials a un sistema de buzón y calendario existente.

Para habilitar el reenvío automático:

1. Vaya al portal de Microsoft 365 Defender en<https://security.microsoft.com/>
2. En el menú de navegación izquierdo, vaya a Directivas de **& de**  >  **colaboración &**  >  **reglas**  >   de amenazas Directivas contra correo no deseado en la sección Directivas
3. En la **página Directivas contra correo** no deseado, seleccione Directiva de salida contra correo no deseado **(predeterminado)** en la lista
4. En el control emergente de detalles de la directiva que aparece, seleccione Editar configuración de **protección** para modificar la regla de autocarreción.
5. En **Reglas de reenvío,** cambie la condición de reenvío automático a **Activado: el** reenvío está habilitado y guarde los cambios.

:::image type="content" source="media/essentials-antispam.png" alt-text="Imagen que muestra el control de la directiva de salida contra correo no deseado del Portal de Microsoft Defender con Activado, el reenvío está habilitado en Reglas de reenvío." :::

Para obtener más información sobre cómo configurar directivas de correo no deseado salientes, visite Configurar el filtrado [de correo no deseado saliente: Office 365 | Microsoft Docs](/microsoft-365/security/office-365-security/configure-the-outbound-spam-policy?view=o365-worldwide&preserve-view=true).

## <a name="connect-teams-essentials-to-exchange-online-with-exchange-on-premises"></a>Conectar Teams Essentials para Exchange Online con Exchange local

Puede disfrutar de todo lo que Teams Essentials (AAD) tiene que ofrecer mediante un enfoque híbrido para configurar la conexión entre Microsoft Teams y Exchange Online con Exchange local.

Para hacer que el acceso Exchange al calendario funcione para sus buzones locales, siga las instrucciones que se proporcionan en Configurar el acceso de calendario Teams para buzones locales: Microsoft[Tech Community](https://techcommunity.microsoft.com/t5/exchange-team-blog/configuring-teams-calendar-access-for-exchange-on-premises/ba-p/1484009)

Para implementar Salas de Microsoft Teams en un entorno híbrido con Exchange local, visite Implementar Salas de Microsoft Teams con Exchange [local: Microsoft Teams | Microsoft Docs](rooms/with-exchange-on-premises.md)

## <a name="connect-teams-essentials-to-third-party-email-systems-with-calendar"></a>Conectar Teams Essentials a sistemas de correo electrónico de terceros con calendario

Si no tiene previsto cambiar el buzón de su organización a Microsoft 365, puede conectar Teams Essentials a un sistema de calendario y correo electrónico de terceros existente. Esta conexión le permite recibir notificaciones Teams en su sistema de correo electrónico existente mientras ve las invitaciones a reuniones existentes y los eventos del calendario en Microsoft Teams.

### <a name="connect-teams-essentials-to-third-party-email-using-vanity-domain-google-workspace-example"></a>Conectar Teams Essentials a correo electrónico de terceros con dominio de vanidad (ejemplo de Google Workspace)

En la siguiente sección se muestra cómo conectarse Microsoft Teams un sistema de correo electrónico existente con el calendario, como Google Workspace. Logrará esta conexión dejando intacto el sistema de correo electrónico actual, reenviando todo el correo electrónico a Exchange Online, filtrando todo excepto los correos electrónicos del tipo de calendario. Al hacerlo, los correos electrónicos de calendario aparecen automáticamente en el calendario Teams se eliminan como correos electrónicos provisionales y de tipo no calendario.

Todo el correo electrónico generado en Microsoft 365 se reenvía a Google Workspace para que los usuarios reciban Teams y notificaciones. Las identidades de usuario, como el correo electrónico principal del usuario, se pueden duplicar. El inicio de sesión único también es posible, pero no es necesario. Los usuarios deben poder unirse Teams reuniones desde el calendario de terceros o desde Teams calendario. Otras Teams funciones funcionarán según lo esperado.

:::image type="content" source="media/essentials-googleworkspace.png" alt-text="Imagen que muestra un diagrama del flujo de correo entre EXO y Gmail":::

Estos ejemplos se basan en el Conectar de comandos de [PowerShell de ExchangeOnline](/powershell/module/exchange/connect-exchangeonline?view=exchange-ps&preserve-view=true) que forma parte del Exchange Online [de PowerShell V2.](/powershell/exchange/exchange-online-powershell-v2&preserve-view=true) Si recibe un error al ejecutar Conectar-ExchangeOnline, asegúrese de que ha seguido las instrucciones recomendadas para instalar el módulo con Instalar el [módulo EXO V2.](/powershell/exchange/exchange-online-powershell-v2?view=exchange-ps&preserve-view=true) Cuando Connect-ExchangeOnline solicita credenciales, asegúrese de usar una cuenta de administrador de inquilinos.

**Paso uno: Configurar un nuevo dominio Microsoft 365 inquilino**

1. Vaya al Centro de administración en <https://admin.microsoft.com> .

2. Vaya a **Configurar**  >  **dominios** y seleccione **Agregar dominio** para agregar el dominio existente. Si no agrega un dominio, los usuarios de su organización usarán el dominio onmicrosoft.com para sus direcciones de correo electrónico hasta que lo haga. Asegúrese de agregar el dominio antes de agregar usuarios, para que no tenga que configurarlos dos veces.

3. Compruebe el dominio con un registro TXT siguiendo los pasos de [Comprobar con un registro TXT.](/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider?view=o365-worldwide&preserve-view=true)

4. Cuando se le solicite, seleccione **No permitir Microsoft 365 configurar DNS.**

5. Cuando se le solicite, deje los registros MX existentes en su lugar sin modificarlos.

6. Actualice el registro TXT de SPF existente para incluir Microsoft 365.

7. Configure DomainKeys Identified Mail (DKIM) para Microsoft 365 siguiendo estos pasos para configurar manualmente [DKIM.](/microsoft-365/security/office-365-security/use-dkim-to-validate-outbound-email?view=o365-worldwide&preserve-view=true)

8. Vuelva a iniciar sesión en Centro de administración de Microsoft 365 <https://admin.microsoft.com/AdminPortal/> en para habilitar DKIM

9. En el panel de navegación de la izquierda, seleccione **Configurar**  >  **dominios**

10. Con la casilla, seleccione su dominio existente que no es de Microsoft (por ejemplo, JohannaL@contosolandscapting2.m365master.com) de las listas de dominios actuales.

11. Seleccione el botón con **tres puntos verticales** para abrir un menú.

12. En el menú, seleccione **Establecer como predeterminado**

13. **Confirme el conjunto como predeterminado** en la ventana que aparece para establecer el dominio existente como predeterminado.
    :::image type="content" source="media/essentials-internalrelay2.png" alt-text="Imagen del cuadro de diálogo de confirmación para establecer el dominio como predeterminado":::

    Para obtener más instrucciones sobre cómo agregar un dominio a Microsoft 365, siga los pasos descritos en Agregar un dominio [a Microsoft 365](https://support.office.com/article/add-a-domain-to-office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611?ui=en-US&rs=en-US&ad=US).

**Paso dos: Agregar usuarios y asignar Teams de Essentials**

1. Ir al centro de administración en <https://admin.microsoft.com> para agregar un usuario individual

2. Vaya a **Usuarios**  >  **usuarios activos y** seleccione Agregar un **usuario**

3. En el **panel Configurar los conceptos** básicos, rellene la información básica del usuario y, a continuación, **seleccione Siguiente.**
    - **Nombre:** Rellene el nombre y apellidos, el nombre para mostrar y el nombre de usuario.
    - **Dominio:** Elija el dominio de la cuenta del usuario. Por ejemplo, si el nombre de usuario del usuario es Jakob y el dominio está contoso.com, iniciarán sesión con jakob@contoso.com.
    - **Configuración de contraseña:** Elija usar la contraseña autogenerada o crear su propia contraseña segura para el usuario.  Determine si desea enviar la contraseña en un correo electrónico cuando se agrega el usuario.

4. En el **panel Asignar licencias de producto,** seleccione la ubicación y la licencia adecuada para el usuario. Si no tiene licencias disponibles, puede agregar un usuario y comprar más licencias. Seleccione Siguiente.

5. En el **panel Configuración opcional,** expanda **Roles** si desea convertir a este usuario en administrador. Expanda **Información de perfil** para agregar información adicional sobre el usuario.

6. Seleccione **Siguiente,** revise la configuración del nuevo usuario, realice cualquier otro cambio si es necesario y, a continuación, seleccione **Finalizar adición** y cierre.

Para agregar varios usuarios al mismo tiempo, siga los pasos recomendados en Agregar usuarios y asignar licencias Microsoft 365 [administrador | Microsoft Docs](/microsoft-365/admin/add-users/add-users?view=o365-worldwide&preserve-view=true)

**Paso tres: Configurar Google Workspace**

***Configure la entrega dual de correo electrónico para Microsoft 365 y quitar datos adjuntos:***

1. Siga los pasos de Google para configurar la entrega dual: <https://support.google.com/a/answer/9228551?hl=en>

2. Agregar ruta para Office 365

    - Ir a la consola de administración de Google en <https://admin.google.com> )
    - Vaya a Aplicaciones > Google Workspace > Gmail > anfitriones.
    - Escriba un nombre de ruta. (Por ejemplo, Microsoft 365)
    - Elija "Host único" y escriba el registro MX especificado para el dominio en Microsoft 365 (por ejemplo: ContosoLandscaping2-m365master-com.mail.protection.outlook.com)

    **Método de host inteligente para resolver el código de respuesta ATTR35 cuando se envía correo a Exchange local o Exchange Online :**
    - Elija "Host único" y escriba el registro MX para el dominio inicial del inquilino como host inteligente. El dominio inicial está en el formato GUID.onmicrosoft.com. Un GUID es un valor único que se proporciona a todas las organizaciones como parte de su inscripción en el servicio. Un GUID es un entero de 128 bits (16 bytes) que se puede usar en todos los equipos y redes siempre que sea necesario un identificador único.
    - Puede usar la línea de comandos: nslookup -type MX GUID.onmicrosoft.com para resolver el registro MX (por ejemplo: contosolandscaping2.mail.protection.outlook.com)
    - Elija **Puerto:25**
    - Continuar con las opciones recomendadas

3. Configurar la ruta para Office 365

    - Abrir la **consola de administración de Google** en <https://admin.google.com>

    - Ir a **Aplicaciones**  >  **Google Workspace**  >  **Gmail**  >  **Routing**

    - En la **pestaña Enrutamiento,** seleccione **Configurar**

    - Escriba **Nombre para** la regla. (Por ejemplo, Gmail para Office 365)

    - Para **que los mensajes de correo electrónico afecten,** seleccione Recepción **entrante**  **e interna**

    - En **Para los tipos de mensajes anteriores,** seleccione Modificar **mensaje**

    - En **Entregar también a**, seleccione Agregar más **destinatarios** y, a continuación, seleccione Agregar para agregar la ruta de correo **secundaria.**

    - En **Destinatarios,** seleccione la flecha abajo "" y seleccione **Avanzadas.**

    - Seleccione **Cambiar ruta.**

    - En la lista, seleccione la ruta de correo secundaria que creó anteriormente

    - En **Datos adjuntos,** seleccione **Quitar datos adjuntos del mensaje**

    - Desplácese hacia abajo y seleccione **Guardar**.

***Agregue el subdominio en El área de trabajo de Google para recibir correo electrónico de Microsoft 365.***

  A continuación, creará reglas de reenvío en Microsoft 365 buzones de correo a su subdominio. Elija un subdominio para usar en Google Workspace para recibir correo electrónico de Microsoft 365 (por ejemplo, g.contosolandscaping2.m365master.com)

1. Iniciar en **la consola de administración de Google** (en admin.google.com)

2. Ir a **Administrar dominios**  >  **de**  >  **cuenta**

3. Seleccione **Agregar un dominio**

4. Escriba el nombre de dominio que seleccionó

5. Seleccionar **dominio de alias de usuario**

6. Seleccione **Agregar dominio & iniciar la verificación**

7. Espere a que se complete la verificación y actualice la página

8. Seleccione **Activar Gmail**

9. Elija **Omitir la configuración del registro MX** y, a continuación, seleccione **SIGUIENTE**

10. En el **cuadro de diálogo Enrutar** correo a otro servidor, tome nota del servidor al que enrutar el correo (por ejemplo, aspmx.l.google.com) y seleccione Uso otro servidor **de correo**

***Permitir que el correo electrónico Microsoft 365 omitir el filtro de CORREO NO DESEADO***

1. Para buscar un encabezado adecuado desde el Microsoft 365 inquilino, envíe un correo electrónico a un usuario en el área de trabajo de Google.

2. Abra el mensaje y seleccione **Mostrar original**

3. Elija un encabezado de correo electrónico que identifique exclusivamente el correo procedente de su Microsoft 365 inquilino. (Por ejemplo, X-MS-Exchange-CrossTenant-id: 92f60fc7-eab3-403b-9d7d-9d683bf0a4b5)

4. Ir a **la consola de administración de Google** en <https://admin.google.com>

5. Ir a **Aplicaciones**  >  **Google Workspace** Cumplimiento de  >  **Gmail**  >  

6. Vaya a **Cumplimiento de contenido** y seleccione **Configurar**

7. Asigne un nombre a la configuración. Por ejemplo, la lista Microsoft 365 correo electrónico.

8. En **mensajes de correo electrónico que afectan a la** comprobación De entrada

9. En **Agregar expresiones que describen el** contenido que desea buscar en cada mensaje, seleccione si alguno de los siguientes coincide con el **mensaje**

10. En **Expresiones,** seleccione **Agregar** xi. En **Agregar configuración,** elija **Coincidencia de contenido avanzada**

11. En **Ubicación,** elija **Encabezados completos**

12. En **Tipo de coincidencia,** elija **Texto completo**

13. En contenido, escriba el encabezado de correo electrónico que identifica exclusivamente el correo electrónico procedente de su espacio empresarial de Microsoft 365 (por ejemplo, X-MS-Exchange-CrossTenant-id: 92f60fc7-eab3-403b-9d7d-9d683bf0a4b5)

14. Seleccione **Guardar**

15. En si **coinciden las expresiones anteriores,** haga lo  siguiente en el campo Modificar mensaje > y active Omitir filtro de **correo** no deseado para este mensaje en Correo **no deseado.**

16. Seleccione **Guardar**

**Paso cuatro: Configurar Microsoft 365 configuración para la integración**

*Configurar el conector para enrutar el correo Microsoft 365 a Gmail:*

1. Vaya al **Centro de administración de Microsoft** en <https://admin.microsoft.com/AdminPortal>

2. Seleccione **Mostrar todo en** el menú de navegación de la izquierda.

3. En **Centros de administración,** **seleccione Exchange** para abrir el centro Exchange administración en una pestaña nueva

4. En el **Exchange** de navegación izquierdo del centro de administración, seleccione Conectores de flujo de correo, abra el menú desbordamiento (...) y seleccione  >  Agregar un conector

5. En **Conexión desde en** la ventana del nuevo **conector,** seleccione Office 365

6. En **Conexión para** seleccionar el servidor de correo electrónico de su organización, seleccione **Siguiente**

7. Escriba un **nombre** para el nuevo conector (por ejemplo: Para Gmail) y continúe **Siguiente**

8. En la **sección Uso del** conector, seleccione Solo cuando tenga configurada una regla de transporte que redirige los mensajes a este **conector** y seleccione **Siguiente.**

9. En la sección Enrutamiento, escriba el host de correo inteligente adecuado (por ejemplo, aspmx.l.google.com), seleccione y, a **+** continuación, continúe **Siguiente**.

10. En la **sección Restricciones de** seguridad, acepte la configuración predeterminada seleccionando **Siguiente**

11. En la **sección Correo electrónico de** validación , escriba una dirección de correo electrónico válida para el sistema de Gmail (por ejemplo, johannal@g.contosolandscaping2.m365master.com), seleccione el signo más **(+)** y, a continuación, seleccione **Validar**

12. Espere a que se complete la validación y, si se realiza correctamente, presione Siguiente

13. En **Revisar conector,** compruebe que la configuración es correcta y presione Crear conector

14. Cuando vea la notificación de conector creada, presione **Listo**

*Reenviar correo de Microsoft 365 buzones de correo a Gmail*

1. Use el **Administración de Microsoft 365 para** actualizar cada buzón o puede usar un script de **PowerShell,** como el siguiente:

    ```powershell
    $forwardingDomain = "g.contosolandscaping2.m365master.com"
    Connect-ExchangeOnline
    $Mailboxes = Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"}
    Foreach ($mbx in $mailboxes) {
    
    Set-Mailbox $mbx.Identity -DeliverToMailboxAndForward $true -ForwardingSMTPAddress $($mbx.Alias,$forwardingDomain -join "@")
    } 
    ```

*Configurar Exchange Online de transporte directo al calendario*

1. Al configurar esta configuración, se aceptarán automáticamente las invitaciones de calendario para que se muestren en un calendario Teams sin que los usuarios interactúen con la invitación en Outlook Web App.

2. El siguiente script se puede usar para crear las reglas de transporte:

    ```powershell
    Connect-ExchangeOnline
    New-TransportRule -Name "Direct to Calendar" -MessageTypeMatches Calendaring -SetHeaderName "X-MS-Exchange-Organization-CalendarBooking-Response" -SetHeaderValue Tentative
    New-TransportRule -Name "Direct to Calendar triage action" -MessageTypeMatches Calendaring -SetHeaderName "X-MS-Exchange-Organization-CalendarBooking-TriageAction" -SetHeaderValue MoveToDeletedItems
    
    ```

*Deshabilitar Outlook en la Web para buzones*

1. Siga las instrucciones de [Habilitar o deshabilitar Outlook en la Web para](/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-outlook-web-app) un buzón en Exchange Online para deshabilitar Outlook en la Web para buzones.

2. Puede deshabilitar el Outlook en la Web el Centro **Exchange de administración o** **PowerShell.** Puede usar el siguiente ejemplo de PowerShell para deshabilitar Outlook en la Web todos los buzones:

    ```powershell
    Connect-ExchangeOnline
    $Mailboxes = Get-Mailbox -ResultSize Unlimited -Filter {RecipientTypeDetails -eq "UserMailbox"}
    Foreach ($mbx in $mailboxes) {
    Set-CASMailbox $mbx.Identity -OWAEnabled $false
    }
    ```

**Paso 5: Configurar Exchange Online dominio para retransmisión interna**

Este paso garantiza que el correo electrónico se envía al sistema de terceros para su resolución final.

1. Vaya al **Centro de administración de Microsoft** en <https://admin.microsoft.com/AdminPortal>

2. En la navegación a la izquierda, selecciona **Mostrar todo**

3. En **Centros de administración,** **seleccione Exchange** para abrir Exchange de administración en una pestaña nueva

4. En **Exchange de administración,** seleccione **Flujo** de correo en el menú de navegación izquierdo y, a continuación, seleccione **Dominios aceptados**

5. Pulse en el nombre de dominio configurado en el sistema de terceros (por ejemplo, contosoLandscaping2.m365master.com)

    :::image type="content" source="media/essentials-internalrelay1.png" alt-text="Imagen que muestra la Exchange del Centro de administración para el flujo de correo.":::

6. Seleccione **Retransmisión interna y,** a continuación, haga clic **en Guardar**

    :::image type="content" source="media/essentials-internalrelay2.png" alt-text="Imagen que muestra el acto de guardar la configuración de retransmisión interna.":::

**Paso seis: Crear una regla para eliminar todo el correo entrante a Exchange Online excepto para Calendarios**

1. Puede configurar esta regla en el Centro de Exchange **o** **PowerShell.** Puede usar el siguiente ejemplo **de PowerShell** para crear la regla:

    ```powershell
    Connect-ExchangeOnline
    New-TransportRule -Name "Delete all except Calendaring" -ExceptIfMessageTypeMatches Calendaring -FromScope NotInOrganization -DeleteMessage:$true 
    
    ```

### <a name="connect-teams-essentials-to-third-party-email-not-using-vanity-domain-gmail-example"></a>Conectar Teams Essentials a correo electrónico de terceros que no usan dominio de vanidad (ejemplo de Gmail)

Puede programar y unirse Teams una reunión de Teams directamente desde Google Workspace conectando una cuenta de Gmail de consumidor a Teams Essentials con la dependencia principal del complemento [Teams G Suite.](https://support.microsoft.com/en-us/office/install-the-teams-meeting-add-on-for-google-workspace-bba2dfbe-0b2b-4ee7-be10-261ad80ddb60) Esto le ofrece la oportunidad de programar videoconferencias y audioconferencias con uso compartido de pantalla, chat de reunión, pizarras digitales y mucho más.

Configurará Gmail para extraer correo electrónico de Exchange Online para asegurarse de que el correo generado en Microsoft 365 y Teams llegan correctamente a Gmail. Es posible que sea necesario deshabilitar los valores predeterminados de seguridad para lograr esta conexión, lo que hace que el uso de una contraseña única segura sea esencial. No se requiere un dominio personalizado para este escenario, pero se puede configurar en Microsoft 365 para su uso en Gmail si desea usar uno.

:::image type="content" source="media/essentials-gmail.png" alt-text="Imagen que despicirá el flujo de correo entre Teams Essentials y Gmail":::

**Asegúrese de que tiene una cuenta de Gmail configurada.**

Si ya tiene una cuenta existente, puede continuar con el paso siguiente. Si no es así, visita [Crear nueva cuenta de Google](https://accounts.google.com/SignUp?hl=en) para configurar una nueva cuenta de Gmail.

**2. Configurar su Microsoft 365 inquilino**

*Configurar Teams AAD usuarios*

1. Siga las instrucciones de[Agregar usuarios y asigne licencias](/microsoft-365/admin/add-users/add-users?view=o365-worldwide&preserve-view=true) para agregar varios usuarios

*Configurar la protección de identidades*

1. Deshabilite los valores predeterminados de seguridad si están activos.

2. Configurar la autenticación multifactor para los usuarios

3. Si usa el acceso condicional, asegúrese de hacer una excepción para el acceso POP al buzón

*Agregar dominio al centro Administración de Microsoft 365 (opcional)*

1. En navegación, seleccione Configuración > dominio y, a continuación, seleccione Agregar dominio

2. Escriba el nombre de dominio en el campo correspondiente

3. Siga las instrucciones en pantalla para comprobar el dominio con el registro TXT

4. Cuando se le solicite, permita que Microsoft configure DNS

5. Complete las instrucciones para comprobar la ruta de registro MX a Microsoft 365

6. Configurar el registro TXT de SPF para incluir Microsoft 365

7. Complete las instrucciones para configurar registros TXT DKIM para Microsoft 365

8. Compruebe que DKIM está habilitado al cerrar sesión y volver a iniciar sesión en el Centro de administración

**3. Configurar Gmail**

1. Configurar Gmail para extraer Exchange Online correo electrónico en su sistema

2. Configurar el Teams calendario

3. Habilitar Gmail para usar el dominio empresarial (opcional)