---
title: Quitar la asociación del servidor de archivado
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove the Archiving server association
ms:assetid: dabac157-71ee-4afe-b0b6-4a083d165ffb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721903(v=OCS.15)
ms:contentKeyID: 49733837
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c3d9de311668bd43d913b0f746470235060bafe3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499977"
---
# <a name="remove-the-archiving-server-association"></a>Quitar la asociación del servidor de archivado

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-04_

Para quitar un servidor de archivado, debe cambiar o borrar la dependencia en el grupo de servidores front-end asociado, el servidor front-end, la aplicación de sucursal con funciones de supervivencia y el servidor de sucursal con funciones de supervivencia. Edite las propiedades del grupo de servidores front-end, el servidor front-end, la aplicación de sucursal con funciones de supervivencia y el servidor de sucursal con funciones de supervivencia para eliminar la dependencia. Una vez que borre la dependencia y elimine el servidor en el generador de topologías, se le notificará que también se eliminará el objeto de almacén de base de datos asociado en Topology Builder.

<div>

## <a name="to-remove-the-archiving-server-association"></a>Para quitar la asociación del servidor de archivado

1.  Abra el servidor front-end de Lync Server 2013 y abra el generador de topologías.

2.  Navegue hasta el nodo 2010 de Lync Server.

3.  En el generador de topologías, expanda grupos de servidores **front-end Enterprise Edition**, **servidores front-end Standard Edition**o **sitios de sucursal**, en función de dónde se haya definido el servidor de archivado.

4.  Si tiene asociado un servidor de sucursal con funciones de supervivencia, expanda **sitios de sucursal**, expanda el nombre del sitio de sucursal y, a continuación, expanda aplicaciones de sucursal con funciones de **supervivencia**.
    
    <div>
    

    > [!NOTE]  
    > Las <STRONG>aplicaciones de sucursal</STRONG> con funciones de supervivencia de la interfaz de usuario se aplican a un servidor de sucursal con funciones de supervivencia y una aplicación de sucursal con funciones de supervivencia.

    
    </div>

5.  Haga clic con el botón secundario en el grupo de servidores, servidor o dispositivo asociado con el servidor de archivado y, a continuación, haga clic en **Editar propiedades**.

6.  En **Editar propiedades**, en **General**, en **Asociaciones**, desmarque la casilla **Asociar servidor de archivado** y, a continuación, haga clic en **Aceptar**.

7.  Repita el paso anterior para cualquier otro grupo de servidores, servidor o dispositivo asociado con el servidor de archivado que desee quitar.

8.  Haga clic con el botón secundario en el servidor de archivado y haga clic en **eliminar**.

9.  En **Eliminar almacenes dependientes**, haga clic en **Aceptar**.

10. Publique la topología, compruebe el estado de replicación y, a continuación, ejecute el Asistente para la implementación de Lync Server según sea necesario.

</div>

</div>

<span> </span>

</div>

</div>

</div>

