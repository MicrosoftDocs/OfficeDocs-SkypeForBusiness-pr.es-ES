---
title: Implementar el servidor perimetral piloto
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Deploy pilot Edge Server
ms:assetid: 11a59c48-0a53-4de1-83ed-875f850febd5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204682(v=OCS.15)
ms:contentKeyID: 48183446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6cbf3be6dd47f794768ba0f3c8140e7124a1cabb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180413"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploy-pilot-edge-server"></a>Implementar el servidor perimetral piloto

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-19_

En este tema se destacan las opciones de configuración que debe tener en cuenta antes de implementar el servidor perimetral de Lync Server 2013. En esta sección solo se destacan los puntos clave que se deben tener en cuenta como parte de la implementación del grupo de servidores perimetrales piloto. Para conocer los pasos detallados, consulte [Deploying external User Access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) en la documentación sobre implementación, que describe el proceso de implementación y también proporciona información de configuración para el acceso de usuarios externos.

Al navegar por el asistente **Definir nuevo grupo de servidores perimetrales**, repase las principales opciones de configuración recogidas en cada paso. Observe que solo se muestran unas cuantas páginas de**** este asistente.

**Definir un grupo de servidores perimetrales**

1.  Abra la topología del grupo piloto en Generador de topologías.

2.  Navegue hasta el nodo 2013 de Lync Server. haga clic con el botón secundario en **Grupos de servidores perimetrales** y en **Nuevo grupo de servidores perimetrales**.
    
    ![Definir el cuadro de diálogo nuevo grupo de servidores perimetrales](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Definir el cuadro de diálogo nuevo grupo de servidores perimetrales")

3.  Un grupo de servidores perimetrales puede ser un **Grupo de varios equipos** o un **Grupo de un solo equipo**.
    
    ![Cuadro de diálogo definir el FQDN del grupo de servidores perimetrales](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Cuadro de diálogo definir el FQDN del grupo de servidores perimetrales")

4.  En la página **Seleccionar características**, no habilite la federación ni la federación XMPP. La Federación y la Federación XMPP actualmente se enrutan a través del servidor perimetral de Office Communications Server 2007 R2 heredado. Estas características se configurarán en una fase posterior de la migración.
    
    ![Cuadro de diálogo Seleccionar características](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Cuadro de diálogo Seleccionar características")

5.  A continuación, siga completando las siguientes páginas del asistente: **Seleccione opciones IP**, **FQDN externos**, **defina la dirección IP interna**y **defina la dirección IP externa**.

6.  En la página **definir el próximo salto** , seleccione el director para el próximo salto del grupo de servidores perimetrales de Lync Server 2013.
    
    ![Cuadro de diálogo definir nuevo grupo de servidores perimetrales, lista de grupo de servidores de próximo salto](images/JJ204682.61d963d5-e0bd-4b1f-b437-e37c267347ba(OCS.15).jpg "Cuadro de diálogo definir nuevo grupo de servidores perimetrales, lista de grupo de servidores de próximo salto")

7.  En la página **asociar grupos de servidores front-end** , no asocie un grupo de servidores a este grupo de servidores perimetrales en este momento. El tráfico de medios externos se enruta actualmente a través del servidor perimetral de Office Communications Server 2007 R2 heredado. Definiremos esta configuración en una fase posterior de la migración.
    
    ![Cuadro de diálogo definir nuevo grupo de servidores perimetrales](images/JJ204682.bb538039-bd2a-40ed-a120-8b80bd2cefc2(OCS.15).jpg "Cuadro de diálogo definir nuevo grupo de servidores perimetrales")

8.  Haga clic en **Finalizar** y, a continuación, publique**** la topología.

9.  Siga los pasos descritos en [instalar servidores perimetrales para Lync Server 2013](lync-server-2013-install-edge-servers.md) en la documentación de implementación para instalar los archivos en el nuevo servidor perimetral, configurar los certificados e iniciar los servicios.

Es muy importante que siga las instrucciones de los temas [Deploying external User Access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) en la documentación sobre implementación. En esta sección solo se ha proporcionado cierta orientación sobre las opciones de configuración al instalar estos roles de servidor.

Ahora debe tener una implementación heredada de servidor perimetral de Office Communications Server 2007 R2, indicada por la presencia de BackCompatSite, en paralelo con una implementación de servidor perimetral de Lync Server 2013. La Federación está configurada para usar el director de Office Communications Server 2007 R2. Antes de pasar a la siguiente fase, confirme que ambas implementaciones funcionan correctamente, que los servicios se han iniciado y que puede administrar cada una de las implementaciones.

![Generador de topologías que muestra el servidor perimetral de OCS](images/JJ204682.171363a3-eaf0-4c94-bd41-02b1ab6fa7dc(OCS.15).jpg "Generador de topologías que muestra el servidor perimetral de OCS")

</div>

<span> </span>

</div>

</div>

</div>

