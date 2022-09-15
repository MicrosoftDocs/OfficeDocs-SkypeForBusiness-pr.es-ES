---
title: Crear cuentas de recursos para salas y dispositivos compartidos de Teams
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
ms.custom: seo-marvel-apr2020
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: Lea este artículo para obtener información sobre cómo crear cuentas de recursos para salas y dispositivos compartidos, incluidos Salas de Microsoft Teams, Salas de Teams en Surface Hub y escritorio caliente en pantallas de Teams.
ms.openlocfilehash: 213cd2019aa23c296706c70a66e3e873f7527ee9
ms.sourcegitcommit: 424b14534aa269bb408c97c368102a193b481656
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67706637"
---
# <a name="create-and-configure-resource-accounts-for-rooms-and-shared-teams-devices"></a>Crear y configurar cuentas de recursos para salas y dispositivos compartidos de Teams

En este artículo se proporcionan pasos para crear cuentas de recursos para espacios compartidos y dispositivos, e incluye pasos para configurar cuentas de recursos para Salas de Microsoft Teams en Windows, Salas de Teams en Android, Salas de Teams en Surface Hub y pantallas de escritorio caliente en Teams.

Las cuentas de recursos de Microsoft 365 son cuentas de buzón y de Teams dedicadas a recursos específicos, como una sala o un proyector. Estas cuentas de recursos pueden responder automáticamente a las invitaciones a reuniones con reglas que defina cuando se creen. Por ejemplo, si tiene un recurso común, como una sala de conferencias, puede configurar una cuenta de recursos para esa sala de conferencias que aceptará o rechazará automáticamente invitaciones a reuniones en función de su disponibilidad del calendario. 

Cada cuenta de recursos es única para una única instalación Salas de Microsoft Teams o teams muestra la implementación de escritorio rápido.

> [!NOTE]
> Si usa paneles de Microsoft Teams, el Salas de Teams cuenta de recursos inicia sesión en Salas de Teams y en los paneles de Teams asociados.

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

> [!NOTE]
> **Skype Empresarial** <br><br>
> Si necesita habilitar la cuenta de recursos para que funcione con Skype Empresarial, vea [Implementar Salas de Microsoft Teams con Skype Empresarial Server](with-skype-for-business-server-2015.md)

## <a name="before-you-begin"></a>Antes de empezar

### <a name="requirements"></a>Requirements

En función de su entorno, necesita uno o más roles para crear cuentas de recursos.

|**Ambiente**|**Roles necesarios**|
|-----|-----|
|Azure Active Directory  <br/> |Administrador global o administrador de usuarios  <br/> |
|Active Directory  <br/> |Los administradores de empresa de Active Directory, los administradores de dominio o tienen derechos delegados para crear usuarios. Derechos de sincronización de Azure Active Directory Connect.  <br/> |
|Exchange Online  <br/> |Administrador global o administrador de Exchange   <br/> |
|Exchange Server  <br/> |Administración de la organización de Exchange o Administración de destinatarios   <br/> |

Si está creando cuentas de recursos para Salas de Teams, el UPN debe coincidir con la dirección SMTP de la cuenta de recursos. Consulte [Salas de Microsoft Teams requisitos](requirements.md) antes de implementar Salas de Teams.

### <a name="what-license-do-you-need"></a>¿Qué licencia necesita?

Antes de crear una cuenta de recursos de Microsoft 365, compruebe qué tipo de licencia necesita:

- **Reuniones de Teams** Si desea asociar la cuenta de recursos a un dispositivo compartido, como una sala de Microsoft Teams o una pantalla de Teams con escritorio rápido, y usarla para unirse a una reunión de Teams y que los asistentes puedan usarla para presentar vídeo y audio a través de ella, necesita una licencia de sala de reuniones. Para obtener más información sobre las licencias para salas de reuniones, consulte [Licencias](rooms-licensing.md) de salas de reuniones de Teams.

- **Llamadas RTC** Si desea que el recurso realice o reciba llamadas a un número de teléfono externo (denominado red telefónica conmutada o llamada RTC), necesita un sistema telefónico de Microsoft 365 o una licencia de Microsoft 365 Business Voice. Solo necesita completar el paso 1 en la siguiente información general. A continuación, consulte [Licencias de complementos de Microsoft Teams](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md) para obtener más información.

