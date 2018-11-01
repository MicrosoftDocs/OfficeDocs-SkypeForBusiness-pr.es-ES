---
title: 'Lync Server 2013: Información general del entorno híbrido de Lync Server'
TOCTitle: Información general del entorno híbrido de Lync Server 2013
ms:assetid: 0d16ec3a-28f0-4483-96e7-8e68f30398fa
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204669(v=OCS.15)
ms:contentKeyID: 48274417
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Información general del entorno híbrido de Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

El entorno híbrido de Lync Server 2013 hace referencia a una implementación en la cual algunos usuarios se hospedan en Lync Server 2013 local y otros en Lync Online, pero todos comparten el mismo dominio, por ejemplo, user@contoso.com.

## Acerca de esta guía

En esta guía se describen las tareas necesarias para configurar su entorno de Lync Server 2013 para la interoperabilidad con Lync Online y luego mover los usuarios desde la implementación local para usar Lync Online.

## Requisitos previos

Es necesario tener instaladas las siguientes aplicaciones y utilidades para completar las tareas de configuración de una implementación híbrida. Los programas de instalación para estos archivos se incluyen en los medios de instalación proporcionados para la implementación, así como en los vínculos de la lista siguiente.

  - [Servicios de federación de Active Directory (AD FS) 2.0](http://go.microsoft.com/fwlink/p/?linkid=257305)

  - [Herramienta de sincronización de directorios de Microsoft 9.1](http://go.microsoft.com/fwlink/p/?linkid=257307)

  - [Instalar Windows PowerShell para un inicio de sesión único con AD FS](http://go.microsoft.com/fwlink/p/?linkid=398710)

  - Microsoft Online Services - Ayudante para el inicio de sesión (msoidcli-7.0.msi) se incluye con la configuración de escritorio de Office 365, que se puede obtener desde la página de descargas vinculada en el portal de administración de Office 365.

## Credenciales de administrador

Cuando se le solicite que proporcione sus credenciales de administrador, use el nombre de usuario y la contraseña de la cuenta de administrador para el inquilino de Office 365. También usará estas credenciales para configurar Servicios de federación de Active Directory (AD FS) 2.0, la sincronización de directorios, el inicio de sesión único y la federación, y para mover usuarios a Lync Online.

## Conexión con Lync Online PowerShell

Ahora, los administradores pueden usar Windows PowerShell para administrar Lync Online y sus cuentas de usuario de Lync Online. Para ello, primero debe descargar e instalar el módulo del conector de Lync Online del Centro de descarga de Microsoft (http://go.microsoft.com/fwlink/?LinkId=294688). Para obtener más información sobre cómo descargar, instalar y usar el módulo del conector de Lync Online, así como información detallada sobre el uso de Windows PowerShell para administrar Lync Online, vea [Administrar Lync Online con Windows PowerShell](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).

