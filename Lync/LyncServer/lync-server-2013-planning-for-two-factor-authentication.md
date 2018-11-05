---
title: Planeación de la autenticación en dos fases
TOCTitle: Planeación de la autenticación en dos fases
ms:assetid: 16f08710-8961-4659-acbf-ebb95a198fb4
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Dn308562(v=OCS.15)
ms:contentKeyID: 56271269
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Planeación de la autenticación en dos fases

 

_**Última modificación del tema:** 2016-12-08_

A continuación se muestra una lista de consideraciones de implementación al configurar un entorno de Microsoft Lync Server 2013 para admitir autenticación en dos fases.

## Compatibilidad con clientes

Las actualizaciones acumulativas de Lync 2013 para Lync Server 2013: cliente de escritorio, julio de 2013, son el único cliente de Lync que actualmente admite la autenticación en dos fases.

## Requisitos de topología

Se recomienda encarecidamente a los clientes que implementen la autenticación en dos fases mediante el uso de actualizaciones acumulativas dedicadas de Lync Server 2013 para Lync Server 2013: grupos de usuarios, director y perimetrales, julio de 2013. Para habilitar la autenticación pasiva para los usuarios de Lync, se deben deshabilitar los demás métodos de autenticación para otros roles y servicios, incluidos los siguientes:


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
<td><p>Servidor perimetral</p></td>
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


A menos que estos tipos de autenticación se deshabiliten en el nivel de servicio, ninguna de las demás versiones del cliente de Lync podrá iniciar sesión correctamente una vez que la autenticación en dos fases esté habilitada dentro de la implementación.

## Detección de servicios de Lync

Los registros DNS utilizados por clientes internos o externos para detectar servicios de Lync deben configurarse para resolver en un servidor de Lync que no esté habilitado para la autenticación en dos fases. Con esta configuración, los usuarios de Lync Pools que no estén habilitados para la autenticación en dos fases no tendrán que especificar un PIN para autenticarse, mientras que los usuarios de Lync Pools que estén habilitados para la autenticación en dos fases sí tendrán que hacerlo.

## Autenticación de Exchange

Los clientes que han implementado la autenticación en dos fases para Microsoft Exchange pueden observar que algunas características en el cliente de Lync no están disponibles. Esto sucede actualmente por diseño, ya que el cliente de Lync no admite la autenticación en dos fases para las características que dependen de la integración de Exchange.

## Contactos de Lync

Los usuarios de Lync que están configurados para aprovechar la característica del almacén de contactos unificado observarán que sus contactos ya no están disponibles tras iniciar sesión con la autenticación en dos fases.

Debe usar el cmdlet **Invoke-CsUcsRollback** para quitar los contactos de usuarios existentes del almacén de contactos unificado y almacenarlos en Lync Server 2013 antes de habilitar la autenticación en dos fases.

## Búsqueda de aptitudes

Los usuarios que han configurado la característica de búsqueda de aptitudes en su entorno de Lync observarán que esta característica no funciona cuando Lync está habilitado para la autenticación en dos fases. Esto sucede por diseño, ya que Microsoft SharePoint no admite actualmente la autenticación en dos fases.

## Credenciales de Lync

Hay varias consideraciones de implementación que implican credenciales guardadas de Lync que pueden afectar a los usuarios configurados para usar la autenticación en dos fases.

## Eliminación de credenciales guardadas

Los usuarios deben usar la opción **Eliminar info. de inicio de sesión** en el cliente de Lync y eliminar su carpeta de perfil SIP de %localappdata%\\Microsoft\\Office\\15.0\\Lync antes de intentar iniciar sesión por primera vez con la autenticación en dos fases.

## DisableNTCredentials

Con el método de autenticación NTLM o Kerberos, las credenciales de Windows de los usuarios se utilizan automáticamente para la autenticación. En una implementación típica de Lync Server 2013 donde Kerberos o NTLM se habilitan para la autenticación, los usuarios no tienen que especificar sus credenciales cada vez que inician sesión.

Si se les solicitan de manera no intencionada las credenciales a los usuarios antes de que se les pida especificar su PIN, la clave del Registro **DisableNTCredentials** puede configurarse de manera no intencionada en los equipos cliente, posiblemente a través de la directiva de grupo.

Para evitar otras solicitudes de credenciales, cree la siguiente entrada de Registro en la estación de trabajo local o use la plantilla administrativa de Lync para aplicar a todos los usuarios de un grupo determinado mediante la directiva de grupo:

HKEY\_LOCAL\_MACHINE\\Software\\Policies\\Microsoft\\Office\\15.0\\Lync

REG\_DWORD: DisableNTCredentials

Valor: 0x0

## SavePassword

Cuando un usuario inicia sesión en Lync por primera vez, se le pide que guarde su contraseña. Si se selecciona, esta opción permite que el certificado del cliente del usuario se almacene en el almacén de certificados personales y que las credenciales de Windows del usuario se almacenen en el Administrador de credenciales del equipo local.

La configuración del Registro **SavePassword** debe deshabilitarse cuando Lync está configurado para admitir la autenticación en dos fases. Para impedir que los usuarios guarden sus contraseñas, cambie la siguiente entrada de Registro en la estación de trabajo local o use la plantilla administrativa de Lync para aplicar a todos los usuarios de un grupo determinado mediante la directiva de grupo:

HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync

REG\_DWORD: SavePassword

Valor: 0x0

## Reproducción de tokens de AD FS 2.0

AD FS 2.0 proporciona una característica que se conoce como detección de reproducción de tokens, mediante la cual varias solicitudes de tokens que usan el mismo token se pueden detectar y descartar. Cuando esta característica está habilitada, la detección de reproducción de tokens protege la integridad de las solicitudes de autenticación en el perfil pasivo de la federación WS y el perfil de SAML WebSSO asegurándose de que el mismo token nunca se use más de una vez.

Esta característica debe habilitarse en situaciones donde la seguridad es extremadamente preocupante como cuando se usan quioscos. Para obtener más información acerca de la detección de reproducción de tokens, consulte los Procedimientos recomendados para la planeación e implementación seguras de AD FS 2.0 en [http://go.microsoft.com/fwlink/p/?LinkId=309215](http://go.microsoft.com/fwlink/p/?linkid=309215).

## Acceso de usuarios externos

Estos temas no abordan la configuración de un proxy de ADFS o proxy inverso para admitir la autenticación en dos fases de Lync desde redes externas.

