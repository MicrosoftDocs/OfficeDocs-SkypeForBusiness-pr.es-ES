---
title: 'Lync Server 2013: herramienta de diagnóstico de PRELLAMADA de Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync PreCall Diagnostics Tool
ms:assetid: 0ff291ec-cfb4-43eb-b5d6-a7a325681e3f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn451255(v=OCS.15)
ms:contentKeyID: 56708404
ms.date: 11/04/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0377460340e1b639a7fca5862dcd85aed399b94a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186213"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="lync-precall-diagnostics-tool-in-lync-server-2013"></a>Herramienta de diagnóstico de PRELLAMADA de Lync en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2016-11-04_

La herramienta de diagnóstico de PRELLAMADA de Lync (PCD) es una aplicación basada en cliente que le permite ver cómo el estado actual de la red puede afectar a la calidad de audio en una próxima llamada de telefonía IP empresarial.

PCD es más útil en situaciones en las que es probable que el último salto de una red sea el más débil (por ejemplo, con equipos portátiles de una red WiFi pública o usuarios domésticos). PCD crea una pequeña secuencia de paquetes que atraviesa esta pierna final de la red. A continuación, la herramienta analiza la secuencia de paquetes para estimar cómo la vibración y la pérdida a lo largo de esta sección pueden influir en la calidad de la llamada y, a continuación, proporciona un informe. Puede ejecutar PCD continuamente en el cliente, incluso mientras se colocan las llamadas. La secuencia de paquetes no tiene un efecto significativo en el ancho de banda.

**La versión más reciente del PCD, versión 1,1, incluye las siguientes mejoras:**

  - Compatibilidad con contraseñas más largas, que ahora pueden tener hasta 127 caracteres

  - Diagnósticos adicionales para problemas de inicio de sesión de autenticación

  - Mejor compatibilidad con las implementaciones híbridas de Lync

  - Actualizaciones del selector de credenciales

  - Mejoras en la estabilidad

Agradecemos cualquier comentario. Envíe todas las preguntas o problemas de soporte al alias de [comentarios PCD](mailto:pcdfb@microsoft.com) en <pcdfb@microsoft.com>.

En este tema se incluyen las siguientes secciones:

  - Versiones de PCD de Lync

  - Requisitos del sistema para PCD de Lync

  - Características de PCD de Lync

  - Ejecutar el PCD de Lync

  - Desinstalar PCD de Lync

<span id="Version"></span>

<div>

## <a name="lync-pcd-versions"></a>Versiones de PCD de Lync

En este tema se describen las siguientes versiones de la herramienta, disponibles para su descarga gratuita:

  - Aplicación de escritorio de[https://go.microsoft.com/fwlink/?LinkId=327914](https://go.microsoft.com/fwlink/p/?linkid=327914)Windows ()

</div>

<span id="Requirements"></span>

<div>

## <a name="lync-pcd-system-requirements"></a>Requisitos del sistema para PCD de Lync

<div>


> [!NOTE]  
> PCD requiere que la API Web de comunicaciones unificadas (UCWA) esté instalada y configurada para admitir clientes móviles en la implementación de Lync Server. UCWA se instala con Lync Server.



</div>

<div>

## <a name="windows-desktop-app-requirements"></a>Requisitos de la aplicación de escritorio de Windows

  - Cualquier edición del sistema operativo Windows 7 o Windows 8

  - Microsoft .NET Framework 4,5 está disponible en[https://go.microsoft.com/fwlink/?LinkId=327790](https://go.microsoft.com/fwlink/p/?linkid=327790)

</div>

</div>

<span id="features"></span>

<div>

## <a name="lync-pcd-features"></a>Características de PCD de Lync

El PCD de Lync incluye las siguientes características:

  - Ejecutar en valor predeterminado a petición (ráfagas de 2 minutos)

  - Ejecutar en modo siempre activo (hasta 24 horas en la vista acoplada)

  - Vista histórica de las ejecuciones de prueba

  - Diagnóstico de errores de inicio de sesión (PCD de Lync solo para Windows 8)

![Captura de pantalla del progreso de inicio de sesión de características de PCD en Lync](images/Dn451255.7e0eb891-1481-47ae-8d63-164468f69c96(OCS.15).png "Captura de pantalla del progreso de inicio de sesión de características de PCD en Lync")

  - Vista gráfica de métricas de red: MOS de red, pérdida de paquetes e vibración de inserción en la vista de pantalla completa y en la vista acoplada.

**Vista de pantalla completa**

![Gráficos de resultados de pruebas de herramienta de diagnóstico precall](images/Dn451255.5d01fd94-9e59-4823-96c7-7a1c83dd7d31(OCS.15).png "Gráficos de resultados de pruebas de herramienta de diagnóstico precall")

**Vista acoplada**

![Resultados de la prueba de uso de la herramienta de diagnóstico precall](images/Dn451255.30501ba7-22d1-4db1-9297-56cf7dc6721c(OCS.15).png "Resultados de la prueba de uso de la herramienta de diagnóstico precall")

</div>

<span id="running"></span>

<div>

## <a name="running-lync-pcd"></a>Ejecutar el PCD de Lync

<div>

## <a name="running-windows-desktop-app"></a>Ejecutar la aplicación de escritorio de Windows

1.  Para iniciar el PCD en un sistema con Windows 7, seleccione **diagnósticos de PRELLAMADA** del menú **Inicio** .
    
    Para iniciar PCD en un sistema con Windows 8, seleccione el icono de la pantalla Inicio o busque "diagnósticos de PRELLAMADA".
    
    ![Icono de la herramienta de diagnóstico precall](images/Dn451255.c9800fde-54f6-4efe-bb35-1a38064ec380(OCS.15).png "Icono de la herramienta de diagnóstico precall")

2.  Cuando se inicie la herramienta, seleccione el método preferido para suministrar credenciales y seleccione el modo de funcionamiento de red en el cuadro de diálogo Opciones de la **herramienta de diagnóstico PRELLAMADA** y, a continuación, seleccione **Aceptar**:

3.  Seleccione el botón **iniciar prueba** para empezar a ejecutar diagnósticos.
    
    Si seleccionó la opción **usar credenciales de red** , la prueba comienza inmediatamente.
    
    Si seleccionó la opción **permitir especificar mis credenciales** , se abrirá el cuadro de diálogo **seguridad de Windows** . Después de escribir las credenciales, la prueba se inicia.

</div>

</div>

<span id="uninstall"></span>

<div>

## <a name="uninstalling-lync-pcd"></a>Desinstalar PCD de Lync

Para quitar el PCD de Lync, siga el procedimiento para su sistema operativo:

  - En un sistema Windows 7, abra el **Panel de control**, seleccione **programas y características**y, a continuación, haga doble clic en **diagnósticos de PRELLAMADA de Lync 2013**.

  - En un sistema Windows 8, haga clic con el botón secundario en el icono de PCD y haga clic en **desinstalar** desde la barra de aplicaciones en la parte inferior de la pantalla Inicio.

</div>

</div>

<span> </span>

</div>

</div>

</div>

