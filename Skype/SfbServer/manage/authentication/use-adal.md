---
title: Cómo usar la autenticación moderna (ADAL) con Skype Empresarial
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 2/13/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5ca71746-ead6-4e8c-90b1-461e846d1f4a
description: This article explains how to use Modern Authentication (which is based on the Active Directory Authentication Library (ADAL) and OAuth 2.0) that can be found in the March 2016 Cumulative Update for Skype for Business for Skype for Business Server 2015.
ms.openlocfilehash: efd0e35ce92143e9fb5fda03301eb51d2926c979
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a>Cómo usar la autenticación moderna (ADAL) con Skype Empresarial
 
This article explains how to use Modern Authentication (which is based on the Active Directory Authentication Library (ADAL) and OAuth 2.0) that can be found in the March 2016 Cumulative Update for Skype for Business for Skype for Business Server 2015.
  
## <a name="whats-in-this-article"></a>¿Qué se incluye en este artículo?

[¿Qué es ADAL?](use-adal.md#BKMK_ADAL)
  
[Configurar ADAL en su grupo y configurar ADFS como un servidor de token de seguridad](use-adal.md#BKMK_Config)
  
[Otras opciones para habilitar el inicio de sesión de ADAL (como aplicaciones cliente de Office)](use-adal.md#BKMK_Options)
  
[Clientes en los que no se admite la autenticación moderna / ADAL](use-adal.md#BKMK_Support)
  
## <a name="what-is-adal"></a>¿Qué es ADAL?
<a name="BKMK_ADAL"> </a>

ADAL es el acrónimo de "Biblioteca de autenticación de Active Directory" y, junto con OAuth 2.0, es fundamental en la autenticación moderna. This code library is designed to make secured resources in your directory available to client applications (like Skype for Business) via security tokens. ADAL funciona con OAuth 2.0 para permitir más escenarios de autorización y autenticación, como la autenticación multifactor (MFA) y más formas de autenticación SAML.
  
Varias aplicaciones que actúan como clientes pueden aprovecharse de la autenticación moderna para obtener recursos protegidos. In Skype for Business Server 2015, this technology is used between on-premises clients and on-premises servers in order to give users a proper level of authorization to resources.
  
Las conversaciones de autenticación moderna (que se basan en ADAL y OAuth 2.0) tienen algunos elementos en común.
  
- There is a client making a request for a resource, in this case, the client is Skype for Business.
    
- There is a resource to which the client needs a specific level of access, and this resource is secured by a directory service, in this case the resource is Skype for Business Server 2015.
    
- There is an OAuth connection, in other words, a connection that is dedicated to  *authorizing*  a user to access a resource. (OAuth también se conoce por el nombre descriptivo, autenticación "de servidor a servidor" y, a menudo, aparece abreviado como S2S).
    
In Skype for Business Server 2015 Modern Authentication (ADAL) conversations, Skype for Business Server 2015 communicates through ADFS (ADFS 3.0 in Windows Server 2012 R2). La autenticación puede ocurrir con otro proveedor de identidades (IdP), pero el servidor de Skype Empresarial necesita configurarse para poder comunicarse directamente con ADFS. If you haven't configured ADFS to work with Skype for Business Server 2015 please complete the [ADFS installation](https://technet.microsoft.com/en-us/library/adfs2-step-by-step-guides%28v=ws.10%29.aspx).
  
ADAL is included in the March 2016 Cumulative Update for Skype for Business Server 2015, and the March 2016 Cumulative Update for Skype for Business **must** be installed and is needed for successful configuration.
  
> [!NOTE]
> Con la versión inicial, la autenticación moderna en un entorno local solo se admite si no existe una topología combinada de Skype. For example, if the environment is purely Skype for Business Server 2015. Esta instrucción puede estar vinculada a cambios. 
  
Debe descargarse un paquete de PowerShell que incluye archivos .ps1 con los comandos que usa ADAL para obtener una configuración correcta.
  
### <a name="configure-adal-in-your-pool-and-set-adfs-as-security-token-server"></a>Configurar ADAL en su grupo y configurar ADFS como un servidor de token de seguridad
<a name="BKMK_Config"> </a>

In this process, you connect your installation of ADFS to a Skype for Business Server 2015 pool that is configured for ADAL.
  
1. Install the March 2016 Cumulative Update for Skype for Business Server 2015 to your Skype for Business Server 2015 pool or Standard Edition server. (Programe la ventana de mantenimiento, según sus necesidades, para ejecutar Windows Update para la instalación automática).
    
2. On your on-premises ADFS server(s), [download](https://aka.ms/sfbadalscripts) the Setup-AdfsOAuthTrustForSfB script. (Esto debe realizarse por cada granja de servidores de ADFS o servidores independientes de ADFS. No es necesario realizarlo en proxy o proxies ADFS).
    
3. Make a note of the internal and external Web Service fully qualified domain names (FQDNs) for your Skype for Business Server 2015 pool or Standard Edition server. Esto debe realizarse para todos los grupos de Skype Empresarial.
    
4. Desde PowerShell en los servidores de ADFS, ejecute el script Setup-AdfsOAuthTrustForSfB. Necesitará escribir las direcciones URL adecuadas para los FQDN de servicios web externos e internos. Aquí se muestra un ejemplo:
    
     `Setup-AdfsOAuthTrustForSfB.ps1 -poolIDs https://contosoSkype.contoso.com,https://contoso01Skype.contosoIn.com`
    
    For any additional pools, you will need to add the Pool Web Services URLs manually to the Skype for Business Server 2015 Relying Party Trust in ADFS.
    
    > [!IMPORTANT]
    > No es posible usar a la vez ADAL y la autenticación pasiva para un grupo. Para poder usar ADAL, debe deshabilitar la autenticación pasiva. For PowerShell cmdlets on how to set authentication for a Pool see [this](https://technet.microsoft.com/en-us/library/gg398396.aspx) article.
  
    > [!TIP]
    > If you have additional pools you need to add them as [Identifiers](https://technet.microsoft.com/en-us/library/gg557759%28v=ws.10%29.aspx) to the Relying Party Trust in ADFS.> Go to your ADFS server and open ADFS Management. Expand Trust Relationships \> Relying Party Trusts. Right-click the Relying Party Trust that's listed and right-click for Properties \> Identifiers \> type the additional Pool URL(s) \> click Add. 
  
5. Return to your Skype for Business Server 2015 Front End or Standard Edition server server. From here you must run cmdlets that create an OAuth server and modify that OAuth configuration to work with Skype for Business. You only need to do this step once per Skype for Business Server 2015 deployment. Aquí se muestra un ejemplo:
    
     `New-CsOAuthServer -Identity sts.contosoIn.com -Type ADFS -MetadataURL https://sts.contosoIn.com/FederationMetadata/2007-06/FederationMetadata.xml`
    
    > [!TIP]
    > The 'Identity' URL you see in this command is actually the ADFS Federation Service Name you can see in ADFS Management when you right-click Service \> Properties. The 'Type' is always ADFS, and the 'MetadataURL' is always \<Your ADFS service name\> + "/FederationMetadata/2007-06/FederationMetadata.xml". 
  
     `Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity sts.contosoIn.com`
    
6. Still on your Skype for Business Server 2015 Front End or Standard Edition server, test the new configuration by entering the SIP address of a user and the pool FQDN. You only need to do this step once per Skype for Business Server 2015 deployment. Aquí se muestra un ejemplo:
    
     `Test-CsRegistration -UserSipAddress AyakaY@contosoIns.com -TargetFqdn Pool1.contoso.com -Authentication OAuthInteractive`
    
7. Cuando se le solicite, escriba las credenciales del usuario de prueba. Compruebe que la prueba se completa correctamente.
    
    > [!NOTE]
    > When your STS URL resolves to ADFS  *internally*  , the prompt you will see will be a **Windows Security** prompt. Si la dirección URL se resuelve externamente, verá un aviso denominado **Iniciar sesión**. Normalmente, querríamos un aviso de **Seguridad de Windows** aquí. Tenga en cuenta que este comportamiento cambia, particularmente si ha implementado la Autenticación basada en formularios (FBA).
  
Además, tenga en cuenta que cuando la dirección URL de STS se resuelve como un servidor interno de ADFS y la autenticación integrada de Windows está habilitada en los exploradores, pueden producirse errores de autenticación en los equipos donde muchos usuarios diferentes inician sesión en aplicaciones cliente, a no ser que el explorador esté configurado explícitamente para solicitar las credenciales a los usuarios en una zona de seguridad del explorador determinada. Por ejemplo, piense en un quiosco. La cuenta con sesión iniciada en el sistema operativo puede ser diferente que la cuenta de usuario con sesión iniciada en el cliente de Skype Empresarial. Si este es el caso, consulte los errores que se describen aquí.
    
You can see and change this browser setting in Internet Explorer by clicking \> Tools (or the Gear) \> Internet Options \> Security tab \> and the Security Zone (such as Local Intranet). Desde este cuadro de diálogo, haga clic en el botón Nivel personalizado y desplácese al final de la lista del cuadro de diálogo Configuración. Under User Authentication \> Login \> you'll see an option to 'Prompt for user name and password'. Si tiene quioscos en los que el usuario que inicia el cliente de Skype Empresarial es diferente (tiene una cuenta diferente) del usuario que ha iniciado sesión en el equipo, quizás le interese establecer esta opción en "ACTIVADO" para estas máquinas de la directiva de grupo.
    
Por último y muy importante, tal vez experimente más de un aviso ya que el sistema de seguridad recopila la información que necesita para autenticar o autorizar la cuenta.
    
### <a name="other-options-for-enabling-adal-sign-in-like-office-client-apps"></a>Otras opciones para habilitar el inicio de sesión de ADAL (como aplicaciones cliente de Office)
<a name="BKMK_Options"> </a>

Now that ADAL is configured for your Skype for Business and (automatically) for Office 2016 client apps across platforms, you may want to leverage it for Exchange Online (where it is not 'On' by default), or in Office 2013 clients.
  
> [!IMPORTANT]
> ¿Necesita saber qué esperar de los inicios de sesión con autenticación moderna de sus aplicaciones cliente? Take a look at [How modern authentication works for Office 2013 and Office 2016 client apps](https://support.office.com/en-us/article/How-modern-authentication-works-for-Office-2013-and-Office-2016-client-apps-e4c45989-4b1a-462e-a81b-2a13191cf517?ui=en-US&amp;rs=en-US&amp;ad=US). 
  
To turn Modern Authentication on for Exchange Online, you'll need to run some PowerShell cmdlets. In the case of Office 2013 client apps, you will need to change some registry keys on client machines.
  
- Connect to Exchange Online and run the following cmdlets:
    
     `Set-OrganizationConfig -OAuth2ClientProfileEnabled:$true`
    
     `Get-OrganizationConfig | ft name, *OAuth*`
    
- Establezca estas claves del registro para cada dispositivo o equipo en el que quiera habilitar la autenticación moderna. Necesitará un GPO para organizaciones más grandes. For information on how to make a GPO, see the 'Create a Group Policy Object to modify the registry on a domain joined computer' of [this ](https://support.office.com/en-us/article/Switching-between-the-Skype-for-Business-and-the-Lync-client-user-interfaces-a2394a4c-7522-484c-a047-7b3289742be0)article.
    
||||
|:-----|:-----|:-----|
|Clave del registro  <br/> |Tipo  <br/> |Valor  <br/> |
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL  <br/> |REG_DWORD  <br/> |1  <br/> |
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version  <br/> |REG_DWORD  <br/> |1  <br/> |
   
Once these keys are set, set your Office 2013 apps to [use Multifactor Authentication (MFA) with Office 365](https://support.office.com/en-us/article/Set-up-multi-factor-authentication-for-Office-365-8f0454b2-f51a-4d9c-bcde-2c48e41621c6?ui=en-US&amp;rs=en-US&amp;ad=US).
  
> [!TIP]
> To disable Modern Authentication on devices for Office 2013, set the HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL registry key to a value of zero. Be aware that a similar Registry key (HKCU\SOFTWARE\Microsoft\Office\ **16.0** \Common\Identity\EnableADAL) can also be used to disable Modern Authentication on devices for Office 2016.
  
### <a name="clients-where-modern-authentication--adal-isnt-supported"></a>Clientes en los que no se admite la autenticación moderna / ADAL
<a name="BKMK_Support"> </a>

Algunas versiones de cliente no admiten OAuth. Puede comprobar su versión de cliente de Office en la ventana de Agregar y quitar programas del Panel de control para comparar el número de versión de las versiones (o intervalos de versiones) enumeradas aquí:
  
- Office Client 15.0.[0000-4766].\*
    
- Office Client 16.0.[0000-4293].\*
    
- Cliente de Office 16.0.6001.[0000-1032]
    
- Office Client 16.0.[6000-6224].\*
    

