---
title: Administrar la autenticación en dos fases en Skype Empresarial Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 16f08710-8961-4659-acbf-ebb95a198fb4
description: 'Resumen: Administrar la autenticación de dos factores en Skype para Business Server 2015.'
ms.openlocfilehash: 5933afc311514e841d7fb96f41988d8f495d0bee
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="manage-two-factor-authentication-in-skype-for-business-server-2015"></a>Administrar la autenticación en dos fases en Skype Empresarial Server 2015
 
**Resumen:** Administrar la autenticación de dos factores en Skype para Business Server 2015.
  
La autenticación en dos fases proporciona seguridad mejorada al exigir a los usuarios que proporcionen dos formas de autenticación o identificación, específicamente una combinación de nombre de usuario/contraseña y un token o certificado. Esto también es conocido como "algo que tiene, algo que sabe". 
  
Un ejemplo típico de autenticación en dos fases con un certificado es el uso de tarjetas inteligentes. Una tarjeta inteligente contiene un certificado asociado con la cuenta del usuario y se puede validar con información de certificado y usuario almacenada en un servidor. Al comparar la información del usuario (nombre de usuario y contraseña) con el certificado proporcionado, el servidor valida las credenciales y autentica al usuario.
  
Considere a los asuntos siguientes al configurar un Skype para entorno Business Server 2015 para admitir la autenticación de dos factores.
  
## <a name="client-support"></a>Compatibilidad con clientes

Las actualizaciones acumulativas de Lync Server 2013: julio de 2013, cliente de escritorio y el Skype para cliente de negocios son los únicos clientes que actualmente admiten la autenticación de dos factores.
  
## <a name="topology-requirements"></a>Requisitos de topología

Los clientes se recomienda encarecidamente implementar autenticación de dos factores mediante Skype dedicado para Business Server 2015 con borde, Director y grupos de usuario. Para habilitar la autenticación pasiva para los usuarios, se necesitan deshabilitar los demás métodos de autenticación para otros roles y servicios, incluidos los siguientes:
  
|**Tipo de configuración**|**Tipo de servicio**|**Función de servidor**|**Tipo de autenticación para deshabilitar**|
|:-----|:-----|:-----|:-----|
|Servicio web  <br/> |Servidor Web  <br/> |Director  <br/> |Kerberos, NTLM y certificado  <br/> |
|Servicio web  <br/> |Servidor Web  <br/> |Front-end  <br/> |Kerberos, NTLM y certificado  <br/> |
|Proxy  <br/> |EdgeServer  <br/> |Perimetral  <br/> |Kerberos y NTLM  <br/> |
|Proxy  <br/> |Registrador  <br/> |Front-end  <br/> |Kerberos y NTLM  <br/> |
   
A menos que estos tipos de autenticación se deshabiliten en el nivel de servicio, ninguna de las demás versiones del cliente podrá iniciar sesión correctamente una vez que la autenticación en dos fases esté habilitada dentro de la implementación.
  
## <a name="skype-for-business-service-discovery"></a>Detección de servicios de Skype Empresarial

Registros DNS utilizados por los clientes internos o externos para descubrir Skype para servicios empresariales deben configurarse para resolver como un Skype para Business server que no está habilitado para la autenticación de dos factores. Con esta configuración, los usuarios de Skype para grupos de negocios que no están habilitados para autenticación de dos factores no le pedirá que escriba un NIP para autenticar, mientras que los usuarios de Skype para grupos de negocios que están habilitados para la autenticación de dos factores pedirá que introduzca su NIP para autenticar.
  
## <a name="exchange-authentication"></a>Autenticación de Exchange

Clientes que han implementado la autenticación de dos factores para Microsoft Exchange pueden encontrar ciertas características en el cliente no están disponibles. Actualmente esto es por diseño, como el Skype para Business client no admite la autenticación de dos factores para las características que dependen de la integración de Exchange.
  
## <a name="contacts"></a>Contactos

Skype para usuarios profesionales que están configurados para aprovechar la característica almacén de contacto unificado encontrará sus contactos ya no están disponibles después de iniciar sesión con autenticación de dos factores.
  
Debe utilizar el cmdlet **Invoke-CsUcsRollback** para quitar contactos de usuario existentes desde el almacén de contacto unificado y almacenarlos en Skype para Business Server 2015 antes de habilitar la autenticación de dos factores.
  
