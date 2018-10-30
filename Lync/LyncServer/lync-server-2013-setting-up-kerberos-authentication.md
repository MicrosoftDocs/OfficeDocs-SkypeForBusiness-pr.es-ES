---
title: 'Lync Server 2013: Configurar la autenticación Kerberos'
TOCTitle: Configurar la autenticación Kerberos
ms:assetid: dd8009ef-6265-4cc0-b2c7-e474cd1f4b09
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398976(v=OCS.15)
ms:contentKeyID: 48276887
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configurar la autenticación Kerberos en Lync Server 2013

 

_**Última modificación del tema:** 2013-02-21_

Lync Server 2013 admite la autenticación NTLM y Kerberos para Servicios web. Office Communications Server 2007 y Office Communications Server 2007 R2 usaban los RTCComponentService y RTCService predeterminados como cuentas de usuario para ejecutar los grupos de aplicaciones de Servicios web, lo que permitía asignar un nombre de entidad de seguridad de servicio (SPN) a las cuentas de usuario para que actuara como entidad de seguridad de autenticación. Lync Server usa NetworkService para ejecutar Servicios web y NetworkService no puede tener asignado ninguna SPN.

Para solucionar el problema que supone no tener objetos de Active Directory que contengan las SPN, Panel de control de Lync Server puede usar objetos de cuenta de equipo para este propósito. Los objetos de cuenta de equipo pueden contener las SPN y no están sujetos a la expiración de las contraseñas, lo que suponía un problema si se usaban cuentas de usuario en versiones anteriores.

Para configurar los objetos de equipo con el fin de proporcionar la autenticación Kerberos, use los cmdlets de Windows PowerShell.

## En esta sección

  - [Requisitos previos para habilitar la autenticación Kerberos en Lync Server 2013](lync-server-2013-prerequisites-for-enabling-kerberos-authentication.md)

  - [Crear una cuenta de autenticación Kerberos en Lync Server 2013](lync-server-2013-create-a-kerberos-authentication-account.md)

  - [Asignar una cuenta de autenticación Kerberos a un sitio en Lync Server 2013](lync-server-2013-assign-a-kerberos-authentication-account-to-a-site.md)

  - [Configurar las contraseñas de cuenta de autenticación Kerberos en Lync Server 2013](lync-server-2013-setting-up-kerberos-authentication-account-passwords.md)

  - [Agregar autenticación Kerberos a otros sitios en Lync Server 2013](lync-server-2013-add-kerberos-authentication-to-other-sites.md)

  - [Quitar la autenticación Kerberos de un sitio en Lync Server 2013](lync-server-2013-remove-kerberos-authentication-from-a-site.md)

  - [Comprobar y notificar el estado y asignación de la autenticación Kerberos en Lync Server 2013](lync-server-2013-testing-and-reporting-the-status-and-assignment-of-kerberos-authentication.md)

