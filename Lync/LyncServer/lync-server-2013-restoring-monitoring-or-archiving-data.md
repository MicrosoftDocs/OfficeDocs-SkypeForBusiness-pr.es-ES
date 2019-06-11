---
title: 'Lync Server 2013: restaurar o archivar datos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restoring monitoring or archiving data
ms:assetid: 60118526-13bb-4b03-803e-6ffae219d436
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202175(v=OCS.15)
ms:contentKeyID: 51541483
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 803cb6050d4230653a13f1e3e66c2a092911c509
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822387"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-monitoring-or-archiving-data-in-lync-server-2013"></a>Restaurar o archivar datos en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-18_

La restauración de datos de supervisión y archivado no es necesaria para que Lync Server funcione correctamente después de un error. Sin embargo, si la supervisión y el archivado de datos son esenciales para su organización, querrá restaurar los datos después de volver a crear las bases de datos.

En el procedimiento siguiente se describe cómo usar SQL Server Management Studio para restaurar o archivar datos.

<div>

## <a name="to-restore-monitoring-or-archiving-data-from-a-backup-file"></a>Para restaurar datos de supervisión o de archivado desde un archivo de copia de seguridad

1.  Inicie sesión en el servidor que va a restaurar como miembro del grupo administradores en el equipo local o en un grupo con derechos de usuario equivalentes.

2.  Abra SQL Server Management Studio: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft SQL Server 2012** o **Microsoft SQL Server 2008 R2**y, a continuación, haga clic en **SQL Server Management Studio**.

3.  En **conectar con el servidor**, conéctese a la instancia de SQL Server proporcionando al menos el nombre del servidor y la información de autenticación.

4.  En el **Explorador de objetos**, haga clic con el botón secundario en **bases**de datos y luego haga clic en **restaurar base de datos**.

5.  En **seleccionar una página**, haga clic en **General**y, a continuación, en **base de datos** Seleccione el nombre de la base de datos de la siguiente manera:
    
      - Para una base de datos de archivado, seleccione **LcsLog**.
    
      - Para obtener una base de datos de grabación de detalles de llamadas (CDR), seleccione **LcsCDR**.
    
      - Para obtener una base de datos de calidad de la experiencia (QoE), seleccione **QoEMetrics**.

6.  Haga clic en **desde dispositivo**.

7.  En **seleccionar los conjuntos de copia de seguridad que se restaurarán**, haga clic en el archivo de copia de seguridad y luego en **restaurar**.

8.  En **seleccionar una página**, haga clic en **Opciones**, compruebe que la ruta del archivo de datos y la ruta de registro estén en la carpeta correcta y, a continuación, haga clic en **Aceptar**.

</div>

<div>

## <a name="to-make-sure-that-access-control-lists-acls-are-correct"></a>Para asegurarse de que las listas de control de acceso (ACL) sean correctas

1.  Expanda **bases**de datos, expanda la base de datos de archivado o supervisión, expanda **seguridad**y, a continuación, expanda **usuarios**.

2.  Compruebe que el grupo de dominio RTCComponentUniversalServices existe como usuario.

3.  Si RTCComponentUniversalServices no existe en **usuarios**, haga lo siguiente:
    
    1.  Haga clic con el botón secundario en **usuarios**y luego haga clic en **nuevo usuario**.
    
    2.  En **nombre de inicio de sesión**, escriba el nombre del grupo que falta, RTCComponentUniversalServices.
    
    3.  En pertenencia al rol de la **** **base de datos**, seleccione el permiso y haga clic en **Aceptar**.
    
    <div>
    

    > [!NOTE]  
    > No es necesario que reinicie el servicio de archivado o supervisión.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

