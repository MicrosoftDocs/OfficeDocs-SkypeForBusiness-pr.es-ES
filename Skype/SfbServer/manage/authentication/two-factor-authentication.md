---
title: Administrar la autenticación en dos fases en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 16f08710-8961-4659-acbf-ebb95a198fb4
description: 'Resumen: administrar la autenticación en dos fases en Skype Empresarial Server.'
ms.openlocfilehash: 1b899dce829e016e60435584c18481d03810a876e7c8b85665b75b94574374b7
ms.sourcegitcommit: 2a76435beaac1e5daa647e93f693ea8672ec0135
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/11/2021
ms.locfileid: "57849995"
---
# <a name="manage-two-factor-authentication-in-skype-for-business-server"></a>Administrar la autenticación en dos fases en Skype Empresarial Server
 
**Resumen:** Administrar la autenticación en dos fases Skype Empresarial Server.
  
La autenticación en dos fases proporciona una seguridad mejorada al requerir que los usuarios proporcionen dos formas de autenticación o identificación, es decir, una combinación de nombre de usuario y contraseña y un token o certificado. Esto también se conoce como "algo que tienes, algo que sabes". 
  
Un ejemplo típico de autenticación en dos fases con un certificado es el uso de tarjetas inteligentes. Una tarjeta inteligente contiene un certificado asociado a la cuenta de usuario y se puede validar con la información de usuario y certificado almacenada en un servidor. Al comparar la información de usuario (nombre de usuario y contraseña) con el certificado proporcionado, el servidor valida las credenciales y autentica al usuario.
  
Tenga en cuenta los siguientes temas al configurar un entorno Skype Empresarial Server para admitir la autenticación en dos fases.
  
## <a name="client-support"></a>Soporte técnico de cliente

Las actualizaciones acumulativas para Lync Server 2013: cliente de escritorio de julio de 2013 y el cliente Skype Empresarial son los únicos clientes que admiten actualmente la autenticación en dos fases.
  
## <a name="topology-requirements"></a>Requisitos de topología

Se recomienda a los clientes que implemente la autenticación en dos fases Skype Empresarial Server con grupos de servidores perimetrales, directores y usuarios. Para habilitar la autenticación pasiva para los usuarios, se deben deshabilitar otros métodos de autenticación para otros roles y servicios, incluidos los siguientes:
  
|**Tipo de configuración**|**Tipo de servicio**|**Rol del servidor**|**Tipo de autenticación que se deshabilitará**|
|:-----|:-----|:-----|:-----|
|Servicio Web  <br/> |WebServer  <br/> |Director  <br/> |Kerberos, NTLM y Certificado  <br/> |
|Servicio Web  <br/> |WebServer  <br/> |Front-end  <br/> |Kerberos, NTLM y Certificado  <br/> |
|Proxy  <br/> |EdgeServer  <br/> |Microsoft Edge  <br/> |Kerberos y NTLM  <br/> |
|Proxy  <br/> |Registrador  <br/> |Front-end  <br/> |Kerberos y NTLM  <br/> |
   
A menos que estos tipos de autenticación estén deshabilitados en el nivel de servicio, todas las demás versiones del cliente no podrán iniciar sesión correctamente una vez habilitada la autenticación en dos fases en la implementación.
  
## <a name="skype-for-business-service-discovery"></a>Skype Empresarial Detección de servicios

Los registros DNS usados por clientes internos o externos para detectar los servicios Skype Empresarial deben configurarse para resolverse en un servidor Skype Empresarial que no esté habilitado para la autenticación en dos fases. Con esta configuración, los usuarios de grupos de servidores de Skype Empresarial que no estén habilitados para la autenticación en dos fases no tendrán que escribir un PIN para autenticarse, mientras que los usuarios de grupos de servidores de Skype Empresarial habilitados para la autenticación en dos fases tendrán que escribir su PIN para autenticarse.
  
## <a name="exchange-authentication"></a>Exchange Autenticación

Los clientes que han implementado la autenticación en dos fases para Microsoft Exchange pueden encontrar que ciertas características del cliente no están disponibles. Este comportamiento es por diseño, ya que el cliente Skype Empresarial no admite la autenticación en dos fases para las características que dependen de Exchange integración.
  
## <a name="contacts"></a>Contactos

