---
title: 'Lync Server 2013: planeamiento de la autenticación en dos fases'
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
ms.openlocfilehash: e610990182e01c0e9e2d7199bd3a34f70fbe3132
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41750440"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-two-factor-authentication-in-lync-server-2013"></a>Planeamiento de la autenticación en dos fases en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2015-04-06_

A continuación se muestra una lista de consideraciones de implementación al configurar un entorno de Microsoft Lync Server 2013 para admitir la autenticación en dos fases.

<div>

## <a name="client-support"></a>Compatibilidad con clientes

Las actualizaciones acumulativas de Lync 2013 para Lync Server 2013: el cliente de escritorio de julio 2013 y todos los clientes móviles admiten actualmente la autenticación de dos factores.

</div>

<div>

## <a name="topology-requirements"></a>Requisitos de topología

Se recomienda a los clientes implementar la autenticación en dos fases con la aplicación dedicada de Lync Server 2013 con las actualizaciones acumulativas para Lync Server 2013:2013 de julio de, director y grupos de usuarios. Para habilitar la autenticación pasiva para los usuarios de Lync, deben estar deshabilitados otros métodos de autenticación para otros roles y servicios, entre los que se incluyen los siguientes:


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
<th>Rol del servidor</th>
<th>Tipo de autenticación para deshabilitar</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Servicio web</p></td>
<td><p>WebServer</p></td>
<td><p>Director</p></td>
<td><p>Kerberos, NTLM y certificado</p></td>
</tr>
<tr class="even">
<td><p>Servicio web</p></td>
<td><p>WebServer</p></td>
<td><p>Front-end</p></td>
<td><p>Kerberos, NTLM y certificado</p></td>
</tr>
<tr class="odd">
<td><p>Proxy</p></td>
<td><p>EdgeServer</p></td>
<td><p>Perimetral</p></td>
<td><p>Kerberos y NTLM</p></td>
</tr>
<tr class="even">
<td><p>Proxy</p></td>
<td><p>Registrador</p></td>
<td><p>Front-end</p></td>
<td><p>Kerberos y NTLM</p></td>
</tr>
</tbody>
</table>


A menos que estos tipos de autenticación estén deshabilitados en el nivel de servicio, todas las demás versiones del cliente de Lync no podrán iniciar sesión correctamente una vez que la autenticación en dos fases esté habilitada dentro de la implementación.

</div>

<div>

## <a name="lync-service-discovery"></a>Detección de servicios de Lync

Los registros DNS usados por clientes internos o externos para descubrir servicios de Lync deben configurarse para que se resuelvan en un servidor de Lync que no esté habilitado para la autenticación en dos fases. Con esta configuración, los usuarios de los grupos de Lync que no están habilitados para la autenticación de dos factores no necesitarán especificar un PIN para autenticar, mientras que los usuarios de los grupos de Lync que estén habilitados para la autenticación en dos fases deberán introducir su PIN para autenticar.

</div>

<div>

## <a name="exchange-authentication"></a>Autenticación de Exchange

Es posible que los clientes que hayan implementado la autenticación en dos fases de Microsoft Exchange no se encuentren disponibles determinadas características del cliente de Lync. Esto se ha hecho por diseño, ya que el cliente de Lync no admite la autenticación en dos fases para las características que dependen de la integración de Exchange.

</div>

<div>

## <a name="lync-contacts"></a>Contactos de Lync

Los usuarios de Lync que estén configurados para usar la característica de almacenamiento de contactos unificado encontrarán que sus contactos ya no están disponibles después de iniciar sesión con la autenticación en dos fases.

Debe usar el cmdlet **Invoke-CsUcsRollback** para quitar los contactos de usuario existentes del almacén de contactos unificado y almacenarlos en Lync Server 2013 antes de habilitar la autenticación en dos fases.

</div>

<div>

## <a name="skill-search"></a>Búsqueda de aptitudes

