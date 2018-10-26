---
title: 'Lync Server 2013: Publicar una topología'
TOCTitle: Publicar una topología
ms:assetid: bfed3829-7a54-4b5c-a7cb-28871acd35e7
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg412935(v=OCS.15)
ms:contentKeyID: 48276555
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Publicar una topología en Lync Server 2013

 

_**Última modificación del tema:** 2012-09-08_

Cada vez que use Generador de topologías para crear la topología, debe publicar la topología en una base de datos en el Almacén de administración central, de modo que se puedan usar los datos para implementar Lync Server 2013. Siga el procedimiento indicado a continuación para publicar la topología.

## Para publicar la topología

1.  Inicie el Generador de topologías: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Generador de topologías de Lync Server**.

2.  En Generador de topologías, en al árbol de la consola, haga clic con el botón derecho en **Lync 2013** y haga clic en **Publicar topología**.

3.  En la página **principal** del Asistente, haga clic en **Siguiente** .

4.  En la página **Generador de topologías ha encontrado un almacén de administración de configuración** , haga clic en **Siguiente** .

5.  En la página **Crear otras bases de datos** , haga clic en **Siguiente** .

6.  Cuando el estado indica que la creación de bases de datos se ha realizado correctamente, haga lo siguiente:
    
      - Para visualizar el registro, haga clic en **Ver registro** .
    
      - Para cerrar el asistente, haga clic en **Finalizar** .
        
        > [!IMPORTANT]  
        > Si se trata de una instalación nueva de Servidor perimetral o Grupo de servidores perimetrales, debe exportar la configuración de Servidor perimetral desde un Servidor front-end, Grupo de servidores front-end o Servidor Standard Edition existente. Para exportar la configuración, consulte <a href="lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md">Exportar la topología de Lync Server 2013 y copiarla en un medio externo para la instalación perimetral</a>. Importará el archivo de configuración desde un medio externo o un recurso compartido de redes durante la instalación y la fase de implementación de Servidores perimetrales a través de Asistente para la implementación de Lync Server.<br />
        > Una vez que el Servidores perimetrales son operativos y la base de datos de almacenamiento de administración de configuración local se replica con la implementación interna, las actualizaciones posteriores de la configuración del Lync Server 2013 se publicarán y replicarán en el Servidores perimetrales.

