---
title: 'Lync Server 2013: Instalar el almacén de configuración local'
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
ms.openlocfilehash: e4af6d4b6dfe203f69a6b104b6ade636d2658178
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726190"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-the-local-configuration-store-in-lync-server-2013"></a>Instalar el almacén de configuración local en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-06-27_

Antes de seguir estos pasos, asegúrese de que ha iniciado sesión en el servidor con una cuenta de usuario de dominio que es un administrador local y un miembro del grupo RTCUniversalReadOnlyAdmin.

Para poder hacer cualquier cosa con el Asistente para la implementación de Lync Server, necesitamos que el almacén de configuración local exista en un servidor. El almacén de configuración local es una copia de solo lectura del almacén de administración central, que se crea después de la instalación local de SQL Server Express. El almacén de administración central se agrega a la base de datos de SQL Server existente instalada en el servidor Standard Edition o en una base de datos basada en SQL Server Express.

<div>


> [!IMPORTANT]  
> Si aún no ha ejecutado el programa de instalación de Lync Server 2013 en este servidor, se le pedirá una unidad y una ruta de acceso para instalar Lync Server 2013 en. Esto le permitirá instalar en una unidad distinta de la del sistema, si su organización lo requiere, o si tiene problemas de espacio. Puede cambiar la ruta de acceso de la ubicación de instalación de los archivos de Lync Server en el cuadro de diálogo de configuración a una nueva unidad disponible. Si instala los archivos de instalación en esta ruta de acceso, incluido OCSCore. msi, el resto de los archivos de Lync Server 2013 se implementarán también.



</div>

<div>

## <a name="to-install-the-local-configuration-store"></a>Para instalar el almacén de configuración local

1.  Desde los medios de instalación, vaya \\a\\instalar\\AMD64 Setup. exe y haga clic en **Aceptar**.

2.  Si se le pide que instale el paquete redistribuible de Microsoft Visual C++ 2012, haga clic en **sí**.

3.  En la página **Ubicación de instalación de Lync Server 2013** , haga clic en **Aceptar**.

4.  En la página contrato de licencia para el **usuario final** , revise los términos de licencia, deberá seleccionar **acepto las condiciones del contrato de licencia**y, a continuación, hacer clic en **Aceptar** para poder continuar.

5.  En la página Asistente para la implementación, haga clic en **instalar o actualizar el sistema de Lync Server**.

6.  En la página de **Lync Server 2013** , junto a **STEP1: instalar el almacén de configuración local**, haga clic en **Ejecutar**.

7.  En la página **Instalar almacén de configuración local**, asegúrese de que la opción **Recuperar directamente del Almacén de administración central** esté seleccionada y luego haga clic en **Siguiente**.

8.  Cuando la instalación de configuración del servidor local haya finalizado, haga clic en **Finalizar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

