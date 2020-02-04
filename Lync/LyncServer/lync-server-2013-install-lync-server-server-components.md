---
title: 'Lync Server 2013: Instalar componentes del servidor Lync Server'
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
ms.openlocfilehash: 4f039f9363469663410f08f078a3b7e17a170075
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763724"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-server-components-for-lync-server-2013"></a>Instalar componentes del servidor en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-05-05_

Antes de seguir estos pasos, asegúrese de que ha iniciado sesión en el servidor con una cuenta de usuario de dominio que es un administrador local y miembro del grupo RTCUniversalReadOnlyAdmins en Active Directory.

El Asistente para la implementación de Lync Server se usa para instalar los componentes necesarios para cada rol de Lync Server y para activar el servidor. Este artículo le guiará a través de los pasos de implementación de un servidor Standard Edition o de un servidor front-end en su infraestructura de Lync.

<div>

## <a name="to-install-lync-server-components"></a>Para instalar los componentes de Lync Server

1.  Si el Asistente para la implementación de Lync Server no se está ejecutando, inícielo en el servidor en el que desea instalar Lync.

2.  Haga clic en **instalar o actualizar el sistema de Lync Server**.

3.  En el Asistente para la implementación, confirme que el **paso 1: instalar el almacén de configuración local** tiene una marca de verificación verde, lo que significa que este servidor tiene una copia local de la tienda instalada correctamente. Si no está activado, debe instalar el almacén de configuración local en el servidor. Siga los pasos de [instalar el almacén de configuración local en Lync Server 2013](lync-server-2013-install-the-local-configuration-store.md) y, a continuación, vuelva aquí.

4.  Cuando esté listo para instalar los componentes de Lync Server 2013 en el servidor, haga clic en **Ejecutar** junto al **paso 2: configurar o quitar los componentes de Lync Server**.

5.  En la página **configurar los componentes de Lync Server** , haga clic en **siguiente** para configurar los componentes definidos en la topología publicada.

6.  La página **Commands Execute** mostrará un resumen de comandos e información de instalación a medida que se realiza la configuración. Cuando finalice, puede usar la lista para seleccionar un registro que quiera ver y, luego, hacer clic en **Ver registro**.

7.  Cuando termine la instalación de los componentes de Lync Server 2013 y haya revisado los registros según sea necesario, haga clic en **Finalizar** para completar este paso en la instalación.
    
    <div>
    

    > [!NOTE]  
    > Si se le pide que reinicie el servidor (lo que puede ocurrir si es necesario instalar la experiencia de escritorio de Windows), lo hace definitivamente. Cuando el equipo esté en funcionamiento, tendrá que realizar estos pasos de nuevo, empezando desde el paso tres que se indican anteriormente (básicamente, ejecute el paso 2 en el Asistente de implementación una vez más).

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

