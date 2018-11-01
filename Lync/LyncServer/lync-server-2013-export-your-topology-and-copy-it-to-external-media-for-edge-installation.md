---
title: "Exportar la topología y copiarla en un medio externo para la instalación perimetral"
TOCTitle: Exportar la topología y copiarla en un medio externo para la instalación perimetral
ms:assetid: def9f416-c519-4a72-b242-7d3057d9c1fd
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398983(v=OCS.15)
ms:contentKeyID: 48276929
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Exportar la topología de Lync Server 2013 y copiarla en un medio externo para la instalación perimetral

 

_**Última modificación del tema:** 2012-09-08_

Una vez publicada la topología, el Asistente para la implementación de Lync Server debe obtener acceso a los datos del Almacén de administración central para iniciar el proceso de implementación en el servidor. En la red interna, se puede obtener acceso a los datos desde los servidores, pero los servidores perimetrales que no se encuentran en el dominio interno no pueden obtener acceso a los datos. Para hacer que los datos de configuración de la topología estén disponibles para una implementación de servidor perimetral, debe exportar los datos de topología a un archivo y copiarlo en medios externos (por ejemplo, una unidad USB o un recurso compartido de red al que se puede obtener acceso desde el servidor perimetral) antes de ejecutar el Asistente para la implementación de Lync Server en el servidor perimetral. Siga el procedimiento indicado a continuación para hacer que sus datos de configuración de topología estén disponibles en el servidor perimetral que está implementando.


> [!NOTE]
> Una vez instalado Lync Server 2013 en un servidor perimetral, el servidor perimetral se administra mediante las herramientas administrativas de la red interna que automáticamente replican la configuración en todos los servidores perimetrales de la implementación. La única excepción es la asignación e instalación de certificados, así como la detención y el inicio de servicios que deben realizarse en el servidor perimetral.



## Para hacer que los datos de la topología estén disponibles en un servidor perimetral mediante el Shell de administración de Communications Server

1.  Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Shell de administración de Lync Server**.

2.  En el Shell de administración de Lync Server, ejecute el cmdlet siguiente:
    
        Export-CsConfiguration -FileName <ConfigurationFilePath.zip>

3.  Copie el archivo externo a medios externos (por ejemplo, una unidad USB o un recurso compartido de red disponible desde el servidor perimetral durante la implementación).

