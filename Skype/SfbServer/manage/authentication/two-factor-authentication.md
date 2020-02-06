---
title: Administrar la autenticación en dos fases en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 16f08710-8961-4659-acbf-ebb95a198fb4
description: 'Resumen: administre la autenticación en dos fases en Skype empresarial Server.'
ms.openlocfilehash: 90dc286e247c0c6eeb75bb884071b85e57663278
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818722"
---
# <a name="manage-two-factor-authentication-in-skype-for-business-server"></a>Administrar la autenticación en dos fases en Skype empresarial Server
 
**Resumen:** Administrar la autenticación en dos fases en Skype empresarial Server.
  
La autenticación en dos fases proporciona seguridad mejorada al exigir a los usuarios que proporcionen dos formas de autenticación o identificación, específicamente una combinación de nombre de usuario/contraseña y un token o certificado. Esto también se conoce como "algo que tienes, algo que conoces". 
  
Un ejemplo típico de autenticación en dos fases con un certificado es el uso de tarjetas inteligentes. Una tarjeta inteligente contiene un certificado asociado con la cuenta del usuario y se puede validar con información de certificado y usuario almacenada en un servidor. Al comparar la información del usuario (nombre de usuario y contraseña) con el certificado proporcionado, el servidor valida las credenciales y autentica al usuario.
  
Tenga en cuenta lo siguiente cuando configure un entorno de Skype empresarial Server para que admita la autenticación en dos fases.
  
## <a name="client-support"></a>Compatibilidad con clientes

Las actualizaciones acumulativas para Lync Server 2013: el cliente de escritorio de julio de 2013 y el cliente de Skype empresarial son los únicos clientes que admiten actualmente la autenticación de dos factores.
  
## <a name="topology-requirements"></a>Requisitos de topología

Se recomienda a los clientes implementar la autenticación en dos fases con un servidor dedicado de Skype empresarial con las agrupaciones de Edge, director y usuario. Para habilitar la autenticación pasiva para los usuarios, se necesitan deshabilitar los demás métodos de autenticación para otros roles y servicios, incluidos los siguientes:
  
|**Tipo de configuración**|**Tipo de servicio**|**Rol de servidor**|**Tipo de autenticación para deshabilitar**|
|:-----|:-----|:-----|:-----|
|Servicio web  <br/> |WebServer  <br/> |Director  <br/> |Kerberos, NTLM y certificado  <br/> |
|Servicio web  <br/> |WebServer  <br/> |Front-end  <br/> |Kerberos, NTLM y certificado  <br/> |
|Proxy  <br/> |EdgeServer  <br/> |Perimetral  <br/> |Kerberos y NTLM  <br/> |
|Proxy  <br/> |Registrador  <br/> |Front-end  <br/> |Kerberos y NTLM  <br/> |
   
A menos que estos tipos de autenticación se deshabiliten en el nivel de servicio, ninguna de las demás versiones del cliente podrá iniciar sesión correctamente una vez que la autenticación en dos fases esté habilitada dentro de la implementación.
  
## <a name="skype-for-business-service-discovery"></a>Detección de servicios de Skype Empresarial

Los registros DNS usados por clientes internos o externos para descubrir servicios de Skype empresarial se deben configurar para que se resuelvan en un servidor de Skype empresarial que no esté habilitado para la autenticación en dos fases. Con esta configuración, los usuarios de grupos de Skype para empresas que no estén habilitados para la autenticación de dos factores no tendrán que introducir un PIN para autenticar, mientras que los usuarios de los grupos de Skype empresarial habilitados para la autenticación en dos fases se necesario para introducir su PIN para autenticar.
  
## <a name="exchange-authentication"></a>Autenticación de Exchange

Es posible que los clientes que hayan implementado la autenticación en dos fases de Microsoft Exchange no encuentren disponibles determinadas características del cliente. Esto se ha hecho por diseño, ya que el cliente de Skype empresarial no admite la autenticación en dos fases para características que dependen de la integración de Exchange.
  
## <a name="contacts"></a>Contactos

Los usuarios de Skype empresarial que estén configurados para aprovechar la característica de almacenamiento de contactos unificado encontrarán que sus contactos ya no están disponibles después de iniciar sesión con la autenticación en dos fases.
  
