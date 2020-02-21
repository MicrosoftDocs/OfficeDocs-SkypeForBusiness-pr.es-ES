---
title: 'Lync Server 2013: restauración de datos de archivado o supervisión'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring monitoring or archiving data
ms:assetid: 60118526-13bb-4b03-803e-6ffae219d436
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202175(v=OCS.15)
ms:contentKeyID: 51541483
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e44bf1fe66aa7c03caea2ba367f425f1094a9a4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208586"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="restoring-monitoring-or-archiving-data-in-lync-server-2013"></a>Restauración de datos de supervisión o archivado en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-18_

La restauración de datos de supervisión y archivado no es necesaria para poner Lync Server en funcionamiento tras un error. Sin embargo, si los datos de supervisión y archivado son críticos para su organización, querrá restaurarlos después de volver a crear las bases de datos.

El siguiente procedimiento describe cómo usar SQL Server Management Studio para restaurar los datos de archivado o supervisión.

<div>

## <a name="to-restore-monitoring-or-archiving-data-from-a-backup-file"></a>Para restaurar datos de archivado o supervisión de un archivo de copia de seguridad

1.  Inicie sesión en el servidor que va a restaurar como miembro del grupo administradores en el equipo local o en un grupo con derechos de usuario equivalentes.

2.  Abra SQL Server Management Studio: haga clic en **Inicio**, en **todos los programas**, en **Microsoft SQL Server 2012** o en **Microsoft SQL Server 2008 R2**y, a continuación, haga clic en **SQL Server Management Studio**.

3.  En **Conectar al servidor**, conéctese a la instancia de SQL Server indicando al menos el nombre del servidor y la información de autenticación.

4.  En **Explorador de objetos**, haga clic con el botón secundario del mouse en **Bases de datos** y, a continuación, haga clic en **Restaurar base de datos**.

5.  En **Seleccionar una página**, haga clic en **General** y, a continuación, en **Base de datos de destino**, seleccione el nombre de la base de datos de la siguiente forma:
    
      - Para una base de datos de archivado, seleccione **LcsLog**.
    
      - Para una base de datos de registros de detalles de las llamadas (CDR), seleccione **LcsCDR**.
    
      - Para una base de datos de calidad de la experiencia (QoE), seleccione **QoEMetrics**.

6.  Haga clic en **Dispositivos de origen**.

7.  En **Seleccionar los conjuntos de copia de seguridad que se van a restaurar**, haga clic en el archivo de copia de seguridad y, a continuación, haga clic en **Restaurar**.

8.  En **Seleccionar una página**, haga clic en **Opciones**, compruebe que la ruta del archivo de datos y la ruta del registro se encuentran en la carpeta correcta y, a continuación, haga clic en **Aceptar**.

</div>

<div>

## <a name="to-make-sure-that-access-control-lists-acls-are-correct"></a>Para asegurarse de que las listas de control de acceso (ACL) son correctas

1.  Expanda **Bases de datos**, expanda la base de datos de archivado o supervisión, expanda **Seguridad** y, a continuación, expanda **Usuarios**.

2.  Compruebe que el grupo de dominio RTCComponentUniversalServices existe como usuario.

3.  Si RTCComponentUniversalServices no existe en **usuarios**, haga lo siguiente:
    
    1.  Haga clic con el botón secundario en **Usuarios** y haga clic en **Nuevo usuario**.
    
    2.  En **nombre de inicio de sesión**, escriba el nombre del grupo que falta, RTCComponentUniversalServices.
    
    3.  En **Miembros del rol de base de datos**, seleccione el permiso **ServerRole** y, a continuación, haga clic en **Aceptar**.
    
    <div>
    

    > [!NOTE]  
    > No será necesario reiniciar el servicio de archivado o supervisión.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

