---
title: 'Lync Server 2013: Reforzar y proteger las bases de datos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardening and protecting the databases of Lync Server 2013
ms:assetid: 6953e721-3511-4235-b848-51bab093dc89
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn518330(v=OCS.15)
ms:contentKeyID: 62625490
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77e02a5fd0f90367f23e7b0fb314f037f7b31e45
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739590"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hardening-and-protecting-the-databases-of-lync-server-2013"></a>Reforzar y proteger las bases de datos de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-12-05_

Microsoft Lync Server 2013 también depende de las bases de datos de SQL Server para almacenar información de usuario, estado de la Conferencia, datos de archivado y registros de detalles de llamadas (CDRs). Puede maximizar la disponibilidad de datos de Lync Server 2013 en bases de datos back-end de Lync Server, al particionar los datos de la aplicación de forma que mejore la tolerancia a errores y simplifique la solución de problemas. Para lograr estos objetivos, divida los datos de la aplicación por:

  - **Uso**   de las prácticas recomendadas para la partición de servidores separe los archivos de sistema operativo, aplicaciones y programas de los archivos de datos.

  - **Almacenar archivos de registro de transacciones y archivos**   de base de datos almacene estos archivos por separado para aumentar la tolerancia a errores y optimizar la recuperación, y almacenarlos en un disco o volumen cifrado.

  - **Usar clústeres de servidor**   agrupar los servidores back-end para optimizar la disponibilidad del sistema de Lync Server 2013.

  - **Asegurarse de que todas las copias de seguridad de los datos se cifren y se administren**   correctamente los medios de copia de seguridad perdidos, descartados o extraviados pueden suponer una amenaza importante para la seguridad de los datos para implementaciones de Lync Server 2013

En cualquier servidor de Lync Server 2013 excepto el servidor Standard Edition, no se puede acceder a la instancia de SQL Server Express (instancia RTCLOCAL) de forma remota y no se crean excepciones de Firewall local, excepto SQL Server Express en un servidor Standard Edition. En un servidor Standard Edition, tanto la base de datos back-end como el almacén de administración central (CMS) están configurados para que sean accesibles de forma remota. Para reforzar las bases de datos de SQL Server, puede hacer lo siguiente:

  - Personalizar el Firewall de SQL Server Express en servidores Standard Edition, lo que limita el ámbito de los servidores que pueden tener acceso a la base de datos de forma remota. De forma predeterminada, cualquier dirección IP puede tener acceso remoto a la base de datos.

  - Use el administrador de configuración de SQL Server para especificar los protocolos, las direcciones IP y los puertos para el acceso remoto de SQL Server:
    
      - Lync Server 2013 usa el protocolo TCP/IP. Es compatible con IP versión 4 (IPv4), pero no con IP versión 6 (IPv6).
        
        <div>
        

        > [!NOTE]  
        > Lync Server 2013 puede funcionar en una red con dos pilas IP habilitadas.

        
        </div>
    
      - Lync Server 2013 admite varias direcciones IP (tarjetas de dirección de red multitarjeta). Puede especificar que SQL Server solo escuche direcciones IP específicas (dirección individual o por subred) y use únicamente protocolos específicos.
    
      - Lync Server 2013 admite puertos de SQL Server estáticos y dinámicos.

  - Ejecute SQL Server en un puerto estático (no predeterminado) y no ejecute SQL Server Browser (por lo tanto, no puede informar del puerto de escucha al cliente). Esto requiere una configuración personalizada en cada cliente de SQL Server, incluidos los servidores front-end, el servidor de supervisión, el servidor de archivado y las consolas administrativas (ejecutando el shell de administración de Lync Server, el panel de control de Lync Server o el generador de topología) y todos los demás servidores que ejecutan bases de datos de Lync Server).

<div>


> [!NOTE]  
> El acceso a bases de datos debe limitarse a los administradores de bases de datos de confianza. Un administrador de bases de datos malintencionado puede insertar o modificar datos en las bases de datos para adquirir privilegios sobre los servidores de Lync Server 2013 o para obtener información confidencial de los servicios, incluso si el administrador de la base de datos no se le ha concedido acceso directo o control de los servidores de Lync Server 2013.



</div>

Para obtener información detallada sobre las configuraciones personalizadas y la consolidación de las bases de datos de SQL Server, consulte el artículo del blog de NextHop, "usar Lync Server 2010 con una [http://go.microsoft.com/fwlink/p/?LinkId=214008](http://go.microsoft.com/fwlink/p/?linkid=214008)configuración de red de SQL Server personalizada", en.

<div>


> [!NOTE]  
> También puede reforzar los sistemas operativos y los servidores de aplicaciones, y puede usar la Directiva de grupo para implementar los bloqueos de seguridad en su implementación de Lync Server. Para obtener más información, consulte <A href="lync-server-2013-hardening-and-protecting-servers-and-applications.md">reforzar y proteger servidores y aplicaciones para Lync Server 2013</A>.



</div>

</div>

<span> </span>

</div>

</div>

</div>

