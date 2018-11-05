---
title: Herramienta PreCall Diagnostics de Lync en Lync Server 2013
TOCTitle: Herramienta PreCall Diagnostics de Lync en Lync Server 2013
ms:assetid: 0ff291ec-cfb4-43eb-b5d6-a7a325681e3f
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Dn451255(v=OCS.15)
ms:contentKeyID: 59602832
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Herramienta PreCall Diagnostics de Lync en Lync Server 2013

 

_**Última modificación del tema:** 2016-12-08_

La herramienta PreCall Diagnostics (PCD) de Lync es una aplicación basada en el cliente que le permite ver el modo en que el estado actual de la red puede afectar a la calidad del audio en la próxima llamada de Telefonía IP empresarial.

La PCD es muy útil en situaciones donde es probable que el último acceso de una red sea el más débil (por ejemplo, al usar un portátil en una red Wi-Fi pública o usuarios domésticos). La PCD crea una secuencia de paquetes pequeños que atraviesa este último tramo de la red. La herramienta analiza la secuencia de paquetes para estimar cómo pueden afectar a la calidad de la llamada la vibración y la pérdida existentes en este tramo, y luego elabora un informe. Se puede ejecutar continuamente en el cliente aunque se estén haciendo llamadas. La secuencia de paquetes no tiene efectos significativos sobre el ancho de banda.

**La última versión de la PCD, 1.1, incluye las siguientes mejoras:**

  - Admite contraseñas más largas, que pueden tener hasta 127 caracteres

  - Diagnósticos adicionales para problemas de autenticación de inicio de sesión

  - Más soporte para las implementaciones híbridas de Lync

  - Actualizaciones del seleccionador de credenciales

  - Mejoras de estabilidad

Todos los comentarios son bienvenidos. Envíenos sus dudas o preguntas de soporte técnico al alias [Comentarios sobre PCD](mailto:pcdfb@microsoft.com) en la dirección <pcdfb@microsoft.com>.

Este tema incluye las secciones siguientes:

  - Versiones de PCD de Lync

  - Requisitos del sistema para PCD de Lync

  - Características de la PCD de Lync

  - Ejecutar PCD de Lync

  - Desinstalar PCD de Lync

## Versiones de PCD de Lync

