---
title: Configurar un nodo de monitor para que participe en la detección de System Center
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring a watcher node to participate in System Center discovery
ms:assetid: 15c5dcfd-603b-47ea-af1b-8714c2ec08af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204704(v=OCS.15)
ms:contentKeyID: 48183500
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 66be6bd0336471626f2ca4e41a89c3a45b073f05
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842296"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-in-lync-server-2013-to-participate-in-system-center-discovery"></a>Configuración de un nodo de monitor en Lync Server 2013 para participar en la detección de System Center

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-22_

Para asegurarse de que el nodo de monitor participe en el proceso de descubrimiento de System Center Operations Manager, debe completar el siguiente procedimiento en un equipo en el que se haya instalado la consola de System Center Operations Manager:

1.  En la pestaña **Administración** , haga clic en **agente administrado**.

2.  Haga clic con el botón secundario en el nombre del equipo del nodo de monitor y, a continuación, haga clic en **propiedades**. En el cuadro de diálogo **propiedades** , en la pestaña **seguridad** , seleccione **permitir que este agente actúe como proxy y descubrir objetos administrados en otros equipos**y, a continuación, haga clic en **Aceptar**.

Después de configurar el nodo de monitor para que actúe como proxy, reinicie el equipo del nodo de monitor. Después de reiniciar el equipo, compruebe que no se graban eventos de error en el registro de eventos de Operations Manager de ese equipo. Una vez que el equipo se haya ejecutado durante 15 minutos o más, use la consola de Operations Manager para comprobar que los equipos de Lync Server aparecen en la categoría **Lync** .

</div>

<span> </span>

</div>

</div>

</div>

