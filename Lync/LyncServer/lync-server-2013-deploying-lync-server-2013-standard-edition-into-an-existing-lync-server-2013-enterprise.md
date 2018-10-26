---
title: "Implementación de Lync Server 2013 Standard Edition en Lync Server 2013 Enterprise"
TOCTitle: Implementación de Lync Server 2013 Standard Edition en un Lync Server 2013 Enterprise existente
ms:assetid: 05ea128d-6c94-49b3-b28b-477367196425
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg398112(v=OCS.15)
ms:contentKeyID: 48274312
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Implementación de Lync Server 2013 Standard Edition en un Lync Server 2013 Enterprise existente

 

_**Última modificación del tema:** 2012-10-01_

La implementación de un Servidor Standard Edition en una implementación de Enterprise Edition existente es similar a la implementación de roles de servidor adicionales. Un Servidor Standard Edition puede implementarse en otro sitio, lo que permite a los usuarios de dicho sitio estar hospedados en el Servidor Standard Edition, en lugar de en el Grupo de servidores front-end, en una red de área extensa (WAN). Los procedimientos de instalación del sitio nuevo y de los servidores de dicho sitio ya se han definido en otras secciones de la documentación de [Implementar Lync Server 2013](lync-server-2013-deploying-lync-server.md).

**Para definir un sitio nuevo**

1.  Inicie el Generador de topologías: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y, después, en **Generador de topologías de Lync Server**.

2.  En el árbol de la consola, haga clic con el botón secundario en **Lync Server 2013** y después en **Nuevo sitio central**.

3.  En la página **Identificar el sitio**, escriba un nombre para el sitio y, opcionalmente, una descripción.

4.  Siga los procedimientos de definición del resto de la topología del sitio. Para más información, consulte [Definición y configuración de la topología en Lync Server 2013](lync-server-2013-defining-and-configuring-the-topology.md).

5.  Publicar la topología actualizada. Para más información, consulte [Publicar la topología en Lync Server 2013](lync-server-2013-publish-the-topology.md).

6.  Configure e instale un Servidor Standard Edition.
    
    > [!CAUTION]  
    > Si ha implementado un entorno con un solo Servidor Standard Edition, será necesario que inicie el proceso de configuración desde el Asistente para la implementación de Lync Server usando el vínculo <strong>Preparar el primer servidor Standard Edition</strong> para instalar los archivos de base de datos iniciales para el nuevo Servidor Standard Edition. <strong>No</strong> siga ese proceso cuando instale un Servidor Standard Edition en una implementación de Lync Server 2013 existente.
    

