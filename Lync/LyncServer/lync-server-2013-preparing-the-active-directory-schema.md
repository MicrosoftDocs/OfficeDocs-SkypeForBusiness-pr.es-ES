---
title: 'Lync Server 2013: preparación del esquema de Active Directory'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing the Active Directory schema
ms:assetid: 067726ae-fd3f-4133-a32f-26d2603ac674
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398119(v=OCS.15)
ms:contentKeyID: 48183300
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: efabd082fce4dba5cf210e2c0f9c390324474cd2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201786"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="preparing-the-active-directory-schema-in-lync-server-2013"></a>Preparar el esquema de Active Directory en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-08-27_

Antes de empezar a preparar los servicios de dominio de Active Directory, puede abrir los archivos de esquema con un editor de texto, como el Bloc de notas de Windows, o ver las [extensiones de esquema, las clases y los atributos de Active Directory usados por Lync server 2013](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md) para revisar todas las extensiones de esquema de servicios de dominio de Active Directory que se modificarán para Lync Server 2013. Lync Server usa cuatro archivos de esquema:

  - ExternalSchema. ldf, que se usa para la interoperabilidad con Microsoft Exchange Server

  - ServerSchema. ldf, que es el archivo de esquema principal de Lync Server 2013

  - BackCompatSchema.ldf, que se usa para la interoperabilidad con todos los componentes de versiones anteriores

  - VersionSchema.ldf, que se usa para la información de versión del esquema preparado

Todos los archivos .ldf se instalan durante la preparación del esquema, sin importar si se está migrando desde una versión anterior o si se está realizando una instalación limpia. Estos archivos de esquema se instalan en la secuencia que se muestra en la lista anterior y \\se\\encuentran en la carpeta esquema de soporte en los medios de instalación.

Las extensiones de esquema de Lync Server se replican en todos los dominios, lo que afecta al tráfico de red. Ejecute la preparación del esquema cuando el uso de la red sea bajo.

<div>


> [!NOTE]  
> Si necesita agregar compatibilidad con los clientes móviles de Microsoft® Office Communicator Mobile 2007 R2 para Java y Microsoft® Office Communicator Mobile para Nokia 1,0 a su implementación de Lync Server 2013, debe preparar el esquema de Active Directory para Microsoft Office Communications Server 2007 R2 durante la instalación de Lync Server 2013. Para consultar la documentación y el software necesario <A href="https://go.microsoft.com/fwlink/p/?linkid=207172">https://go.microsoft.com/fwlink/p/?linkId=207172</A>, consulte.



</div>

<div>

## <a name="adsi-edit"></a>ADSI Edit

El editor de interfaces de servicio de Active Directory (ADSI Edit) es una herramienta administrativa del servicio de dominio de Active Directory (AD DS) que puede usarse para verificar la preparación y replicación de esquemas.

ADSI Edit se instala de forma predeterminada al instalar el rol AD DS para hacer del servidor un controlador de dominios. Para Windows Server 2008 y Windows Server 2008 R2, ADSI Edit (AdsiEdit. msc) se incluye con las herramientas de administración remota del servidor (RSAT). También puede instalar las RSAT en servidores de miembros de domino o en servidores independientes. El paquete de RSAT se copia de forma predeterminada en estos servidores al instalar Windows, pero no se instala de forma predeterminada. Las herramientas individuales se instalan con el Administrador de servidores. El editor ADSI se incluye en **Herramientas de administración de roles**, **Herramientas de los Servicios de dominio de Active Directory**, **Herramientas del controlador de dominio de Active Directory**.

Para Windows Server 2003, el editor ADSI se incluye con las herramientas de soporte técnico. Las herramientas de soporte están disponibles en el CD de Windows Server 2003 \\,\\en la carpeta Support Tools, o puede descargarlas desde "herramientas de soporte técnico de Windows server 2003 Service [https://go.microsoft.com/fwlink/p/?linkId=125770](https://go.microsoft.com/fwlink/p/?linkid=125770)Pack 2 32-bit" en. Las instrucciones para instalar las herramientas de soporte desde el CD del producto están disponibles en "instalar herramientas de [https://go.microsoft.com/fwlink/p/?linkId=125771](https://go.microsoft.com/fwlink/p/?linkid=125771)soporte de Windows" en. Adsiedit. dll se registra automáticamente al instalar las herramientas de soporte técnico. Sin embargo, si copió los archivos en el equipo, debe ejecutar el comando **regsvr32** para registrar el archivo ADSIEdit. dll antes de poder ejecutar la herramienta.

</div>

<div>

## <a name="in-this-section"></a>En esta sección

  - [Ejecución de la preparación del esquema de Active Directory en Lync Server 2013](lync-server-2013-running-schema-preparation.md)

  - [Comprobar la replicación de esquemas de Active Directory en Lync Server 2013](lync-server-2013-verifying-schema-replication.md)

</div>

<div>

## <a name="see-also"></a>Consulta también


[Preparar el bosque para Lync Server 2013](lync-server-2013-preparing-the-forest.md)  
[Preparar dominios para Lync Server 2013](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

