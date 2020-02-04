---
title: 'Lync Server 2013: Preparación del esquema de Active Directory'
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
ms.openlocfilehash: 572f531b57c504bda210f8f21298076428342b62
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747400"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-the-active-directory-schema-in-lync-server-2013"></a>Preparación del esquema de Active Directory en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-08-27_

Antes de empezar a preparar los servicios de dominio de Active Directory, puede abrir los archivos de esquema con un editor de texto, como el Bloc de notas de Windows, o ver las [extensiones, las clases y los atributos de esquema de Active Directory que usa Lync server 2013](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md) para revisar todas las extensiones de esquema de los servicios de dominio de Active Directory que se modificarán para Lync Server 2013. Lync Server usa cuatro archivos de esquema:

  - ExternalSchema. ldf, que se usa para la interoperabilidad con Microsoft Exchange Server

  - ServerSchema. ldf, que es el archivo de esquema principal de Lync Server 2013

  - BackCompatSchema. ldf, que se usa para la interoperabilidad con cualquier componente de versiones anteriores

  - VersionSchema. ldf, que se usa para la información de versión del esquema preparado

Todos los archivos. ldf se instalan durante la preparación del esquema, independientemente de si está migrando desde una versión anterior o realizando una instalación limpia. Estos archivos de esquema se instalan en el orden que se muestra en la lista anterior y \\se\\encuentran en la carpeta esquema de soporte en los medios de instalación.

Las extensiones de esquema de Lync Server se replican en todos los dominios, lo que afecta al tráfico de red. Ejecutar la preparación del esquema en un momento en que el uso de la red es bajo.

<div>


> [!NOTE]  
> Si necesita agregar compatibilidad con Microsoft® Office Communicator Mobile 2007 R2 para Java y Microsoft® Office Communicator Mobile para clientes móviles Nokia 1,0 a su implementación de Lync Server 2013, debe preparar el esquema de Active Directory para Microsoft Office. Communications Server 2007 R2 durante la instalación de Lync Server 2013. Para obtener información sobre el software y la <A href="http://go.microsoft.com/fwlink/p/?linkid=207172">http://go.microsoft.com/fwlink/p/?linkId=207172</A>documentación necesarios, consulte.



</div>

<div>

## <a name="adsi-edit"></a>ADSI Edit

El editor de interfaces de servicio de Active Directory (ADSI Edit) es una herramienta de administración de AD DS que puede usar para comprobar la preparación y la replicación del esquema.

ADSI Edit se instala de forma predeterminada al instalar el rol AD DS para convertir un servidor en controlador de dominio. Para Windows Server 2008 y Windows Server 2008 R2, ADSI Edit (AdsiEdit. msc) se incluye con las herramientas de administración remota del servidor (RSAT). También puede instalar RSAT en servidores miembro de dominio o servidores independientes. El paquete de RSAT se copia en estos servidores de forma predeterminada al instalar Windows, pero no se instala de forma predeterminada. Instale herramientas individuales con el administrador del servidor. ADSI Edit se incluye en **herramientas de administración de roles**, **herramientas de servicios de dominio de Active**Directory, herramientas de controlador de dominio de **Active**Directory.

Para Windows Server 2003, se incluye ADSI Edit con las herramientas de soporte técnico. Las herramientas de soporte técnico están disponibles en el CD de Windows Server \\2003\\, en la carpeta Herramientas de soporte, o puede descargarlas desde "herramientas de soporte técnico de Windows server [http://go.microsoft.com/fwlink/p/?linkId=125770](http://go.microsoft.com/fwlink/p/?linkid=125770)2003 Service Pack 2 32" en. Encontrará instrucciones para instalar las herramientas de soporte del CD del producto en "instalar herramientas de soporte técnico de [http://go.microsoft.com/fwlink/p/?linkId=125771](http://go.microsoft.com/fwlink/p/?linkid=125771)Windows" en. Adsiedit. dll se registra automáticamente al instalar las herramientas de soporte técnico. Sin embargo, si ha copiado los archivos en el equipo, debe ejecutar el comando **regsvr32** para registrar el archivo ADSIEdit. dll antes de poder ejecutar la herramienta.

</div>

<div>

## <a name="in-this-section"></a>En esta sección

  - [Ejecutar la preparación del esquema de Active Directory en Lync Server 2013](lync-server-2013-running-schema-preparation.md)

  - [Comprobar la replicación de esquemas de Active Directory en Lync Server 2013](lync-server-2013-verifying-schema-replication.md)

</div>

<div>

## <a name="see-also"></a>Vea también


[Preparación del bosque para Lync Server 2013](lync-server-2013-preparing-the-forest.md)  
[Preparar dominios para Lync Server 2013](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

