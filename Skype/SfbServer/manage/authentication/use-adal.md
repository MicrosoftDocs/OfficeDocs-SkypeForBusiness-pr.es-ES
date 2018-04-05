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
description: Este artículo explica cómo utilizar autenticación modernos (que se basa en la biblioteca de autenticación de Active Directory (ADAL) y OAuth 2.0) que se puede encontrar en el de 2016 marzo actualización acumulativa de Skype para el negocio de Skype para Business Server 2015.
ms.openlocfilehash: 9ef430f770b0b5d2ee22f2744e95b6df47fa95b9
ms.sourcegitcommit: ffca287cf70db2cab14cc1a6cb7cea68317bedd1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/05/2018
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a>Cómo usar la autenticación moderna (ADAL) con Skype Empresarial
 
Este artículo explica cómo utilizar autenticación modernos (que se basa en la biblioteca de autenticación de Active Directory (ADAL) y OAuth 2.0) que se puede encontrar en el de 2016 marzo actualización acumulativa de Skype para el negocio de Skype para Business Server 2015.
  
## <a name="whats-in-this-article"></a>¿Qué se incluye en este artículo?

[¿Qué es ADAL?](use-adal.md#BKMK_ADAL)
  
[Configurar ADAL en su grupo y configurar ADFS como un servidor de token de seguridad](use-adal.md#BKMK_Config)
  
[Otras opciones para habilitar el inicio de sesión de ADAL (como aplicaciones cliente de Office)](use-adal.md#BKMK_Options)
  
[Clientes en los que no se admite la autenticación moderna / ADAL](use-adal.md#BKMK_Support)
  
## <a name="what-is-adal"></a>¿Qué es ADAL?
<a name="BKMK_ADAL"> </a>

ADAL es el acrónimo de "Biblioteca de autenticación de Active Directory" y, junto con OAuth 2.0, es fundamental en la autenticación moderna. Esta biblioteca del código está diseñada para disponer de recursos protegidos en el directorio de aplicaciones de cliente (como Skype para empresas) a través de tokens de seguridad. ADAL funciona con OAuth 2.0 para permitir más escenarios de autorización y autenticación, como la autenticación multifactor (MFA) y más formas de autenticación SAML.
  
Varias aplicaciones que actúan como clientes pueden aprovecharse de la autenticación moderna para obtener recursos protegidos. En Skype para Business Server 2015, esta tecnología se utiliza entre clientes locales y servidores locales con el fin de proporcionar a los usuarios un nivel adecuado de autorización de recursos.
  
Las conversaciones de autenticación moderna (que se basan en ADAL y OAuth 2.0) tienen algunos elementos en común.
  
- Hay un cliente que realiza una solicitud para un recurso, en este caso, el cliente Skype para el negocio.
    
- Hay un recurso al que el cliente necesita un nivel específico de acceso, y este recurso está protegido por un servicio de directorio, en este caso, el recurso es Skype para Business Server 2015.
    
- Hay una conexión de OAuth, en otras palabras, una conexión que está dedicado a *autorizar a* un usuario para tener acceso a un recurso. (OAuth también se conoce por el nombre descriptivo, autenticación "de servidor a servidor" y, a menudo, aparece abreviado como S2S).
    
En Skype para conversaciones de negocios servidor 2015 modernos autenticación (ADAL), Skype para Business Server 2015 se comunica a través de ADFS (ADFS 3.0 en Windows Server 2012 R2). La autenticación puede ocurrir con otro proveedor de identidades (IdP), pero el servidor de Skype Empresarial necesita configurarse para poder comunicarse directamente con ADFS. Si no ha configurado ADFS para trabajar con Skype para Business Server 2015 complete la [instalación de ADFS](https://technet.microsoft.com/en-us/library/adfs2-step-by-step-guides%28v=ws.10%29.aspx).
  
ADAL se incluye en el de 2016 marzo actualización acumulativa de Skype para Business Server 2015 y el de 2016 marzo actualización acumulativa de Skype para el negocio **debe** instalarse y es necesario para una configuración correcta.
  
> [!NOTE]
> Con la versión inicial, la autenticación moderna en un entorno local solo se admite si no existe una topología combinada de Skype. Por ejemplo, si el entorno es puramente Skype para Business Server 2015. Esta instrucción puede estar vinculada a cambios. 
  
Debe descargarse un paquete de PowerShell que incluye archivos .ps1 con los comandos que usa ADAL para obtener una configuración correcta.
  
### <a name="configure-adal-in-your-pool-and-set-adfs-as-security-token-server"></a>Configurar ADAL en su grupo y configurar ADFS como un servidor de token de seguridad
<a name="BKMK_Config"> </a>

En este proceso, se conecta la instalación de ADFS a un Skype para Business Server 2015 grupo configurado para ADAL.
  
1. Instalar el de 2016 marzo actualización acumulativa de Skype para Business Server 2015 para su Skype para Business Server 2015 pool o servidor Standard Edition. (Programe la ventana de mantenimiento, según sus necesidades, para ejecutar Windows Update para la instalación automática).
    
2. En sus servidores locales ADFS, [Descargue](https://aka.ms/sfbadalscripts) el programa de instalación-AdfsOAuthTrustForSfB secuencia de comandos. (Esto debe realizarse por cada granja de servidores de ADFS o servidores independientes de ADFS. No es necesario realizarlo en proxy o proxies ADFS).
    
3. Tome nota de los internos y el servicio Web externo completo de nombres de dominio (FQDN) de su Skype para servidor Standard Edition o grupo de servidores de Business Server 2015. Esto debe realizarse para todos los grupos de Skype Empresarial.
    
4. Desde PowerShell en los servidores de ADFS, ejecute el script Setup-AdfsOAuthTrustForSfB. Necesitará escribir las direcciones URL adecuadas para los FQDN de servicios web externos e internos. Aquí se muestra un ejemplo:
    
     `Setup-AdfsOAuthTrustForSfB.ps1 -poolIDs https://contosoSkype.contoso.com,https://contoso01Skype.contosoIn.com`
    
    Para las agrupaciones adicionales, debe agregar manualmente las URL de servicios Web de grupo para el Skype para Business Server 2015 confiar parte confiar en ADFS.
    
    > [!IMPORTANT]
    > No es posible usar a la vez ADAL y la autenticación pasiva para un grupo. Para poder usar ADAL, debe deshabilitar la autenticación pasiva. Para los cmdlets de PowerShell acerca de cómo configurar la autenticación para un grupo de servidores, consulte [este](https://technet.microsoft.com/en-us/library/gg398396.aspx) artículo.
  
    > [!TIP]
    > Si tiene grupos adicionales debe agregarlos como [identificadores](https://technet.microsoft.com/en-us/library/gg557759%28v=ws.10%29.aspx) a confiar parte de confianza de ADFS. > vaya a su servidor de ADFS y abrir Administración de ADFS. Ampliar las relaciones de confianza \> confianza confianzas de fiesta. Haga clic en confiar confía en las partes que se enumeran y propiedades con el botón secundario \> identificadores \> escriba la dirección URL de grupo adicionales \> haga clic en Agregar. 
  
5. Volver a tu Skype de server Business Server 2015 Front-End o Standard Edition. Desde aquí debe ejecutar los cmdlets que crean un servidor OAuth y modificar esa configuración OAuth para trabajar con Skype para el negocio. Sólo necesita realizar este paso una vez por Skype para la implementación de Business Server 2015. Aquí se muestra un ejemplo:
    
     `New-CsOAuthServer -Identity sts.contosoIn.com -Type ADFS -MetadataURL https://sts.contosoIn.com/FederationMetadata/2007-06/FederationMetadata.xml`
    
    > [!TIP]
    > La dirección URL de 'Identidad' verá en este comando es realmente el ADFS federación nombre del servicio se puede ver en la administración de ADFS secundario servicio \> propiedades. 'Tipo' es siempre de ADFS y lo 'MetadataURL' es siempre \<nombre del servicio de ADFS de la\> + "/ FederationMetadata/2007-06/FederationMetadata.xml". 
  
     `Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity sts.contosoIn.com`
    
6. Aún en su Skype para Business Server 2015 Front-End o Standard Edition server, probar la nueva configuración introduciendo la dirección SIP de un usuario y el FQDN del grupo. Sólo necesita realizar este paso una vez por Skype para la implementación de Business Server 2015. Aquí se muestra un ejemplo:
    
     `Test-CsRegistration -UserSipAddress AyakaY@contosoIns.com -TargetFqdn Pool1.contoso.com -Authentication OAuthInteractive`
    
7. Cuando se le solicite, escriba las credenciales del usuario de prueba. Compruebe que la prueba se completa correctamente.
    
    > [!NOTE]
    > Cuando se resuelve la URL de STS para ADFS *internamente* , el aviso que se verá será un indicador de **Seguridad de Windows** . Si la dirección URL se resuelve externamente, verá un aviso denominado **Iniciar sesión**. Normalmente, querríamos un aviso de **Seguridad de Windows** aquí. Tenga en cuenta que este comportamiento cambia, particularmente si ha implementado la Autenticación basada en formularios (FBA).
  
Además, tenga en cuenta que cuando la dirección URL de STS se resuelve como un servidor interno de ADFS y la autenticación integrada de Windows está habilitada en los exploradores, pueden producirse errores de autenticación en los equipos donde muchos usuarios diferentes inician sesión en aplicaciones cliente, a no ser que el explorador esté configurado explícitamente para solicitar las credenciales a los usuarios en una zona de seguridad del explorador determinada. Por ejemplo, piense en un quiosco. La cuenta con sesión iniciada en el sistema operativo puede ser diferente que la cuenta de usuario con sesión iniciada en el cliente de Skype Empresarial. Si este es el caso, consulte los errores que se describen aquí.
    
Puede ver y cambiar esta configuración del explorador en Internet Explorer haciendo clic en \> herramientas (o el engranaje) \> opciones de Internet \> ficha seguridad \> y la zona de seguridad (tales como Intranet Local). Desde este cuadro de diálogo, haga clic en el botón Nivel personalizado y desplácese al final de la lista del cuadro de diálogo Configuración. En la sección autenticación de usuario \> inicio de sesión \> verá una opción para 'Preguntar por el nombre de usuario y la contraseña'. Si tiene quioscos en los que el usuario que inicia el cliente de Skype Empresarial es diferente (tiene una cuenta diferente) del usuario que ha iniciado sesión en el equipo, quizás le interese establecer esta opción en "ACTIVADO" para estas máquinas de la directiva de grupo.
    
Por último y muy importante, tal vez experimente más de un aviso ya que el sistema de seguridad recopila la información que necesita para autenticar o autorizar la cuenta.
    
### <a name="other-options-for-enabling-adal-sign-in-like-office-client-apps"></a>Otras opciones para habilitar el inicio de sesión de ADAL (como aplicaciones cliente de Office)
<a name="BKMK_Options"> </a>

Ahora que ADAL está configurado para su Skype para empresas y (automáticamente) para aplicaciones cliente de Office 2016 entre plataformas, puede que desee aprovechar para Exchange Online (que no es 'On' de forma predeterminada), o en los clientes de Office 2013.
  
> [!IMPORTANT]
> ¿Necesita saber qué esperar de los inicios de sesión con autenticación moderna de sus aplicaciones cliente? Eche un vistazo a [modernos cómo funciona la autenticación para aplicaciones de cliente de Office 2013 y 2016 de Office](https://support.office.com/en-us/article/How-modern-authentication-works-for-Office-2013-and-Office-2016-client-apps-e4c45989-4b1a-462e-a81b-2a13191cf517?ui=en-US&amp;rs=en-US&amp;ad=US). 
  
Para activar la autenticación modernos para Exchange Online, necesitará ejecutar algunos cmdlets de PowerShell. En el caso de aplicaciones cliente de Office 2013, debe cambiar algunas claves del registro en los equipos cliente.
  
- Conectarse a Exchange Online y ejecute los siguientes cmdlets:
    
     `Set-OrganizationConfig -OAuth2ClientProfileEnabled:$true`
    
     `Get-OrganizationConfig | ft name, *OAuth*`
    
- Establezca estas claves del registro para cada dispositivo o equipo en el que quiera habilitar la autenticación moderna. Necesitará un GPO para organizaciones más grandes. Para obtener información sobre cómo crear un GPO, vea la 'crear un objeto de directiva de grupo para modificar el registro en los equipos unidos a un dominio' de [este ](https://support.office.com/en-us/article/Switching-between-the-Skype-for-Business-and-the-Lync-client-user-interfaces-a2394a4c-7522-484c-a047-7b3289742be0)artículo.
    
|Clave del registro  <br/> |Tipo  <br/> |Valor  <br/> |
|:-----|:-----|:-----|
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL  <br/> |REG_DWORD  <br/> |1  <br/> |
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version  <br/> |REG_DWORD  <br/> |1  <br/> |
   
Una vez establecidas estas claves, establecer sus aplicaciones de Office 2013 utilizar [Autenticación con autenticación (AMF) con Office 365](https://support.office.com/en-us/article/Set-up-multi-factor-authentication-for-Office-365-8f0454b2-f51a-4d9c-bcde-2c48e41621c6?ui=en-US&amp;rs=en-US&amp;ad=US).
  
> [!TIP]
> Para deshabilitar la autenticación modernos en dispositivos para Office 2013, establezca la clave del registro HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL en un valor de cero. Tenga en cuenta que también puede utilizarse una clave del Registro similar (HKCU\SOFTWARE\Microsoft\Office\ **16.0** \Common\Identity\EnableADAL) para deshabilitar la autenticación modernos en dispositivos de 2016 de Office.
  
### <a name="clients-where-modern-authentication--adal-isnt-supported"></a>Clientes en los que no se admite la autenticación moderna / ADAL
<a name="BKMK_Support"> </a>

Algunas versiones de cliente no admiten OAuth. Puede comprobar su versión de cliente de Office en la ventana de Agregar y quitar programas del Panel de control para comparar el número de versión de las versiones (o intervalos de versiones) enumeradas aquí:
  
- Cliente de Office 15.0. [0000-4766].\*
    
- Cliente de Office 16.0. [0000-4293.]\*
    
- Cliente de Office 16.0.6001.[0000-1032]
    
- Cliente de Office 16.0. [6000-6224].\*
    

