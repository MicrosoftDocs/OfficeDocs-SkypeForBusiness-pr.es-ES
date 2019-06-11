---
title: Implementar el servidor perimetral piloto
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Deploy pilot Edge Server
ms:assetid: 11a59c48-0a53-4de1-83ed-875f850febd5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204682(v=OCS.15)
ms:contentKeyID: 48183446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c9cfe98069d3c90f4e021b34f6a7d31c583e7565
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842834"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-pilot-edge-server"></a>Implementar el servidor perimetral piloto

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-19_

En este tema se destacan las opciones de configuración que debe tener en cuenta antes de implementar el servidor perimetral de Lync Server 2013. Esta sección solo resalta los puntos clave que debe considerar como parte de la implementación del grupo de bordes de la prueba piloto. Para conocer los pasos detallados, vea [implementar el acceso de usuarios externos en Lync Server 2013](lync-server-2013-deploying-external-user-access.md) en la documentación de implementación, que describe el proceso de implementación y también proporciona información de configuración para el acceso de usuarios externos.

Mientras navega por el asistente **definir nuevo grupo de bordes** , revise la configuración de clave que se muestra en los siguientes pasos. Observe que solo se muestran algunas páginas del asistente **definir nuevo grupo de bordes** .

**Definir un grupo perimetral**

1.  Abra la topología de la agrupación piloto con el generador de topología.

2.  Vaya al nodo de 2013 de Lync Server. Haga clic con **** el botón secundario en agrupaciones perimetrales y haga clic en **nuevo borde**.
    
    ![Definir el cuadro de diálogo nuevo grupo perimetral] (images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Definir el cuadro de diálogo nuevo grupo perimetral")

3.  Un grupo de servidores perimetrales puede ser un **grupo de varios equipos** o un **único grupo de equipos**.
    
    ![Definir el cuadro de diálogo FQDN del grupo de bordes] (images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Definir el cuadro de diálogo FQDN del grupo de bordes")

4.  En la página **seleccionar características** , no habilite la Federación ni la Federación XMPP. La Federación y la Federación de XMPP actualmente se enrutan a través del servidor perimetral heredado de Office Communications Server 2007 R2. Estas características se configurarán en una fase posterior de la migración.
    
    ![Cuadro de diálogo Seleccionar características] (images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Cuadro de diálogo Seleccionar características")

5.  Después, siga completando las siguientes páginas del asistente: **Seleccione opciones de IP**, **FQDN externos**, **defina la dirección IP interna**y **defina la dirección IP externa**.

6.  En la página **definir el siguiente salto** , seleccione el director para el próximo salto del grupo de servidores perimetrales de Lync Server 2013.
    
    ![Cuadro de diálogo definir nuevo grupo perimetral, lista Grupo de próximos saltos] (images/JJ204682.61d963d5-e0bd-4b1f-b437-e37c267347ba(OCS.15).jpg "Cuadro de diálogo definir nuevo grupo perimetral, lista Grupo de próximos saltos")

7.  En la página **asociar pools front-end** , no asocie un grupo con este grupo perimetral en este momento. El tráfico multimedia externo se enruta actualmente a través del servidor perimetral heredado de Office Communications Server 2007 R2. Esta configuración se configurará en una fase posterior de la migración.
    
    ![Cuadro de diálogo definir nuevo grupo perimetral] (images/JJ204682.bb538039-bd2a-40ed-a120-8b80bd2cefc2(OCS.15).jpg "Cuadro de diálogo definir nuevo grupo perimetral")

8.  Haga clic en **Finalizar** y, a continuación, **publique** la topología.

9.  Siga los pasos que se indican en [instalar servidores perimetrales para Lync Server 2013](lync-server-2013-install-edge-servers.md) en la documentación de implementación para instalar los archivos en el nuevo servidor perimetral, configurar certificados e iniciar los servicios.

Es muy importante seguir las directrices de los temas [implementar el acceso de usuarios externos en Lync Server 2013](lync-server-2013-deploying-external-user-access.md) en la documentación de implementación. En esta sección se proporciona una mera información sobre las opciones de configuración al instalar estos roles de servidor.

Ahora debe tener una implementación heredada de servidor perimetral de Office Communications Server 2007 R2, indicada por la presencia de la BackCompatSite, en paralelo con una implementación de servidor perimetral de Lync Server 2013. La Federación está configurada para usar el director de Office Communications Server 2007 R2. Compruebe que las implementaciones se ejecutan correctamente y que se inician los servicios, y puede administrar cada implementación antes de pasar a la siguiente fase.

![Generador de topología que muestra el servidor perimetral de OCS] (images/JJ204682.171363a3-eaf0-4c94-bd41-02b1ab6fa7dc(OCS.15).jpg "Generador de topología que muestra el servidor perimetral de OCS")

</div>

<span> </span>

</div>

</div>

</div>

