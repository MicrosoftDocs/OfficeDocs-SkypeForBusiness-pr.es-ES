---
title: 'Lync Server 2013: restaurar un servidor miembro de Enterprise Edition'
description: 'Lync Server 2013: restaurar un servidor miembro de Enterprise Edition.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring an Enterprise Edition member server
ms:assetid: d960b19c-2104-4719-b736-0d940f254d42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202191(v=OCS.15)
ms:contentKeyID: 51541523
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4f9838f030205d92988e185798d982f835122c9f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576056"
---
# <a name="restoring-an-enterprise-edition-member-server-in-lync-server-2013"></a>Restauración de un servidor miembro de Enterprise Edition en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-18_

Si se produce un error en un servidor que ejecuta uno de los siguientes roles de servidor, siga el procedimiento de este tema para restaurar el servidor. Si se producen errores en varios servidores de forma independiente, siga el procedimiento en cada servidor.

  - Servidor front-end

  - Servidor de mediación

  - Director

  - Servidor de chat persistente

  - Servidor perimetral

<div>


> [!TIP]  
> Le recomendamos que tome una copia de imagen del sistema antes de comenzar la restauración. Puede usar esta imagen como un punto de reversión, en caso de que algo salga mal durante la restauración. Es posible que desee tomar la copia de la imagen después de instalar el sistema operativo y SQL Server, y restaurar o volver a inscribir los certificados.



</div>

<div>

## <a name="to-restore-a-member-server"></a>Para restaurar un servidor miembro

1.  Empiece con un servidor nuevo o limpio que tenga el mismo nombre de dominio completo (FQDN) que el servidor con el error, instale el sistema operativo y, a continuación, restaure o vuelva a inscribir los certificados.
    
    <div>
    

    > [!NOTE]  
    > Siga los procedimientos de implementación de servidores de la organización para realizar este paso.

    
    </div>

2.  Desde una cuenta de usuario que sea miembro del grupo RTCUniversalServerAdmins, inicie sesión en el servidor que va a restaurar.

3.  Vaya a la carpeta o los medios de instalación de Lync Server e inicie el Asistente para la implementación de Lync Server que se encuentra en la \\ instalación de \\ AMD64 \\Setup.exe.

4.  Siga el asistente para la implementación para hacer lo siguiente:
    
    1.  Ejecute el **Paso 1: Instalar el almacén de configuración local** para instalar los archivos de configuración local.
    
    2.  Ejecute el **paso 2: configurar o quitar componentes de Lync Server** para instalar el rol de servidor de Lync Server.
    
    3.  Ejecute el **Paso 3: Solicitar, instalar o asignar certificados** para asignar los certificados.
    
    4.  Ejecute el **Paso 4: Iniciar servicios** para iniciar los servicios en el servidor.
    
    Para obtener más información sobre cómo ejecutar el Asistente para la implementación, consulte la documentación de implementación del rol de servidor que va a restaurar.

</div>

</div>

<span> </span>

</div>

</div>

</div>

