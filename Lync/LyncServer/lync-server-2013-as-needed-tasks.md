---
title: 'Lync Server 2013: tareas necesarias'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: As-needed tasks
ms:assetid: b66bc6fe-f138-4cf4-ba7f-aee9a3e0497e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn722431(v=OCS.15)
ms:contentKeyID: 63969643
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 98b4323374c9801ec07930941a0daa3635b04e43
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529547"
---
# <a name="as-needed-tasks-in-lync-server-2013"></a>Tareas necesarias en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-08-18_

Realice las siguientes tareas según sea necesario. Con frecuencia también se incluyen en los procedimientos estándar:

  - **Auditoría de seguridad completa   ** Puede realizar esta auditoría con regularidad, en respuesta a una actualización o rediseño del sistema de mensajería, o en respuesta a una infracción de seguridad intentada (o exitosa). El procedimiento puede implicar análisis de puertos en servidores y firewalls, auditorías de revisiones de seguridad y pruebas de penetración de terceros.

  - **Reemplazar certificados a punto de expirar**     La comprobación de los certificados de Lync Server es una tarea semanal normal y, como parte del procedimiento, un administrador debe tener un registro de todas las fechas de expiración de los certificados. Este registro permite a un administrador crear una notificación cuando un certificado concreto está a punto de caducar y se reemplaza según sea necesario.

  - **Actualización de líneas de base**     de rendimiento Actualice las líneas de base de rendimiento después de un cambio en la configuración o la actualización. Su organización puede usar líneas de base para medir los cambios de rendimiento y detectar problemas que afectan al rendimiento del sistema.

  - **Administración del grupo**     de servidores Enterprise Durante la implementación de los servidores individuales, se realizó la configuración inicial de los grupos de servidores Enterprise, los servidores Standard Edition y cualquier otro servidor del entorno de la organización. La administración posterior a la implementación de servidores y grupos de servidores Standard Edition y grupos de servidores Enterprise incluye las siguientes tareas:
    
      - Administración de servidores front-end
    
      - Administración de conferencias web
    
      - Administración de conferencias
    
      - Cambio de las credenciales de la cuenta de servicio
    
      - Administración de bases de datos
    
      - Inicio y detención de servicios y desactivación de roles de servidor
    
      - Quitar servidores y roles de servidor, quitar grupos de servidores y retirar servidores y grupos de servidores

  - **Administración del uso**     Puede configurar Lync Server 2013 para proporcionar las características y funciones más adecuadas para su organización. Esto incluye lo siguiente:
    
      - Administración de la compatibilidad con reuniones de conferencias web locales
    
      - Administración del uso de grupos de distribución para enviar mensajes instantáneos
    
      - Administración de contactos, presencia y consultas
    
      - Configuración del filtrado de versiones de cliente
    
      - Configuración del filtrado inteligente de mensajería instantánea
    
      - Configuración del archivado, registro detallado de llamadas y cumplimiento de las reuniones

  - **Administración de la conectividad**     del servidor perimetral La administración continua de los servidores y la configuración necesaria para proporcionar conectividad externa incluye lo siguiente:
    
      - Administración de la conectividad entre servidores internos y servidores perimetrales
    
      - Configuración de interfaces y certificados internos y externos para servidores perimetrales
    
      - Administración del acceso de socios federados

  - **Administración de la libreta**     de direcciones La administración de los servidores de la libreta de direcciones incluye lo siguiente:
    
      - Configuración de la normalización del teléfono del servidor de libreta de direcciones
    
      - Administración del servidor de la libreta de direcciones desde la línea de comandos

  - **Administración de cuentas**     de usuario La administración de cuentas de usuario incluye lo siguiente:
    
      - Habilitación de cuentas de usuario para Lync Server
    
      - Configuración de usuarios de Lync Server mediante el asistente
    
      - Configuración de propiedades de cuenta de usuario de Lync Server individual
    
      - Buscar usuarios de Lync Server
    
      - Mover usuarios de Lync Server
    
      - Eliminación de usuarios de Lync Server

  - **Analizar los archivos**     de registro de 2013 de Lync Server Una herramienta muy útil, generalmente usada para la solución de problemas, es la herramienta de registro de Lync Server 2013 que se describe en detalle en uso de la [herramienta de registro de Lync server 2013](https://technet.microsoft.com/library/gg558599.aspx).

Debido a que la herramienta de registro genera archivos de registro (en función de cada servidor), estos archivos de registro se pueden ver y analizar mediante la herramienta de supervisión, si las herramientas del kit de recursos de Microsoft Office Server 12 están instaladas en el equipo. De lo contrario, los registros también se pueden analizar con un editor de texto, que es mucho menos transparente y más complejo que el uso de la utilidad de supervisión.

Para ver y analizar mensajes de protocolo

En la herramienta de registro, cuando haya finalizado la sesión de depuración, haga clic en analizar archivos de registro para ver los archivos de registro mediante la herramienta de supervisión. Puede analizar los registros de protocolo para los siguientes componentes:

  - Lync Server SipStack (SIP)

  - Lync Server S4 (SIP)

  - Tráfico de señalización de conferencias de Lync Server (C3P), incluido el C3P de infrarrojos y el foco C3P

  - Tráfico de conferencia Web de Lync Server (PSOM)

  - Cliente de la plataforma de cliente de comunicaciones unificadas de Lync Server (UCCP)

  - Informes de errores de la base de datos de archivado

Para ayudar a organizar el rendimiento de las tareas necesarias, consulte As-Needed lista de comprobación de operaciones.

<div>


> [!IMPORTANT]  
> Para obtener información detallada acerca de los procedimientos de administración y administración, consulte la guía de administración de Microsoft Lync Server 2013.



</div>

<div>

## <a name="backup-and-restore-policies-or-configuration-settings"></a>Opciones de configuración y directivas de copia de seguridad (y restauración)

Lync Server 2013 permite realizar copias de seguridad y restaurar todo el sistema. IIF desea realizar una copia de seguridad (y, a continuación, quizás algún día de la restauración) una única directiva o una sola recopilación de opciones de configuración, recuperar la Directiva adecuada y, a continuación, canalizar el objeto al cmdlet Export-Clixml, que guarda la información de la Directiva como un archivo XML:

`Get-CsClientPolicy -Identity "RedmondClientPolicy" | Export-Clixml -Path C:\Backup\RedmondClientPolicy.xml`

Ahora puede experimentar con RedmondClientPolicy y cambiar una gran cantidad de opciones de configuración. Si, en su lugar, decide restaurar la directiva anterior, escriba:

`$x = Import-Clixml -Path C:\Backup\RedmondClientPolicy.xml`

`Set-CsClientPolicy -Instance $x`

Tenga en cuenta que este enfoque funcionará con la mayoría de las directivas y la configuración, pero no funcionará con algunos de los elementos más complejos (elementos que contienen varios subobjetos) (como las opciones de configuración de enrutamiento, que contienen varias rutas de voz independientes).

</div>

</div>

<span> </span>

</div>

</div>

</div>

