
Cada dispositivo Salas de Microsoft Teams necesita su propia cuenta de recursos. La cuenta de recursos es la cuenta en la que el dispositivo Salas de Teams inicia sesión y es la que los usuarios de su organización invitan a reservar la sala de Teams.

Al crear el buzón de recursos, puede especificar si desea permitir reuniones periódicas, hacer que la sala acepte automáticamente invitaciones, cuántos días en el futuro va a aceptar invitaciones, etc.

> [!TIP]
> Al asignar un nombre a las cuentas de recursos, se recomienda usar una convención de nomenclatura estándar al principio de la dirección de correo electrónico. Esto ayudará a crear grupos dinámicos para facilitar la administración en Azure Active Directory. Por ejemplo, podría usar "mtr-" para todas las cuentas de recursos que se asociarán con Salas de Microsoft Teams.

> [!TIP]
> Le recomendamos que cree todas las cuentas de recursos con Exchange Online y Azure Active Directory.

Cree una cuenta de recursos con un método de una de las pestañas siguientes:

#### <a name="in-microsoft-365-admin-center"></a>[**En Centro de administración de Microsoft 365**](#tab/m365-admin-center)

1. Inicie sesión en el Centro de administración de Microsoft 365.

2. Proporcione las credenciales de administrador para su inquilino de Microsoft 365.

3. Vaya a **Recursos** en el panel izquierdo y, después, seleccione **Salas & equipamiento**. Si estas opciones no están disponibles en el panel izquierdo, es posible que primero tenga que seleccionar **Mostrar todo** .

4. Seleccione **Agregar recurso** para crear una nueva cuenta de recursos. Escribe un nombre para mostrar y una dirección de correo electrónico para la cuenta y, a continuación, selecciona **Guardar**.

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

Es posible que también tenga que aplicar directivas de ancho de banda o directivas de reunión a esta cuenta. Puede establecer directivas de buzón en un paso posterior.

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
