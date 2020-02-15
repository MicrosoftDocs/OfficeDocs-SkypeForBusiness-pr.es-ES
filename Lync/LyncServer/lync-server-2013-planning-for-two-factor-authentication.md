---
title: 'Lync Server 2013: Planeación de la autenticación en dos fases'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for two-factor authentication
ms:assetid: 16f08710-8961-4659-acbf-ebb95a198fb4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308562(v=OCS.15)
ms:contentKeyID: 54973683
ms.date: 04/06/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba76bbc896c1da2929a584611af0607a51d5afcc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050252"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-two-factor-authentication-in-lync-server-2013"></a>Planeación de la autenticación en dos fases en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2015-04-06_

La siguiente es una lista de consideraciones de implementación al configurar un entorno de Microsoft Lync Server 2013 para que admita la autenticación en dos fases.

<div>

## <a name="client-support"></a>Compatibilidad con clientes

Las actualizaciones acumulativas de Lync 2013 para Lync Server 2013: el cliente de escritorio de julio de 2013 y todos los clientes móviles admiten actualmente la autenticación en dos fases.

</div>

<div>

## <a name="topology-requirements"></a>Requisitos de topología

Se recomienda encarecidamente a los clientes que implementen la autenticación en dos fases con el servicio dedicado Lync Server 2013 con actualizaciones acumulativas para Lync Server 2013: los grupos de usuarios de la periferia, director y usuario de 2013 de julio. Para habilitar la autenticación pasiva para los usuarios de Lync, deben estar deshabilitados otros métodos de autenticación para otros roles y servicios, incluidos los siguientes:


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo de configuración</th>
<th>Tipo de servicio</th>
<th>Rol de servidor</th>
<th>Tipo de autenticación que se va a deshabilitar</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Servicio Web</p></td>
<td><p>WebServer</p></td>
<td><p>Dirección</p></td>
<td><p>Kerberos, NTLM y certificado</p></td>
</tr>
<tr class="even">
<td><p>Servicio Web</p></td>
<td><p>WebServer</p></td>
<td><p>Front-end</p></td>
<td><p>Kerberos, NTLM y certificado</p></td>
</tr>
<tr class="odd">
<td><p>Proxy</p></td>
<td><p>EdgeServer</p></td>
<td><p>Microsoft Edge</p></td>
<td><p>Kerberos y NTLM</p></td>
</tr>
<tr class="even">
<td><p>Proxy</p></td>
<td><p>Dominios</p></td>
<td><p>Front-end</p></td>
<td><p>Kerberos y NTLM</p></td>
</tr>
</tbody>
</table>


A menos que estos tipos de autenticación estén deshabilitados en el nivel de servicio, todas las demás versiones del cliente de Lync no podrán iniciar sesión correctamente una vez que se haya habilitado la autenticación en dos fases dentro de la implementación.

</div>

<div>

## <a name="lync-service-discovery"></a>Detección de servicios de Lync

Los registros DNS que usan los clientes internos o externos para detectar servicios de Lync deben configurarse para que se resuelvan en un servidor de Lync que no está habilitado para la autenticación en dos fases. Con esta configuración, los usuarios de los grupos de Lync que no están habilitados para la autenticación en dos fases no tendrán que especificar un PIN para autenticarse, mientras que los usuarios de los grupos de Lync que estén habilitados para la autenticación en dos fases tendrán que escribir su PIN para autenticar.

</div>

<div>

## <a name="exchange-authentication"></a>Autenticación de Exchange

Los clientes que hayan implementado la autenticación en dos fases de Microsoft Exchange podrían encontrar que determinadas características del cliente de Lync no están disponibles. Actualmente es una característica de diseño, ya que el cliente de Lync no admite la autenticación en dos fases para las características que dependen de la integración de Exchange.

</div>

<div>

## <a name="lync-contacts"></a>Contactos de Lync

Los usuarios de Lync que están configurados para aprovechar la característica de almacenamiento de contactos unificado comprobarán que sus contactos ya no están disponibles después de iniciar sesión con la autenticación en dos fases.

Debe usar el cmdlet **Invoke-CsUcsRollback** para quitar los contactos de usuario existentes del almacén de contactos unificados y almacenarlos en Lync Server 2013 antes de habilitar la autenticación en dos fases.

</div>