Skype Empresarial usuarios que están configurados para aprovechar la característica almacén de contactos unificados encontrarán que sus contactos ya no están disponibles después de iniciar sesión con la autenticación en dos fases.
  
Debe usar el cmdlet **Invoke-CsUcsRollback** para quitar los contactos de usuario existentes del almacén de contactos unificado y almacenarlos en Skype Empresarial Server antes de habilitar la autenticación en dos fases.
  
## <a name="skill-search"></a>Búsqueda de aptitudes

Los clientes que han configurado la característica de búsqueda de aptitudes en su entorno Skype Empresarial encontrarán que esta característica no funciona cuando Skype Empresarial está habilitada para la autenticación en dos fases. Esto es por diseño, ya que Microsoft SharePoint actualmente no admite la autenticación en dos fases.
  
## <a name="credentials"></a>Credenciales

Hay una serie de consideraciones de implementación que implican credenciales Skype Empresarial que pueden afectar a los usuarios que están configurados para usar la autenticación en dos fases.
  
### <a name="deleting-saved-credentials"></a>Eliminación de credenciales guardadas

Los usuarios  deben usar la opción Eliminar mi información de inicio de sesión en el cliente de Skype Empresarial y eliminar su carpeta de perfil SIP de %localappdata%\Microsoft\Office\15.0\Skype Empresarial antes de intentar iniciar sesión por primera vez mediante la autenticación en dos fases.
  
### <a name="disablentcredentials"></a>DisableNTCredentials

Con el método de autenticación Kerberos o NTLM, las credenciales Windows usuario se usan automáticamente para la autenticación. En una implementación típica Skype Empresarial Server donde Kerberos o NTLM está habilitado para la autenticación, los usuarios no deben tener que escribir sus credenciales cada vez que inicien sesión.
  
Si a los usuarios se les piden credenciales sin especificar antes de que se les pida que escriban su PIN, es posible que la clave del Registro **DisableNTCredentials** esté configurada de forma involuntara en los equipos cliente, posiblemente a través de la directiva de grupo.
  
Para evitar el mensaje adicional de credenciales, cree la siguiente entrada del Registro en la estación de trabajo local o use la plantilla administrativa Skype Empresarial para aplicar a todos los usuarios de un grupo determinado mediante la directiva de grupo:
  
HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Office\15.0\Lync
  
REG_DWORD: DisableNTCredentials

Valor: 0x0
  
### <a name="savepassword"></a>SavePassword

Cuando un usuario inicia sesión Skype Empresarial por primera vez, se le pide que guarde su contraseña. Si se selecciona, esta opción permite que el certificado de cliente del usuario se almacene en el almacén de certificados personal y las credenciales de Windows del usuario se almacenen en el Administrador de credenciales del equipo local.
  
La configuración del Registro **SavePassword** debe deshabilitarse Skype Empresarial se configura para admitir la autenticación en dos fases. Para evitar que los usuarios guarden sus contraseñas, cambie la siguiente entrada del Registro en la estación de trabajo local o use la plantilla administrativa Skype Empresarial para aplicar a todos los usuarios de un grupo determinado mediante la directiva de grupo:
  
HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync
  
REG_DWORD: SavePassword
  
Valor: 0x0
  
## <a name="ad-fs-20-token-replay"></a>Reproducción de tokens de AD FS 2.0

AD FS 2.0 proporciona una característica denominada detección de reproducción de tokens, mediante la cual se pueden detectar y descartar varias solicitudes de token con el mismo token. Cuando esta característica está habilitada, la detección de reproducción de tokens protege la integridad de las solicitudes de autenticación tanto en el perfil pasivo de WS-Federation como en el perfil webSSO de SAML al asegurarse de que el mismo token nunca se usa más de una vez.
  
Esta característica debe habilitarse en situaciones en las que la seguridad es una preocupación muy alta, como cuando se usan quioscos. Para obtener más información acerca de la detección de reproducción de tokens, vea Procedimientos recomendados para la planeación e implementación seguras de [AD FS 2.0](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ff630160(v=ws.10)).
  
## <a name="guest-user-access"></a>Acceso de usuario invitado

La configuración de un proxy ADFS o proxy inverso para admitir Skype Empresarial autenticación en dos fases desde redes externas no se trata en estos temas.
  
## <a name="see-also"></a>Consulta también

[Configurar la autenticación en dos fases en Skype Empresarial Server](configure-two-factor.md)
