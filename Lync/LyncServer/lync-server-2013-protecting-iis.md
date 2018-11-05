---
title: 'Lync Server 2013: Proteger IIS'
TOCTitle: Proteger IIS en Lync Server 2013
ms:assetid: a67171a6-6703-4e09-abb3-35d335bb674e
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Dn518332(v=OCS.15)
ms:contentKeyID: 60505977
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Proteger IIS en Lync Server 2013

 

_**Última modificación del tema:** 2013-12-05_

En Microsoft Office Communications Server 2007 y Microsoft Office Communications Server 2007 R2, Internet Information Services (IIS) se ejecutaba con una cuenta de usuario estándar. Esto podía provocar problemas: si la contraseña expiraba, se podían perder los servicios web, un problema que a menudo era difícil de diagnosticar. Para evitar el problema de expiración de una contraseña, Microsoft Lync Server 2013 permite crear una cuenta de equipo (para un equipo que no existe realmente) capaz de funcionar como entidad de seguridad de autenticación para todos los equipos de un sitio que ejecuten IIS. Como estas cuentas usan el protocolo de autenticación Kerberos, se hace referencia a las cuentas como cuentas Kerberos, y el nuevo proceso de autenticación se conoce como autenticación web Kerberos. Esto le permite administrar todos sus servidores IIS usando una sola cuenta.

Para ejecutar los servidores con esta entidad de seguridad de autenticación, antes debe crear una cuenta de equipo usando el cmdlet New-CsKerberosAccount; luego, esta cuenta se asigna a uno o más sitios. Una vez realizada la asignación, se habilita la asociación entre la cuenta y el sitio de Lync Server 2013 ejecutando el cmdlet Enable-CsTopology. Esta acción crea, entre otras cosas, el nombre de entidad de seguridad de servicio (SPN) necesario en los servicios de dominio de Active Directory (AD DS). Los SPN ofrecen un modo para que las aplicaciones cliente ubiquen un servicio concreto. Para más información, vea [New-CsKerberosAccount](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsKerberosAccount) en la documentación de operaciones.

## Recomendaciones

Para contribuir a mejorar la seguridad de IIS, le recomendamos que implemente una cuenta Kerberos para IIS. Si no implementa una cuenta Kerberos, IIS se ejecutará con una cuenta de usuario estándar.

