---
title: Cómo usar la autenticación moderna (ADAL) con Skype Empresarial
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5ca71746-ead6-4e8c-90b1-461e846d1f4a
description: En este artículo se explica cómo usar la autenticación moderna (que se basa en la biblioteca de autenticación de Active Directory (ADAL) y OAuth 2,0) que puede encontrarse en la actualización acumulativa de marzo de 2016 para Skype empresarial para Skype empresarial 2015.
ms.openlocfilehash: 9fe4470e1f8f6e2cd345cd176250fb1ffb16448f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286126"
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a>Cómo usar la autenticación moderna (ADAL) con Skype Empresarial
 
En este artículo se explica cómo usar la autenticación moderna (que se basa en la biblioteca de autenticación de Active Directory (ADAL) y OAuth 2,0) que se puede encontrar en la actualización acumulativa de marzo de 2016 para Skype empresarial para Skype empresarial 2015, o desde el inicio versión para Skype empresarial Server 2019.
  
## <a name="whats-in-this-article"></a>¿Qué se incluye en este artículo?

[Configuración de ADAL en su grupo y establecimiento de AD FS como servidor de token de seguridad](use-adal.md#BKMK_Config)
  
[Otras opciones para habilitar el inicio de sesión de ADAL (como aplicaciones cliente de Office)](use-adal.md#BKMK_Options)
  
[Clientes en los que no se admite la autenticación moderna / ADAL](use-adal.md#BKMK_Support)
  
### <a name="configure-adal-in-your-pool-and-set-ad-fs-as-security-token-server"></a>Configuración de ADAL en su grupo y establecimiento de AD FS como servidor de token de seguridad
<a name="BKMK_Config"> </a>

En este proceso, conectará la instalación de AD FS con un grupo de servidores de Skype empresarial configurado para ADAL.
  
1. Instale la actualización acumulativa de marzo de 2016 (o posterior) para Skype empresarial Server 2015 en el grupo de servidores de Skype empresarial o el servidor Standard Edition. (Programe la ventana de mantenimiento, según sus necesidades, para ejecutar Windows Update para la instalación automática).
    
2. En los servidores locales de AD FS, [Descargue](https://aka.ms/sfbadalscripts) el script Setup-AdfsOAuthTrustForSfB. (Esto debe hacerse por granja de AD FS o por servidores de AD FS independientes. No es necesario realizarla en proxys de AD FS ni en proxies de aplicaciones Web.)
    
3. Anote los nombres de dominio completos (FQDN) de los servicios Web internos y externos para su servidor de Skype empresarial Server o Standard Edition. Esto debe realizarse para todos los grupos de Skype Empresarial.
    
4. Desde PowerShell en los servidores AD FS, ejecute `Setup-AdfsOAuthTrustForSfB.ps1` (para windows Server 2012 R2) o `Setup-Adfs2016OAuthTrustForSfB.ps1` (para Windows Server 2016 o posterior). Tendrá que introducir las direcciones URL apropiadas para los nombres de dominio completos (FQDN) internos y externos. Aquí se muestra un ejemplo:
    
     `Setup-AdfsOAuthTrustForSfB.ps1 -poolIDs https://contosoSkype.contoso.com,https://contoso01Skype.contosoIn.com`
    
    Para cualquier conjunto de servidores adicionales, tendrá que agregar las direcciones URL de los servicios Web de grupo manualmente a la relación de confianza para usuario autenticado de Skype empresarial Server en AD FS.
    
    > [!IMPORTANT]
    > No es posible usar a la vez ADAL y la autenticación pasiva para un grupo. Para poder usar ADAL, debe deshabilitar la autenticación pasiva. Para los cmdlets de PowerShell sobre cómo establecer la autenticación para un grupo, consulte [este](https://technet.microsoft.com/en-us/library/gg398396.aspx) artículo.
  
    > [!TIP]
    > Si tiene agrupaciones adicionales, debe agregarlas como [identificadores](https://technet.microsoft.com/en-us/library/gg557759%28v=ws.10%29.aspx) a la relación de confianza para usuario autenticado en AD FS. > vaya al servidor de AD FS y abra Administración de AD FS. Expanda relaciones \> de confianza confianzas de usuario de confianza. Haga clic con el botón secundario en la relación de confianza para usuario autenticado que se \> muestra y \> haga clic con el botón secundario para identificar \> los identificadores de propiedades. 
  
5. Vuelva a su servidor de Skype empresarial Server front end o Standard Edition. Desde aquí, debe ejecutar cmdlets que creen un servidor de OAuth y modificar esa configuración de OAuth para que funcione con Skype empresarial. Solo tiene que realizar este paso una vez por cada implementación de Skype empresarial Server. Aquí se muestra un ejemplo:
    
     `New-CsOAuthServer -Identity sts.contosoIn.com -Type ADFS -MetadataURL https://sts.contosoIn.com/FederationMetadata/2007-06/FederationMetadata.xml`
    
    > [!TIP]
    > La dirección URL de la identidad que aparece en este comando es, en realidad, el nombre del servicio de Federación de AD FS que puede ver en la administración \> de AD FS al hacer clic con el botón secundario en propiedades de servicio. El ' tipo ' es siempre ' ADF ' y ' MetadataURL ' siempre \<es tu nombre\> de servicio de AD FS + "/FederationMetadata/2007-06/FederationMetadata.xml". 
  
     `Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity sts.contosoIn.com`
    
6. Aún en su servidor de Skype empresarial Server front end o Standard Edition, pruebe la nueva configuración introduciendo la dirección SIP de un usuario y el FQDN del grupo. Solo tiene que realizar este paso una vez por cada implementación de Skype empresarial Server. Aquí se muestra un ejemplo:
    
     `Test-CsRegistration -UserSipAddress AyakaY@contosoIns.com -TargetFqdn Pool1.contoso.com -Authentication OAuthInteractive`
    
7. Cuando se le solicite, escriba las credenciales del usuario de prueba. Compruebe que la prueba se completa correctamente.
    
    > [!NOTE]
    > Cuando la dirección URL de STS se resuelve en AD ** FS internamente, el aviso que verá será una pregunta de **seguridad de Windows** . Si la dirección URL se resuelve externamente, verá un aviso denominado **Iniciar sesión**. Normalmente, querríamos un aviso de **Seguridad de Windows** aquí. Tenga en cuenta que este comportamiento cambia, particularmente si ha implementado la Autenticación basada en formularios (FBA).
  
Además, tenga en cuenta que cuando la dirección URL de STS se resuelve en un servidor interno de AD FS y la autenticación integrada de Windows está habilitada en los exploradores, los equipos donde muchos usuarios diferentes inician sesión en las aplicaciones cliente pueden tener errores para autenticar a menos que el explorador sea explícitamente configurado para solicitar a los usuarios sus credenciales en una zona de seguridad determinada del explorador. Por ejemplo, piense en un quiosco. La cuenta con sesión iniciada en el sistema operativo puede ser diferente que la cuenta de usuario con sesión iniciada en el cliente de Skype Empresarial. Si este es el caso, consulte los errores que se describen aquí.
    
Para ver y cambiar esta configuración del explorador en Internet Explorer, haga \> clic en herramientas (o en \> la pestaña \> \> de seguridad opciones de Internet) y en la zona de seguridad (como la Intranet local). Desde este cuadro de diálogo, haga clic en el botón Nivel personalizado y desplácese al final de la lista del cuadro de diálogo Configuración. En autenticación \> de usuario \> iniciada, verá la opción ' preguntar por el nombre de usuario y la contraseña '. Si tiene quioscos en los que el usuario que inicia el cliente de Skype Empresarial es diferente (tiene una cuenta diferente) del usuario que ha iniciado sesión en el equipo, quizás le interese establecer esta opción en "ACTIVADO" para estas máquinas de la directiva de grupo.
    
Por último y muy importante, tal vez experimente más de un aviso ya que el sistema de seguridad recopila la información que necesita para autenticar o autorizar la cuenta.
    
### <a name="other-options-for-enabling-adal-sign-in-like-office-client-apps"></a>Otras opciones para habilitar el inicio de sesión de ADAL (como aplicaciones cliente de Office)
<a name="BKMK_Options"> </a>

Ahora que ADAL está configurado para Skype empresarial y (automáticamente) para aplicaciones cliente de Office 2016 en todas las plataformas, es posible que desee aprovecharla para Exchange Online (donde no está "activada" de forma predeterminada) o en clientes de Office 2013.
  
> [!IMPORTANT]
> ¿Necesita saber qué esperar de los inicios de sesión con autenticación moderna de sus aplicaciones cliente? Eche un vistazo a [Cómo funciona la autenticación moderna para las aplicaciones cliente de office 2013 y de office 2016](https://support.office.com/en-us/article/How-modern-authentication-works-for-Office-2013-and-Office-2016-client-apps-e4c45989-4b1a-462e-a81b-2a13191cf517?ui=en-US&amp;rs=en-US&amp;ad=US). 
  
Para activar la autenticación moderna en Exchange Online, tendrá que ejecutar algunos cmdlets de PowerShell. En el caso de las aplicaciones cliente de Office 2013, tendrá que cambiar algunas claves de registro en los equipos cliente.
  
- Conéctese a Exchange Online y ejecute los siguientes cmdlets:
    
     `Set-OrganizationConfig -OAuth2ClientProfileEnabled:$true`
    
     `Get-OrganizationConfig | ft name, *OAuth*`
    
- Establezca estas claves del registro para cada dispositivo o equipo en el que quiera habilitar la autenticación moderna. Necesitará un GPO para organizaciones más grandes. Para obtener información acerca de cómo crear un GPO, consulte el artículo "crear un objeto de directiva de grupo para modificar el registro en un equipo unido a un dominio" de [este ](https://support.office.com/en-us/article/Switching-between-the-Skype-for-Business-and-the-Lync-client-user-interfaces-a2394a4c-7522-484c-a047-7b3289742be0)artículo.
    
|Clave del registro  <br/> |Tipo  <br/> |Valor  <br/> |
|:-----|:-----|:-----|
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL  <br/> |REG_DWORD  <br/> |1  <br/> |
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version  <br/> |REG_DWORD  <br/> |1  <br/> |
   
Una vez que se hayan establecido estas claves, configure las aplicaciones de Office para que [usen la autenticación multifactor (MFA) con Office 365](https://support.office.com/en-us/article/Set-up-multi-factor-authentication-for-Office-365-8f0454b2-f51a-4d9c-bcde-2c48e41621c6?ui=en-US&amp;rs=en-US&amp;ad=US).
  
> [!TIP]
> Para deshabilitar la autenticación moderna en dispositivos de Office 2013, establezca la clave del registro HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL en un valor de cero. Tenga en cuenta que también se puede usar una clave de registro similar (HKCU\SOFTWARE\Microsoft\Office\ **16,0** \Common\Identity\EnableADAL) para deshabilitar la autenticación moderna en dispositivos de Office 2016.
  
### <a name="clients-where-modern-authentication--adal-isnt-supported"></a>Clientes en los que no se admite la autenticación moderna / ADAL
<a name="BKMK_Support"> </a>

Algunas versiones de cliente no admiten OAuth. Puede comprobar su versión de cliente de Office en la ventana de Agregar y quitar programas del Panel de control para comparar el número de versión de las versiones (o intervalos de versiones) enumeradas aquí:
  
- Cliente de Office 15,0. [0000-4766].\*
    
- Cliente de Office 16,0. [0000-4293].\*
    
- Cliente de Office 16.0.6001.[0000-1032]
    
- Cliente de Office 16,0. [6000-6224].\*
    
> [!NOTE]
> La autenticación moderna y híbrida también está disponible con Skype empresarial local, si quiere saber más, visite [Cómo configurar Skype empresarial local para usar la autenticación moderna híbrida](https://docs.microsoft.com/en-us/office365/enterprise/configure-skype-for-business-for-hybrid-modern-authentication) .
