---
title: 'Lync Server 2013: instalar componentes de Lync Server Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install Lync Server server components
ms:assetid: 186aed6e-7adf-4a92-9f2e-f9a4de5ff202
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398239(v=OCS.15)
ms:contentKeyID: 48183528
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b6cb5c895eb58f7839c3e748524d7b355a08daff
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153662"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="install-server-components-for-lync-server-2013"></a>Instalación de componentes de servidor para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-05-05_

Antes de seguir estos pasos, asegúrese de que ha iniciado sesión en el servidor con una cuenta de usuario de dominio que sea un administrador local y un miembro del grupo RTCUniversalReadOnlyAdmins en Active Directory.

El Asistente para la implementación de Lync Server se usa para instalar los componentes necesarios para cada función de Lync Server y para activar el servidor. Este artículo le guiará por los pasos necesarios para implementar un servidor Standard Edition o un servidor front-end en su infraestructura de Lync.

<div>

## <a name="to-install-lync-server-components"></a>Para instalar los componentes de Lync Server

1.  Si el Asistente para la implementación de Lync Server no se está ejecutando, inícielo en el servidor en el que desea instalar Lync.

2.  Haga clic en **instalar o actualizar el sistema Lync Server**.

3.  En el Asistente para la implementación, confirme que el **paso 1: instalar el almacén de configuración local** tiene una marca de verificación verde, lo que significa que este servidor tiene una copia local de la tienda instalada correctamente. Si no se selecciona, debe instalar el almacén de configuración local en el servidor. Siga los pasos descritos en [Install the local Configuration store in Lync Server 2013](lync-server-2013-install-the-local-configuration-store.md) y, a continuación, vuelva aquí.

4.  Cuando esté listo para instalar los componentes de Lync Server 2013 en el servidor, haga clic en **Ejecutar** junto al **paso 2: configurar o quitar componentes de Lync Server**.

5.  En la página **Configurar componentes de Lync Server** , haga clic en **siguiente** para configurar los componentes tal y como se definen en su topología publicada.

6.  La página **ejecución de comandos** mostrará un resumen de los comandos y la información de instalación a medida que se realiza la configuración. Cuando haya terminado, puede usar la lista para seleccionar un registro y, a continuación, hacer clic en **Ver registro**.

7.  Cuando termine la instalación de los componentes de Lync Server 2013 y haya revisado los registros según sea necesario, haga clic en **Finalizar** para completar este paso en la instalación.
    
    <div>
    

    > [!NOTE]  
    > Si se le pide que reinicie el servidor (lo que puede ocurrir si es necesario instalar la experiencia de escritorio de Windows), hágalo definitivamente. Cuando el equipo vuelva a estar en funcionamiento, deberá realizar estos pasos de nuevo, comenzando desde el paso tres enumerado anteriormente (básicamente, ejecute el paso 2 del Asistente para la implementación una vez más).

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

