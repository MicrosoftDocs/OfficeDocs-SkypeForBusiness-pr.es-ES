---
title: 'Lync Server 2013: Instalar servidores perimetrales'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Install Edge Servers
ms:assetid: 1655ab69-3899-4ee4-a1cc-8243bc1bfa0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398230(v=OCS.15)
ms:contentKeyID: 48183503
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 211baa13f80e89fa081b6bf65d4bd7e90d50d000
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835006"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-edge-servers-for-lync-server-2013"></a>Instalar servidores perimetrales para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-08_

Para instalar Lync Server 2013 en servidores perimetrales, use el Asistente para la implementación de Lync Server. Al ejecutar el Asistente para la implementación en cada servidor perimetral, puede completar la mayoría de las tareas necesarias para configurar el servidor perimetral. Para implementar Lync Server 2013 en un servidor perimetral, debe ejecutar ya el generador de topologías para definir y publicar la topología del servidor perimetral, y exportarla a medios que estén disponibles desde el servidor perimetral. Para obtener información detallada, vea [escenarios de acceso de usuarios externos en Lync server 2013](lync-server-2013-scenarios-for-external-user-access.md) y [exportar su topología de Lync Server 2013 y copiarla en medios externos para la instalación perimetral](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md).

Después de usar el Asistente para la implementación para instalar cada servidor perimetral, instalar y asignar los certificados necesarios e iniciar los servicios necesarios, puede completar la configuración con la información de [configurar compatibilidad con el acceso de usuarios externos en Lync Server 2013 ](lync-server-2013-configuring-support-for-external-user-access.md)para habilitar y configurar el acceso externo del usuario y la información para [comprobar la implementación perimetral en Lync Server 2013](lync-server-2013-verifying-your-edge-deployment.md) para validar la configuración, incluida la conectividad de servidor y de cliente.

<div>

## <a name="to-install-an-edge-server"></a>Para instalar un servidor perimetral

1.  Inicie sesión en el equipo en el que desea instalar el servidor perimetral como miembro del grupo de administradores locales o en una cuenta con derechos y permisos de usuario equivalentes.

2.  Asegúrese de que el archivo de configuración de topología creado con el generador de topología y, a continuación, exportado y copiado a un medio externo esté disponible en el servidor perimetral (por ejemplo, el acceso a la unidad USB en la que ha copiado el archivo de configuración de topología o Compruebe acceso al recurso compartido de red en el que ha copiado el archivo).

3.  Inicie el Asistente para la implementación.
    
    <div>
    

    > [!NOTE]  
    > Si recibe un mensaje que indica que necesita instalar Microsoft Visual C++ Redistributable, haga clic en <STRONG>sí</STRONG>. En el siguiente cuadro de diálogo, puede aceptar la <STRONG>Ubicación de instalación</STRONG> predeterminada o hacer clic en <STRONG>examinar</STRONG> para seleccionar una ubicación alternativa y, a continuación, hacer clic en <STRONG>instalar</STRONG>. En el siguiente cuadro de diálogo, active la casilla acepto <STRONG>los términos del contrato de licencia</STRONG> y, a continuación, haga clic en <STRONG>Aceptar</STRONG>.

    
    </div>

4.  En el Asistente para la implementación, haga clic en **instalar o actualizar el sistema de Lync Server**.

5.  Una vez que el asistente determina el estado de implementación, en el **paso 1. Instale el almacén de configuración local**, haga clic en **Ejecutar** y luego haga lo siguiente:
    
      - En el cuadro de diálogo **configurar réplica local del almacén de administración central** , haga clic en **Importar desde un archivo (recomendado para servidores perimetrales)**, vaya a la ubicación del archivo de configuración de topología exportada, seleccione el archivo. zip, haga clic en **abrir**y, a continuación, Haga clic en **siguiente**.
    
      - El Asistente para la implementación lee la información de configuración del archivo de configuración y escribe el archivo de configuración XML en el equipo local.
    
      - Cuando el proceso **Ejecución de comandos** se complete, haga clic en **Finalizar**.

6.  En el Asistente para la implementación, haga clic en **paso 2: configurar o quitar los componentes de Lync Server** para instalar los componentes de borde de lync Server 2013 que se especifican en el archivo de configuración XML que se almacena en el equipo local.

7.  Una vez completada la instalación, use la información de [configurar certificados perimetrales para Lync Server 2013](lync-server-2013-set-up-edge-certificates.md) para instalar y asignar los certificados necesarios antes de iniciar los servicios.

</div>

</div>

<span> </span>

</div>

</div>

</div>

