---
title: 'Lync Server 2013: prueba de recuperación ante desastres'
TOCTitle: Prueba de recuperación ante desastres
ms:assetid: 04f5e747-d837-4350-9fc0-8605dbf025a7
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Dn747887(v=OCS.15)
ms:contentKeyID: 62293599
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Prueba de recuperación ante desastres en Lync Server 2013

 

_**Última modificación del tema:** 2015-01-26_

Realice una recuperación del sistema para un servidor del grupo de Lync Server 2013 para poner a prueba su proceso documentado de recuperación ante desastres. Esta prueba simulará un error completo de hardware en un servidor y ayudará a garantizar que los recursos, planes y datos estén disponibles para su recuperación. Trate de variar cada mes el objeto de esta simulación, de modo que su organización vaya poniendo a prueba distintos servidores u otros elementos.

Tenga en cuenta que el programa mediante el cual las organizaciones realizan pruebas de recuperación ante desastres puede variar. Es muy importante no ignorar o descuidar estas pruebas.


Exporte a un archivo su topología, directivas y configuración de Lync Server 2013. Entre otras cosas, este archivo podrá usarse para restaurar esta información en el Almacén de administración central después de una actualización, un error de hardware o cualquier otro problema que resulte en la pérdida de datos.

Importe la topología, directivas y configuración de Lync Server 2013 en el Almacén de administración central o el equipo local, como se muestra en los siguientes comandos:

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

Para realizar copias de seguridad de los datos de producción de Lync Server 2013:

  - Realice una copia de seguridad de las bases de datos RTC y LCSLog empleando el proceso de copia de seguridad estándar de SQL Server para volcar una base de datos a un archivo o dispositivo de volcado de cinta.

  - Use una aplicación de terceros para realizar en un archivo o cinta una copia de seguridad de los datos.

  - Use el cmdlet Export-CsUserData para crear una exportación XML de toda la base de datos RTC.

  - Use la copia de seguridad del sistema de archivos o una aplicación de terceros para realizar una copia de seguridad del contenido de las reuniones y los registros de cumplimiento.

  - Use la herramienta de línea de comandos Export-CsConfiguration para realizar una copia de seguridad de la configuración de Lync Server 2013.

El primer paso en el procedimiento de conmutación por error incluye el traslado forzoso de los usuarios desde el grupo de producción al grupo de recuperación ante desastres.

Se trata de un traslado forzoso porque el grupo de producción no estará disponible para aceptar la reubicación de los usuarios.

El proceso de traslado de usuarios de Lync Server 2013 consiste en un cambio en un atributo del objeto cuenta de usuario, sumado a la actualización de un registro en la base de datos SQL RTC.

Estos datos pueden restaurarse mediante los dos siguientes procesos:

  - La base de datos RTC puede restaurarse desde el SQL Server de producción en el dispositivo original de volcado de copia de seguridad, usando el proceso estándar de restauración de SQL Server, o bien usando una utilidad de restauración/copia de seguridad de terceros.

  - Los datos de contacto de usuarios pueden restaurarse con la utilidad DBIMPEXP.exe, utilizando el archivo XML creado por la exportación del SQL Server de producción.

Una vez restaurados estos datos, los usuarios ya pueden conectarse al grupo de recuperación ante desastres de Lync Server 2013 y operar del modo normal.

Para habilitar la conexión de usuarios al grupo de recuperación ante desastres de Lync Server 2013 es preciso un cambio de registro DNS.

Los clientes harán referencia al grupo de producción de Lync Server 2013 mediante los registros de autoconfiguración y de servidor DNS de:

  - SRV: \_sip.\_tls.\<domain\> /CNAME: SIP.\<domain\>

  - CNAME: SIP.\<domain\> /cvc-pool-1.\<domain\>

Para facilitar la conmutación por error, este registro CNAME debe actualizarse para que haga referencia al FQDN DROCSPool:

  - CNAME: SIP.\<domain\> /DROCSPool.\<domain\>

  - Sip.\<domain\>

  - AV.\<domain\>

  - webconf.\<domain\>

  - OCSServices.\<domain\>

> [!IMPORTANT]  
> Si quiere consultar procedimientos detallados de administración y gestión, vea <a href="lync-server-2013-backing-up-and-restoring-lync-server.md">Copia de seguridad y restauración de Lync Server 2013</a>.



## Vea también

#### Conceptos

[Planeación de alta disponibilidad y recuperación ante desastres en Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
[Cmdlets de copia de seguridad y de alta disponibilidad](https://docs.microsoft.com/en-us/powershell/module/skype/?view=skype-ps)  

#### Otros recursos

[Import-CsConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Import-CsConfiguration)  
[Copia de seguridad y restauración de Lync Server 2013](lync-server-2013-backing-up-and-restoring-lync-server.md)  
[Administrar la recuperación ante desastres, la alta disponibilidad y el servicio de copia de seguridad en Lync Server 2013](lync-server-2013-managing-lync-server-disaster-recovery-high-availability-and-backup-service.md)