<div>

## <a name="skill-search"></a>Búsqueda de aptitudes

Los clientes que hayan configurado la característica de búsqueda de aptitudes en su entorno de Lync comprobarán que esta característica no funciona cuando Lync está habilitado para la autenticación en dos fases. Esto es así por diseño, ya que Microsoft SharePoint no admite actualmente la autenticación en dos fases.

</div>

<div>

## <a name="lync-credentials"></a>Credenciales de Lync

Hay varias consideraciones de implementación que implican las credenciales de Lync guardadas que pueden afectar a los usuarios que están configurados para usar la autenticación en dos fases.

<div>

## <a name="deleting-saved-credentials"></a>Eliminación de credenciales guardadas

Los usuarios de clientes de escritorio deben usar la opción **eliminar mi información de inicio de sesión** en el cliente Lync y eliminar su carpeta de perfil\\SIP\\de\\%\\LocalAppData% Microsoft Office 15,0 Lync antes de intentar iniciar sesión por primera vez mediante la autenticación en dos fases.

</div>

<div>

## <a name="disablentcredentials"></a>DisableNTCredentials

Con el método de autenticación Kerberos o NTLM, las credenciales de Windows del usuario se usan automáticamente para la autenticación. En una implementación típica de Lync Server 2013 en la que se habilita Kerberos o NTLM para la autenticación, los usuarios no deben especificar sus credenciales cada vez que inicien sesión.

Si se solicitan involuntariamente las credenciales a los usuarios antes de que se les pida que especifiquen su PIN, es posible que la clave del registro **DisableNTCredentials** no esté configurada de forma accidental en los equipos cliente, posiblemente a través de la Directiva de grupo.

Para evitar la solicitud adicional de credenciales, cree la siguiente entrada del registro en la estación de trabajo local o use la plantilla administrativa de Lync para aplicarla a todos los usuarios de un grupo de servidores dado mediante la Directiva de Grupo:

HKEY\_directivas\_\\de\\software\\del equipo\\local\\de\\Microsoft Office 15,0 Lync

REG\_DWORD: DisableNTCredentials

Value: 0X0

</div>

<div>

## <a name="savepassword"></a>SavePassword

Cuando un usuario inicia sesión en Lync por primera vez, se le pide al usuario que guarde su contraseña. Si se selecciona, esta opción permite que el certificado de cliente del usuario se almacene en el almacén de certificados personales y que las credenciales de Windows del usuario se almacenen en el administrador de credenciales del equipo local.

La configuración del registro **SavePassword** debe estar deshabilitada cuando Lync está configurado para admitir la autenticación en dos fases. Para evitar que los usuarios guarden sus contraseñas, cambie la siguiente entrada del registro en la estación de trabajo local o use la plantilla administrativa de Lync para aplicarla a todos los usuarios de un grupo de servidores dado mediante la Directiva de Grupo:

HKEY\_actual\_software\\\\para usuarios\\de\\Microsoft\\Office 15,0 Lync

REG\_DWORD: SavePassword

Value: 0X0

</div>

</div>

<div>

## <a name="ad-fs-20-token-replay"></a>Reproducción de tokens 2,0 de AD FS

AD FS 2,0 proporciona una característica denominada detección de reproducción de tokens, por la que se pueden detectar varias solicitudes de tokens que usan el mismo token y, a continuación, descartarse. Si esta característica está habilitada, la detección de reproducción de tokens protege la integridad de las solicitudes de autenticación tanto en el perfil de WS-Federation Passive como en el perfil de SAML WebSSO asegurándose de que el mismo token no se use nunca más de una vez.

Esta característica debe estar habilitada en situaciones en las que la seguridad es una preocupación muy importante, como cuando se usan quioscos. Para obtener más información acerca de la detección de reproducción de tokens, consulte Best Practices for Secure Planning and [http://go.microsoft.com/fwlink/p/?LinkId=309215](http://go.microsoft.com/fwlink/p/?linkid=309215)Deployment of AD FS 2,0 en.

</div>

<div>

## <a name="external-user-access"></a>Acceso de usuarios externos

En estos temas no se incluye la configuración de un proxy de AD FS o proxy inverso para admitir la autenticación de dos factores de Lync desde redes externas.

</div>

</div>

<span> </span>

</div>

</div>

</div>

