---
title: Implementar el servidor perimetral piloto
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Deploy pilot Edge Server
ms:assetid: dab345c0-8577-4c11-ac73-fe8b2a75f4cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205306(v=OCS.15)
ms:contentKeyID: 48185559
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ba616f6a5ce86e0f94c3b52afd60aaba34b7635
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751272"
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

En este tema se destacan las opciones de configuración que debe tener en cuenta antes de implementar el servidor perimetral de Lync Server 2013. Los procesos de implementación y configuración de Lync Server 2013 son muy similares a los de Lync Server 2010. En esta sección solo se detallan los aspectos clave que hay que considerar al implementar el grupo piloto. Para conocer los pasos detallados, consulte [Deploying external User Access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) en la documentación sobre implementación, que describe el proceso de implementación y también proporciona información de configuración para el acceso de usuarios externos.

As you navigate through the **Define New Edge Pool** wizard, review the key configuration settings shown in the following steps. Note that only a few pages of the **Define New Edge Pool** wizard are shown.

**Definir un grupo de servidores perimetrales**

1.  Inicie sesión en el equipo en el que Topology Builder esté instalado como miembro del grupo Admins. del dominio y el grupo RTCUniversalServerAdmins.

2.  Navegue hasta el nodo 2013 de Lync Server. haga clic con el botón secundario en **Grupos de servidores perimetrales** y en **Nuevo grupo de servidores perimetrales**.
    
    ![Definir el cuadro de diálogo nuevo grupo de servidores perimetrales](images/JJ205306.a90d388c-49ff-4620-a19d-42e2f1bb559c(OCS.15).jpg "Definir el cuadro de diálogo nuevo grupo de servidores perimetrales")

3.  Un grupo de servidores perimetrales puede ser un **Grupo de varios equipos** o un **Grupo de un solo equipo**.
    
    ![Cuadro de diálogo definir el FQDN del grupo de servidores perimetrales](images/JJ205306.4904fe8f-537c-4e66-a399-1bd8a316dc10(OCS.15).jpg "Cuadro de diálogo definir el FQDN del grupo de servidores perimetrales")

4.  En la página **Seleccionar características**, no habilite la federación ni la federación XMPP. La Federación y la Federación de XMPP se enrutan actualmente a través del servidor perimetral de Lync Server 2010 antiguo. Estas características se configurarán en una fase posterior de la migración.
    
    ![Cuadro de diálogo Seleccionar características](images/JJ205306.cb0b45a4-2856-45ba-bd97-e49fafbb077e(OCS.15).jpg "Cuadro de diálogo Seleccionar características")

5.  Tras ello, siga cumplimentando las siguientes páginas del asistente: **FQDN externos**, **Definir la dirección IP interna** y **Definir la dirección IP externa**.

6.  En la página **definir el próximo salto** , seleccione el director para el próximo salto del grupo de servidores perimetrales de Lync Server 2010.
    
    ![Cuadro de diálogo definir el próximo salto](images/JJ205306.11baf3ea-74f5-4eb7-8650-b03b3b190416(OCS.15).jpg "Cuadro de diálogo definir el próximo salto")

7.  En la página **asociar grupos de servidores front-end o de mediación** , no asocie un grupo de servidores con este grupo de servidores perimetrales en este momento. El tráfico multimedia externo se enruta actualmente a través del servidor perimetral heredado de Lync Server 2010. Definiremos esta configuración en una fase posterior de la migración.
    
    ![Cuadro de diálogo asociar grupos de servidores front-end](images/JJ205306.fe0da887-7b51-4564-afc5-d57da95a2eb6(OCS.15).jpg "Cuadro de diálogo asociar grupos de servidores front-end")

8.  Haga clic en **Finalizar** y, a continuación, publique**** la topología.

9.  Siga los pasos descritos en [instalar servidores perimetrales para Lync Server 2013](lync-server-2013-install-edge-servers.md) en la documentación de implementación para instalar los archivos en el nuevo servidor perimetral, configurar los certificados e iniciar los servicios.

Es muy importante que siga las instrucciones de los temas [Deploying external User Access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) en la documentación sobre implementación. En esta sección solo se ha proporcionado cierta orientación sobre las opciones de configuración al instalar estos roles de servidor.

Ahora debe tener un servidor perimetral de Lync Server 2010 que esté implementado en paralelo con una implementación de servidor perimetral de Lync Server 2013. Antes de pasar a la siguiente fase, confirme que ambas implementaciones funcionan correctamente, que los servicios se han iniciado y que puede administrar cada una de las implementaciones.

</div>

<span> </span>

</div>

</div>

</div>

