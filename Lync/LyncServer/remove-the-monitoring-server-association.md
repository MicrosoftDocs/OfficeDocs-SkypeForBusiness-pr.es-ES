---
title: Quitar la Asociación del servidor de supervisión
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove the Monitoring server association
ms:assetid: c45b22ae-fc06-484a-a05b-735bd1bb7448
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721877(v=OCS.15)
ms:contentKeyID: 49733810
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 746558cc47a7ed5ef7f59abe4e4f0771cc514d47
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008866"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-the-monitoring-server-association"></a>Quitar la Asociación del servidor de supervisión

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-04_

Para quitar el servidor de supervisión, debe cambiar o borrar la dependencia en el grupo de servidores front-end asociado, el servidor front-end, la aplicación de sucursal con funciones de supervivencia y el servidor de sucursal con funciones de supervivencia. Edite las propiedades del grupo de servidores front-end, el servidor front-end, la aplicación de sucursal con funciones de supervivencia y el servidor de sucursal con funciones de supervivencia para eliminar la dependencia. Una vez que borre la dependencia y elimine el servidor en el generador de topologías, se le notificará que también se eliminará el objeto de almacén de base de datos asociado en Topology Builder.

<div>

## <a name="to-remove-the-monitoring-server-association"></a>Para quitar la asociación del Servidor de supervisión:

1.  Abra el servidor front-end de Lync Server 2013 y abra el generador de topologías.

2.  Navegue hasta el nodo 2010 de Lync Server.

3.  En el generador de topologías, expanda grupos de servidores **front-end Enterprise Edition**, **servidores front-end Standard Edition**o **sitios de sucursal**, en función de dónde se haya definido el servidor de supervisión.

4.  Si tiene asociado un servidor de sucursal con funciones de supervivencia, expanda **sitios de sucursal**, expanda el nombre del sitio de sucursal y, a continuación, expanda aplicaciones de sucursal con funciones de **supervivencia**.
    
    <div>
    

    > [!NOTE]  
    > Las <STRONG>aplicaciones de sucursal</STRONG> con funciones de supervivencia de la interfaz de usuario se aplican a un servidor de sucursal con funciones de supervivencia y una aplicación de sucursal con funciones de supervivencia.

    
    </div>

5.  Haga clic con el botón secundario en el grupo de servidores, servidor o dispositivo asociado con el servidor de supervisión y, a continuación, haga clic en **Editar propiedades**.

6.  En **Editar propiedades**, bajo **General** y **Asociaciones**, desactive la casilla **Asociar servidor de supervisión** y haga clic en **Aceptar**.

7.  Repita el paso anterior para cualquier otro grupo de servidores, servidor o dispositivo asociado con el servidor de supervisión.

8.  Haga clic con el botón secundario en el servidor de supervisión y haga clic en **eliminar**.

9.  En **Eliminar almacenes dependientes**, haga clic en **Aceptar**.

10. Publique la topología, compruebe el estado de la replicación y ejecute el Asistente para la implementación de Lync Server según sea necesario.

</div>

</div>

<span> </span>

</div>

</div>

</div>