- Si solo usa una cuenta de recursos para reservar un recurso&mdash;, invite al recurso a la reunión y pídale que acepte o rechace automáticamente la invitación&mdash;que no necesita para asignar una licencia a la cuenta de recursos y solo necesita completar el paso 1 en la siguiente información general.  

## <a name="overview"></a>Información general

**Paso 1:** [Crear una nueva cuenta de recursos](#create-a-resource-account). O bien, si ya existe un buzón de sala y desea convertirlo en una cuenta de recursos, puede [modificar un buzón de sala de Exchange existente](?tabs=existing-account#create-a-resource-account).

**Paso 2:**  A continuación, [configure su cuenta](#configure-mailbox-properties) para Reuniones de Teams.

**Paso 3:**  Si la cuenta de recursos se va a asociar a un dispositivo compartido, como se muestra en Teams con hot-desking, [desactive la expiración de la contraseña](#turn-off-password-expiration).

**Paso 4:**  Por último, [asigne una licencia de sala de reuniones](#assign-a-meeting-room-license) para que la cuenta pueda acceder a Microsoft Teams.

Después de crear y configurar las cuentas de recursos, vea [Pasos siguientes](#next-steps) para revisar las tareas de configuración adicionales, incluidos los grupos de distribución, la funcionalidad de red y las llamadas.

## <a name="create-a-resource-account"></a>Crear una cuenta de recursos

> [!TIP]
> Al asignar un nombre a las cuentas de recursos, se recomienda usar una convención de nomenclatura estándar al principio de la dirección de correo electrónico. Esto ayudará a crear grupos dinámicos para facilitar la administración en Azure Active Directory. Por ejemplo, podría usar "mtr-" para todas las cuentas de recursos que se asociarán con Salas de Microsoft Teams.

> [!TIP]
> Le recomendamos que cree todas las cuentas de recursos con Exchange Online y Azure Active Directory.

Cree una cuenta de recursos con un método de una de las pestañas siguientes:

#### <a name="in-microsoft-365-admin-center"></a>[**En Centro de administración de Microsoft 365**](#tab/m365-admin-center)

1. Inicie sesión en el Centro de administración de Microsoft 365.

2. Proporcione las credenciales de administrador para su inquilino de Microsoft 365.

3. Vaya a **Recursos** en el panel izquierdo y, después, seleccione **Salas & equipamiento**. Si estas opciones no están disponibles en el panel izquierdo, es posible que primero tenga que seleccionar **Mostrar todo** .

4. Seleccione **Agregar recurso** para crear una nueva cuenta de salón. Escribe un nombre para mostrar y una dirección de correo electrónico para la cuenta, selecciona **Agregar** y, a continuación, **cerrar**.

5. De forma predeterminada, las cuentas de recursos están configuradas con las siguientes opciones:

    - Permitir la repetición de reuniones
    - Rechazar reuniones automáticamente fuera de los siguientes límites
      - Ventana de reservas (días): 180
      - Duración máxima (horas): 24
    - Aceptar automáticamente convocatorias de reunión

    Si desea cambiarlas, seleccione **Editar opciones de reserva** antes de seleccionar **Cerrar**. Si desea cambiarlos más adelante, vaya a **Salas** >  de recursos **& equipo**, seleccione la cuenta de recursos. A continuación, en **Opciones de reserva**, seleccione **Editar**.

6. Vaya a **Usuarios** > **activos** y seleccione el salón que creó para abrir el panel de propiedades.

7. A continuación, asigne una contraseña a la cuenta de recursos. En el panel, selecciona **Restablecer contraseña**.
 
8. Si se requiere que los usuarios cambien la contraseña en un dispositivo compartido, se producirán problemas de inicio de sesión. Desactive **Requerir que este usuario cambie su contraseña la primera vez que inicie sesión** y seleccione **Restablecer contraseña**.

9. En la sección **Licencias y aplicaciones** , establece **Seleccionar ubicación** en el país o la región donde se instalará el dispositivo. A continuación, seleccione la licencia que desea asignar, como Sala de reuniones, y seleccione **Guardar cambios**. La licencia puede variar en función de su organización.

Para cambiar la configuración del buzón de recursos, vea [Configurar las propiedades del buzón](#configure-mailbox-properties) o usar el Centro de administración de Exchange.

Es posible que también tenga que aplicar directivas de ancho de banda o directivas de reunión a esta cuenta. Consulte [Pasos siguientes](#next-steps) para obtener más información.

#### <a name="with-exchange-online"></a>[**Con Exchange Online**](#tab/exchange-online)

1. Conéctese a [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

    ``` PowerShell
    Connect-ExchangeOnline
    ```

2. De forma predeterminada, los buzones de sala no tienen cuentas asociadas. Agregue una cuenta al crear un buzón de sala para que pueda autenticarse con Microsoft Teams.

    Si está creando un nuevo buzón de recursos:
    
    ``` PowerShell
    New-Mailbox -MicrosoftOnlineServicesID <Office365 ID> -Name <String> -Alias <string> -Room -EnableRoomMailboxAccount $true  -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
    ```
    
    En este ejemplo se crea un buzón de sala con la siguiente configuración:

    - Cuenta: ConferenceRoom01@contoso.com
          
    - Nombre: ConferenceRoom01
        
     - Alias: ConferenceRoom01
        
     - Contraseña de la cuenta: P@$$W 0rd5959

    ``` PowerShell
    New-Mailbox -MicrosoftOnlineServicesID ConferenceRoom01@contoso.com -Name "ConferenceRoom01" -Alias ConferenceRoom01 -Room -EnableRoomMailboxAccount $true  -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
    ```

Si no está en una configuración híbrida de Exchange, puede continuar con el paso siguiente, [Configurar las propiedades del buzón](#configure-mailbox-properties).

Si se encuentra en una configuración híbrida de Exchange, debe agregar una dirección de correo electrónico para su cuenta de dominio local. Vea [Sincronizar directorios de cuentas de usuario locales y Office 365](https://support.microsoft.com/topic/how-to-use-smtp-matching-to-match-on-premises-user-accounts-to-office-365-user-accounts-for-directory-synchronization-75673b94-e1b8-8a9e-c413-ee5a2a1a6a78) para obtener más información.

#### <a name="with-exchange-server"></a>[**Con Exchange Server**](#tab/exchange-server)

  1. Conéctese al Shell de administración de Exchange. [Abra el Shell de administración de Exchange](/powershell/exchange/exchange-server/open-the-exchange-management-shell) o [conéctese al servidor de Exchange con PowerShell remoto](/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell).

   2. Para crear un buzón de sala:

      ``` PowerShell
      New-Mailbox -UserPrincipalName <UPN> -Name <String> -Alias <String> -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
      ```
     
   En este ejemplo se crea un buzón de sala con la siguiente configuración:

   - Cuenta: ConferenceRoom01@contoso.com
  
   - Nombre: ConferenceRoom01

   - Alias: ConferenceRoom01

   - Contraseña de la cuenta: P@$$W 0rd5959

   ``` PowerShell
   New-Mailbox -UserPrincipalName ConferenceRoom01@contoso.com -Name "ConferenceRoom01" -Alias ConferenceRoom01 -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
   ```

#### <a name="modify-an-existing-exchange-room-mailbox"></a>[**Modificar un buzón de exchange existente**](#tab/existing-account)

Para modificar un buzón de sala existente para que se convierta en una cuenta de recursos, use la siguiente sintaxis:

``` PowerShell
Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
```

En este ejemplo se habilita la cuenta para el buzón de sala existente que tiene el valor de alias ConferenceRoom02 y se establece la contraseña en 9898P@$$W 0rd.

``` PowerShell
Set-Mailbox -Identity ConferenceRoom02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
```

Si se encuentra en una configuración híbrida de Exchange, también deberá agregar una dirección de correo electrónico para su cuenta de dominio local. Vea [Sincronizar directorios de cuentas de usuario locales y Office 365](https://support.microsoft.com/topic/how-to-use-smtp-matching-to-match-on-premises-user-accounts-to-office-365-user-accounts-for-directory-synchronization-75673b94-e1b8-8a9e-c413-ee5a2a1a6a78) para obtener más información.

Para obtener información detallada sobre la sintaxis y los parámetros, vea [New-Mailbox](/powershell/module/exchange/mailboxes/new-mailbox) y [Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox).

> [!NOTE]
> Si vas a crear esta cuenta para Salas de Teams en Surface Hub, también debes habilitar ActiveSync en esta cuenta. Esto te permitirá enviar correo directamente desde Surface Hub, que puedes usar para características como Whiteboard. Consulta [Aplicar directivas de ActiveSync a cuentas de dispositivo (Surface Hub)](/surface-hub/apply-activesync-policies-for-surface-hub-device-accounts) para obtener más información.

---

> [!IMPORTANT]
> Si solo usa esta cuenta de recursos para reservar espacio y acepta o rechaza automáticamente invitaciones, ya ha completado la configuración. Si usa esta cuenta de recursos para las llamadas RTC, consulte [Licencias de complementos de Microsoft Teams](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md) para determinar qué licencia necesita.
>
> Continúe con la siguiente sección solo si la cuenta de recursos es para una Salas de Teams en Windows, Salas de Teams en Android, Salas de Teams en Surface Hub o una pantalla de Teams con escritorio rápido.

## <a name="configure-mailbox-properties"></a>Configurar las propiedades del buzón

En Exchange PowerShell, ya sea en línea o local, configure las siguientes opciones en el buzón de sala para mejorar la experiencia de reunión:

- **AutomateProcessing: `AutoAccept`** Los organizadores de la reunión reciben la decisión de reserva de la sala directamente sin la intervención humana.

- **AddOrganizerToSubject: `$false`** El organizador de la reunión no se agrega al asunto de la convocatoria de reunión.

- **DeleteComments: `$false`** Mantenga cualquier texto en el cuerpo del mensaje de las convocatorias de reunión entrantes. Esto es necesario para procesar reuniones externas de Teams y de terceros para proporcionar una experiencia de unirse a one touch.

- **DeleteSubject: `$false`** Mantenga el asunto de las convocatorias de reunión entrantes.

- **ProcessExternalMeetingMessages: `$true`** Especifica si se procesarán las convocatorias de reunión que se originen fuera de la organización de Exchange. Necesario para reuniones de Teams externas y [reuniones de terceros](/microsoftteams/rooms/third-party-join).

- **RemovePrivateProperty: `$false`** Garantiza que la marca privada que envió el organizador de la reunión en la convocatoria de reunión original permanece según lo especificado.

- **AddAdditionalResponse: `$true`** El texto especificado por el parámetro AdditionalResponse se agrega a las convocatorias de reunión.

- **AdditionalResponse: "¡Esta es una sala de reuniones de Microsoft Teams!"** El texto adicional que se agregará a la respuesta de aceptación de la reunión.

En este ejemplo se configuran estas opciones en un buzón de sala denominado ConferenceRoom01:

``` PowerShell
Set-CalendarProcessing -Identity "ConferenceRoom01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -ProcessExternalMeetingMessages $true -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams Meeting room!"
```

Para obtener información detallada sobre la sintaxis y los parámetros, consulte [Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing).

## <a name="turn-off-password-expiration"></a>Desactivar la expiración de la contraseña

Si la contraseña de la cuenta de recursos expira, el dispositivo no inicia sesión después de la fecha de expiración. La contraseña tendrá que cambiarse para la cuenta de recursos y, a continuación, actualizarse en cada dispositivo. Para evitar esto, puede desactivar la expiración de la contraseña.
  
> [!NOTE]
> Establecer **la contraseña nunca expira** es un requisito para los dispositivos compartidos de Microsoft Teams. Si las reglas de su dominio prohíben las contraseñas que no expiran, tendrá que crear una excepción para cada cuenta de recursos de dispositivo de Teams.

Siga los pasos de una de las siguientes pestañas para desactivar la expiración de la contraseña:

#### <a name="azure-active-directory-20"></a>[**Azure Active Directory 2.0**](#tab/azure-active-directory2-password/)

En primer lugar, conéctese a PowerShell de Active Directory:

```PowerShell
   Connect-AzureAD
```

A continuación, consulta [Establecer una contraseña para que nunca expire](/microsoft-365/admin/add-users/set-password-to-never-expire#set-a-password-to-never-expire).

En este ejemplo se establece que la contraseña de la cuenta ConferenceRoom01@contoso.com no expire nunca.

```PowerShell
Set-AzureADUser -ObjectID ConferenceRoom01@contoso.com -PasswordPolicies DisablePasswordExpiration
```

#### <a name="azure-active-directory-10"></a>[**Azure Active Directory 1.0**](#tab/azure-active-directory1-password/)

 1. Conectarse a PowerShell de MSOnline:

       ```PowerShell
       Connect-MsolService
       ```

       Para obtener más información sobre Active Directory, consulte [Azure Active Directory (MSOnline)](/powershell/azure/active-directory/overview?view=azureadps-1.0&preserve-view=true).

2. Establezca la contraseña para que nunca expire con la siguiente sintaxis:

    ```PowerShell
    Set-MsolUser -UserPrincipalName <userPrincipalName> -PasswordNeverExpires $true
    ```

    En este ejemplo se establece que la contraseña de la cuenta ConferenceRoom01@contoso.com no expire nunca.

    ```PowerShell
    Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -PasswordNeverExpires $true
    ```

#### <a name="active-directory-on-premises"></a>[**Active Directory (local)**](#tab/active-directory1-password/)

1. Conectarse a PowerShell de Active Directory:

    ```PowerShell
       Import-Module ActiveDirectory
    ```
    
    Para obtener más información sobre PowerShell de Active Directory, vea [ActiveDirectory](/powershell/module/activedirectory/).

2. Establezca la contraseña para que nunca expire con la siguiente sintaxis:

    ```PowerShell
    Set-ADUser -Identity <samAccountName> -PasswordNeverExpires $true
    ```

    En este ejemplo se establece que la contraseña de la cuenta ConferenceRoom01@contoso.com no expire nunca.

    ```PowerShell
    Set-ADUser -Identity ConferenceRoom01@contoso.com -PasswordNeverExpires $true
    ```

---

## <a name="assign-a-meeting-room-license"></a>Asignar una licencia de sala de reuniones

La cuenta de recursos necesita una licencia de Microsoft 365 o Office 365 para iniciar sesión en Microsoft Teams.

> [!NOTE]
> Salas de Microsoft Teams Basic y Salas de Microsoft Teams Pro son las dos SKU disponibles para dispositivos de salas de reuniones compartidas, incluidos Salas de Teams. Se requiere una licencia de sala de reuniones para las pantallas de Teams con escritorio caliente. Para obtener más información, vea [Salas de Microsoft Teams licencias](rooms-licensing.md).

Para asignar licencias con la Centro de administración de Microsoft 365, vea [Asignar licencias a usuarios](/microsoft-365/admin/manage/assign-licenses-to-users). Para asignar licencias con Azure AD, consulte una de las siguientes pestañas:

#### <a name="active-directory-20"></a>[**Active Directory 2.0**](#tab/active-directory2-license/)


1. Conectarse a Azure AD
  
    ```PowerShell
    Connect-AzureAD
    ```

     Para obtener más información sobre Active Directory, consulte [PowerShell de Azure Active Directory para Graph](/powershell/azure/active-directory/overview?view=azureadps-2.0&preserve-view=true).
    
2. Asigne una ubicación de uso a su cuenta de recursos mediante el `Set-AzureADUser` cmdlet. Esto determina qué SKU de licencia están disponibles.

    En este ejemplo, el usuario se encuentra en la Estados Unidos (EE. UU.):

    ```PowerShell
    Set-AzureADUser -ObjectID ConferenceRoom01@contoso.com -UsageLocation 'US'
    ```

3. A continuación, use `Get-AzureADSubscribedSku` esta opción para recuperar una lista de sku disponibles para su organización de Microsoft 365 o Office 365.

    ```PowerShell
    Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
    ```

4. Para asignar la licencia, use el `Set-AzureADUser` cmdlet y convierta el id. de SKU de licencia (vea el paso 2) en un objeto de tipo de licencia de PowerShell. Después, asigne ese objeto a la cuenta de recursos. En el ejemplo siguiente, el id. de SKU de licencia es 6070a4c8-34c6-4937-8dfb-39bbc6397a60 y se asigna a la cuenta conferenceroom01@contoso.com:

    ```PowerShell
    #Create an object for a single license type
    $License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense 
    $License.SkuId = "6070a4c8-34c6-4937-8dfb-39bbc6397a60" 
       
    #Create an object for a multiple license type
    $Licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses 
       
    #Add the single license object to the multiple license object
    $Licenses.AddLicenses = $License 
       
    #Assign the license to the resource account
    Set-AzureADUserLicense -ObjectId ConferenceRoom01@contoso.com -AssignedLicenses $Licenses
    ```

#### <a name="active-directory-10"></a>[**Active Directory 1.0**](#tab/active-directory1-license/)

1. Conéctese a PowerShell de MSOnline.

   ```PowerShell
   Connect-MsolService
   ```

    Para obtener más información sobre Active Directory, vea [Azure Active Directory (MSOnline).](/powershell/azure/active-directory/overview?view=azureadps-1.0&preserve-view=true)

2.  Asigne una ubicación de uso a su cuenta de recursos mediante el `Set-MsolUser` cmdlet. Esto determina qué SKU de licencia están disponibles.

    En este ejemplo, el usuario se encuentra en la Estados Unidos (EE. UU.).
    
    ```PowerShell
    Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -UsageLocation 'US'
    ```
    
    A continuación, puede usar `Get-MsolAccountSku` para recuperar una lista de SKU disponibles para su organización de Microsoft 365 o Office 365.

4. Para asignar la licencia, use el `Set-MsolUser` cmdlet. En este ejemplo, se asigna la licencia "contoso:MEETING_ROOM" a la cuenta conferenceroom01@contoso.com:

    ```PowerShell
    Set-MsolUserLicense -UserPrincipalName 'ConferenceRoom01@contoso.com' -AddLicenses 'contoso:MEETING_ROOM'
    ```

---

Para validar la creación de la cuenta y la asignación de licencias, inicie sesión en cualquier cliente de Teams con la cuenta que ha creado.

## <a name="next-steps"></a>Pasos siguientes

### <a name="meeting-policies"></a>Directivas de reunión

Es posible que deba aplicar directivas personalizadas de red, ancho de banda o reunión a esta cuenta. Para obtener más información sobre las directivas de ancho de banda y de red, vea Configuración de la [directiva de reunión para audio & vídeo](/microsoftteams/meeting-policies-audio-and-video). Para Salas de Teams, le recomendamos que establezca el ancho de banda de la directiva de reunión en 10 Mbps.

Para fines de colaboración, active PowerPoint Live, Whiteboard y notas compartidas. Se recomienda que habilite la configuración de directiva de reunión "Reunirse ahora en reuniones privadas". Es posible que desee crear una directiva de reunión para ajustar la configuración de participantes e invitados para Salas de Teams. Por ejemplo, revise la configuración de la sala de espera, como qué asistentes admitirán automáticamente en las reuniones. Para obtener más información sobre las directivas de reunión de Teams, vea [Administrar directivas de reunión en Microsoft Teams](/microsoftteams/meeting-policies-overview).

### <a name="calling"></a>Llamadas

No hay requisitos únicos para habilitar las llamadas con cuentas de recursos. Habilite la cuenta de recursos para llamar de la misma manera que habilita un usuario normal.

> [!NOTE]
> Se recomienda desactivar el correo de voz para dispositivos compartidos asignando una directiva de llamada a las cuentas de recursos de dispositivo. Consulte [Llamadas y desvío de llamadas en Teams](../teams-calling-policy.md) para obtener más información.

### <a name="configure-distribution-groups-for-teams-calendar"></a>Configurar grupos de distribución para el calendario de Teams

Para organizar las ubicaciones de las salas de reuniones, puede agregar sus cuentas de recursos de dispositivo a los grupos de distribución de Exchange. Por ejemplo, si tiene oficinas en tres ubicaciones geográficas diferentes, puede crear tres grupos de distribución y agregar las cuentas de recursos adecuadas a cada ubicación. Para obtener más información, vea [Crear una lista de salas](/exchange/recipients/room-mailboxes?view=exchserver-2019&preserve-view=true#create-a-room-list).

### <a name="configure-places-for-outlook-calendar"></a>Configurar lugares para Calendario de Outlook
Para que las ubicaciones de las salas de reuniones aparezcan en el Buscador de salas de Outlook, debe usar el cmdlet de PowerShell de Set-Place Exchange. No solo Set-Place rellenar el Buscador de salas en Outlook, también le permite agregar metadatos adicionales, como la capacidad de la sala o el suelo de la construcción de la sala. Para obtener más información, consulte [Set-Place](/powershell/module/exchange/set-place).

## <a name="related-articles"></a>Artículos relacionados

[Configurar cuentas para Salas de Microsoft Teams](rooms-configure-accounts.md)

[Plan para Salas de Microsoft Teams](rooms-plan.md)

[Implementar Salas de Microsoft Teams](rooms-deploy.md)

[Administrar Salas de Microsoft Teams](rooms-manage.md)

[Licencias de Salas de Microsoft Teams](rooms-licensing.md)
