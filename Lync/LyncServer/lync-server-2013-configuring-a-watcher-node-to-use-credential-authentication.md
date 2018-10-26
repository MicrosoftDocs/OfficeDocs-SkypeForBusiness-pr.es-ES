﻿---
title: "Configuración de un nodo de monitor para usar la autenticación mediante credenciales"
TOCTitle: "Conf. d’un nœud obs. pour l’util. de l’auth. des info. d’identification"
ms:assetid: 032e33f3-9483-42e6-a33c-347eb6779597
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ204632(v=OCS.15)
ms:contentKeyID: 48274263
ms.date: 01/07/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuración de un nodo de monitor para usar la autenticación mediante credenciales

 

_**Última modificación del tema:** 2012-10-20_

Si el equipo del nodo del observador se encuentra fuera de la red perimetral, debe seguir un procedimiento ligeramente diferente para configurar el nodo del observador a fin de que ejecute las transacciones sintéticas. De manera específica, no debe crear un grupo de servidores de aplicaciones de confianza y una aplicación de confianza, y debe instalar un certificado que habilita el nodo del observador para que envíe alertas a un equipo dentro de la red perimetral. Esto significa que tendrá que completar dos tareas independientes:

  - Actualizar la pertenencia al grupo Administradores de solo lectura local de RTC del equipo

  - Instalar los archivos de configuración del nodo del observador

## Actualización de la pertenencia al grupo Administradores de solo lectura local de RTC

Si su nodo de observador se encuentra fuera de la red perimetral, debe agregar la cuenta del servicio de red al grupo Administradores de solo lectura local de RTC al equipo del nodo de observador. Para ello, complete el siguiente procedimiento en el nodo de observador:

1.  Haga clic en **Inicio** , haga clic con el botón secundario en **Equipo** y, a continuación, haga clic en **Administrar** .

2.  En el Administrador de servidores, expanda **Configuración**, **Usuarios y grupos locales** y, a continuación, haga clic en **Grupos**.

3.  En el panel Grupos, haga doble clic en **RTC Local Read-only Administrators**.

4.  En el cuadro de diálogo **Propiedades de RTC Local Read-only Administrators**, haga clic en **Agregar**.

5.  En el cuadro de diálogo para **seleccionar usuarios, equipos, cuentas de servicio o grupos**, haga clic en **Ubicaciones**.

6.  En el cuadro de diálogo **Ubicaciones**, seleccione el nombre del equipo del nodo de observador y, a continuación, haga clic en **Aceptar**.

7.  En el cuadro **Escribir los nombres de objeto para seleccionar**, escriba **Servicio de red** y, a continuación, haga clic en **Aceptar**.

8.  En el cuadro de diálogo **Propiedades de RTC Local Read-only Administrators**, haga clic en **Aceptar** y, a continuación, cierre **Administrador de servidores**.

Reinicie el equipo del nodo de observador.

## Instalación de los archivos de configuración del nodo de observador

Una vez se ha iniciado el equipo del nodo de observador, el siguiente paso es ejecutar el archivo Watchernode.msi. Para ejecutar este archivo, abra el Shell de administración de Lync Server 2013 haciendo clic en **Inicio**, **Todos los programas**, **Lync Server 2013** y, a continuación, en **Shell de administración de Lync Server**. En el Shell de administración de Lync Server, escriba el siguiente comando y, a continuación, presione ENTRAR (asegúrese de especificar la ruta de acceso real a su copia de Watchernode.msi):

    C:\Tools\Watchernode.msi Authentication=Negotiate


> [!NOTE]
> Como se ha descrito con anterioridad, Watchernode.msi también se puede ejecutar desde una ventana de comando. Para abrir una ventana de comando, haga clic en <STRONG>Inicio</STRONG>, haga clic con el botón secundario en <STRONG>Símbolo del sistema</STRONG> y, a continuación, haga clic en <STRONG>Ejecutar como administrador</STRONG>. Cuando se abra la ventana del comando, escriba el mismo comando que se ha mostrado anteriormente.



El modo Negotiate se usa en cualquier momento que el nodo de observador no se puede configurar como un grupo de servidores de aplicaciones de confianza. En este modo, los administradores tendrá que administrar contraseñas de usuario de prueba en el nodo de observador.

