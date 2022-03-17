---
title: Crear cuentas de recursos para salas y dispositivos Teams compartidos
ms.author: czawideh
author: cazawideh
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
ms.custom: seo-marvel-apr2020
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: Lea este artículo para obtener información sobre cómo crear cuentas de recursos para salas y dispositivos compartidos, incluidos Salas de Microsoft Teams, Salas de Teams en Surface Hub y escritorio en Teams pantallas.
ms.openlocfilehash: e7525a9e9ec6737bab18de4351675d567b61611b
ms.sourcegitcommit: dafe48cea1643e1bd79390482da9b002d7e9e0bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/16/2022
ms.locfileid: "63514551"
---
# <a name="create-and-configure-resource-accounts-for-rooms-and-shared-teams-devices"></a>Crear y configurar cuentas de recursos para salas y dispositivos Teams compartidos

En este artículo se proporcionan pasos para crear cuentas de recursos para espacios y dispositivos compartidos, e incluye pasos para configurar cuentas de recursos para Salas de Microsoft Teams en Windows, Salas de Teams en Android, Salas de Teams en Surface Hub y escritorio en caliente en Teams pantallas.

Microsoft 365 de recursos son cuentas de buzón Teams que están dedicadas a recursos específicos, como un salón o un proyector. Estas cuentas de recursos pueden responder automáticamente a las invitaciones a reuniones mediante reglas que defina cuando se crean. Por ejemplo, si tiene un recurso común como una sala de conferencias, puede configurar una cuenta de recursos para esa sala de conferencias que aceptará o rechazará automáticamente las invitaciones a reuniones según la disponibilidad del calendario.

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

> [!NOTE]
> **Skype Empresarial** <br><br>
> Si necesita habilitar la cuenta de recursos para que funcione con Skype Empresarial, vea Implementar Salas de Microsoft Teams [con Skype Empresarial Server](with-skype-for-business-server-2015.md)

## <a name="before-you-begin"></a>Antes de empezar

### <a name="requirements"></a>Requirements

Según su entorno, necesita uno o varios roles para crear cuentas de recursos.

|**Entorno**|**Roles obligatorios**|
|-----|-----|
|Azure Active Directory  <br/> |Administrador global o administrador de usuarios  <br/> |
|Active Directory  <br/> |Active Directory Enterprise administradores, administradores de dominios o tienen derechos delegados para crear usuarios. Azure Active Directory Conectar derechos de sincronización.  <br/> |
|Exchange Online  <br/> |Administrador global o Exchange administrador   <br/> |
|Exchange Server  <br/> |Exchange organización o administración de destinatarios   <br/> |

Si va a crear cuentas de recursos para Salas de Teams, el UPN debe coincidir con la dirección SMTP de la cuenta de recursos. Consulte [Salas de Microsoft Teams requisitos antes](requirements.md) de implementar Salas de Teams.

### <a name="what-license-do-you-need"></a>¿Qué licencia necesita?

Antes de crear una Microsoft 365 de recursos, compruebe qué tipo de licencia necesita:

- **Teams** Reuniones Si desea asociar la cuenta de recursos a un dispositivo compartido, como una sala de Microsoft Teams o una pantalla Teams con escritorio en caliente, y úsela para unirse a una reunión de Teams para que los asistentes puedan usarla para presentar vídeo y audio a través de ella, necesita una licencia de Sala de reuniones. Para obtener más información sobre las licencias de salas de reuniones, [vea Teams Sala de reuniones licencias](rooms-licensing.md).

- **Llamadas RTC** Si desea que el recurso realice o reciba llamadas desde o hacia un número de teléfono externo (denominado Red telefónica conmutada pública o llamada RTC), necesita una licencia de Microsoft 365 Sistema telefónico o Microsoft 365 Business Voice teléfono. Solo necesita completar el paso 1 en la siguiente información general. A continuación, [vea Microsoft Teams de complementos para](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md) obtener más información.