Debe usar el cmdlet **Invoke-CsUcsRollback** para quitar los contactos de usuario existentes del almacén de contactos unificado y almacenarlos en Skype empresarial Server antes de habilitar la autenticación en dos fases.
  
## <a name="skill-search"></a>Búsqueda de aptitudes

Los clientes que hayan configurado la característica de búsqueda de aptitudes en su entorno de Skype empresarial encontrarán que esta característica no funciona cuando Skype empresarial está habilitado para la autenticación en dos fases. Esto sucede por diseño, ya que Microsoft SharePoint no admite actualmente la autenticación en dos fases.
  
## <a name="credentials"></a>Credenciales

Existen diversas consideraciones de implementación que afectan a las credenciales de Skype empresarial guardadas, que pueden afectar a los usuarios que están configurados para usar la autenticación en dos fases.
  
### <a name="deleting-saved-credentials"></a>Eliminación de credenciales guardadas

Los usuarios deben usar la opción **eliminar mi información de inicio de sesión** en el cliente de Skype empresarial y eliminar su carpeta de perfil SIP de%LocalAppData%\Microsoft\Office\15.0\Skype para empresas antes de intentar iniciar sesión por primera vez con la autenticación en dos fases.
  
### <a name="disablentcredentials"></a>DisableNTCredentials

Con el método de autenticación Kerberos o NTLM, las credenciales de Windows del usuario se usan automáticamente para la autenticación. En una implementación típica de Skype empresarial Server donde se habilita Kerberos o NTLM para la autenticación, los usuarios no deben especificar sus credenciales cada vez que inicien sesión.
  
Si se les solicitan de manera no intencionada las credenciales a los usuarios antes de que se les pida especificar su PIN, la clave del Registro **DisableNTCredentials** puede configurarse de manera no intencionada en los equipos cliente, posiblemente a través de la directiva de grupo.
  
Para evitar la solicitud de credenciales adicionales, cree la siguiente entrada de registro en la estación de trabajo local o use la plantilla administrativa de Skype empresarial para aplicar a todos los usuarios de un grupo determinado mediante una directiva de Grupo:
  
    HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Office\15.0\Lync
  
    REG_DWORD: DisableNTCredentials
  
    Value: 0x0
  
### <a name="savepassword"></a>SavePassword

Cuando un usuario inicia sesión en Skype empresarial por primera vez, se le pide al usuario que guarde su contraseña. Si se selecciona, esta opción permite que el certificado de cliente del usuario se almacene en el almacén de certificados personales y las credenciales de Windows del usuario para que se almacenen en el administrador de credenciales del equipo local.
  
La configuración del registro **SavePassword** debe estar deshabilitada cuando Skype empresarial está configurado para admitir la autenticación en dos fases. Para impedir que los usuarios guarden sus contraseñas, cambie la siguiente entrada del registro en la estación de trabajo local o use la plantilla administrativa de Skype empresarial para aplicar a todos los usuarios de un grupo determinado mediante una directiva de Grupo:
  
    HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync
  
    REG_DWORD: SavePassword
  
    Value: 0x0
  
## <a name="ad-fs-20-token-replay"></a>Reproducción de tokens de AD FS 2.0

AD FS 2.0 proporciona una característica que se conoce como detección de reproducción de tokens, con la cual varias solicitudes de tokens que usan el mismo token se pueden detectar y descartar. Cuando esta característica está habilitada, la detección de reproducción de tokens protege la integridad de las solicitudes de autenticación en el perfil pasivo de la federación WS y el perfil de SAML WebSSO asegurándose de que el mismo token nunca se use más de una vez.
  
Esta característica necesita habilitarse en situaciones donde la seguridad es extremadamente preocupante como cuando se usan quioscos. Para obtener más información sobre la detección de reproducción de tokens, vea [procedimientos recomendados para la planeación y la implementación de AD FS 2,0](https://go.microsoft.com/fwlink/p/?LinkId=309215).
  
## <a name="external-user-access"></a>Acceso de usuarios externos

En estos temas no se aborda la configuración de un proxy de ADFS o proxy inverso para admitir la autenticación de dos factores de Skype empresarial desde redes externas.
  
## <a name="see-also"></a>Vea también

[Configurar la autenticación en dos fases en Skype empresarial Server](configure-two-factor.md)
  
