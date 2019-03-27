---
title: Administrar la autenticación de dos factores en Skype para Business Server
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 16f08710-8961-4659-acbf-ebb95a198fb4
description: 'Resumen: Administrar la autenticación de dos factores en Skype para Business Server.'
ms.openlocfilehash: ce6d43b8ace741a754cb4406235534fd83e414b3
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30888405"
---
# <a name="manage-two-factor-authentication-in-skype-for-business-server"></a>Administrar la autenticación de dos factores en Skype para Business Server
 
**Resumen:** Administrar la autenticación de dos factores en Skype para Business Server.
  
La autenticación en dos fases proporciona seguridad mejorada al exigir a los usuarios que proporcionen dos formas de autenticación o identificación, específicamente una combinación de nombre de usuario/contraseña y un token o certificado. Esto es también conocida como "algo que tiene, algo que sabe." 
  
Un ejemplo típico de autenticación en dos fases con un certificado es el uso de tarjetas inteligentes. Una tarjeta inteligente contiene un certificado asociado con la cuenta del usuario y se puede validar con información de certificado y usuario almacenada en un servidor. Al comparar la información del usuario (nombre de usuario y contraseña) con el certificado proporcionado, el servidor valida las credenciales y autentica al usuario.
  
Tenga en cuenta a los siguientes asuntos al configurar un Skype para entorno Business Server para admitir la autenticación en dos fases.
  
## <a name="client-support"></a>Compatibilidad con clientes

Las actualizaciones acumulativas para Lync Server 2013: julio de 2013 el Skype para clientes empresariales y cliente de escritorio son los únicos clientes que admiten actualmente la autenticación en dos fases.
  
## <a name="topology-requirements"></a>Requisitos de topología

Los clientes se recomienda encarecidamente implementar la autenticación en dos fases mediante Skype dedicada para Business Server con borde, el Director y grupos de usuario. Para habilitar la autenticación pasiva para los usuarios, se necesitan deshabilitar los demás métodos de autenticación para otros roles y servicios, incluidos los siguientes:
  
|**Tipo de configuración**|**Tipo de servicio**|**Función de servidor**|**Tipo de autenticación para deshabilitar**|
|:-----|:-----|:-----|:-----|
|Servicio web  <br/> |WebServer  <br/> |Director  <br/> |Kerberos, NTLM y certificado  <br/> |
|Servicio web  <br/> |WebServer  <br/> |Front-end  <br/> |Kerberos, NTLM y certificado  <br/> |
|Proxy  <br/> |EdgeServer  <br/> |Perimetral  <br/> |Kerberos y NTLM  <br/> |
|Proxy  <br/> |Registrador  <br/> |Front-end  <br/> |Kerberos y NTLM  <br/> |
   
A menos que estos tipos de autenticación se deshabiliten en el nivel de servicio, ninguna de las demás versiones del cliente podrá iniciar sesión correctamente una vez que la autenticación en dos fases esté habilitada dentro de la implementación.
  
## <a name="skype-for-business-service-discovery"></a>Detección de servicios de Skype Empresarial

Los registros DNS utilizados por los clientes internos o externos para detectar Skype para servicios de negocios deben configurarse para resolver a un Skype para Business server que no está habilitado para la autenticación en dos fases. Con esta configuración, no se pedirá a los usuarios de Skype para grupos de negocio que no están habilitados para la autenticación en dos fases para escribir un PIN para autenticar, mientras que los usuarios de Skype para grupos de negocio que están habilitados para la autenticación en dos fases necesario para escribir su PIN para autenticar.
  
## <a name="exchange-authentication"></a>Autenticación de Exchange

Los clientes que han implementado la autenticación en dos fases para Microsoft Exchange es posible que encuentre que ciertas características en el cliente no están disponibles. Esto es actualmente por diseño, tal como la Skype para clientes empresariales no es compatible con la autenticación en dos fases para las características que dependen de la integración de Exchange.
  
## <a name="contacts"></a>Contactos

Skype para los usuarios de negocio que están configurados para aprovechar la característica de almacén de contactos unificados encontrará que sus contactos ya no están disponibles después de iniciar sesión con autenticación de dos factores.
  
