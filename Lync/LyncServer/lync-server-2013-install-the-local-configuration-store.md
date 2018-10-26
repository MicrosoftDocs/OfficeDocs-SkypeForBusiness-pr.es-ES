---
title: 'Lync Server 2013: Instalar el almacén de configuración local'
TOCTitle: Instalar el almacén de configuración local
ms:assetid: b563030d-d338-411f-9611-28d5eb4b3238
ms:mtpsurl: https://technet.microsoft.com/es-es/library/Gg412874(v=OCS.15)
ms:contentKeyID: 48276420
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Instalar el almacén de configuración local en Lync Server 2013

 

_**Última modificación del tema:** 2014-06-27_

Antes de seguir estos pasos, asegúrese de que ha iniciado sesión en el servidor con una cuenta de usuario del dominio que sea administrador local y miembro del grupo RTCUniversalReadOnlyAdmins.

Para poder hacer todo cualquier cosa con la Asistente para la implementación de Lync Server, tiene que existir el almacén de configuración local en el servidor. El almacén de configuración local es una copia de solo lectura del Almacén de administración central, que se crea después de la instalación local de SQL Server Express. El propio Almacén de administración central se agrega a la base de datos SQL Server existente instalada en la base de datos de Servidor Standard Edition o basada en SQL Server Express.

> [!IMPORTANT]  
> Si no ha ejecutado la configuración de Lync Server 2013 en este servidor antes, se le pedirá una unidad y una ruta para instalar Lync Server 2013. Esto le permitirá instalarlo en una unidad diferente a la del sistema, si su organización lo requiere o si tiene problemas de espacio. Simplemente puede cambiar la ruta de ubicación de la instalación para los archivos de servidor Lync en el cuadro de diálogo Configuración. Si instala los archivos de instalación en esta ruta de acceso, incluido el archivo OCSCore.msi, el resto de los archivos de Lync Server 2013 se implementará también en esta unidad.



## Para instalar el almacén de configuración local

1.  En el disco de instalación, vaya a \\setup\\amd64\\Setup.exe y haga clic en **Aceptar**.

2.  Si se le pide que instale Microsoft Visual C++ 2008 distribuible, haga clic en **Sí**.

3.  En la página **Lync Server 2013Ubicación de la instalación**, haga clic en **Aceptar**.

4.  En la página **Contrato de licencia para el usuario final**, lea los términos de la licencia, tendrá que seleccionar **Acepto los términos del contrato de licencia** y luego haga clic en **Aceptar** para continuar.

5.  En la página del asistente para la implementación, haga clic en **Instalar o actualizar el sistema Lync Server** .

6.  En la página **Lync Server 2013**, junto a **Paso 1: Instalar almacén de configuración local**, haga clic en **Ejecutar**.

7.  En la página **Instalar almacén de configuración local**, asegúrese de que la opción **Recuperar directamente del Almacén de administración central** está seleccionada y luego haga clic en **Siguiente**.

8.  Una vez completado el proceso de instalación de configuración del servidor local, debe hacer clic en **Finalizar**.

