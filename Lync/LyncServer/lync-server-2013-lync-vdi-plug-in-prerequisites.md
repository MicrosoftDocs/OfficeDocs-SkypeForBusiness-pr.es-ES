---
title: 'Lync Server 2013: Requisitos previos del componente de VDI de Lync'
TOCTitle: Requisitos previos del componente de VDI de Lync
ms:assetid: da25a976-7624-4dfc-b332-9c4db4ee78da
ms:mtpsurl: https://technet.microsoft.com/es-es/library/JJ205304(v=OCS.15)
ms:contentKeyID: 48276859
ms.date: 03/08/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Requisitos previos del componente de VDI de Lync en Lync Server 2013

 

_**Última modificación del tema:** 2017-03-07_

En un entorno de Infraestructura de escritorio virtual (VDI), las máquinas virtuales y el equipo local del usuario deben cumplir los requisitos que se indican en este apartado.


> [!NOTE]
> Consulte al proveedor de soluciones de virtualización para obtener más información sobre la instalación y la implementación del entorno virtualizado. Para más información sobre la implementación de un entorno virtualizado en función de los servicios de Hyper-V y de escritorio remoto, consulte los artículos siguientes en la biblioteca de TechNet de Microsoft: 
> <UL>
> <LI>
> <P>Hyper-V en <A class=uri href="http://go.microsoft.com/fwlink/?linkid=247514">http://go.microsoft.com/fwlink/?linkid=247514</A></P>
> <LI>
> <P>Servicios de escritorio remoto en Windows Server&nbsp;2008&nbsp;R2 en <A class=uri href="http://go.microsoft.com/fwlink/?linkid=247513">http://go.microsoft.com/fwlink/?linkid=247513</A></P></LI></UL>



A continuación aparecen los requisitos para las máquinas virtuales que se ejecutan en el equipo del centro de datos:

  - Las máquinas virtuales deben configurarse con Windows 8, Windows 7 o Windows Server 2008 R2 con los últimos Service Pack.

Estos son los requisitos del usuario y del equipo local del usuario:

  - El usuario debe estar hospedado en Lync Server 2013.

  - El equipo local debe ejecutar Windows Embedded Standard 7 con el SP1, Windows 7 con el SP1 o Windows 8.

  - Si usa los servicios de escritorio remoto, el valor de bits del complemento de VDI de Lync (es decir, si la aplicación es de 32 bits o de 64 bits) debe coincidir con el valor de bits del sistema operativo en el equipo local. No es necesario que coincidan el valor de bits del sistema operativo del equipo local y del sistema operativo de la máquina virtual. Si usa otra plataforma u otra solución de virtualización, consulte a su proveedor de soluciones de virtualización para informarse de los requisitos del valor de bits.

  - El equipo local debe ejecutar la última versión del cliente de escritorio remoto. Instale las últimas actualizaciones de cliente de los servicios de escritorio remoto de Microsoft o el último software cliente de escritorio remoto del proveedor de soluciones de virtualización. Para informarse de las últimas actualizaciones de los servicios de escritorio remoto, vea <http://go.microsoft.com/fwlink/?linkid=268032>.

  - En el equipo local, configure el cliente de escritorio remoto para que el audio se reproduzca en el equipo local y la grabación remota esté deshabilitada. Para configurar estos parámetros para la conexión a escritorio remoto en Windows, vea la sección siguiente, "Configuración de los parámetros de conexión al escritorio remoto".

## Configuración de los parámetros de conexión al escritorio remoto

Para preparar la conexión a escritorio remoto en Windows para el complemento de VDI de Lync, ejecute los pasos siguientes.

1.  Si el PC local ejecuta Windows 8, sáltese este paso. Si el PC local ejecuta Windows 7 con el SP1, instale la última versión de Windows 8 del cliente de los servicios de escritorio remoto, disponible en <http://go.microsoft.com/fwlink/?linkid=268032>.

2.  Inicie el cliente de servicios de escritorio remoto haciendo clic en **Iniciar** y después en **Conexión a escritorio remoto**.

3.  Haga clic en **Opciones**.

4.  Haga clic en la pestaña **Recursos locales**. En **Audio remoto**, haga clic en **Configuración** y haga lo siguiente:
    
      - En **Reproducción de audio remota**, seleccione **Reproducir en este equipo**.
    
      - En **Grabación de audio remota**, seleccione **No grabar**.
    
      - Haga clic en **Aceptar**.

5.  Haga clic en la pestaña **Experiencia**. En **Rendimiento**, desactive la casilla **Almacenamiento en caché persistente de mapas de bits**.

6.  Haga clic en la pestaña **General**. En **Equipo**, escriba el nombre de la máquina virtual y haga clic en **Conectar**.

