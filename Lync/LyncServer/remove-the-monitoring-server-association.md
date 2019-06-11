---
title: Quitar la asociación del servidor de supervisión
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Remove the Monitoring server association
ms:assetid: c45b22ae-fc06-484a-a05b-735bd1bb7448
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721877(v=OCS.15)
ms:contentKeyID: 49733810
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a5703153bb1034f1318fbe14ca3583ad5744ffdb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849858"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-the-monitoring-server-association"></a>Quitar la asociación del servidor de supervisión

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-04_

Para quitar el servidor de supervisión, debe cambiar o borrar la dependencia en el grupo front-end, el servidor front-end, el equipo de la sucursal y el servidor de la sucursal supervivientes relacionados. Edite las propiedades del grupo de servidores front-end, el servidor front-end, el equipo de sucursales con la supervivencia y el servidor de sucursal con la supervivencia para quitar la dependencia. Después de borrar la dependencia y eliminar el servidor en el generador de topología, se le notificará que el objeto de almacén de base de datos asociado en el generador de topología también se eliminará.

<div>

## <a name="to-remove-the-monitoring-server-association"></a>Para quitar la Asociación de servidor de supervisión

1.  Abra el servidor front-end 2013 de Lync Server, abra Topology Builder.

2.  Vaya al nodo de 2010 de Lync Server.

3.  En el generador de topología, expanda las **agrupaciones front-end Enterprise Edition**, **los servidores de aplicaciones para el usuario Standard Edition**o los **sitios de sucursales**en función de dónde se defina el servidor de supervisión.

4.  Si tiene asociado un servidor de sucursal, expanda **sitios de sucursales**, expanda el nombre del sitio de la sucursal y, a continuación, expanda **aplicaciones de sucursales**reutilizables.
    
    <div>
    

    > [!NOTE]  
    > Los <STRONG>dispositivos</STRONG> de la interfaz de usuario que son supervivientes se aplican a los servidores de sucursal con supervivencia y con la aplicación de rama superviviente.

    
    </div>

5.  Haga clic con el botón secundario en el grupo, servidor o dispositivo asociado al servidor de supervisión y, a continuación, haga clic en **Editar propiedades**.

6.  En **Editar propiedades**, en **General**, en **asociaciones**, desactive la casilla **asociar servidor de supervisión** y, a continuación, haga clic en **Aceptar**.

7.  Repita el paso anterior para cualquier otro grupo, servidor o dispositivo asociado al servidor de supervisión.

8.  Haga clic con el botón secundario en el servidor de supervisión y luego haga clic en **eliminar**.

9.  En **eliminar almacenes**dependientes, haga clic en **Aceptar**.

10. Publique la topología, compruebe el estado de la replicación y ejecute el Asistente para la implementación de Lync Server según sea necesario.

</div>

</div>

<span> </span>

</div>

</div>

</div>