Debe usar el cmdlet **Invoke-CsUcsRollback** para quitar los contactos existentes de usuario desde el almacén de contactos unificados y almacenar en Skype para Business Server antes de habilitar la autenticación en dos fases.
  
## <a name="skill-search"></a>Búsqueda de aptitudes

Los clientes que han configurado la característica de búsqueda de aptitudes en su Skype para el entorno de negocios encontrarán que esta característica no funciona cuando Skype para la empresa está habilitado para la autenticación en dos fases. Esto sucede por diseño, ya que Microsoft SharePoint no admite actualmente la autenticación en dos fases.
  
## <a name="credentials"></a>Credenciales

Hay una serie de consideraciones de implementación que implican guardada Skype para las credenciales de negocio que pueden afectar a los usuarios que están configurados para usar la autenticación en dos fases.
  
### <a name="deleting-saved-credentials"></a>Eliminación de credenciales guardadas

Los usuarios deben usar la opción **Eliminar mi información de inicio de sesión** en el Skype para clientes empresariales y eliminar su carpeta de perfil SIP de %localappdata%\Microsoft\Office\15.0\Skype para la empresa antes de intentar iniciar sesión por primera vez con dos fases autenticación.
  
### <a name="disablentcredentials"></a>DisableNTCredentials

Con el método de autenticación NTLM o Kerberos, las credenciales de Windows del usuario se usan automáticamente para la autenticación. En una típica Skype para la implementación de Business Server donde está habilitado Kerberos o NTLM para la autenticación, los usuarios no deben tener que escribir sus credenciales cada vez que inician sesión en.
  
Si se les solicitan de manera no intencionada las credenciales a los usuarios antes de que se les pida especificar su PIN, la clave del Registro **DisableNTCredentials** puede configurarse de manera no intencionada en los equipos cliente, posiblemente a través de la directiva de grupo.
  
Para evitar que el símbolo del sistema adicional para las credenciales, crear la entrada del registro siguiente en la estación de trabajo local o usar el Skype para la plantilla administrativa de negocio que se debe para aplicar a todos los usuarios para un determinado grupo de servidores con la directiva de grupo:
  
    HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Office\15.0\Lync
  
    REG_DWORD: DisableNTCredentials
  
    Value: 0x0
  
### <a name="savepassword"></a>SavePassword

Cuando un usuario inicia sesión en Skype para la empresa por primera vez, se pide al usuario que guarde su contraseña. Si se selecciona, esta opción permite que el certificado del usuario cliente deben almacenarse en el almacén de certificados personal y credenciales de Windows del usuario se almacenen en el Administrador de credenciales del equipo local.
  
La configuración del registro de **SavePassword** debe deshabilitarse cuando Skype para la empresa está configurado para admitir la autenticación en dos fases. Para impedir que los usuarios guarden sus contraseñas, cambie la entrada del registro siguiente en la estación de trabajo local o usar el Skype para la plantilla administrativa de negocio que se debe para aplicar a todos los usuarios para un determinado grupo de servidores con la directiva de grupo:
  
    HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync
  
    REG_DWORD: SavePassword
  
    Value: 0x0
  
## <a name="ad-fs-20-token-replay"></a>Reproducción de tokens de AD FS 2.0

AD FS 2.0 proporciona una característica que se conoce como detección de reproducción de tokens, con la cual varias solicitudes de tokens que usan el mismo token se pueden detectar y descartar. Cuando esta característica está habilitada, la detección de reproducción de tokens protege la integridad de las solicitudes de autenticación en el perfil pasivo de la federación WS y el perfil de SAML WebSSO asegurándose de que el mismo token nunca se use más de una vez.
  
Esta característica necesita habilitarse en situaciones donde la seguridad es extremadamente preocupante como cuando se usan quioscos. Para obtener más información acerca de la detección de reproducción de tokens, vea [Procedimientos recomendados para proteger planeación e implementación de AD FS 2.0](https://go.microsoft.com/fwlink/p/?LinkId=309215).
  
## <a name="external-user-access"></a>Acceso de usuarios externos

En estos temas no se trata la configuración de un Proxy de AD FS o el Proxy inverso para admitir Skype para la autenticación de dos factores de profesionales de redes externas.
  
## <a name="see-also"></a>Consulte también

[Configuración de autenticación de dos factores en Skype para Business Server](configure-two-factor.md)
  