## <a name="skill-search"></a>Búsqueda de aptitudes

Los clientes que han configurado la característica de búsqueda de perfiles en su Skype para el entorno de negocios encontrarán que esta característica no funciona cuando Skype para empresas está habilitado para la autenticación de dos factores. Esto sucede por diseño, ya que Microsoft SharePoint no admite actualmente la autenticación en dos fases.
  
## <a name="credentials"></a>Credenciales

Hay una serie de consideraciones de implementación que implican Skype guardado las credenciales de negocios que puede afectar a los usuarios que están configurados para usar la autenticación de dos factores.
  
### <a name="deleting-saved-credentials"></a>Eliminación de credenciales guardadas

Usuarios deben utilizar la opción **Eliminar mi información de inicio de sesión** en el Skype para cliente de empresa y eliminar su carpeta de perfil SIP de %localappdata%\Microsoft\Office\15.0\Skype para el negocio antes de intentar iniciar sesión por primera vez mediante dos factores autenticación.
  
### <a name="disablentcredentials"></a>DisableNTCredentials

Con el método de autenticación Kerberos o NTLM, las credenciales de Windows se utilizan automáticamente para la autenticación. En un típico Skype para la implementación de Business Server 2015 donde está habilitado Kerberos o NTLM para la autenticación, los usuarios no deben tener que escribir sus credenciales cada vez que inician sesión en.
  
Si se les solicitan de manera no intencionada las credenciales a los usuarios antes de que se les pida especificar su PIN, la clave del Registro **DisableNTCredentials** puede configurarse de manera no intencionada en los equipos cliente, posiblemente a través de la directiva de grupo.
  
Para evitar que la solicitud de credenciales adicional, cree la entrada de registro siguiente en la estación de trabajo o utilizar el Skype para plantillas administrativas de negocio para aplicar a todos los usuarios de un grupo determinado mediante Directiva de grupo:
  
    HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Office\15.0\Lync
  
    REG_DWORD: DisableNTCredentials
  
    Value: 0x0
  
### <a name="savepassword"></a>SavePassword

Cuando un usuario inicia sesión en Skype para el negocio por primera vez, se pide al guardar su contraseña de usuario. Si se selecciona, esta opción permite que el certificado del usuario cliente para almacenarse en el almacén de certificados personales y credenciales de Windows del usuario se almacenan en el Administrador de credenciales del equipo local.
  
La configuración del registro **SavePassword** debe deshabilitarse cuando Skype para empresas está configurado para admitir la autenticación de dos factores. Para impedir que los usuarios guarden sus contraseñas, cambiar la entrada de registro siguiente en la estación de trabajo o utilizar el Skype para plantillas administrativas de negocio para aplicar a todos los usuarios de un grupo determinado mediante Directiva de grupo:
  
    HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync
  
    REG_DWORD: SavePassword
  
    Value: 0x0
  
## <a name="ad-fs-20-token-replay"></a>Reproducción de tokens de AD FS 2.0

AD FS 2.0 proporciona una característica que se conoce como detección de reproducción de tokens, con la cual varias solicitudes de tokens que usan el mismo token se pueden detectar y descartar. Cuando esta característica está habilitada, la detección de reproducción de tokens protege la integridad de las solicitudes de autenticación en el perfil pasivo de la federación WS y el perfil de SAML WebSSO asegurándose de que el mismo token nunca se use más de una vez.
  
Esta característica necesita habilitarse en situaciones donde la seguridad es extremadamente preocupante como cuando se usan quioscos. Para obtener más información acerca de la detección de reproducción token, vea [Prácticas recomendadas para proteger planeamiento e implementación de AD FS 2.0](https://go.microsoft.com/fwlink/p/?LinkId=309215).
  
## <a name="external-user-access"></a>Acceso de usuarios externos

Configurar un Proxy ADFS o Proxy inverso para admitir Skype para autenticación de dos factores de negocios desde redes externas que no se trata en estos temas.
  
## <a name="see-also"></a>Vea también

#### 

[Configurar la autenticación de dos factores en Skype para Business Server 2015](configure.md)
  
[Configurar la autenticación de dos factores en Skype para Business Server 2015](configure.md)

