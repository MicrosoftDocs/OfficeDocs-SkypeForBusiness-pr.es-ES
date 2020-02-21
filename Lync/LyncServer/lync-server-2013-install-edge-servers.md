---
title: 'Lync Server 2013: instalar servidores perimetrales'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install Edge Servers
ms:assetid: 1655ab69-3899-4ee4-a1cc-8243bc1bfa0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398230(v=OCS.15)
ms:contentKeyID: 48183503
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: af95403b8a1fc383d8d6065f26a55242e735a51b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204219"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="install-edge-servers-for-lync-server-2013"></a>Instalar servidores perimetrales para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-09-08_

Instale Lync Server 2013 en servidores perimetrales mediante el Asistente para la implementación de Lync Server. Cuando se ejecuta el Asistente para la implementación en cada servidor perimetral, se puede llevar a cabo la mayor parte de las tareas necesarias para configurar el servidor en cuestión. Para implementar Lync Server 2013 en un servidor perimetral, debe haber ejecutado el generador de topologías para definir y publicar la topología del servidor perimetral y exportarla a medios disponibles desde el servidor perimetral. Para obtener más información, consulte [escenarios para el acceso de usuarios externos en Lync server 2013](lync-server-2013-scenarios-for-external-user-access.md) y [exportar la topología de Lync Server 2013 y copiarla en un medio externo para la instalación perimetral](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md).

Después de usar el Asistente para la implementación para instalar cada servidor perimetral, instalar y asignar los certificados necesarios e iniciar los servicios necesarios, puede completar la configuración con la información de [configuración de compatibilidad para el acceso de usuarios externos en Lync server 2013](lync-server-2013-configuring-support-for-external-user-access.md) para habilitar y configurar el acceso de usuarios externos y la información en [comprobar la implementación perimetral en Lync Server 2013](lync-server-2013-verifying-your-edge-deployment.md) para validar la configuración, incluida la conectividad de cliente

<div>

## <a name="to-install-an-edge-server"></a>Para instalar un servidor perimetral

1.  Inicie sesión en el equipo en el que desea instalar el servidor perimetral como miembro del grupo Administradores o con una cuenta que tenga derechos o permisos de usuario similares.

2.  Asegúrese de que el archivo de configuración de la topología que ha creado mediante el generador de topologías y, a continuación, de que se ha exportado y copiado a un medio externo está disponible en el servidor perimetral (por ejemplo, acceso a la unidad USB en la que copió el archivo de configuración de la topología o Compruebe acceso al recurso compartido de red en el que copió el archivo).

3.  Inicie el Asistente para la implementación.
    
    <div>
    

    > [!NOTE]  
    > Si recibe un mensaje en el que se indica que es necesario instalar Microsoft Visual C++ Redistributable, haga clic en <STRONG>Sí</STRONG>. En el siguiente cuadro de diálogo, puede aceptar la <STRONG>Ubicación de instalación</STRONG> predeterminada o bien hacer clic en <STRONG>Examinar</STRONG> para seleccionar otra. Tras ello, haga clic en <STRONG>Instalar</STRONG>. En el siguiente cuadro de diálogo, active la casilla <STRONG>Acepto los términos del contrato de licencia</STRONG> y haga clic en <STRONG>Aceptar</STRONG>.

    
    </div>

4.  En el Asistente para la implementación, haga clic en **Instalar o actualizar sistema Lync Server**.

5.  Una vez que el asistente ha averiguado el estado de la implementación, en **Paso 1. Instalar almacén de configuración local**, haga clic en **Ejecutar** y realice lo siguiente:
    
      - En el cuadro de diálogo **Configurar réplica local del almacén de administración central**, haga clic en **Importar desde un archivo (recomendado en servidores perimetrales)**, vaya a la ubicación del archivo de configuración de la topología exportado, seleccione el archivo .zip, haga clic en **Abrir** y, a continuación, en **Siguiente**.
    
      - El Asistente para la implementación lee la información de configuración de este archivo y escribe el archivo de configuración XML en el equipo local.
    
      - Cuando el proceso **Ejecución de comandos** se complete, haga clic en **Finalizar**.

6.  En el Asistente para la implementación, haga clic en **paso 2: configurar o quitar componentes de Lync Server** para instalar los componentes perimetrales de lync Server 2013 que se han especificado en el archivo de configuración XML que se almacena en el equipo local.

7.  Una vez finalizada la instalación, use la información de [configurar certificados perimetrales para Lync Server 2013](lync-server-2013-set-up-edge-certificates.md) para instalar y asignar los certificados necesarios antes de iniciar los servicios.

</div>

</div>

<span> </span>

</div>

</div>

</div>