Este tema describe las siguientes versiones de la herramienta, que se pueden bajar gratuitamente:

  - Aplicación de escritorio para Windows ([http://go.microsoft.com/fwlink/?LinkId=327914](http://go.microsoft.com/fwlink/p/?linkid=327914))

  - Aplicación para Windows 8 Modern ([http://go.microsoft.com/fwlink/?LinkId=322110](http://go.microsoft.com/fwlink/p/?linkid=322110))


> [!NOTE]
> Los usuarios de Lync para Office 365 pueden usar las dos versiones de la PCD.



Si quiere usar una versión anterior de la PCD, vea lo siguiente:

  - La versión de 32 bits de la PCD se puede bajar gratis desde el Centro de descarga de Microsoft en [Office Communications Server 2007 R2: herramienta del kit de recursos PreCallDiagnostic (32 bits)](http://go.microsoft.com/fwlink/p/?linkid=164769).

  - La versión de 64 bits de la PCD se incluye con las herramientas de Office Communications Server 2007 R2, que se pueden bajar gratis desde el Centro de descarga de Microsoft en [Office Communications Server 2007 R2: herramientas del kit de recursos](http://go.microsoft.com/fwlink/p/?linkid=145159).

## Requisitos del sistema para PCD de Lync


> [!NOTE]
> La PCD requiere que la API web de comunicaciones unificadas (UCWA) esté instalada y configurada para admitir clientes móviles en la implementación de Lync Server. UCWA se instala con Lync Server.



## Requisitos de la aplicación de escritorio para Windows

  - Cualquier edición del sistema operativo Windows 7 o Windows 8

  - Microsoft .NET Framework 4.5 disponible en [http://go.microsoft.com/fwlink/?LinkId=327790](http://go.microsoft.com/fwlink/p/?linkid=327790)

## Requisitos de la aplicación para Windows 8 Modern

  - Cualquier edición del sistema operativo Windows 8

  - Microsoft .NET Framework 4.5 disponible en [http://go.microsoft.com/fwlink/?LinkId=327790](http://go.microsoft.com/fwlink/p/?linkid=327790)

## Características de la PCD de Lync

La PCD de Lync tiene las características siguientes:

  - Se ejecuta, de manera predeterminada, bajo demanda (ráfagas de 2 minutos)

  - Se puede ejecutar en el modo Siempre activada (hasta 24 horas en la vista acoplada)

  - Vista histórica de las series de pruebas

  - Diagnóstico de los errores de inicio de sesión (PCD de Lync solo para Windows 8)

![Captura de pantalla del progreso de inicio de sesión en las características PCD de Lync](images/Dn451255.7e0eb891-1481-47ae-8d63-164468f69c96(OCS.15).png "Captura de pantalla del progreso de inicio de sesión en las características PCD de Lync")

  - Vista gráfica de las métricas de la red: MOS de red, pérdida de paquetes y vibración entre llegadas en pantalla completa y vista acoplada.

**Vista de pantalla completa**

![Gráficos de los resultados de las pruebas de la herramienta de diagnóstico previo a la llamada](images/Dn451255.5d01fd94-9e59-4823-96c7-7a1c83dd7d31(OCS.15).png "Gráficos de los resultados de las pruebas de la herramienta de diagnóstico previo a la llamada")

**Vista acoplada**

![Resultados de la prueba de utilización de la herramienta de diagnóstico previo a la llamada](images/Dn451255.30501ba7-22d1-4db1-9297-56cf7dc6721c(OCS.15).png "Resultados de la prueba de utilización de la herramienta de diagnóstico previo a la llamada")

## Ejecutar PCD de Lync

## Ejecutar la aplicación de escritorio para Windows

1.  Para iniciar la PCD en un sistema Windows 7, seleccione **PreCall Diagnostics** en el menú **Inicio**.
    
    Para iniciar la PCD en un sistema Windows 8, seleccione el icono de la pantalla de Inicio o busque "PreCall Diagnostics".
    
    ![Icono de la herramienta de diagnóstico previo a la llamada](images/Dn451255.c9800fde-54f6-4efe-bb35-1a38064ec380(OCS.15).png "Icono de la herramienta de diagnóstico previo a la llamada")

2.  Cuando la herramienta se inicie, seleccione el método que prefiera para indicar las credenciales, seleccione el modo de funcionamiento de la red en el cuadro de diálogo **Opciones de la herramienta PreCall Diagnostics** y seleccione **Aceptar**:

3.  Seleccione el botón **Iniciar prueba** para empezar a ejecutar el diagnóstico.
    
    Si seleccionó la opción **Usar credenciales de red**, la prueba empieza inmediatamente.
    
    Si seleccionó la opción **Escribir las credenciales**, se abre el cuadro de diálogo **Seguridad de Windows**. Cuando introduce las credenciales, empieza la prueba.

## Ejecutar la aplicación para Windows 8 Modern


1.  Para iniciar la PCD, seleccione el icono de la pantalla de Inicio o busque "PreCall Diagnostics".
    
    ![Icono de la herramienta de diagnóstico previo a la llamada](images/Dn451255.c9800fde-54f6-4efe-bb35-1a38064ec380(OCS.15).png "Icono de la herramienta de diagnóstico previo a la llamada")

2.  Cuando la herramienta se inicie, escriba las credenciales de Lync y seleccione **Aceptar**.
    
    ![Inicio de sesión en la herramienta de diagnóstico previo a la llamada de Lync](images/Dn451255.88039914-4c68-48f6-a9fa-58cb4e3f3488(OCS.15).jpg "Inicio de sesión en la herramienta de diagnóstico previo a la llamada de Lync")

3.  Seleccione el botón **Iniciar prueba** para empezar a ejecutar el diagnóstico.

## Desinstalar PCD de Lync

Para quitar la PCD de Lync, siga los pasos correspondientes a su sistema operativo:

  - En un sistema Windows 7, abra el **Panel de control**, seleccione **Programas y características**, y haga doble clic en **Lync 2013 PreCall Diagnostics**.

  - En un sistema Windows 8, haga clic con el botón secundario en el icono de la PCD y haga clic en **Desinstalar** en la barra de aplicaciones de la parte inferior de la pantalla de Inicio.

