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
ms.openlocfilehash: 4fc04381e315375fe0d5858c9a12ad577f6c8baf
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007829"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disaster-recovery-test-in-lync-server-2013"></a>Prueba de recuperación ante desastres en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2015-01-26_

Realice una recuperación del sistema para un servidor de grupo de servidores de Lync Server 2013 para probar el proceso de recuperación ante desastres documentado. Esta prueba simulará un error de hardware completo para un servidor y ayudará a garantizar que los recursos, los planes y los datos estén disponibles para la recuperación. Intente girar el foco de la prueba cada mes para que la organización Pruebe el error de un servidor diferente o de otro elemento del equipo cada vez.

Tenga en cuenta que la programación por la que las organizaciones realizan pruebas de recuperación ante desastres variarán. Es muy importante que las pruebas de recuperación ante desastres no se ignore o sin atender.

<div>


Exporte la topología, las directivas y las opciones de configuración de Lync Server 2013 a un archivo. Entre otras cosas, este archivo puede usarse para restaurar esta información en el almacén de administración central después de una actualización, un error de hardware o algún otro problema ha provocado la pérdida de datos.

Importe la topología, las directivas y las opciones de configuración de Lync Server 2013 al almacén de administración central o al equipo local, como se muestra en los siguientes comandos:

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

Para hacer una copia de seguridad de los datos de 2013 de producción de Lync Server:

  - Realice una copia de seguridad de las bases de datos RTC y LCSLog mediante el proceso de copia de seguridad estándar de SQL Server para volcar la base de datos en un dispositivo de volcado de archivos o cinta.

  - Use una aplicación de copia de seguridad de terceros para realizar una copia de seguridad de los datos en archivo o en cinta.

  - Use el cmdlet Export-CsUserData para crear una exportación XML de toda la base de datos RTC.

  - Use la copia de seguridad del sistema de archivos o de terceros para hacer copias de seguridad de contenido de reuniones y registros de cumplimiento.

  - Use la herramienta de línea de comandos Export-CsConfiguration para realizar una copia de seguridad de la configuración de Lync Server 2013.

El primer paso del procedimiento de conmutación por error incluye un movimiento forzoso de los usuarios del grupo de producción al grupo de recuperación ante desastres.

Esto será un movimiento forzado porque el grupo de producción no estará disponible para aceptar la reubicación del usuario.

El proceso de migración de usuarios de Lync Server 2013 es, en realidad, un cambio en un atributo del objeto de cuenta de usuario además de una actualización de registros en la base de datos SQL de RTC.

Estos datos se pueden restaurar a través de los dos procesos siguientes:

  - RTC Database puede restaurarse a partir del dispositivo de volcado de copia de seguridad original desde el SQL Server de producción mediante el proceso de restauración estándar de SQL Server o mediante una utilidad de copia de seguridad y restauración de terceros.

  - Los datos de contacto de los usuarios se pueden restaurar con la utilidad DBIMPEXP. exe mediante el archivo XML que se creó a partir de la exportación de SQL Server de producción.

Una vez que se han restaurado estos datos, los usuarios pueden conectarse de forma eficaz al grupo de recuperación ante desastres de Lync Server 2013 y funcionar como de costumbre.

Para permitir que los usuarios se conecten al grupo de recuperación ante desastres Lync Server 2013, será necesario cambiar un registro DNS.

Los clientes harán referencia al grupo de producción Lync Server 2013 mediante la configuración automática y los registros SRV de DNS de:

  - SRV: \_SIP. \_TLS. \</CNAME\> de dominio: SIP. \<dominio\>

  - CNAME: SIP. \<dominio\> /CVC-Pool-1. \<dominio\>

Para facilitar la conmutación por error, este registro CNAME debe actualizarse para que haga referencia al FQDN DROCSPool:

  - CNAME: SIP. \<dominio\> /DROCSPool. \<dominio\>

  - SIP. \<dominio\>

  - AV.\<dominio\>

  - WebConf. \<dominio\>

  - OCSServices. \<dominio\>

<div>


> [!IMPORTANT]  
> Para obtener información detallada acerca de los procedimientos de administración y administración, consulte <A href="lync-server-2013-backing-up-and-restoring-lync-server.md">copia de seguridad y restauración de Lync Server 2013</A>.



</div>

</div>

<div>

## <a name="see-also"></a>Vea también


[Planeación de alta disponibilidad y recuperación ante desastres en Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
[Cmdlets de copia de seguridad y alta disponibilidad en Lync Server 2013](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps)  


[Import-CsConfiguration](https://docs.microsoft.com/powershell/module/skype/Import-CsConfiguration)  
[Copia de seguridad y restauración de Lync Server 2013](lync-server-2013-backing-up-and-restoring-lync-server.md)  
[Administración del servicio de copia de seguridad, alta disponibilidad y recuperación ante desastres de Lync Server 2013](lync-server-2013-managing-lync-server-disaster-recovery-high-availability-and-backup-service.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

