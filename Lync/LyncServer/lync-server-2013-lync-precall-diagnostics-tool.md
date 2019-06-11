---
title: 'Lync Server 2013: herramienta de diagnóstico de PRELLAMADA de Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Lync PreCall Diagnostics Tool
ms:assetid: 0ff291ec-cfb4-43eb-b5d6-a7a325681e3f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn451255(v=OCS.15)
ms:contentKeyID: 56708404
ms.date: 11/04/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e22b542a5840714455d4abdb0a7163e6a8ba748
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834926"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="lync-precall-diagnostics-tool-in-lync-server-2013"></a>Herramienta de diagnóstico de PRELLAMADA de Lync en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2016-11-04_

La herramienta de diagnóstico de PRELLAMADA de Lync (PCD) es una aplicación basada en cliente que le permite ver cómo el estado actual de su red puede influir en la calidad del audio en una próxima llamada de telefonía empresarial.

PCD es más útil en situaciones en las que es probable que el último salto de una red sea el más débil (por ejemplo, con equipos portátiles en una red WiFi pública o usuarios domésticos). PCD crea una pequeña secuencia de paquetes que atraviesa esta pierna final de la red. Después, la herramienta analiza la secuencia de paquetes para estimar cómo la vibración y la pérdida de este segmento pueden influir en la calidad de la llamada y, a continuación, proporciona un informe. Puede ejecutar PCD continuamente en el cliente, incluso mientras se están colocando las llamadas. La secuencia de paquetes no tiene un efecto significativo en el ancho de banda.

**La última versión del PCD, versión 1,1, incluye las siguientes mejoras:**

  - Compatibilidad con contraseñas más largas, que ahora pueden tener hasta 127 caracteres

  - Diagnósticos adicionales para problemas de inicio de sesión de autenticación

  - Mejor compatibilidad para implementaciones híbridas de Lync

  - Actualizaciones del selector de credenciales

  - Mejoras en la estabilidad

Agradecemos todos los comentarios. Envía todas las preguntas o problemas de soporte al alias de [comentarios PCD](mailto:pcdfb@microsoft.com) en <pcdfb@microsoft.com>.

Este tema incluye las secciones siguientes:

  - Versiones de PCD de Lync

  - Requisitos del sistema de Lync PCD

  - Características de PCD de Lync

  - Ejecución de PCD de Lync

  - Desinstalar PCD de Lync

<span id="Version"></span>

<div>

## <a name="lync-pcd-versions"></a>Versiones de PCD de Lync

En este tema se describen las siguientes versiones de la herramienta, disponibles para su descarga gratis:

  - Aplicación de escritorio de[http://go.microsoft.com/fwlink/?LinkId=327914](http://go.microsoft.com/fwlink/p/?linkid=327914)Windows ()

</div>

<span id="Requirements"></span>

<div>

## <a name="lync-pcd-system-requirements"></a>Requisitos del sistema de Lync PCD

<div>


> [!NOTE]  
> PCD requiere que la API Web de comunicaciones unificadas (UCWA) se instale y configure para admitir clientes móviles en la implementación de Lync Server. UCWA se instala con Lync Server.



</div>

<div>

## <a name="windows-desktop-app-requirements"></a>Requisitos de la aplicación de escritorio de Windows

  - Cualquier versión del sistema operativo Windows 7 o Windows 8

  - Microsoft .NET Framework 4,5 está disponible en[http://go.microsoft.com/fwlink/?LinkId=327790](http://go.microsoft.com/fwlink/p/?linkid=327790)

</div>

</div>

<span id="features"></span>

<div>

## <a name="lync-pcd-features"></a>Características de PCD de Lync

El PCD de Lync incluye las características siguientes:

  - Ejecutar en forma predeterminada a petición (2 minutos de ráfagas)

  - Ejecutar en modo siempre activo (hasta 24 horas en la vista acoplada)

  - Vista histórica de las ejecuciones de pruebas

  - Diagnosticar errores de inicio de sesión (PCD de Lync para Windows 8 solamente)

![Captura de pantalla de características de PCD de Lync] (images/Dn451255.7e0eb891-1481-47ae-8d63-164468f69c96(OCS.15).png "Captura de pantalla de características de PCD de Lync")

  - Vista gráfica de métricas de red: MOS de red, pérdida de paquetes e vibración de la interrecepción en la vista de pantalla completa y acoplada.

**Vista pantalla completa**

![Gráficos de resultados de pruebas] de la herramienta de diagnóstico prellamar (images/Dn451255.5d01fd94-9e59-4823-96c7-7a1c83dd7d31(OCS.15).png "Gráficos de resultados de pruebas") de la herramienta de diagnóstico prellamar

**Vista acoplada**

![Resultados de pruebas de uso de la herramienta de diagnóstico PRELLAMADA] (images/Dn451255.30501ba7-22d1-4db1-9297-56cf7dc6721c(OCS.15).png "Resultados de pruebas de uso de la herramienta de diagnóstico PRELLAMADA")

</div>

<span id="running"></span>

<div>

## <a name="running-lync-pcd"></a>Ejecución de PCD de Lync

<div>

## <a name="running-windows-desktop-app"></a>Ejecutando la aplicación de escritorio de Windows

1.  Para iniciar el PCD en un sistema Windows 7, seleccione **diagnósticos** de PRELLAMADA en el menú **Inicio** .
    
    Para iniciar el PCD en un sistema Windows 8, seleccione el icono de la pantalla de inicio o busque "diagnósticos de PRELLAMADA".
    
    ![Icono] de la herramienta de diagnóstico de PRELLAMADA (images/Dn451255.c9800fde-54f6-4efe-bb35-1a38064ec380(OCS.15).png "Icono") de la herramienta de diagnóstico de PRELLAMADA

2.  Cuando se inicie la herramienta, seleccione el método preferido para proporcionar credenciales y seleccione el modo de funcionamiento de red en el cuadro de diálogo Opciones de la **herramienta de diagnóstico PRELLAMADA** y, a continuación, seleccione **Aceptar**:

3.  Seleccione el botón **iniciar prueba** para empezar a ejecutar diagnósticos.
    
    Si seleccionó la opción **usar credenciales de red** , la prueba se iniciará inmediatamente.
    
    Si seleccionó la opción **permitir especificar mis credenciales** , se abrirá el cuadro de diálogo **seguridad de Windows** . Después de escribir sus credenciales, se inicia la prueba.

</div>

</div>

<span id="uninstall"></span>

<div>

## <a name="uninstalling-lync-pcd"></a>Desinstalar PCD de Lync

Para quitar el PCD de Lync, siga el procedimiento correspondiente a su sistema operativo:

  - En un sistema Windows 7, abra el **Panel de control**, seleccione **programas y características**y haga doble clic en diagnósticos de prellamada de **Lync 2013**.

  - En un sistema Windows 8, haga clic con el botón derecho en el mosaico **** de PCD y haga clic en desinstalar en la barra de aplicaciones de la parte inferior de la pantalla de inicio.

</div>

</div>

<span> </span>

</div>

</div>

</div>