- Si solo usa una cuenta de recursos para reservar un recurso,&mdash; invite el recurso a&mdash; la reunión y pídale que acepte o rechace automáticamente la invitación que no necesita para asignar una licencia a la cuenta de recursos y solo necesita completar el paso 1 en la siguiente información general.  

## <a name="overview"></a>Información general

**Paso 1: crear** [una nueva cuenta de recursos](#create-a-resource-account). O bien, si ya existe un buzón de sala y desea convertirlo en una cuenta de recurso, puede modificar un buzón de Exchange [sala existente](?tabs=existing-account#create-a-resource-account).

**Paso 2 -**  Después, [configure su cuenta para](#configure-mailbox-properties) Teams reuniones.

**Paso 3 -**  Si la cuenta de recursos va a estar asociada a un dispositivo compartido, como Teams pantallas con hot-desking, desactive la expiración [de la contraseña](#turn-off-password-expiration).

**Paso 4 -**  Por último, [asigne una licencia de sala de reuniones](#assign-a-meeting-room-license) para que la cuenta pueda acceder a Microsoft Teams.

Después de crear y configurar las cuentas de recursos, [](#next-steps) vea Pasos siguientes para revisar las tareas de configuración adicionales, incluidos los grupos de distribución, la capacidad de red y las llamadas.

## <a name="create-a-resource-account"></a>Crear una cuenta de recursos

> [!TIP]
> Al asignar un nombre a las cuentas de recursos, se recomienda usar una convención de nomenclatura estándar al principio de la dirección de correo electrónico. Esto le ayudará a crear grupos dinámicos para facilitar la administración en Azure Active Directory. Por ejemplo, puede usar "mtr-" para todas las cuentas de recursos que se asociarán con Salas de Microsoft Teams.

> [!TIP]
> Le recomendamos que cree todas las cuentas de recursos Exchange Online y Azure Active Directory.

Cree una cuenta de recurso con un método de una de las siguientes pestañas:

#### <a name="in-microsoft-365-admin-center"></a>[**En Centro de administración de Microsoft 365**](#tab/m365-admin-center)

1. Inicie sesión en el Centro de administración de Microsoft 365.

2. Proporcione las credenciales de administrador para su Microsoft 365 inquilino.

3. Vaya a **Recursos** en el panel izquierdo y, a continuación, seleccione **Salas & equipo**. Si estas opciones no están disponibles en el panel izquierdo, es posible que deba seleccionar **Mostrar todo primero** .

4. Seleccione **Agregar un buzón de recursos** para crear una nueva cuenta de salón. Escriba un nombre para mostrar y una dirección de correo electrónico para la cuenta, seleccione **Agregar** y, a continuación, **seleccione Cerrar**.

5. De forma predeterminada, las cuentas de recursos se configuran con la siguiente configuración:

    - Permitir reuniones repetidas
    - Rechazar automáticamente reuniones fuera de los límites siguientes
      - Ventana de reserva (días): 180
      - Duración máxima (horas): 24
    - Aceptar automáticamente las solicitudes de reunión

    Si desea cambiarlas, seleccione **Establecer opciones de programación** antes de seleccionar **Cerrar**. Si desea cambiarlas más adelante, vaya a **ResourcesRooms** >  **& equipo**, seleccione la cuenta de recursos. A continuación, **en Opciones de reserva**, seleccione **Editar**.

6. Vaya a **UsuariosActivos** >  y seleccione el salón que creó para abrir el panel de propiedades.

7. A continuación, asigne una contraseña a la cuenta de recursos. En el panel, seleccione **Restablecer contraseña**.
 
8. Requerir que los usuarios cambien la contraseña en un dispositivo compartido causará problemas de inicio de sesión. Desactive **Requerir que este usuario cambie su contraseña al iniciar sesión** por primera vez y seleccione **Restablecer**.

9. En la **sección Licencias y aplicaciones** , establezca **Seleccionar ubicación** en el país o región donde se instalará el dispositivo. A continuación, seleccione la licencia que desea asignar, como Sala de reuniones, y seleccione **Guardar cambios**. La licencia puede variar según su organización.

Para cambiar la configuración del buzón de recursos, vea [Configurar las](#configure-mailbox-properties) propiedades del buzón o usar el centro Exchange de administración.

Es posible que también tenga que aplicar directivas de ancho de banda o directivas de reunión a esta cuenta. Vea [Pasos siguientes para](#next-steps) obtener más información.

#### <a name="with-exchange-online"></a>[**Con Exchange Online**](#tab/exchange-online)

1. Conectar a [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

    ``` PowerShell
    Connect-ExchangeOnline
    ```

2. De forma predeterminada, los buzones de sala no tienen cuentas asociadas. Agregue una cuenta al crear un buzón de sala para que pueda autenticarse con Microsoft Teams.

    Si va a crear un buzón de recursos nuevo:
    
    ``` PowerShell
    New-Mailbox -MicrosoftOnlineServicesID <Office365 ID> -Name <String> -Alias <string> -Room -EnableRoomMailboxAccount $true  -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
    ```
    
    En este ejemplo se crea un nuevo buzón de sala con la siguiente configuración:

        - Account: ConferenceRoom01@contoso.com
          
        - Name: ConferenceRoom01
        
        - Alias: ConferenceRoom01
        
        - Account password: P@$$W0rd5959

    ``` PowerShell
    New-Mailbox -MicrosoftOnlineServicesID ConferenceRoom01@contoso.com -Name "ConferenceRoom01" -Alias ConferenceRoom01 -Room -EnableRoomMailboxAccount $true  -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
    ```

Si no está en una configuración híbrida Exchange, puede continuar con el siguiente paso, [Configurar propiedades del buzón](#configure-mailbox-properties).

Si está en una configuración híbrida Exchange, debe agregar una dirección de correo electrónico para su cuenta de dominio local. Para [obtener más información, vea Sincronizar directorios de cuentas de](https://support.microsoft.com/topic/how-to-use-smtp-matching-to-match-on-premises-user-accounts-to-office-365-user-accounts-for-directory-synchronization-75673b94-e1b8-8a9e-c413-ee5a2a1a6a78) Office 365 locales y de usuario.

#### <a name="with-exchange-server"></a>[**Con Exchange Server**](#tab/exchange-server)

  1. Conectar para Exchange Shell de administración. [Abra el Exchange de administración](/powershell/exchange/exchange-server/open-the-exchange-management-shell) o conéctese a su [servidor Exchange con PowerShell remoto](/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell).

   2. Para crear un buzón de sala nuevo:

      ``` PowerShell
      New-Mailbox -UserPrincipalName <UPN> -Name <String> -Alias <String> -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
      ```
     
   En este ejemplo se crea un nuevo buzón de sala con la siguiente configuración:

   - Cuenta: ConferenceRoom01@contoso.com
  
   - Nombre: ConferenceRoom01

   - Alias: ConferenceRoom01

   - Contraseña de la cuenta: P@$$W 0rd5959

   ``` PowerShell
   New-Mailbox -UserPrincipalName ConferenceRoom01@contoso.com -Name "ConferenceRoom01" -Alias ConferenceRoom01 -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
   ```

#### <a name="modify-an-existing-exchange-room-mailbox"></a>[**Modificar un buzón de Exchange sala existente**](#tab/existing-account)

Para modificar un buzón de sala existente para convertirse en una cuenta de recursos, use la sintaxis siguiente:

``` PowerShell
Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
```

En este ejemplo, se habilita la cuenta para el buzón de sala existente que tiene el valor de alias ConferenceRoom02 y se establece la contraseña en 9898P@$$W 0rd.

``` PowerShell
Set-Mailbox -Identity ConferenceRoom02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
```

Si está en una configuración Exchange híbrida, también tendrá que agregar una dirección de correo electrónico para su cuenta de dominio local. Para [obtener más información, vea Sincronizar directorios de cuentas de](https://support.microsoft.com/topic/how-to-use-smtp-matching-to-match-on-premises-user-accounts-to-office-365-user-accounts-for-directory-synchronization-75673b94-e1b8-8a9e-c413-ee5a2a1a6a78) Office 365 locales y de usuario.

Para obtener información detallada sobre la sintaxis y los parámetros, vea [Nuevo buzón](/powershell/module/exchange/mailboxes/new-mailbox) y [Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox).

> [!NOTE]
> Si va a crear esta cuenta para Teams room en Surface Hub, también debe habilitar ActiveSync en esta cuenta. Esto le permitirá enviar correo electrónico directamente desde el Surface Hub, que puede usar para características como Whiteboard. Vea [Aplicar directivas de ActiveSync a cuentas de dispositivo (Surface Hub) para](/surface-hub/apply-activesync-policies-for-surface-hub-device-accounts) obtener más información.

---

> [!IMPORTANT]
> Si solo usa esta cuenta de recursos para reservar espacio y aceptar o rechazar invitaciones automáticamente, ha completado la configuración. Si usa esta cuenta de recurso para las llamadas RTC, [consulte](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md) Microsoft Teams de complementos para determinar qué licencia necesita.
>
> Continúe con la siguiente sección solo si la cuenta de recursos es para un Salas de Teams en Windows, Salas de Teams en Android, Salas de Teams en Surface Hub o una pantalla Teams con escritorio en caliente.

## <a name="configure-mailbox-properties"></a>Configurar las propiedades del buzón

En Exchange PowerShell, ya sea en línea o local, configure la siguiente configuración en el buzón de sala para mejorar la experiencia de reunión:

- **Automatizarproceso: `AutoAccept`** Los organizadores de la reunión reciben la decisión de reserva de la sala directamente sin intervención humana.

- **AddOrganizerToSubject: `$false`** El organizador de la reunión no se agrega al asunto de la solicitud de reunión.

- **DeleteComments: `$false`** Conserve cualquier texto en el cuerpo del mensaje de las solicitudes de reunión entrantes. Esto es necesario para procesar reuniones Teams y de terceros para proporcionar una experiencia de unirse a One Touch.

- **DeleteSubject: `$false`** Mantenga el asunto de las solicitudes de reunión entrantes.

- **ProcessExternalMeetingMessages: `$true`** Especifica si desea procesar las solicitudes de reunión que se originan fuera de la Exchange organización. Necesario para reuniones Teams y reuniones [de terceros](/microsoftteams/rooms/third-party-join).

- **RemovePrivateProperty: `$false`** Garantiza que la marca privada enviada por el organizador de la reunión en la solicitud de reunión original permanece como se ha especificado.

- **AddAdditionalResponse: `$true`** El texto especificado por el parámetro AdditionalResponse se agrega a las solicitudes de reunión.

- **AdditionalResponse: "Esta es una sala Microsoft Teams reunión"** El texto adicional que se agregará a la respuesta de aceptación de la reunión.

En este ejemplo se configuran estas opciones en un buzón de sala denominado ConferenceRoom01:

``` PowerShell
Set-CalendarProcessing -Identity "ConferenceRoom01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -ProcessExternalMeetingMessages $true -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams Meeting room!"
```

Para obtener información detallada sobre la sintaxis y los parámetros, vea [Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing).

## <a name="turn-off-password-expiration"></a>Desactivar la expiración de la contraseña

Si la contraseña de la cuenta de recursos expira, el dispositivo no inicia sesión después de la fecha de expiración. La contraseña tendrá que cambiarse para la cuenta de recursos y, a continuación, actualizarse en cada dispositivo. Para evitar esto, puede desactivar la expiración de la contraseña.
  
> [!NOTE]
> Establecer **contraseña nunca expira es** un requisito para dispositivos Microsoft Teams compartidos. Si las reglas de dominio prohíben las contraseñas que no expiran, deberá crear una excepción para cada Teams de recursos de dispositivo.

Siga los pasos de una de las siguientes pestañas para desactivar la expiración de la contraseña:

#### <a name="azure-active-directory-20"></a>[**Azure Active Directory 2.0**](#tab/azure-active-directory2-password/)

En primer lugar, Conectar PowerShell de Active Directory:

```PowerShell
   Connect-AzureAD
```

A continuación, [vea Establecer una contraseña para que nunca expire](/microsoft-365/admin/add-users/set-password-to-never-expire?view=o365-worldwide#set-a-password-to-never-expire).

En este ejemplo se establece la contraseña de la cuenta ConferenceRoom01@contoso.com que nunca expire.

```PowerShell
Set-AzureADUser -ObjectID ConferenceRoom01@contoso.com -PasswordPolicies DisablePasswordExpiration
```

#### <a name="azure-active-directory-10"></a>[**Azure Active Directory 1,0**](#tab/azure-active-directory1-password/)

 1. Conectar a MSOnline PowerShell:

       ```PowerShell
       Connect-MsolService
       ```

       Para obtener más información sobre Active Directory, [vea Azure Active Directory (MSOnline)](/powershell/azure/active-directory/overview?view=azureadps-1.0).

2. Establezca la contraseña para que nunca expire con la sintaxis siguiente:

    ```PowerShell
    Set-MsolUser -Identity <samAccountName> -PasswordNeverExpires $true
    ```

    En este ejemplo se establece la contraseña de la cuenta ConferenceRoom01@contoso.com que nunca expire.

    ```PowerShell
    Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -PasswordNeverExpires $true
    ```

#### <a name="active-directory-on-premises"></a>[**Active Directory (local)**](#tab/active-directory1-password/)

1. Conectar PowerShell de Active Directory:

    ```PowerShell
       Import-Module ActiveDirectory
    ```
    
    Para obtener más información sobre PowerShell de Active Directory, vea [ActiveDirectory](/powershell/module/activedirectory/?view=windowsserver2022-ps).

2. Establezca la contraseña para que nunca expire con la sintaxis siguiente:

    ```PowerShell
    Set-ADUser -Identity <samAccountName> -PasswordNeverExpires $true
    ```

    En este ejemplo se establece la contraseña de la cuenta ConferenceRoom01@contoso.com que nunca expire.

    ```PowerShell
    Set-ADUser -Identity ConferenceRoom01@contoso.com -PasswordNeverExpires $true
    ```

---

## <a name="assign-a-meeting-room-license"></a>Asignar una licencia de sala de reuniones

La cuenta de recursos necesita una licencia Microsoft 365 o Office 365 para iniciar sesión en Microsoft Teams.

> [!NOTE]
> Salas de Microsoft Teams Estándar y Salas de Microsoft Teams Premium son las dos SKU disponibles para dispositivos de salas de reuniones compartidas, incluidas Salas de Teams. Se requiere una licencia de sala de reuniones para Teams pantallas con escritorio en caliente. Para obtener más información, [vea Teams licencias de salas de reuniones](rooms-licensing.md).

Para asignar licencias con el Centro de administración de Microsoft 365, vea [Asignar licencias a los usuarios](/microsoft-365/admin/manage/assign-licenses-to-users). Para asignar licencias con Azure AD, vea una de las siguientes pestañas:

#### <a name="active-directory-20"></a>[**Active Directory 2.0**](#tab/active-directory2-license/)


1. Conectar Azure AD
  
    ```PowerShell
    Connect-AzureAD
    ```

     Para obtener más información sobre Active Directory, [vea Azure Active Directory PowerShell para Graph](/powershell/azure/active-directory/overview?view=azureadps-2.0).
    
2. Asigne una ubicación de uso a su cuenta de recursos con el `Set-AzureADUser` cmdlet. Esto determina qué SKU de licencia están disponibles.

    En este ejemplo, el usuario se encuentra en Estados Unidos (EE. UU.):

    ```PowerShell
    Set-AzureADUser -ObjectID ConferenceRoom01@contoso.com -UsageLocation 'US'
    ```

3. A continuación, úse `Get-AzureADSubscribedSku` para recuperar una lista de SKU disponibles para su Microsoft 365 o Office 365 organización.

    ```PowerShell
    Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
    ```

4. Para asignar la licencia, use el `Set-AzureADUser` cmdlet y convierta el id. de SKU de licencia (vea el paso 2) en un objeto de tipo de licencia de PowerShell. A continuación, asigne ese objeto a la cuenta de recursos. En el ejemplo siguiente, el id. de SKU de licencia es 6070a4c8-34c6-4937-8dfb-39bbc6397a60 y se asigna a la cuenta conferenceroom01@contoso.com:

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

1. Conectar a MSOnline PowerShell.

   ```PowerShell
   Connect-MsolService
   ```

    Para obtener más información sobre Active Directory, [vea Azure Active Directory (MSOnline).](/powershell/azure/active-directory/overview?view=azureadps-1.0)

2.  Asigne una ubicación de uso a su cuenta de recursos con el `Set-MsolUser` cmdlet. Esto determina qué SKU de licencia están disponibles.

    En este ejemplo, el usuario se encuentra en Estados Unidos (EE. UU.).
    
    ```PowerShell
    Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -UsageLocation 'US'
    ```
    
    A continuación, puede `Get-MsolAccountSku` usar para recuperar una lista de SKU disponibles para su Microsoft 365 o Office 365 organización.

4. Para asignar la licencia, use el `Set-MsolUser` cmdlet. En este ejemplo, la licencia "contoso:MEETING_ROOM" se asigna a la cuenta conferenceroom01@contoso.com:

    ```PowerShell
    Set-MsolUserLicense -UserPrincipalName 'ConferenceRoom01@contoso.com' -AddLicenses 'contoso:MEETING_ROOM'
    ```

---

Para validar la creación de la cuenta y la asignación de licencias, inicie sesión en cualquier Teams cliente con la cuenta que creó.

## <a name="next-steps"></a>Siguientes pasos

### <a name="network-and-bandwidth"></a>Red y ancho de banda

Es posible que tenga que aplicar directivas de red, ancho de banda o reunión personalizadas a esta cuenta. Para obtener más información sobre las directivas de red y ancho de banda, vea [Configuración de directiva de reunión para audio & vídeo](/microsoftteams/meeting-policies-audio-and-video). Para Salas de Teams, le recomendamos que establezca el ancho de banda de la directiva de reunión en 10 Mbps.

Para fines de colaboración, active PowerPoint Live, Whiteboard y notas compartidas. Es posible que desee crear una directiva de reunión para ajustar la configuración de participantes y invitados Salas de Teams. Por ejemplo, revise la configuración de la sala de espera, como qué asistentes admitirán automáticamente las reuniones. Para obtener más información sobre Teams de reunión, vea [Administrar directivas de reunión en Microsoft Teams](/microsoftteams/meeting-policies-overview).

### <a name="calling"></a>Llamadas

No hay requisitos únicos para habilitar las llamadas con cuentas de recursos. Habilitar la cuenta de recursos para las llamadas de la misma manera que habilita a un usuario normal.

> [!NOTE]
> Se recomienda desactivar el correo de voz para dispositivos compartidos asignando una directiva de llamadas a las cuentas de recursos del dispositivo. Vea [Llamadas y reenvío de llamadas en Teams](../teams-calling-policy.md) para obtener más información.

### <a name="configure-distribution-groups"></a>Configurar grupos de distribución

Para organizar las ubicaciones de la sala de reuniones, puede agregar las cuentas de recursos de dispositivo a Exchange grupos de distribución. Por ejemplo, si tiene oficinas en tres ubicaciones geográficas diferentes, puede crear tres grupos de distribución y agregar las cuentas de recursos adecuadas a cada ubicación. Para obtener más información, vea [Crear una lista de salas](/exchange/recipients/room-mailboxes?view=exchserver-2019#create-a-room-list).

## <a name="related-articles"></a>Artículos relacionados

[Configurar cuentas para Salas de Microsoft Teams](rooms-configure-accounts.md)

[Plan para Salas de Microsoft Teams](rooms-plan.md)

[Implementar Salas de Microsoft Teams](rooms-deploy.md)

[Administrar Salas de Microsoft Teams](rooms-manage.md)

[Salas de Microsoft Teams licencias](rooms-licensing.md)
