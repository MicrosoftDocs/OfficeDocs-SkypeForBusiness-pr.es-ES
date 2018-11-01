---
title: 'Lync Server 2013: Preparación del esquema de Active Directory'
TOCTitle: Preparación del esquema de Active Directory
ms:assetid: 067726ae-fd3f-4133-a32f-26d2603ac674
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398119(v=OCS.15)
ms:contentKeyID: 48274316
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Preparación del esquema de Active Directory en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

Antes de empezar a preparar Servicios de dominio de Active Directory, puede abrir los archivos de esquema con un editor de texto, como, por ejemplo, Windows Notepad, o bien consultar [Extensiones de esquema, clases y atributos de Active Directory usados por Lync Server 2013](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md) para revisar todas las extensiones de esquema de Servicios de dominio de Active Directory que se modificarán para Lync Server 2013. Lync Server usa cuatro archivos de esquema:

  - ExternalSchema.ldf, que se usa para la interoperabilidad con Microsoft Exchange Server

  - ServerSchema.ldf, que es el archivo de esquema principal de Lync Server 2013

  - BackCompatSchema.ldf, que se usa para la interoperabilidad con todos los componentes de versiones anteriores

  - VersionSchema.ldf, que se usa para la información de versión del esquema preparado

Todos los archivos .ldf se instalan durante la preparación del esquema, sin importar si se está migrando desde una versión anterior o si se está realizando una instalación limpia. Estos archivos de esquema se instalan en el orden que se muestra en la lista precedente y están ubicados en la carpeta \\Support\\schema del medio de instalación.

Las extensiones del esquema de Lync Server se replican en todos los dominios, lo que afecta al tráfico de la red. Ejecute la preparación del esquema cuando el uso de la red sea bajo.


> [!NOTE]
> Si necesita agregar compatibilidad para Microsoft® Office Communicator Mobile 2007 R2 para Java y Microsoft® Office Communicator Mobile para los clientes de móviles Nokia 1.0 a la implementación de Lync Server 2013, tendrá que preparar el esquema de Active Directory para Microsoft Office Communications Server 2007 R2 durante la instalación de Lync Server 2013. Si desea conocer el software y la documentación necesarios, consulte <A href="http://go.microsoft.com/fwlink/?linkid=207172%26clcid=0xc0a">http://go.microsoft.com/fwlink/?linkid=207172&amp;clcid=0xC0A</A>.



## ADSI Edit

El editor de interfaces de servicio de Active Directory (ADSI Edit) es una herramienta administrativa del servicio de dominio de Active Directory (AD DS) que puede usarse para verificar la preparación y replicación de esquemas.

ADSI Edit se instala de forma predeterminada al instalar el rol AD DS para hacer del servidor un controlador de dominios. En el caso de Windows Server 2008 y Windows Server 2008 R2, ADSI Edit (adsiedit.msc) viene incluido con las herramientas de administración remota del servidor (RSAT). También puede instalar las RSAT en servidores de miembros de domino o en servidores independientes. El paquete de RSAT se copia de forma predeterminada en estos servidores al instalar Windows, pero no se instala de forma predeterminada. Las herramientas individuales se instalan con el Administrador de servidores. El editor ADSI se incluye en **Herramientas de administración de roles**, **Herramientas de los Servicios de dominio de Active Directory**, **Herramientas del controlador de dominio de Active Directory**.

En el caso de Windows Server 2003, el Editor ADSI se incluye con las herramientas de soporte. Las herramientas de soporte se encuentran disponibles en el CD de Windows Server 2003, en la carpeta \\SUPPORT\\TOOLS. También puede descargarlas desde "Herramientas de soporte técnico de Windows Server 2003 Service Pack 2 de 32 bits" en [http://go.microsoft.com/fwlink/?linkid=125770\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=125770%26clcid=0xc0a). Las instrucciones para instalar las herramientas de soporte desde el CD del producto están disponibles en “Instalar las herramientas de soporte de Windows", en [http://go.microsoft.com/fwlink/?linkid=125771\&clcid=0xC0A](http://go.microsoft.com/fwlink/?linkid=125771%26clcid=0xc0a). Adsiedit.dll se registra automáticamente cuando se instalan las herramientas de soporte. Si, sin embargo, copió los archivos en el equipo, deberá ejecutar el comando **regsvr32** para registrar el archivo adsiedit.dll antes de poder ejecutar la herramienta.

## En esta sección

  - [Ejecutar la preparación del esquema de Active Directory en Lync Server 2013](lync-server-2013-running-schema-preparation.md)

  - [Comprobar la replicación de esquemas de Active Directory en Lync Server 2013](lync-server-2013-verifying-schema-replication.md)

## Vea también

#### Otros recursos

[Preparación del bosque para Lync Server 2013](lync-server-2013-preparing-the-forest.md)  
[Preparar dominios para Lync Server 2013](lync-server-2013-preparing-domains.md)

