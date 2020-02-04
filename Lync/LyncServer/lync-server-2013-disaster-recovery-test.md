---
title: 'Lync Server 2013: prueba de recuperación ante desastres'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disaster recovery test
ms:assetid: 04f5e747-d837-4350-9fc0-8605dbf025a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn747887(v=OCS.15)
ms:contentKeyID: 63969571
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7c6c3b7c3b5d78324fe9c674650dd94338baea4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739200"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disaster-recovery-test-in-lync-server-2013"></a>Prueba de recuperación ante desastres en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2015-01-26_

Realice una recuperación del sistema de un servidor de grupo 2013 de Lync Server para probar el proceso de recuperación ante desastres documentado. Esta prueba simulará un error completo de hardware en un servidor y ayudará a garantizar que los recursos, planes y datos estén disponibles para su recuperación. Trate de variar cada mes el objeto de esta simulación, de modo que su organización vaya poniendo a prueba distintos servidores u otros elementos.

Tenga en cuenta que el programa mediante el cual las organizaciones realizan pruebas de recuperación ante desastres puede variar. Es muy importante no ignorar o descuidar estas pruebas.

<div>


Exporte su topología, directivas y configuración de configuración de Lync Server 2013 a un archivo. Entre otras cosas, este archivo podrá usarse para restaurar esta información en el Almacén de administración central después de una actualización, un error de hardware o cualquier otro problema que resulte en la pérdida de datos.

Importe la topología, las directivas y las opciones de configuración de Lync Server 2013 en el almacén de administración central o en el equipo local, tal y como se muestra en los siguientes comandos:

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

Para hacer una copia de seguridad de los datos de producción de Lync Server 2013:

  - Haga una copia de seguridad de las bases de datos RTC y LCSLog con el proceso de copia de seguridad estándar de SQL Server para volcar la base de datos en un dispositivo de volcado de archivo o cinta.

  - Use una aplicación de terceros para realizar en un archivo o cinta una copia de seguridad de los datos.

  - Use el cmdlet Export-CsUserData para crear una exportación XML de toda la base de datos RTC.

  - Use la copia de seguridad del sistema de archivos o una aplicación de terceros para realizar una copia de seguridad del contenido de las reuniones y los registros de cumplimiento.

  - Use la herramienta de línea de comandos Export-CsConfiguration para realizar copias de seguridad de la configuración de Lync Server 2013.

El primer paso en el procedimiento de conmutación por error incluye el traslado forzoso de los usuarios desde el grupo de producción al grupo de recuperación ante desastres.

Se trata de un traslado forzoso porque el grupo de producción no estará disponible para aceptar la reubicación de los usuarios.

El proceso de desplazar usuarios de Lync Server 2013 es realmente un cambio en un atributo del objeto de cuenta de usuario, además de una actualización de registro en la base de datos de SQL de RTC.

Estos datos pueden restaurarse mediante los dos siguientes procesos:

  - La base de datos RTC puede restaurarse desde el dispositivo de volcado de copia de seguridad original desde el servidor SQL de producción mediante el proceso de restauración estándar de SQL Server o mediante una herramienta de copia de seguridad y restauración de terceros.

  - Los datos de contacto de usuarios pueden restaurarse con la utilidad DBIMPEXP.exe, utilizando el archivo XML creado por la exportación del SQL Server de producción.

Una vez que se hayan restaurado estos datos, los usuarios podrán conectarse eficazmente al grupo de recuperación ante desastres de Lync Server 2013 y funcionar como de costumbre.

Para permitir que los usuarios se conecten al grupo de recuperación ante desastres de Lync Server 2013, será necesario un cambio de registro DNS.

Los clientes hará referencia al grupo de producción de Lync Server 2013 con la configuración automática y los registros SRV de DNS de:

  - SRV: \_SIP. \_TLS. \</CNAME\> de dominio: SIP. \<dominio\>

  - CNAME: SIP. \<domain\> /CVC-Pool-1. \<dominio\>

Para facilitar la conmutación por error, este registro CNAME debe actualizarse para que haga referencia al FQDN DROCSPool:

  - CNAME: SIP. \<domain\> /DROCSPool. \<dominio\>

  - SIP. \<dominio\>

  - AV.\<Domain\>

  - WebConf. \<dominio\>

  - OCSServices. \<dominio\>

<div>


> [!IMPORTANT]  
> Para obtener información detallada sobre la administración y los procedimientos de administración, consulte <A href="lync-server-2013-backing-up-and-restoring-lync-server.md">copia de seguridad y restauración de Lync Server 2013</A>.



</div>

</div>

<div>

## <a name="see-also"></a>Vea también


[Planeación de alta disponibilidad y recuperación ante desastres en Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
[Cmdlets de copia de seguridad y alta disponibilidad en Lync Server 2013](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps)  


[Importar-CsConfiguration](https://docs.microsoft.com/powershell/module/skype/Import-CsConfiguration)  
[Copia de seguridad y restauración de Lync Server 2013](lync-server-2013-backing-up-and-restoring-lync-server.md)  
[Administrar la recuperación ante desastres, la alta disponibilidad y el servicio de copia de seguridad en Lync Server 2013](lync-server-2013-managing-lync-server-disaster-recovery-high-availability-and-backup-service.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

