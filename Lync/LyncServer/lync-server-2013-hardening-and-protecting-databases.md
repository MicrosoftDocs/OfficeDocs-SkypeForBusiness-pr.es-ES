---
title: 'Lync Server 2013: refuerzo y protección de bases de datos'
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
ms.openlocfilehash: 0254c77bb276add6f55ccff623c1fc2bec590102
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536917"
---
# <a name="hardening-and-protecting-the-databases-of-lync-server-2013"></a>Refuerzo y protección de las bases de datos de Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-12-05_

Microsoft Lync Server 2013 también depende de las bases de datos de SQL Server para almacenar información de usuario, estado de conferencia, datos de archivado y registros de detalles de llamadas (CDR). Puede maximizar la disponibilidad de los datos de Lync Server 2013 en las bases de datos back-end de Lync Server, mediante la partición de los datos de la aplicación de forma que se mejore la tolerancia a errores y se simplifique la solución de problemas. Para lograr estos objetivos, divida en particiones los datos de la aplicación mediante las siguientes acciones:

  - **Uso de las prácticas**     recomendadas para la partición del servidor Separe los archivos del sistema operativo, la aplicación y el programa de los archivos de datos.

  - **Almacenamiento de archivos de registro de transacciones y archivos**     de base de datos Almacene estos archivos por separado para aumentar la tolerancia a errores y optimizar la recuperación, y almacénelos en un disco o volumen cifrado.

  - **Uso de clústeres**     de servidor Agrupar los servidores back-end para optimizar la disponibilidad del sistema de Lync Server 2013.

  - **Asegurarse de que todas las copias de seguridad de datos se cifran y se administran correctamente**     Los medios de copia de seguridad perdidos, descartados o extraviados pueden suponer una amenaza importante para la seguridad de datos para implementaciones de Lync Server 2013

En cualquier servidor de Lync Server 2013 excepto en el servidor Standard Edition, la instancia de SQL Server Express (instancia RTCLOCAL) no es accesible de forma remota y no se crean excepciones del firewall local, excepto para SQL Server Express en un servidor Standard Edition. En un servidor Standard Edition, tanto la base de datos back-end como el Almacén de administración central (CMS) están configurados para poder acceder a ellos de forma remota. Para proteger las bases de datos de SQL Server, puede hacer lo siguiente:

  - Personalizar el firewall de SQL Server Express en los servidores Standard Edition, limitando el ámbito de servidores que pueden acceder de forma remota a la base de datos. De manera predeterminada, cualquier dirección IP puede acceder a la base de datos de forma remota.

  - Usar el Administrador de configuración de SQL Server para especificar los protocolos, direcciones IP y puertos para el acceso remoto a SQL Server:
    
      - Lync Server 2013 usa el protocolo TCP/IP. Admite la versión 4 de IP (IPv4), pero no admite la versión 6 (IPv6).
        
        <div>
        

        > [!NOTE]  
        > Lync Server 2013 puede funcionar en una red con una pila IP dual habilitada.

        
        </div>
    
      - Lync Server 2013 admite varias direcciones IP (tarjetas de dirección de red multitarjeta). Puede especificar que SQL Server escuche solo direcciones IP específicas (direcciones individuales o por subred) y use solo protocolos específicos.
    
      - Lync Server 2013 admite puertos de SQL Server estáticos y dinámicos.

  - Ejecute SQL Server en un puerto estático (que no sea predeterminado) y no ejecute SQL Server Browser (para que no pueda informar del puerto de escucha al cliente). Esto requiere una configuración personalizada en cada cliente de SQL Server, incluidos los servidores front-end, el servidor de supervisión, el servidor de archivado y las consolas administrativas (ejecutando el shell de administración de Lync Server, el panel de control de Lync Server o el generador de topologías) y todos los demás servidores que ejecutan las bases de datos de Lync Server.

<div>


> [!NOTE]  
> El acceso a las bases de datos debe limitarse a los administradores de bases de datos de confianza. Un administrador de bases de datos malintencionado puede insertar o modificar datos en las bases de datos para adquirir privilegios en los servidores de Lync Server 2013 u obtener información confidencial de los servicios, incluso si el administrador de la base de datos no tiene acceso directo ni control de los servidores de Lync Server 2013.



</div>

Para obtener más información sobre las configuraciones personalizadas y consolidar las bases de datos de SQL Server, vea el artículo del blog NextHop, "Using Lync Server 2010 con una configuración de red de SQL Server personalizada", en [https://go.microsoft.com/fwlink/p/?LinkId=214008](https://go.microsoft.com/fwlink/p/?linkid=214008) .

<div>


> [!NOTE]  
> También puede reforzar los sistemas operativos y los servidores de aplicaciones, y puede usar la Directiva de grupo para implementar bloqueos de seguridad en su implementación de Lync Server. Para obtener más información, consulte <A href="lync-server-2013-hardening-and-protecting-servers-and-applications.md">refuerzo y protección de servidores y aplicaciones para Lync Server 2013</A>.



</div>

</div>

<span> </span>

</div>

</div>

</div>

