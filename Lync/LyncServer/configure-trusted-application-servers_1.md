---
title: Configuración de servidores de aplicaciones de confianza
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure trusted application servers
ms:assetid: 47a9e72e-566c-4c23-bec2-760a3098a974
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204865(v=OCS.15)
ms:contentKeyID: 48184056
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0474e3e75998e43965bd57ef4ed1f67ef8058a0b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503277"
---
# <a name="configure-trusted-application-servers"></a>Configuración de servidores de aplicaciones de confianza

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-04_

En un entorno mixto, si crea un nuevo servidor de aplicaciones de confianza después de combinar la topología heredada de Office Communications Server con Lync Server 2013 y define un nuevo servidor de aplicaciones de confianza con el generador de topologías, debe establecer el grupo de servidores de próximo salto para que sea un grupo de servidores de Lync Server 2013. En un entorno combinado, tanto el grupo de servidores de Office Communications Server heredado como el grupo de servidores de Lync Server 2013 aparecen en la lista desplegable. *No* se puede seleccionar el grupo heredado.

<div>

## <a name="to-select-lync-server-2013-as-next-hop-when-creating-a-trusted-application-server"></a>Para seleccionar Lync Server 2013 como próximo salto al crear un servidor de aplicaciones de confianza

1.  Abrir una topología existente en el Generador de topologías

2.  En el panel izquierdo, haga clic con el botón derecho en **Servidores de aplicaciones de confianza** y haga clic en **Nuevo grupo de aplicaciones de confianza**.

3.  Introduzca el **FQDN del grupo de servidores** del grupo de aplicaciones de confianza y seleccione si será una implementación de un solo servidor o de varios servidores.

4.  Haga clic en **Siguiente**.

5.  En la página **seleccionar el próximo salto** , en la lista, seleccione el grupo de servidores front-end 2013 de Lync Server.
    
    ![Cuadro de diálogo definir nuevo grupo de aplicaciones de confianza](images/JJ204865.ecfe2bb8-758b-4b36-8146-573005c4ab09(OCS.15).jpg "Cuadro de diálogo definir nuevo grupo de aplicaciones de confianza")  

6.  Haga clic en  **Finalizar **.

7.  Seleccione el nodo superior **Lync Server** y en el panel  **Acciones**, seleccione **Publicar**.

8.  El **Grupo de aplicaciones de confianza** se creó correctamente y está asociado con el grupo de front-end correcto.

</div>

</div>

<span> </span>

</div>

</div>

</div>

