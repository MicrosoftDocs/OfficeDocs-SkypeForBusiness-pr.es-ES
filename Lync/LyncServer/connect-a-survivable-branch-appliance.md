---
title: Conectar una aplicación de sucursal con funciones de supervivencia
description: Conecte una aplicación de sucursal con funciones de supervivencia.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Connect a Survivable Branch Appliance
ms:assetid: fe3167e2-d1b1-4cd4-bf30-262e0e7d14e8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721948(v=OCS.15)
ms:contentKeyID: 49733886
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f5bbf9e1a4189d3c80d6dec449adf68b82cd3691
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550286"
---
# <a name="connect-a-survivable-branch-appliance"></a>Conectar una aplicación de sucursal con funciones de supervivencia

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2012-10-19_

Cada aplicación de sucursal con funciones de supervivencia (SBA) está asociada a un grupo de servidores front-end que sirve como registrador de copias de seguridad para SBA. Cuando el grupo de servidores front-end se migra a Lync Server 2013, SBA debe estar desasociado del grupo de servidores front-end de Lync Server 2010 mientras se actualiza el grupo, una vez que el grupo se ha migrado a Lync Server 2013, la SBA se puede volver a asociar con el grupo de servidores front-end actualizado. Esto implica eliminar la SBA de la topología de Lync Server 2010 heredada en el generador de topologías y, a continuación, agregar la SBA a la topología de Lync Server 2013. Los usuarios hospedados en el servidor de Lync Server 2010 SBA deben moverse primero a otro grupo de servidores front-end antes de quitar SBA de la topología. Una vez agregada SBA a la topología de Lync Server 2013, estos usuarios pueden volver a moverse a SBA. Estos pasos se sintetizan a continuación:

1.  Mueva los usuarios de sucursal alojados en el servidor de Lync Server 2010 heredado a otro grupo de servidores front-end.

2.  Quite SBA de la topología heredada de Lync Server 2010 para desconectar el grupo de servidores front-end existente como registrador de reserva.

3.  Agregue SBA a la topología de Lync Server 2013 y configure este nuevo grupo de servidores front-end como registrador de reserva.

4.  Mueva los usuarios de sucursal al nuevo SBA de Lync Server 2013.

**Agregar un sitio de sucursal SBA de Lync Server 2010 a la topología**

1.  Abrir **Generador de topologías**.

2.  En el panel de la izquierda, hacer clic con el botón secundario en **Sitios de sucursal** y, a continuación, en **Nuevo sitio de sucursal**.

3.  En el cuadro de diálogo **Definir nuevo sitio de sucursal**, haga clic en **Nombre ** y escriba el nombre del sitio de sucursal.

4.  (Opcional) Haga clic en **Descripción ** y escriba una descripción significativa para el sitio de sucursal.

5.  Haga clic en **Siguiente**.

6.  (Opcional) En el siguiente cuadro de diálogo **Definir nuevo sitio de sucursal**, realice una de las siguientes acciones:
    
    1.  Haga clic en **Ciudad** y escriba el nombre de la ciudad en la se ubica el sitio de sucursal.
    
    2.  Haga clic en **Provincia o región** y escriba el nombre de la provincia o la región en la que se ubica el sitio de sucursal.
    
    3.  Haga clic en **código de país** y escriba el código telefónico de dos dígitos del país o la región en el que se ubica el sitio de sucursal.

7.  Haga clic en **Siguiente** y, a continuación, siga uno de estos procedimientos:
    
    1.  Si utiliza una aplicación o un servidor de sucursal con funciones de supervivencia de Lync 2010 en este sitio, no olvide desactivar la opción **Abrir el Asistente con nuevas funciones de supervivencia cuando se cierre el asistente**. Haga clic en **Finalizar**.

8.  Para asociar el SBA heredado de Lync Server 2010 al grupo de servidores front-end de Lync Server 2013:
    
    1.  Expanda el sitio de sucursal que ha creado.
    
    2.  Haga clic con el botón secundario en **Lync Server 2010** y, a continuación, en **Nuevo**.
    
    3.  Haga clic en **Aplicación de sucursal con funciones de supervivencia…**

9.  Siga las indicaciones del asistente que se abrirá. Para obtener información sobre los elementos del asistente, consulte [definir una aplicación o un servidor de sucursal con funciones de supervivencia en Lync Server 2013](lync-server-2013-define-a-survivable-branch-appliance-or-server.md).
    
    <div>
    

    > [!NOTE]  
    > Una aplicación de sucursal con funciones de supervivencia de Lync Server 2010 solo se puede asociar a un almacén de supervisión de Lync Server 2010.

    
    </div>

10. Si no usa una aplicación o un servidor de sucursal con funciones de supervivencia en este sitio, desactive la casilla **Abrir el Asistente con nuevas funciones de supervivencia cuando se cierre este asistente** y haga clic en **Finalizar**.

11. Repita los pasos anteriores para cada sitio de sucursal que desee agregar a la topología.

</div>

<span> </span>

</div>

</div>

</div>

