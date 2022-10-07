
Al igual que cualquier cuenta de Microsoft 365, la contraseña de una cuenta de recursos recién creada se establece para expirar automáticamente después de un período de tiempo. Sin embargo, si la contraseña de la cuenta de recursos expira, el dispositivo Salas de Teams en el que haya iniciado sesión no podrá volver a iniciar sesión la fecha de expiración. 

Para evitar tener que restablecer la contraseña de la cuenta de recursos y volver a iniciar sesión en cada Salas de Teams dispositivo, puede desactivar la expiración de la contraseña de la cuenta.
  
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
    Set-MsolUser -Identity <samAccountName> -PasswordNeverExpires $true
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
    
    Para obtener más información sobre PowerShell de Active Directory, vea [ActiveDirectory](/powershell/module/activedirectory).

2. Establezca la contraseña para que nunca expire con la siguiente sintaxis:

    ```PowerShell
    Set-ADUser -Identity <samAccountName> -PasswordNeverExpires $true
    ```

    En este ejemplo se establece que la contraseña de la cuenta ConferenceRoom01@contoso.com no expire nunca.

    ```PowerShell
    Set-ADUser -Identity ConferenceRoom01@contoso.com -PasswordNeverExpires $true
    ```

---