---
title: Cómo usar la autenticación moderna (ADAL) con Skype Empresarial
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5ca71746-ead6-4e8c-90b1-461e846d1f4a
description: Este artículo explica cómo usar la autenticación moderno (que se basa en la biblioteca de autenticación de Active Directory (ADAL) y OAuth 2.0) que puede encontrarse en la actualización de marzo de 2016 actualización acumulativa de Skype para la empresa de Skype para Business Server 2015.
ms.openlocfilehash: 0121e1a99aab70b10a00dbcf72d3a8be8a50553a
ms.sourcegitcommit: 8e5fc1d8c19a7f26f53e40b23dd6476a8c6d805f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/26/2019
ms.locfileid: "30800142"
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a>Cómo usar la autenticación moderna (ADAL) con Skype Empresarial
 
Este artículo explica cómo usar la autenticación moderno (que se basa en la biblioteca de autenticación de Active Directory (ADAL) y OAuth 2.0) que puede encontrarse en la actualización de marzo de 2016 actualización acumulativa de Skype para la empresa de Skype para Business Server 2015, o de inicial versión de Skype para Business Server 2019.
  
## <a name="whats-in-this-article"></a>¿Qué se incluye en este artículo?

[Configurar ADAL en el grupo de servidores y establecer AD FS como servidor de token de seguridad](use-adal.md#BKMK_Config)
  
[Otras opciones para habilitar el inicio de sesión de ADAL (como aplicaciones cliente de Office)](use-adal.md#BKMK_Options)
  
[Clientes en los que no se admite la autenticación moderna / ADAL](use-adal.md#BKMK_Support)
  
### <a name="configure-adal-in-your-pool-and-set-ad-fs-as-security-token-server"></a>Configurar ADAL en el grupo de servidores y establecer AD FS como servidor de token de seguridad
<a name="BKMK_Config"> </a>

En este proceso, la instalación de AD FS se conecta a un Skype para profesionales de servidores que está configurada para ADAL.
  
1. Instalar la actualización de marzo de 2016 actualización acumulativa (o posterior) para Skype para Business Server 2015 a su Skype para profesionales de servidores o servidor Standard Edition. (Programe la ventana de mantenimiento, según sus necesidades, para ejecutar Windows Update para la instalación automática).
    
2. En sus instalaciones en servidores de AD FS, [Descargue](https://aka.ms/sfbadalscripts) el programa de instalación-AdfsOAuthTrustForSfB secuencia de comandos. (Esto debe hacerse por servidores de AD FS independientes o de granja de servidores de AD FS. Lo necesitan realizarse en los servidores proxy de AD FS o servidores proxy de aplicación Web.)
    
3. Tome nota de los internos y servicio Web externo completo de nombres de dominio (FQDN) para su Skype para servidor Standard Edition o grupo de servidores empresariales. Esto debe realizarse para todos los grupos de Skype Empresarial.
    
4. Desde PowerShell en el servidor o servidores de AD FS, ejecute `Setup-AdfsOAuthTrustForSfB.ps1` (para Windows Server 2012 R2) o `Setup-Adfs2016OAuthTrustForSfB.ps1` (para Windows Server 2016 o más adelante.) Debe escribir las direcciones de URL correcta para los nombres internos y externos servicio Web dominio completo (FQDN). Aquí se muestra un ejemplo:
    
     `Setup-AdfsOAuthTrustForSfB.ps1 -poolIDs https://contosoSkype.contoso.com,https://contoso01Skype.contosoIn.com`
    
    Para cualquiera de los grupos adicional, debe agregar las direcciones URL de grupo de servidores Web Services manualmente a la Skype para Business Server relación de confianza en AD FS.
    
    > [!IMPORTANT]
    > No es posible usar a la vez ADAL y la autenticación pasiva para un grupo. Para poder usar ADAL, debe deshabilitar la autenticación pasiva. Para los cmdlets de PowerShell acerca de cómo configurar la autenticación para un grupo de servidores, vea [este](https://technet.microsoft.com/en-us/library/gg398396.aspx) artículo.
  
    > [!TIP]
    > Si tiene grupos de servidores adicionales, que es necesario agregar como [identificadores](https://technet.microsoft.com/en-us/library/gg557759%28v=ws.10%29.aspx) a la relación de confianza en AD FS.> vaya a su servidor AD FS y abrir Administración de AD FS. Expanda las relaciones de confianza \> confianzas de terceros de confianza. Haga clic en la relación de confianza que se enumeran y con el botón secundario para las propiedades de \> identificadores \> escriba la dirección URL de grupo de servidores adicionales \> haga clic en Agregar. 
  
5. Volver a su Skype para profesionales de servidor Front-End o servidor Standard Edition server. Desde aquí debe ejecutar los cmdlets que crear un servidor de OAuth y modificar esa configuración de OAuth para que funcione con Skype para la empresa. Sólo debe realizar este paso una vez por Skype para la implementación de Business Server. Aquí se muestra un ejemplo:
    
     `New-CsOAuthServer -Identity sts.contosoIn.com -Type ADFS -MetadataURL https://sts.contosoIn.com/FederationMetadata/2007-06/FederationMetadata.xml`
    
    > [!TIP]
    > La dirección URL de 'Identidad' vea en este comando es realmente el AD FS federación nombre servicio puede ver en administración de AD FS cuando haga clic en servicio \> propiedades. 'Tipo' siempre es 'ADFS' y la 'MetadataURL' es siempre \<su nombre de servicio de AD FS\> + "/ FederationMetadata/2007-06/FederationMetadata.xml". 
  
     `Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity sts.contosoIn.com`
    
6. Aún en su Skype para profesionales de servidor Front-End o servidor Standard Edition, probar la nueva configuración escribiendo la dirección SIP de un usuario y el FQDN del grupo. Sólo debe realizar este paso una vez por Skype para la implementación de Business Server. Aquí se muestra un ejemplo:
    
     `Test-CsRegistration -UserSipAddress AyakaY@contosoIns.com -TargetFqdn Pool1.contoso.com -Authentication OAuthInteractive`
    
7. Cuando se le solicite, escriba las credenciales del usuario de prueba. Compruebe que la prueba se completa correctamente.
    
    > [!NOTE]
    > Cuando la URL de STS se resuelve en AD FS *internamente* , el símbolo del sistema que se verá será un símbolo del sistema de **Seguridad de Windows** . Si la dirección URL se resuelve externamente, verá un aviso denominado **Iniciar sesión**. Normalmente, querríamos un aviso de **Seguridad de Windows** aquí. Tenga en cuenta que este comportamiento cambia, particularmente si ha implementado la Autenticación basada en formularios (FBA).
  
También debe tener en cuenta cuando la URL STS se resuelve en un servidor interno de AD FS y autenticación integrada de Windows está habilitada en los exploradores, donde muchos usuarios diferentes iniciar sesión en las aplicaciones cliente de los equipos pueden tener errores para autenticar a menos que el explorador es explícitamente configurado para solicitar a los usuarios sus credenciales en un explorador determinado de zona de seguridad. Por ejemplo, piense en un quiosco. La cuenta con sesión iniciada en el sistema operativo puede ser diferente que la cuenta de usuario con sesión iniciada en el cliente de Skype Empresarial. Si este es el caso, consulte los errores que se describen aquí.
    
Puede ver y cambiar esta configuración del explorador en Internet Explorer, haga clic en \> herramientas (o el engranaje) \> opciones de Internet \> ficha seguridad \> y la zona de seguridad (por ejemplo, Intranet Local). Desde este cuadro de diálogo, haga clic en el botón Nivel personalizado y desplácese al final de la lista del cuadro de diálogo Configuración. En autenticación de usuario \> inicio de sesión \> verá una opción para 'Preguntar por el nombre de usuario y contraseña'. Si tiene quioscos en los que el usuario que inicia el cliente de Skype Empresarial es diferente (tiene una cuenta diferente) del usuario que ha iniciado sesión en el equipo, quizás le interese establecer esta opción en "ACTIVADO" para estas máquinas de la directiva de grupo.
    
Por último y muy importante, tal vez experimente más de un aviso ya que el sistema de seguridad recopila la información que necesita para autenticar o autorizar la cuenta.
    
### <a name="other-options-for-enabling-adal-sign-in-like-office-client-apps"></a>Otras opciones para habilitar el inicio de sesión de ADAL (como aplicaciones cliente de Office)
<a name="BKMK_Options"> </a>

Ahora que ADAL está configurado para su Skype para la empresa y (automáticamente) para las aplicaciones cliente de Office 2016 en plataformas, es posible que desee aproveche para Exchange Online (que no es 'En' de forma predeterminada) o en los clientes de Office 2013.
  
> [!IMPORTANT]
> ¿Necesita saber qué esperar de los inicios de sesión con autenticación moderna de sus aplicaciones cliente? Eche un vistazo a [moderno cómo funciona la autenticación para aplicaciones de cliente de Office 2013 y Office 2016](https://support.office.com/en-us/article/How-modern-authentication-works-for-Office-2013-and-Office-2016-client-apps-e4c45989-4b1a-462e-a81b-2a13191cf517?ui=en-US&amp;rs=en-US&amp;ad=US). 
  
Para activar la autenticación moderno para Exchange Online, debe ejecutar algunos cmdlets de PowerShell. En el caso de las aplicaciones de cliente de Office 2013, debe cambiar algunas claves del registro en los equipos cliente.
  
- Conectarse a Exchange Online y ejecute los cmdlets siguientes:
    
     `Set-OrganizationConfig -OAuth2ClientProfileEnabled:$true`
    
     `Get-OrganizationConfig | ft name, *OAuth*`
    
- Establezca estas claves del registro para cada dispositivo o equipo en el que quiera habilitar la autenticación moderna. Necesitará un GPO para organizaciones más grandes. Para obtener información acerca de cómo hacer que un GPO, vea la 'crear un objeto de directiva de grupo para modificar el registro en los equipos unidos a un dominio' de [este ](https://support.office.com/en-us/article/Switching-between-the-Skype-for-Business-and-the-Lync-client-user-interfaces-a2394a4c-7522-484c-a047-7b3289742be0)artículo.
    
|Clave del registro  <br/> |Tipo  <br/> |Valor  <br/> |
|:-----|:-----|:-----|
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL  <br/> |REG_DWORD  <br/> |1  <br/> |
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version  <br/> |REG_DWORD  <br/> |1  <br/> |
   
Una vez se establecen estas claves, establecer sus aplicaciones de Office para [usar la autenticación con autenticación (MFA) con Office 365](https://support.office.com/en-us/article/Set-up-multi-factor-authentication-for-Office-365-8f0454b2-f51a-4d9c-bcde-2c48e41621c6?ui=en-US&amp;rs=en-US&amp;ad=US).
  
> [!TIP]
> Para deshabilitar la autenticación moderno en dispositivos de Office 2013, establezca la clave del registro HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL en un valor de cero. Tenga en cuenta que también se puede usar una clave del Registro similar (HKCU\SOFTWARE\Microsoft\Office\ **16.0** \Common\Identity\EnableADAL) para deshabilitar la autenticación moderno en dispositivos de Office 2016.
  
### <a name="clients-where-modern-authentication--adal-isnt-supported"></a>Clientes en los que no se admite la autenticación moderna / ADAL
<a name="BKMK_Support"> </a>

Algunas versiones de cliente no admiten OAuth. Puede comprobar su versión de cliente de Office en la ventana de Agregar y quitar programas del Panel de control para comparar el número de versión de las versiones (o intervalos de versiones) enumeradas aquí:
  
- Cliente de Office 15.0. [0000-4766].\*
    
- Cliente de Office 16.0. [0000-4293].\*
    
- Cliente de Office 16.0.6001.[0000-1032]
    
- Cliente de Office 16.0. [6000-6224].\*
    
> [!NOTE]
> Autenticación moderno híbrida también está disponible con Skype para empresarial local, si desea saber más, visite [cómo configurar Skype para la empresa local para usar la autenticación moderno híbrida](https://docs.microsoft.com/en-us/office365/enterprise/configure-skype-for-business-for-hybrid-modern-authentication)