Los clientes que hayan configurado la característica de búsqueda de aptitudes en su entorno de Lync encontrarán que esta característica no funciona cuando Lync está habilitado para la autenticación en dos fases. Esto sucede por diseño, ya que Microsoft SharePoint no admite actualmente la autenticación en dos fases.

</div>

<div>

## <a name="lync-credentials"></a>Credenciales de Lync

Hay varias consideraciones de implementación que afectan a las credenciales de Lync guardadas que pueden afectar a los usuarios que están configurados para usar la autenticación en dos fases.

<div>

## <a name="deleting-saved-credentials"></a>Eliminación de credenciales guardadas

Los usuarios de clientes de escritorio deben usar la opción **eliminar mi información de inicio de sesión** en el cliente de Lync y eliminar su carpeta de\\perfil\\SIP\\de\\% LocalAppData% Microsoft Office 15,0 Lync antes de intentar iniciar sesión por primera vez con la autenticación en dos fases.

</div>

<div>

## <a name="disablentcredentials"></a>DisableNTCredentials

Con el método de autenticación NTLM o Kerberos, las credenciales de Windows de los usuarios se utilizan automáticamente para la autenticación. En una implementación típica de Lync Server 2013 donde se habilita Kerberos o NTLM para la autenticación, los usuarios no deben especificar sus credenciales cada vez que inicien sesión.

Si se les solicitan de manera no intencionada las credenciales a los usuarios antes de que se les pida especificar su PIN, la clave del Registro **DisableNTCredentials** puede configurarse de manera no intencionada en los equipos cliente, posiblemente a través de la directiva de grupo.

Para evitar la solicitud de credenciales adicionales, cree la siguiente entrada de registro en la estación de trabajo local o use la plantilla administrativa de Lync para aplicar a todos los usuarios de un grupo determinado mediante una directiva de Grupo:

HKEY\_directivas\_\\de\\software\\del equipo\\local\\de\\Microsoft Office 15,0 Lync

REG\_DWORD: DisableNTCredentials

Valor: 0x0

</div>

<div>

## <a name="savepassword"></a>SavePassword

Cuando un usuario inicia sesión en Lync por primera vez, se le pide que guarde su contraseña. Si se selecciona, esta opción permite que el certificado del cliente del usuario se almacene en el almacén de certificados personales y que las credenciales de Windows del usuario se almacenen en el Administrador de credenciales del equipo local.

La configuración del registro **SavePassword** debe estar deshabilitada cuando Lync está configurado para admitir la autenticación en dos fases. Para evitar que los usuarios guarden sus contraseñas, cambie la siguiente entrada del registro en la estación de trabajo local o use la plantilla administrativa de Lync para aplicar a todos los usuarios de una agrupación determinada mediante una directiva de Grupo:

HKEY\_current\_USER\\software\\Microsoft\\Office\\15,0\\Lync

REG\_DWORD: SavePassword

Valor: 0x0

</div>

</div>

<div>

## <a name="ad-fs-20-token-replay"></a>Reproducción de tokens de AD FS 2.0

AD FS 2.0 proporciona una característica que se conoce como detección de reproducción de tokens, con la cual varias solicitudes de tokens que usan el mismo token se pueden detectar y descartar. Cuando esta característica está habilitada, la detección de reproducción de tokens protege la integridad de las solicitudes de autenticación en el perfil pasivo de la federación WS y el perfil de SAML WebSSO asegurándose de que el mismo token nunca se use más de una vez.

Esta característica necesita habilitarse en situaciones donde la seguridad es extremadamente preocupante como cuando se usan quioscos. Para obtener más información sobre la detección de reproducción de tokens, vea procedimientos recomendados para la planeación y la [http://go.microsoft.com/fwlink/p/?LinkId=309215](http://go.microsoft.com/fwlink/p/?linkid=309215)implementación seguros de AD FS 2,0 en.

</div>

<div>

## <a name="external-user-access"></a>Acceso de usuarios externos

En estos temas no se aborda la configuración de un proxy de AD FS o proxy inverso para admitir la autenticación de dos factores de Lync de redes externas.

</div>

</div>

<span> </span>

</div>

</div>

</div>

