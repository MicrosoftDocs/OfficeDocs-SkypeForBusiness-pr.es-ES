---
title: 'Lync Server 2013: instalar el almacén de configuración local'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install the Local Configuration store
ms:assetid: b563030d-d338-411f-9611-28d5eb4b3238
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412874(v=OCS.15)
ms:contentKeyID: 48185180
ms.date: 06/28/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e16d4edfb53511712c58cb41510559fcf69cfa9a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498577"
---
# <a name="install-the-local-configuration-store-in-lync-server-2013"></a>Instalar el almacén de configuración local en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-06-27_

Antes de seguir estos pasos, asegúrese de que ha iniciado sesión en el servidor con una cuenta de usuario de dominio que sea un administrador local y un miembro del grupo al rtcuniversalreadonlyadmin.

Para poder realizar cualquier acción con el Asistente para la implementación de Lync Server, es necesario que el almacén de configuración local exista en un servidor. El almacén de configuración local es una copia de solo lectura del almacén de administración central, que se crea después de la instalación local de SQL Server Express. El propio almacén de administración central se agrega a la base de datos de SQL Server existente instalada en el servidor Standard Edition o en la base de datos basada en SQL Server Express.

<div>


> [!IMPORTANT]  
> Si no ha ejecutado el programa de instalación de Lync Server 2013 en este servidor, se le pedirá una unidad y una ruta de acceso para instalar Lync Server 2013 en. Esto le permitirá instalar en una unidad distinta de la unidad del sistema, si su organización la necesita, o si tiene problemas de espacio. Solo puede cambiar la ruta de acceso de la ubicación de instalación para los archivos de Lync Server en el cuadro de diálogo de instalación a una unidad nueva y disponible. Si instala los archivos de instalación en esta ruta de acceso, incluido OCSCore.msi, también se implementará el resto de los archivos de Lync Server 2013.



</div>

<div>

## <a name="to-install-the-local-configuration-store"></a>Para instalar el almacén de configuración local

1.  En los medios de instalación, vaya a \\ setup \\ AMD64 \\Setup.exe y, a continuación, haga clic en **Aceptar**.

2.  Si se le pide que instale el paquete redistribuible de Microsoft Visual C++ 2012, haga clic en **sí**.

3.  En la página **Ubicación de instalación de Lync Server 2013** , haga clic en **Aceptar**.

4.  En la página contrato de licencia para el **usuario final** , revise los términos de licencia, debe seleccionar **acepto los términos del contrato de licencia**y, a continuación, haga clic en **Aceptar** para poder continuar.

5.  En la página del asistente para la implementación, haga clic en **Instalar o actualizar el sistema Lync Server**.

6.  En la página **Lync Server 2013** , junto a **paso 1: instalar almacén de configuración local**, haga clic en **Ejecutar**.

7.  En la página **instalar el almacén de configuración local** , asegúrese de que la opción **recuperar directamente del almacén de administración central** esté seleccionada y, a continuación, haga clic en **siguiente**.

8.  Una vez completada la instalación de configuración del servidor local, debe hacer clic en **Finalizar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

