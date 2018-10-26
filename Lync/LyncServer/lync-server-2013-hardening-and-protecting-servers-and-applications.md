---
title: 'Lync Server 2013: Reforzar y proteger los servidores y las aplicaciones'
TOCTitle: Reforzar y proteger los servidores y las aplicaciones de Lync Server 2013
ms:assetid: 9ca2b233-26f1-4d72-96e7-81a82c727806
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Dn518331(v=OCS.15)
ms:contentKeyID: 60505976
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Reforzar y proteger los servidores y las aplicaciones de Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Debe proteger el sistema operativo y las aplicaciones de acuerdo con los procedimientos recomendados correspondientes al componente en cuestión. En esta sección se explica cómo proteger los servidores de aplicaciones y el uso de la directiva de grupo para implementar bloqueos de seguridad.


> [!NOTE]
> También se pueden proteger las bases de datos que se usan en la implementación de Microsoft Lync Server 2013. Para obtener información detallada, consulte <A href="lync-server-2013-hardening-and-protecting-databases.md">Reforzar y proteger las bases de datos de Lync Server 2013</A>.



## Proteger los servidores de aplicaciones

En el caso de los servidores de aplicaciones, deben protegerse el sistema operativo y las aplicaciones. Así, un equipo con Windows Server 2008 dedicado a ejecutar Microsoft Internet Security and Acceleration (ISA) Server 2006 se debe proteger tanto desde el punto vista del sistema operativo como de las aplicaciones. Reducir el número de servicios que se ejecutan y ofrecen en un servidor debe ser un objetivo primordial.

## Proteger los servidores virtuales

Las instantáneas de servidores virtuales contienen copias de los discos de datos del servidor y volcados de datos de memoria. Ambos elementos pueden contener datos criptográficos confidenciales que pueden ser objeto de ataques. Conviene deshabilitar todas las instantáneas de servidor en los servidores de producción que se han implementado usando la virtualización o, al menos, administrarlas de forma muy controlada. Si quiere información detallada sobre cómo proteger servidores virtuales Hyper-V, consulte la guía de seguridad de Hyper-V en [http://go.microsoft.com/fwlink/p/?LinkId=214176](http://go.microsoft.com/fwlink/p/?linkid=214176).

## Directiva de grupo

En Windows Server 2008 y Windows Server 2008 R2, la directiva de grupo permite la administración de la configuración de escritorio basada en directorios. La directiva de grupo puede servir para implementar bloqueos de seguridad, que se logra definiendo la configuración de equipo y usuario de los siguientes elementos en un objeto de la directiva de grupo (GPO):

  - Directivas basadas en el Registro

  - Seguridad

  - Instalación de software

  - Scripts

  - Redirección de carpetas

  - Servicios de instalación remota

Para proporcionar una interfaz de usuario donde el administrador pueda definir estas configuraciones, se incluyen plantillas en los sistemas operativos, Service Pack y algunas aplicaciones, incluido Lync Server 2013.

El archivo Communicator.adm es una plantilla administrativa que viene con Lync Server 2013, se instala en el directorio *%windir%*\\inf\\ y ofrece una interfaz para la configuración de directiva de grupo. Cada opción de configuración de Communicator.adm se corresponde con una opción del Registro que afecta al comportamiento de la aplicación.

Se puede obtener acceso a esta configuración desde GPedit.dll, que está disponible en la consola Usuarios y equipos de Active Directory y en la Consola de administración de directivas de grupo (GPMC).

## Configuración de seguridad de la directiva de grupo

La directiva de grupo contiene una configuración de seguridad para un GPO en Configuración del equipo/Configuración de Windows/Configuración de seguridad si se obtiene acceso desde GPedit.dll. Puede importar plantillas de seguridad para definir la configuración de seguridad del GPO. En la guía de seguridad de Windows Server 2008, en [http://go.microsoft.com/fwlink/p/?LinkId=145186](http://go.microsoft.com/fwlink/p/?linkid=145186), y el kit de herramientas de administración del cumplimiento de seguridad de Windows Server 2008 R2, en [http://go.microsoft.com/fwlink/p/?LinkId=211882](http://go.microsoft.com/fwlink/p/?linkid=211882), encontrará algunas plantillas de ejemplo que puede modificar para adaptarlas a sus necesidades.

## Recomendaciones

  - Proteja todos los sistemas operativos y aplicaciones del servidor.

  - Proteja las instantáneas de servidor y mejore la seguridad de todos los servidores virtuales.

  - Use la directiva de grupo para implementar bloqueos de seguridad.

