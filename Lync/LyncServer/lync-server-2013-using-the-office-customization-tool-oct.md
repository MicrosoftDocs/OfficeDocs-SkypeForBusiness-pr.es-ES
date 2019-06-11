---
title: 'Lync Server 2013: uso de la herramienta de personalización de Office (OCT)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using the Office Customization Tool (OCT)
ms:assetid: 26647cb6-ba84-4ba7-8b6f-2cf86818e530
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204748(v=OCS.15)
ms:contentKeyID: 48183654
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cbdd9c101b9098f9a5a6ac6088740c067039921b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850160"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-office-customization-tool-oct-in-lync-server-2013"></a>Usar la herramienta de personalización de Office (OCT) en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-02_

La herramienta de personalización de Office (OCT) forma parte del programa de instalación y es la herramienta recomendada para muchas personalizaciones. Al usar la OCT, se personaliza Office y se guardan las personalizaciones en un archivo. MSP de personalización del programa de instalación. El archivo se coloca en la carpeta actualizaciones del punto de instalación de red. Al instalar Office, el programa de instalación busca un archivo de personalización de la configuración en la carpeta actualizaciones y aplica las personalizaciones. La carpeta actualizaciones solo se puede usar para implementar actualizaciones de software durante una instalación inicial de Office 2013.

La OCT forma parte de la instalación y se incluye en las versiones de licencia por volumen del producto. Para ejecutar la OCT, escriba `setup.exe /admin` en la línea de comandos de la raíz del punto de instalación de red que contiene los archivos de origen de Office 2013. Por ejemplo, use lo siguiente:

`\\server\share\Office15\setup.exe /admin`

Los administradores pueden usar la OCT para crear un archivo .msp de personalización de la instalación. Al igual que en Microsoft Office 2010, los administradores pueden personalizar las siguientes áreas:

  - **Configuración** Se usa para especificar la ubicación de instalación predeterminada en el cliente y el nombre de la organización predeterminada, otras fuentes de instalación en red, la clave de producto, el contrato de licencia para el usuario final, el nivel de presentación, las versiones anteriores de Office que se deben quitar y los programas personalizados que se ejecutan durante instalación, configuración de seguridad y propiedades de configuración.

  - **Características** Se usa para configurar las opciones de usuario y personalizar la instalación de las características de Office. Los administradores pueden usar la OCT para especificar los valores iniciales predeterminados de la aplicación de Office para los usuarios. Los usuarios pueden modificar la mayoría de las opciones después de la instalación.

  - **Contenido adicional** Se usa para agregar o quitar archivos, agregar o quitar entradas del registro y configurar accesos directos.

  - **Outlook** Se usa para personalizar el perfil predeterminado de Outlook de un usuario, especificar la configuración de Exchange, agregar cuentas, quitar cuentas y exportar\\la configuración y especificar los grupos de envío y recepción.

Para obtener más información sobre la OCT <http://go.microsoft.com/fwlink/p/?linkid=267516>, consulte.

</div>

<span> </span>

</div>

</div>

</div>

